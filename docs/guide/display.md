Where to find it: Windows › Display

# Display and screen tools

Monitor settings, brightness schedules and night light on **Display**; a color picker, text extractor, ruler, pins and locked-file finder on **Screen tools**.

Deck changes displays through Windows and the monitor's standard DDC/CI channel. It never injects into games, so none of this is an anti-cheat risk.

## Display

Where to find it: Windows › Display

The top shows one card per monitor with its number and refresh rate; click one to jump to its section. **Identify** shows each display's number on its screen for 2 seconds, the same number its card has (the main display is 1). It never takes focus, and Deck refuses while a game or full-screen app is in front. **Turn off display** puts every screen to sleep now; move the mouse or press a key to wake them.

### Each monitor

Each monitor has one card, headed by its number, name (**Main** for the primary one), resolution, refresh rate and scale. Inside are **Display mode**, **Picture**, **Monitor settings**, **Input & speakers** (when the monitor has them) and **Night & tests**.

| Control | What it does |
|---|---|
| **Refresh rate** | One button per rate. If the monitor runs below its top rate, a line says so and **Use N Hz** switches to it. Common rates show first; **Show all rates** shows every one. |
| **Resolution** | The monitor's modes, largest first. |
| **Scale** | Windows' display scaling; the recommended one is marked. |
| **Orientation** | **Landscape**, **Portrait**, **Landscape (flipped)** or **Portrait (flipped)**. |
| **HDR** | On or off, when the monitor and driver support it. **Auto HDR** opens Windows' own Auto HDR setting. |
| **Brightness** | 0 to 100 %, on monitors that answer DDC/CI. A **DDC/CI** chip says whether it is available. |
| Range | The fold under Brightness ("Range 0–100%"): the lowest and highest brightness the slider covers, for a panel too bright at the top or to match two monitors. Schedules follow it. **Full range** resets it. |
| **Contrast** | 0 to 100 %, when the monitor reports it. |

If the monitor refuses a value, the slider returns to what the monitor reports.

**The 15-second way back.** Changing refresh rate, resolution or orientation asks **Keep these display settings?** with a countdown. Press **Keep these settings** or **Go back**. If you do nothing (or the screen is black), Deck goes back after 15 seconds.

### Night & tests

Three blocks: **Schedule**, **Night light** and **Test pattern**.

**Schedule and idle dimming.** Press **Set schedule** (or **Edit schedule**):

| Field | Meaning |
|---|---|
| **Turn on this monitor's schedule and idle dimming** | The switch for this monitor. Off by default. Turning it off restores what Deck changed. |
| **Time**, **Brightness**, **Strength %** | A target for that time of day. Deck fades between times, across midnight too. **Add time** / **Remove time**; up to 24 times. |
| **Dim after idle, minutes (0 means off)** | Dims after this long without keyboard or mouse use. |
| **Idle brightness %** | The brightness while dimmed. Using the PC brings back the scheduled value. |

The schedule needs DDC/CI brightness. Strength works like night light.

**Night light.** Set the strength (0 to 100 %) and press **Apply night light**. Deck warms the picture by lowering blue and green in that monitor's color curve, on top of its calibration.

- The original curve is restored when Deck quits, and at the next start after a crash.
- HDR or Windows' own Night light can override it. If the driver refuses, Deck says so.
- Not for color-critical work.

**Reset changes** resets everything Deck changed on every monitor (brightness, color, input) and turns every schedule off.

**Test patterns.** Pick one and press **Show pattern**. It covers that monitor until you press Escape, or for two minutes.

| Pattern | Checks |
|---|---|
| **Solid black** | Backlight bleed, glow, stuck lit pixels. |
| **Solid white** | Dead pixels, tint, uneven brightness. |
| **Solid red**, **Solid green**, **Solid blue** | Stuck sub-pixels, color uniformity. |
| **Gradient** | Banding. |
| **Grid** | Geometry and sharpness. |
| **Uniformity** | Uneven brightness or tint on mid-gray. |

### Monitor settings (DDC/CI)

Deck asks the monitor what it supports and shows only those settings ("Asking the monitor…"). They are the settings of the monitor's own buttons, and the monitor keeps them on any PC.

| Control | Notes |
|---|---|
| **Digital vibrance** | NVIDIA only, on the driver's own scale (not NVIDIA Control Panel's percentage). Higher means stronger colors. |
| Sharpness | When the monitor allows it; otherwise "Sharpness: monitor menu only". |
| Color preset | The presets the monitor lists (sRGB, 6500 K, User 1). An unknown one shows as "Custom (code …)". |
| Red, Green, Blue | Color gains, as a percentage of the monitor's range. |

