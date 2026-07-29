# ESP32-S3 E-Paper Calendar Dashboard

## From hardware bring-up to secure wireless updates

What began as a search for a compact, low-power Google Calendar display evolved into a fully tested embedded system built around a Waveshare ESP32-S3 development board and a 3.97-inch, 800 × 480 e-paper panel.

The original goal was deliberately practical: create an always-visible agenda for a refrigerator or desk, with excellent readability, very low standby power and no continuously illuminated screen. During development, the project grew into a broader embedded platform with Wi-Fi provisioning, live calendar data, Polish text rendering, battery monitoring, hardware diagnostics and rollback-protected firmware updates.

> **Physically validated baseline:** Wi-Fi provisioning, NTP synchronization, live Google Calendar data over certificate-verified HTTPS, bounded JSON parsing, UTF-8 rendering with Polish characters, dual-slot OTA, candidate-image validation and automatic rollback.
>
> **Current development:** persistent, physically provisioned wireless OTA authorization, a battery and USB charging indicator, and a second diagnostics screen. These additions remain under review and hardware validation.

![The current calendar prototype with the battery and USB charging indicator. Personal calendar data has been redacted.](../assets/epaper-calendar-dashboard/live-calendar-battery-redacted.jpg)

*The current calendar prototype. Personal appointment details and network identifiers were removed before publication.*

## 1. Selecting the platform

The first design decision was whether to use a smaller all-in-one 400 × 300 module or a higher-resolution board with enough room for a genuinely readable agenda. The final choice was the Waveshare ESP32-S3 3.97-inch e-paper board because it offered:

- an 800 × 480 monochrome panel;
- an ESP32-S3 with 16 MB flash and 8 MB PSRAM;
- USB-C and battery support;
- an AXP2101 power-management IC;
- physical controls, RTC, microSD and onboard environmental sensing;
- enough screen area for a portrait-oriented agenda without reducing text to an unreadable size.

![The development board, battery, speaker, cable and accessories as delivered.](../assets/epaper-calendar-dashboard/hardware-as-delivered.jpg)

*The hardware package before the first custom firmware was flashed.*

Before changing anything, the complete 16 MB factory flash was backed up and verified byte-for-byte. A known-good recovery build was also retained locally. This made experimentation reversible from the beginning.

## 2. Hardware bring-up and capability probing

The board arrived with a factory demonstration application. It confirmed that the display, controls and basic peripherals were functional, but the final product required a clean ESP-IDF firmware and an independently verified understanding of the hardware.

A dedicated hardware-probe application was created to validate the board feature by feature. It covered power management, screen orientation, full and partial refresh, controls, virtual pages, audio paths and other board capabilities. This prevented product code from being built on assumptions copied from examples or vendor documentation.

The probe exposed several integration details that only became obvious on the real device:

- the e-paper power rail had to be enabled through the AXP2101;
- the panel required a portrait-specific rotation and coordinate mapping;
- the vendor text API used foreground and background arguments in a surprising order;
- partial-refresh regions required careful transformation;
- physical button handling needed debouncing and explicit event semantics.

The hardware probe was treated as a validation tool rather than throwaway code. Each capability was first demonstrated independently, then incorporated into the product firmware only after the physical result was understood.

## 3. Polish text rendering

Polish calendar data made UTF-8 support a product requirement rather than a cosmetic improvement. The vendor fonts did not provide a reliable path for every required character, so the firmware received bounded UTF-8 handling and embedded glyph support.

The first attempts produced visibly corrupted diacritics. Instead of hiding the defect, the project introduced a repeatable glyph-validation screen and used it to isolate rendering, bit-order and coordinate problems. The resulting renderer preserves UTF-8 boundaries and displays lowercase and uppercase Polish characters without external font files.

![Before-and-after comparison of the Polish glyph renderer.](../assets/epaper-calendar-dashboard/polish-glyphs-before-after.jpg)

*An early corrupted renderer on the left and the validated glyph layout on the right.*

This work later became part of the normal calendar renderer, including date labels, event titles, locations and system messages.

## 4. From a static layout to live Google Calendar data

The first calendar screen used a controlled local fixture. That allowed the visual hierarchy, field limits and text rendering to be validated before networking was introduced.

The live data path was then built as a deliberately narrow pipeline:

```text
Google Calendar
    → Google Apps Script
    → versioned JSON contract
    → certificate-verified HTTPS
    → ESP32 parser and renderer
    → e-paper display
```

The Apps Script service reads a limited future window, sorts the events and returns only the fields required by the display. The schema includes generation time, timezone, date labels and a bounded list of events. Text is truncated at valid UTF-8 boundaries to match fixed firmware buffers.

