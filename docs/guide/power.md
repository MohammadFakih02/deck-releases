Where to find it: Power & time › Keep awake

# Power: keep awake, timers and shutdown plans

The Power & time area controls when your PC sleeps, shuts down or reminds you of something.

| Page | What it is for |
|---|---|
| [Keep awake](#keep-awake) | Keep the PC (and the screen) from sleeping: for a while, until downloads finish, or while an app runs. |
| [Timers & breaks](#timers--breaks) | Timers, a stopwatch, break reminders and time rules. |
| [Shut down when…](#shut-down-when) | Shut down, sleep, restart and more when something happens or at a set time. |

Home's **Power & timers** tile and the tray menu's **Keep awake** reach the same features ([Home](home.md)). None of these pages change your Windows power plan, and none touch a game.

## Keep awake

Keep awake asks Windows not to sleep for as long as you choose. When it ends, or when you quit Deck, normal sleep returns.

### The Keep awake card

The card shows **On** or **Off** and **Keeping awake** or **Not keeping awake**.

- **Off:** one click starts it: **30 min**, **1 hour**, **2 hours**, **4 hours** or **Indefinitely**.
- **On:** the time left, how it ends (**Until** a time, **While** an app **runs**, **Downloading** or **Waiting for a download**, or **Indefinitely**), **30 min** (adds time to a timed one), and **Stop**.
- **Keep screen on**: on, the screen stays on too; off, only the PC stays awake. You can change it while Keep awake runs. Turn it off for overnight downloads so the monitor can sleep.

### Other ways to start

| Card | What it does |
|---|---|
| **For a duration** | Type 1 to 1440 **Minutes** and press **Start duration** (or Enter). |
| **Until downloads finish** | Set **Downloading above** (default 100 KB/s) and **Then quiet for** (default 1 min), then **Start watching downloads**. It waits for a download to begin, then ends once downloads have been quiet that long. |
| **While an app runs** | Pick an app in **Choose a running app…**, then **Start watching app**. It ends when the app closes. You can start it before the app opens. |

A download is an unfinished download file in your Downloads folder that is still being written (such as `.crdownload` or `.part`), a Steam download in progress, or network traffic above your speed. When a downloads keep awake ends, a notification says so.

### Windows sleep

Read only: **PC sleeps after** and **Screen off after** from your Windows power plan for the current power source. Keep awake overrides them while it is on. **Open settings** opens Windows' sleep settings.

### Windows requests

Other programs and drivers asking Windows to stay awake, from Windows' own list. Use it when your PC won't sleep. **Refresh list** reads it again. Windows only shows this list to an administrator.

### After the PC wakes

A few seconds after the PC wakes, Deck checks audio devices, graphics card settings, fans, lighting, monitor brightness and the phone server (only parts this PC has) and tries again what didn't come back, after 2, 6 and 20 seconds. The **Check** row shows the last result (**All fine** or **N failing**); each part shows **Fine**, **Fixed** or **Still failing**, with the reason behind **?**. **Check now** runs it again. It waits while a game is in front (**Waiting for game**).

### What woke this PC

Read only, from Windows: **Last wake source**, **Wake timers** and **Devices allowed to wake the PC**. If Windows refuses a read, the card says it couldn't read it.

### Battery health

On PCs with a battery: the **Report date**, **Full charge / design capacity** and the **Cycle count** when Windows reports it. These are the battery's own estimates.

- **Monthly capacity trend**: up to 12 months from Windows' history, one value per month. Gaps stay empty.
- **Sleep drain sessions**: how much charge was lost during each sleep. **Sleep study needs Modern Standby.**
- The report refreshes at most once a day and waits while a game runs. If it fails it says **Report unavailable. Reopen this page tomorrow to try again.**
- Reports stay on your PC. A capacity drop of another 5 % adds a line to **Activity**.

Each app's power use on battery is on [Power use](power-use.md); the **PC status › Power use** link at the top of the page opens it.

### Good to know

- A running Keep awake is listed under **What Deck changed**, where **Undo** turns it off.
- It doesn't survive quitting Deck.
- Closing the lid or pressing the power button follows your Windows settings.

## Timers & breaks

### Timers

- The top card shows **Next to ring** with its time and **Rings at**, and counts of **Counting down**, **Paused** and **Finished**.
- **Start a timer**: one click on **1**, **3**, **5**, **10**, **15**, **25**, **45** or **60** min, or type a **Duration** (`25m`, `1h30`, `90s`, `1:30`) and an optional **Label (optional)**, then **Start timer**.
- **Your timers**: each timer with **Pause** or **Resume**, **+5 min** and **Cancel**. A finished one shows **Done**, **Again** and **Dismiss**.
- When a timer ends, a notification rings from the tray, even with Deck's window closed.
- You can also type `timer 10m` in search or use Home's tile.

Timers only run while Deck runs.

### Stopwatch

**Start** or **Stop**, **Reset** and **Lap**. Laps show the split and the total.

### Break reminders

| Setting | What it does | Default |
|---|---|---|
| **Stand-up reminder** | A nudge after a stretch of use. | Off |
| **Remind me every** | 20 to 120 minutes (shown while the reminder is on). | 50 minutes |
| **Break length** | 30 seconds to 10 minutes. | 1 minute |
| **Eye-rest reminder** | Every 20 minutes: look about 6 meters away for 20 seconds. | Off |

Only time at the PC counts: about two minutes without keyboard or mouse resets the stand-up count, about 20 seconds resets the eye-rest one. Reminders wait for fullscreen games and videos to end, so they never interrupt a game.

### Timeline

**Timer timeline** (on this page) and **Plan timeline** (on **Shut down when…**) show each step as **Done**, **Now**, **Next**, **Skipped**, **Missed** or **Paused**, with an **On hold:** line and the reason when something waits. Sleeping time doesn't count as "quiet". A warning that ran out during sleep starts again instead of acting; a timer that ran out still rings and says how long ago.

### Time rules

**Time rules** change fans, lighting or volume at set times.

1. Press **Add a rule** and name it.
2. Choose the time and the days (**Mon** to **Sun**, **Weekdays**, **Weekends** or **Every day**).
3. Pick a **Fans** preset, a **Lighting** effect and a **Volume**, or leave a field on **Leave as is**.
4. Press **Save rules**.

Up to 12 rules. A rule waits while a game is in front, and is skipped for the day if its time passed more than 6 hours ago. Fan presets need hardware control.

**What rules changed** lists recent changes as **Applied**, **Failed**, **Undone** or **Sent, not confirmed**, with **Undo** to restore the old value.

## Shut down when…

Choose an action and a condition, check the options, and press **Start plan**. Only one plan can be set at a time; the sidebar shows **Set** while it is.

### Build a plan

1. Under **Action**, choose what happens.
2. Under **When**, choose the condition. Fill in its fields (minutes, a time, an app or a folder).
3. Check **Plan options** and any condition options.
4. Press **Start plan**. For Shut down, Sleep, Restart, Hibernate and Sign out Deck asks first, saying whether open work closes and how long the warning is.

**Discard changes** clears the form. Your options are remembered on this PC.

### Actions

| Action | What happens |
|---|---|
| **Shut down**, **Restart**, **Sign out** | As in Windows. |
| **Sleep** | The PC sleeps; open work stays open. |
| **Hibernate** | Saves memory to disk and powers off. Needs hibernation turned on in Windows. |
| **Lock** | Locks Windows. |
| **Screen off** | Turns the monitors off. |
| **Just tell me** | Only shows a notification. |

### Conditions

The **When** list is grouped into Time, Jobs, Activity and Hardware.

| Condition | Met when | Fields |
|---|---|---|
| **After a while** | A number of minutes has passed. | **In** minutes |
| **At a time** | The clock reaches the time (tomorrow if it has passed today). | **At** |
| **Downloads finish** | Nothing downloads any more (browser, Steam or any download). | Quiet minutes |
| **Deck's downloads finish** | Deck's own downloads (Store apps, Deck updates) are done. The plan names the download and its progress; if it fails, the plan is called off. | **Then wait** |
| **A transfer finishes** | A [PC to PC](pc-to-pc.md) transfer or a copy to another drive is done. A failed transfer calls the plan off. | **Then wait** |
| **A folder stops changing** | Nothing is written to a chosen folder for some minutes. | **Folder**, **Quiet for** |
| **An app finishes its work** | An app that stays open (a render) has been busy and is now quiet. | **App**, **Quiet for** |
| **An app closes** | A chosen app has closed. | **App** |
| **A task says it's done** | Every program that signals Deck is finished. See [When a task says it's done](#when-a-task-says-its-done). | Minutes |
| **Music or video stops** | Something played and has stopped. | **Silent for** |
| **I've been away** | No mouse, keyboard or controller input. | **Away for** |
| **The PC goes idle** | CPU use stays low. | **Quiet for** |
| **The graphics card goes idle** | GPU use stays low. Only when Deck can read the graphics card. | **Quiet for** |
| **The disk goes quiet** | Disk use stays low. | **Quiet for** |
| **The network goes quiet** | Network traffic stays low. | **Quiet for** |

The card shows the plan as a sentence, such as "Shut down when downloads finish and stay quiet for 5 min".

### Plan options

| Option | What it does | Default |
|---|---|---|
| **Warn me before** | Seconds of warning, with **Cancel** and **Do it now**. 0 means no warning. | 60 s |
| **Not while I'm playing** | Waits while a fullscreen game or video is in use, then warns again. | On |
| **Keep awake while waiting** | Stops Windows sleeping while the plan waits. | On |
| **Force-close apps that block it** | Shut down, Restart and Sign out only: closes apps that would stop it. Unsaved work is lost. | Off |

Condition options (only for the chosen condition):

| Condition | Option | Default |
|---|---|---|
| Downloads finish | **Quiet below** (KB/s), **Paused after** (min: an untouched file counts as paused), **Also watch** (more folders; Downloads is always watched). | 100, 5 |
| The network goes quiet | **Quiet below** (KB/s), **Count uploads too**. | 100, on |
| The PC goes idle, The graphics card goes idle | **Idle below** (%). | 10 |
| An app finishes its work | **Finished when under** (% CPU). | 10 |
| The disk goes quiet | **Quiet below** (KB/s). | 1024 |
| An app closes | **Closed for** (seconds), so a launcher that restarts itself doesn't count. | 30 |
| A task says it's done | **Waiting for my answer** (min; 0 waits for you), **A task that stops with an error counts as done**. | 0, off |
| I've been away | **A controller counts as being here**, **Playing music or video counts as being here**. | on, off |
| Downloads finish, An app closes | **Then wait until the PC is idle**, with **Counts as idle below** for CPU and disk. Good for downloads that unpack afterwards. | Off |

### When a task says it's done

For jobs Deck can't judge from outside, such as a coding tool working in the background, or a long script: the program tells Deck itself.

Set it up once under **Where signals come from**:

- **Signals from** Claude Code and **Signals from** Codex: a switch each. Deck adds a few lines to that tool's settings file and removes them when you turn it off. Codex asks you to approve the new hooks once: type `/hooks` in it.
- **Any other program or script**: **Copy line**, then run it with `start` when the work begins and `done` when it ends.

**Tasks Deck has heard from** lists each task:

| It says | The plan |
|---|---|
| **Working** | waits |
| **Waiting for you** (it asked a question) | waits, or goes on after **Waiting for my answer** |
| **Stopped** (an error or usage limit) | waits, or goes on if you turned that option on |
| **Finished** | goes on once every counted task is finished |

**Don't count** leaves a task out; **Count again** puts it back. A tool you stop by hand sends nothing and stays **Working**, so use **Don't count**. Work in WSL, the cloud or another PC isn't seen. Try it first with **Just tell me**.

### While a plan is set

- The plan card shows what it waits for and how far along it is, with **15 more min** and **Cancel**.
- When the condition is met, a warning notification ("Shut down in 60 s") offers **Cancel** and **Do it now**. If the condition stops being true during the warning, Deck goes back to waiting and says why.
- Download, music and app conditions first wait to see the thing happen, so nothing fires at once.
- **Missed times are skipped**: if the PC was asleep or off at the set time, the plan is dropped instead of running late.
- Plans survive a Deck restart. A plan from before you last restarted or signed in is dropped (except a set-time plan), so last night's "when downloads finish" can't shut down the PC you just turned on.
- **Replace this plan** opens the builder again.

The same plan can be set from search, Home, your phone or a notification.

### Quick picks

**Shut down when downloads finish**, **Sleep when music stops**, **Sleep when I'm away 20 min**, **Sleep in 30 min**, **Sleep in 1 hour** and **Shut down in 1 hour**. Each asks first, uses your last options and replaces any plan.

The warning can also go to your phone or chat through [Alerts](alerts.md).

## Typing commands in search

| Type | Result |
|---|---|
| `timer 10m` (or `t 10m`) | Starts a 10-minute timer. |
| `sleep in 30m`, `shutdown in 2h`, `restart in 1h`, `lock in 10m` | Sets a timed plan, after you confirm. `after` works too. |
| `awake 2h` (also `keep awake`, `stay awake`) | Keeps the PC awake for 2 hours. |
| `cancel` or `stop` | Cancels the current plan. |

## Recommended setup

- **Overnight download or render:** **Downloads finish** (or **An app closes**, **The PC goes idle**), with **Then wait until the PC is idle** if it unpacks afterwards, and the 60-second warning.
- **Falling asleep to music or a film:** **Sleep when music stops** or **Sleep in 1 hour**.
- **Gamers:** keep **Not while I'm playing** on.
- **Laptops:** use Keep awake for a duration so you don't drain the battery.
- Leave **Force-close apps that block it** off unless everything is saved.

## Troubleshooting

**The PC slept even though Keep awake was on.** Check the card says **Keeping awake**. A timed one ends at its time; the lid and power button follow Windows; quitting Deck ends it.

**The PC won't sleep.** Look at **Windows requests** for programs holding it awake, and check that Deck's own Keep awake and **Keep awake while waiting** in a plan aren't on.

**"Shut down when downloads finish" never fires.** It first waits to see a download start. A download manager that saves elsewhere isn't seen: add its folder under **Also watch**. Traffic below **Quiet below** counts as quiet.

**The plan didn't run after the PC woke.** Missed set times are skipped, and plans from before a restart are dropped. Set it again.

**Hibernate is turned off.** Turn hibernation on in Windows (`powercfg /hibernate on` as administrator), or choose Sleep.

**The graphics card condition is missing.** It only shows when Deck can read the graphics card.

**My timer didn't ring.** Timers only run while Deck runs.

## FAQ

**Can I have two plans?** No. A new plan replaces the old one.

**Can I stop a plan during the warning?** Yes: **Cancel** in the notification or on the page, or type `cancel` in search.

**Does Deck change my Windows power plan?** Not from these pages. (CPU profiles can; see [CPU](cpu.md).)

**Will unsaved work be lost on shutdown?** Only with **Force-close apps that block it** on.

**Does a plan run with Deck's window closed?** Yes, while Deck runs in the tray. Not after you quit Deck.

**Are timers sent to my phone?** No. Only the plan warning can be sent ([Alerts](alerts.md)).
