# Display and screen tools

This page covers two parts of Deck's **Desktop** group:

- **Display**: resolution, refresh rate, scale, orientation, HDR, brightness and contrast for each monitor, a brightness and warmth schedule, idle dimming, night colour, the monitor's own picture settings and input switch, test patterns, and Windows' dark and light theme.
- **Screen tools**: a colour picker, copy text from the screen, a pixel ruler, a "what is holding this file?" finder, and shortcuts to Windows panels.

Find them under **Desktop > Display** and **Desktop > Screen tools** in the sidebar.

Deck changes displays through Windows and the monitor's standard DDC/CI channel. It never injects into games or reads their memory, so none of this is a risk for anti-cheat.

---

## Display

The top of the page shows one card per connected monitor (its number, "main" or "secondary", and its current refresh rate). Click a card to jump to that monitor's section. If no display is connected the page says so.

### Each monitor's section

The heading shows the monitor's name (with a **Main** chip for the primary one), its resolution and refresh rate.

| Control | What it does | Notes |
|---|---|---|
| **Refresh rate** | One chip per rate the monitor supports. Click one to switch. | Shown only when the monitor offers more than one. If the monitor is running below its maximum, a hint says so and a **Use N Hz** button switches to the top rate. Most people want the maximum. |
| **Brightness** | A slider from 0 to 100%. | Laptop panels and monitors that answer Windows or DDC/CI. Otherwise the page says "Brightness can't be changed from Windows. Turn on DDC/CI in the monitor's menu." |
| **Contrast** | A slider from 0 to 100%. | Shown only when the monitor reports it. |
| **Resolution** | Drop-down of the monitor's modes, the largest first. | Shown only when more than one is available. |
| **Scale (text, apps)** | Windows' display scaling. The recommended one is marked. | Shown only when more than one is available. |
| **Orientation** | Landscape, Portrait, Landscape (flipped) or Portrait (flipped). | |
| **HDR** | A switch. | Shown only when the monitor and graphics driver support HDR. |

**The 15-second way back.** Changing refresh rate, resolution or orientation opens a "Keep these display settings?" box with a countdown. Press **Keep these settings** to accept or **Go back** to return at once. If you do nothing, or the screen is black and you cannot see the box, Deck goes back after 15 seconds. While the box is open the monitor's controls are disabled so only one change is in flight.

### Schedule, night colour and test patterns

Inside each monitor's section is a fold called **Schedule, night colour and test patterns**. It does the following, per monitor.

**Schedule and idle dimming.** Press **Set schedule and idle dimming** (or **Edit enabled schedule** once it is on). The editor has:

| Field | Meaning |
|---|---|
| **Enable this monitor's schedule and idle dimming** | The master switch for this monitor. Off by default. Turning it off puts back what Deck changed on that monitor. |
| **Time**, **Brightness %**, **Warmth %** (one row per time) | A target for that time of day. Deck fades smoothly from one time to the next, including across midnight. **Add time** adds a row, **Remove time** deletes one. Up to 24 times, each at a different minute, in order. |
| **Dim after idle, minutes (0 means off)** | Dims the screen after this long without keyboard or mouse use. From half a minute to a day. 0 turns idle dimming off. |
| **Idle brightness %** | The brightness used while dimmed. |

Notes:

- The schedule checks every few seconds; brightness changes use the monitor's DDC/CI brightness, so the monitor needs to support it (the same requirement as the Brightness slider). If it does not, the schedule cannot work and Deck logs a warning.
- When you use the PC again after an idle dim, brightness returns to the scheduled value.
- Warmth is applied as a colour curve (see Night colour below).

**Undo display changes.** Puts back everything Deck changed on every monitor (brightness, colour, input), and turns every schedule off.

**Night colour.** Type a **Night colour warmth %** (0 to 100) and press **Apply night colour**. Deck lowers the blue and green parts of that monitor's colour curve, so the picture turns warmer. It uses the monitor's saved calibration as a starting point and scales it, never replacing it. Notes:

