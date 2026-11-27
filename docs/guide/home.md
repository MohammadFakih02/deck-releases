Where to find it: Home › Home

# Home, the tray icon and how Deck opens

Home is your starting board: quick controls and live status. This page also covers how Deck opens, the window modes and the tray menu.

For a one-minute map of the sidebar and search, see [Find your way around](find-your-way.md). The settings for opening Deck are in [Settings › General](settings.md#opening-deck).

## Opening and closing Deck

Deck runs in the tray (the notification area next to the clock).

| Way | What it does |
|---|---|
| Hot corner | Rest the pointer in a screen corner. Each corner can open Deck, show the desktop, lock, turn off the display or sleep. Opening Deck needs Quick panel mode. |
| Tray icon | Left-click shows or hides Deck. Right-click opens the [tray menu](#the-tray-icon-and-its-menu). |
| Keyboard shortcut | Shows or hides Deck, also over games. Empty until you set one. |
| Start menu | Starts Deck, or shows it if it is already running. Deck never runs a second copy. |
| Phone | The [phone remote](phone.md) drives many of Deck's controls. |

The **X** hides Deck. It keeps running in the tray, so timers, hot corners and fan control carry on. To quit, choose **Quit Deck** in the tray menu or in Settings › About. See [What quitting does](#what-quitting-does).

### Hot corners

Set each corner in Settings › General: **Top left corner**, **Top right corner**, **Bottom left corner** and **Bottom right corner**. Each has an action (**Does nothing**, **Open Deck**, **Show the desktop**, **Lock the PC**, **Turn off display**, **Sleep**) and its own delay (0 to 1000 ms).

So a corner does not fire by accident:

- It only counts at an outer corner of the whole desktop, not where two monitors meet.
- The pointer must rest there for the delay. A quick pass does nothing.
- It waits while a mouse button is held, and ignores screenshot tools.
- Over fullscreen games and videos it stays off unless you turn on **Works over fullscreen games and videos**. Deck then opens without taking focus from the game.

The corners only read the pointer position. Nothing touches the game.

## Quick panel and App window

**Window mode** in Settings › General picks one of two modes.

| | **Quick panel** (default) | **App window** |
|---|---|---|
| Looks like | A panel over a dimmed screen, no taskbar button. | A normal window with a title bar and a taskbar button. |
| Closes | When you click elsewhere (**Hide when clicking elsewhere**), after you open an app (**Hide after opening an app**), or with the X or shortcut. | Only when you close or minimize it. |
| Position | Fills the monitor the pointer is on. | Remembers its place and size. |
| Pin | Turns the panel into a small window that stays on top. | Keeps the window above other windows. |

Pick Quick panel to flick Deck open and dismiss it. Pick App window to keep it open on a second monitor.

## The top bar

- **Search** finds pages, settings, apps, games, files and commands, and does sums and conversions. See [Launcher and search](launcher.md).
- **Activity** opens [What Deck changed](#what-deck-changed) and recent results.
- The pin keeps Deck on top (see above). The X hides Deck.

## The sidebar

Fourteen areas, with Settings alone at the bottom. Clicking an area opens its first page; its other pages are tabs above the page. The full list is in [Find your way around](find-your-way.md#the-areas).

- Hardware pages hide themselves when your PC has nothing for them. [This PC](this-pc.md) shows what Deck found.
- Some areas show a live hint, such as your CPU profile or your next timer.
- To reorder, drag an area or a tab, use Alt+arrow keys on it, or use **Arrange** in Settings › General. **Reset order** puts it back. See [Settings](settings.md#sidebar).
- To hide areas or pages, use [Settings › Features](settings.md#features).

## The tray icon and its menu

If you can't see the icon, click the up arrow next to the clock and drag Deck's icon onto the taskbar. Right-click it for the menu. Items only show when your PC has the hardware and you have not hidden the page.

| Item | What it does |
|---|---|
| **Open Deck** | Shows Deck. |
| **Open Clipboard** | Opens the Clipboard page. |
| **Keep awake** | Keeps the PC awake until you turn it off. See [Power](power.md). |
| **Settings** | Opens Settings. |
| **What Deck changed…** | Opens the list of changes Deck is holding. |
| **Gaming** | **Show or hide Deck bar**, **Deck game mode**, **Close apps now**, the **Death counter** items and the **Controller** overlay items. |
| **Hardware** | **CPU profile**, **GPU profile**, **All fans**, **Lights off**, **Cooler display off**, **Clear RAM**, **Reset all hardware** and **Sound output**. Clear RAM and Reset all hardware need administrator. |
| **Desktop** | **Show music card**, **Text extractor**, **Pick a color**, and **Voice** while the mic is running. |
| **Quit Deck** | Quits Deck. |

**Reset all hardware** hands the fans to the BIOS, the graphics card to its defaults and the CPU to its original power plan, then lists what each part did.

### What quitting does

Quitting stops everything Deck runs in the background: hot corners, clipboard history, timers, Keep awake, the phone link and any Deck game mode session. Fans go back to the BIOS and the GPU fan to the driver. A shutdown plan you set is kept and carries on when Deck starts again in the same Windows session ([Power](power.md)).

## The Home tiles

A new install shows **Sound**, **Pinned & frequent apps**, **PC status**, **Power & timers** and **Now playing**, plus the game tile while a game runs. Add the rest with **Edit Home**. Tiles update live, but a tile you are using is left alone until you finish.

| Tile | What it shows |
|---|---|
| **Current game** | The game in front (**Playing now**) or the last one (**Last played**): its profile, **Review in Game profiles**, CPU and GPU chips, and its death count with **+1 death** and **Undo** if it has a death counter. While a game runs, the ⋯ menu has **Not a game**. See [Game profiles](gaming.md). |
| **PC status** | A ring and **Temp**, **Speed**, **Power** for CPU and GPU, **Used**, **Free**, **Total** for memory, and download and upload for **Network**. **Energy** shows **Today**, **This month** and **Gaming** in kWh and opens [Power use](power-use.md). **Choose sensors** picks the cards and **Drives and free space**. |
| **Sound** | Master volume, the default output and up to three apps. See [Mixer](sound.md). |
| **Pinned & frequent apps** | Up to eight apps. Right-click one for **Open**, **Show file** and **Pin to home** or **Unpin**. |
| **Power & timers** | Your shutdown plan with **Cancel**, timers, one-tap timers (5 to 60 min), **Keep awake** and **Shut down when…**. See [Power](power.md). |
| **Now playing** | The song or video playing, with previous, play/pause and next. |
| **CPU & GPU profiles** | Switch CPU and GPU profiles. **Set by** names the game that set them. |
| **Quick actions** | **Keep awake** and **Light mode** switches, and **Color picker**, **Text extractor**, **Ruler**, **Lock**, **Turn off display** and **Sleep** (Sleep asks first). |
| **Clock** | Time and a **Week** or **Month** calendar, with chips for **Staying awake**, a shutdown plan and timers. |
| **Network** | Download and upload speed. See [Network](network.md). |
| **Disk space** | Free space per drive; "Low space" above 95 % used. |
| **Clipboard** | Your five newest clipboard items. See [Clipboard](clipboard.md). |
| **Ready to play?** | The checks from Game profiles, each with its reason and a link to the fix. |
| **What Deck changed** | The same list as the Activity button. |
| **I want my PC to be…** | **Quieter**, **Faster in games** or **Use less power**: shows the CPU and GPU modes it would pick and what you give up. **Apply these** sets them; **Undo** goes back; **Forget previous choices** clears the memory. |

The CPU's clock, power and temperature need administrator. Without it the CPU card shows an **Admin** chip; click it to restart Deck as administrator ([why](getting-started.md#why-deck-needs-administrator)).

### Playing layout

Turn on **Home changes while you play** in Edit Home to give Home a second layout while a game runs. It has extra tiles: **Game while playing**, **CPU and GPU strip** and **Gaming actions**. Pick **Default** or **While playing** to choose which layout you edit.

## Editing Home

1. Press **Edit Home**.
2. Drag a tile's bar to move it and its corner to resize it. The eye hides it; **Fit** sizes it to its content.
3. **Add widget** lists the tiles that are not on the board.
4. **Fit to content** and **Line up rows** tidy the whole board. **List view** shows **All Home tiles** with width, height, **Move up** and **Move down**, for use with the keyboard.
5. Press **Done** to keep the changes, or **Discard changes** to undo everything since you started. **Reset layout** returns to Deck's default.

Your layout is part of your settings, so a [backup](settings.md#backups) includes it.

## What Deck changed

The **Activity** button beside search shows how many changes Deck is holding ("Activity · 2 changes") and opens one window with three parts.

- **What Deck changed**: each change Deck is holding now (a game mode, a GPU mode, fan speeds, Keep awake, a scheduled power action, Windows tweaks), with **Now**, **Before** and, for changes that end on their own, **Ends**. **Undo** ends one change; **Undo all** ends them all after one confirmation. CPU profiles, display, sound, startup fixes and removed apps are not in this list yet; undo them on their own pages.
- **Recent activity**: results from this Deck window (speed tests, cleanups, app updates) with **Running**, **Done**, **Failed** or **Info** and an **Open page** link. Up to 100 entries, kept until Deck quits. Failures you have not seen show as "N failed" on the button.
- **Other recent changes**: changes made from the tray, the phone or before the window reloaded.

To hide the button, turn off **Show Activity** in [Settings › Appearance](settings.md#appearance); the tray still has **What Deck changed…**.

## First run

The first time, Deck opens on Home with two cards:

- An introduction that says how to open Deck again, with **Change Deck's look**, **What Deck found on this PC** and **Dismiss introduction**.
- **First steps**: a few pages worth visiting on your PC. A tick means you visited it. **Dismiss first steps** removes the list.

Tours never start automatically. Press the tour button next to search to play the tour of the page you are on.

## Recommended setup

- Keep Quick panel with the top-left corner, and set a keyboard shortcut for opening Deck over games.
- App window suits a laptop or a second monitor.
- With two monitors, use an outer corner or the shortcut.
- Run Deck as administrator so Home shows CPU temperature, clock and power.

## Troubleshooting

**The hot corner does nothing.** Check the corner's action is **Open Deck** and Window mode is **Quick panel**. Use an outer corner of the whole desktop. A fullscreen game blocks it unless **Works over fullscreen games and videos** is on. Move out of the corner and back in.

**Deck opens by accident.** Raise the corner's delay, pick another corner, or set it to **Does nothing** and use the shortcut.

**The tray icon is missing.** Look under the up arrow next to the clock. If Deck isn't running, start it from the Start menu.

**The CPU card shows "Admin".** Click it and accept the Windows prompt. Deck restarts as administrator and stays that way at each start.

**A tile is empty.** Games, deaths and FPS appear after you play with Deck running. Drives can be hidden in **Choose sensors**.

**Home looks wrong.** Press **Edit Home**, then **Reset layout**.

## FAQ

**Can the hot corner trigger anti-cheat?** No. It only reads the pointer position. See the [FAQ](faq.md#safety-and-anti-cheat).

**Does Deck start with Windows?** Yes, hidden in the tray (**Start with Windows** in Settings › General).

**Can I hide the game banner?** Yes: **Edit Home**, then hide **Current game**.

**Is the pin the same as "always on top"?** In App window, yes. In Quick panel it also stops the panel closing when you click elsewhere.
