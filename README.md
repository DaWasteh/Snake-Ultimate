# 🐍 Snake Ultimate (v0.3)

Snake Ultimate ist eine erweiterte Version des klassischen Arcade-Spiels "Snake". Das Projekt wurde vollständig in HTML5, CSS3 und Vanilla JavaScript entwickelt und kommt ohne externe Frameworks aus.

Es bietet neben dem klassischen Einzelspieler-Modus einen lokalen Multiplayer, verschiedene visuelle Themes und anpassbare Spielmechaniken (Addons) – vollständig optimiert für Desktop, Tablet und Mobile.

---

## 📸 Screenshots

![Neon Cyberpunk Theme](image.png)
Das Hauptmenü im „Neon Cyberpunk" Theme.

![Classic 3310 Theme](image-1.png)
Das „Classic 3310" Theme beim Spielen mit Hunger-Addon.

Und noch 6 weitere Styles!
---

## ✨ Features

**Responsives Design:** Das Spielfeld skaliert dynamisch für Desktop, Tablet, Hochformat- und Querformat-Smartphones (16:9, 18:9, 9:16) und behält dabei stets das 4:3-Seitenverhältnis bei.

**Lokaler Multiplayer:** Zwei Spieler können gleichzeitig an einer Tastatur spielen. Bei einer Kollision der Schlangenköpfe kommt es zu einem Unentschieden (Double K.O.).

**8 Visuelle Themes:** Ändern nicht nur die Farbpalette, sondern auch die Rendering-Logik der Objekte und die Schriftarten.

**Highscore-Speicherung:** Der persönliche Rekord wird lokal im Browser gespeichert und bleibt auch nach einem Neuladen der Seite erhalten.

**Multiplayer D-Pad:** Auf Touch-Geräten erscheinen im 2-Spieler-Modus zwei separate D-Pads nebeneinander – P1 links, P2 rechts.

**Tastaturbedienung:** Das gesamte Spiel inklusive Menü lässt sich über die Tastatur steuern.

**Touch-Steuerung:** Swipe-Gesten auf dem Spielfeld und On-Screen D-Pad für komfortable mobile Bedienung.

---

## 🎨 Visuelle Themes

### Bestehende Themes (v0.1 / v0.2)

| Theme | Beschreibung |
|-------|--------------|
| 🌐 **Neon Cyberpunk** | Rasterhintergrund, Neon-Leuchteffekte, cyan/magenta Farbgebung. |
| 🧱 **Classic 3310** | Monochromes Grün mit sichtbarem Pixel-Raster (Nokia-Feel). |
| 🌊 **Deep Sea** | Organische, runde Formen mit Tiefsee-Farbverlauf. |
| 🔥 **Inferno Blood** | Dunkelrote Farbgebung mit gezackten Diamanten-Schlangenmodellen. |
| 🌿 **Plants vs. Zombies** | Grüner Rasen, Sonnenblumen-Food, Zombie-Hindernisse. |

### Neue Themes (v0.3)

| Theme | Beschreibung |
|-------|--------------|
| 💻 **Matrix Code** | Reines Schwarz mit grünen Scan-Lines und Raster. Die Schlange besteht aus leuchtend grünen Blöcken mit `>` Zeichen. Futter erscheint als weißes Pixel mit `1`. Gift-Äpfel blinken rot als `0`. Der Jäger flackert bedrohlich. |
| 🌸 **Vaporwave** | Retro-80s-Ästhetik: violetter Himmel mit Farbverlauf, klassisches Perspektiv-Grid auf dem Boden. Die Schlange besteht aus pink/lila Kreisen, Futter als rotierender Strahlen-Burst. |
| 🌲 **Dark Forest** | Organischer dunkler Wald: prozedural erzeugte Büsche als Hintergrundtextur. Futter sind rote Beeren mit Glanzlicht und Stiel. Hindernisse sind Baumstümpfe mit Jahresringen. Der Jäger ist nur durch zwei glühende rote Augen in der Dunkelheit zu erkennen. |

---