- The original colour curve is restored exactly when Deck quits, and after a crash the next start restores it.
- It may not work, or may be overridden, while **HDR** or Windows' own **Night light** is on. Turn those off and try again. If the driver refuses, Deck says "The display driver did not accept colour calibration."
- It is per monitor and separate from the schedule's warmth, which uses the same mechanism.
- Warmth is for comfort. Do not use it for colour-critical work, and expect a game's own gamma setting or some capture tools to fight with it.

**Test patterns.** Pick a pattern and press **Show full-screen pattern**. It covers that monitor until you press Escape, and closes by itself after two minutes.

| Pattern | Use it to check |
|---|---|
| **Solid black** | Backlight bleed, glow, dead-on-black OLED, stuck lit pixels in the dark. |
| **Solid white** | Dead or stuck pixels, yellow tint, uneven brightness. |
| **Solid red / green / blue** | Stuck sub-pixels and colour uniformity. |
| **Gradient** | Banding across a black-to-white ramp. |
| **Grid** | Geometry and sharpness (a line every 64 pixels). |
| **Uniformity** | A mid-grey screen with a small white square in the middle, to spot uneven brightness or tint. |

The patterns are drawn by Deck itself, not by a browser or by capturing the screen.

### The monitor's own settings (DDC/CI)

Below the fold, Deck asks the monitor what it supports and shows only those settings. The monitor takes a moment to answer ("Asking the monitor..."). These are the settings you would otherwise change with the monitor's buttons; the monitor keeps them whichever PC it is plugged into.

Under **Picture tuning**:

| Control | Notes |
|---|---|
| **Digital vibrance** | NVIDIA graphics only. The Control Panel's colour saturation, 50 to 100%. 50% is normal. Higher makes colours stronger and less natural. The driver keeps it. |
| **Sharpness** | If the monitor lets Deck set it. If not, the page says it can only be changed from the monitor's own menu. |
| **Colour preset** | The presets the monitor lists (for example sRGB, Native, 6500 K, User 1). |
| **Red**, **Green**, **Blue** | Colour gains, when listed. |

Under **Input and audio**:

| Control | Notes |
|---|---|
| **Input** | Switches the monitor to another input, for example HDMI or DisplayPort. Only inputs the monitor lists are offered. Deck asks first, because the monitor will then show that input instead of this PC until you switch it back with the monitor's own buttons. |
| **Speaker volume** | Monitors with built-in speakers. |

Deck deliberately does not offer anything that could turn a monitor off or reset it (power mode, factory reset).

If a monitor has no DDC/CI settings the card says so. On many monitors DDC/CI must be turned on in the monitor's own on-screen menu, and a few docks, KVMs, adapters or cables do not pass it through.

### Personalise Windows

| Setting | What it does | Default |
|---|---|---|
| **Windows theme** | Dark or Light for Windows and apps. | Whatever Windows uses. |
| **Switch automatically** | Switches the theme on a schedule. The line under it shows when it will go light and dark. A switch you make by hand holds until the next scheduled change. | Off |
| **When** | **Set times** or **Sunrise & sunset**. | Set times |
| **Times** | Light and Dark clock times (for Set times). | Light at 07:30, dark at 19:30 |
| **Location** | For Sunrise & sunset. **Use my location** guesses a rough place from your internet address (it makes one request to a public location lookup) and stores it in Deck's settings. | Not set |

### Turn screens off

The **Turn screens off** button puts every monitor to sleep now (the PC keeps running). Move the mouse or press a key to wake them. For keeping the PC awake instead, see [Power](power.md).

### Recommended setup

- Desktop with a high-refresh monitor: check **Refresh rate** shows the top rate. Deck flags a monitor that runs below its maximum.
- Late-night use: create a schedule with 3 or 4 times, for example 08:00 at 80% brightness and 0 warmth, 18:00 at 50% and 30, 22:00 at 25% and 60.
- OLED or always-on screens: turn on idle dimming (for example 5 minutes, 20%).
- Laptop: brightness changes affect the battery; a schedule can help. The idle dim uses idle time of the keyboard and mouse, not the display's own power timer.
- Competitive games: leave **Digital vibrance** at a level you like, but test it, and do not use a night colour warmth that makes enemies harder to see.

