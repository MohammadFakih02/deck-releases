Where to find it: Hardware › CPU

# CPU

Switch your processor between cool and quiet and full speed with one click, and see what it is doing right now.

The page has three tabs: **Profiles**, **Sensors** and **Cores**. Related pages: [GPU](gpu.md) (graphics card profiles work the same way), [Fans](fans.md), [Game profiles](gaming.md) (a CPU profile per game) and [Sensors](sensors.md).

## How CPU profiles work

A CPU profile is a real Windows power plan (named "Deck · <profile name>") plus a few extras Deck applies itself.

The power plan holds the clock caps (one for the whole CPU, or separate caps for main and background cores), the processor state, the turbo mode, how many cores stay awake and the energy preference. Switching profiles switches the active plan, which takes effect at once. This works on any Intel or AMD CPU, desktop or laptop, without administrator.

The extras are things a power plan can't do:

- CPU power limits (Intel), applied again if the firmware resets them
- a clock floor, so the CPU doesn't drop below a clock
- a turbo overclock on unlocked Intel CPUs
- **Hold the cap in games**, which turns Windows Game Mode off while the profile is on

On a fresh install Deck adds three ordinary profiles once: **Gaming**, **Everyday** and **Quiet**. Edit, rename or delete them like any profile.

If you pick a different plan in Windows or another tool, the matching profile's card lights up. Deck never disables the CPU's idle states, and a cap at or above your CPU's top turbo counts as no cap.

## What you need

| Feature | Needs |
|---|---|
| Profiles (clock caps, turbo, processor state, cores kept awake, energy preference) | Any Intel or AMD CPU. |
| Live clock, temperature, power and per-core sensors | Deck running as administrator. |
| CPU power limits | Administrator and an Intel CPU. On other CPUs the power-limit choices only set Windows' power mode, and the editor says so. |
| Clock floor | Administrator. |
| Turbo overclock | An unlocked Intel CPU (K and KF) and administrator. The slider only appears on one. |
| Plugged in and on battery switching | A PC with a battery. |

