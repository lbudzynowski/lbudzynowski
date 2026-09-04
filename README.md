# Łukasz Budzynowski

**Technical Program Leader • AI Workflow Architecture & Agentic Systems • IT Governance • Digital Transformation**

Projektuję i prowadzę systemy od problemu do działającej produkcji — łącząc zarządzanie programami IT, architekturę rozwiązań, governance i bezpieczeństwo z praktycznym tworzeniem oprogramowania, automatyzacji oraz human–AI workflows.

Mam ponad 20 lat doświadczenia w pełnym cyklu życia systemów informatycznych: od analizy potrzeb, wymagań, dokumentacji i wyboru wykonawców, przez wdrożenia i odbiory, po utrzymanie, rozwój, ciągłość działania i nadzór nad środowiskami produkcyjnymi.

Równolegle buduję własne rozwiązania w Pythonie, Kotlinie, ESP-IDF i Bashu, pracuję z Linuxem, CI/CD, urządzeniami embedded i agentami AI. Projekty techniczne prowadzę w modelu GitHub-first: decyzja → kontrolowana implementacja → CI → review → walidacja produkcyjna lub fizyczna.

**Warsaw, Poland · Polish · English C2**

## Open to opportunities

**Technical Program Leader · AI Adoption / Enablement · Head of IT · IT Programme Manager · System Owner**

Interesują mnie role łączące odpowiedzialność za systemy i produkty cyfrowe z transformacją organizacji, AI, governance, bezpieczeństwem i rzeczywistym dowożeniem rozwiązań.

Najlepiej odnajduję się tam, gdzie trzeba połączyć perspektywę biznesową, organizacyjną i techniczną — uporządkować problem, zaprojektować sposób działania, zorganizować wykonanie, doprowadzić rozwiązanie do produkcji i później świadomie nim zarządzać.

## What I do

- strategia IT, governance i transformacja cyfrowa;
- zarządzanie projektami i programami oraz pełnym cyklem życia systemów;
- AI adoption, human–AI workflows i agentic operating models;
- zarządzanie zespołami, interesariuszami, dostawcami, ryzykiem i zmianą;
- wymagania, OPZ, kryteria wyboru wykonawców i dokumentacja zamówień publicznych;
- architektura, integracje, wdrożenia, utrzymanie i rozwój systemów;
- bezpieczeństwo, ciągłość działania, monitoring i operational readiness;
- Linux, Python, Bash, GTK, Kotlin, Android TV, ESP32 i automatyzacja;
- GitHub Actions, GitLab CI/CD, testy, release engineering i kontrolowane deploymenty;
- NIS2/KSC, WCAG, UX oraz testowanie bezpieczeństwa aplikacji.

---

## Featured public software

### [Codex Usage Tray](https://github.com/lbudzynowski/codex-usage-tray)

Wskaźnik dla Ubuntu GNOME pokazujący wykorzystanie limitów OpenAI Codex i integrujący lokalne funkcje Codex z pulpitem Linux.

Projekt obejmuje aplikację Python/GTK, klienta `codex app-server`, integrację Codex Remote Control, kontrolowane blokowanie uśpienia podczas aktywnej pracy, testy jednostkowe, GitHub Actions, paczki `.deb`, autostart GNOME, dokumentację oraz publiczne wydania.

Aplikacja nie odczytuje plików uwierzytelniających ani tokenów — korzysta z mechanizmów logowania zarządzanych przez Codex.

