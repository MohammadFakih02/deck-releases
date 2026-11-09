# Settings

Settings is the one place for Deck's preferences: how it opens and looks, what search covers, game profiles, the death counter, CPU and GPU profile options, the clipboard, connections to your other PCs and phone, warnings, backups and updates. Pages that are settings in themselves (Overlay, Game bar, Flyouts, Fans, Lighting) stay where they are; each part of Settings ends with links to them under **On their own pages**.

**Where to find it:** the **Settings** button at the bottom of the sidebar, or **Settings** in the tray menu. The parts are listed on the left, grouped and coloured like the sidebar. **Find a setting** at the top of the list narrows it to the parts that match, and hides the rows of the open part that don't.

| Part | What it covers |
|---|---|
| [General](#general) | How Deck opens (window mode, hot corner, shortcut), starting with Windows, crash restart, the sidebar |
| [Appearance](#appearance) | Theme, accent colour, opacity, opening animation, low-spec mode, units |
| [Search](#search) | Web search provider, saved links and commands, local file search |
| Games | Automatic game profiles, the default profile, programs that are not games, crash records ([Gaming](gaming.md#gaming-settings)) and controller batteries ([Controller](controller.md)) |
| Death counter | Counting, stream text files, automatic counting, the in-game counter and the card after a death ([Death counter](death-counter.md#death-counter-settings)) |
| CPU and GPU | Profile shortcuts, the switch notice, the GPU profile at start, plugged in / on battery profiles, memory clean-up ([CPU](cpu.md#settings-for-cpu-profiles), [GPU](gpu.md#settings-for-gpu-profiles)) |
| Desktop | Clipboard history, snippets, plain-text paste ([Clipboard](clipboard.md#clipboard-settings)) and Store app updates ([Apps](apps.md)) |
| Notifications | Drive health warnings ([Drives](drives.md#drive-health-warnings)), with links to temperature alerts and break reminders |
| Connections | PC to PC ([PC to PC](pc-to-pc.md#pc-to-pc-settings)), Workspace Sync ([Workspace Sync](workspace-sync.md#workspace-sync-settings)) and what a phone may do ([Phone](phone.md#power-and-uploads)) |
| [Data & recovery](#data--recovery) | Backups and restore, Deck's storage |
| [About](#about) | Version, updates, quitting Deck, diagnostics |

The parts that belong to one feature are described in full on that feature's guide page (linked above); this page covers the rest.

At the end of this page: [where Deck stores data](#where-deck-stores-data), [privacy: what leaves your PC](#privacy-what-leaves-your-pc), troubleshooting and an FAQ.

## Contents

- [Finding a setting](#finding-a-setting)
- [General](#general)
- [Appearance](#appearance)
- [Search](#search)
- [Data & recovery](#data--recovery)
- [About](#about)
- [Where Deck stores data](#where-deck-stores-data)
- [Privacy: what leaves your PC](#privacy-what-leaves-your-pc)
- [Recommended setup](#recommended-setup)
- [Troubleshooting](#troubleshooting)
- [FAQ](#faq)

## Finding a setting

- **Find a setting** (top of the list on the left): type a word ("hot corner", "battery", "obs"). The list keeps the parts whose settings match; the open part hides rows that don't match. Clear the box to see everything again.
- The search box at the top of Deck also finds the most used settings ("Clipboard settings", "Profile shortcut preferences", "Deck updates").

## General

### First start

The first time you open Deck, Settings opens on **Choose your look**: pick a theme (Midnight, Graphite or Forest are offered first; **All themes and accents** unfolds the rest) and press **Done**. You can change it any time under Appearance. A short introduction, **What Deck found on this PC**, may also appear at the top of General the first time. It lists which feature areas your PC supports (Available / Partly available / Not available) with switches for **Clipboard history** and **Local file search**, shortcuts to the CPU, GPU, Fans and This PC pages, and a **Done** button. You can bring it back later with **Show introduction** at the bottom of General.

### Opening Deck

See [Home](home.md) for what each option feels like in use.

| Setting | What it does | Default | Notes |
|---|---|---|---|
| **Window mode** | **Quick panel**: a popup over a dimmed screen. **App window**: a normal desktop window. | Quick panel | Quick panel is for glancing; App window stays open beside your apps. |
| **Keyboard shortcut** | Opens and closes the panel (Quick panel) or brings the window forward / minimises it (App window). | None | Click the button, press the keys. **Esc** cancels, **Backspace** clears it. If another program already uses those keys the button says "Taken by another app. Choose another shortcut." |
| **Hot corner** | Move the pointer to this corner to open Deck: Off, Top left, Top right, Bottom left, Bottom right. | Top left | Quick panel mode only. |
| **Hot corner delay** | How long the pointer must rest in the corner, 0 to 1000 ms. | 250 ms | Only shown when the hot corner is not Off. Raise it if Deck opens by accident. |
| **Works over fullscreen games and videos** | Whether the hot corner works while a game or video fills the screen. | Off | Off avoids opening Deck by accident when you flick into a corner mid-game. The keyboard shortcut works either way. When on, Deck opens without taking focus from the game. |
| **Hide when clicking elsewhere** | The panel closes when you click another window. | On | Quick panel only. The pin (top bar) overrides it. |
| **Hide after opening an app** | The panel closes after you launch something from it. | On | Quick panel only. |
| **Start with Windows** (*Starting*) | Deck starts hidden in the tray when you sign in. | On | It works through Deck's own scheduled task, so no prompt appears. Turning it off or on changes that task; this needs Deck to be running as admin (use **Set up** if the switch does nothing). |
| **Start again after a crash** (*Starting*) | Reopens Deck if it closes unexpectedly. | On | After three crashes within ten minutes Deck stops restarting itself, and the next start comes up with fans on BIOS control and no overclock, so a crash can never turn into a loop. Leave it on. |

#### Start again after a crash

When Deck is ended from outside (a crash, Task Manager, a driver installer) a small helper process hands your fans and graphics card back to the BIOS and driver, waits for any driver installer to finish, and then starts Deck again, hidden. Three such endings within ten minutes mean something keeps killing it, so it stops and the following start is in a safe state (BIOS fan control, no overclock) until you say otherwise. If you have turned on [Notifications out](alerts.md#notifications-out) for crash reports, you will get a message.

### Sidebar

| Setting | What it does |
|---|---|
| **Group and page order** | Drag sidebar groups or page tabs to reorder them. **Reset order** (enabled once you have reordered) returns them to the default after a confirmation. |
| **Show Workspace Sync** | Workspace Sync only appears in the sidebar while it is on, unless you tick this. See [Workspace Sync](workspace-sync.md). |
| **What Deck found on this PC** > **Show introduction** | Shows the introduction again. |

### Page tours

The first time you open a page, a short tour lights up its main parts one at a time (its tabs, a key panel, the main buttons), with a sentence beside each. Use **Next** and **Back** (or the arrow keys), **Skip** to end this page's tour, or **Skip all tours** to stop tours on pages you haven't opened yet. **Esc** also ends it. The **✦** button next to the search box plays the tour of the page you are on again, at any time.

| Setting | What it does | Default |
|---|---|---|
| **Show a tour the first time a page opens** | Off: tours only play when you press ✦. **Skip all tours** turns this off. | On |
| **Start the tours over** > **Reset** | Every page shows its tour again on your next visit. | |

**On their own pages:** **Home layout** opens Home's editor (which tiles show, and their size).

## Appearance

### Appearance

| Setting | What it does | Default |
|---|---|---|
| **Theme** | Eight themes: **Midnight** (default), Graphite, OLED black, Pure black, Nord, Forest, Plum, Ember. Each card previews the theme in the current accent. | Midnight |
| **Accent** | Eight accent colours: Blue, Violet, Purple, Pink, Orange, Amber, Green, Teal. | Blue |
| **Opacity with pin off** / **Opacity with pin on** | How see-through Deck's surfaces are, 30 % to 100 % in steps of 5. Only the backgrounds fade (frosted); text and the accent keep their colour. The pin has its own value, so a pinned floating panel can be fainter than the normal one. | 100 % |
| **Opening animation** | How Deck appears: Zoom (default), Fade, Pop, Rise, Drop, Flip, Swirl, Blur in, None. **Preview** plays it. | Zoom |

OLED black and Pure black save power on OLED screens and look best on them. Use a lower opacity if you want to see what is behind a pinned panel.

### Performance and units

| Setting | What it does | Default |
|---|---|---|
| **Low-spec mode** | No animations or soft shadows, and live readings refresh every 3 seconds instead of every second. The opening animation is off while this is on. | Off |
| **Clock speeds** | Show clocks in **MHz** or **GHz**. Offsets you type on the Tune pages stay in MHz. | MHz |
| **Network speed** | **Mb/s** (megabits) or **MB/s** (megabytes); 8 megabits equal 1 megabyte. | Mb/s |
| **Temperature** | **°C** or **°F**. Fan curves and limits stay in °C. | °C |

Recommended: turn **Low-spec mode** on for older PCs, or to keep Deck as light as possible while you play.

## Search

The search box at the top of every page looks through apps, pages, settings, games, files and more (see [Home](home.md#the-top-bar-search-pin-and-close) and [Launcher](launcher.md)). This tab controls what it uses.

### Web search

**Search provider** decides where "search the web" goes: **Google** (default), DuckDuckGo, Bing, Brave or YouTube.

### Quicklinks, custom commands and chained actions

Saved actions you run by typing their keyword into the search box. Buttons: **New quicklink**, **New custom command**, **New chain**, and **Undo chain's power plan**.

- A **quicklink** is a website address with `{query}` in it (for example a search on a site you use). The text you type after the keyword is encoded safely into the link. Only `http` and `https` addresses.
- A **custom command** runs a program (a full `.exe` path) with arguments, one per line, with an optional `{query}`; it is stopped after its time limit (1 to 600 seconds, default 30).
- A **chain** runs steps in order: switch sound output, CPU profile, GPU profile, power plan, open an app. A failed step stops the rest. **Undo chain's power plan** puts back the Windows power plan that a chain changed.

Each saved action has **Edit**, **Run** and **Delete**. The first time you run a saved action in a session Deck shows exactly what it will do and asks you to confirm. More in [Launcher](launcher.md).

### Local file search

| Setting | What it does | Default |
|---|---|---|
| **Find files from the search box** | Builds a list of files and folders so search can find them instantly. Shows how many items it found and how long reading took; refreshes every 30 minutes. | On |
| **Folders search looks in** | **Add folder**, remove with the red cross, **Refresh now**. | Desktop, Documents, Pictures, Videos, Music, OneDrive |

Deck skips program folders, `node_modules`, `.git`, build output and AppData. If the index is "partly indexed" (too many files, or folders Deck could not read) the page tells you which folders and why; choose fewer folders or fix permissions, then refresh. Turn the main switch off and the folder list is greyed out.

The index is Deck's own list on your PC; it is not sent anywhere.

## Data & recovery

### Backups

A Deck backup saves your settings and profiles, fan and hardware settings, fan curves, clipboard history and the death counter's data and taught screens into one file.

| Control | What it does |
|---|---|
| **Back up Deck to a file** | Pick a file; Deck writes a `.zip`. **Include secrets** adds the phone pairing key and your VirusTotal key, and needs a password of at least 12 characters (it cannot be recovered, so keep it safe). Without it, every key, token and password is blanked. |
| **Restore from a file** | Choose a backup (enter its password if it has secrets). Deck shows **Review restore** with the files and their sizes. **Restore on next start** schedules it; a recovery copy of what you have now is saved first. Quit Deck from the tray and open it again to finish. |
| **Weekly backup** | Saves a copy about once a week, without secrets, to your chosen folder. Off by default. |
| **Backup folder** | Where weekly copies go (default: a **Deck backups** folder in your Documents). |
| **Weekly copies to keep** | 1 to 52, default 4. The oldest are removed beyond that. |

What a restore does **not** do: it never turns on a network service or startup tuning. After a restore the following are switched off and you turn them back on if you want them: the phone remote, Workspace Sync, PC to PC, automatic Game mode start, automatic updates and weekly backups. Active CPU and GPU profile choices, the GPU startup profile and the plugged-in / battery profile choices are cleared. Restoring a newer backup into an older Deck is refused ("update Deck first").

A backup does **not** include: alert rules and notification addresses ([Alerts](alerts.md)), the shutdown plan, game artwork, logs, driver files or tweak undo records.

Recommended: keep **Weekly backup** on with the default 4 copies, and make a manual backup (with secrets and a password, if you use the phone remote) before moving to a new PC or reinstalling Windows.

### Deck's storage

Shows how much room Deck's saved data uses, by area, and the **Artwork cache limit** (16 to 4096 MB, default 256 MB), checked hourly. **Clear artwork** removes downloaded game artwork (it is downloaded again when needed; your settings and taught images stay). **Refresh sizes** re-measures. Logs rotate, and crash files keep at most eight and 64 MB, so none of it grows without limit.

## About

### Deck

**User guide** > **Open the guide** opens this guide in your browser. Searching "guide" in Deck does the same.

Shows the **Version** and whether Deck is running as admin ("Running as admin, so hardware controls and Windows settings work." or "Running without admin rights.").

### Updates

| Control | What it does | Default |
|---|---|---|
| **Check now** | Looks for a newer Deck immediately. | |
| **Install *version*** | Appears when an update is available. | |
| **Update by itself** | Checks once a day (and shortly after Deck starts) and installs when no game or fullscreen program is in front. Your settings and profiles stay. With it off, Deck checks only when you press Check now. | On |
| **Beta releases** | Include preview versions when checking. Turn it off to follow stable releases again; Deck never downgrades automatically. | Off |
| **Go back to *version*** | Appears when a previous version is available. Saves a backup first, then restores the previous setup and restarts Deck. | |
| **Stop the download** | Appears while an update is downloading, with a progress bar. | |
| **What is new** | After an update, shows what changed with **Mark as read**. | |

How updating works and how it is kept safe:

- Deck asks the project's public GitHub releases page (the same place you downloaded it) for the newest version. Only the setup file and its checksum are downloaded.
- The download is checked against its **SHA-256 checksum**. This guards against a damaged download; the checksum comes from the same release page.
- When Deck runs as admin (through its scheduled tasks) the update installs silently, once no game or fullscreen program is in front: it waits and shows "It installs when the game or fullscreen program closes." It never interrupts a game.
- Otherwise Deck tells you and installs when you press **Install**, with one UAC prompt.
- The setup closes Deck, installs over the old copy, recreates Deck's scheduled tasks and starts Deck hidden again.
- A copy of Deck in a folder your own account can change does not update itself.

### Quit Deck

**Quit Deck** stops everything Deck runs: the hot corner, clipboard history, timers, shutdown plans, keep awake, the phone link and any Game mode session. Fans go back to BIOS control and the GPU fan back to the driver. You are asked to confirm because timers and shutdown plans stop too. **Support report** opens the support report on the [This PC](this-pc.md) page.

### Diagnostics

Choose how much detail Deck records for troubleshooting. **Log levels** (fold) has one drop-down per area: gpu, hw, cpu, update, backup, remote, worker.supervisor, ui, memory and other. Each can be **Normal** (default; routine events), **Debug** (extra detail, for investigating a problem in one area) or **Warnings only**. Warnings and errors are always kept. The panel also shows the state of Deck's background workers and, once an hour, a memory sample (Deck's own memory and the web-view processes it uses). **Open support report** takes you to the report page.

Recommended: leave everything on Normal. Switch one area to Debug only while reproducing a problem, then switch it back.

## Where Deck stores data

All of it is on your PC. In the paths, `%APPDATA%` and `%LOCALAPPDATA%` are your own Windows user folders.

| What | Where |
|---|---|
| Program | `C:\Program Files\Deck` (SDL3 for the controller overlay is written here on first use; downloaded updates go to an admin-only `updates` folder) |
| Your settings and profiles | `%APPDATA%\Deck\settings.json` (a `.bak` copy is kept; a damaged file is set aside and recovered, never silently reset) |
| Fan, lighting and display settings, fan curves | `%APPDATA%\Deck\hardware\settings.ini` and `curves.ini` |
| Alert rules and notification addresses | A separate file next to the settings (addresses are encrypted for your Windows account) |
| Clipboard history | `%APPDATA%\Deck\clipboard\history.json` |
| Death counter | `%APPDATA%\Deck\deaths\` (plus per-game files under `%LOCALAPPDATA%\Deck`) |
| Gaming: sessions, found games, artwork | `boost.json`, `boost-history.json`, `games.json`, `art\` in `%APPDATA%\Deck` |
| Drive health history | `%APPDATA%\Deck\drive-health.json` |
| Sensor log (when on) | `%APPDATA%\Deck\monitor.csv` |
| Shutdown plan | `%APPDATA%\Deck\plan.json` (removed when the plan ends) |
| Tweaks undo journal | `%APPDATA%\Deck\tweaks.json` |
| PC to PC, Workspace Sync | `%APPDATA%\Deck\transfer\`, `%APPDATA%\Deck\claude-sync\` |
| Log | `%LOCALAPPDATA%\Deck\logs\deck.log` (2 MB per file, four older files kept) |
| Crash evidence | `%LOCALAPPDATA%\Deck\crashes` |
| Store downloads, update records | `%LOCALAPPDATA%\Deck\store\` |
| Hardware driver files | `C:\ProgramData\Deck\pawnio\` (for fan and sensor access) |

Hardware settings (fan curves, overclocks) are also fingerprinted in the registry (under Deck's own key) so a program that edits the files behind Deck's back is not trusted blindly; this is a protection against tampering, and deleting the key only means Deck trusts the current files at its next admin start.

**Secrets** (the phone remote key and pairing code, PC to PC and Workspace Sync keys, your VirusTotal key, the ntfy / Discord addresses) are stored encrypted for your Windows account (DPAPI), so a copy of the files on another account or PC cannot read them.

**The log** is masked as it is written: values after words like token, password, secret, API key, "Bearer", pairing code, sync key and phone key are hidden, and your user name and PC name are removed from paths. The same line repeated within a minute is counted instead of written again. Logs stay on your PC; a support report is only built when you ask for one, and crash files are only included in it after you agree.

To remove Deck's data after uninstalling, delete the `Deck` folders listed above (or run `uninstall.ps1 -Purge` if you installed from source).

## Privacy: what leaves your PC

Deck is a local app. It does not need an account. It does not upload your settings, logs, crash files or clipboard on its own. These are the only features that contact the internet, and most only when you use them:

| Feature | Contacts | Why |
|---|---|---|
| Update checks | GitHub (the project's public releases) | Look for and download a newer Deck. Turn off with **Update by itself**; **Check now** still works. |
| Game artwork and details | Steam's store and CDN, GOG's catalogue, PCGamingWiki, Wikipedia / Wikimedia | Download cover and banner pictures for games found on your PC. Cached on your PC; **Clear artwork** removes them. |
| Currency conversion in search | A public exchange-rate service | Rates for the search box's converter. |
| Speed test | Cloudflare's speed-test servers | Only when you press the speed test. |
| Display schedule by sunset | A public "approximate location from IP address" service | Only when you use the sunset schedule on the Display page. |
| Safety check of a file (Processes) | VirusTotal | Only if you add your own VirusTotal key and ask for a check. |
| Store apps | Microsoft's Store servers | Only when you use the Apps page's Store features. |
| Notifications out | The ntfy or Discord address you typed | Only if you turn it on. See [Alerts](alerts.md). |
| Share links, phone, PC to PC, Workspace Sync | Your own devices on your network (or Tailscale for an internet share link, if you open one) | Features you turn on; they are off until you do. |

A **web search** opens your chosen search site in your browser, like any other link.

Deck never injects into games and never reads their memory; its overlay, death counter, game bar and controller overlay work without touching a game process.

## Recommended setup

- **Most people:** keep the defaults. Choose a theme, keep **Start with Windows**, **Start again after a crash**, **Update by itself** and local file search on, and turn on **Weekly backup**.
- **Gamers:** leave the hot corner off over fullscreen, or turn the hot corner off and use a shortcut; keep **Update by itself** on (it never installs while a game is in front); use Low-spec mode if you want Deck to be as light as possible.
- **Laptops:** App window mode, a lower opacity pinned view if you like, and keep an eye on **Temperature** units (°C or °F).
- **Privacy-minded:** turn off **Update by itself** (and check manually), leave Notifications out off, leave VirusTotal off, and remove artwork with **Clear artwork** if you like; Deck works without any of them.
- **Old / low-power PCs:** turn on Low-spec mode and reduce the folders under Local file search.

## Troubleshooting

**The hot corner or shortcut stopped working after I changed window mode.** The hot corner settings only appear in Quick panel mode. In App window mode use the shortcut or the tray icon.

**"Start with Windows" does nothing.** It changes Deck's scheduled task, which needs admin. Open the CPU or Home page and press **Set up**, or reinstall Deck with the setup so the task is created.

**The shortcut button says "Taken by another app."** Pick different keys.

**A restore did not apply.** A restore is applied at the next start. Quit Deck from the tray (not just close it) and open it again. If Deck says the settings need a newer version, update Deck first.

**After a restore some things are off.** This is deliberate: the phone remote, PC to PC, Workspace Sync, automatic updates, weekly backups and automatic Game mode are switched off by a restore so a backup can never switch on a network service by itself. Turn them back on.

**Weekly backup did not run.** It runs about once a week while Deck is running. If the folder is not writable Deck shows "Weekly backup could not be saved". Choose another folder.

**An update shows "installs when the game closes".** Deck waits until no game or fullscreen program is in front. Close it or press Install when you are ready.

**An update failed.** The page shows the reason (often no internet connection). Press **Check now** to try again. With **Go back to *version*** you can return to the previous one if Deck offers it.

**Search does not find my files.** Check **Find files from the search box** is on, that the folder is in the list and not skipped (program folders, AppData, `node_modules`, `.git` and build output are skipped), and press **Refresh now**.

**Deck is using too much disk space.** Open Data & recovery > Deck's storage and use **Clear artwork** or lower the cache limit.

**I want to start over.** Back up first, then quit Deck and move `%APPDATA%\Deck\settings.json` away. Deck starts with defaults. (A damaged settings file is never overwritten silently; Deck keeps it aside.)

## FAQ

**Is Deck safe to leave running?** Yes. It sits in the tray, and a helper hands fans and the graphics card back to the BIOS and driver if Deck is ended from outside.

**Does Deck need admin?** For fans, CPU / GPU tuning, CPU temperature and silent updates, yes: Deck runs as admin through its own scheduled tasks so there is no prompt at each start. Without admin the rest still works. Apps Deck launches start as your normal user.

**Can I move Deck to another PC?** Install Deck there, then use a manual backup with a password (including secrets if you want the phone key) and restore it. Alert rules are not in the backup.

**Can I use Deck without the internet?** Yes. Updates, artwork, currency rates, the speed test and similar features need it; everything else is local.

**Does Deck collect data about me?** Deck does not upload your settings or logs. See [Privacy](#privacy-what-leaves-your-pc) for the list of features that contact the internet.

**Will changing settings affect games or anti-cheat?** Settings on this page (window mode, theme, search, backups, updates) do not touch games. Deck never injects into games or reads their memory.

**Where do I turn off the death counter, overlay, game bar or controller overlay?** On their own pages: [Death counter](death-counter.md), [Overlay](overlay.md), [Game bar](game-bar.md) and [Controller](controller.md).

**Why are some pages missing from the sidebar?** Hardware pages only show when your PC has something for them; see [This PC](this-pc.md).

**How do I uninstall Deck?** Use Windows' installed apps list, or `uninstall.ps1` if you installed from source (add `-Purge` to delete settings too). To remove your settings as well, delete the Deck folders under `%APPDATA%` and `%LOCALAPPDATA%` afterwards. Deck gives fans back to the BIOS and undoes its changes when it stops.
