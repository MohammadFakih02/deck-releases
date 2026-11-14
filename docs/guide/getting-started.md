Where to find it: Home › Home

# Getting started

This page takes you from download to a comfortably set up Deck: installing, why Deck asks for administrator rights, the one-time set up, the first run, the ways to open Deck, a 10-minute tour of what to set first, updates and uninstalling.

## What you need

- Windows 10 or 11, 64-bit.
- Nothing else for the basics. Some features need extras, and each page says so: an NVIDIA graphics card for [GPU](gpu.md) tuning, [RivaTuner Statistics Server](overlay.md) for the in-game overlay and FPS readings (Deck can install it for you), and the free VB-CABLE for using the phone as a microphone ([Phone](phone.md)).

## Installing

1. Download the setup, **`Deck_<version>_x64-setup.exe`**, from the latest release on Deck's public releases page (GitHub, the `deck-releases` repository). Installed copies of Deck look at the same page for updates.
2. Run it. The setup is not code-signed, so Windows SmartScreen may say "Windows protected your PC". Click **More info**, then **Run anyway**.
3. Windows asks for administrator permission once. The setup then shows one short page with one button (**Install**, or **Update** / **Reinstall** when Deck is already there).
4. Deck installs to `C:\Program Files\Deck`, adds a Start menu entry, and starts hidden in the tray.

Good to know:

- Installing over an existing Deck updates it in place. Your settings stay. The setup closes a running Deck itself and hands the fans back to the BIOS while it does.
- An older per-user copy of Deck (in your own user folder) is removed by the setup; your settings are kept.
- The release page lists a SHA-256 checksum for each setup if you want to check a manual download. Deck checks it by itself when it updates.

## Why Deck needs administrator rights

Windows only lets administrators talk to hardware. Reading the CPU's clock, power and temperature, controlling fans and lights, tuning the GPU, reading drive health and changing most Windows tweaks all need it. Without admin rights Deck still runs and the rest works: the launcher, clipboard, sound, flyouts, network tools and more. The pages that need admin say so and offer **Set up**.

How Deck gets those rights without asking every time:

- The setup creates Deck's own scheduled tasks. At sign-in Windows starts Deck through those tasks, with the rights it needs and no prompt.
- Programs Deck opens for you (a game, a browser, an installer) start as your normal account, not as administrator.
- Deck refuses to set up admin start for a copy of itself in a folder your normal account could change, so another program cannot swap in its own code and borrow the rights.
- If another program edits Deck's fan, CPU or GPU settings files behind its back, Deck refuses to act on them until you approve (the "hardware held" safeguard, explained in the [CPU FAQ](cpu.md#faq)).

## The one-time "Set up"

The installer already does the set up, so you normally never see it. If you started Deck some other way (an old copy, or the files copied by hand), hardware pages show a card titled **One-time set up**, and the CPU card on Home says **Needs admin**.

1. Open any hardware page ([CPU](cpu.md), [GPU](gpu.md), [Fans](fans.md), [Lighting](lighting.md), [Drive health](drives.md)), click **Needs admin** on Home's CPU card, or use the card on [This PC](this-pc.md#one-time-set-up).
2. Press **Set up**. Windows shows one administrator prompt.
3. Deck creates its start-up task and restarts itself with those rights. The card does not come back.

