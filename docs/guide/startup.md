# Startup apps and the Startup optimizer

Two pages help with a slow sign-in and a crowded start:

- **Startup apps** (Clean > Startup apps) lists every program that starts with Windows and lets you switch each one off or on.
- **Startup optimizer** (Clean > Startup optimizer) measures how long Windows took to start, ranks what slowed it down, and offers a few safe fixes, each of which can be undone.

Neither page deletes anything. Switching a startup app off stops it launching at sign-in; the app stays installed and you can still open it yourself.

---

# Part 1: Startup apps

Find it under **Clean > Startup apps**. The page title line says "What starts with Windows."

## The list

The toolbar shows **N of M apps start with Windows**, a **Search startup apps** box (it matches the name, the launch command and the source) and **Refresh**.

The page has two lists:

- **Starts with Windows**: apps that are switched on.
- **Off at startup**: apps that are listed but switched off.

Each row has the app's icon and name, a second line with where the entry comes from (and, if Windows measured it, "slowed startup by 3 s"), and a switch. Click the name to see details on the right.

### Where entries come from

Deck reads all the places Windows starts programs from, which is the same set Task Manager's Startup tab shows:

| Source | What it is |
|---|---|
| **You (registry)** | The `Run` list for your account. |
| **All users (registry)** | The `Run` list for every account on the PC (including 32-bit entries). |
| **You (Startup folder)** | Shortcuts in your own Startup folder. |
| **All users (Startup folder)** | Shortcuts in the shared Startup folder. |
| **Store app** | Microsoft Store apps (such as WhatsApp, Teams or Phone Link) that start through a startup task declared in their package. |

### The switch

