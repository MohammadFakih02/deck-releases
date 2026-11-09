# Frequently asked questions

Short answers to the questions people ask most, each with a link to the page that has the detail. For problems ("X does not work") see [Troubleshooting](troubleshooting.md).

## Contents

- [Safety and anti-cheat](#safety-and-anti-cheat)
- [What Deck changes on your PC and how to undo it](#what-deck-changes-on-your-pc-and-how-to-undo-it)
- [Administrator rights](#administrator-rights)
- [What leaves your PC](#what-leaves-your-pc)
- [Hardware: AMD, Intel, laptops](#hardware-amd-intel-laptops)
- [Performance cost](#performance-cost)
- [Crashes and quitting](#crashes-and-quitting)
- [Backups and moving to a new PC](#backups-and-moving-to-a-new-pc)
- [Updates and uninstalling](#updates-and-uninstalling)
- [Features](#features)

## Safety and anti-cheat

**Will Deck get me banned?**
Deck never injects code into a game, never reads a game's memory and installs no hooks into games. Its features use ordinary Windows calls (power plans, window positions, volume), read your keys and controller passively, or are drawn by a tool anti-cheat systems already accept (RivaTuner draws the overlay). Each page has an anti-cheat answer: [Gaming](gaming.md#faq), [Overlay](overlay.md#faq), [Game bar](game-bar.md#faq), [Controller](controller.md#faq), [Deaths](death-counter.md#faq), [Flyouts](flyouts.md#faq), [Sensors](sensors.md#faq), [Home](home.md#faq) (the hot corner).

**Is there any exception?**
Yes, one known: the FACEIT anti-cheat client refuses to run while Deck's hardware driver (PawnIO) is loaded. While FACEIT runs, Deck hands the fans back to the BIOS, stops using the driver and shows a notification saying why; it carries on when FACEIT closes. Features that need the driver (fan control, CPU temperature, board lighting) pause meanwhile. See [Fans](fans.md#what-happens-with-anti-cheat).

**Is it safe to leave Deck running all the time?**
Yes. It sits in the tray, and a small helper hands the fans and the graphics card back to the BIOS and driver if Deck is ended from outside ([Settings FAQ](settings.md#faq)).

**Can hardware tuning damage my PC?**
Deck stays inside what your hardware and driver allow, and has guards: the heat guard gives fans 100 % when the CPU is at 85 C, a GPU fan 100 % above 85 C or with no reading, a crash guard starts the GPU and CPU at stock after an unexpected restart, and an overclock is only offered on CPUs Deck detects as unlocked. But overclocking, undervolting and changing fan behaviour can make a PC unstable or hot, as in any tool. Read [CPU](cpu.md#faq), [GPU](gpu.md#faq) and [Fans](fans.md#faq) before changing things.

**Can Tweaks break Windows?**
Safe and most Behaviour tweaks are easy to reverse. Advanced ones can reduce protection or stability, so they ask for a restore point and a review. Undo restores settings, not deleted data. There is no switch for Defender or for Windows Update itself. See [Tweaks](tweaks.md#faq).

**Is the phone remote safe?**
Every request is signed with a key that never leaves your devices, each signed request works only once and the connection is encrypted. Anyone who scans your code can control what you allowed, so treat the code like a password and use **Make a new code** after sharing it. Deck does not open your router to the internet; away from home it uses Tailscale. See [Phone](phone.md#faq).

## What Deck changes on your PC and how to undo it

Deck only changes what you ask for, and records old values so it can put them back. The usual answers:

| Area | What changes | How to undo |
|---|---|---|
| Fans | Fan speeds in the motherboard chip while Deck runs (never the BIOS settings). | Set fans to **BIOS** and **Apply**, or quit Deck ([Fans](fans.md#faq)). |
| GPU | Power limit, offsets, curve, clock locks, fan. | **Back to stock**, or restart the PC. Clock locks are let go when Deck quits ([GPU](gpu.md#faq)). |
| CPU | A Windows power plan plus Deck's own caps, floor and limits. | Switch profile; the clock floor is let go when Deck quits; a turbo overclock stays until the PC restarts ([CPU](cpu.md#faq)). |
| Windows settings | Registry and system settings you choose on Tweaks. | Undo one by one or all at once, even months later ([Tweaks](tweaks.md)). |
| Sound | Default devices, volumes, per-app outputs, microphone settings. | **Undo sound changes** ([Sound and mic](sound.md#faq)). |
| Display | Resolution, brightness, colour. | Resolution changes come with a way back; brightness and colour go back exactly when Deck quits or after a crash ([Display](display.md)). |
| Windows, Flyouts | Window positions, on-top flag and opacity of windows you choose; optionally hides Windows' own volume pop-up. | Turn the setting off ([Windows](windows.md#faq), [Flyouts](flyouts.md#faq)). |
| Game mode | Power plan, priorities, closed background apps, per-game PC settings. | Deck puts them back when the game closes, and after a crash at the next start ([Gaming](gaming.md#faq)). |
| Uninstalled apps | Removed programs and their leftovers. | Files go to the Recycle Bin; registry keys and services are backed up first ([Apps](apps.md#faq)). |
| Firewall | One rule for the phone port (home and work networks, not public). | Removed when you uninstall Deck ([Phone](phone.md#faq)). |
| RivaTuner | Deck writes its look and the global frame limit into RivaTuner's profiles. | **Put RivaTuner's look back** ([Overlay](overlay.md#faq)). |

Full details of what Deck stores and where: [Settings > Where Deck stores data](settings.md#where-deck-stores-data).

**Does Deck change my BIOS?**
No. For fans it writes the fan chip's live registers (and saves the originals first), never BIOS settings ([Fans](fans.md#faq)).

**Does Deck turn off Windows Defender or Windows Update?**
No ([Tweaks](tweaks.md#faq)).

## Administrator rights

**Does Deck need admin?**
For fans, CPU and GPU tuning, CPU temperature, drive health, lighting, most Windows tweaks and silent updates, yes. Deck runs as admin through its own scheduled tasks created by the setup, so there is no prompt at each start. Without admin the rest works. Programs Deck launches start as your normal user. See [Getting started](getting-started.md#why-deck-needs-administrator-rights) and [Settings](settings.md#faq).

**I see "Needs admin" or a Set up button. What do I do?**
Press **Set up**: one admin prompt, and from then on Deck starts with those rights. See [Getting started](getting-started.md#the-one-time-set-up) and [This PC](this-pc.md#one-time-set-up).

**Can another program borrow Deck's admin rights?**
Deck is built so it cannot: it will not set up admin start for a copy in a folder a normal program could change, runs the programs it opens as you, and refuses to act on hardware settings files that were edited behind its back (the "hardware held" safeguard, you press **Apply them** if the change was yours). See [CPU](cpu.md#faq).

## What leaves your PC

**Does Deck collect data about me?**
No. It does not need an account and does not upload your settings, logs, crash files or clipboard on its own. The full list of features that contact the internet, and why, is in [Settings > Privacy](settings.md#privacy-what-leaves-your-pc).

**Which features use the internet?**
Update checks (GitHub), game artwork (Steam, GOG, PCGamingWiki, Wikipedia), currency rates in search, the speed test and lag check (Cloudflare), the sunset schedule (an IP-location lookup), VirusTotal (only with your own key), Microsoft's servers for Store apps, and ntfy or Discord if you set up Notifications out. Phone, PC to PC and Workspace Sync talk to your own devices, and are off until you turn them on.

**Do the support report and logs contain personal data?**
No. File paths are shortened, drive serial numbers are left out, and the log hides values after words like token, password and secret, and your user name and PC name. Crash files are only added if you agree. See [This PC](this-pc.md#support-report) and [Settings](settings.md#where-deck-stores-data).

**Can I use Deck without the internet?**
Yes. Updates, artwork, currency rates and the speed test need it; everything else is local.

## Hardware: AMD, Intel, laptops

**Does Deck work on AMD processors?**
Yes. CPU profiles built on Windows power plans work on any CPU. On AMD the power-limit choices only set Windows' power mode, and AMD reports one package temperature rather than one per core. Power limits and the clock lock are Intel features; turbo ratios are for unlocked Intel CPUs ([CPU](cpu.md)).

**Does Deck work with AMD or Intel graphics?**
Yes for sensors, the overlay (through RivaTuner), closing apps, priority, display, fan and sound changes, and session reports. GPU tuning and Target FPS need an NVIDIA card; the driver-kept frame cap is NVIDIA only, and on other cards the cap is kept in RivaTuner. [This PC](this-pc.md) shows "Partly" for AMD and Intel graphics ([GPU](gpu.md), [Gaming](gaming.md#faq)).

**Does it work on laptops and handhelds?**
Yes, with limits. Laptops usually control their own fans; Deck drives HP laptop fans, and everything else is monitor-only or left to the maker. CPU profiles for plugged in and on battery, flyouts for charger and brightness, and touch-friendly controls on handhelds work. [This PC](this-pc.md) lists "Partly" and "Not yet" honestly, and the support report you save there is what helps add support for a laptop. See [Recommended setups](recommended.md#laptop-on-battery).

**Why is a page missing from the sidebar?**
Hardware pages hide themselves when your PC has nothing Deck can use for them (no controllable fans, no NVIDIA card, no lighting). Check [This PC](this-pc.md). Without admin rights, the Fans page shows only **Set up** ([Fans](fans.md#troubleshooting)).

**Which fan chips and boards are supported?**
Nuvoton NCT668x / NCT679x and ITE Super I/O chips (most MSI, ASUS, Gigabyte and ASRock boards) and HP laptop fans. Chips that have not been verified are monitor-only until you allow control. See [Fans](fans.md) and [This PC](this-pc.md#hardware-and-access).

**Can I use Deck with MSI Afterburner or my motherboard's fan software?**
Not at the same time for the same job. Two programs writing the same fan chip or the same GPU settings fight. Deck imports Afterburner profiles and can stop Afterburner from tuning; for fans, let Deck or the maker's software own them ([GPU](gpu.md#faq), [Fans](fans.md#faq)). Deck does not need Afterburner; RivaTuner Statistics Server is enough for the overlay ([Overlay](overlay.md#faq)).

## Performance cost

**Does Deck slow down my games?**
Very little. Sensor readings are taken once a second (every three seconds for the heavier ones while a game is in front), the controller overlay redraws only while visible, flyouts over a game are drawn without the web engine, the death counter looks at a small picture a few times a second, and alert rules are checked once a second against readings Deck already has. Updates, tweaks, app removal and hardware changes wait until no game is in front. See [Sensors](sensors.md#faq), [Controller](controller.md#faq), [Deaths](death-counter.md#faq), [Alerts](alerts.md#faq).

**Can I make Deck even lighter?**
Turn on **Low-spec mode** in [Settings](settings.md#performance-and-units) (no animations, readings every 3 seconds), turn off features you do not use (each has its own switch), and reduce the folders in Local file search.

## Crashes and quitting

**What happens if Deck crashes or I end it in Task Manager?**
A small helper hands the fans and the GPU fan back to the BIOS and driver within seconds, then Deck starts again hidden (**Start again after a crash**, on by default). After three endings within ten minutes Deck stops restarting itself and the next start is safe: fans on BIOS control and no overclock. See [Settings](settings.md#start-again-after-a-crash) and [Fans](fans.md#faq).

**What happens if the PC crashes in the middle of a game?**
At the next start Deck puts back the power plan, profiles and other settings it had changed, and the crash guard starts an overclocked CPU or GPU profile at stock. You choose when to apply it again ([Gaming](gaming.md#faq), [CPU](cpu.md#troubleshooting), [GPU](gpu.md#troubleshooting)).

**What does quitting Deck do?**
It stops the hot corner, clipboard history, timers, shutdown plans, keep awake, the phone link and any Game mode session; fans go back to the BIOS and the GPU fan back to the driver. A set shutdown plan carries on when Deck starts again in the same Windows session. See [Home](home.md#what-quitting-does).

## Backups and moving to a new PC

**How do I back up Deck?**
Settings > Data & recovery > **Back up Deck to a file**, or turn on **Weekly backup**. A backup holds settings and profiles, fan and hardware settings, curves, clipboard history and the death counter's data and taught screens. It does not hold alert rules, the shutdown plan, game artwork, logs or tweak undo records ([Settings](settings.md#backups)).

**How do I move to a new PC?**
Install Deck there, then restore a manual backup made with **Include secrets** and a password (at least 12 characters) if you want the phone key to come along. After a restore the phone remote, PC to PC, Workspace Sync, automatic Game mode, automatic updates and weekly backups are switched off on purpose; turn them back on. To bring your Windows look and tweaks, use [PC to PC](pc-to-pc.md) or save your tweaks to a file ([Tweaks](tweaks.md)).

**How do I export my death counts?**
Deaths > Games tab > **Export** or **Export everything** (CSV) ([Deaths](death-counter.md#faq)).

## Updates and uninstalling

**How does Deck update?**
It checks the public releases page daily and installs silently when no game or fullscreen program is in front, after checking the SHA-256 checksum. Your settings stay. Turn off **Update by itself** to check manually only, and use **Go back to *version*** if a version is offered. See [Settings](settings.md#updates) and [Getting started](getting-started.md#updates).

**How do I uninstall Deck?**
Windows Settings > Apps > Installed apps > Deck. A tick box also deletes your settings. It removes Deck's tasks, shortcuts, firewall rule, the PawnIO driver (if Deck installed it) and puts back CPU power plans. Undo tweaks and sound changes first if you want Windows exactly as before. See [Getting started](getting-started.md#uninstalling).

## Features

**Does Deck replace MSI Afterburner, my motherboard's fan software and debloat scripts?**
It can replace their jobs: GPU profiles with Afterburner import ([GPU](gpu.md)), fan control ([Fans](fans.md)), Windows tweaks with an exact undo ([Tweaks](tweaks.md)). It still uses RivaTuner Statistics Server for the in-game overlay and FPS ([Overlay](overlay.md)).

**Does the death counter work in every game?**
Yes, once you count a death there. Built-in games count automatically; others are watched after your first manual count. Screens in Spanish, French, German, Italian, Portuguese and Polish are read without setup, and wordless screens can be taught once ([Deaths](death-counter.md#faq)).

**Does it replace Win+V for the clipboard?**
No; both work side by side ([Clipboard](clipboard.md#faq)).

**Can I get alerts on my phone?**
Yes, through ntfy or a Discord webhook. Email and SMS are only possible if you set them up on the ntfy side ([Alerts](alerts.md#faq)).

**Can the phone work away from home?**
Yes, through Tailscale (free); Deck does not open your router. See [Phone](phone.md#faq).

**Is anything sent to Deck's author?**
No. Deck needs no account and does not upload your settings or logs. Notifications out goes only to the ntfy or Discord address you typed ([Alerts](alerts.md#faq), [Settings](settings.md#privacy-what-leaves-your-pc)).
