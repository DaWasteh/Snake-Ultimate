# 🐍 Snake Ultimate (v0.3)

Snake Ultimate ist eine erweiterte Version des klassischen Arcade-Spiels "Snake". Das Projekt wurde vollständig in HTML5, CSS3 und Vanilla JavaScript entwickelt und kommt ohne externe Frameworks aus.

Es bietet neben dem klassischen Einzelspieler-Modus einen lokalen Multiplayer, verschiedene visuelle Themes und anpassbare Spielmechaniken (Addons) – vollständig optimiert für Desktop, Tablet und Mobile.

---

## 📸 Screenshots

![Neon Cyberpunk](image.png)
Das Hauptmenü im „Neon Cyberpunk" Theme.

![Classic 3310](image-1.png)
Das „Classic 3310" Theme beim Spielen mit Addon's.

Und noch 6 weitere Styles!

---

## ✨ Features

**Responsives Design:** Das Spielfeld skaliert dynamisch für Desktop, Tablet, Hochformat- und Querformat-Smartphones (16:9, 18:9, 9:16) und behält dabei stets das 4:3-Seitenverhältnis bei.

**Lokaler Multiplayer:** Zwei Spieler können gleichzeitig an einer Tastatur spielen. Bei einer Kollision der Schlangenköpfe kommt es zu einem Unentschieden (Double K.O.).

**8 Visuelle Themes:** Ändern nicht nur die Farbpalette, sondern auch die Rendering-Logik der Objekte und die Schriftarten:

- 🌐 **Neon Cyberpunk:** Rasterhintergrund und Neon-Leuchteffekte.
- 🧱 **Classic 3310:** Monochromes Grün mit sichtbarem Pixel-Raster.
- 🌊 **Deep Sea:** Organische, runde Formen und Tiefsee-Farbverlauf.
- 🔥 **Inferno Blood:** Dunkelrote Farbgebung mit gezackten Schlangenmodellen.
- 🌿 **Plants vs. Zombies:** Grüner Rasen, Sonnenblumen-Food, Zombie-Hindernisse.
- 💻 **Matrix Code:** Schwarzer Hintergrund, grüne Glyphen, Scan-Line-Overlay.
- 🌸 **Vaporwave:** Perspektivisches Raster, Sonnenuntergang-Gradient, Pink/Lila-Palette.
- 🌲 **Dark Forest:** Prozeduraler Waldhintergrund, Beeren als Food, Baumstumpf-Hindernisse.

**Tastaturbedienung:** Das gesamte Spiel inklusive Menü lässt sich über die Tastatur steuern.

**Touch-Steuerung:** Swipe-Gesten auf dem Spielfeld und On-Screen D-Pad für komfortable mobile Bedienung. Im Multiplayer stehen zwei unabhängige D-Pads für simultanes Multi-Touch bereit.

**Highscore-Speicherung:** Bester Punktestand wird persistent im Local Storage gesichert und in der Top-Bar angezeigt.

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
| ☠️ Gift-Äpfel   | Sporadisch erscheinende Giftfrüchte: Fressen kostet 15 Punkte und schrumpft die Schlange. |

---

## 🎮 Steuerung

### Menüsteuerung

| Taste              | Aktion                             |
|--------------------|------------------------------------|
| `Leertaste`        | Spiel starten                      |
| `↑` / `↓`          | Geschwindigkeit wechseln           |
| `Alt Gr`           | 1- / 2-Spieler-Modus umschalten    |
| `+` / `-`          | Visuelles Theme wechseln           |
| `1`, `2`, `3`, `4` | Addons ein- / ausschalten          |
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
| Multiplayer | Zwei separate D-Pad-Zonen für simultanes Multi-Touch |

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

### v0.3 – Layout-Overhaul & Neue Themes

**Bugfixes (Responsive Layout):**
- 🐛 **[KRITISCH]** Fehlender `.game-center`-Wrapper: Ohne diesen Wrapper war kein `flex-row`-Layout in Landscape möglich → D-Pad überlagerte mit `position: fixed` den Canvas.
- 🐛 **[KRITISCH]** D-Pad `position: fixed` in Landscape → schwebte über dem Spielfeld statt daneben zu stehen. Jetzt `position: static` als normales Flex-Item im `.game-center`-Row.
- 🐛 **[HOCH]** Canvas-Breite in Landscape nicht D-Pad-aware → Canvas nutzte volle Viewport-Breite und wurde vom D-Pad überdeckt.
- 🐛 **[HOCH]** Keyboard-Legende zeigte `[1,2,3]` statt `[1,2,3,4]` — Gift-Äpfel-Shortcut fehlte.
- 🐛 Doppelter Abstand zwischen Canvas und D-Pad durch redundante Kombination von `margin-top` und `gap`.
- 🐛 `.overlay` hatte kein globales `overflow-y: auto` → Start-Button auf sehr kleinen Fenstern nicht erreichbar.
- 🐛 Multiplayer-Landscape: Zwei D-Pads mit 44px Buttons überschritten 275px auf iPhone SE Landscape → Overflow.
- 🐛 `.topbar-hs` fehlte `flex-shrink: 0` → Highscore-Anzeige wurde bei schmalem Viewport gequetscht.

**Layout-Verbesserungen:**
- ✅ Neuer `.game-center`-Wrapper umschließt Canvas + D-Pad: Portrait → `flex-column`, Landscape → `flex-row`.
- ✅ Canvas in Landscape: `width: auto; height: 100%; aspect-ratio: 4/3; flex-shrink: 1` — passt sich D-Pad-Breite korrekt an.
- ✅ Multiplayer-Landscape: D-Pad-Buttons auf 32px verkleinert, kein Overflow mehr.
- ✅ `flex-shrink: 0` auf `.topbar-hs` gesetzt.

**Neue Features:**
- ✅ 3 neue visuelle Themes: **Matrix Code**, **Vaporwave**, **Dark Forest** (je eigene Draw-Funktion + CSS-Theme-Variablen).
- ✅ **Gift-Äpfel-Addon** (☠️): Giftfrüchte spawnen sporadisch, verschwinden nach kurzer Zeit, Fressen kostet Punkte und Länge.
- ✅ **Highscore-Persistenz** via Local Storage (`snakeUltimate_hs`): Bester Wert bleibt über Sessions hinweg erhalten, wird in Top-Bar und Game-Over-Screen angezeigt. Neuer Rekord löst Blink-Animation aus.

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
- ✅ Game-Over-Screen hat jetzt zwei klare Buttons: „↺ NOCHMAL" und „☰ HAUPTMENÜ".
- ✅ Keyboard-Hints werden auf Touch-Geräten ausgeblendet.
- ✅ `viewport-fit=cover` + `user-scalable=no` für Notch-Geräte und sauberere Darstellung.

### v0.1 – Initiale Version

Bei der Entwicklung wurde auf eine klare Trennung der Rendering-Logik geachtet. Jedes Theme nutzt eine eigene Draw-Funktion, um individuelle Formen (Quadrate, Kreise, Diamanten) performant auf das Canvas zu zeichnen. Zudem ist eine State-Machine implementiert, die den Wechsel zwischen Menü, aktivem Spiel und Game-Over-Status verwaltet. Die Input-Queue verhindert sofortige U-Turns bei schnellen Tastenfolgen.

---

## 📋 Geplante Erweiterungen

- [x] ~~Highscore-Speicherung (Local Storage)~~ ✅ v0.3
- [x] ~~Multiplayer-D-Pad auf Mobile (getrennte Zonen für P1/P2)~~ ✅ v0.3
- [ ] Soundeffekte (v0.4)

---

Entwickelt von **DaWasteh**.