**Input & speakers:** the input switch (HDMI, DisplayPort) asks first, because the monitor then shows that input until you switch back with its own buttons. Speaker volume shows for monitors with speakers. Deck never offers power-off or factory reset.

If a monitor shows **No DDC/CI settings on this monitor**, turn on DDC/CI in its own menu. Some docks, KVMs, adapters and cables block it.

### Appearance

| Setting | What it does | Default |
|---|---|---|
| **Windows theme** | **Dark** or **Light** for Windows and apps. | As Windows is |
| **Switch automatically** | Switches the theme on a schedule. A manual switch holds until the next change. | Off |
| **When** | **Set times** or **Sunrise & sunset**. | Set times |
| **Times** | Light and dark times. | 07:30 and 19:30 |
| **Location** | For sunrise and sunset. **Use my location** guesses a rough place from your internet address (one request to a public lookup). | Not set |

### Recommended setup

- High-refresh monitor: check **Refresh rate** shows the top rate.
- Evenings: a schedule with 3 or 4 times, for example 08:00 at 80 % and strength 0, 18:00 at 50 % and 30, 22:00 at 25 % and 60.
- OLED: idle dimming at 5 minutes and 20 %.
- Competitive games: keep night light strength low enough to see enemies.

### Troubleshooting

- **No brightness slider.** Turn on DDC/CI in the monitor's menu and avoid docks or adapters that block it.
- **The screen went black after a change.** Wait 15 seconds; Deck goes back.
- **The schedule does nothing.** Check its switch, that brightness works on that monitor, and that HDR or Windows Night light aren't overriding it.
- **The input switch left no picture.** Use the monitor's buttons to pick the PC's input, then **Reset changes**.

### FAQ

- **What does Deck change?** Display mode, scale, brightness, contrast, the color curve and the monitor's own settings, only when you ask. Brightness and color return when Deck quits. The input switch isn't undone on quit, since you may have switched on purpose.
- **Do the changes affect games?** Refresh rate, resolution and HDR do, as in Windows.

## Screen tools

Where to find it: Windows › Screen tools

Two tabs: **Capture** and **Locked files**.

### Capture

The **Tools** card has five tools, each with **Start**. Deck hides itself, freezes a copy of the screen in memory (never saved) and lets you point at it. Escape cancels.

| Tool | What it does |
|---|---|
| **Pick a color** | Click any pixel. Its color is copied as hex, RGB or HSL (set by **New picks copy**) and added to **Colors**. |
| **Text extractor** | Drag over text in an image, video, game or window. Windows' text recognition reads it and copies it. **Language** picks the language; **Lines** chooses **Keep breaks** or **Join**. |
| **Ruler** | Drag a box. Its size in screen pixels is copied (`640 x 480`). On a scaled screen it also gives the size apps draw at. |
| **Pin an area** | Drag over something. A copy stays on top in a small window that never takes the keyboard. Drag to move, right-click to close. Clipboard pictures can be pinned with **Float on screen**. |
| **Mirror a window** | Drag over part of a window. A small on-top window shows that part live, and closes with the source. |

Up to 8 pins and mirrors at once. **On screen** lists open ones, each with **Close**, plus **Close all**.

**Recent captures** keeps your last 10 **Ruler** measurements and **Text extractor** texts, newest first, each with **Copy**. They stay on this PC only, encrypted for your Windows account, and are never logged. **Clear** deletes them after asking.

**Colors** lists your last 40 colors. Select one for its **Hex**, **RGB** and **HSL** values, each with **Copy**, and its contrast on white and black. Right-click a swatch to copy its RGB value. **Clear history** empties it.

If text isn't recognized, add its language in Windows Settings › Time & language.

### Locked files

For when Windows says a file or folder is in use. Choose **Pick a file** or **Pick a folder**. Deck lists the programs holding it, each marked "Has it open" or "Runs from here", with its path and process ID, or says it is free.

**End task** ends that program after asking; unsaved work in it is lost. Don't end Windows system programs; restart the PC instead.

### Windows tools

Click the empty search box at the top of Deck: **Windows tools** links to Task Manager, Windows Settings, Terminal, Environment variables, Sound devices, Network adapters, Power options, Installed apps, Downloads and Snipping Tool. Typing shows the same links in search results.

### Screen tools FAQ

- **Does it work over games?** On whatever is on screen. Exclusive-fullscreen games may not be captured; use borderless or windowed.
- **Is the screen copy saved?** No, it stays in memory while the tool is open.