## ⚙️ Spielmodi & Addons

### Geschwindigkeiten

| Modus    | Intervall |
|----------|-----------|
| Leicht   | 150 ms    |
| Mittel   | 100 ms    |
| Schnell  |  70 ms    |
| Ultra    |  45 ms    |
| ALBTRAUM |  35 ms    |

**ALBTRAUM:** Alle Addons zwingend aktiv + roter Jäger verfolgt die Schlange.

### Addons (Toggles)

| Taste | Addon | Beschreibung |
|-------|-------|--------------|
| `[1]` | 🪨 **Hindernisse** | Für jedes 3. gesammelte Futter spawnt ein permanentes Hindernis. |
| `[2]` | 🥩 **Hunger** | Leiste leert sich kontinuierlich. Bei 0: Schlange schrumpft und Punktabzug. Fressen füllt sie wieder. |
| `[3]` | 🌀 **Eis. Jungfrau** | Wand wächst spiralförmig von außen nach innen. Fressen drückt sie zurück. |
| `[4]` | ☠️ **Gift-Äpfel** *(neu v0.3)* | Siehe unten. |

### ☠️ Gift-Äpfel (neu in v0.3)

Taucht regelmäßig ein giftiger Apfel neben dem normalen Futter auf. Er ist theme-spezifisch dargestellt (lila Diamant, glitchender Block, Pilz, etc.) und verschwindet nach ca. 8 Sekunden von selbst, wenn er nicht gefressen wird.

**Wird er versehentlich gefressen:**
- Die Schlange schrumpft sofort um 3 Segmente
- `-15 Punkte` werden abgezogen
- Der Gift-Apfel verschwindet

Der Modus erfordert, dass man nicht blind allem Leuchtenden hinterherjagt – Situationsbewusstsein ist gefragt.

---

## 🏆 Highscore-System (neu in v0.3)

Der persönliche Rekord wird automatisch im Local Storage des Browsers gespeichert.

- Der aktuelle Bestwert ist jederzeit in der Top-Leiste sichtbar (`🏆 BEST: X`).
- Nach jedem Spiel wird auf dem Game-Over-Screen angezeigt, ob ein neuer Rekord erzielt wurde.
- Bei einem neuen Rekord blinkt das Banner auf dem Game-Over-Screen.
- Der Highscore bleibt über Browser-Sessions hinweg erhalten.

---

## 📱 Multiplayer D-Pad (neu in v0.3)

Auf Touch-Geräten (Smartphones, Tablets) erscheinen im 2-Spieler-Modus automatisch zwei separate D-Pads unterhalb des Spielfelds:

- **Linkes D-Pad (P1):** Steuerung für Spieler 1, farblich in der Akzentfarbe des Themes.
- **Rechtes D-Pad (P2):** Steuerung für Spieler 2, farblich in Magenta gehalten.

Im Einzelspieler-Modus erscheint weiterhin nur ein zentriertes D-Pad.

Im Querformat-Modus (Landscape) wird das D-Pad fix am unteren Rand positioniert, damit es das Spielfeld nicht verdeckt.

---

## 🎮 Steuerung

### Menüsteuerung

| Taste         | Aktion                             |
|---------------|------------------------------------|
| `Leertaste`   | Spiel starten                      |
| `↑` / `↓`     | Geschwindigkeit wechseln           |
| `Alt Gr`      | 1- / 2-Spieler-Modus umschalten    |
| `+` / `-`     | Visuelles Theme wechseln           |
| `1`, `2`, `3`, `4` | Addons ein- / ausschalten     |
| `Strg`        | Zurück ins Hauptmenü               |

### Spielsteuerung (Keyboard)

| Spieler   | Tasten                              |
|-----------|-------------------------------------|
| Spieler 1 | `↑` `↓` `←` `→` (Pfeiltasten)      |
| Spieler 2 | `W` `A` `S` `D`                     |

### Mobile Steuerung

