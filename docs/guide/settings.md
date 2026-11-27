Where to find it: Settings › General

# Settings

Settings holds Deck's app-wide preferences: how it opens and looks, search, profile options, warnings, backups and updates.

A feature's own settings sit on that feature's page, so each setting is in one place: Game profiles (end of the Games tab), Session reports (its ⚙ menu), Crashes (Profiles), Death counter (under Now), Soundboard (Options card), Clipboard (under the history), Apps (Store apps & updates), Device batteries, PC to PC, Phone and Project sync. Each part of Settings starts with an **On their own pages** row of links to those pages.

## Finding a setting

- **Find a setting** (top of the list on the left): type a word ("hot corner", "battery"). The list keeps the parts that match, and the open part hides rows that don't. **Back to results** returns to the matches after you open one.
- The search box at the top of Deck finds every setting, including those on feature pages, and opens the page that holds it.
- A setting that differs from its default shows **Changed from default** and a **Back to default** button that names the default value. The end of each part says **All at defaults** or **N changed from default**. Rows with their own save button don't carry the mark.

## The parts of Settings

The parts are listed on the left in three groups. Below 1000 px wide the list becomes a drop-down above the part.

| Group | Part | What it holds |
|---|---|---|
| Deck | [General](#general) | How Deck opens and starts, keyboard shortcuts, the sidebar. |
| | [Appearance](#appearance) | Theme, accent color, opacity, animation, units. |
| | [Features](#features) | Which areas and pages Deck shows. |
| | [Search](#search) | Web search provider, saved actions, local file search. |
| | Notifications | Drive warnings ([Drive health](drives.md#drive-health-warnings)) and **New items** (**New startup items**, **App first uses the network**). |
| Hardware and connections | CPU and GPU | What CPU and GPU profiles share: shortcuts, the switch notice, plugged in and on battery. See [CPU](cpu.md#settings-for-cpu-profiles) and [GPU](gpu.md#settings-for-gpu-profiles). |
| | Connections | **Outside actions**: what shortcuts, scripts and deck:// links may run. See [PC to PC](pc-to-pc.md#actions-from-the-command-line-and-links). |
| Deck's data | [Data & recovery](#data--recovery) | Backups, Deck's storage. |
| | [About](#about) | Help, version and updates, support report, tester mode, diagnostics, quitting. |

## General

### Opening Deck

| Setting | What it does | Default |
|---|---|---|
| **Window mode** | **Quick panel**: a panel over a dimmed screen. **App window**: a normal window that stays open. See [Home](home.md#opening-and-closing-deck). | Quick panel |
| **Keyboard shortcut** | Opens and closes Deck. Click it and press the keys; **Esc** cancels, **Backspace** clears. Shows **Taken by another app** if another program holds the keys. | None |
| **Top left corner**, **Top right corner**, **Bottom left corner**, **Bottom right corner** | What resting the pointer in that corner does: **Does nothing**, **Open Deck**, **Show the desktop**, **Lock the PC**, **Turn off display** or **Sleep**, with a slider for how long to rest (0 to 1000 ms). Quick panel mode only. | Top left: Open Deck |
| **Works over fullscreen games and videos** | Lets the corners work while a game or video fills the screen. Deck then opens without taking focus from the game. | Off |
| **Hide when clicking elsewhere** | Closes the panel when you click another window. The pin overrides it. | On |
| **Hide after opening an app** | Closes the panel after you launch something from it. | On |

### Keyboard shortcuts

A read-only list of every Deck shortcut, with **Off** when its feature is off, **Used twice** when two shortcuts share a key (only one works) and **Taken by another app**. The pencil opens the place where that key is set. Every action a shortcut runs is also in a menu.

### Starting Deck

| Setting | What it does | Default |
|---|---|---|
| **Start with Windows** | Starts Deck hidden in the tray when you sign in, through Deck's own scheduled task, so no prompt appears. Changing it needs administrator. | On |
| **Restart after a crash** | Reopens Deck if it closes unexpectedly. | On |

#### Restart after a crash

When Deck is ended from outside (a crash, Task Manager, a driver installer), a small helper hands the fans and graphics card back to the BIOS and driver, waits for any driver installer to finish, then starts Deck again, hidden. After three crashes in ten minutes it stops: the next start uses BIOS fan control and holds hardware tuning for your review, so a crash can't turn into a loop. Leave it on.

### Sidebar

| Setting | What it does |
|---|---|
| **Group and page order** | Drag groups or page tabs, or press **Alt+arrow keys** on them. **Arrange** opens a list of every group and its pages with move-up and move-down buttons. **Reset order** returns to the default order after a confirmation. |
| **Sidebar style** | **Automatic** shows only icons below 1000 px wide, **Labels** always shows names, **Icons** always shows the narrow rail. Default: Automatic. |
| **What Deck found on this PC** | **Show controls** opens a list of which areas your PC supports (**Available**, **Partly available**, **Not available**), with links to CPU, GPU, Fans and This PC. |

To show or hide Project sync, use [Features](#features).

Tours never start on their own: press the tour button next to the search box to play the tour of the page you are on.

## Features

Hide areas or pages you don't use. Hiding only removes the entry.

- **Sidebar areas** at the top says how many areas and pages are shown, with **Show everything** to bring them all back.
- Each area has a card with **Show in sidebar** (**Shown** or **Hidden**) and one button per page. When an area is hidden its pages say **Hidden with area**, and their own choices come back when you show it again.
- A card's links open the real switches of that area (for example the death counter or Keep awake), in case you want a feature off rather than hidden.
- Pages your hardware doesn't support say **Not available on this PC**, with the reason.

Hiding removes the entry from the sidebar, search, Home and the tray menu. It never stops anything, changes how a feature works, or deletes data: hidden timers and Keep awake keep running. Home and Settings can't be hidden. A link to a hidden page still opens it, with a short notice and a **Show it** button. Project sync starts hidden unless it is on.

## Appearance

### Look

| Setting | What it does | Default |
|---|---|---|
| **Theme** | Eight themes: Midnight, Graphite, OLED black, Pure black, Nord, Forest, Plum, Ember. Each card previews the theme in your accent. | Midnight |
| **Accent color** | Blue, Violet, Purple, Pink, Orange, Amber, Green or Teal. | Blue |

OLED black and Pure black look best and save power on OLED screens.

### Window

| Setting | What it does | Default |
|---|---|---|
| **Opacity when Deck can hide** / **Opacity when pinned open** | How see-through Deck's backgrounds are, 30 % to 100 %. Text keeps its color. | 100 % |
| **Show Activity** | Shows Activity by the search box: live changes, recent results and failures. Off hides it; **What Deck changed** stays in the tray menu. | On |
| **Animation effects** | How Deck appears: Zoom, Fade, Pop, Rise, Drop, Flip, Swirl, Blur in or None. **Preview** plays it. | Zoom |

### Performance & units

| Setting | What it does | Default |
|---|---|---|
| **Reduce effects** | No animations or shadows, and live values refresh every 3 seconds instead of every second. Good for older PCs. | Off |
| **Clock speeds** | **MHz** or **GHz**. Offsets on the Hardware pages stay in MHz. | MHz |
| **Network speed** | **Mb/s (megabits)** or **MB/s (megabytes)**. 8 megabits are 1 megabyte. | Mb/s |
| **Temperature** | **°C** or **°F**. Fan curves and limits stay in °C. | °C |

## Search

The search box at the top of every page finds apps, pages, settings, games and files ([Launcher and search](launcher.md)). This part sets what it uses.

### Web search

**Search provider** decides where web searches go: Google (default), DuckDuckGo, Bing, Brave or YouTube.

### Saved actions

Actions you run by typing their keyword in search: **New quicklink**, **New custom command** and **New chain**, each with **Edit**, **Run** and **Delete**. **Restore power plan** puts back a Windows power plan a chain changed. See [Launcher and search](launcher.md#saved-actions).

### Local file search

| Setting | What it does | Default |
|---|---|---|
| **File search** | Lists files and folders so search finds them instantly. **Indexed files** shows the count. Refreshes every 30 minutes. | On |
| **Search folders** | **Add folder**, remove a folder with its cross, **Refresh**. | Desktop, Documents, Pictures, Videos, Music, OneDrive |

Program folders, `node_modules`, `.git`, build output and AppData are skipped. If the list says **Partly indexed**, choose fewer folders or fix permissions, then press **Refresh**. The index stays on your PC.

## Data & recovery

### Backups

A backup holds your settings and profiles, fan and hardware settings, fan curves and the death counter's data and taught screens.

| Control | What it does |
|---|---|
| **Export my setup** | Lists the parts with check boxes and sizes. Then **Save to a file** (a `.zip`) or **Send to another PC** (to a paired PC over [PC to PC](pc-to-pc.md); secrets and clipboard history stay here). **Include secrets** (file only) adds the phone pairing key and your VirusTotal key and needs a **Backup password** of at least 12 characters. It can't be recovered, so keep it safe. Without it, every key and password is blanked. |
| **Import my setup** | Pick a file and enter its password if it has one. **Review restore** lists its parts; only the selected ones are restored. **Restore on next start** saves a recovery copy of your current setup first. Quit Deck from the tray and open it again to finish. |
| **Copies from before updates** | Deck saves a copy before each update and keeps the newest five. **Review and restore** opens one like a file. |
| **Include clipboard history in backups** | Adds clipboard history, but only to backups with a password. Weekly copies never include it. Off by default. |
| **Weekly backup** | Saves a copy about once a week, without passwords and keys. Off by default. |
| **Backup folder** | Where weekly copies go (default: Documents / Deck backups). **Choose folder** changes it. |
| **Weekly copies to keep** | 1 to 52, default 4. Older copies are removed. |

A restore never turns on a network service. Afterwards the phone remote, Project sync, PC to PC, automatic Deck game mode, automatic updates and weekly backups are off, and active CPU and GPU profile choices are cleared; turn them back on if you want them. A backup from a newer Deck is refused ("update Deck first").

A backup doesn't include alert rules and notification addresses ([Alerts](alerts.md)), the shutdown plan, game artwork, logs, driver files or tweak undo records.

Recommended: turn on **Weekly backup**, and make a backup with a password before you move to a new PC or reinstall Windows.

### Deck's storage

**Saved on this PC** shows how much room Deck's data uses, with **Refresh sizes**, then each area with its limit. **Artwork cache limit** is 16 to 4096 MB (default 256 MB; the oldest artwork goes first). Packages are installers you downloaded through Deck and stay until you remove them.

**Clear artwork** (under **Reset**) removes downloaded game artwork; it downloads again when needed, and your settings and taught images stay. [Clean up](cleanup.md) also lists it as **Deck's game artwork**.

## About

### Help

**User guide** › **Open guide** opens this guide in your browser.

### Updates

| Control | What it does | Default |
|---|---|---|
| **Version** | Deck's version, and whether it runs as administrator. | |
| **Check for updates** | Looks for a newer Deck now. **Install** appears with the new version number when one is found, and **Stop the download** while it downloads. | |
| **Previous version** | Appears when an earlier version is kept: **Go back to** that version saves a backup first, then restores it and restarts Deck. | |
| **Beta releases** | Includes preview versions. Turn it off to follow stable releases again; Deck never downgrades automatically. | Off |
| **Update automatically** | Checks once a day and installs when no game or fullscreen program is in front. Needs administrator. Off: Deck checks only when you press **Check for updates**. | On |
| **What is new in Deck** | Shown after an update: what changed, then **What moved**: the controls that moved in the redesign, each with **Open** to go to its new place. **Mark as read** hides it. | |

How updates are kept safe:

- Deck downloads only the setup and its checksum from the project's public GitHub releases page.
- The download must carry Deck's own signature and match its SHA-256 checksum, or it is thrown away. The card then says what was checked.
- With administrator, the update installs silently once no game or fullscreen program is in front ("It installs when the game or fullscreen program closes."). Otherwise press **Install**, with one Windows prompt.
- The setup closes Deck, installs over it and starts it hidden again. Your settings and profiles stay.
- A copy of Deck in a folder your own account can change doesn't update itself.

### Support report

A text report of what this PC is and what Deck found. Attach or paste it when you report a problem.

- **Copy report** puts it on the clipboard; **Save report** writes it to a file and shows it in Explorer.
- **Include crash files (may contain private data)** adds Deck's crash reports. Keep it off unless someone asks.
- If Deck controls lighting on your PC, **Save report** asks **Add a lights test?**: the lights cycle red, green and blue for 15 seconds, then return. Choose **Add the test**, **Save without it** or **Cancel**.

The report covers Deck (version, administrator, engines, shortcut keys), Windows, the computer (board, BIOS, battery, processor, memory, graphics), what Deck detected, the hardware it found, RivaTuner, drive health, this run and the previous one, background workers, problems and the last 80 log lines. It also lists maker apps, ACPI devices and HID devices, to help add support for more hardware; nothing is sent to the devices. File paths are shortened and serial numbers are left out.

### Tester mode

For people testing Deck on hardware it doesn't know yet (AMD or Intel graphics, laptops, headsets, AIO coolers).

1. Turn on **Tester mode** (off by default, in the Support report card).
2. A **Tester details** card shows what Deck detected: the processor, each graphics adapter with its id, the interfaces that answer, graphics and cooler sensors, plugged-in headsets with the battery Deck read, and Bluetooth batteries. **Control paths (read, change)** lists what Deck can read and change, and why not.
3. Take a screenshot, or press **Copy tester report**.
4. Turn it off when the test is done.

The tester report leaves out file paths, PC, user and device names, serial numbers and log lines. Tester mode only reads: it changes nothing.

### Diagnostics

**Log detail by area** sets how much Deck logs for each area by name: Graphics card, Fans, lights and sensors, CPU profiles, Updates, Backup and restore, Phone remote, Background tasks, Interface, Memory and Everything else. Each can be **Normal** (default), **Debug** or **Warnings only**; warnings and errors are always kept. A line says whether background tasks are running normally, and **Background task and memory details** shows them with Deck's memory use.

Leave everything on Normal. Set one area to Debug only while you reproduce a problem.

### What Deck exposes

A read-only list of what Deck has opened on this PC: **Network ports**, **Firewall rules**, **Scheduled tasks** and **Services**. Each row says why it is there and shows **As expected**, **Look at this** or **Not checked** (for example a rule that needs administrator to read).

### Quit Deck

**Quit Deck** stops everything: the hot corners, clipboard history, timers, shutdown plans, Keep awake, the phone link and any Deck game mode session. Fans return to the BIOS and the GPU fan to the driver. You are asked first, because timers and shutdown plans stop too.

## Where Deck stores data

All of it is on your PC. `%APPDATA%` and `%LOCALAPPDATA%` are your own Windows user folders.

| What | Where |
|---|---|
| Program | `C:\Program Files\Deck` (updates download to an `updates` folder only administrators can change) |
| Settings and profiles | `%APPDATA%\Deck\settings.json` (with a `.bak` copy; a damaged file is set aside, never reset silently) |
| Fan, lighting and display settings, fan curves | `%APPDATA%\Deck\hardware\settings.ini` and `curves.ini` |
| Alert rules and notification addresses | A separate file next to the settings |
| Clipboard history | `%APPDATA%\Deck\clipboard\history.json` |
| Death counter | `%APPDATA%\Deck\deaths\` (plus per-game files under `%LOCALAPPDATA%\Deck`) |
| Game sessions, found games, artwork | `boost.json`, `boost-history.json`, `games.json`, `art\` in `%APPDATA%\Deck` |
| Drive health history | `%APPDATA%\Deck\drive-health.json` |
| Sensor log (when on) | `%APPDATA%\Deck\monitor.csv` |
| Shutdown plan | `%APPDATA%\Deck\plan.json` (removed when the plan ends) |
| Windows tweaks undo records | `%APPDATA%\Deck\tweaks.json` |
| PC to PC, Project sync | `%APPDATA%\Deck\transfer\`, `%APPDATA%\Deck\claude-sync\` |
| Log | `%LOCALAPPDATA%\Deck\logs\deck.log` (2 MB per file, four older files kept) |
| Crash files | `%LOCALAPPDATA%\Deck\crashes` |
| Store downloads | `%LOCALAPPDATA%\Deck\store\` |
| Hardware driver | `C:\ProgramData\Deck\pawnio\` |

- Hardware settings are also fingerprinted in the registry, so Deck doesn't trust files another program changed behind its back.
- Secrets (phone, PC to PC and Project sync keys, your VirusTotal key, ntfy and Discord addresses) are encrypted for your Windows account, so a copy on another account or PC can't read them.
- The log hides tokens, passwords, keys and pairing codes, and removes your user and PC names from paths. Logs stay on your PC.

To remove Deck's data after uninstalling, delete the `Deck` folders listed above.

## Privacy: what leaves your PC

Deck needs no account and uploads nothing on its own. Only these features contact the internet, most only when you use them:

| Feature | Contacts | Why |
|---|---|---|
| Updates | GitHub (the project's public releases) | Look for and download a newer Deck. Off with **Update automatically**. |
| Game artwork and details | Steam, Epic, GOG, PCGamingWiki, Wikipedia | Covers for games found on your PC, and which Steam apps are games (app numbers only). **Clear artwork** removes them. |
| Currency conversion in search | A public exchange-rate service | Rates for the converter. |
| Speed test | Cloudflare | Only when you run it. |
| Display schedule by sunset | A public location-from-IP service | Only when you use the sunset schedule. |
| File safety check (Processes) | VirusTotal | Only with your own key, when you ask. |
| Store apps | Microsoft Store servers | Only when you use Store features on Apps. |
| Notifications out | The ntfy or Discord address you typed | Only if you turn it on ([Alerts](alerts.md)). |
| Share links, Phone, PC to PC, Project sync | Your own devices (or Tailscale for an internet share link) | Off until you turn them on. |

A web search opens your search site in your browser. Deck never injects into games or reads their memory.

## Recommended setup

- **Most people:** keep the defaults, pick a theme and turn on **Weekly backup**.
- **Gamers:** leave **Works over fullscreen games and videos** off, or use a shortcut; keep **Update automatically** on (it never installs while a game is in front); turn on **Reduce effects** for the lightest Deck.
- **Privacy-minded:** turn off **Update automatically** and check by hand, leave Notifications out and VirusTotal off. Deck works without them.
- **Older PCs:** turn on **Reduce effects** and search fewer folders.

## Troubleshooting

**The hot corner stopped working after I changed window mode.** The corners only work in Quick panel mode. In App window mode use the shortcut or the tray icon.

**Start with Windows does nothing.** It changes Deck's scheduled task, which needs administrator. Press **Restart as administrator** on any page that shows **Needs administrator**, or reinstall Deck. See [Getting started](getting-started.md#why-deck-needs-administrator).

**The shortcut says "Taken by another app".** Pick different keys.

**A restore didn't apply.** It applies at the next start. Quit Deck from the tray (closing only hides it) and open it again. If Deck says the settings need a newer version, update Deck first.

**After a restore some things are off.** This is on purpose: a restore turns off network services, automatic updates, weekly backups and automatic Deck game mode. Turn them back on.

**Weekly backup didn't run.** It runs about once a week while Deck runs. If the folder can't be written, Deck says so; choose another folder.

**An update failed.** The card shows the reason (often no internet). Press **Check for updates** to try again, or go back with **Previous version** if Deck offers it.

**Search doesn't find my files.** Check that **File search** is on, the folder is in the list and not skipped, then press **Refresh**.

**Deck uses too much disk space.** In Data & recovery › Deck's storage press **Clear artwork** or lower the **Artwork cache limit**.

**I want to start over.** Back up, quit Deck and move `%APPDATA%\Deck\settings.json` away. Deck starts with defaults.

## FAQ

**Is Deck safe to leave running?** Yes. If Deck is ended from outside, a helper hands the fans and graphics card back to the BIOS and driver.

**Does Deck need administrator?** For fans, CPU and GPU tuning, CPU temperature and silent updates, yes. Deck starts as administrator through its own scheduled task, so there is no prompt at each start. Everything else works without it, and apps Deck opens start as your normal account. See [Getting started](getting-started.md#why-deck-needs-administrator).

**Can I move Deck to another PC?** Install Deck there, then use **Export my setup** › **Send to another PC**, or a file with a password, and **Import my setup**. Alert rules aren't included.

**Can I use Deck offline?** Yes. Updates, artwork, currency rates and the speed test need the internet; everything else is local.

**Will settings affect games or anti-cheat?** No. Deck never injects into games or reads their memory.

**Where do I turn off the death counter, overlay, Deck bar or controller overlay?** On their own pages: [Death counter](death-counter.md), [Performance overlay](overlay.md), [Deck bar](game-bar.md) and [Controller](controller.md).

**Why are some pages missing from the sidebar?** Hardware pages only show when your PC has something for them; see [This PC](this-pc.md).

**How do I uninstall Deck?** Use Windows' installed apps list; see [Getting started](getting-started.md#uninstalling).