Without administrator the page shows **Power limits and per-core sensors need administrator** with **Restart as administrator**. See [Why Deck needs administrator](getting-started.md#why-deck-needs-administrator). In Windows Safe Mode Deck changes no clocks or limits ([FAQ](faq.md)).

## The Profiles tab

From top to bottom:

1. **Applied profile**: the profile that is on, with what it **Asks for** beside the **Current** value (clock or main and efficient cores, **Power**, **Turbo / energy**). **Edit profile** opens its editor. With no Deck profile on, it says "Windows power plan".
2. **Built-in modes** beside **Your profiles**.

A banner appears when the measured power limit differs from the profile ("Power limit 125 W · profile asks 65 W"). **Reapply profile** sends it again. A short difference right after a switch is normal.

**Your profiles** has one card per profile with its name, a summary and its shortcut key. Click a card to switch to it; the pencil edits it. Chips:

| Chip | Meaning |
|---|---|
| **On** | This profile is active. |
| **Plan missing** | The Windows plan behind it was deleted. Applying or saving the profile rebuilds it. |
| **Above stock** | The profile overclocks. After an unexpected restart it isn't applied again (see [Crash guard](#crash-guard-for-the-turbo-overclock)). |
| **Taken by another app** | Another program uses that shortcut key. Choose another. |
| **Crashed … this week** | See [Crashes this week](#crashes-this-week). |

The **⋯** menu has **Edit profile**, **Export profile…**, **Duplicate profile** and **Delete profile and shortcuts** (it offers **Delete power plan**; leave it off to keep the plan in Windows).

In the **Your profiles** heading:

- **New profile** creates a profile that starts as a copy of the active Windows plan and opens its editor.
- The download icon has **Import Windows power plans…** (turns plans already on this PC, such as ThrottleStop's, into profiles; Windows' own plans are never selected for you, and the plans themselves are not changed) and **Import profile file…**.

## Built-in modes

Five ready-made modes, the same on every PC. The names mean the same as on [GPU](gpu.md#built-in-modes). Click a row or **Use** to switch. Chips say what each mode changes (for example **Speed first** and **Max power**, **No turbo** and **15 W**, **Default**). The **⋯** menu has **Copy to my profiles to change it**.

| Mode | What it sets | Use it for |
|---|---|---|
| **Performance** | Every core awake, aggressive turbo, energy preference 0, the board's power limits with Windows set to best performance | Heavy work, rendering, compiling |
| **Balanced** | Windows' own balance | Everyday use |
| **Quiet** | Gentle turbo, energy preference 60 | Nearly full speed with less heat and noise |
| **Saver** | No turbo, 15 W sustained and 25 W bursts, energy preference 80, holds the cap in games | Light work, laptops on battery |
| **Low power** | No turbo, at most half speed, Saver's power limits, energy preference 100 | Longest battery life, coolest PC |

- Modes can't be edited or deleted, but you can give one a shortcut key and desktop or Start menu shortcuts.
- Modes appear wherever profiles do: the tray, the phone, Game profiles and battery switching.
- The eye button in the heading hides the modes (**Hide built-in modes** / **Show built-in modes**). The CPU and GPU pages remember this separately.
- Power limits need an Intel CPU and administrator. Otherwise the mode applies the plan values and Windows' power mode.

## The profile editor

Click the pencil or **Edit profile**. The header holds **Back to CPU**, the icon, **Name** and **Shortcut key**, and two tabs: **Speed & power** and **Advanced**. An **Unsaved** chip shows when you have changes.

- Nothing reaches the CPU until you press **Save profile** (**Save and apply profile** for the active one).
- **Discard** drops your changes; **Close** shows when there are none.
- **Apply temporarily** puts the settings on the CPU for 60 seconds without saving. A strip counts down with **Restore now**. The old settings come back when time is up, when you leave the editor, when Deck quits, or after a crash.
- Leaving with unsaved changes asks **Discard your changes?** with **Keep editing** and **Discard changes**.
- **More** (**⋯**) has **Desktop shortcut**, **Start menu** and **Lighting color** (lights one color while the profile is on; a GPU profile color wins). Shortcuts switch the profile without opening Deck and never show an administrator prompt.

### Speed & power

| Setting | What it does | Recommended |
|---|---|---|
| **CPU speed limit** (or **Main cores' speed limit** and **Background cores' speed limit**) | The highest clock, in 100 MHz steps. Fully right is **No cap**. Lower means less heat, noise and power, but slower heavy work. Most games barely notice. | Games: a little under top turbo saves a lot of power. |
| **Turbo boost** | Whether the CPU may boost above its base clock. The label shows the mode, such as "On · Efficient". **Change mode in Advanced** opens the choices. | On. Off for the coolest, quietest PC. |
| **Energy preference** | A hint to the CPU's boost logic: 0 ramps up fastest and runs hottest, 100 slowest and coolest. Fully left is **Plan's own**. | Plan's own. |

**Power limits**:

| Choice | What it does |
|---|---|
| **Motherboard** | Your board's own limits (the default). |
| **Saver 15 W** | 15 W sustained, 25 W bursts, Windows set to best power efficiency. |
| **Performance** | The board's limits, Windows set to best performance. |
| **Custom** | **Power for long tasks** (sustained) and **Power for short bursts**, from 5 W. The burst is never below the sustained value. |

The sustained limit decides heat and noise in long loads such as games. The burst limit covers short spikes of tens of seconds. Custom limits can't go above what your board started with. A **Needs administrator** chip shows when Deck can't set limits.

### Advanced

Rarely needed: wrong values can make the PC hot, slow or unstable.

**Clock limits**

| Setting | What it does |
|---|---|
| **Clock floor** | Keeps the cores above this clock, which can stop stutter while the CPU ramps up. Costs idle heat and power. The real floor lands about 8 % lower than you pick. Released automatically above 92 °C and when you switch profile. Needs administrator. |
| **Overclock turbo to** | Raises the turbo limit up to 300 MHz above top turbo on unlocked Intel CPUs. Too high can crash or freeze the PC: raise in small steps and test. |
| **Hold the cap in games** | Only with a clock cap. Turns Windows Game Mode off while the profile is on, because Game Mode can lift your caps in games. Game Mode comes back when you switch to a profile without a cap. |

**Windows plan settings**

| Setting | What it does |
|---|---|
| **Turbo mode** | **Off**, **On**, **Aggressive** (most plans), **Efficient** or **Efficient aggressive**. |
| **Max processor state** | The top speed Windows asks for. On most CPUs anything under 100 % also turns turbo off. |
| **Min processor state** | The lowest speed when idle. Windows' default is 5 %. |
| **Cores kept awake** | The share of cores Windows never parks. More responds faster but uses more idle power. |

The editor warns when the speed limit stops the overclock from taking effect, or when the clock floor is above the cap (the cap wins).

## The Sensors tab

Tiles for **Load**, **Temperature** (with a **Normal**, **Warm** or **Hot** chip: warm from 80 °C, hot from 90 °C) and **Power**, then a live chart and:

- **Measured now**: the clock of the fastest core and **Power used** against the limit in force ("65 W · 125 W burst" when the two differ), with **Set by the active profile** or **Set by your motherboard**, the clock asked for and what holds the CPU back.
- **Held at the power limit** shows when load is at least 60 % and power at least 95 % of the limit: the CPU would clock higher with more power.
- **In-game clock check**: while a game runs under a capped profile, the real average and peak clock. **Above the cap** means the average went more than 5 % over: turn on **Hold the cap in games**. **Game Mode off** shows while Deck keeps Game Mode off.
- **Asked and measured**: the last applied limits next to the value read back, each **Verified**, **Changed by the hardware**, **Not taken** or **Not confirmed**.

A line under the tabs names a running vendor program (such as Armoury Crate) that can reset Deck's power limits, with **Pause** for this session. **Start again** (or restarting the PC) brings it back. Pause is refused while a game runs.

## The Cores tab

- **Core sensors**: clock, load and temperature per core (P = performance, E = efficient), and a heat strip with one cell per core. Needs administrator. AMD CPUs report one package temperature.
- A chart of clock, temperature, load or power over the last minute, with **now**, **min** and **max**.

## Settings for CPU profiles

In **Settings › CPU and GPU**:

| Setting | What it does | Default |
|---|---|---|
| **Profile keyboard shortcuts** | Turns every profile shortcut key on or off. | On |
| **Notice when a profile switches** | A small notice at each CPU or GPU profile switch. | On |
| **Desktop and Start shortcuts** › **Recreate shortcuts** | Rebuilds every profile shortcut if one stopped working. | |
| **When plugged in, switch to** / **On battery, switch to** (PCs with a battery) | The profile to use when the charger connects or you unplug. | **Don't switch** |
| **Profiles also apply on battery** | Off: on battery Windows keeps the plan's own battery values. | On |
| **Memory** › **Free up memory** | Trims memory programs aren't using and empties Windows' standby cache. Nothing closes. Needs administrator. The tray has the same action as **Clear RAM**. | |

Battery switching never happens while a game session has set a profile.

Profiles also switch from Home's CPU drop-down, the tray's **CPU profile** menu, shortcut keys, desktop shortcuts, the [phone](phone.md) and [Game profiles](gaming.md).

## What Deck changes and how to undo it

| Deck changes | How to undo it |
|---|---|
| Creates "Deck · <name>" power plans and makes one active | Switch to any other plan. Delete a profile with **Delete power plan** to remove its plan. |
| Writes the CPU power limits (Intel) | Switch to a profile with **Motherboard** limits. |
| Raises the clock floor or turbo limit (Intel) | Turn the setting **Off** and save, or switch profile. |
| Turns Game Mode off for **Hold the cap in games** | Switch to a profile without a cap. |
| Creates shortcuts and scheduled tasks for profile shortcuts | Delete the profile or turn the shortcut off. |

**Reset all hardware** (Profiles tab, under **Applied profile**) hands fans, the graphics card, CPU power limits and lights back to the hardware's own control, then lists each part: **Back to stock** only for a part that was read again and matches, **Still changed** otherwise. Saved profiles are kept, but none stays active.

Uninstalling Deck stops all of this. Your power plans stay in Windows until you delete them.

### Crash guard for the turbo overclock

If the PC restarted while the turbo overclock was on, the next start uses factory settings and the page says **Overclock held back**. Apply it again by hand once you trust it. Power plans and caps can't crash a PC, so only the overclock is guarded.

## Crashes this week

A profile or mode shows a **Crashed … this week** chip (once, twice or 3×) when the PC, a game or the graphics driver crashed while it was on. Deck never turns a profile off for this. See [GPU › Crashes this week](gpu.md#crashes-this-week).

## Recommended setups

- **Most people:** **Balanced** day to day, **Quiet** for a calm PC, **Performance** for heavy work. Use [Game profiles](gaming.md) to switch per game.
- **Gamers:** a profile with a speed limit a little under top turbo and **Hold the cap in games** on; check **In-game clock check**. If a game stutters while the CPU ramps up, try a moderate **Clock floor**.
- **Laptops:** plugged in Balanced or Performance, on battery Saver (or Low power).
- **Quiet PCs:** **Quiet**, or a profile with a modest **Custom** limit (for example 65 W on a CPU that runs 125 W stock). Pair it with a gentle curve on [Fans](fans.md).
- **Unlocked Intel CPUs:** raise **Overclock turbo to** in 100 MHz steps and stress test after each.

## Troubleshooting

**The page says power limits and per-core sensors need administrator.** Press **Restart as administrator**. One Windows prompt, then Deck starts with the rights every time.

**Power limits show "Needs administrator", or the CPU reports no limit.** Deck isn't running as administrator, or the CPU isn't Intel. On AMD the choices only set Windows' power mode.

**The power limit I set isn't the one measured.** Press **Reapply profile**. Some boards lock the limit in firmware; then the board wins. Custom values above the board's own are held at the board's value.

**A card says "Plan missing".** The Windows plan was deleted. Switch to the profile, or edit and save it, and Deck rebuilds it.

**My clock cap doesn't hold in games.** Turn on **Hold the cap in games** (**Advanced** › **Clock limits**) and check **In-game clock check**. A cap at or above top turbo counts as no cap.

**The shortcut key does nothing.** Check **Profile keyboard shortcuts** in Settings › CPU and GPU. If the card says **Taken by another app**, pick another key.

**Per-core values are empty.** They need administrator. If Deck runs as administrator and they stay empty, open [Sensors](sensors.md) to see which source provides them.

**The overclock is gone after a restart.** The crash guard held it back on purpose. Apply it again once the PC is stable.

## FAQ

**Is it safe with anti-cheat?** Yes: plans and caps are ordinary Windows settings, and Deck never touches games. One anti-cheat, FACEIT, refuses Deck's hardware driver; see [Fans › What happens with anti-cheat](fans.md#what-happens-with-anti-cheat).

**Can it damage the CPU or void the warranty?** Caps and lower limits only ask the CPU to do less. The turbo overclock carries the same risk as overclocking in the BIOS; Deck allows at most 300 MHz above top turbo, only on unlocked CPUs, and never raises power limits past your board's.

**What happens when I quit Deck?** The power plan stays active and its values keep working. The clock floor is released. A turbo overclock stays in the CPU until the PC restarts.

**What does "hardware held" mean?** Another program edited Deck's fan, CPU or GPU settings files, so Deck won't act on them until you press **Apply them** in the notice. Apply only if you made the change.

**Can I use ThrottleStop or a vendor tool too?** Deck doesn't fight over plans, but two programs writing power limits will. Use one at a time, or **Pause** the vendor program.

**Can I share a profile?** **Export profile…** shows it as text (**Copy text**, **Save file**); only values go in. **Import profile file…** checks it against this PC and **Add profile** adds it switched off.
