# Troubleshooting

Problems by symptom, with the steps to try and links to the page that explains more. Each page also ends with its own Troubleshooting section for problems specific to it. If nothing here helps, jump to [Getting the log and a support report](#getting-the-log-and-a-support-report).

## Contents

- [A page or setting says "not available", "Needs admin" or is greyed out](#a-page-or-setting-says-not-available-needs-admin-or-is-greyed-out)
- [A page is missing from the sidebar](#a-page-is-missing-from-the-sidebar)
- [The overlay is not showing, or is frozen or doubled](#the-overlay-is-not-showing-or-is-frozen-or-doubled)
- [Fans are not controlled](#fans-are-not-controlled)
- [GPU options are greyed out or missing](#gpu-options-are-greyed-out-or-missing)
- [The phone cannot connect](#the-phone-cannot-connect)
- [The game bar does not open](#the-game-bar-does-not-open)
- [The death counter is not counting](#the-death-counter-is-not-counting)
- [High CPU use or Deck feels heavy](#high-cpu-use-or-deck-feels-heavy)
- [Deck will not start or cannot be opened](#deck-will-not-start-or-cannot-be-opened)
- [After a crash or an unexpected restart](#after-a-crash-or-an-unexpected-restart)
- [Getting the log and a support report](#getting-the-log-and-a-support-report)

## A page or setting says "not available", "Needs admin" or is greyed out

Work out which of three causes you have. [This PC](this-pc.md) answers it in plain words: its "What Deck can do here" table says whether your hardware or Deck is the limit.

1. **Deck is not running with administrator rights.** Signs: the CPU card on Home says **Needs admin**, a hardware page shows a **One-time set up** card or a **Set up** button, drive health says "No drives could be read", Tweaks say "Needs Deck's admin rights". Fix: press **Set up** (one Windows prompt). If you installed with the setup this was done for you; if it keeps coming back, reinstall with the setup. Check on This PC that **Admin rights** shows Deck runs with them. See [Getting started](getting-started.md#the-one-time-set-up).
2. **Your hardware does not offer it.** Examples: GPU profiles need a supported NVIDIA card; Highest speed needs Volta or newer and Memory speed needs Ampere or newer; fan control needs a supported fan chip; lighting needs a supported controller; power limits and the clock lock are Intel features. Choices appear only if the PC has the device. This is not a fault.
3. **Something else is in the way.** A game in front blocks changes to Windows settings, updates, app removal and calibration ("a game is in front": leave the game and try again). Another program (Afterburner, a maker's fan or RGB tool) can be fighting Deck. A "hardware held" toast means Deck found its fan, CPU or GPU settings files edited behind its back; press **Apply them** only if you made the change ([CPU](cpu.md#faq)).

Specific pages: [Tweaks](tweaks.md#troubleshooting), [Gaming](gaming.md#troubleshooting) (greyed-out choices), [Drives](drives.md#troubleshooting), [Fans](fans.md#troubleshooting), [CPU](cpu.md#troubleshooting).

## A page is missing from the sidebar

Hardware pages hide themselves when your PC has nothing Deck can use for them: CPU, GPU, Fans, Lighting, Cooler display and Sensors. Workspace Sync only shows while it is on, unless you tick **Show Workspace Sync** (Settings > General > Sidebar) ([Settings](settings.md#sidebar)). Without admin rights the Fans page shows only **Set up**.

- Open [This PC](this-pc.md) to see what Deck found.
- Pages you hid or reordered yourself: Settings > General > Sidebar > **Reset order** puts the order back.
- The GPU page appears only for an NVIDIA card with Deck's access; AMD and Intel graphics get [Sensors](sensors.md) but no tuning page ([GPU](gpu.md#troubleshooting)).

## The overlay is not showing, or is frozen or doubled

There are three overlay-like things; find yours.

**The in-game overlay (readings, drawn by RivaTuner)** - [Overlay](overlay.md#troubleshooting)
1. Check the strip at the top of the page: the switch is on and RivaTuner is running. Use Deck's own **Open RivaTuner** button, because RivaTuner draws its window properly only when it opens it itself.
2. Play in borderless or windowed mode. Some games (some anti-cheat protected games, some launchers) cannot be hooked by RivaTuner, and then nothing can be drawn there; the overlay's other features still work.
3. Shown twice or frozen: NVIDIA, AMD and Xbox Game Bar overlay windows are kept out of RivaTuner's hooks, but a window that was already open keeps its old copy until it restarts. Restart the game or launcher, or the PC.
4. "No reading" on some lines: that sensor is not provided by the PC right now. FPS and frametime empty: RivaTuner has to be measuring that game.
5. Using Afterburner as well: turn off *Share readings like Afterburner* and use only one overlay.
6. Want RivaTuner back as it was: Behaviour > RivaTuner > **Put RivaTuner's look back**.

**The controller overlay** - [Controller](controller.md#troubleshooting)
Check the main switch, the monitor and that **Hide without a controller** is not hiding it; use borderless or windowed mode (overlays hide in exclusive fullscreen). "Waiting for a controller": connect it by USB or Bluetooth and press a button.

**Flyouts and the death counter on screen** - [Flyouts](flyouts.md#troubleshooting), [Deaths](death-counter.md#troubleshooting)
Exclusive fullscreen hides windows. Use borderless or windowed mode; for flyouts you can set **Over games and fullscreen** to **Overlay text** with the Overlay on.

## Fans are not controlled

Page: [Fans](fans.md#troubleshooting).

1. **No Fans page, or it only shows Set up.** The PC has no fans Deck can see (laptops usually control their own), or Deck lacks admin rights. Press **Set up**, then check [This PC](this-pc.md): "Readable; control not verified" means Deck can read the chip but will not control a fan it is unsure about.
2. **The page is read-only.** A banner gives the reason. Possible reasons: an unverified board (turn on **Allow control on this unverified board** only if you accept the risk), another user's Deck owns the hardware (quit it there), or an anti-cheat client such as FACEIT is open (Deck hands the fans back while it runs; close the client, see [Fans](fans.md#what-happens-with-anti-cheat)).
3. **You changed a mode and nothing happened.** Edits are a draft; press **Apply** in the bar.
4. **A fan is faster than the curve.** A safety rule is active (CPU at 85 C, the source at 90 C or no reading) or a calibration is holding that fan.
5. **Two programs on the same chip.** Close the maker's fan software or any other tool that controls fans; two programs fight.
6. **Fans went to the BIOS by themselves.** That is the safe fallback after a crash, a crash loop, a quit, or a "hardware held" notice. Press **Apply them** if you made the change.
7. **Graphics card fans** are not on the Fans page; they are in the GPU profile ([GPU](gpu.md)).

## GPU options are greyed out or missing

Page: [GPU](gpu.md#troubleshooting).

- **No GPU page:** it appears only for an NVIDIA card. Make sure Deck has admin rights and the NVIDIA driver is installed.
- **Some controls missing in the editor:** the card or driver does not offer them (Highest speed needs Volta or newer, Memory speed needs Ampere or newer, some laptop cards have no power-limit range).
- **"GPU asleep":** the card is powered down, common on laptops with switchable graphics. It wakes when a program uses it.
- **Settings gone after a restart:** GPU settings reset on every restart. Choose a profile under **Apply a profile at start**. An overclocked profile is skipped after an unexpected restart ("Started at stock"); press **Apply anyway** only if you think the restart had another cause.
- **Afterburner and Deck disagree:** Afterburner's startup profile, hotkeys or fan control override Deck. Use **Stop Afterburner from tuning...** or close Afterburner.
- **In Gaming:** GPU profiles and *Target FPS* need an NVIDIA card; Target FPS also needs the game in front, a fresh FPS reading from RivaTuner, admin rights and no other tuning program ([Gaming](gaming.md#troubleshooting)).

## The phone cannot connect

Page: [Phone](phone.md#troubleshooting).

1. **Updated Deck? Update the phone app too.** After Deck 3.7.5 the phone link is encrypted only and every request is signed, so the Android app must be the matching new version; older apps must update. The old browser page stops working until it is reloaded from the PC. Scan the code again (the Phone page has a "Don't have the Android app yet?" section with a code for the newest app).
2. **Set the Windows network to Private.** Deck's firewall rule covers home and work (Private) networks only, not Public ones. If Windows calls your network **Public**, the phone cannot reach the PC: in Windows Settings > Network & internet, open your connection's properties and set the network profile to **Private**. Also avoid guest networks that isolate devices.
3. **The basics.** Both devices on the same network, the PC awake, **Allow phone connection** on, Deck running with admin rights (it adds the firewall rule when it has them). Try **Make a new code**.
4. **The phone warns the page is not secure.** Expected; Deck's certificate is its own. Accept it once. If it asks again, the PC's address changed and Deck made a new certificate.
5. **The QR code does not appear.** The connection is off, or the certificate could not be made; the page says why.
6. **"Connecting to your PC" forever (away from home).** Tailscale must be on and signed in on both devices with the same account.
7. **Screen is black or laggy:** lower the bitrate or size, pick 30 fps; with no monitor attached, install the virtual display. **Taps do nothing:** Screen access must be **View and control**, **Control** on in the phone, and no game in front (**Control in games**). **Phone mic silent:** check "VB-CABLE ready" and that the call app uses **CABLE Output**.

## The game bar does not open

Page: [Game bar](game-bar.md#troubleshooting).

1. Check **Use the game bar** is on and the game runs in borderless or windowed fullscreen, not exclusive fullscreen.
2. Test with **Open it now** with the game in front.
3. Controller combination: it is read only while a game is in front and the controller must be one Deck can read ([Controller](controller.md)). The chosen buttons must exist on your pad (Select and Start are Create and Options on PlayStation controllers); try a longer or shorter **Hold for**.
4. Keyboard shortcut refused: another program owns the combination. Choose a different one.
5. If the game minimises when the bar opens, turn off **Take the keyboard** (and then **Keep clicks off the game**).
6. No controller or keyboard: use the tray menu, the phone, or **Open it now**.

## The death counter is not counting

Page: [Deaths](death-counter.md#troubleshooting).

1. **Death counter** and **Watch for death screens** are on, and the game is in borderless or windowed mode.
2. A game Deck does not know is not watched until you count a death in it (**+1 death**, the tray, or choose **Watch in > Every game**).
3. Read the status line at the bottom of the Now tab: "Game screen unreadable" (Deck sees a black picture; use borderless windowed), "English death screens may be missed" (add English to Windows' languages), "Save not found" (count by hand for now).
4. Wrong or double counts: History > the line's menu > **That wasn't a death**; use **Not a boss** or **Same boss as** for misread names.
5. Not showing in the game: use borderless or windowed, check **Show the counter in games**, and **In every game** if the game is not known.
6. Better boss names: turn on the **OCR pack**. A wordless death screen: teach it once on the Games tab.

Deck does this without reading the game's memory, so it is safe with anti-cheat.

## High CPU use or Deck feels heavy

Deck is light when idle, and features cost something only while they are on. Try, in this order:

1. **Low-spec mode** (Settings > Appearance): no animations, live readings every 3 seconds ([Settings](settings.md#performance-and-units)).
2. Turn off what you do not use: **Watch for death screens** ([Deaths](death-counter.md)) stops the screen watcher entirely; the controller overlay does nothing when off ([Controller](controller.md#faq)); screen and audio streaming on [Phone](phone.md) cost CPU while a phone is connected, so lower the picture size and fps.
3. In [Sensors](sensors.md), turn on **Slow readings during games**, and turn off **Log every sensor to a CSV file** when you are not investigating.
4. [Network](network.md): **Connection quality** and **Data per app** run in the background only if you turned them on.
5. [Overlay](overlay.md): a shorter update interval does a little more work than a longer one.
6. [Processes](processes.md): file safety checks use disk and CPU while they run; press **Stop**.
7. Reduce the folders in **Local file search** ([Settings](settings.md#local-file-search)); the first index build is the heavy part.
8. In the support report, "Background workers" and "Deck memory" show whether something is stuck (see below).

## Deck will not start or cannot be opened

1. **It may already be running.** Deck never runs two copies; starting it again just shows the first. Look for the tray icon (click the up-arrow near the clock). The **X** hides Deck rather than quitting.
2. **Open it from the Start menu.** Hot corner not working: it needs Quick panel mode and an outer corner of the whole desktop ([Home](home.md#troubleshooting)).
3. **It started and left again after crashes.** After three endings within ten minutes Deck stops restarting itself ([Settings](settings.md#start-again-after-a-crash)). Start it from the Start menu; it comes up in a safe state (fans on the BIOS, no overclock).
4. **"Deck couldn't create its scheduled tasks" or admin start is off.** Reinstall with the setup (it installs over the old copy and keeps settings). Set up refuses to create the tasks for a copy in a folder a normal program could change; install to `C:\Program Files\Deck`.
5. **Settings damaged.** A damaged settings file is set aside and recovered, never silently reset. To start over: back up first, quit Deck, then move `%APPDATA%\Deck\settings.json` away. Deck starts with defaults ([Settings](settings.md#troubleshooting)).
6. **A restore did not apply.** A restore applies at the next start; quit Deck from the tray (not just close) and open it again. "Settings need a newer version": update Deck first.
7. **Blocked by SmartScreen when installing:** click **More info**, then **Run anyway** ([Getting started](getting-started.md#installing)).
8. Get a support report if you can open Deck at all (below).

## After a crash or an unexpected restart

What Deck does by itself, and what to check:

- **Fans and GPU fan** are handed back to the BIOS and driver within seconds, even if Deck was killed from Task Manager ([Fans](fans.md#what-happens-if-deck-crashes-or-quits)).
- **Deck starts again hidden** (**Start again after a crash**). It waits for a graphics driver installer to finish first.
- **Overclocks are held back.** After an unexpected PC restart, a CPU overclock or an overclocked GPU profile is not applied ("Started at stock"). Re-apply by hand once you are sure the PC is stable ([CPU](cpu.md#troubleshooting), [GPU](gpu.md#troubleshooting)).
- **Game mode, sound and phone changes** that Deck made (power plan, muted or switched devices, the phone speaker or mic) are put back at the next start; Target FPS limits are restored from a record written before the first change ([Gaming](gaming.md#faq), [Phone](phone.md#faq)).
- **Tweaks:** the before-value is saved before each step, so Undo still works afterwards ([Tweaks](tweaks.md#faq)).
- **Timers and a shutdown plan** only run while Deck runs; a plan set before a restart is dropped ([Power](power.md#troubleshooting)).
- **Hardware held:** if a toast says Deck's hardware settings were edited outside Deck, nothing is applied until you press **Apply them**.
- **Check the reports:** the support report's "Runs" section says how the previous run ended (quit cleanly, closed by an update, or ended without quitting) and "Problems this run" lists the warnings and errors. If Deck keeps crashing, include crash files in the report when you ask for help.

## Getting the log and a support report

### The support report

1. Open [This PC](this-pc.md) and scroll to **Support report** (or Settings > About > **Support report**).
2. **Copy report** puts it on the clipboard to paste into a chat or an issue. **Save report** writes it to a file in Deck's data folder and shows it in Explorer.
3. Tick **Include crash files (may contain private data)** only if asked or if Deck has crashed. Copying adds the crash text to the end with personal details blanked out; saving makes one zip.
4. For lighting problems, answer **Add the test** when Save report offers the 15-second lights test (the lights cycle red, green and blue).

The report holds Deck's version and whether it runs as admin, whether the hardware engine, PawnIO driver and NVIDIA engine run, Windows and PC details, what Deck detected, drive health, how this run and the previous one ended, background workers, problems this run, and the last 80 log lines. It leaves out file paths and drive serial numbers. Read it before posting if you are unsure ([This PC](this-pc.md#support-report)).

### The log file

The log is `%LOCALAPPDATA%\Deck\logs\deck.log` (2 MB per file, four older files kept). Paste that path into the File Explorer address bar. Values after words like token, password and secret are hidden, and your user name and PC name are removed from paths as lines are written. Crash evidence is in `%LOCALAPPDATA%\Deck\crashes`; it is only added to a report if you agree.

### More detail for one problem

Settings > About > **Diagnostics** > **Log levels**: set the one area involved (gpu, hw, cpu, update, backup, remote, worker.supervisor, ui, memory) to **Debug**, reproduce the problem, then take the support report, and set the area back to **Normal** ([Settings](settings.md#diagnostics)).

### Where to ask

Bug reports, ideas and death-screen reports go to the project's public releases repository on GitHub (`deck-releases`). Attach the support report. Security problems should be reported privately, as described in `SECURITY.md` in the repository.

## Related pages

- [FAQ](faq.md)
- [Getting started](getting-started.md)
- [Recommended setups](recommended.md)
