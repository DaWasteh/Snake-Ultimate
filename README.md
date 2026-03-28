# 🐍 Snake Ultimate (v0.2)

Snake Ultimate ist eine erweiterte Version des klassischen Arcade-Spiels "Snake". Das Projekt wurde vollständig in HTML5, CSS3 und Vanilla JavaScript entwickelt und kommt ohne externe Frameworks aus.

Es bietet neben dem klassischen Einzelspieler-Modus einen lokalen Multiplayer, verschiedene visuelle Themes und anpassbare Spielmechaniken (Addons) – vollständig optimiert für Desktop, Tablet und Mobile.

---

## 📸 Screenshots

![Neon Cyberpunk Theme](image.png)
Das Hauptmenü im „Neon Cyberpunk" Theme.

![Classic 3310 Theme](image1.png)
Das „Classic 3310" Theme beim Spielen mit Hunger-Addon.

![Deep Sea Theme](image2.png)
Das Hauptmenü im „Deep Sea" Theme mit 2-Spieler-Modus.

![Inferno Blood Theme](image3.png)
Das Hauptmenü im „Inferno Blood" Theme mit allen Addons aktiv.

---

## ✨ Features

**Responsives Design:** Das Spielfeld skaliert dynamisch für Desktop, Tablet, Hochformat- und Querformat-Smartphones (16:9, 18:9, 9:16) und behält dabei stets das 4:3-Seitenverhältnis bei.

**Lokaler Multiplayer:** Zwei Spieler können gleichzeitig an einer Tastatur spielen. Bei einer Kollision der Schlangenköpfe kommt es zu einem Unentschieden (Double K.O.).

**5 Visuelle Themes:** Ändern nicht nur die Farbpalette, sondern auch die Rendering-Logik der Objekte und die Schriftarten:

- 🌐 **Neon Cyberpunk:** Rasterhintergrund und Neon-Leuchteffekte.
- 🧱 **Classic 3310:** Monochromes Grün mit sichtbarem Pixel-Raster.
- 🌊 **Deep Sea:** Organische, runde Formen und Tiefsee-Farbverlauf.
- 🔥 **Inferno Blood:** Dunkelrote Farbgebung mit gezackten Schlangenmodellen.
- 🌿 **Plants vs. Zombies:** Grüner Rasen, Sonnenblumen-Food, Zombie-Hindernisse.

**Tastaturbedienung:** Das gesamte Spiel inklusive Menü lässt sich über die Tastatur steuern.

**Touch-Steuerung:** Swipe-Gesten auf dem Spielfeld und On-Screen D-Pad für komfortable mobile Bedienung.

---

## ⚙️ Spielmodi & Addons

Die Spielgeschwindigkeit und zusätzliche Mechaniken lassen sich modular anpassen.

### Geschwindigkeiten

| Modus     | Intervall |
|-----------|-----------|
| Leicht    | 150 ms    |
| Mittel    | 100 ms    |
| Schnell   |  70 ms    |
| Ultra     |  45 ms    |
| ALBTRAUM  |  35 ms    |

**ALBTRAUM:** Alle Addons zwingend aktiv + roter Geist verfolgt die Schlange.

### Addons (Toggles)

| Addon           | Beschreibung |
|-----------------|--------------|
| 🪨 Hindernisse  | Für jedes 3. gesammelte Futter spawnt ein permanentes Hindernis. |
| 🥩 Hunger       | Leiste leert sich kontinuierlich. Bei 0: Schlange schrumpft und Punktabzug. Fressen füllt sie wieder. |
| 🌀 Eis. Jungfrau | Wand wächst spiralförmig von außen nach innen. Fressen drückt sie zurück. |

---

## 🎮 Steuerung

### Menüsteuerung

| Taste              | Aktion                             |
|--------------------|------------------------------------|
| `Leertaste`        | Spiel starten                      |
| `↑` / `↓`          | Geschwindigkeit wechseln           |
| `Alt Gr`           | 1- / 2-Spieler-Modus umschalten    |
| `+` / `-`          | Visuelles Theme wechseln           |
| `1`, `2`, `3`      | Addons ein- / ausschalten          |
| `Strg`             | Zurück ins Hauptmenü               |

### Spielsteuerung (Keyboard)

| Spieler   | Tasten                              |
|-----------|-------------------------------------|
| Spieler 1 | `↑` `↓` `←` `→` (Pfeiltasten)      |
| Spieler 2 | `W` `A` `S` `D`                     |

### Mobile Steuerung

| Methode   | Beschreibung                                      |
|-----------|---------------------------------------------------|
| Swipe     | Wischen auf dem Spielfeld (min. 25 px Distanz)    |
| D-Pad     | On-Screen Steuerkreuz erscheint automatisch beim Spielstart |

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

### v0.2 – Bugfixes & Mobile Overhaul

**Bugfixes:**
- 🐛 **[KRITISCH]** `showMenu()` fügte bei jedem Aufruf neue Event-Listener auf den Start-Button → `startGame()` wurde doppelt oder mehrfach aufgerufen → Spiel startete nicht korrekt auf Mobile.
- 🐛 **[KRITISCH]** Overlay war `position: absolute` innerhalb des 4:3-Game-Containers → auf Landscape-Phones (16:9, 18:9) nur ~250px hoch → Menü war abgeschnitten und nicht scrollbar.
- 🐛 Swipe-Erkennung fehlte Mindestabstand-Check → jede 1px-Bewegung registrierte Richtungswechsel.
- 🐛 `resizeCanvas()` setzte `canvas.style.width/height` per JavaScript, während CSS gleichzeitig `width: 100%` setzte → Größenkonflikt auf Mobile.
- 🐛 Doppelter `@media (max-width: 600px)` Block (140 Zeilen redundantes CSS).
- 🐛 PvZ-Theme war im Code implementiert aber nicht im Style-Dropdown auswählbar.

**Mobile Improvements:**
- ✅ Overlay wird auf Touch-Geräten zu `position: fixed; inset: 0` → immer vollbildschirmfüllend und scrollbar.
- ✅ Separate CSS-Breakpoints für Portrait (≤600px) und Landscape (max-height: 500px).
- ✅ `touch-action: manipulation` auf allen Buttons → eliminiert 300ms Tap-Delay.
- ✅ On-Screen D-Pad erscheint automatisch auf Touch-Geräten während des Spiels.
- ✅ In Landscape wird das D-Pad fest rechts unten positioniert (bleibt neben dem Canvas).
- ✅ Game-Over-Screen hat jetzt zwei klare Buttons: „↺ NOCHMAL" und „☰ HAUPTMENÜ".
- ✅ Keyboard-Hints werden auf Touch-Geräten ausgeblendet.
- ✅ `viewport-fit=cover` + `user-scalable=no` für Notch-Geräte und sauberere Darstellung.

### v0.1 – Initiale Version

Bei der Entwicklung wurde auf eine klare Trennung der Rendering-Logik geachtet. Jedes Theme nutzt eine eigene Draw-Funktion, um individuelle Formen (Quadrate, Kreise, Diamanten) performant auf das Canvas zu zeichnen. Zudem ist eine State-Machine implementiert, die den Wechsel zwischen Menü, aktivem Spiel und Game-Over-Status verwaltet. Die Input-Queue verhindert sofortige U-Turns bei schnellen Tastenfolgen.

---

## 📋 Geplante Erweiterungen

- [ ] Highscore-Speicherung (Local Storage)
- [ ] Soundeffekte
- [ ] Multiplayer-D-Pad auf Mobile (getrennte Zonen für P1/P2)

---

Entwickelt von **DaWasteh**.