| Methode  | Beschreibung                                      |
|----------|---------------------------------------------------|
| Swipe    | Wischen auf dem Spielfeld (min. 25 px Distanz)    |
| D-Pad    | On-Screen Steuerkreuz erscheint automatisch beim Spielstart; im 2-Spieler-Modus zwei separate Pads |

---

## 🚀 Installation & Start

Das Spiel läuft vollständig clientseitig im Browser, es wird kein lokaler Server benötigt.

```bash
# Repository klonen
git clone https://github.com/DaWasteh/snake-ultimate.git

# Datei im Browser öffnen
open snake_ultimate.html
```

Kompatibel mit allen modernen Browsern: Chrome, Firefox, Edge, Safari (Desktop & Mobile).

---

## 🛠️ Entwicklung & Architektur

### v0.3 – Highscore, Multiplayer D-Pad, neue Themes & Gift-Äpfel

**Neue Features:**
- ✅ **Highscore (Local Storage):** Persistente Speicherung des Bestwerts (`snakeUltimate_hs`). Anzeige in Top-Bar und Game-Over-Screen. Blink-Animation bei neuem Rekord.
- ✅ **Multiplayer D-Pad:** Zwei separate D-Pads (`dpad-p1-zone`, `dpad-p2-zone`) mit eigenem Input-Routing über `pushInput(snake, dir)`. Automatisch sichtbar auf Touch-Geräten nur während des Spiels.
- ✅ **3 neue Themes:** Matrix Code, Vaporwave, Dark Forest – jedes mit eigener `draw*()` Funktion und CSS-Theme-Block.
- ✅ **Gift-Äpfel Addon:** Separates `poisonFood`-Objekt mit eigenem Lebenszyklus (`ticksLeft`). Spawn per probabilistischem Intervall (`POISON_SPAWN_DIV`). Theme-spezifische Darstellung via `drawPoisonFoodGeneric(style)` Helper.
- ✅ **Input-Refactor:** Zentrale `pushInput(snake, direction)`-Funktion für alle Eingabequellen (Keyboard, D-Pad, Swipe). Verhindert U-Turns und Queue-Overflow einheitlich.

**Technische Details:**
- Dark Forest Hintergrund verwendet einen deterministischen `forestRng(x, y)` Hash, sodass Busch-Texturen stabil und ohne Flimmern gerendert werden.
- Vaporwave Perspektiv-Grid nutzt `Math.pow()` für nicht-lineare Linienabstände (realistischere Perspektive).
- Matrix Schlangen-Segmente werden mit dynamischer Opacity basierend auf der Distanz zum Kopf gerendert (Fade-Out-Effekt).

### v0.2 – Bugfixes & Mobile Overhaul

**Bugfixes:**
- 🐛 **[KRITISCH]** `showMenu()` fügte bei jedem Aufruf neue Event-Listener auf den Start-Button → `startGame()` wurde doppelt aufgerufen.
- 🐛 **[KRITISCH]** Overlay war `position: absolute` innerhalb des 4:3-Containers → abgeschnitten auf Landscape-Phones.
- 🐛 Swipe-Erkennung fehlte Mindestabstand-Check.
- 🐛 Doppelter `@media (max-width: 600px)` Block (redundantes CSS).
- 🐛 PvZ-Theme war nicht im Dropdown auswählbar.

**Mobile Improvements:**
- ✅ Overlay wird auf Touch-Geräten `position: fixed; inset: 0`.
- ✅ Separate CSS-Breakpoints für Portrait (≤600px) und Landscape (max-height: 500px).
- ✅ `touch-action: manipulation` eliminiert 300ms Tap-Delay.
- ✅ Game-Over-Screen mit zwei klaren Buttons: „↺ NOCHMAL" und „☰ HAUPTMENÜ".

### v0.1 – Initiale Version

Klare Trennung der Rendering-Logik: jedes Theme nutzt eine eigene Draw-Funktion. State-Machine für Menü → Spiel → Game-Over. Input-Queue verhindert sofortige U-Turns.

---

## 📋 Geplante Erweiterungen (v0.4)

- [ ] Soundeffekte

---

Entwickelt von **DaWasteh**.