The switch is **the same one Task Manager uses** (Windows' own "StartupApproved" flags). Switching an app off:

- does not delete the entry,
- does not close the app if it is running right now,
- does not uninstall it,
- takes effect at the next sign-in.

Switch it back on at any time. Because it is Windows' own switch, a change made here shows in Task Manager and the other way round.

**All users** entries need administrator rights to change. Without them the switch is replaced by a chip, "On - admin only" or "Off - admin only". Deck normally runs with administrator rights after its one-time set up, so you will usually be able to change them.

### The details panel

Select an app to see:

- A switch, and "Starts with Windows" or "Off at startup".
- **Source**.
- **Launch command**: the exact command Windows runs. **Copy launch command** copies it.
- **Slowed the last start by**: about how many seconds this app added to Windows' recent starts. This is Windows' own measurement (from the Diagnostics-Performance event log), shown only when Windows recorded one. No figure just means Windows did not time that app.

## What to switch off

- **Usually safe to switch off:** chat apps, game launchers, cloud-storage clients you do not need constantly, music players and update helpers, printer and scanner utilities. They start when you open them.
- **Leave on:** your antivirus, your audio and graphics control panels (if you use them), backup software, touchpad and keyboard utilities, and Deck itself if you want it in the tray.
- If you are not sure what something is, the name plus **Launch command** usually tells you. When in doubt, switch it off for a week; nothing is lost, and you can switch it back on.

**Recommended:** switch off what you do not need within seconds of signing in, starting with the entries that show a measured "slowed startup" time. The more apps start together, the longer the desktop feels busy.

---

# Part 2: Startup optimizer

Find it under **Clean > Startup optimizer**. It reads Windows' own startup measurements and local settings, ranks the causes of delay, and keeps a way back for everything it changes.

**Analysis is read-only.** Press **Analyze** to read the measurements. It can take up to about a minute because Windows has to be asked for its startup history and Deck checks services, tasks and settings. Nothing changes until you press a fix button and confirm.

## What it shows

### Last recorded start

A summary such as "Your last recorded start took 38.2 s: 9.5 s firmware, 20.1 s windows, 6.0 s sign-in, 2.6 s desktop settling", with a coloured bar and the four phases:

| Phase | Meaning |
|---|---|
| **Firmware** | The time your motherboard's firmware (BIOS/UEFI) took before Windows started. Only shown when it matches this boot. |
| **Windows** | Windows loading itself, up to the sign-in screen. |
| **Sign-in** | From the sign-in until the desktop was ready. Some Windows versions do not record a sign-in boundary, in which case "Windows and sign-in" are shown together. |
| **Desktop settling** | The time the desktop took to quiet down after it appeared. |

Underneath: the date of the recorded boot, the main path time, Windows' BootTime and the latest firmware reading. Windows measures these itself, so they can differ from clock time, and delays can overlap.

### Last recorded starts

A small bar chart of up to your last 10 recorded Windows starts, oldest to newest (not counting firmware). Shutdown, restart and update starts can differ, so look at the trend rather than a single bar.

### Unavailable measurements

If Windows cannot supply something, a panel says what and how to get it. The most common case: **startup logging is off**. Deck does not turn it on for you. The message tells you to open Event Viewer, go to Applications and Services Logs > Microsoft > Windows > Diagnostics-Performance > Operational, choose **Enable Log** as administrator, and restart Windows. Some Windows setups never publish these events.

### Findings by impact

The ranked list of things that affected the last start. Each finding has:

- A rank, a title, a kind and an **impact** ("2.4 s extra" or "9.1 s total"), with a bar scaled against the biggest.
- A **Keep** chip when the item should stay on (security software, drivers, Windows components).
- Plain advice, the source of the measurement and an **About** fold for longer explanation.
- Action buttons where one applies.

**Measured** findings come from Windows' own record of what slowed that start: apps (switch off at sign-in), services, drivers, devices, Windows components and security software. For an app that is also in your startup list, the **Turn off at sign-in** / **Turn on at sign-in** button is the same switch as the Startup apps page, and it is greyed out for read-only entries. Delays can overlap, so the times are not promised savings.

**Other checks (impact unknown)** are things Deck can see but Windows did not time:

| Finding | What Deck tells you |
|---|---|
| Firmware initialisation takes time | If firmware takes 10 s or more: check Fast Boot and unused boot devices in your BIOS/UEFI. Deck never changes firmware. |
| Hibernation is off | Fast Startup needs the hibernation file. Deck leaves that choice to you because it creates a large system file. |
| Fast Startup is off | Offers **Enable Fast Startup** (see below) when hibernation is on. |
| Explorer delays startup apps | Offers **Remove startup delay** (see below). |
| Windows Update needs a restart | Restart from the Start menu; a start after updates can be slower. |
| Group Policy waits for the network | On managed PCs this may be required; ask the administrator. |
| Windows Search and SysMain | Their start type, as advice only. Deck does not change them. |
| N startup apps enabled | A **Review startup apps** button takes you to Part 1. |
| Automatic services outside the Windows folder | Advice to ask the publisher about delayed start. |
| Scheduled tasks that run at sign-in | Advice to review them in Task Scheduler. Deck does not disable them. |
| The Windows drive is nearly full | With under 15% free, a **Review disk space** button opens [Disk space](drives.md). |
| Windows starts from a hard disk | Advice: reduce optional sign-in work or consider an SSD. |
| Many font files are installed | Over 1,000 font files; advice only. |

## The fixes

Deck offers only a few fixes, all reversible:

| Fix | What it changes | Needs admin |
|---|---|---|
| **Enable Fast Startup** | Turns on Windows' Fast Startup setting. Offered only if it is off and hibernation is on. It helps after **Shut down**, not **Restart**, and can affect dual-boot and some device troubleshooting. | Yes |
| **Remove startup delay** | Sets Explorer's delay for startup apps to zero. Apps launch sooner, but the desktop can feel busier while it loads. The saving is not measured. | No |
| **Use delayed start** | For a few optional updater services (Adobe's and Mozilla's), after checking they are signed and nothing depends on them. The service stays enabled and is not stopped; it just starts after the initial rush. | Yes |

Every other service, task or security tool is advice only, so Deck can never disable your antivirus or a system service from here.

When you press a fix button, Deck asks "Apply this setting for the next start? Deck saves the previous value first." The change takes effect at the **next start**. Fixes are refused while a game is in front.

## Undo startup fixes

A panel lists every fix you applied with its exact previous value saved. **Undo** restores one (it warns that it replaces any later change you made to that setting) and **Undo all** restores everything in reverse order. The undo records are tamper-checked, so if the file is changed elsewhere Deck refuses to use it and tells you to restore from a trusted backup rather than risk writing wrong values.

## Administrator setup

If Deck is not running with administrator rights, a panel offers **Set up administrator access** for the machine-wide fixes. It asks Windows for permission once and restarts Deck.

---

## Recommended setup

1. Open **Startup apps** and switch off the apps you do not need at sign-in, starting with those that show a measured delay.
2. Restart, then open **Startup optimizer** and press **Analyze** to see the new timing.
3. Apply **Remove startup delay** only if you want your tray apps up as fast as possible. Apply **Enable Fast Startup** only if you use Shut down, not Restart, and do not dual boot.
4. Compare using a few starts, not one.

**PCs that start from a hard drive:** every startup app costs more there (the optimizer flags this), so be strict. **Laptops:** Fast Startup only helps after Shut down, not after Restart or waking from sleep.

---

## Troubleshooting

**"Startup logging is off."** Enable the Diagnostics-Performance Operational log in Event Viewer as described above, restart Windows, then analyze again. Deck does not enable it by itself.

**"No recorded boots are available."** The log is on but has no start recorded yet, or your Windows setup does not publish them. Restart once and try again.

**A startup app I turned off still starts.** It may have more than one entry (for example in both the registry and a startup task), or a service or scheduled task starts it. Search its name on the Startup apps page and switch off each entry; if it is a task, Task Scheduler is the place.

**The switch is greyed with "admin only".** It is an all-users entry and Deck is not running with administrator rights.

**A fix says it needs administrator rights.** Use **Set up administrator access**, then apply it again.

**Analyze says it could not read the startup inventory.** Try again after Windows has finished signing in; it times out if the PC is very busy.

---

## FAQ

**Is it safe to switch off startup apps?** Yes. It is the same switch as Task Manager. The app stays installed and works normally when you open it. Security software is the exception worth keeping.

**Will Deck close an app that is running when I switch it off?** No. It only stops it from starting next time.

**Can the optimizer harm my PC?** Analysis only reads. The three fixes are small, labelled and reversible with exact before-values.

**Does Deck start with Windows?** By default it can, hidden in the tray, through its own start-up task. That is controlled by the **Start with Windows** setting in [Settings](settings.md), not from the Startup apps list.

**Why do my "seconds saved" differ from the estimate?** The estimates are not promises. Windows measures each start separately and phases overlap, so use the trend over several starts.