The ESP32 stores Wi-Fi configuration in NVS, synchronizes time through NTP and fetches the feed only after time is valid enough for TLS certificate checks. The feed URL and access token remain outside the repository and are not printed in logs.

The device also provides a physical recovery path: holding the BOOT control for five seconds clears saved Wi-Fi configuration and returns the board to provisioning mode.

## 5. Problems found only on real hardware

The live integration exposed failures that unit tests and a desktop HTTP client did not reproduce.

### Google Apps Script redirects

Google Apps Script returned an HTTP 302 response whose body used chunked transfer encoding. The first implementation relied on automatic redirect handling, but ESP-IDF reported an incomplete response before performing the second request.

The final implementation performs the redirect in two controlled stages: it validates the `Location` header, closes the first response without trying to consume the chunked body, and then performs a second certificate-verified HTTPS request to an explicitly allowed Google host.

### Stack pressure

Large URL buffers initially lived on the main task stack. They were moved to the heap and released on every exit path, eliminating stack exhaustion without masking the problem by simply increasing the task stack.

### Time synchronization

A short custom wait loop could stop SNTP before a valid time was obtained. It was replaced with the ESP-IDF synchronization API, a longer bounded timeout and explicit diagnostic logs.

These corrections were validated on the physical board, not only in CI.

## 6. Secure and recoverable OTA updates

Once the live calendar was stable, the firmware moved from a factory-only partition layout to two 7 MiB application slots with OTA metadata and bootloader rollback enabled.

The update process is intentionally defensive:

1. Fetch a manifest over certificate-verified HTTPS.
2. Require HTTP 200 and an exact content length.
3. Validate the declared version, image URL, size and SHA-256.
4. Stream the candidate image into the inactive slot.
5. Check the image header, project identity and embedded version.
6. Compare the streamed SHA-256 before changing the boot partition.
7. Boot the candidate as a trial image.
8. Mark it valid only after the board, display, Wi-Fi, NTP, calendar feed and local OTA service initialize successfully.
9. Roll back automatically when the candidate does not reach the confirmation point.

The implementation was exercised with normal and negative hardware tests, including:

- a successful update between slots;
- an interrupted transfer;
- an incorrect SHA-256;
- the same version as the running firmware;
- a manifest version that did not match the image;
- an image built for a different project;
- a deliberately non-confirmed candidate followed by automatic rollback.

In every rejection case, the currently valid application remained selected and operational.

## 7. Current development stage

The validated baseline is now being extended in two stacked development lines.

### Persistent, fully wireless OTA authorization

The original local OTA endpoint generated a new bearer token on every boot and exposed it through the serial monitor. The network transfer was wireless, but obtaining the token still required USB.

The replacement design introduces a persistent 256-bit secret stored in NVS. Initial provisioning is allowed only during a short window opened by physically booting the device with the BOOT control held. After this one-time migration, subsequent updates can be authorized over Wi-Fi without serial access, `esptool` or a USB cable.

The threat model is stated explicitly: authorization currently travels over local HTTP, so provisioning and updates are intended for a trusted or isolated LAN.

### Battery status and a second screen

The calendar header now has a phone-style battery indicator with proportional fill, percentage text and an independent USB charging symbol. The implementation uses the existing AXP2101 readings rather than estimating battery state from voltage, and it has host tests for boundary and invalid values.

A second screen is also being developed for diagnostics and selected upcoming appointments. A physical button switches between the two full-screen views, while the normal calendar view refreshes its feed when the user returns to it.

At the time of writing, these changes are still draft work. They have passed automated tests and clean builds, but they are intentionally not described as part of the physically validated baseline until the complete device workflow is tested again.

## Engineering approach

This project follows a few consistent rules:

- GitHub and exact commit identifiers are the source of truth.
- A firmware image is not flashed until its exact revision has passed formatting, host tests and ESP-IDF builds.
- Hardware validation is recorded separately from CI success.
- Secrets, private feed URLs, Wi-Fi credentials and recovery images remain outside the repository.
- Potentially destructive changes begin with a verified flash backup and a recovery path.
- Negative tests are treated as product requirements, not optional cleanup.

## Technology

`ESP32-S3` · `ESP-IDF 5.5.5` · `C` · `FreeRTOS` · `e-paper 800 × 480` · `AXP2101` · `NVS` · `SNTP` · `HTTPS/TLS` · `Google Apps Script` · `Google Calendar` · `JSON` · `SHA-256` · `dual-slot OTA` · `rollback` · `GitHub Actions`

## Privacy and repository scope

The product repository is private. This public case study intentionally contains no Wi-Fi credentials, calendar-feed token, OTA secret, private server path, recovery image or personal calendar information. Photographs containing appointment or network details were cropped or redacted before publication.
