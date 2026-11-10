# CPU

The CPU page lets you switch your processor between "quiet and cool" and "everything on" with one click. Each choice is a **CPU profile**: a real Windows power plan plus a few extras Deck applies itself (power limits, a minimum clock, an optional overclock, and a way to stop Windows Game Mode lifting your limits). The page also shows what the CPU is actually doing: clock, temperature, load, power, the power limit in force and every core.

**Where to find it:** sidebar > **Tune** > **CPU**. The page has four tabs: **Profiles**, **Power & limits**, **Cores** and **Settings**. Deck remembers the tab you used last.

Related pages: [GPU](gpu.md) (graphics card profiles, which work the same way), [Fans](fans.md), [Gaming](gaming.md) (pick a CPU profile per game), [Sensors](sensors.md) (every reading, graphs and history), [Power](power.md).

## Contents

- [How CPU profiles work](#how-cpu-profiles-work)
- [What you need](#what-you-need)
- [The Profiles tab](#the-profiles-tab)
- [Built-in modes](#built-in-modes)
- [The profile editor](#the-profile-editor)
- [The Power & limits tab](#the-power--limits-tab)
- [The Cores tab](#the-cores-tab)
- [Settings for CPU profiles](#settings-for-cpu-profiles)
- [Switching profiles without opening the page](#switching-profiles-without-opening-the-page)
- [What Deck changes on your PC, and how to undo it](#what-deck-changes-on-your-pc-and-how-to-undo-it)
- [Recommended setups](#recommended-setups)
- [Troubleshooting](#troubleshooting)
- [FAQ](#faq)

## How CPU profiles work

**Starter profiles.** On a fresh install with no profiles of your own, Deck adds three ordinary, editable profiles once: **Gaming**, **Everyday** and **Quiet**, copies of built-in modes (of Performance, Balanced and Quiet). Edit, rename or delete them like any profile; deleting them doesn't bring them back.

A CPU profile has two halves.

**The Windows power plan half.** Deck creates and manages a normal Windows power plan for each profile (named "Deck · <profile name>"). It holds:

- the highest clock the performance cores (P-cores) and efficiency cores (E-cores) may run at, or one cap for the whole CPU on processors without the two kinds
- the maximum and minimum processor state
- the turbo boost mode
- how many cores stay awake (core parking)
- the energy preference

Switching profiles switches the active Windows power plan, which takes effect instantly. These settings need no admin rights, work on Intel and AMD, and on desktops and laptops.

**The extras half.** Things Windows plans cannot do, which Deck applies itself:

- **CPU power limits** (Intel's PL1 and PL2), re-applied if the firmware resets them
- a **clock floor** that stops the CPU dropping below a clock
- a **turbo overclock** on unlocked Intel CPUs
- **Hold the cap in games**, which turns Windows Game Mode off while the profile is on

Deck also watches for plan changes made elsewhere (every two seconds). If you pick a different plan in Windows or in another tool, the card of the matching profile lights up.

Two safety rules apply everywhere:

- A clock cap at or above your CPU's top turbo counts as "no cap", so a profile never ends up holding the CPU at its maximum by accident.
- Deck never disables the CPU's idle states. A CPU that cannot idle runs hot doing nothing.

## What you need

| Feature | Needs |
|---|---|
| Profiles built on power plans (clock caps, turbo mode, processor state, cores kept awake, energy preference) | Nothing special. Any Intel or AMD CPU, any Windows 10 or 11 PC. |
| Live readings of clock, temperature, power, per-core clocks | Deck running as administrator (the page shows a banner with **Set up admin access** if it isn't). |
| CPU power limits (Saver, Performance, Custom), reading the limit in force | Administrator rights and an **Intel** CPU. On other CPUs the power-limit choices only set Windows' power mode, and the editor says so. |
| Clock floor | Administrator rights. Listed as an Intel feature in Deck's README. |
| Overclock turbo | An **unlocked Intel** CPU (K and KF models) and administrator rights. The slider only appears when Deck detects one. |
| Plugged in / on battery switching | A PC with a battery. |
| Clear RAM | Administrator rights. |

Deck reads some CPU values through a small signed hardware driver (PawnIO) that it installs when you set up admin access. See [Troubleshooting](#troubleshooting) if readings stay empty.

## The Profiles tab

This is the first tab. From top to bottom:

**Applied profile.** The profile that is on now, with the values it asks for: the requested clock cap (P-core cap on a CPU with two kinds of core) and the requested sustained power (**Motherboard**, **15 W** for Saver, or your custom watts). **Edit profile** opens its editor, and its shortcut key shows beside it. If no profile matches the active plan, it says "Windows power plan".

**A warning banner** appears when the CPU power limit measured on the CPU differs from what the profile asked for ("The CPU power limit differs from the profile: asked 65 W, measured 125 W"). **Re-apply profile** sends it again. A short difference right after a switch is normal.

**Your profiles.** One card per profile. A card shows its name, a one-line summary, its shortcut key, small icons if it has a desktop or Start menu shortcut, and these chips:

| Chip | Meaning |
|---|---|
| **On** | This profile is active. |
| **Plan missing** | The Windows power plan behind the profile was deleted. Applying or saving the profile rebuilds it. |
| **OC** | The profile overclocks. It is not re-applied automatically after an unexpected restart (see [Crash guard](#crash-guard-for-the-turbo-overclock)). |
| **Taken by another app** (on the shortcut chip) | Another program already uses that key. Choose another; Deck keeps trying. |

Click a card to switch to it. The pencil edits it. The **...** menu has:

- **Edit profile**
- **Duplicate profile**
- **Delete profile and shortcuts**: asks for confirmation and offers **Also delete the Windows power plan**. Leave it off to keep the plan in Windows.

**Built-in modes** sit in a fold under your profiles (see below).

**Page buttons:**

| Button | What it does |
|---|---|
| **New profile** | Asks for a name and creates a profile that starts as a copy of the active Windows power plan, then opens its editor. |
| **Use my existing plans** (with a **?**) | Lists power plans already on this PC (made by you or a tool such as ThrottleStop) and turns the ticked ones into Deck profiles. Windows' own plans (Balanced, High performance, Power saver, Ultimate Performance) are never ticked for you. The plans are not changed or copied, so old shortcuts to them keep working. Plans that are already profiles are greyed out. |

## Built-in modes

Five ready-made profiles, the same on every PC. Open the **Built-in modes** fold on the Profiles tab. One click switches; the **...** menu has **Copy to my profiles to change it**, which makes an editable copy and opens it.

| Mode | What it sets | Use it for |
|---|---|---|
| **Performance** | Every core awake, turbo aggressive, energy preference 0 (speed), the Performance power preset | Heavy CPU work, rendering, compiling |
| **Balanced** | Windows' own balance: boosts for work, saves when idle | Everyday use |
| **Quiet** | Gentle (efficient) turbo, energy preference 60 | Nearly full speed with less heat and fan noise |
| **Saver** | No turbo, Saver power limits (15 W sustained, 25 W bursts), energy preference 80, holds the cap in games | Light work, laptops on battery |
| **Ultra saver** | No turbo, at most half speed, Saver power limits, energy preference 100, holds the cap in games | Longest battery life, coolest PC. Slow in heavy work. |

Good to know:

- Each mode gets its own Windows plan the first time you use it ("Deck · Saver" and so on).
- Deck writes their settings at every start, so they cannot be edited or deleted; Deck refuses a delete. You can still give a mode a shortcut key and desktop / Start menu shortcuts.
- Modes appear everywhere profiles do: the tray, the phone remote, Gaming, and plugged in / on battery switching.
- The button with the eye icon on the **Built-in modes** header folds all modes away (**Hide modes** / **Show modes**). They then sit behind one "Modes" row in profile pickers. The CPU and GPU pages remember this separately.
- The power limits in Saver, Ultra saver and Performance need an Intel CPU with admin rights. On others the mode still applies the plan values and Windows' power mode, and a note says what could not be done.

## The profile editor

Click the pencil on a card or **Edit profile**. The editor opens in place of the page with a **Back to CPU** button and three tabs: **Profile**, **Speed & power** and **Advanced**. A yellow **Unsaved** chip shows when you have changes. **Nothing reaches the CPU until you press Save** (it applies at once if the profile is the active one). **Discard** drops your changes; **Close** appears when there are none.

### Profile tab

| Setting | What it does | Default |
|---|---|---|
| **Use a lighting colour while this profile is active** | Turns the board and RAM lights one colour while this profile is on. Afterwards the previous effect returns. A GPU profile colour wins over a CPU one. See [Lighting](lighting.md). | Off (colour #009BDE when you switch it on) |
| **Icon** | Click the icon to pick one of the built-in icons, or **Choose file...** for your own `.ico`, `.png` or `.exe` icon. The icon is used on shortcuts. | A built-in icon |
| **Name** | Up to 40 characters. | The name you gave |
| **Shortcut key** (**?**) | A key combination that switches to this profile from anywhere, even inside a game. Use Ctrl, Alt or Win with a key. | None |
| **More** (the **...** button) | Shows **Desktop shortcut** and **Start menu** switches. Each creates a shortcut that switches to this profile without opening Deck. Saving adds or removes them; deleting the profile removes them. | Off |

Shortcuts run through a small Windows scheduled task, so switching from a shortcut never shows an admin prompt. If the shortcuts break, use **Repair** in Settings › CPU and GPU.

### Speed & power tab

**Speed**

| Setting | What it does | Recommended |
|---|---|---|
| **Max clock** (or **P-cores max** and **E-cores max** on CPUs with both kinds of core) | The highest clock Windows lets the cores run at (the plan's "Maximum processor frequency"). The slider moves in 100 MHz steps; fully right is **No cap**. A lower cap means less heat, noise and power, but slower CPU-heavy work such as compiling or rendering. Most games barely notice because the graphics card is the limit. | Games: a little under top turbo saves a lot of power. E-cores: a low cap saves power almost for free; too low slows heavy multi-core work. |
| **Turbo boost** | Whether the CPU may boost above its base clock. Off is the strongest cooling setting there is: the CPU stays at its base clock. On sets Aggressive; other modes are under Advanced. | On for games and work. Off for the coolest and quietest PC. |
| **Energy preference** | A hint to the CPU's own boost logic (Intel Speed Shift, AMD CPPC): 0 ramps up instantly and runs hottest; 100 ramps slowly and runs coolest. Fully left is **Plan's own**, with the plan's current value shown beside it. | Leave on Plan's own unless you have a reason. Deck's plans copy Balanced. |

A hint appears if the plan favours saving (a value above 0) while you expect games to ramp up quickly.

**Power limits** (**?**)

| Choice | What it does |
|---|---|
| **Motherboard** | The limits your board set. This is the default. |
| **Saver 15 W** (shown as **Saver**) | 15 W sustained, 25 W bursts, and Windows set to best power efficiency. |
| **Performance** | The board's limits, with Windows set to best performance. |
| **Custom** | You choose **Sustained (PL1)** and **Burst (PL2)** with sliders (from 5 W; the burst is always kept at least as high as the sustained value). |

Notes:

- The CPU's **sustained limit** (PL1) is the wattage it may draw for as long as it likes: it decides heat and noise in long loads such as games and rendering. The **burst limit** (PL2) is for short bursts of tens of seconds: lowering it stops short heat spikes and fan revs.
- **Custom limits can't go above the limits your board started with.** If you ask for more, they are held at the board's value.
- Deck re-applies the limits if the firmware resets them.
- A chip says **Needs admin** when Deck has no admin rights. Without an Intel CPU, only the three Windows power modes apply.

### Advanced tab

Two folds. The first opens by itself when one of its settings is on.

**Advanced clocks**

| Setting | What it does | Risk and undo |
|---|---|---|
| **Clock floor** (**?**) | Raises the plan's minimum so the cores never drop below this clock. Some games stutter while the CPU ramps up from a low clock; holding it up removes the ramp. Higher means smoother games but more idle heat and power. Fully left is **Off**. The real floor lands about 8 % under the number you pick, because Windows maps the percentage a little low. Deck lets go of it if the CPU passes 92 degrees C (a heat guard) and when you switch profile. | Needs admin. Set it back to **Off**, or switch profile. |
| **Overclock turbo to** (**?**) | Raises the CPU's turbo ratio limit (up to 300 MHz above top turbo, in 100 MHz steps) so every core may boost higher. Only for unlocked Intel CPUs. Fully left is **Off**. | **Too high can crash or freeze the PC.** Raise in small steps and test. If the PC restarts by itself, turn it off. See [Crash guard](#crash-guard-for-the-turbo-overclock). |
| **Hold the cap in games** (**?**) | Only shown when the profile caps the clock. Turns Windows Game Mode off while the profile is on, because Game Mode can lift the CPU's limits inside games, which would lift the caps you set. | Game Mode comes back by itself when you switch to a profile without a cap. |

**Advanced Windows plan settings**

| Setting | What it does |
|---|---|
| **Turbo mode** | **Off**: base clock only. **On**: boosts with work. **Aggressive**: sooner and harder (most plans). **Efficient**: only when it is worth the power. **Efficient aggressive**. |
| **Max processor state** | The top speed Windows asks for, as a share of full speed. 100 % is full. On most CPUs anything under 100 % also turns turbo off, so 99 % is an old cooling trick. |
| **Min processor state** | The lowest speed the CPU drops to when idle. Windows' default is 5 %. Higher is snappier but idles warmer and uses more power. It never limits top speed. |
| **Cores kept awake** | The share of cores Windows never parks (puts into deep sleep). More awake smooths stutters and responds faster, at the cost of idle power. 100 % means no core is parked. |

### Warnings the editor shows

- If the overclock is higher than the P-core cap: "The P-core cap stops the CPU before the overclock can take effect."
- If the clock floor is above the cap: "The clock floor is above the cap: the cap wins."

## The Power & limits tab

Shows the **Applied profile** panel beside **Measured now**, then the difference banner and **In-game clock check**.

**Measured now** is live (updated every second):

- the **clock** of the fastest core, with **Temp**, **Load** and **Power** under it
- **Effective sustained limit**: the wattage limit in force, with a bar showing power against it ("65 W · 125 W burst" if the two differ). Under it: **Set by the active profile** or **Set by your motherboard**, a line like "Asked for 4,200 MHz (your cap), running 3,900 MHz", and the reason the CPU is held back, if Deck can tell.
- **Held at the power limit** (warning): shown when load is at least 60 % and power is at least 95 % of the sustained limit (or the burst limit when it is higher). It means the CPU draws all it may and would clock higher with more. If your cooling allows, raise the limit with a Custom limit in the profile, or go back to **Motherboard** limits.

**In-game clock check** (**?**): while a game is in front under a capped profile, Deck records the real CPU clock (average and peak) so you can see whether the cap held without alt-tabbing. If the average went more than 5 % over the cap, a chip says **Above the cap**: turn on **Hold the cap in games** in the profile. A chip **Game Mode held off** shows while Deck is keeping Game Mode off.

## The Cores tab

- **Core readings**: one row per core with its clock, load and temperature (P-cores and E-cores are labelled P and E). Needs admin; without it the tab says "Per-core clocks need Deck to run as admin."
- **CPU over the last minute**: a chart of the clock, temperature, load or power (pick one above it), with numbers on both axes. The line fills the chart from the moment you open the page; the time axis says how long it covers.

AMD CPUs report one package temperature rather than a temperature per core.

## Settings for CPU profiles

These live in **Settings › CPU and GPU**.

**CPU and GPU profiles** (shared with the GPU page and the overlay):

| Setting | What it does | Default |
|---|---|---|
| **Profile keyboard shortcuts** | Switches every profile shortcut key on or off in one go. | On |
| **Show a notice when a profile switches** | A small notice each time a CPU or GPU profile switches. | On |
| **Desktop and Start menu shortcuts** > **Repair** | Recreates every profile shortcut. Use it if one stopped working or was deleted. | |

**Plugged in and on battery** (only on PCs with a battery; **?**):

| Setting | What it does | Default |
|---|---|---|
| **When plugged in, switch to** | The profile Deck switches to when the charger connects. | Don't switch |
| **On battery, switch to** | The profile Deck switches to the moment you unplug. | Don't switch |
| **Profiles also apply on battery** | On: a profile's caps hold on battery too. Off: on battery Windows keeps the plan's own battery values, as before Deck. | On |

Deck checks the power source every two seconds. It never switches while hardware control is on hold (see [FAQ](#faq)) or while a Gaming session has switched the plan or a CPU profile.

**Memory** (**?**) > **Clear RAM now**: asks programs to hand back memory they are not using and empties Windows' standby cache (files kept in memory for reuse). Free memory rises at once. Programs reload what they need, so the next moments can be a little slower. Nothing closes and no work is lost. Needs admin. Useful before a game on a PC short of memory, or when a game stutters after hours of browsing. The tray has the same action as **Clear RAM**.

## Switching profiles without opening the page

Every way runs the same code, so they all do the same thing:

- profile cards and the Home page's CPU drop-down
- the tray's **CPU profile** submenu (the built-in modes sit in a **Modes** submenu)
- the profile's shortcut key
- desktop and Start menu shortcuts
- the [phone remote](phone.md)
- [Gaming](gaming.md), per game (and back when the game closes)
- plugged in / on battery switching

## What Deck changes on your PC, and how to undo it

| Deck changes | How to undo it |
|---|---|
| Creates Windows power plans named "Deck · <name>" and makes one active | Switch to any other plan, in Deck or in Windows. Delete a profile with **Also delete the Windows power plan** to remove its plan. |
| Writes the CPU's power-limit register (Intel) | Switch to a profile with **Motherboard** limits. Deck keeps a copy of the board's original values for this. |
| Raises the clock floor or the turbo ratio (Intel) | Turn the setting **Off** and save, or switch profile. |
| Turns Windows Game Mode off while a profile with **Hold the cap in games** is on | Switch to a profile without a cap and Game Mode comes back by itself. |
| Creates shortcuts and scheduled tasks for profile shortcuts | Delete the profile (it removes its shortcuts) or turn the shortcut off in the editor. |

Uninstalling Deck stops all of this. Your Windows power plans stay in Windows until you delete them.

### Crash guard for the turbo overclock

If the PC restarted without Deck quitting while the turbo overclock was on, the next start brings the CPU up **at stock** and the overclock is not re-applied. A toast says why, and you can apply it again by hand. Without a clean end Deck cannot know whether the overclock caused the restart, so it plays safe. Only the turbo overclock is guarded; power plans and caps cannot crash a PC.

## Recommended setups

**Most people (desktop):** Use **Balanced** day to day. Switch to **Quiet** when you want the PC calm, **Performance** for heavy work. Set **Gaming** (see [Gaming](gaming.md)) to switch profile per game.

**Gamers:** Make a profile with a P-core cap a little under top turbo and **Hold the cap in games** on, then check the **In-game clock check** to see it held. Games usually lose almost nothing and the CPU runs much cooler. If a game stutters while the CPU ramps up, try a **Clock floor** at a moderate clock. Leave the overclock off unless you know your CPU and cooling.

**Laptops:** Set **When plugged in** to Balanced or Performance and **On battery** to Saver (or Ultra saver for the longest battery). Leave **Profiles also apply on battery** on.

**Quiet PCs:** Pick **Quiet**, or build a profile with turbo on, a modest sustained power limit (Intel: Custom PL1, for example 65 W on a CPU that stock-runs 125 W) and an energy preference around 60. Pair it with a gentle fan curve on [Fans](fans.md).

**Intel unlocked CPUs (K/KF) and overclocking:** raise **Overclock turbo to** in 100 MHz steps, stress test after each, and keep an eye on temperature on [Sensors](sensors.md). Keep the sustained limit within what your cooler handles.

## Troubleshooting

**The page says "Windows plans and clock caps work. Hardware limits and per-core readings need admin."** Click **Set up admin access**. One admin prompt, then Deck starts with the rights it needs and never asks again.

**Power limits say "Needs admin", or the CPU reports no limit.** Either Deck has no admin rights, or your CPU is not Intel. On AMD, the power-limit choices only set Windows' power mode.

**The power limit I set isn't the one measured.** The banner on the Profiles / Power tabs shows both. Press **Re-apply profile**. Some boards lock the register in firmware; then the board's limits win and nothing Deck does can change them. Custom values above the board's own are held at the board's value.

**A profile card says "Plan missing".** The Windows plan was deleted (perhaps in Windows' own settings or by a cleaning tool). Press **Edit profile** and **Save**, or switch to the profile, and Deck rebuilds it.

**My clock cap doesn't hold in games.** Windows Game Mode can lift the cap. Turn on **Hold the cap in games** in the profile (**Advanced** tab > **Advanced clocks**). Check **In-game clock check** to confirm.

**The clock is higher than my cap.** A cap at or above the CPU's top turbo counts as no cap. If the cap is real, Windows Game Mode may be lifting it in games: see the previous answer.

**The profile shortcut key does nothing.** Check that **Profile keyboard shortcuts** is on (Settings › CPU and GPU). If the chip says **Taken by another app**, choose another key.

**Per-core readings are empty.** They need admin rights. If you set up admin and still see nothing, open [Sensors](sensors.md): the reading's "Where these readings come from" says which collector provides it.

**The overclock isn't there after a restart.** Deck held it back on purpose because the PC restarted unexpectedly while it was on (the crash guard). Re-apply it by hand once you are sure the PC is stable.

## FAQ

**Is it safe for anti-cheat?** Deck never injects into games or reads their memory. Plans, caps and profile switches are ordinary Windows settings. The CPU power-limit and overclock features talk to the CPU through Deck's signed hardware driver, not through the game. One anti-cheat client, FACEIT, refuses to run alongside that driver: while FACEIT is running Deck hands the fans back to the BIOS and stops using the driver, then resumes when it closes. See [Fans](fans.md#what-happens-with-anti-cheat).

**Will it void my warranty or damage the CPU?** Plan values, caps and lower power limits only ask the CPU to do less. The turbo overclock asks it to do more, which is the same risk as overclocking in the BIOS. Deck only allows an overclock on CPUs it detects as unlocked, only up to 300 MHz above top turbo, and never raises power limits past what your board set.

**What happens when I quit Deck?** The Windows power plan stays active, and plan values (caps, turbo, energy preference) keep applying because Windows owns them. The clock floor is let go when Deck quits. Deck re-asserts power limits only while it runs (if the firmware resets them). A turbo overclock that is on when you close Deck stays in the CPU until the PC restarts, so the crash guard still counts it if the PC then restarts unexpectedly.

**What does "hardware held" mean?** If another program edits Deck's fan, CPU or GPU settings files, Deck refuses to act on them: the fans stay on the BIOS, no overclock is applied and profiles do not switch by themselves until you click **Apply them** in the toast. Apply only if you made the change. This protects you from software that tries to borrow Deck's admin rights.

**Do profiles work together with Gaming?** Yes. In [Gaming](gaming.md) you can pick a CPU profile per game; Deck switches when the game starts and goes back when it ends. Plugged in / on battery switching does not interfere while a game session has set the profile.

**Can I use ThrottleStop or my vendor's tool alongside it?** Deck does not fight over plans: it reads existing plans (**Use my existing plans**) and notices when you or another tool change the active plan. Two programs writing power limits at once will fight, though, because Deck re-asserts its limits. Use one at a time.

**What gets deleted if I delete a profile?** The profile, its shortcuts, and optionally its Windows plan. Nothing else.

**What if I choose Ultra saver and the PC feels slow?** It caps the CPU at half speed with no turbo on purpose. Switch to Quiet or Balanced.