### Troubleshooting

**There is no brightness slider.** Windows could not change this monitor's brightness. Turn on DDC/CI in the monitor's menu, avoid adapters or docks that block it, and reopen the page.

**The DDC/CI section says the monitor has no settings.** The monitor or its connection does not offer DDC/CI. Use its buttons instead.

**The screen went black after a change.** Wait 15 seconds, Deck goes back by itself.

**The schedule does nothing.** Check the monitor's switch is on, that the times are in order, that Brightness is adjustable on that monitor, and that Windows Night light or HDR are not overriding the colour curve.

**Night colour has no effect or looks wrong.** HDR, Windows Night light and some GPU colour tools replace the colour curve. Turn them off, or use only one.

**Input switch left me with no picture.** Use the monitor's own buttons to select the PC's input. Press **Undo display changes** once the PC is visible again.

### FAQ

**What does Deck change?** Display mode, scale, brightness, contrast, the colour curve and the monitor's DDC/CI settings, only when you ask. Brightness and colour are restored when Deck quits or after a crash. The input switch is deliberately **not** undone on quit (you may have moved the monitor to another PC on purpose); **Undo display changes** puts it back.

**Is night colour like f.lux?** In spirit yes, but it is simple: one warmth number per time of day on top of your own colour calibration.

**Do the changes affect games?** The refresh rate, resolution and HDR do, as they would in Windows. Keep night colour off for colour-sensitive games.

---

## Screen tools

Find them under **Desktop > Screen tools**. The page has three tabs: **Screen & colours**, **Locked files** and **Shortcuts**.

### Screen & colours

Three big buttons start a tool. Deck hides itself first, then freezes a copy of the screen in memory (nothing is saved to disk) and shows it full screen so you can point at it; the copy is released when the tool closes. Escape cancels.

| Tool | What it does |
|---|---|
| **Pick colour** | Click any pixel. Its colour (as a hex code such as `#1A2B3C`) is copied to the clipboard and added to your history. |
| **Copy screen text** | Drag over text in an image, a video, a game or a window that will not let you select text. Deck reads it with Windows' built-in text recognition (OCR) and copies the result to the clipboard. |
| **Measure area** | Drag a box. Its width and height in pixels are copied to the clipboard (for example `640 x 480`). |

A notification confirms each result.

The text tool uses the recognition languages installed in Windows. If text in a language is not recognised, add that language in Windows Settings > Time & language.

**Colours you picked.** The last 40 distinct colours are listed as swatches. Click one to select it, then **Copy hex** or **Copy RGB**. Right-click a swatch to copy its RGB value straight away. **Clear colours** empties the history after asking.

### Locked files

For when Windows says a file or folder is "in use" and refuses to move or delete it. Choose **Pick a file** or **Pick a folder**. Deck lists the programs holding it open, each marked **Has it open** or **Runs from here**, with the program path and process ID. If nothing holds it, the page says it is free.

Deck combines two views: Windows' own file-in-use list, and a scan of every program's open files, so it also finds a program that merely has a folder open (a terminal or Explorer window in it) or runs from inside the folder.

**End it** ends that program after a confirmation. Unsaved work in it will be lost. The page then checks again. Do not end Windows system programs; if the holder is a system service, restarting the PC is safer.

### Shortcuts

Buttons that open Windows panels: Task Manager, Windows Settings, Terminal, Environment variables, Sound devices, Network adapters, Power options, Installed apps, Downloads and Snipping Tool.

### Screen tools FAQ

**Does Pick colour work in games?** It works on whatever is drawn on screen when the tool starts. Deck takes a normal screen copy; for exclusive-fullscreen games this may not capture the game, so switch the game to borderless or windowed. Deck never reads game memory.

**Is the screen copy saved?** No. It stays in memory while the tool is open.

**Where do the colour hex codes go?** To the clipboard, and to the history on this page. The history is part of Deck's settings; clear it any time.
