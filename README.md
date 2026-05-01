<img width="800" src="https://github.com/user-attachments/assets/779412ca-d726-493a-8b47-bec9420c1347" />

# SniperTAK — Plugin balistyczny dla ATAK-CIV

> 🇵🇱 [Wersja polska poniżej](#-snipertak--plugin-balistyczny-dla-atak-civ-1)

---

# 🇬🇧 SniperTAK — Ballistic Plugin for ATAK-CIV

**SniperTAK** is a tactical plugin for **ATAK-CIV** (Android Team Awareness Kit) that adds a full ballistic calculator, OP (Observation Post) map workflow, and UDP telemetry display directly inside the ATAK interface.

> ⚠️ **Compatibility notice**
> The current stable version works with **ATAK-CIV 5.5.x** (tested on 5.5.1).
> Support for **ATAK-CIV 5.7** is actively being developed — upcoming releases will bring full 5.7 compatibility.

---

## 📦 Installation

### Requirements

- Android device with **ATAK-CIV 5.5.x** installed
- Plugin APK: `ATAK-Plugin-snipertak-*.apk`

### Step-by-step installation

1. **Copy the APK to your device**
   - Connect your Android device via USB or transfer the APK file wirelessly (ADB, email, file manager, etc.)

2. **Install the plugin**
   - Open ATAK-CIV on your device
   - Tap the main menu (≡) in the top-right corner
   - Go to **Settings → Manage Plugins → Install Plugin from File**
   - Navigate to the downloaded `.apk` file and confirm installation

3**Verify installation**
   - The **SniperTAK** icon (crosshair/scope) should appear in the ATAK toolbar
   - Tap the icon to open the plugin panel

---

## 🔧 Main Features

### 🎯 Tab: Target (`Cel`)
- Enter **distance** to target manually or **tap on the map** to auto-fill
- Get **elevation** correction (mils) and **windage** correction (mils) instantly
- Sliders for quick **wind speed** and **wind direction** adjustments
- Auto-recalculate on any wind/condition change
- **Ballistic Data** requester showing: max ordinate, first/second zero, transonic/subsonic boundary, total drop, muzzle velocity and energy at target
- Target limit: 2 000 m (displays a warning if exceeded)

### 🗺️ Tab: OP (Observation Post)
- Place an **OP marker** on the map (or move an existing one)
- Add **target markers** by tapping on the map
- **Targets table** with columns: distance, azimuth, elevation correction, LOS status
  - Row colours reflect Line-of-Sight state: clear / obstructed / unknown
  - Tap a row to centre the map on the target and highlight its marker
  - Long-press a row to edit the target name
  - Tap **X** to remove a target from both the table and the map
- Coordinates display in **MGRS** format
- Reference point selector: **Calculate from Me** / **Calculate from OP**
- **Wind HUD** overlay on the map (near compass): direction arrow, azimuth, wind speed, temperature

### 📋 Tab: Tables (`Tabele`)
- Full **ballistic table** for distances 100–2 000 m (every 100 m)
- Columns: distance, elevation (mils), windage (mils), drop (cm), time of flight (s)

### 🔫 Tab: Rifle (`Karabin`)
- Create, edit, and delete **weapon profiles** (saved persistently)
- Parameters: calibre, muzzle velocity, ballistic coefficient (G1/G7), zero distance, sight height, twist rate, and more

### 🌤️ Tab: Conditions (`Warunki`)
- Input environmental data: wind speed, wind direction, temperature, pressure
- Changes automatically trigger recalculation across all tabs

### 📡 UDP Telemetry
- Built-in **UDP listener** on port 14550
- Receives `lat,lon,alt` packets from external devices (UAV, rangefinder, etc.)
- Displays live position data inside the plugin panel

---

## 📖 Usage Examples

### Example 1: Unknown-distance target on a shooting range (polygonal range)

This workflow is ideal when you know your position but not the exact distance to the target.

1. **Configure your weapon profile** (Tab: Rifle)
   - Set calibre, muzzle velocity, BC, zero distance (e.g. 100 m), and sight height
   - Save the profile

2. **Set environmental conditions** (Tab: Conditions)
   - Enter temperature, pressure, wind speed and direction

3. **Place your OP marker** (Tab: OP)
   - Tap **"Umieść OP / Place OP"**
   - The OP marker is placed at the centre of the current map view — pan the map to your firing position first

4. **Tap the target on the map** (Tab: OP, map is visible)
   - Tap the approximate target position on the map
   - A target marker is created; the table fills in distance and azimuth automatically

5. **Read the firing solution** (Tab: OP table or Tab: Target)
   - Elevation correction (mils) → dial on your scope
   - Windage correction (mils) → hold-off or scope adjustment
   - Use **"Ballistic Data"** for additional trajectory metrics

6. **Adjust quickly** — use the wind sliders in Tab: Target to recalculate on-the-fly without leaving the results view

---

### Example 2: OP workflow — field observation post

This workflow supports a sniper / spotter team managing multiple targets from a fixed observation post.

1. **Configure weapon profile and conditions** (Tabs: Rifle + Conditions)

2. **Navigate to Tab: OP**
   - Tap **"Umieść OP"** to mark your observation post position on the map
   - The OP MGRS coordinates are displayed in the panel

3. **Select reference point**
   - Choose **"Obliczaj do OP / From OP"** if firing from the OP position
   - Choose **"Obliczaj do mnie / From Me"** if your device GPS is at the firing position

4. **Add targets by tapping on the map**
   - Switch to map view and tap each target location
   - Each tap creates a numbered target marker and adds a row to the OP table

5. **Monitor targets in the table**
   - Each row shows: target name, distance, azimuth, elevation, LOS status
   - Green/red colour coding shows line-of-sight status
   - Tap a row to centre the map on that target

6. **Engage a target**
   - Tap the desired target row to select it
   - Read elevation and windage from the table or switch to Tab: Target for full details
   - Use sliders to adjust for real-time wind changes

7. **Remove targets as needed**
   - Tap **X** in the table row — the marker is removed from the map simultaneously
   - Or delete the marker directly from the ATAK map (table updates automatically)

---

## ❓ Tips & FAQ

| Situation | Solution |
|-----------|----------|
| Plugin icon not visible | Restart ATAK; check Manage Plugins — plugin must be enabled |
| Marker not appearing on map | Zoom in/out; verify ATAK map layers are active |
| Distance shows 0 | Tap a point on the map while in Tab: Target or Tab: OP |
| Wind HUD not visible | Scroll the map — HUD is anchored near the compass widget |
| Target limit exceeded (>2000 m) | The calculator shows a warning; zoom in closer |

---

## ☕ Support the Project

SniperTAK is developed independently as a free, open tool for the ATAK community.

If this plugin saves you time or helps your team, consider buying me a coffee — it fuels late-night debugging sessions and new features:

**[☕ Buy Me a Coffee → buymeacoffee.com/snipertak](https://buymeacoffee.com/snipertak)**

No obligation, always appreciated. Thank you! 🙏

---

## 📄 License

SniperTAK is released under the **Apache License 2.0**.

You are free to use, modify, and distribute this software — including for commercial purposes — as long as you include the original license notice and attribution.

See the [LICENSE](LICENSE) file for full terms, or visit:
[https://www.apache.org/licenses/LICENSE-2.0](https://www.apache.org/licenses/LICENSE-2.0)

---
---

# 🇵🇱 SniperTAK — Plugin balistyczny dla ATAK-CIV

**SniperTAK** to taktyczny plugin dla **ATAK-CIV** (Android Team Awareness Kit), który dodaje pełny kalkulator balistyczny, workflow mapowy OP (Punkt Obserwacyjny) oraz wyświetlanie telemetrii UDP bezpośrednio w interfejsie ATAK.

> ⚠️ **Informacja o zgodności**
> Aktualna stabilna wersja działa z **ATAK-CIV 5.5.x** (testowano na 5.5.1).
> Wsparcie dla **ATAK-CIV 5.7** jest aktywnie rozwijane — nadchodzące wydania przyniosą pełną zgodność z wersją 5.7.

---

## 📦 Instalacja

### Wymagania

- Urządzenie Android z zainstalowanym **ATAK-CIV 5.5.x**
- Plik APK pluginu: `ATAK-Plugin-snipertak-*.apk`

### Instalacja krok po kroku

1. **Skopiuj plik APK na urządzenie**
   - Podłącz telefon/tablet przez USB lub prześlij plik bezprzewodowo (ADB, e-mail, menedżer plików itp.)

2. **Zainstaluj plugin**
   - Uruchom ATAK-CIV na urządzeniu
   - Otwórz menu główne (≡) w prawym górnym rogu
   - Przejdź do **Ustawienia → Zarządzaj Pluginami → Zainstaluj Plugin z pliku**
   - Wskaż pobrany plik `.apk` i potwierdź instalację
3. **Sprawdź instalację**
   - Ikona **SniperTAK** (celownik/lunetka) powinna pojawić się na pasku narzędzi ATAK
   - Kliknij ikonę, aby otworzyć panel pluginu

---

## 🔧 Główne funkcje

### 🎯 Zakładka: Cel
- Wpisz **dystans** do celu ręcznie lub **kliknij na mapie**, aby wypełnić automatycznie
- Natychmiastowe wyniki: **elewacja** (mils) i **kierunek korekty / drift** (mils)
- Suwaki do szybkiej regulacji **prędkości** i **kierunku wiatru**
- Automatyczne przeliczenie po zmianie warunków
- Przycisk **Dane Balistyczne** — szczegółowy requester z metrykami trajektorii:
  - maksymalna rzędna (max ordinate)
  - pierwsze i drugie zero
  - wejście w zakres transsomiczny i subsoniczny
  - całkowity opad
  - prędkość i energia w celu
- Limit dystansu: 2 000 m (przy przekroczeniu wyświetlany jest komunikat ostrzegawczy)

### 🗺️ Zakładka: OP (Punkt Obserwacyjny)
- Ustaw **marker OP** na mapie (lub przesuń istniejący)
- Dodawaj **cele kliknięciem na mapie**
- **Tabela celów** z kolumnami: dystans, azymut, korekta elewacji, stan LOS
  - Kolory wierszy odzwierciedlają stan linii widzenia: wolna / zablokowana / nieznana
  - Kliknięcie wiersza centruje mapę na celu i podświetla jego marker
  - Długie przytrzymanie wiersza → edycja nazwy celu
  - Przycisk **X** usuwa cel z tabeli i z mapy jednocześnie
- Koordynaty PO w formacie **MGRS**
- Wybór punktu odniesienia: **Obliczaj do mnie** / **Obliczaj do OP**
- **HUD wiatru** na mapie (przy kompasie): strzałka kierunku, azymut, prędkość, temperatura

### 📋 Zakładka: Tabele
- Pełna **tabela balistyczna** dla dystansów 100–2 000 m (co 100 m)
- Kolumny: dystans, elewacja (mils), kierunek (mils), opad (cm), czas lotu (s)

### 🔫 Zakładka: Karabin
- Twórz, edytuj i usuwaj **profile broni** (zapisywane trwale)
- Parametry: kaliber, prędkość wylotowa, współczynnik balistyczny (G1/G7), dystans zerowania, wysokość celownika, skok gwintu i inne

### 🌤️ Zakładka: Warunki
- Wprowadź dane środowiskowe: prędkość wiatru, kierunek wiatru, temperatura, ciśnienie
- Zmiany automatycznie wyzwalają przeliczenie we wszystkich zakładkach

### 📡 Telemetria UDP
- Wbudowany **listener UDP** na porcie 14550
- Odbiera pakiety `lat,lon,alt` z zewnętrznych urządzeń (BSP, dalmierz, itp.)
- Wyświetla dane pozycji na żywo w panelu pluginu

---

## 📖 Przykłady użycia

### Przykład 1: Strzelnica poligonowa — nieznana odległość do celu

Ten workflow sprawdza się, gdy znasz swoją pozycję, ale nie znasz dokładnego dystansu do celu.

1. **Skonfiguruj profil broni** (Zakładka: Karabin)
   - Wprowadź kaliber, prędkość wylotową, BC, dystans zerowania (np. 100 m) oraz wysokość celownika
   - Zapisz profil

2. **Ustaw warunki środowiskowe** (Zakładka: Warunki)
   - Wprowadź temperaturę, ciśnienie, prędkość i kierunek wiatru

3. **Umieść marker OP** (Zakładka: OP)
   - Kliknij **„Umieść OP"**
   - Marker OP pojawia się na środku widocznego obszaru mapy — wcześniej wyśrodkuj mapę na swojej pozycji strzeleckiej

4. **Kliknij cel na mapie** (Zakładka: OP, mapa jest widoczna)
   - Kliknij przybliżoną pozycję celu na mapie
   - Tworzy się marker celu; tabela wypełnia dystans i azymut automatycznie

5. **Odczytaj dane do strzelania** (Tabela OP lub Zakładka: Cel)
   - Korekta elewacji (mils) → nastaw na lunecie
   - Korekta boczna (mils) → punkt celowania lub nastaw lunety
   - Użyj **„Dane Balistyczne"**, aby zobaczyć dodatkowe metryki trajektorii

6. **Szybka korekta wiatru** — suwaki wiatru w Zakładce: Cel pozwalają natychmiast przeliczyć bez zmiany widoku

---

### Przykład 2: Praca na OP — terenowy punkt obserwacyjny

Ten workflow wspiera parę snajper/obserwator zarządzającą wieloma celami z ustalonego punktu obserwacyjnego.

1. **Skonfiguruj profil broni i warunki** (Zakładki: Karabin + Warunki)

2. **Przejdź do Zakładki: OP**
   - Kliknij **„Umieść OP"**, aby oznaczyć pozycję punktu obserwacyjnego na mapie
   - Koordynaty OP w formacie MGRS są wyświetlane w panelu

3. **Wybierz punkt odniesienia**
   - **„Obliczaj do OP"** — gdy strzelasz z pozycji OP
   - **„Obliczaj do mnie"** — gdy GPS urządzenia jest na pozycji strzeleckiej

4. **Dodawaj cele klikając na mapę**
   - Przejdź do widoku mapy i klikaj kolejne pozycje celów
   - Każde kliknięcie tworzy ponumerowany marker celu i dodaje wiersz do tabeli OP

5. **Monitoruj cele w tabeli**
   - Każdy wiersz zawiera: nazwę celu, dystans, azymut, elewację, stan LOS
   - Kolorowe kodowanie wierszy wskazuje stan linii widzenia
   - Kliknij wiersz, aby wyśrodkować mapę na danym celu

6. **Otwarcie ognia do wybranego celu**
   - Kliknij wiersz wybranego celu
   - Odczytaj elewację i poprawkę boczną z tabeli lub przejdź do Zakładki: Cel
   - Użyj suwaków wiatru do korekty na bieżąco

7. **Usuwanie celów po zaangażowaniu**
   - Kliknij **X** w wierszu — marker znika jednocześnie z mapy
   - Możesz też usunąć marker bezpośrednio z mapy ATAK (tabela zaktualizuje się automatycznie)

---

## ❓ Często zadawane pytania

| Sytuacja | Rozwiązanie |
|----------|-------------|
| Ikona pluginu niewidoczna | Uruchom ATAK ponownie; sprawdź Zarządzaj Pluginami — plugin musi być włączony |
| Marker nie pojawia się na mapie | Oddal/przybliż widok; sprawdź aktywne warstwy mapy ATAK |
| Dystans wynosi 0 | Kliknij punkt na mapie będąc w Zakładce: Cel lub Zakładce: OP |
| HUD wiatru niewidoczny | Przewiń mapę — HUD jest zakotwiczony przy widgecie kompasu |
| Przekroczony limit dystansu (>2000 m) | Kalkulator wyświetla ostrzeżenie; zbliż się lub przybliż widok mapy |

---

## ☕ Wesprzyj projekt

SniperTAK jest rozwijany niezależnie jako darmowe narzędzie dla społeczności ATAK.

Jeśli plugin oszczędza Ci czas lub wspiera Twój zespół — postaw mi kawę! Każda kawa to paliwo do nocnych sesji debugowania i nowych funkcji:

**[☕ Postaw kawę → buymeacoffee.com/snipertak](https://buymeacoffee.com/snipertak)**

Nie ma obowiązku, ale każde wsparcie jest ogromnie cenione. Dziękuję! 🙏

---

## 📄 Licencja

SniperTAK jest udostępniany na licencji **Apache License 2.0**.

Możesz swobodnie używać, modyfikować i dystrybuować tego oprogramowania — w tym do celów komercyjnych — pod warunkiem zachowania oryginalnej informacji o licencji i atrybucji.

Pełna treść licencji znajduje się w pliku [LICENSE](LICENSE) lub pod adresem:
[https://www.apache.org/licenses/LICENSE-2.0](https://www.apache.org/licenses/LICENSE-2.0)

---

*SniperTAK Plugin | ATAK-CIV 5.5.x stable · 5.7 coming soon*

