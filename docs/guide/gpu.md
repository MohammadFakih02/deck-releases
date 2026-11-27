Where to find it: Hardware › GPU

# GPU

Tune an NVIDIA graphics card with saved profiles and ready-made modes, switched with one click or a key, like MSI Afterburner's profile slots.

The page has two tabs: **Profiles** and **Sensors**. Related pages: [CPU](cpu.md) (profiles work the same way), [Fans](fans.md) (case and CPU fans), [Game profiles](gaming.md) (a GPU profile per game) and [Performance overlay](overlay.md).

## What you need

- An NVIDIA graphics card. AMD and Intel graphics have no GPU page; [Sensors](sensors.md) shows their temperature and load. On an NVIDIA card or driver without tuning, the page says "GPU tuning isn't supported by this graphics card or driver" with a link to **PC status › Sensors**.
- Deck running as administrator. Without it the page shows **Card changes need administrator** with **Restart as administrator**. See [Why Deck needs administrator](getting-started.md#why-deck-needs-administrator).
- Some controls depend on the card: **Highest speed** and **Lowest speed** need Volta or newer, **Memory speed** needs Ampere (RTX 30) or newer, and **Temperature limit**, **Voltage boost** and the voltage curve show only when the card offers them.
- Some laptop cards don't let the power limit change. **Highest speed** and **Memory speed** still save power there.

Each control only shows if your card supports it.

## Safety

Lowering the power limit, capping the speed, slowing memory and fan curves can't run the card past what it was built for. Anything that runs it faster than stock (a positive speed adjustment, voltage boost, a curve raised at high voltages) is an overclock and can crash games, freeze the PC or reset the driver.

- The editor always says which it is: **Safe settings: nothing here runs the card faster than it was made to.** or **Overclock: can crash games or the PC. After a crash Deck starts at stock.**
- The first overclock you make asks **This is an overclock** with **I understand**.
- **Apply temporarily** tries settings without saving them.
- The [crash guard](#crash-guard-and-applying-again) starts the card at stock if the PC restarted during an overclock.
- Card settings reset at every PC restart unless Deck applies a profile at start.

To undo everything, press **Reset GPU** in **Applied profile**. Your profiles are kept.

## The Profiles tab

1. **Applied profile**: the active profile, with what it **Asks for** beside the **Current** value for **Power limit**, **Core clock**, **Memory** and **Fan**, plus what holds the card back (such as **Held back by the power limit**). **Edit profile**, **Reset GPU** and **Reset all hardware** (see [CPU](cpu.md#what-deck-changes-and-how-to-undo-it)) are here.
2. **Built-in modes** beside **Your profiles**.
3. **Auto undervolt**.

Banners you may see:

| Banner | What to do |
|---|---|
| **MSI Afterburner** may override the card | Press **Stop Afterburner from tuning…** (see [MSI Afterburner](#msi-afterburner)). |
| **Overclock held back** · factory settings now | The PC restarted during an overclock. **Reapply the held profile** once you trust it. |
| "Power limit 100 W · profile asks 98 W" | The measured limit differs. **Reapply profile** sends it again. The card can't go outside its own range, so a small difference can stay. |

**Your profiles** has a card per profile with a summary (for example "85% power · +120 MHz · custom curve") and chips: **On**, **Above stock** (an overclock, not applied again after an unexpected restart), **Taken by another app** and **Crashed … this week**. Click a card to apply it; the pencil edits it. The **⋯** menu has **Edit profile**, **Export profile…**, **Duplicate profile** and **Delete profile and shortcuts**.

**New profile** is in the heading. The download icon has **Import profile file…** and, with Afterburner installed, **Import from Afterburner…**.

On a fresh install Deck adds three ordinary profiles once: **Gaming**, **Everyday** and **Quiet**, copies of modes your card has.

## Built-in modes

Ready-made profiles worked out from your card's own limits, so another card gets other numbers. Click a row or **Use** to apply one. Modes can't be edited: the **⋯** menu has **Copy to my profiles** and **Shortcut key and shortcuts…**. The eye button in the heading hides them.

| Mode | What it does |
|---|---|
| **Performance** | The card's highest power and temperature limits. Hotter and louder. Only when the card has headroom above stock. |
| **Balanced** | The card as sold. |
| **Quiet** | About 75 % power: a few frames less, cooler and quieter. |
| **Efficient** | Full memory speed, the core held at the fastest speed it reaches at its lowest voltage. Most frames for far less power. |
| **Saver** | Most frames per watt: lower memory speed too. On cards without clock locks, just the lowest power limit. |
| **Low power** | Less power than Saver, for lighter games. |
| **Lowest power** | The least power that still runs games; heavy games stutter. |
| **Minimum** | The lowest memory speed. **Light only**: heavier games drop to a few frames. |

The names mean the same as on [CPU](cpu.md#built-in-modes); Efficient, Lowest power and Minimum are GPU-only. A mode that would come out the same as another is left out, and modes below Saver need clock locks. Modes set the fan to **Card decides**.

## Measure this card

**Measure each mode's speed** (in the **Built-in modes** panel) finds the lowest voltage and fastest clock your card really holds, so Efficient, Saver and the lower modes use real numbers instead of the driver's table ("Estimated from the driver's table" until then).

- Shown when Deck runs as administrator, the card has clock locks and the modes aren't hidden.
- Takes about three minutes. Close games first; the screen may flicker once. It never runs the card above stock.
- Afterwards a summary shows each mode before and after, and your profile is restored.
- Results are saved per card and driver. Measure again after a driver update.

## The profile editor

Click **New profile**, a pencil or **Edit profile**. The header holds **Back to GPU**, the icon, **Name** and **Shortcut key**, and two tabs: **Tuning & curve** and **Fan**. A built-in mode shows only **Mode settings**, with **Copy to my profiles to change it**.

**Measured on the card now** at the top shows power, clocks, temperature, fan and load every second. A new profile can start from a mode with **Start from**.

| Button | What it does |
|---|---|
| **Apply temporarily** | Puts the settings on the card without saving. Test in a game. |
| **Cancel** / **Discard changes** | Closes the editor. After a test it reads **Cancel and restore settings** and puts back what was on the card. |
| **Save profile** (**Save and apply profile** for the active one) | Saves. After trying a different profile it reads **Save profile and restore settings**. |
| **Back to GPU** | With unsaved edits asks **Discard your changes?** (**Keep editing** or **Discard changes**). |

Under **⋯** are **Desktop shortcut**, **Start menu** and **Lighting color** (see [Lighting](lighting.md)).

### Tuning & curve

A dot marks a setting that differs from the card's own; its undo arrow resets that one.

| Setting | What it does | Default |
|---|---|---|
| **Power limit** | How much power the card may draw, in percent and watts. The easiest way to a cooler, quieter card; many cards lose only a few percent at 80 %. | 100 % |
| **Temperature limit** | The card slows down to stay under it. | **Card's own** |
| **Highest speed** | The fastest the chip may run. Capping the top saves a lot of power for few frames, and goes below the lowest power limit. | **No limit** |
| **Lowest speed** | After **Also set a lowest speed**: keeps the card above it. | **Card decides** |
| **Adjust speed by** | **One offset** or **Voltage curve**. | One offset |
| **Speed adjustment** | Adds or removes MHz at every point of the boost curve. Raise in 15 to 30 MHz steps and test. | 0 MHz |
| **Voltage boost** | Lets the card use its top voltage steps (0 to 100 %). Helps an overclock hold; more heat. | None |
| **Memory speed** | **Card decides**, or the fixed steps the card offers. Slower memory saves a lot at the desktop but slows games. | Card decides |
| **Memory speed adjustment** | Adds MHz to the memory clock. Too high often lowers FPS, so benchmark each step. | 0 MHz |

A line under the speed settings says the fastest the card will run with them and which setting decides it.

When a curve has a flat part and no **Highest speed**, Deck adds a clock cap at the flat part, so a warm card can't climb back to high voltage. You don't need to do anything.

### Fan

| Choice | What it does |
|---|---|
| **Card decides** | The driver's own fan curve. |
| **Quiet** | 30 % at 40 °C rising to 100 % at 90 °C. |
| **Cool** | 40 % at 30 °C rising to 100 % at 85 °C. |
| **Fixed** | One speed. |
| **My curve** | Your own curve (drag points, or use the keyboard as on [Fans](fans.md#the-curves-tab)). |

Deck never goes below the card's minimum fan speed, and gives the fan 100 % at 85 °C or when the temperature can't be read, until the card is back at 80 °C. The driver takes the fan back when Deck quits. Case and CPU fans are on [Fans](fans.md).

## The voltage curve editor

Choose **Voltage curve** under **Adjust speed by**. The graph shows the clock at each voltage. Undervolting means the same clock at a lower voltage: the same frames with less heat and noise.

Gray is the stock curve, blue is yours, red is your **Highest speed**, orange is where the card is now, green is a locked point. The curve never falls to the right, as in Afterburner.

| Action | How |
|---|---|
| Move a point | Drag it |
| Select a range | Shift+drag |
| Move the whole curve | Ctrl+drag |
| Bend the neighbors along | Alt+drag |
| Add or remove a point | Ctrl+click |
| Nudge | Up / Down: 15 MHz (Shift 1 MHz, Ctrl 100 MHz) |
| Lock the card to a point | L, or **Lock point** (**Unlock** releases it) |
| Flatten from a point | Ctrl+F |
| Reset the curve | Ctrl+D |
| Undo / redo | Ctrl+Z / Ctrl+Y |

Click the graph first so keys reach it. **Curve tools** above the graph:

- **Undervolt: keep** a clock **MHz from** a voltage up, then **Apply to the curve**: the quickest undervolt (Afterburner's flat-line trick). A common start is your usual game clock at 850 to 900 mV.
- **Flatten from that voltage**: keeps the clock the curve already has at that voltage, from there up.
- **Move the whole curve by** a number of MHz.
- **Reset the curve**.

**Back to the card's own curve** drops the curve completely. A locked point holds that clock on the desktop too, so the card runs warmer.

## The Sensors tab

- Tiles for **Load**, **Temperature** (with **Normal**, **Warm** or **Hot**: warm from 75 °C, hot from 85 °C) and **Power**, and a chart of the last minute.
- **Clock & limits**: core clock, what holds it back and **Power limit** in watts and percent of factory.
- The card's name and driver, **Memory**, **Fan** (marked **Deck** or **Driver**), **Voltage**, **Video memory** and **PCIe link** (lower while idle is normal).
- **Asked and measured**: the power limit you asked for next to what the card reports.

## Settings for GPU profiles

**Profile when Deck starts** (bottom of **Your profiles**) is applied when Deck starts with Windows, because card settings reset at every restart. Default: **None (leave the card alone)**. After an unexpected restart an overclocked profile is skipped.

Shortcut keys, the switch notice and shortcut repair are shared with the CPU in **Settings › CPU and GPU** (see [CPU](cpu.md#settings-for-cpu-profiles)).

## MSI Afterburner

**Import from Afterburner…** lists Afterburner's five profiles and copies their settings, curves and Ctrl+Alt hotkeys, optionally the startup profile (**Apply at startup**) and the overlay items. Afterburner's files are not changed.

**Stop Afterburner from tuning…** backs up Afterburner's settings, then clears its startup profile, hotkeys and fan control. **Restore Afterburner's settings** puts them back.

You can uninstall Afterburner once you have imported what you need. If its uninstaller offers to remove RivaTuner Statistics Server, say no: the [Performance overlay](overlay.md) uses it. Never let both programs tune the card at once.

## Auto undervolt

**Find my undervolt** on the **Auto undervolt** card finds the lowest voltage at which your card still holds its stock clock.

1. Close games and MSI Afterburner. Deck must run as administrator. The confirmation says how long it takes (about 20 minutes).
2. Deck finds the stock clock, then flattens the curve 25 mV lower each step under load. A driver reset or stalled load counts as unstable.
3. The card shows the step being tested and **Stop**. A game, 87 °C on the card, Afterburner starting or Deck closing also stop it.
4. It always ends at stock or at the result: a stable result is saved as a new profile and switched on.

If the PC restarts during a step, the card starts at stock and the card shows **PC restarted** with a button to save the lowest stable step as a profile.

## Crashes this week

A profile or mode shows a **Crashed … this week** chip (amber from twice) when the PC, a game or the graphics driver crashed while it was on. The tooltip lists what crashed. Hard resets are always counted; game crashes and driver resets need **Record Windows crash reports** in [Diagnostics › Crashes](crashes.md#profiles). Deck never turns a profile off for this. The same chip shows on [CPU](cpu.md).

## Crash guard and applying again

- After a restart during an overclock, the next start uses factory settings (**Overclock held back**). Lower-power profiles and undervolts don't count as overclocks.
- After a driver reset Deck applies the profile again once; after sleep, about five seconds after waking.
- Fan settings are sent again every ten seconds. Clock locks are released when Deck quits, on **Reset GPU** and after a crash.
- Switching profiles inside a game is safe: no driver reset.

## Recommended setups

- **Most people:** **Efficient** or **Saver** for gaming (run **Measure each mode's speed** once), **Balanced** for the card as sold, **Quiet** for less noise.
- **A simple undervolt:** with the voltage curve, pick your usual game clock at 850 to 900 mV, use **Undervolt: keep** with **Apply to the curve**, then **Apply temporarily**, play a while, then save. Or let [Auto undervolt](#auto-undervolt) do it.
- **A small overclock:** raise **Speed adjustment** in 15 to 30 MHz steps with **Apply temporarily**, then memory the same way. Step back from the first unstable value.
- **Laptops:** power-lowering modes help most; **Highest speed** and **Memory speed** work where the power limit is locked.

## Troubleshooting

**There is no GPU page.** It only appears for an NVIDIA card. Check that the NVIDIA driver is installed and Deck runs as administrator.

**The page says "GPU asleep".** The card is powered down, common on laptops with switchable graphics. It wakes when a program uses it.

**Some controls are missing.** The card or driver doesn't offer them.

**Settings are gone after a restart.** Choose **Profile when Deck starts**. An overclocked profile is skipped after an unexpected restart.

**My fan speed isn't what I set.** The card's minimum fan speed and the 85 °C safety rule win.

**Afterburner and Deck disagree.** Use **Stop Afterburner from tuning…** or close Afterburner.

**A game crashes after an undervolt.** Raise the voltage or lower the clock of the flat part, and test with **Apply temporarily**.

## FAQ

**Is it safe with anti-cheat?** Deck talks to NVIDIA's driver, as Afterburner does, and never touches a game. See [FAQ](faq.md).

**Can this damage my card?** Everything stays inside NVIDIA's own limits. An overclock carries Afterburner's risk: instability, not usually damage.

**What happens when Deck quits or crashes?** The driver takes the fan back within seconds and locked clocks are released. Other settings stay until the PC restarts or you press **Reset GPU**.

**Do profiles survive a driver update?** Yes. Measure the card again, because voltage tables can change.

**Can I use a profile only for some games?** Yes, in [Game profiles](gaming.md).

**What does "hardware held" mean?** See [CPU › FAQ](cpu.md#faq).
