Where to find it: PC status › Sensors

# Sensors

See every temperature, clock, load, power and fan sensor on your PC, now and over time. This page only reads; it changes nothing.

Three tabs: **All sensors** (opens first), **Graphs** and **Alerts**. Deck remembers the last one you used.

Related: [Performance overlay](overlay.md) (sensors over a game), [Alerts](alerts.md) (alert rules and notifications), [Drive health](drives.md), [This PC](this-pc.md).

## What you need

- CPU temperature and power, per-core clocks and the motherboard's sensors need administrator. Without it the page shows **Sensors need administrator** with **Restart as administrator**. See [Getting started](getting-started.md#why-deck-needs-administrator).
- The **Frametimes** graph needs RivaTuner Statistics Server. Deck can install it from [Performance overlay](overlay.md).
- The sensors depend on your PC. The page shows what is there and hides the rest.

## The All sensors tab

**Left:** one button per device (CPU, GPU, Motherboard, Memory, each drive and network adapter) with how hot and how busy it is. **Find a sensor…** searches every device at once; Esc clears it.

**Right:** the chosen device's sensors, grouped under **Temperatures**, **Power**, **Load**, **Voltages** and so on, with **Current**, **Lowest**, **Average** and **Highest**.

- Per-core and per-fan sensors are one table, **Cores** or **Fans**. **Current** and **Range** choose the figures.
- Temperatures get a **Normal**, **Warm** or **Hot** chip:

| Part | Warm from | Hot from |
| --- | --- | --- |
| CPU | 80 °C | 90 °C |
| GPU | 75 °C | 85 °C |
| Drive | 55 °C | 70 °C |
| Motherboard and others | 85 °C | 95 °C |

- Fan outputs Deck can change are marked **Controllable** (change them on [Fans](fans.md)).
- A sensor that stopped updating says how long ago it was last seen. A missing value is a dash, never a wrong number.
- **Reset statistics** starts lowest, average and highest again from now. Press it before a test so earlier peaks don't hide the result.
- **Where these sensors come from** (a fold) names the program behind each sensor and how fresh it is.

### Heat check

Above the table, **Heat check** points out what the CPU and GPU sensors suggest:

- **Seen**: the hardware reported a limit was reached (heat, power or clock).
- **Possible**: a pattern that often means heat is holding the part back, for example a clock well below its peak at high load near the temperature limit. Not proof.
- **Not enough data**: the temperature itself is missing.

When nothing stands out it says **Nothing unusual: temperatures and clocks look steady**. Your alert limits are not hardware limits.

### Where the numbers come from

| Device | Source | Good to know |
| --- | --- | --- |
| CPU | Its own sensors and energy counters, through Deck's hardware driver | Package temperature is the one fans and alerts use. AMD reports one package value, not one per core. Power is the CPU's own estimate. Voltage is what the CPU asks for. |
| GPU | The graphics driver (NVIDIA or AMD) | GPU fan is the requested percent, not RPM. Graphics from other makers may show fewer sensors. |
| Cooler (AIO) | [liquidctl](https://github.com/liquidctl/liquidctl), if you install it in `C:\Program Files\liquidctl\` | Pump, liquid temperature and the cooler's fans. Close the maker's app if the cooler doesn't answer. |
| Motherboard | The board's monitoring chip, through the driver | Names come from the chip. Voltages can be off by a few percent. |
| Memory, drives, network | Windows | Not every drive reports a temperature. |

Everything is read on your PC; nothing is sent anywhere.

## The Graphs tab

Live graphs, refreshed every second. **Charts** and **Table** switch between the graphs and a table of the same five minutes (one row per second). **Customize this page** moves, resizes, hides and shows panels.

| Panel | What it shows |
| --- | --- |
| **Temperatures** | A small graph for the CPU, the GPU and each motherboard temperature. |
| Temperature · 5 min | CPU and GPU temperature, with now, min and max. |
| **Load % · 5 min** | CPU and GPU load. |
| **Power W · 5 min** | CPU package and graphics card power. Shows what a power limit or undervolt really changed. |
| **History** | A day, week or month of CPU and GPU temperature, load or power. Collected only while Deck runs. |
| **Frametimes** | Each frame's time, average FPS, 1 % and 0.1 % lows, for the game RivaTuner draws in. The lows show stutter the average hides. |
| **GPU clock MHz · this visit** | The GPU core clock since you opened the tab. |
| **Fan speeds** | One graph per fan that reports a speed. **Show unused connectors** lists the rest. |

## The Alerts tab

Temperature alerts are off by default. Changes are a draft until you press **Apply changes** (or **Discard changes**).

**Temperature alerts**

| Setting | What it does | Default |
| --- | --- | --- |
| **Temperature alerts** | A Windows notification when the CPU or GPU goes above your limit, at most every 5 minutes per part. | Off |
| **CPU above** | 60 to 105 °C. | 90 °C |
| **GPU above** | 60 to 100 °C. | 85 °C |
| **Flash lights red** | A few seconds of red on the board lights per alert. See [Lighting](lighting.md). | Off |

**Sensor logging**

| Setting | What it does | Default |
| --- | --- | --- |
| **Log to file** | Writes every sensor once a second to `monitor.csv`, which Excel opens. A new file starts at 50 MB and the latest five are kept. Rows starting with `#` mark game starts, profile changes and session summaries. | Off |
| **Slower in games** | While a game is in front, drives and idle fan chips are read every 3 seconds instead of every second. | On |
| **Open folder** | Opens the folder with `monitor.csv`. | |

Alert rules and sending alerts to your phone are on the same tab: see [Alerts](alerts.md).

## Units

**Settings › Appearance › Performance & units** chooses MHz or GHz, Mb/s or MB/s and °C or °F for every page, the phone and the overlay. Fan curves and limits you type stay in °C and MHz.

## Recommended setup

- Before and after changing a profile, fan curve or undervolt: press **Reset statistics**, run the same test, and compare **Highest** and **Average**.
- Turn on **Temperature alerts** if you tune the CPU, GPU or fans. The defaults suit most PCs.
- Turn on **Log to file** only while you investigate something.
- Gamers: use **Frametimes** to see stutter and **History** to compare a week.

## Troubleshooting

**CPU temperature or power is missing.** It needs administrator: press **Restart as administrator**. Then check the **Where these sensors come from** fold.

**An AMD CPU shows one temperature.** AMD reports one package value.

**A value shows a dash.** The device doesn't report it, or the sensor stopped. The fold says when it was last seen.

**The GPU page is missing but Sensors shows my card.** GPU tuning is NVIDIA only. Other graphics get sensors only.

**Frametimes is empty.** Start RivaTuner and a game it draws in.

**History is empty.** It only collects while Deck runs. Leave it running.

**Temperatures differ from another program.** Tools may read different sensors (package, core, board). Compare the same named sensor.

## FAQ

**Is it safe with anti-cheat?** Yes. Deck never reads a game's memory. CPU and board sensors come through Deck's signed driver; while FACEIT runs Deck stops using that driver, so those sensors pause (see [Fans](fans.md#what-happens-with-anti-cheat)).

**Does monitoring slow my game?** Very little. With **Slower in games**, the heavier sensors are read every 3 seconds during games.

**Can I see sensors over my game?** Yes, on [Performance overlay](overlay.md).

**Can I export the data?** Turn on **Log to file** and open the CSV in Excel.
