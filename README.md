# Łukasz Budzynowski

**Senior IT Manager • IT Project Manager • System Owner • systemy publiczne • bezpieczeństwo • automatyzacja i AI**

Projektuję, wdrażam, rozwijam i utrzymuję systemy informatyczne — od analizy potrzeb, dokumentacji i wyboru wykonawców, przez odbiory i uruchomienia, po monitoring, utrzymanie środowisk produkcyjnych oraz dalszy rozwój.

Łączę wieloletnie doświadczenie w systemach publicznych z praktycznym tworzeniem narzędzi dla Ubuntu, automatyzacją procesów oraz budowaniem produktów od pomysłu do działającego wydania. Rozwijam również aplikacje Android TV, rozwiązania e-paper/ESP32 i prywatne narzędzia wspierające bezpieczną pracę z AI.

## Otwarty na nowe możliwości / Open to opportunities

**Senior IT Manager · IT Project Manager · System Owner**

Jestem otwarty na rozmowy o rolach związanych z zarządzaniem systemami informatycznymi, transformacją cyfrową, ładem IT, bezpieczeństwem i zgodnością w organizacjach publicznych oraz regulowanych.

Wnoszę ponad 20 lat doświadczenia w pełnym cyklu życia systemów — od analizy wymagań, dokumentacji, OPZ i wyboru wykonawców, przez wdrożenia i odbiory, po utrzymanie, rozwój, ciągłość działania i nadzór nad dostawcami. Łączę perspektywę zarządczą, biznesową i techniczną z praktycznym doświadczeniem w Linuxie, Pythonie, automatyzacji, CI/CD i bezpiecznym wykorzystaniu AI.

**Warszawa / Warsaw, Poland · Polish · English C2**

## Obszary

- architektura, wdrażanie, utrzymanie i rozwój systemów IT;
- przygotowanie dokumentacji, wymagań, OPZ i kryteriów oceny;
- prowadzenie odbiorów i współpraca z wykonawcami;
- Linux, Python, Bash, GTK i automatyzacja;
- monitoring, niezawodność i dokumentacja operacyjna;
- GitHub Actions, GitLab CI/CD i zarządzanie kodem;
- środowiska chmurowe, integracje i bezpieczeństwo aplikacji;
- WCAG, UX oraz testy bezpieczeństwa;
- analiza i planowanie zgodności z wymaganiami NIS2/KSC;
- Android TV, Kotlin, ESP32, e-paper i szybkie prototypowanie;
- OpenSCAD i druk 3D.

## Publiczny projekt

### [Codex Usage Tray](https://github.com/lbudzynowski/codex-usage-tray)

Publiczny wskaźnik dla Ubuntu GNOME pokazujący wykorzystanie limitów OpenAI Codex.

Projekt obejmuje klienta lokalnego `codex app-server`, aplikację Python/GTK, testy jednostkowe, GitHub Actions, instalacyjną paczkę `.deb`, autostart GNOME, stronę podręcznika oraz publiczne wydania. Aplikacja nie odczytuje plików uwierzytelniających ani tokenów — korzysta z obsługi logowania zarządzanej przez Codex.

