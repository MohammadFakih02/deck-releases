Where to find it: Startup › Startup apps

# Startup apps and the Startup optimizer

Choose what starts with Windows, see what slowed the last start, and apply a few safe fixes that can be undone.

- **Startup apps** lists every program that starts with Windows, with a switch for each.
- **Startup optimizer** measures how long Windows took to start, ranks what slowed it and offers small reversible fixes.

Neither page deletes anything. An app you turn off stays installed; you can still open it yourself.

## Startup apps

Where to find it: Startup › Startup apps

### The list

The summary shows **Added to boot time**, how many apps are **Enabled**, how many have **Impact measured**, and how many need administrator. Below are **Search startup apps** (name, command or source), a sort (**Impact first** or **Name**) and **Refresh**.

Apps are listed under **Enabled** and **Disabled**. Each row shows the icon, name, source, **Startup impact** (Windows' measured seconds, or **Not measured**) and a switch. Select a row for details on the right.

### Where entries come from

The same places as Task Manager's Startup tab:

| Source | What it is |
|---|---|
| **You (registry)** | The Run list for your account. |
| **All users (registry)** | The Run list for every account, including 32-bit entries. |
| **You (Startup folder)** | Shortcuts in your Startup folder. |
| **All users (Startup folder)** | Shortcuts in the shared Startup folder. |
| **Store app** | Store apps (WhatsApp, Teams, Phone Link) with a startup task. |

### The switch

It is the same switch Task Manager uses. Turning an app off:

- doesn't delete the entry, close the app or uninstall it,
- takes effect at the next sign-in.

A change here shows in Task Manager and the other way round. All users entries need administrator; without it the row shows **On · needs administrator** or **Off · needs administrator**.

### The details panel

- **Source**.
- **Program**: the exact command Windows runs. **Copy program command** copies it.
- How many seconds this app added to recent starts, from Windows' own log, when Windows timed it.

### What to turn off

- Usually safe: chat apps, game launchers, cloud storage you don't need at once, music players, update helpers, printer utilities.
- Leave on: antivirus, audio and graphics control panels you use, backup software, touchpad and keyboard utilities, and Deck if you want it in the tray.
- Not sure? Turn it off for a week. Nothing is lost.

Start with the apps that show the biggest measured impact.

### New at startup

**New at startup** lists programs, tasks and services that began starting with Windows since Deck started watching, with their source (**Run key**, **Startup folder**, **Store app**, **Scheduled task** or **Service**) and when Deck first saw them.

- **Keep** clears the mark.
- **Disable** asks first, then turns the item off. **Undo** turns it back on.
- Deck can't turn off services, and says so.

The watch is off by default. Turn it on with **New startup items** in [Settings](settings.md); it checks every few minutes, never during a game, and never turns anything off automatically.

## Startup optimizer

Where to find it: Startup › Startup optimizer

Analysis only reads. Press **Analyze** (later **Analyze again**); it can take up to a minute. Nothing changes until you press a fix and confirm.

### Start timeline

A summary of the **Last recorded start** with a bar split into four phases:

| Phase | Meaning |
|---|---|
| **Firmware** | Your motherboard's BIOS/UEFI before Windows. Shown only when it belongs to this start. |
| **Windows** | Windows loading, up to the sign-in screen. |
| **Sign-in** | From sign-in until the desktop is ready. When Windows logs no boundary, **Windows and sign-in** show as one part. |
| **Desktop settling** | How long the desktop took to quiet down. |

Chips show the date, **Windows + sign-in** (the main path), **Firmware not counted** when needed, and **No starts since …** when Windows logged nothing for a week. **Usual start** and **Vs usual** compare with your median start.

### Start time

A chart of up to your last 10 starts, oldest to newest, without firmware. Shutdown, restart and update starts differ, so look at the trend.

### When Windows doesn't measure

If startup logging is off, the page says **Startup logging is off**. Deck doesn't turn it on for you. To turn it on:

1. Open Event Viewer as administrator.
2. Go to Applications and Services Logs › Microsoft › Windows › Diagnostics-Performance › Operational.
3. Choose Enable Log.
4. Restart Windows, then press **Analyze**.

### Startup impact

Ranks what affected the last start. Each finding has a rank, a title, its impact ("2.4 s extra"), one sentence on what it cost, and a button where one applies. A **Keep** chip marks items that should stay on (security software, drivers, Windows parts). Delays can overlap, so times are not promised savings.

For an app in your startup list, **Start with Windows** is the same switch as on Startup apps.

**Vs last start** (from the second recorded start on) lists up to five items marked **New**, **Slower**, **Faster** or **Not slow now**.

**Other startup items (N)** are things Windows didn't time:

| Finding | What Deck tells you |
|---|---|
| Firmware takes 10 s or more | Check Fast Boot and unused boot devices in your BIOS. Deck never changes firmware. |
| Fast Startup is off | Offers **Enable Fast Startup** when hibernation is on. |
| Hibernation is off | Fast Startup needs it; Deck leaves that choice to you. |
| Explorer delays startup apps | Offers **Remove startup delay**. |
| Windows Update needs a restart | A start after updates can be slower. |
| Group Policy waits for the network | On managed PCs, ask the administrator. |
| Windows Search and SysMain | Their start type, advice only. |
| Startup apps enabled | **Review startup apps** opens Startup apps. |
| Automatic services outside Windows | One row for all; open it for the names. A signed updater that can wait gets **Use delayed start**. |
| Tasks that run at sign-in | One row for all; check them in Task Scheduler. Deck doesn't turn them off. |
| The Windows drive is nearly full | Under 15 % free: **Review disk space** opens [Disk space](drives.md). |
| Windows starts from a hard disk | Fewer startup apps, or an SSD. |
| Over 1,000 font files | Advice only. |

### The fixes

| Fix | What it changes | Needs administrator |
|---|---|---|
| **Enable Fast Startup** | Turns on Windows' Fast Startup. Helps after Shut down, not Restart, and can affect dual boot. | Yes |
| **Remove startup delay** | Explorer starts startup apps without its usual delay. The desktop can feel busier at first. | No |
| **Use delayed start** | For a few signed optional updater services (Adobe, Mozilla) that nothing depends on. The service still starts, just later. | Yes |

Everything else is advice only, so Deck can't turn off your antivirus or a system service here. Deck asks "Apply this setting for the next start? Deck saves the previous value first." Fixes take effect at the next start and are refused while a game is in front. Machine-wide fixes show **Restart as administrator** when Deck isn't running as administrator.

### Undo startup fixes

**Saved fixes** lists every fix with its saved previous value. **Undo** restores one; **Undo everything** restores all. If the undo list was changed outside Deck, it shows **Undo list unverified** and refuses to use it.

## Recommended setup

1. On **Startup apps**, turn off what you don't need at sign-in, biggest impact first.
2. Restart, then press **Analyze** on the **Startup optimizer**.
3. Apply **Remove startup delay** only if you want tray apps up fast; **Enable Fast Startup** only if you shut down (not restart) and don't dual boot.
4. Judge by a few starts, not one.

## Troubleshooting

- **Startup logging is off.** Turn the log on as described above, restart, analyze again.
- **No starts recorded.** Restart once and analyze again; some Windows setups never publish these events.
- **An app I turned off still starts.** It may have more than one entry, or a task or service starts it. Search its name and turn off each entry.
- **A switch says needs administrator.** It is an all-users entry. Use **Restart as administrator** (see [Getting started](getting-started.md#why-deck-needs-administrator)).
- **Analyze can't read the startup list.** Try again once Windows has finished signing in.

## FAQ

- **Is it safe to turn off startup apps?** Yes; it is Task Manager's switch. Keep security software on.
- **Does turning an app off close it?** No. It only stops it starting next time.
- **Does Deck start with Windows?** Through its own task, set by **Start with Windows** in [Settings](settings.md), not this list.