[![Latest release](https://img.shields.io/github/v/release/lbudzynowski/codex-usage-tray)](https://github.com/lbudzynowski/codex-usage-tray/releases/latest)
[![Tests](https://github.com/lbudzynowski/codex-usage-tray/actions/workflows/tests.yml/badge.svg)](https://github.com/lbudzynowski/codex-usage-tray/actions/workflows/tests.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://github.com/lbudzynowski/codex-usage-tray/blob/main/LICENSE)
[![Ubuntu PPA](https://img.shields.io/badge/PPA-lbudzynowski%2Fapps-E95420?logo=ubuntu&logoColor=white)](https://launchpad.net/~lbudzynowski/+archive/ubuntu/apps)

```bash
sudo add-apt-repository ppa:lbudzynowski/apps
sudo apt update
sudo apt install codex-usage-tray
```

### [Bhola Pulse](https://github.com/lbudzynowski/bhola-pulse)

Animowany dashboard telemetryczny dla Ubuntu GNOME na Wayland/XWayland.

Jeden długo działający provider w Pythonie zasila atomowy cache współdzielony przez instancje Conky. Projekt monitoruje między innymi CPU, RAM, temperatury, dyski, zasilanie, sieć, zaporę oraz lokalne usługi, zachowując celowo ograniczony i zredagowany zakres danych.

Dostępne są dwa niezależne style: graficzny **LARGE SHARP** oraz terminalowy **NERD MODE**.

Wydanie obejmuje testowaną paczkę `.deb`, konfigurację zgodną z XDG, testy Python/Bash, kontrolę SHA-256, GitHub Actions oraz publikację przez Ubuntu PPA.

[![Latest release](https://img.shields.io/github/v/release/lbudzynowski/bhola-pulse)](https://github.com/lbudzynowski/bhola-pulse/releases/latest)
[![CI](https://github.com/lbudzynowski/bhola-pulse/actions/workflows/ci.yml/badge.svg)](https://github.com/lbudzynowski/bhola-pulse/actions/workflows/ci.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://github.com/lbudzynowski/bhola-pulse/blob/main/LICENSE)
[![Ubuntu PPA](https://img.shields.io/badge/PPA-lbudzynowski%2Fapps-E95420?logo=ubuntu&logoColor=white)](https://launchpad.net/~lbudzynowski/+archive/ubuntu/apps)

```bash
sudo add-apt-repository ppa:lbudzynowski/apps
sudo apt update
sudo apt install bhola-pulse
```

<table>
  <tr>
    <td width="49%">
      <a href="https://github.com/lbudzynowski/bhola-pulse/blob/main/docs/images/large-sharp.png"><img src="https://raw.githubusercontent.com/lbudzynowski/bhola-pulse/main/docs/images/large-sharp.png" alt="Bhola Pulse LARGE SHARP" width="100%"></a><br>
      <sub><strong>LARGE SHARP</strong> — graphical telemetry dashboard.</sub>
    </td>
    <td width="49%">
      <a href="https://github.com/lbudzynowski/bhola-pulse/blob/main/docs/images/nerd-mode.png"><img src="https://raw.githubusercontent.com/lbudzynowski/bhola-pulse/main/docs/images/nerd-mode.png" alt="Bhola Pulse NERD MODE" width="100%"></a><br>
      <sub><strong>NERD MODE</strong> — terminal/BBS-inspired view.</sub>
    </td>
  </tr>
</table>

---

## AI & Agentic Engineering

### Human–AI engineering operating model

Projektuję i wykorzystuję model długotrwałej współpracy człowieka z agentami AI obejmujący ChatGPT, Codex, Google Drive, GitHub i kontrolowane środowiska wykonawcze.

Model rozdziela planowanie, decyzje, wykonanie i walidację. Obejmuje między innymi:

- GitHub jako źródło prawdy dla kodu;
- kontrolowaną autonomię agentów;
- jasno określone granice operacji i denylisty;
- CI, review i walidację dokładnego SHA;
- izolowane self-hosted runnery;
- jawne bramki przed operacjami produkcyjnymi lub destrukcyjnymi;
- przenoszenie kontekstu pomiędzy długotrwałymi sesjami bez powierzania agentowi nieograniczonego dostępu do całego środowiska.

To nie jest eksperyment promptowy — model jest używany przy rzeczywistym rozwijaniu i utrzymywaniu kilku projektów software i infrastructure.

### Continuity Bridge / ChatGPT Drive Archive

Prywatny system context engineering dla długotrwałej współpracy z AI.

Łączy pamięć kuratorską, wersjonowane przekazywanie stanu projektu i pełne archiwa rozmów. Eksporter Chrome MV3 pracuje fail-closed przy niejednoznacznym DOM i zachowuje strukturę wiadomości, provenance oraz integralność danych.

Pakiety archiwalne wykorzystują wersjonowany `conversation.json`, katalogi assetów, manifesty SHA-256, pakiet ZIP oraz readback i ponowną weryfikację po zapisaniu.

Celem nie jest tylko archiwizacja rozmów, ale utrzymywanie sprawdzalnej ciągłości pracy człowieka i agentów pomiędzy sesjami i projektami.

### Muza / MUSE-01

Modułowy projekt osobistej asystentki AI: obecnie aplikacja desktopowa dla Ubuntu, docelowo również niewielki fizyczny robot drukowany w 3D.

Działający prototyp Muza Desktop wykorzystuje Python, GTK 4 i przenośny rdzeń aplikacji. Rozwój prowadzony jest GitHub-first, a automatyczne wykonanie odbywa się w kontrolowanym środowisku CI.

Projekt świadomie rozdziela publiczny kod od prywatnych danych i zasobów oraz zakłada jawne sterowanie przyszłym dostępem do mikrofonu, kamery i głosu.

### Guarded infrastructure automation

W prywatnej infrastrukturze rozwijam kontrolowane workflow GitHub Actions i self-hosted runners służące do diagnostyki, deploymentów i fizycznych testów urządzeń.

Stosowane mechanizmy obejmują między innymi minimalne uprawnienia, exact-SHA execution, niezależny readback, fail-closed validation, ograniczone operacje `sudo`, izolację sekretów oraz zakaz automatycznego powtarzania operacji, które mogłyby wywołać efekt fizyczny lub produkcyjny.

---

## Selected product & engineering work

### Storytel TV Player

Nieoficjalny klient Android TV / Google TV do słuchania audiobooków Storytel, rozwijany i realnie testowany na Sony Bravia.

Aplikacja obsługuje prawdziwe konto i półkę użytkownika, sterowanie pilotem, odtwarzanie przez AndroidX Media3 / ExoPlayer, przewijanie, synchronizację pozycji ze Storytel oraz powrót do półki.

Warstwa bezpieczeństwa wykorzystuje Android Keystore i AES-256-GCM do ochrony trwałego materiału sesji; cleartext HTTP i backup danych aplikacji są wyłączone.

Projekt przeszedł security hardening, Android lint, testy, GitHub Actions oraz proces stabilnego podpisywania release. Podpisana publiczna beta została fizycznie zainstalowana i zweryfikowana na Sony Bravia.

**Technologie:** Kotlin · Jetpack Compose for TV · Media3 / ExoPlayer · Android Keystore · GitHub Actions

### Dashboard kalendarza e-paper

Urządzenie oparte na ESP32-S3 i panelu e-paper 3,97″, zaprojektowane jako autonomiczny i energooszczędny dashboard Google Calendar.

Fizycznie zwalidowany prototyp obejmuje provisioning Wi-Fi do NVS, NTP, pobieranie kalendarza przez certyfikatowo zweryfikowane HTTPS, ograniczony kontrakt JSON, renderer UTF-8 z polskimi znakami oraz bezpieczne dwuslotowe OTA.

OTA sprawdza tożsamość projektu, wersję, rozmiar i SHA-256 obrazu, zapisuje aktualizację do nieaktywnego slotu i wykorzystuje rollback bootloadera w przypadku nieudanego uruchomienia.

![Działający dashboard Google Calendar na fizycznym prototypie e-paper. Wybrane dane zostały zredagowane.](assets/epaper-calendar-dashboard/live-calendar-battery-redacted.webp)

[Pełna historia projektu i galeria sprzętu →](projects/epaper-calendar-dashboard.md)

### QR-Audio

Eksperymentalny system przechowywania rzeczywistych danych audio bezpośrednio w jednym lub wielu kodach QR — bez konieczności pobierania nagrania z Internetu podczas odtwarzania.

Androidowy klient wykorzystuje CameraX i lokalny model ML Kit do skanowania wielu części w dowolnej kolejności. Dane są składane, weryfikowane przez CRC32 i odtwarzane lokalnie.

Projekt rozwinął własny format QRA1, encoder, binarny protokół, assembler oraz obsługę skanowania i odtwarzania binarnego QRA1.

**Technologie:** Android · CameraX · ML Kit · binary protocol design · CRC32 · offline-first architecture

### Yeti Smart Tag

System identyfikatorów NFC dla psów połączonych z mobilnym profilem kontaktowym.

Projekt obejmuje fizyczny NTAG213, modele OpenSCAD i druk 3D, responsywny profil internetowy, generator wielu profili, prywatny lokalny CRM oraz kontrolowany proces publikacyjny.

Architektura celowo rozdziela publiczny kod, szablony i dane demonstracyjne od rzeczywistych danych właścicieli i zwierząt.

Projekt służy również jako praktyczne laboratorium privacy-by-design, bezpiecznych deploymentów i integracji usług.

### Repo Security Scanner

Centralny, audit-only system cyklicznego sprawdzania bezpieczeństwa repozytoriów GitHub.

Oddziela skanowanie, agregację raportów i prezentację wyników, wykorzystuje raporty JSON/SARIF oraz narzędzia przypinane do konkretnych wersji.

Założeniem jest fail-closed dla awarii samego narzędzia lub braku rzeczywistego pokrycia skanem — zielony workflow nie może oznaczać bezpieczeństwa, jeśli skaner faktycznie nie wykonał analizy.

---

## Governance & Digital Transformation

### NIS2 / KSC programme

Projekt przygotowania organizacji do wymagań NIS2/KSC prowadzony jako pełny program transformacyjny, a nie pojedynczy audyt zgodności.

Zakres obejmuje między innymi:

- analizę podstaw prawnych i luk;
- governance i RACI;
- architekturę programu i work breakdown structure;
- rejestry ryzyka, aktywów i dowodów;
- plan zespołu i odpowiedzialności;
- budżet i harmonogram;
- operational readiness;
- przygotowanie procesów obsługi incydentów;
- plan uruchomienia i operacjonalizacji wymaganych usług i kanałów współpracy.

Szczegóły organizacyjne i materiały robocze pozostają prywatne.

### IT Systems — Case Studies

W swojej pracy zawodowej przygotowywałem założenia, wymagania i dokumentację systemów informatycznych, prowadziłem wybór i nadzór wykonawców, odbiory, wdrożenia, rozwój oraz utrzymanie środowisk produkcyjnych.

Pracowałem między innymi przy:

- Zintegrowanym Rejestrze Kwalifikacji — ZRK;
- systemie Ekonomicznych Losów Absolwentów — ELA;
- rozwiązaniach Zintegrowanego Systemu Kwalifikacji — ZSK;
- wdrożeniu i utrzymaniu EZD RP;
- systemach webowych, integracjach, chmurze i automatyzacji procesów operacyjnych.

---

## Upstream contributions

Poza własnymi repozytoriami zgłaszam odtwarzalne błędy, regresje, problemy dokumentacyjne i propozycje funkcji bezpośrednio do projektów, których używam.

- **Chromium**
  - #556290470 — regresja przewijania touchpadem w Chrome Canary; problem odizolowany do stanu profilu/Variations i zgłoszony wraz z reprodukcją oraz powiązaniem z istniejącą zmianą Chromium.

- **OpenAI / Codex**
  - [#38863 — Codex Desktop on Linux defaults spellcheck to en-US and flags Polish text as misspelled](https://github.com/openai/codex/issues/38863)
  - [#35928 — Remote Connections docs contradict the new `codex remote-control pair` CLI workflow](https://github.com/openai/codex/issues/35928)

- **PrintStash**
  - [#70 — Preserve the exact printed artifact/revision and slicer settings for Bambu external print jobs](https://github.com/xiao-villamor/PrintStash/issues/70)
  - [#69 — Bambu LAN on Bambu A1 fails with Paho v2 callbacks, PUBACK handling, cleanup order, and partial MQTT reports](https://github.com/xiao-villamor/PrintStash/issues/69)

<details>
<summary>Historical upstream reports</summary>

- **CopyQ**
  - [#1240 — No history after upgrade to Ubuntu 19.10](https://github.com/hluk/CopyQ/issues/1240)

- **WiFi Signal Strength GNOME extension**
  - [#2 — Error](https://github.com/Tomin1/wifisignalstrength/issues/2)

</details>

---

## Other projects

<details>
<summary>Additional software, automation and infrastructure work</summary>

### Put.io Skip Intro TV

Android TV / Google TV application for Sony Bravia with put.io pairing, Android Keystore token storage, subtitle playback and user-defined intro markers.

### Leki 2.0

Private household inventory application combining Google Sheets / Apps Script, a mobile interface and a local Ubuntu barcode scanner with an append-only movement ledger, stock calculations and inventory reconciliation.

### Bambu / Spoolman / PrintStash

Private 3D-printing infrastructure covering physical filament inventory, Bambu Lab A1 / AMS Lite, Spoolman, automatic consumption tracking, PrintStash and controlled diagnostics of printer communication.

### Ubuntu Desktop Tools

Python/GTK utilities for VPN, firewall and service state, system monitoring, web integrations, local automation and mobile notifications.

### Home infrastructure

Mini-PC based environment with Linux, containers, local reverse proxying, monitoring, Home Assistant and controlled GitHub-first infrastructure automation.

</details>

---

## Technology

`Python` · `Bash` · `Linux` · `Ubuntu` · `GTK 3/4` · `Git` · `GitHub Actions` · `GitLab CI/CD` · `Docker` · `systemd` · `Redmine` · `FastAPI` · `Google Apps Script` · `Kotlin` · `Android TV` · `Jetpack Compose` · `ESP-IDF` · `ESP32-S3` · `OpenSCAD`

**Engineering practices:** CI/CD · release engineering · code review · threat-aware design · SHA-256 provenance · fail-closed workflows · least privilege · automated testing · hardware validation · production readback

## Contact

Warsaw, Poland  
[E-mail](mailto:lbudzynowski@gmail.com)

## Support open-source work

[GitHub Sponsors](https://github.com/sponsors/lbudzynowski) · [PayPal](https://paypal.me/lbudzynowski)
