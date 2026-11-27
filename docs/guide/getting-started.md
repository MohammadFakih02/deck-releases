Where to find it: Home › Home

# Getting started

From download to a set-up Deck: installing, why Deck needs administrator, the first run, a 10-minute tour, updates and uninstalling.

## What you need

- Windows 10 or 11, 64-bit.
- Nothing else for the basics. Some features need extras, and their pages say so: an NVIDIA card for [GPU](gpu.md) tuning, [RivaTuner Statistics Server](overlay.md) for the in-game overlay and FPS (Deck can install it), and VB-CABLE for using the phone as a microphone ([Phone](phone.md)).

## Installing

1. Download **`Deck_<version>_x64-setup.exe`** from the latest release on Deck's public releases page (GitHub, `deck-releases`).
2. Run it. The setup isn't code-signed, so Windows SmartScreen may say "Windows protected your PC". Click More info, then Run anyway.
3. Windows asks for administrator permission once. The setup shows one page with one button: **Install**, or **Update** / **Reinstall** when Deck is already there.
4. Deck installs to `C:\Program Files\Deck`, adds a Start menu entry and starts hidden in the tray.

Installing over an existing Deck updates it in place; your settings stay. An older per-user copy is removed, settings kept. The release page lists a SHA-256 checksum for each setup if you want to check a manual download.

## Why Deck needs administrator

Windows only lets administrators talk to hardware: CPU clock, power and temperature, fans and lights, GPU tuning, drive health and most Windows tweaks. Without administrator Deck still runs, and everything else works (launcher, clipboard, sound, pop-ups, network tools and more).

The setup creates Deck's own scheduled task, so Deck starts as administrator at sign-in with no prompt. If Deck runs without it (an old copy, or files copied by hand), pages that need it show **Needs administrator** with a **Restart as administrator** button; Home's CPU card shows an **Admin** chip.

1. Press **Restart as administrator** on any of those pages, the **Admin** chip on Home, or the **Administrator** tile on [This PC](this-pc.md#administrator-access).
2. Windows asks once.
3. Deck creates its startup task and restarts with the rights. The notice doesn't come back.

Good to know:

- Programs Deck opens for you (a game, a browser, an installer) run as your normal account.
- Deck refuses to set up this start for a copy of itself in a folder your normal account can change, so no other program can borrow the rights.
- If another program edits Deck's fan, CPU or GPU settings files, Deck holds them until you approve ([CPU FAQ](cpu.md#faq)).
- **Start with Windows** ([Settings](settings.md#starting-deck)) changes the same task, so it also needs administrator.

## The PawnIO driver

Fan control, motherboard sensors, CPU power limits, board lighting and some temperatures use a small signed driver, PawnIO. Deck installs its own copy when it runs as administrator; you install nothing.

- The anti-cheat client FACEIT refuses to run while this driver is loaded. While FACEIT runs, Deck hands the fans to the BIOS and stops using the driver, then resumes when FACEIT closes. See [Fans](fans.md#what-happens-with-anti-cheat).
- Uninstalling Deck removes the driver if Deck installed it.

## First run

Deck opens on **Home**, with no welcome screen and no questions.

1. A short introduction says how to open Deck again. **Change Deck's look** opens Settings › Appearance; **What Deck found on this PC** lists what your PC supports; **Dismiss introduction** removes it.
2. **First steps** lists a few pages worth a visit. A tick means you've visited it. **Dismiss first steps** removes the list.
3. Home starts with a few tiles; **Edit Home** adds the rest. See [Home](home.md#first-run).
4. The **X** only hides Deck; **Quit Deck** in the tray menu quits it.

Some pages are missing from the sidebar: hardware pages hide when your PC has nothing for them. For a map, read [Find your way around](find-your-way.md).

## Opening Deck

| Way | How |
|---|---|
| Hot corner | Rest the pointer in a screen corner (top left opens Deck by default). Each corner has its own action and delay in Settings › General. |
| Tray icon | Left-click shows or hides Deck; right-click opens the tray menu. If you can't see it, click the up arrow near the clock and drag it onto the taskbar. |
| Keyboard shortcut | None by default. Set one in Settings › General. It works over games too. |
| Start menu | Starts Deck, or shows it if it is already running. |

**Window mode** is **Quick panel** (default: a panel that closes when you click elsewhere) or **App window** (a normal window). See [Home](home.md#opening-and-closing-deck).

## A 10-minute tour

1. **Settings › General**: choose the window mode and, if you like, a shortcut. Keep **Start with Windows** and **Restart after a crash** on.
2. [This PC](this-pc.md): check that the **Administrator** tile says **Can change hardware**, and read what Deck controls on your PC.
3. [Home](home.md): use **Edit Home** to hide tiles and drag the rest.
4. [CPU](cpu.md): try the built-in modes, **Balanced** for every day and **Quiet** for calm. With an NVIDIA card, try **Efficient** on [GPU](gpu.md) and run **Measure this card** once. On a laptop, set what applies plugged in and on battery.
5. [Fans](fans.md) (desktops): set the CPU and case fans to **Balanced**, press **Apply hardware changes** and watch [Sensors](sensors.md) under load. Leave anything you are unsure about on **Motherboard decides**.
6. [Game profiles](gaming.md): leave **Automatic game profiles** on. For FPS, start RivaTuner from [Performance overlay](overlay.md).
7. [Sensors](sensors.md): turn on **Temperature alerts** (90 °C for the CPU, 85 °C for the GPU by default; see [Alerts](alerts.md)).
8. **Settings › Data & recovery**: turn on **Weekly backup** ([Backups](settings.md#backups)).

The "?" next to a setting explains it. [Recommended setups](recommended.md) has checklists by type of user.

## Updates

- With **Update automatically** on (the default), Deck checks once a day and installs when no game or fullscreen program is in front. It never interrupts a game, and starts again hidden afterwards. Settings and profiles stay.
- Every update must carry Deck's signature and match its SHA-256 checksum, or it is thrown away.
- Settings › About also has **Check for updates**, **Previous version** with **Go back**, **Beta releases** and, after an update, **What is new in Deck** with **What moved**.
- Without administrator, press **Install** when Deck offers it; Windows asks once.

More in [Settings › About](settings.md#updates). What changed in each version is in the release notes.

## Uninstalling

1. Open Windows Settings › Apps › Installed apps, find Deck and uninstall it. The uninstaller closes Deck and hands the fans back to the BIOS.
2. To remove your data too, select **Also delete my settings, profiles and death history**. Leave it clear if you may reinstall.
3. The uninstaller removes Deck's scheduled tasks, shortcuts, firewall rules, the PawnIO driver (if Deck installed it) and logs, and restores CPU power plans.

Windows tweaks and sound changes stay as you set them. To get Windows back exactly as it was, undo them first: on [Windows tweaks](tweaks.md), and **Reset all** on [Mixer › Devices](sound.md#devices). Where Deck keeps data: [Settings](settings.md#where-deck-stores-data).
