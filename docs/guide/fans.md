Where to find it: Hardware › Fans

# Fans

Control the case, CPU and pump fans on your motherboard with fixed speeds, temperature curves and quiet hours.

The page has three tabs: **Speeds**, **Curves** and **Calibrate & extras**. Graphics card fans are set on [GPU](gpu.md) (the **Hardware › GPU** link at the top).

The most important thing to know: the motherboard takes the fans back whenever Deck quits, crashes or is ended. See [What happens if Deck crashes or quits](#what-happens-if-deck-crashes-or-quits).

## What you need

- Deck running as administrator: fan control uses a small signed driver (PawnIO). Without it the page shows **Needs administrator** with **Restart as administrator**. See [Why Deck needs administrator](getting-started.md#why-deck-needs-administrator).
- A supported fan chip: Nuvoton NCT668x and NCT679x, ITE chips (many Gigabyte boards and others), and HP Omen and Victus laptop fans through the BIOS. Those chips are in most MSI, ASUS, Gigabyte and ASRock boards. Otherwise the page says **Fan control isn't supported on this PC yet**, with **Copy report** and **Open GitHub issues** so support can be added.
- One Deck controls the hardware per PC. If a second Windows user runs Deck, it only reads, and takes over a few seconds after the first quits.

A board can be in one of three states:

| State | What you see |
|---|---|
| Verified | Normal controls. |
| **Not verified on this board** | Deck reads the fans but controls them only after you turn on **Unverified fan control**. Most boards with that chip work the same. If fans act oddly, turn it off or quit Deck. |
| **Read-only fan chip** | Live speeds only, with the reason behind **?** (for example MSI 800-series boards with the NCT6687DR chip, or another user's Deck owning the hardware). |

## How fan control works

Each fan has a **Mode**:

| Mode | What the fan does |
|---|---|
| **Motherboard decides** | The BIOS controls it. The default, and what every fan returns to when Deck lets go. |
| **Fixed 30%**, **Fixed 50%**, **Fixed 75%**, **Fixed 100%** | A constant speed. Suits pumps and testing. |
| A curve (**Silent**, **Balanced**, **Performance** or your own) | Speed follows a temperature curve. |
| **Trigger rule (two speeds)** | One speed above a hot temperature, a lower one below a cool temperature, the last speed kept in between. |
| Highest, lowest or average of two curves | See [Combine two curves](#combine-two-curves-and-follow-another-fan). |
| Follows another fan | Copies another fan's speed plus a difference. |

Curves and trigger rules read a temperature, set in **Follows**: **CPU**, **GPU**, **CPU/GPU hotter**, **CPU/GPU average**, or a **Board:** sensor. If that sensor disappears, the fan shows **Temperature source lost** and runs on the motherboard until you choose another (**Follow instead**).

Edits are a draft: nothing reaches the fans until you press **Apply hardware changes** in the bar at the bottom. **Discard pending changes** drops them. A **Saved** mark confirms it; **Not saved** gives the reason and changes nothing. Changes from the tray, [Game profiles](gaming.md) and the [Deck bar](game-bar.md) apply at once.

The default curves (°C: fan %):

| Curve | Points |
|---|---|
| **Silent** | 30: 25, 50: 30, 70: 45, 85: 70, 95: 100 |
| **Balanced** | 30: 30, 50: 40, 65: 60, 80: 85, 90: 100 |
| **Performance** | 30: 40, 45: 55, 60: 75, 75: 100, 100: 100 |

Curve points are always in °C, even when Deck shows Fahrenheit elsewhere.

## The Speeds tab

**Fan settings** (or **Fan speeds** when Deck can only read):

- **All fans** sets every fan to one mode. It says **Mixed** when fans differ.
- One row per fan: its name, live **RPM**, the signal Deck sends ("25% signal", not a measured speed) and the last 60 seconds of speed. The arrow folds the fan's settings. Click the name to open its curve.
- Per fan: **Mode**, **Follows**, **Ramp up (%/s)** and **Ramp down (%/s)** (how fast the signal may rise or fall; 0 is off; **Reset to default** clears both), and the trigger rule's fields.
- Headers that read 0 RPM are hidden. **Show unconnected fans** lists them with "No speed: empty header or no speed wire".

**Try for 60 s** runs only your pending changes for a minute, with **Keep** and **Restore now**. Without an answer, or if Deck closes, the saved settings come back.

**Safeguards** sums up the safety rules: **Motherboard on quit**, **Full speed when hot**, **Sensor lost: full speed**. **Asked and measured** compares each fixed speed with what the chip reports.

A line under the tabs names a running vendor program (iCUE, Armoury Crate and others) that can reset Deck's fan speeds, with **Pause** for this session. **Start again**, or a restart, brings it back. Pause is refused while a game runs. While an anti-cheat holds the fans, the page says "BIOS control since" and the time.

## The Curves tab

The chosen curve as a large graph: temperature across, fan speed up. The marker shows the temperature now and the speed it gives. Chips above the graph pick the curve; the fan chips show which fans use it, and **Fans on curve** turns the curve on or off per fan. Under the graph: **Lowest speed**, **Half speed from**, **Full speed from** and **Curve points**.

Editing:

- Mouse: drag a point, click to add one, right-click to remove one.
- Touch: tap to add, drag to move, press and hold to remove.
- Keyboard: Tab into the graph and again to pick a point, arrows move it (Shift: 5 at a time), Delete removes, Insert adds, Esc lets go.

The **⋯** button has **Save as a new curve…**, **Rename…**, **Put Silent, Balanced and Performance back** and **Delete this curve…** (fans that use it go back to the motherboard).

### Slow-down behavior

These rules only delay slowing down; fans speed up at once.

| Setting | What it does | Default |
|---|---|---|
| **Slow down only after the temperature drops** | Fans slow only after the temperature fell this many degrees (0 to 10 °C). | 2 °C |
| **Wait between slow-downs** | The wait before slowing again (0 to 30 s), so short loads don't make fans pulse. | 3 s |

**Ignore short spikes** sets 4 °C and 15 s; **Reset to 2 °C and 3 s** goes back.

### Quiet hours

**Quiet at night** (off by default) caps fans on a curve at night:

| Setting | Default |
|---|---|
| **From** / **to** | 23:00 to 07:00 |
| **Highest overnight speed** | 45 % (25 to 90 %) |
| **Restore full cooling at** | 70 °C (50 to 85 °C) |

Fixed speeds, followers and motherboard fans are not capped. An unknown temperature never caps.

### Stop case fans

**Stop below (0 = never)**: case fans on a curve stop below this temperature (0 to 70 °C) and restart 3 °C above it, or at once when the CPU reaches 85 °C. Only fans named as case fans ("system", "chassis" or "case") can stop; CPU, pump and unnamed headers never do. Test that your fans restart before relying on it.

### Preview a curve

Plays made-up temperatures through your draft curve and all the rules, and plots the result. Nothing is sent to the fans. Pick a fan on a curve and a **Temperature story** (**Steady climb from idle to hot**, **Short spike while idle**, **Sensor lost for 20 seconds**, **Hot, then cooling down**), then **Run preview**.

## The Calibrate & extras tab

### Calibrate fans

**Measure fan range** (or **Measure again**) on a fan, or **Measure all fans**, finds each fan's real range:

- The fan steps from 100 % down to 20 % while Deck reads the RPM. Case fans also go down to 0 % to find where they stop and start again. Under 2 minutes per fan.
- The result reads like "Stops 15%, starts 25%" with the top speed and date. **Stop measuring** ends it.
- It won't start while a game runs, if the CPU is 70 °C or warmer, or if a temperature is missing. It stops at once at 80 °C on the CPU or 85 °C on the GPU, and the fan returns to its own setting.

Afterwards, if a fan turns much slower than measured for two minutes, Windows shows "<fan> looks slower than before". Clean it and measure again.

### Noise test

Tune fans by ear. The **Noise** card lists each fan as **Heard from N %** or **Not tested**.

1. Press **Noise test** (or **Test again**) on a fan. It steps from 20 % to 100 % in 10 % steps.
2. Press **Louder** for the next step and **I hear it** at the first step you can hear. **Stop** or Esc ends it.
3. Turn on **Keep curves under N %** for that fan and press **Apply hardware changes**. Its curves stay one step below what you heard, until the fan's temperature reaches 80 °C.

No answer for 60 seconds, a game, heat or Deck closing end the test. **Forget** clears the result.

### Combine two curves and follow another fan

- **Combine two curves**: run a fan at the highest, lowest or average of two curves, then **Set curves for** that fan. For example, the highest of Silent and Performance.
- **Follow another fan**: run a fan like another one plus a **Speed difference** (−30 to +30 %), then **Set following rule for** that fan. Two fans that follow each other go back to the motherboard.

Both are pending changes: press **Apply hardware changes**.

## Safety rules

Deck applies these to every fan it drives, fixed speeds included:

- 100 % when the CPU reaches 85 °C, the fan's own source reaches 90 °C, or the source has no data.
- Never below 20 %, except a case fan you let stop.
- Speeds fall by at most 4 points a second unless you set **Ramp down**. Heat and missing data skip ramp limits and quiet hours.
- For the first 20 seconds after Deck starts, a fan with no temperature stays with the motherboard.
- Before the first change, Deck saves the fan chip's original values. After a power cut they are restored first.

## What happens if Deck crashes or quits

| Situation | What happens |
|---|---|
| You quit Deck, or Windows shuts down, restarts or signs out | The motherboard gets the fans back (and the driver the GPU fan). |
| Deck crashes | The crash handler hands the fans back first. |
| Deck is ended from Task Manager | A watchdog (a second `deck.exe`) hands the fans back within seconds and starts Deck again, hidden. |
| Three unexpected ends in ten minutes | The watchdog stops restarting. Deck starts with the fans on the motherboard until you turn control on again. |
| Setup, update or uninstall | The fans go back first. |
| Power cut while Deck held a speed | The next start restores the chip's original values. |

To hand every fan back by hand, run `deck.exe --release-fans` as administrator.

## What happens with anti-cheat

Deck never touches games. The only thing that matters is the PawnIO driver Deck uses for fans, CPU limits and motherboard sensors.

- While FACEIT (the one anti-cheat known to refuse this driver) runs, Deck hands the fans back to the motherboard, stops using the driver and says why. It resumes when FACEIT closes.
- Windows can't unload the driver while it runs. If an anti-cheat still refuses, uninstalling Deck removes the driver.
- GPU tuning doesn't use this driver.

## Recommended setups

- **Most people:** CPU and case fans on **Balanced**, case fans following **CPU/GPU hotter**. Leave anything you're unsure about on **Motherboard decides**.
- **Quiet PC:** **Silent**, **Ignore short spikes** and **Quiet at night**. Keep the top of the curve at 100 %. Run the [noise test](#noise-test) and keep curves under what you can hear.
- **Cooling first:** **Performance** for case fans, or the highest of Silent and Performance.
- **Water cooling:** give the pump **Fixed 100%** or leave it on the motherboard.
- **HP laptops:** Deck drives both fans through the BIOS and never asks for less than about 1,800 RPM.

Always press **Apply hardware changes**, then watch [Sensors](sensors.md) under load for a while.

## Troubleshooting

**"Fan control isn't supported on this PC yet".** Deck found no fan chip it knows (on a laptop, the maker's controller runs the fans). They keep working as before. Use **Copy report** and **Open GitHub issues** to ask for support.

**The page is read-only.** See the board states under [What you need](#what-you-need). Another user's Deck may own the hardware, or an anti-cheat is running.

**A fan shows "Unavailable" or "Not measured".** Nothing is plugged in, the fan has no speed wire, or it is stopped on purpose.

**I changed a mode and nothing happened.** Press **Apply hardware changes**.

**The fan is faster than my curve.** A safety rule is on (hot CPU or source, or no data), a test is running, or **Ramp up** is still rising. Check the source in **Follows**.

**Fans surge up and down.** Press **Ignore short spikes**, or raise **Slow down only after the temperature drops**.

**Fans rattle at low speed.** Raise the low end of the curve. **Measure fan range** shows where the fan stops and starts.

**Calibration won't start.** Close the game, let the CPU cool below 70 °C, and check that the temperatures show.

**My other fan software disagrees.** Two programs writing the same chip fight. Close the other tool, or **Pause** it from the line under the tabs.

## FAQ

**Will a crash leave my fans stuck at a low speed?** No. See [What happens if Deck crashes or quits](#what-happens-if-deck-crashes-or-quits).

**Can a low curve damage my PC?** A CPU or pump fan set too low can overheat the CPU, which is why the safety rules give 100 % when hot or without data. Keep the top of your curves at 100 %.

**Do fans keep their setting after a restart?** Deck applies your modes when it starts. Until then the motherboard controls the fans.

**Does Deck change my BIOS?** No. It writes the fan chip's live values and saves the originals first.

**How do I undo everything?** Set fans to **Motherboard decides** and press **Apply hardware changes**, or quit Deck.

**Where are fan settings stored?** In Deck's settings folder under `hardware`. If another program edits them, Deck keeps fans on the motherboard until you press **Apply them** in the notice.