The **Start with Windows** switch in [Settings](settings.md#opening-deck) changes that same task, so it also needs admin.

## The PawnIO driver

Fan control, motherboard sensors, CPU power limits, lighting on supported boards and some temperature readings use a small signed driver called **PawnIO**. Deck installs it from its own embedded copy when the hardware engine starts with admin rights; its files live under `C:\ProgramData\Deck\pawnio` and the Windows service is called `DeckPawnIO`. You do not need to install anything yourself.

- One anti-cheat client, FACEIT, refuses to run while this driver is loaded. While FACEIT is running Deck hands the fans back to the BIOS, stops using the driver and shows a notification, then carries on when FACEIT closes. See [Fans](fans.md#what-happens-with-anti-cheat).
- Uninstalling Deck removes the driver if Deck installed it.

## First run

On the first start Deck opens on **Home**. There is no welcome screen and no questions.

1. A short introduction at the top says what Deck is and how to open it again: from the tray icon next to the clock, and from the hot corner or your shortcut if you use them. It has two buttons: **Change Deck's look** (opens **Settings › Appearance**, so choosing a theme is optional) and **What Deck found on this PC** (a list of which feature areas your PC supports). **Dismiss introduction** removes it for good.
2. **First steps** lists four or five pages worth a visit on your PC, such as CPU, Sensors, Performance overlay and Phone. A tick means you have visited the page. **Dismiss first steps** removes the list.
3. Home starts with four main tiles (Sound, Pinned & frequent apps, PC readings and Power & timers). Everything else is still there: **Edit Home** adds it. See [Home](home.md#first-run).
4. Tours never start by themselves. Press the tour button next to the search box on any page to play that page's tour.
5. Deck then lives in the tray. The **X** in Deck's top corner only hides it; use **Quit Deck** in the tray menu to really quit.

For a one-minute map of the sidebar, search and Settings › Features, read [Find your way around](find-your-way.md).

Some pages will be missing from the sidebar. That is normal: hardware pages hide themselves when your PC has nothing for them. [This PC](this-pc.md) shows what Deck found.

## Opening Deck

| Way | How |
|---|---|
| **Hot corner** | Rest the mouse in the top-left corner of the screen (the default). Quick panel mode only. Off over fullscreen games unless you turn that on. |
| **Tray icon** | Left-click opens or closes Deck. Right-click opens the tray menu. If you cannot see the icon, click the small up-arrow near the clock and drag it onto the bar. |
| **Keyboard shortcut** | Empty by default. Choose one in Settings › General > Opening Deck. It works over games too. |
| **Start menu** | Starts Deck, or shows it if it is already running. Deck never runs a second copy. |
| **Phone** | The phone remote drives many of Deck's controls ([Phone](phone.md)). |

There are two window modes: **Quick panel** (default; a panel over a dimmed screen that closes when you click elsewhere) and **App window** (a normal window that stays open). Details, and how the hot corner avoids opening by accident, are in [Home](home.md#opening-and-closing-deck).

## A 10-minute tour: what to set first

1. **Opening Deck (1 minute).** In [Settings](settings.md) › General choose the window mode and, if you like, a keyboard shortcut. Keep **Start with Windows** and **Start again after a crash** on.
2. **See what Deck found (1 minute).** Open [This PC](this-pc.md). Check that **Admin rights** shows Deck runs with them, and read the "What Deck can control here" list so you know what to expect.
3. **Home (1 minute).** Open [Home](home.md). Use Edit Home to hide tiles you do not want and drag the rest where you like.
4. **Profiles (2 minutes).** On [CPU](cpu.md) try the built-in modes: Balanced day to day, Quiet when you want calm. With an NVIDIA card, try **Efficient** on [GPU](gpu.md) and run **Measure this card** once. Laptop users set what applies when plugged in and on battery.
5. **Fans (2 minutes, desktops).** On [Fans](fans.md) put the CPU fan and case fans on **Balanced**, press **Apply hardware changes**, and watch [Sensors](sensors.md) under load for a while. Leave anything you are unsure about on the BIOS.
6. **Gaming (2 minutes).** On [Game profiles](gaming.md) leave *Automatic game profiles* on, and set a frame rate limit just under your monitor's refresh rate for games where you want less heat and noise. If you want FPS readings, start RivaTuner from [Performance overlay](overlay.md).
7. **Heat alerts (30 seconds).** On [Sensors](sensors.md) turn on **Warn me when it gets hot** (defaults 90 C for the CPU, 85 C for the GPU; see [Alerts](alerts.md)).
8. **Backups (30 seconds).** In Settings › Data & recovery turn on **Weekly backup** ([Settings](settings.md#backups)).

After that, explore at your own pace. Press the "?" next to a hardware setting for a plain explanation of what it does and what to watch for. [Recommended setups](recommended.md) has full checklists by type of user.

## Updates

- Deck checks the public releases page once a day and shortly after it starts. With **Update by itself** on (the default) it downloads the setup, checks its SHA-256 checksum and installs silently once **no game or fullscreen program is in front**. It never interrupts a game.
- Your settings and profiles stay. Deck starts again, hidden, after the update.
- Settings › About > Updates also has **Check now**, **Go back to *version*** (when a previous version is available), **Beta releases** (off by default) and **What is new**.
- If Deck is not running as admin, it tells you and installs when you press **Install**, with one Windows prompt.
- A copy of Deck in a folder your own account can change does not update itself.

More in [Settings](settings.md#updates). What changed in each version is in `CHANGELOG.md` in the repository and in the release notes.

## Uninstalling

1. Quit Deck from the tray menu (the uninstaller also closes it for you and hands the fans back to the BIOS).
2. Open Windows Settings > Apps > Installed apps, find **Deck**, and uninstall it. The uninstaller has a tick box to delete your settings, profiles and death history too. Leave it unticked if you may reinstall.
3. The uninstaller removes Deck's scheduled tasks, shortcuts, firewall rules, the PawnIO driver (if Deck installed it), logs and browser data, and puts back CPU power plans and the minimum-clock lock.
4. To remove your settings later, delete the Deck folders under `%APPDATA%` and `%LOCALAPPDATA%` (listed in [Settings](settings.md#where-deck-stores-data)).

Windows tweaks and sound changes stay as you set them. If you want Windows back exactly as it was, undo them first: tweaks one by one or all at once on the [Windows tweaks](tweaks.md) page, and **Undo sound changes** on [Sound & mic](sound.md).

If you installed from source with `install.ps1`, `uninstall.ps1` removes it; add `-Purge` to delete settings too.

## Where to go next

- [Recommended setups](recommended.md) for your kind of PC.
- [FAQ](faq.md) for safety and what Deck changes.
- [Troubleshooting](troubleshooting.md) if something does not appear or does not work.
