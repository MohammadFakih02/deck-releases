# Power: keep awake, timers and shutdown plans

The **Power** group has three pages for controlling when your PC sleeps, shuts down or reminds you of something:

| Page | What it is for |
|---|---|
| **Keep awake** | Stop the PC and (optionally) the screen from going to sleep, for a while, until a download finishes, or while an app runs. |
| **Timers & breaks** | Countdown timers, a stopwatch, and reminders to stand up and rest your eyes. |
| **Shut down when…** | Shut down, sleep, restart (and more) automatically when something happens: a download finishes, an app closes, the PC goes idle, or at a set time. |

**Where to find it:** sidebar > **Power**, then the tab you want. The Home page also has a **Power & timers** tile and the tray menu has a **Keep the PC awake** switch. See [Home](home.md).

None of these pages change your Windows power plan. Keep awake works by asking Windows not to sleep while Deck is running, and gives the request back when it ends. Deck also never touches any game: nothing here involves anti-cheat.

## Contents

- [Keep awake](#keep-awake)
- [Timers & breaks](#timers--breaks)
- [Shut down when…](#shut-down-when)
- [Typing commands in search](#typing-commands-in-search)
- [Recommended setup](#recommended-setup)
- [Troubleshooting](#troubleshooting)
- [FAQ](#faq)

## Keep awake

Windows normally sleeps the PC after some idle time (and turns the screen off sooner). Keep awake overrides that for as long as you choose. When it ends, normal sleep comes back by itself.

### The status panel

At the top, a panel says either **Windows can put this PC to sleep** or **Staying awake**, with what it is doing: a countdown for "for a duration", "While *app* is running. Ends when it closes.", "Downloading. Ends after the last download stays quiet.", or "Until you turn it off." While it is on you get **Turn off**, and for a timed one a **+ 30 min** button to extend it. It also says whether **the screen stays on too**.

### For a duration

| Control | What it does |
|---|---|
| **Start 30 min**, **Start 60 min**, **Start 120 min** | Start immediately. The preset buttons are 30 min, 1 hour and 2 hours. |
| **More durations** (fold) | **Start 4 hours** and **Until I turn it off** (no end time). |
| **Custom duration** | Type 1 to 1440 minutes (24 hours), press **Start duration** (or Enter). |
| **Also keep the screen on** | On (default): the screen will not turn off either. Off: only the PC stays awake; the screen may turn off as usual. You can change it while keep awake is running. |

Recommended: for a download or an overnight job, turn **Also keep the screen on** off so the monitor can sleep and save power; for a presentation or a video, leave it on.

### Until an event

| Control | What it does |
|---|---|
| **Start watching downloads** | Keeps the PC awake until downloads finish. It first waits for a download to *begin* ("Waiting for a download to begin."), then ends once downloads have stayed quiet long enough. |
| **Download options** (fold) | **Count as downloading above** (default **100 KB/s**, 1 to 100000) and **Stop after downloads stay quiet for** (default **1 minute**, 1 to 1440). These two numbers are Deck settings shared by every "until downloads finish" keep awake. |
| **Start watching app** | Choose a running app from the list (**Choose a running app…**), then start. It stays awake while that app runs and ends when the app closes. |

What counts as a download: an unfinished download file (extensions such as `.crdownload`, `.part`, `.download`, `.tmp` and a few others) written to recently in your Downloads folder, a Steam game download that is genuinely in progress, or network traffic above the speed you set. A paused or abandoned download does not count forever.

When a "downloads" keep awake ends, you get a "Downloads finished: your PC can sleep normally again" notification.

### Also keeping this PC awake

A read-only list of **other** programs and drivers that are asking Windows to stay awake (it reads Windows' own power-request list). Use **Refresh requests** to reload it. If it says "Windows reports no active power requests." nothing else is holding the PC up. This is useful when your PC refuses to sleep and you want to know who is responsible.

### Windows sleep settings (side panel)

Shows, read-only, when the **PC sleeps after** and the **screen turns off after** according to the active Windows power plan for the current power source (plugged in or on battery). "never" means 0 / disabled. Keep awake overrides these while it is on. **Open Windows sleep settings** jumps to Windows Settings to change them; the other two buttons open **Shut down when…** and **Timers & breaks**.

### Good to know

- A running keep awake also appears under **Active changes** on Home, where **Release** turns it off.
- Keep awake belongs to Deck: if you **quit Deck**, the request ends and normal sleep returns. It is not saved across a restart of Deck.
- An app-based keep awake waits for the app to be seen running first, so you can start it before launching the app.
- Closing the laptop lid or pressing the power button follows your Windows lid / power-button settings; keep awake does not change those.

## Timers & breaks

### Timers

- **Your timers:** every running timer with time left, a progress bar, **Pause / Resume** and a remove button. A finished timer shows **Done** and an **Again** button.
- **Start a timer:** presets **Start 5 min**, **Start 10 min**, **Start 25 min**, a **More durations** list (1, 3, 15, 45, 60 min), or type a **Duration** such as `25m`, `1h30`, `90s` or `1:30` with an optional **Label** ("Tea", "Laundry"…) and press **Start timer**.
- When a timer ends you get a sticky notification with a sound, with **5 more min** and **OK** buttons. It rings even if Deck's panel is closed, as long as Deck is running.
- You can also start one by typing `timer 10m` in the search box, or tapping a preset on the Home tile.

Timers only run while Deck is running. If you quit Deck, they stop.

### Stopwatch

**Start / Stop**, **Lap** and **Reset**. Laps show both the split and the total time.

### Break reminders

| Setting | What it does | Default |
|---|---|---|
| **Remind me to stand up or look away** | A nudge after a stretch of use. Waits for fullscreen games and videos to end before showing. | Off |
| **Remind me every** (appears when the above is on) | 20, 30, 45, 50, 60, 90 or 120 minutes. | 50 minutes |
| **Rest your eyes every 20 minutes** | The "20-20-20" rule: every 20 minutes of use, look at something about 6 metres away for 20 seconds. Waits for fullscreen games and videos to end. | Off |

How they count: time only counts while you are using the PC. About two quiet minutes (no keyboard or mouse) resets the stand-up reminder; about 20 quiet seconds resets the eye-break clock. The stand-up notification offers **10 more min** and **Done**. A reminder due during a game or fullscreen video is held back and shows as soon as you leave it; Deck never interrupts a game.

## Shut down when…

This is Deck's "do something when something happens" tool. You choose an **action** and a **condition**, adjust the options, and press **Start plan**. Only **one plan** can be set at a time. While a plan is set, the page shows it with its progress and a **Cancel** button, and the sidebar shows a **Set** badge.

### Actions

| Action | What happens |
|---|---|
| **Shut down** | Windows shuts down. |
| **Sleep** | The PC sleeps. Open work stays open. |
| **Restart** | Windows restarts. |
| **Hibernate** | Saves memory to disk and powers off. Needs hibernation to be enabled in Windows (otherwise Deck reports "Hibernate is turned off on this PC"). |
| **Lock** | Locks Windows. |
| **Sign out** | Signs you out. |
| **Screen off** | Turns the monitors off. |
| **Just tell me** | Only shows a notification when the condition is met. Nothing else happens. |

For Shut down, Sleep, Restart, Hibernate and Sign out, Deck asks you to confirm when you start the plan, and spells out what will happen ("Open work and games will close…" or "Open work and games stay open…") and how many seconds of warning you will get.

### Conditions

| Condition | Meaning | Extra field |
|---|---|---|
| **Downloads finish** | Nothing is downloading any more (browser, Steam or any download). The page shows current download speed. | "After the last one, wait" minutes (default 5). |
| **After a while** | A number of minutes from now. | In *N* minutes. |
| **At a time** | A clock time. If that time has already passed today, it means tomorrow. | At (time). |
| **An app closes** | A chosen running app (a game, an export, an install) has closed. | Choose a running app. |
| **An app finishes its work** | A chosen app that stays open (a render, an export) has become quiet: its CPU use drops below a level for some minutes, after having been busy. | Choose a running app; "Quiet for" minutes. |
| **Music or video stops** | Audio or video that was playing has stopped. It first waits until something has played. | "Silent for" minutes. |
| **The PC goes idle** | CPU use stays below a level (renders, installs, builds). | "Quiet for" minutes. |
| **The graphics card goes idle** | GPU use stays below a level. Only listed when Deck can read an NVIDIA graphics card. | "Quiet for" minutes. |
| **The disk goes quiet** | Disk reads plus writes stay below a speed (installs, unpacking, copying). | "Quiet for" minutes. |
| **The network goes quiet** | Network traffic stays below a speed (uploads, syncing). | "Quiet for" minutes. |
| **I've been away** | No mouse, keyboard or controller input for some minutes. | "Away for" minutes. |

The builder shows a sentence such as "Shut down when downloads finish" and a one-line warning about what happens ("You get 1 minute to cancel before anything happens.").

### Plan options

Options are remembered between plans on this PC (they are kept in the page's local storage). **Undo changes** puts the form back to defaults.

**For every plan**

| Option | What it does | Default |
|---|---|---|
| **Warning** (seconds) | When the condition is met you get a notification with **Cancel** and **Do it now** for this many seconds before anything happens. 0 means no warning. Not used for "Just tell me". | 60 s |
| **Not while I'm playing** | If a fullscreen game or video is in use, the plan waits until you leave it, then gives you a **fresh warning** before acting. | On |
| **Keep the PC awake while waiting** | Stops Windows sleeping before the download ends or the set time arrives. Not applied to "I've been away", and not applied while Deck is still waiting for a download, playback or app to start. | On |
| **Close apps that hold it up** | For Shut down, Restart and Sign out only: forces apps with unsaved work to close. **Unsaved work in them is lost.** Without it, Windows waits for someone to answer. | Off |

**Condition options** (shown for the condition you chose)

| Condition | Option | Default |
|---|---|---|
| Downloads finish | **Quiet below** (KB/s): traffic under this counts as not downloading (averaged over several readings). | 100 |
| | **Paused after** (min): an unfinished file untouched this long counts as paused. | 5 |
| | **Also watch** folders (separated by semicolons) where your download manager saves; Downloads is always watched. | none |
| Network goes quiet | **Quiet below** (KB/s) and **Count uploads too**. | 100, on |
| PC idle | **Idle below** (% CPU). | 10 |
| App finishes its work | **Finished when under** (% CPU): the app must be busy first, then quiet. | 10 |
| Graphics card idle | **Idle below** (% GPU). | 10 |
| Disk quiet | **Quiet below** (KB/s). | 1024 |
| App closes | **Closed for** (seconds), so a launcher that restarts itself does not count. | 30 |
| I've been away | **A controller counts as being here**; **Playing music or video counts as being here**. | on, off |
| Downloads finish / An app closes | **Then wait until the PC is idle**: also wait for CPU and disk to go quiet for the plan's minutes. Good for a download that unpacks or installs afterwards. Shows its own CPU % and disk KB/s fields. | Off |

### While a plan is set

- The plan panel shows what it is waiting for and how far along it is ("Network quiet for 2 min of 5 min", a countdown to a set time with a progress bar).
- When the condition is met the state becomes a **countdown**. You get a sticky notification ("Shut down in 60 s") with **Cancel** and **Do it now**. **Do it now** runs the plan at once; **Cancel** drops it.
- If, during the warning, the condition stops being true (a download resumes, you come back to the PC, the app reopens), the warning is called off and Deck goes back to waiting, with a short notification saying why.
- Download, music and app conditions need to see the thing **happen first**: "downloads finish" will not fire until a download has been seen, "app closes" not until the app has been seen running, so nothing fires immediately because nothing was happening yet. The page says "Waiting for a download to start" / "Waiting for *app* to start" while that holds.
- A plan with a **set time** that Windows slept through is **skipped**, not run late. If the PC was asleep or off at the set time (more than 10 minutes late), Deck drops the plan with a notice rather than acting when you wake it, so a 23:00 shutdown never hits you the next morning.
- Plans are saved, so they survive Deck restarting (an update, a crash) and carry on waiting, with anything they had already seen kept and a fresh warning if one was running. But a plan from **before this Windows session** (before you last signed in, restarted or shut down; Fast Startup does not count as a restart here) is dropped, except a set-time plan, so "shut down when downloads finish" set last night cannot shut down the PC you just switched on. A plan cannot run while Deck is closed.
- The same plan can also be set from search, from the Home tile, from your phone and from notifications; they all use the same single plan.

### Quick picks

On the right of the builder:

- **Shut down when downloads finish** (2 quiet minutes after the last one)
- **Sleep when music stops** (after it has been quiet a minute)
- **Sleep when I'm away 20 min**
- **Sleep in 30 min**, **Sleep in 1 hour**, **Shut down in 1 hour**

Each asks for the usual confirmation, uses the options last set in the form, and replaces any plan already set.

### Outgoing messages for plans

If you turned on [Alerts](alerts.md) "Notifications out" for **Shutdown plans**, the warning before a plan acts is also sent to your phone or chat. See [Alerts](alerts.md).

## Typing commands in search

In Deck's search box:

| Type | Result |
|---|---|
| `timer 10m` (or `t 10m`) | Starts a 10-minute timer. |
| `sleep in 30m`, `shutdown in 2h`, `restart in 1h`, `lock in 10m` | Sets a timed plan (with the usual confirmation). Also accepts `after` instead of `in`. |
| `awake 2h` (also `keep awake`, `caffeine`, `stay awake`) | Keeps the PC awake for 2 hours. |
| `cancel` / `stop` (optionally followed by `plan`, `sleep`, `shutdown` or `restart`) | Cancels the current shutdown plan, when one is set. |

There are also search actions "Keep the PC awake" and "Let the PC sleep normally".

## Recommended setup

- **Overnight download or render:** use **Shut down when… > Downloads finish** (or **An app closes** / **The PC goes idle**) with **Then wait until the PC is idle** if it unpacks afterwards, leave the 60-second warning on, and turn off "Also keep the screen on" in Keep awake if you also use it.
- **Falling asleep to a film or music:** **Sleep when music stops** or **Sleep in 1 hour**.
- **Gamers:** keep **Not while I'm playing** on so a plan never closes a game under you. Use "Just tell me" if you want to be told but not acted on.
- **Laptops:** use Keep awake for a duration instead of "until I turn it off" so you do not forget and drain the battery. Sleep, rather than Shut down, if you want to come back to your work.
- **Quiet PCs:** keep the warning at 60 seconds or more; it is your only chance to cancel.
- Leave **Close apps that hold it up** off unless you have saved everything and need the shutdown to finish unattended.

## Troubleshooting

**The PC went to sleep even though Keep awake was on.** Check the status panel says **Staying awake**. A timed one ends at its time. Lid-close and the power button follow Windows' own settings, and manual Sleep from the Start menu always works. Quitting Deck ends it.

**The PC will not go to sleep.** Open Keep awake and look at **Also keeping this PC awake** for programs holding a request, and make sure Deck's own keep awake is off. A pending shutdown plan with **Keep the PC awake while waiting** also holds the PC up while it waits.

**"Shut down when downloads finish" never fires.** It waits until it has seen a download start, then until nothing downloads for the number of minutes you set. A download that writes to an unusual folder is not seen: add that folder under **Also watch**. A leftover `.tmp` or unfinished file that is no longer being written does not count after the "Paused after" time. Very small or very slow traffic below the **Quiet below** speed counts as quiet.

**The plan did not run after I woke the PC.** Deck skips a set-time plan that Windows slept through, and drops plans from before a restart / sign-out. Set it again.

**"Hibernate is turned off on this PC".** Enable hibernation in Windows (an elevated `powercfg /hibernate on`), or choose Sleep.

**The graphics card idle condition is missing.** It is only offered when Deck can read an NVIDIA card.

**Nothing fired because I was in a game.** That is **Not while I'm playing**. The plan waits until you leave the fullscreen game or video, then gives a fresh warning.

**My timer did not ring.** Timers only run while Deck is running. If you quit Deck the timer is gone.

## FAQ

**Can I have two plans at once?** No, one plan at a time. Setting a new one replaces the old one (the quick picks say so).

**Can I stop a plan after the warning has started?** Yes: press **Cancel** in the notification or on the page, or type `cancel` in search. You can also press **Do it now**.

**Does Deck change my Windows power plan?** No. Keep awake only sets a request while Deck runs. (CPU profiles on the [CPU](cpu.md) page do work with Windows power plans, but that is separate.)

**Will an unsaved document be lost on shutdown?** Not unless you turn on **Close apps that hold it up**. Without it, Windows waits for apps to answer, as with a normal shutdown.

**Does keep awake affect anti-cheat or games?** No. It only asks Windows not to sleep; it never touches a game process.

**Does the shutdown plan work with the Deck window closed?** Yes, as long as Deck is running in the tray. It does not run if Deck is quit.

**Are timers and reminders sent to my phone?** Only the shutdown-plan warning can be sent out (see [Alerts](alerts.md)). Timers and break reminders show on this PC.