[![Latest release](https://img.shields.io/badge/release-v0.1.1-blue.svg)](https://github.com/lbudzynowski/codex-usage-tray/releases/latest)
[![Tests](https://github.com/lbudzynowski/codex-usage-tray/actions/workflows/tests.yml/badge.svg)](https://github.com/lbudzynowski/codex-usage-tray/actions/workflows/tests.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://github.com/lbudzynowski/codex-usage-tray/blob/main/LICENSE)

## Wybrane projekty

### Dashboard kalendarza e-paper

Urządzenie oparte na ESP32-S3 i panelu e-paper 3,97″, projektowane jako energooszczędny dashboard kalendarza Google na lodówkę lub biurko. Projekt obejmuje firmware ESP-IDF, inicjalizację zasilania AXP2101, pracę ekranu w orientacji pionowej, nawigację przyciskami, diagnostykę sprzętu oraz własny renderer UTF-8 z polskimi znakami i symbolami kalendarza.

### Put.io Skip Intro TV

Aplikacja Android TV / Google TV w Kotlinie dla telewizora Sony Bravia. Obsługuje parowanie z put.io, bezpieczne przechowywanie tokenu w Android Keystore, przeglądanie katalogów, bezpośrednie odtwarzanie z napisami oraz ręcznie zapisywane markery początku i końca intro. Przycisk „Pomiń intro” jest obsługiwany pilotem, a build i testy działają w GitHub Actions.

### Repo Security Scanner

Centralny, audit-only system cyklicznego sprawdzania bezpieczeństwa repozytoriów GitHub. Oddziela skanowanie, agregację raportów i prezentację wyników, wykorzystuje ustandaryzowane raporty JSON/SARIF i nie modyfikuje monitorowanego kodu. Pierwszy pilot uruchamia przypięty wersją i sumą kontrolną Gitleaks, redaguje wyniki, waliduje je względem JSON Schema i publikuje wyłącznie bezpieczny artefakt raportu.

### Yeti Smart Tag

Identyfikator NFC dla psa połączony z mobilnym profilem kontaktowym. Działa bez baterii i instalowania aplikacji, a jego prototyp obejmuje stronę, konfigurację danych demonstracyjnych, fizyczny tag NTAG213, model OpenSCAD, druk 3D, testy NFC, proces produkcji i model biznesowy. Repozytorium nie przechowuje prawdziwych danych klientów.

### Muza / MUSE-01

Modułowy projekt osobistej asystentki AI rozwijanej jako lokalna aplikacja dla Ubuntu, a docelowo także jako niewielki fizyczny robot drukowany w 3D. Działający prototyp Muza Desktop wykorzystuje Python, GTK 4 i przenośny rdzeń aplikacji, zachowując prywatne obrazy poza repozytorium oraz jawnie kontrolując przyszłe użycie mikrofonu, kamery i głosu.

### ChatGPT Drive Archive / Continuity Bridge

Prywatny system archiwizacji i przekazywania kontekstu rozmów z AI pomiędzy sesjami. Rozszerzenie Chrome MV3 wydobywa aktywną gałąź rozmowy do wersjonowanego JSON-u, zachowuje strukturę wiadomości, digesty i bezpieczne metadane oraz działa fail-closed przy niejednoznacznym DOM. Kolejny etap rozwija samodzielne pakiety rozmów `conversation.json + images/`, aktualizowane bez duplikatów i bez zapisywania tokenów lub podpisanych adresów URL.

### Leki 2.0

Prywatna aplikacja do prowadzenia domowego magazynu leków, działająca na komputerze i telefonie. Łączy mobilny interfejs i dashboard Google Sheets/Apps Script z lokalnym skanerem kodów na Ubuntu, rejestrem stanów i ruchów, obsługą zakupów i remanentów oraz historią zmian.

### Bambu A1 Filaments

Prywatna aplikacja do zarządzania magazynem filamentów dla Bambu Lab A1 i AMS Lite, dostępna także przez interfejs mobilny. Ewidencjonuje fizyczne szpule i refille, producenta, materiał, rzeczywisty kolor, masę i tarę szpuli, lokalizację oraz ruchy i zużycie, a aktualny stan oblicza z historii operacji zamiast z samego slotu AMS.

### Ubuntu Desktop Tools

Własne narzędzia Python/GTK: wskaźniki VPN i zapory, monitoring usług, integracje z systemami, automatyzacja zadań administracyjnych oraz powiadomienia lokalne i mobilne.

### IT Systems — Case Studies

Doświadczenie w tworzeniu założeń i dokumentacji, wdrażaniu, rozwijaniu i utrzymywaniu systemów publicznych.

### Program zgodności NIS2/KSC

Kompleksowy projekt przygotowania programu zgodności z wymaganiami NIS2/KSC: analiza podstaw prawnych i luk, governance, RACI, rejestry ryzyk i aktywów, harmonogram, budżet, model zespołu, backlog Redmine oraz materiały decyzyjne dla kierownictwa.

## Doświadczenie

Tworzyłem założenia i dokumentację systemów informatycznych, przygotowywałem wymagania i kryteria wyboru wykonawców, prowadziłem odbiory oraz rozwijałem i utrzymywałem rozwiązania we współpracy z wykonawcami i zespołami merytorycznymi.

Pracowałem między innymi przy:

- Zintegrowanym Rejestrze Kwalifikacji — ZRK;
- systemie Ekonomicznych Losów Absolwentów — ELA;
- rozwiązaniach Zintegrowanego Systemu Kwalifikacji — ZSK;
- wdrożeniu i utrzymaniu EZD RP;
- systemach webowych, środowiskach chmurowych, integracjach i automatyzacji procesów operacyjnych.

## Własne narzędzia

Rozwijam narzędzia i aplikacje, między innymi:

- wskaźniki VPN, zapory i usług systemowych;
- monitoring dostępności aplikacji, workflow i infrastruktury;
- integracje z systemami webowymi i API;
- lokalne i mobilne powiadomienia;
- automatyzację zadań administracyjnych;
- aplikacje telewizyjne i narzędzia dla urządzeń embedded;
- rozwiązania wspierające druk 3D i prototypowanie.

## Technologie

`Python` · `Bash` · `Linux` · `GTK 3/4` · `Git` · `GitHub Actions` · `GitLab CI/CD` · `Redmine` · `FastAPI` · `Kotlin` · `Android TV` · `ESP-IDF` · `ESP32-S3` · `OpenSCAD`

## Kontakt

- Warszawa, Polska
- [E-mail](mailto:lbudzynowski@gmail.com)
- [GitHub Sponsors](https://github.com/sponsors/lbudzynowski)
- [PayPal](https://paypal.me/lbudzynowski)
