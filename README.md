<div align="center">

<img src="docs/icon.png" width="96" alt="Deck icon">

# Deck

**One tray app for your Windows gaming PC.** A launcher, a live dashboard, PowerToys-style tools, full CPU / GPU / fan control, an in-game overlay, Windows tweaks with an exact undo, and a phone remote that can also be your PC's speaker and microphone. It replaces MSI Afterburner, your motherboard's fan software and the usual debloat scripts.

[![Release](https://img.shields.io/github/v/release/MohammadFakih02/deck-releases?label=download&color=4f8cff)](https://github.com/MohammadFakih02/deck-releases/releases/latest)
![Windows 10/11](https://img.shields.io/badge/Windows-10%20%7C%2011-0078d4)
[![License: MIT](https://img.shields.io/badge/license-MIT-green)](LICENSE)

<img src="docs/screenshots/home.png" width="860" alt="Deck's Home page: the game you're playing on top, then clock, PC readings, performance profiles, sound mixer and quick actions">

</div>

## Download

Get the setup (**`Deck_<version>_x64-setup.exe`**) from the [latest release](https://github.com/MohammadFakih02/deck-releases/releases/latest) and run it. Deck lives in the tray; open it by resting the mouse in the top-left corner of the screen, or by clicking the tray icon. What changed in each version is in [CHANGELOG.md](CHANGELOG.md).

> The setup isn't code-signed, so Windows SmartScreen may say "Windows protected your PC". Click **More info → Run anyway**.

The setup asks for admin rights once and installs Deck to `C:\Program Files\Deck` (an older per-user copy is removed; your settings stay). It also sets up Deck's admin start, so there is no "Set up" to press afterwards, and Deck starts hidden in the tray. From then on Deck updates itself from GitHub releases (when no game is in front; Settings → About) and starts again by itself if a crash or a graphics driver update ends it.

Hardware control (fans, lighting, CPU power limits, GPU tuning), most Windows tweaks, and the CPU's clock, power and temperature readings need administrator rights. Open any hardware page and click **Set up**, or **Needs admin** on Home's CPU card: one admin prompt, and from then on Deck starts with those rights through scheduled tasks, so it never asks again. Programs Deck opens for you still start as your normal account. How Deck keeps those admin rights from being borrowed and how to report a security problem are in [SECURITY.md](SECURITY.md).

**Needs:** Windows 10 or 11 (64-bit). Optional: [RivaTuner Statistics Server](https://www.guru3d.com/download/rtss-rivatuner-statistics-server-download/) for the in-game overlay (Deck can install it), an NVIDIA card for GPU tuning, [VB-CABLE](https://vb-audio.com/Cable/) (free) for the phone as a microphone (Deck fetches VB-Audio's own setup for you).

## What's inside

### Everyday

| | |
|---|---|
| **Home** | The game you're playing or played last on top, with its artwork, time played, sessions and profile chips, +1/Undo for games with a death counter, and a **Not a game** button if Deck picks up the wrong program. Then clock and calendar, now playing, PC cards (usage, clock, power and temperature for CPU, GPU, memory, VRAM or network; pick them with the tile's settings icon), one-click CPU/GPU profiles, sound mixer, pinned and frequent apps, quick actions, clipboard, timers and network. Drag tiles anywhere, resize them, hide them and bring them back. |
| **Search** | Start-menu and Store apps, files (Deck's own index), every Deck page, setting and tweak, a calculator, unit / currency / number-base conversion, games, clipboard and the web. Understands `timer 10m`, `sleep in 30m`, `awake 2h`, `kill discord`. |
| **Clipboard** | Text, Images and Files tabs, pins, search across a tab or all history, a selected-item inspector and "paste as"; skips password managers. History, image, paste and retention settings live in its Settings tab. |
| **Flyouts** | Optional cards that never take the focus: music (name first, cover later; controls and seek), volume, microphone, sound device, lock keys, brightness, airplane mode and charger. Volume can pair with music or share its card. Choose skips, song endings or both, with advanced end tolerance and per-app music rules. Show the current song from the tray. Each kind has its own switch and duration; all off by default. Native, noninteractive cards over games. |
| **Sound and mic** | Default output, master and per-app volume, media sessions; every microphone with level, boost, mute, a test meter, which mic apps and calls use, and Listen to this device; rename devices. |
| **Power & time** | **Keep awake** (shows Windows' own sleep and screen-off times; "until downloads finish"), **Timers & breaks** (timer creation above paired stopwatch and break reminders), **Shut down when…** a time comes, an app closes, downloads finish (browser, Steam or any download), the CPU, graphics card or disk goes idle, the network goes quiet, media stops or you're away, optionally followed by "then when the PC is idle", with a warning you can cancel. Every threshold, the warning, keeping the PC awake while waiting, waiting while you play and closing apps that hold it up are your choice. A time missed while the PC slept is skipped, not run on wake. |
| **Your look** | 8 themes (including OLED and pure black), accent colours, frosted see-through opacity (separate for pinned), opening animations, and a low-spec mode for older PCs. Scrollbars, switches, tick boxes and sliders are drawn to match. A quick panel over a dimmed screen, a normal window, or pinned as a floating window over your other apps. |

### Gaming

| | |
|---|---|
| **Gaming** | A profile for each game, switched on when it starts and back when it closes: GPU mode or profile, CPU profile or the fastest power plan, a frame rate limit kept by the NVIDIA driver (or RivaTuner) with your monitors' own refresh rates to pick from, game priority, and what frees up the PC (close apps, quieter background apps, free memory, paused downloads). Finds Steam, Epic, Riot, EA, Battle.net, Ubisoft and GOG games with their artwork, and also recognises whatever Windows itself lists as a game, windowed or fullscreen, while leaving out launchers, crash reporters and installers. Add a game by hand or mark a program as not a game. Keeps each session's FPS, watts and FPS per watt. |
| **In-game overlay** | Through RivaTuner (Deck can install it for you). A live preview stays beside the settings while you edit. Choose and group any reading, pick Afterburner-style looks and colours, and add a smooth frametime graph. Keys show the overlay, reset the figures and turn RivaTuner's framerate limiter on and off; the limit itself is set right there too. |
| **Controller overlay** | Your controller's buttons, sticks and triggers on screen over your games, drawn as a DualShock 4, a DualSense or an Xbox pad, matched to the one connected (or a compact strip, or keyboard & mouse keys). Five themes, three styles, PlayStation or Xbox labels, any size and corner, follows the game across monitors, fades when idle, stays out of recordings. Works with PlayStation, Xbox, GameSir and other controllers. |
| **Controller battery** | One tray icon per controller with its battery like a phone's (the percentage inside, green while charging, red when low), the same level on the overlay, and a warning at 15%. Reads GameSir dongles, PlayStation and Xbox controllers and Bluetooth pads, with no vendor software. |
| **Death counter** | Count your deaths in any game, per boss: attempts, wins, time and deaths before the first kill, play sessions, records and boss cards. Counts by itself in the games it knows, and in any other once you've counted a death there: from the death screen ("YOU DIED", "GAME OVER"…) or, for some games, the save file. It finds boss fights by itself, from the game's boss bar and name, including bosses it has never heard of. An optional 24 MB download reads more names and symbols like Sekiro's death screen. A death screen with no words can be taught once and shared so nobody else has to. An in-game counter (skull and number, a ring, or one huge number), a tray menu, keyboard shortcuts and a controller combo to count without leaving the game, Undo for every count, a share picture and CSV export. Works in any game, with extras for 17 hard ones; never reads game memory. |
| **Network** | Live rates with a 1-minute graph, click-to-copy IPs, speed test, ping, and game-server ping for the game you pick. |

### Hardware

| | |
|---|---|
| **CPU** | Built-in modes (Performance, Balanced, Quiet, Saver, Ultra saver), the same on every PC. Profiles built on real Windows power plans plus extras: P-core / E-core clock caps, PL1/PL2 power limits, a minimum-clock lock with a heat guard, turbo-ratio overclock on unlocked Intel chips. |
| **GPU** (NVIDIA) | Built-in modes made for your card (Fastest, Normal, Quiet, Efficient, which holds the core at the fastest speed it reaches at its lowest voltage, a Saver that also lowers the memory speed for the most frames per watt, and Low power, Lowest power and Minimum below it for lighter games), one click each, with **Measure this card** to find your card's own speeds for all of them. Switching profiles in a game is safe (no driver resets), and the modes fold away with one button or sit behind one "Modes" row in profile lists. Afterburner-style profiles: power and temperature limits, clock offsets or a full voltage/frequency curve editor, core and memory clock locks (to go below the lowest power limit), voltage, fan curve. Imports your Afterburner profiles and hotkeys. A crash guard starts at stock after an unexpected restart. |
| **Fans, Lighting, Cooler display** | Super I/O fan control (Nuvoton, ITE) with curves, fixed speeds and presets; MSI Mystic Light and Kingston Fury RGB, with an animated fan-by-fan preview of each effect; USB LCD coolers. Fans always go back to the BIOS when Deck quits, and a small watchdog gives them back if Deck is ended from Task Manager. |
| **Sensors** | 5-minute graphs for temperature, load, power, fans and frametimes (average, 1% and 0.1% lows); every reading with min / max / average; heat alerts; CSV logging. |
| **Drives** | The health of every HDD and SSD (S.M.A.R.T.): temperature, hours, data written, wear and warning signs, with history and optional alerts. |
| **This PC** | What Deck found in the PC (processor generation, built-in or card graphics, laptop maker) and, in plain words, what it can and can't control there yet, and a support report (copy or save) that answers "what is this machine and what did Deck find" without personal data. |

### Windows

| | |
|---|---|
| **Tweaks** | 132 Windows settings in 13 categories: privacy, Start and search, taskbar, File Explorer, right-click menu, appearance, multitasking, gaming, AI and Copilot, updates, network, system, advanced. From Win11Debloat and Chris Titus Tech's WinUtil, each checked, plus Deck's own. Every switch shows what Windows is set to **right now** ("Partly" when another tool set part of it), what it changes, its risk and whether it needs Explorer restarted, a sign-out or a restart. **Every change can be undone to exactly what it was before**, one by one or all at once, even months later. Deck notices when a Windows update changes a tweak back and offers to apply it again. Presets (Privacy, Clean Start & taskbar, Gaming, Quiet Windows) and "Recommended" open as checklists you can untick, and a restore point is offered before Advanced tweaks. Options that don't exist on this Windows or this PC are hidden. |
| **Apps** | Everything installed, with Windows' own uninstall (then a list of what it left behind, for you to pick from) or an **Advanced** one that also clears the folders, registry settings, shortcuts and services an app leaves behind (backed up first). Also finds apps missing from Windows' list and half-removed ones. Built-in apps (Clipchamp, News, the Xbox apps…) can be removed and reinstalled; Edge and WebView2 are never offered. |
| **Store apps without the Store** | Updates for your Store apps (from Microsoft's servers or through the Store), stoppable and resumable. Like store.rg-adguard.net: search the Store, then **Install**, **Download** the package files, send them to a download manager (FluxDM), or copy the links. Files come straight from Microsoft's own servers, only the ones this PC is missing (usually just the app), checked against Microsoft's checksums, in 8 parts at once with progress, speed and time left; a cancelled download carries on where it stopped. Free apps only; desktop apps from the Store install with winget. |
| **Windows & display** | Window pinning, see-through windows, FancyZones-style snap zones and workspaces; display resolution (with a way back), scale, orientation, refresh rate, brightness, contrast and the monitor's own settings over DDC/CI (sharpness, colour preset, colour gains, volume, input), NVIDIA digital vibrance, HDR, screens off, and a dark/light schedule. |
| **Maintenance** | A WizTree-fast disk space treemap (reads the NTFS file table directly), Clean up (caches, leftovers, Clear RAM), startup apps with Task Manager's own switch, processes with optional safety checks (signer, antivirus engines, Defender, and VirusTotal with your own key; sort by risk), and Tools: colour picker, text from screen (OCR), ruler, locked files, Windows panels. |

### Your other devices

| | |
|---|---|
| **Phone remote** | A web app on your phone (scan a QR code, add it to your home screen): media, volume, profiles, timers, power plans, shared files, and text, links and files sent both ways. At home, or from anywhere through Tailscale (free). Choose who can connect, at home and away. The phone key never travels over the network; each request is signed, and the page also opens over https. |
| **Screen on your phone** | See the PC's screen in the phone remote (H.264 or JPEG, up to 60 fps, adapts to a slow line), with the PC's sound, and optionally control it: taps click and the phone's keyboard types. Off until you turn it on; control pauses while a game is in front unless you allow it on the phone. The phone can also be just a controller, with very little delay (several phones are several players), or a keyboard and mouse of your own design: keys, combos, a trackpad, scrolling, typed text and macros, with layouts per game. |
| **Virtual display** | Optional: a free, signed virtual display driver, so the Screen view and remote desktop work with the monitor unplugged or the lid closed. Off, on by itself while no monitor is connected, or always. |
| **Phone as speaker or mic** | The phone plays the PC's sound (the PC's own speakers can stay quiet meanwhile), or its microphone becomes a mic on the PC that Discord, games and recorders can pick (through VB-CABLE, free; Deck sets it up). Optionally the default mic while the phone talks, and put back after. As a speaker it can keep playing with the phone's screen off, about a third of a second behind over Wi-Fi. |
| **PC to PC** | Send files, folders, installers, apps and your Windows setup (look and feel, and your tweaks, each undoable there) between your PCs running Deck, at home or over Tailscale. Each PC has its own key; installers from another PC always ask on this one. **Share links** send a file or folder to anyone, opened in any browser. |
| **Remote desktop** | See and control the PC from your phone or another computer with RustDesk (free); Deck installs and sets it up. |
| **Workspace Sync** | Keeps workspace sessions, memory, settings and MCP servers the same on your PCs, and can copy project folders and install programs another PC has. Incoming settings that could run something new wait for review. Off until you turn it on. |

Settings has General, Search and About with Updates. Home tiles are in Edit Home, clipboard history preferences are on Clipboard, and shared profile preferences are on CPU and GPU. Phone keeps connection, sharing, screen and audio controls together, with longer setup opening inline.

### Quality of life

- **Opens where you are:** rest the mouse in the top-left corner (off over fullscreen games), click the tray icon, use the Start menu, an optional hotkey, or the phone.
- **Every hardware setting has a ?** that explains what it does, why you'd change it and what to watch out for. Pages hide themselves when the PC has nothing for them.
- **Puts things back:** Gaming, tweaks, PC to PC setups and the phone speaker/mic undo what they changed, and after a crash Deck puts back what it had muted or switched.
- **Never in your way while gaming:** updates, Windows tweaks, app removal and hardware changes wait until no game is in front.
- **Looks after itself:** updates from GitHub (checked against their SHA-256), starts again after a crash or a graphics driver update, and the support report on This PC is one click away.
- **Fits any PC, laptop or handheld:** a low-spec mode for older PCs, touch-friendly controls on touchscreens and handhelds (ROG Ally, Legion Go, MSI Claw, Steam Deck and others), and nothing tied to one brand of board.

<table>
<tr>
<td><img src="docs/screenshots/sensors.png" alt="Sensors graphs: temperature, load, power and frametimes with 1% lows"></td>
<td><img src="docs/screenshots/overlay.png" alt="In-game overlay settings with a live preview"></td>
</tr>
<tr>
<td><img src="docs/screenshots/gpu.png" alt="GPU page with profiles and live clocks"></td>
<td><img src="docs/screenshots/fans.png" alt="Fans page with a draggable fan curve"></td>
</tr>
<tr>
<td><img src="docs/screenshots/tweaks.png" alt="Tweaks: Windows privacy settings, each showing its real state, Partly when another tool set part of it, and Undo"></td>
<td><img src="docs/screenshots/phone.png" alt="Phone page: QR code, send to your phone, screen on your phone, speaker and mic"></td>
</tr>
<tr>
<td><img src="docs/screenshots/boost.png" alt="Gaming page"></td>
<td><img src="docs/screenshots/network.png" alt="Network page with speed test and game-server ping"></td>
</tr>
</table>

## Safe with anti-cheat

Deck uses no input hooks and never injects into games. Keys use `RegisterHotKey`, the hot corner polls the cursor, and window snapping uses WinEvent hooks. The in-game overlay is drawn by RivaTuner, which anti-cheat systems already allow. The controller overlay is an ordinary click-through window; controllers are read through SDL like any game reads them, and its keyboard & mouse mode listens through Windows Raw Input (receive-only, the way games read input themselves), only while that mode is on. The phone mic uses VB-CABLE, an ordinary signed audio driver, so Deck installs no driver of its own and needs no test signing.

## Hardware support

- **Fans:** Nuvoton NCT668x / NCT679x and ITE Super I/O chips (most MSI, ASUS, Gigabyte and ASRock boards), HP laptop fans. Chips that haven't been verified are monitor-only.
- **GPU tuning:** NVIDIA (NVML + NvAPI). AMD and Intel GPUs show sensors only.
- **CPU tuning:** any CPU for power-plan profiles; power limits and the clock lock on Intel; turbo ratios on unlocked Intel CPUs.
- Pages hide themselves when the PC has nothing for them.

> **Use hardware tuning and Advanced tweaks at your own risk.** Overclocking, undervolting and changing fan behaviour can make a PC unstable or run hot, and some Windows tweaks turn off features you may miss. Deck has guards (crash guard, heat guard, fans released to the BIOS on quit, exact undo and a restore point for tweaks) but can't protect against every setting.

## Credits

- Built with [Tauri](https://tauri.app).
- Fan and sensor access through the signed [PawnIO](https://github.com/namazso/PawnIO) driver and [PawnIO.Modules](https://github.com/namazso/PawnIO.Modules).
- Tweak recipes and the built-in app list from [Win11Debloat](https://github.com/Raphire/Win11Debloat) and Chris Titus Tech's [WinUtil](https://github.com/ChrisTitusTech/winutil) (MIT).
- Profile icons from [Fluent UI System Icons](https://github.com/microsoft/fluentui-system-icons).
- In-game overlay drawn by [RivaTuner Statistics Server](https://www.guru3d.com/download/rtss-rivatuner-statistics-server-download/). The phone mic plays through VB-Audio's [VB-CABLE](https://vb-audio.com/Cable/) (not included; Deck opens VB-Audio's own setup). Remote desktop by [RustDesk](https://rustdesk.com), away-from-home by [Tailscale](https://tailscale.com).

See [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) for licences. Deck is not affiliated with MSI, NVIDIA, Guru3D, Microsoft or VB-Audio.

## License

[MIT](LICENSE) © 2026 Mohammad Fakih
