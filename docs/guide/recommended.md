Where to find it: Home › Home

# Recommended setups

Short checklists for each kind of user. Each item links to the page that explains it; skip anything your PC doesn't have.

## For everyone, first

- [ ] On [This PC](this-pc.md#administrator-access), check that **Administrator** says **Can change hardware** ([why](getting-started.md#why-deck-needs-administrator)).
- [ ] In [Settings](settings.md), keep **Start with Windows**, **Restart after a crash** and **Update automatically** on, and turn on **Weekly backup** ([Backups](settings.md#backups)).
- [ ] Turn on **Temperature alerts** on [Sensors](sensors.md) ([Alerts](alerts.md)).
- [ ] Make the restore point when [Windows tweaks](tweaks.md) offers one.

## Gamer on a desktop

Goal: smooth frames, a cool PC, nothing in the way of a match.

- [ ] Set a keyboard shortcut to open Deck over games ([Settings](settings.md#opening-deck)).
- [ ] [Game profiles](gaming.md): leave the defaults on, and set a frame rate limit just under your monitor's refresh rate where you want less heat.
- [ ] Competitive players: **Game priority** › **Game first**, **Pause Deck's downloads**, and select sync, torrent and updater apps on **Apps to close**. Skip **Target FPS** in competitive games.
- [ ] [CPU](cpu.md): **Balanced** day to day. Leave the overclock off unless you know your CPU and cooling.
- [ ] [GPU](gpu.md) (NVIDIA): **Efficient** or **Saver** for everyday games, and run **Measure this card** once.
- [ ] [Fans](fans.md#recommended-setups): **Balanced** following **CPU/GPU hotter**, then **Apply hardware changes** and watch [Sensors](sensors.md) under load.
- [ ] [Performance overlay](overlay.md): start from **Essentials** or **One line**. Play in borderless or windowed mode so the overlay, [Deck bar](game-bar.md) and pop-ups can draw.
- [ ] [Windows tweaks](tweaks.md): review the **Gaming** preset. It turns off **Game recording (Xbox Game DVR)**, **Enhance pointer precision (mouse acceleration)** and the **Sticky Keys shortcut**. Leave **GPU scheduling**, **Fullscreen optimizations** and **Memory integrity** at their defaults unless a game needs otherwise.
- [ ] [Network](network.md): run **Lag while busy** once. A poor grade is fixed on the router, not the PC.

## Laptop on battery

Goal: long battery life and no surprises when you unplug.

- [ ] [CPU](cpu.md): **When plugged in** on **Balanced** or **Performance**, **On battery** on **Saver** or **Low power**.
- [ ] [GPU](gpu.md) (NVIDIA): a low-power mode. "GPU asleep" on switchable graphics is normal.
- [ ] [Game profiles](gaming.md): a frame rate limit per game.
- [ ] [Fans](fans.md): leave laptop fans on **Motherboard decides** unless you need manual control.
- [ ] [Power](power.md): use **Keep awake** for a set time, not until you turn it off.
- [ ] [Music & volume pop-ups](flyouts.md): turn on **Charger** and **Brightness**.
- [ ] [Power use](power-use.md): see which apps use the battery.
- [ ] Settings: **App window** suits a small screen ([Home](home.md#opening-and-closing-deck)).

## Quiet PC or work PC

Goal: a calm PC and a clean, private Windows.

- [ ] [CPU](cpu.md) and [GPU](gpu.md): **Quiet**.
- [ ] [Fans](fans.md#recommended-setups): **Silent**, **Ignore short spikes** and **Quiet at night**; keep the top of each curve at 100 %.
- [ ] [Lighting](lighting.md): lower **Brightness**, or **Lights off** in the tray.
- [ ] [Alerts](alerts.md): add a **Fan stopped** alert, so a stopped fan is caught early.
- [ ] [Power](power.md): keep the shutdown warning at 60 seconds or more, and leave **Force-close apps that block it** off.
- [ ] [Windows tweaks](tweaks.md): start with **Recommended safe changes**, then the **Privacy**, **Quiet Windows** and **Clean Start & taskbar** presets. Leave Advanced alone. On a managed work PC, group policy may undo tweaks.
- [ ] [Startup apps](startup.md): **Disable** what you don't need at sign-in, restart, then check the Startup optimizer.
- [ ] [Clean up](cleanup.md): keep the default selection and clean every month or two.
- [ ] [Clipboard](clipboard.md): turn on **Wipe codes and keys after a minute**.
- [ ] Privacy-minded: see [what leaves your PC](settings.md#privacy-what-leaves-your-pc). Deck works with all of it off.

## Streamer or content creator

Goal: overlays that look right on stream and nothing private on screen.

- [ ] [Death counter](death-counter.md#obs-text-files): set a folder for the OBS text files.
- [ ] [Controller](controller.md): choose whether the overlay shows in recordings (**Hide from captures**).
- [ ] [Lighting](lighting.md): a **Lighting color** per profile, and **Death counted** for a red flash on a death.
- [ ] [Music & volume pop-ups](flyouts.md): turn on **Microphone** so you see a mute change.
- [ ] [Mixer](sound.md#devices): send the game to your headset and chat to your speakers under **App outputs**, and save it as an output profile.
- [ ] [Mic](voice.md): check **Others hear** before you go live.
- [ ] [Clipboard](clipboard.md): turn on **Wipe codes and keys after a minute**.
- [ ] [Alerts](alerts.md): send alerts to ntfy or Discord so a heat warning reaches your phone.

## Monitoring only

Goal: see what the PC does, get warned early, change nothing.

- [ ] [Sensors](sensors.md): open **All sensors** and use **Find a sensor…** to jump to what you care about.
- [ ] Turn on **Temperature alerts**, and **Drive warnings** for [Drive health](drives.md).
- [ ] [Processes](processes.md): run **Signatures** and **Defender** once after installing new software.
- [ ] [This PC](this-pc.md): see what Deck found and how the PC did this week.
- [ ] Leave fan, CPU and GPU profiles and [Windows tweaks](tweaks.md) alone. Monitoring pages only read.
