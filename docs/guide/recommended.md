# Recommended setups

Deck has a lot of settings, and most people need only a handful. This page gives a short checklist for each kind of user. Every item links to the page that explains it, and nothing here goes beyond what those pages describe. Tick items off in order; skip anything your hardware does not have (the page for it will not be in your sidebar).

**For everyone, first:**

- [ ] Open [This PC](this-pc.md) and check that **Admin rights** shows Deck runs with them (see [Getting started](getting-started.md#why-deck-needs-administrator-rights)).
- [ ] In [Settings](settings.md) keep **Start with Windows**, **Start again after a crash** and **Update by itself** on, and turn on **Weekly backup** ([Backups](settings.md#backups)).
- [ ] Turn on **Warn me when it gets hot** on [Sensors](sensors.md) (defaults 90 C CPU, 85 C GPU; see [Alerts](alerts.md)).
- [ ] Make the restore point when [Tweaks](tweaks.md) offers one.

## Gamer on a desktop

Goal: smooth frames, a cool and reasonably quiet PC, nothing that gets in the way of a match.

**Opening Deck**
- [ ] Keep Quick panel and the top-left hot corner, and leave **Works over fullscreen games and videos** off. Set a keyboard shortcut so you can open Deck over a game ([Home](home.md#opening-and-closing-deck), [Settings](settings.md#opening-deck)).

**Gaming**
- [ ] Leave *Automatic game profiles* on and everything else at its default ([Gaming](gaming.md)).
- [ ] Set a frame rate limit just under your monitor's refresh rate for the games where you want less heat and noise.
- [ ] Competitive players: set *Game priority* to High on the default profile, pause Deck's downloads, and tick the sync, torrent and updater apps on *Apps to close*. Turn *Close apps* on only for the games where you want it.
- [ ] Skip *Target FPS* for competitive games. Elsewhere it needs an NVIDIA card, admin rights and RivaTuner measuring.

**Tune**
- [ ] [CPU](cpu.md): Balanced day to day; or a profile with a P-core cap a little under top turbo and **Hold the cap in games** on, then confirm with **In-game clock check**. Leave the overclock off unless you know your CPU and cooling.
- [ ] [GPU](gpu.md) (NVIDIA): apply **Efficient** or **Saver** for everyday gaming and run **Measure this card** once. Use **Normal** for the card as sold. In [Gaming](gaming.md) pick a GPU profile per game.
- [ ] [Fans](fans.md): **Performance** for case fans with the source **CPU/GPU hotter**, or a **mix** of Silent and Performance for quiet at the desktop and quick reaction in games. Press **Apply**, then watch [Sensors](sensors.md) under load. Keep the top of every curve at 100 %.

**Overlay and in-game tools**
- [ ] [Overlay](overlay.md): turn it on (Deck installs RivaTuner if needed) and start from *Compact row*, or use *FPS and lows* if you care about stutter. To only keep FPS for session reports, leave RivaTuner running (*Start RivaTuner with Deck*) and the overlay off.
- [ ] Use borderless or windowed mode in games so the overlay, [Game bar](game-bar.md), [Controller](controller.md) overlay and [Flyouts](flyouts.md) can draw. Exclusive fullscreen hides them.
- [ ] [Game bar](game-bar.md): controller players keep **Select + Start** held for 600 ms with **Take the keyboard** off; keyboard players choose a shortcut the game does not use and test with **Open it now** before a match.
- [ ] [Deaths](death-counter.md), if you play hard games: start in borderless or windowed mode, set a **+1 death shortcut** and an **Undo shortcut** you will not press by accident.

**Windows**
- [ ] [Tweaks](tweaks.md): the **Gaming** preset. Specifically Game recording off, Mouse acceleration off and Sticky/Filter Keys shortcuts off. Leave Hardware GPU scheduling, Fullscreen optimisations and Memory integrity at their defaults unless a game needs otherwise.
- [ ] [Clean up](cleanup.md): leave shader caches unticked unless a driver update left you with stuttering or the drive is short on space.
- [ ] [Network](network.md): run **Lag while busy** once. If it grades C or worse, enabling SQM on your router (or pausing big downloads while you play) helps more than any PC setting.
- [ ] [Alerts](alerts.md): keep alerts to notifications. Rules that switch profiles in the middle of a game can change performance unexpectedly.

## Laptop on battery

Goal: long battery life, a cool lap, no surprises when you unplug.

- [ ] [CPU](cpu.md): set **When plugged in** to Balanced or Performance and **On battery** to Saver (or Ultra saver for the longest battery). Leave **Profiles also apply on battery** on.
- [ ] [GPU](gpu.md) (NVIDIA cards): use the modes that lower power; power limits may be locked by the laptop, but **Highest speed** and **Memory speed** still work where the card allows. A "GPU asleep" message on switchable graphics is normal.
- [ ] [Gaming](gaming.md): a frame limit per game, *Target FPS* if you have an NVIDIA card, and a quiet fan preset in *PC settings*.
- [ ] [Fans](fans.md): leave laptop fans on the BIOS unless you need manual control. On HP laptops Deck can drive the two fans, but never asks for less than about 1,800 RPM while a manual speed is set.
- [ ] [Power](power.md): use **Keep awake** for a duration instead of "until I turn it off" so you do not forget and drain the battery. Prefer Sleep to Shut down when you want to come back to your work.
- [ ] [Flyouts](flyouts.md): turn on **Charger** and **Brightness**.
- [ ] [Settings](settings.md): App window mode suits a small screen; on Home the Performance tile switches CPU profiles quickly when you unplug ([Home](home.md#the-home-tiles)).
- [ ] [Tweaks](tweaks.md): leave *Network while asleep* and *Modern Standby* alone unless you know you need them; they affect battery life and wake behaviour.
- [ ] [Alerts](alerts.md): a rule such as "CPU temperature is above 90 for 30 s" that switches to a lower-power CPU profile can protect a thin laptop in a hot room.
- [ ] [Drives](drives.md): with a single NVMe drive the Drives page is your only warning before data loss; keep a backup anyway.
- [ ] [Sound and mic](sound.md): if you dock often, a "dock connects" rule saves opening Windows Sound settings.
- [ ] Handhelds and touchscreens: use [Game bar](game-bar.md) with 1 column, a larger text size and the controller combination.
- [ ] Open [This PC](this-pc.md) and expect "Partly" and "Not yet" on the maker's own controls. That is honest information, not a fault.

## Quiet PC or work PC

Goal: a calm PC that stays out of your way, and a clean, private Windows.

**Quiet**
- [ ] [CPU](cpu.md): pick **Quiet**, or build a profile with turbo on, a modest sustained power limit (Intel: Custom PL1) and an energy preference around 60.
- [ ] [Fans](fans.md): **Silent**, **Ignore short spikes** on, and consider **Quiet hours** at night. Keep the top of the curve at 100 %. Use **Calibrate** to find where a fan stops and starts. Water cooling: give the pump **Fixed 100 %** or leave it on the BIOS.
- [ ] [GPU](gpu.md): **Quiet**, or a fan curve that stays low at idle temperatures.
- [ ] [Lighting](lighting.md): lower **Brightness**, or use **Off**; **Lights off** in the tray is one click. Set **Dim at night** on the cooler display.
- [ ] [Alerts](alerts.md): use a rule on a fan's RPM, not only on temperature, so a stopped fan is caught before the PC heats up.
- [ ] [Power](power.md): keep the shutdown-plan warning at 60 seconds or more; it is your only chance to cancel. Leave **Close apps that hold it up** off unless everything is saved.

**Windows hygiene**
- [ ] [Tweaks](tweaks.md): start with the **Recommended** panel and untick anything you want to keep, then the **Privacy**, **Quiet Windows** and **Clean Start & taskbar** presets. Leave **Advanced** alone unless you know why you need it. Save your tweaks to a file so you can reapply them after a reinstall.
- [ ] Managed work PCs: group policy may override tweaks. If a tweak keeps going back, your organisation is probably resetting it.
- [ ] [Startup apps](startup.md): switch off what you do not need at sign-in, restart, then press **Analyze** in the Startup optimizer. PCs that start from a hard drive benefit most.
- [ ] [Clean up](cleanup.md): leave the default selection, review, and clean every month or two. Laptops and small SSDs: also tick **Old installers in Downloads**.
- [ ] [Apps](apps.md): uninstall with **Uninstall** first; use **Advanced** only when it fails. Start the built-in apps list with *Safe to remove*.
- [ ] [Clipboard](clipboard.md): leave history on, turn on **Wipe codes and keys after a minute** and add snippets for repeated text.

**Privacy-minded**
- [ ] [Settings](settings.md#privacy-what-leaves-your-pc): turn off **Update by itself** and check manually, leave Notifications out and VirusTotal off, and use **Clear artwork** if you like. Deck works without all of them.

## Streamer or content creator

Goal: a death counter and overlays that look right on stream, and nothing private on screen.

- [ ] [Deaths](death-counter.md): set an output folder for the OBS text files and keep **Show in screenshots and recordings** on. Hiding it can make NVIDIA Instant Replay switch itself off. If you prefer a quieter screen, leave **Red edges** off or shorten the card's seconds.
- [ ] [Deaths](death-counter.md): keep **Read save files**, **Watch for death screens**, **Find boss fights by themselves** and the **Shared death-screen library** on; teach a wordless death screen once on the Games tab.
- [ ] [Controller](controller.md): choose whether the controller overlay appears in recordings with **Hide from screenshots and recordings**, and use borderless or windowed mode.
- [ ] [Lighting](lighting.md): use a profile colour per CPU or GPU profile so the lights show which mode the PC is in, and **Flash red on a death** with the death counter. Let Deck own the Mystic Light board and RAM, and use OpenRGB for the rest.
- [ ] [Overlay](overlay.md): the *Gaming* preset with the frametime graph is useful while you test; switch it off when you do not need it on screen.
- [ ] [Flyouts](flyouts.md): turn on **Microphone** so you notice a mute change; set **Over games and fullscreen** to **Nothing** if you never want interruptions on stream.
- [ ] [Sound and mic](sound.md): set the game to your headset and chat or music to your speakers under **App outputs**, save it as an output profile, and run **Check mic for 5 seconds** once.
- [ ] [Clipboard](clipboard.md): turn on **Wipe codes and keys after a minute** so a copied key does not sit in the history.
- [ ] [Phone](phone.md): a phone as a microphone needs VB-CABLE and **Make it the default mic while the phone talks**. Treat the pairing code like a password and use **Make a new code** after sharing it.
- [ ] [Alerts](alerts.md): set up **ntfy** or a **Discord webhook** so a heat warning or a crash reaches your phone while you are live.

## Someone who just wants monitoring

Goal: see what the PC is doing, get warned early, change nothing.

- [ ] Open [Sensors](sensors.md) > **All readings** and click through the devices; use **Find a reading...** to jump to what you care about. Check **Graphs** for a week of history.
- [ ] Turn on **Warn me when it gets hot**, and lower the defaults a few degrees if your PC runs cool. On a PC you leave running, add **ntfy** or a **Discord webhook** ([Alerts](alerts.md)).
- [ ] Gamers: use the **Frametimes** graph with RivaTuner running to see stutter the FPS average hides ([Sensors](sensors.md), [Overlay](overlay.md)).
- [ ] [Drives](drives.md): turn on **Drive health** warnings (Settings › Notifications) and enter the TBW from your SSD's datasheet if Deck did not know it.
- [ ] [Processes](processes.md): leave the defaults; run **Signatures** and **Defender** once after installing a lot of new software.
- [ ] [Network](network.md): use the page when something feels wrong; turn on **Data per app** only if you need it.
- [ ] Use [This PC](this-pc.md) to see what Deck found and its weekly health summary.
- [ ] Do not set up fan, CPU or GPU profiles, and leave [Tweaks](tweaks.md) alone. Monitoring pages only read; they write nothing to your hardware ([Sensors FAQ](sensors.md#faq)).
- [ ] Turn on **Log every sensor to a CSV file** only while investigating something, then turn it off.

## More help

- [FAQ](faq.md) for safety and what Deck changes.
- [Troubleshooting](troubleshooting.md) if something does not appear or work.
