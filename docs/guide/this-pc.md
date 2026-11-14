Where to find it: PC status › This PC

# This PC

The **This PC** page shows your PC's parts at a glance, how the PC did over the last week, and what Deck can and cannot control on it.

Find it under **PC status › This PC** in the sidebar. It is one page with no tabs, and nothing on it changes your PC. The support report that used to be here is now in [Settings › About](settings.md#support-report).

Deck runs on very different machines: Intel or AMD processors, NVIDIA, AMD or Intel graphics, desktops, laptops and handhelds. Some features only exist on some of them. This page is where you can see why a feature is missing on yours.

---

## Order of the page

From top to bottom:

1. **Your PC**: the spec sheet
2. **This week**: five tiles
3. **What Deck can control here**

---

## Your PC

One row per part, with the detail that matters underneath:

| Row | What it shows |
|---|---|
| **Motherboard** (or **Laptop**) | The board's maker and model; on a laptop, the maker and model of the laptop. |
| **Processor** | The CPU name. |
| **Graphics** | Each graphics adapter with its memory, and the NVIDIA driver version when Deck can read it. |
| **Memory** | How much memory, and the speed it runs at. If the memory runs slower than its rated speed, the row says so in amber: turn on **XMP** (Intel) or **EXPO** (AMD) in the BIOS to get the full speed. |
| **Storage** | The total size of your fixed drives, and the free space on each, read live (a line says "Current readings"). If Deck is showing the parts list it read earlier, the line says when it was read and that free space may be out of date. |
| **Main display** (and **Display** for each other monitor) | Its name, resolution and refresh rate. If the monitor can run at a higher refresh rate than it does now, the row says so and offers **Open Display**, where you can change it. |
| **Windows** | The edition and version (for example Windows 11 Pro 25H2), with the build number. |
| **BIOS** | The BIOS maker and version, with its release date. |
| **Running for** | How long since the last restart. |

**Copy specs** puts the list on the clipboard as plain text, ready to paste into a forum post or a support chat.

Storage sizes are decimal (1 GB is 1,000,000,000 bytes, as drive makers count), with one decimal place, and are the same figures Disk space and Drive health show for the same drive. Windows Explorer shows binary sizes under a "GB" label, so its numbers read about 7% lower. The system drive (C:) comes first, then the other volumes by letter.

---

## This week

Five tiles about the last seven days, built from what Deck has recorded. The summary refreshes once a day. Each tile has a word in its corner (**Fine**, **Check** or **Act now**) and opens the page with the details when you click it. Hover a tile to read the full sentence behind it. Peak times use your local time and show hours and minutes, without seconds.

| Tile | What it tells you | Opens |
|---|---|---|
| **Temperatures** | The highest CPU and GPU temperature this week. **Check** from about 95 °C on a processor and 87 °C on a graphics card, where they start to slow themselves down. | [Sensors](sensors.md) › Graphs |
| **Drives** | Whether every drive is healthy, or which ones need attention (a drive in caution or bad health, or one that got worse this week). | [Drive health](drives.md) |
| **Disk space** | The drive with the least free space and that space, with the day and time it was checked (a daily snapshot). **Check** when less than a tenth is free. | Disk space |
| **Sensor alerts** | How many of your own sensor warnings went off this week. | [Sensors](sensors.md) › Alerts |
| **Deck** | Deck's own crashes and unexpected exits (forced closes or power loss count too). | [Settings › About](settings.md#support-report) |

Drive comparisons start after the first saved check: Deck never guesses missing history.

---

## What Deck can control here

One list of what Deck can do on this PC, each row with a chip:

| Chip | Meaning |
|---|---|
| **Works** | Deck can control it. |
| **Partly** | Some of it works; the sentence says what. |
| **Read only** | Deck can read it but not change it. |
| **Not available** | Deck does not control this on your PC. |
| **Not checked** | Deck has not checked it yet. |

**Not available** and **Not checked** use neutral grey chips; they are information, not warnings.

The rows you may see:

- **Processor.** On Intel desktops: turbo and clock presets, and the multiplier on unlocked models. On Intel laptops: turbo and clock presets work, but power limits are often locked by the laptop. On AMD: turbo and clock presets work; AMD power limits and Curve Optimizer are not in Deck yet. Any other processor gets the presets that go through Windows' power plan.
- **Each graphics adapter** by name. NVIDIA: clocks, power limit, fan and overlay readings work. AMD and Intel graphics (card or built-in): Deck reads temperature and load; tuning them is not in Deck yet.
- **Handheld**, on a recognised handheld PC: Deck's pages fit the screen and work by touch, its built-in controls show on the [Controller](controller.md) page when Windows lists them as a controller, and Windows' power mode works. The maker's own power-limit and fan modes are not in Deck yet.
- **Laptop controls**, on a laptop: whether a maker's control interface answered. Fan speed through HP's BIOS works on HP Omen and Victus models; for other makers Deck says plainly that it cannot use their controls yet.
- **Fans**: how many fans and the fan chip. **Works** only when fan control has been checked on this board; **Partly** when Deck can read the fans but control is not yet checked on this board.
- **Board lighting**, **RAM lighting** and **Cooler display**: whether Deck can control them.
- **Admin rights**: whether Deck runs with administrator rights. Without them Deck can only read.

### Administrator access

If the hardware rows are replaced by a card titled **Hardware controls need administrator access**, press **Enable administrator access**. Windows asks for permission once, Deck creates a start-up task and restarts itself with those rights. The installer does this for you, so you usually only see it if you launched Deck some other way. See [Getting started](getting-started.md).

Why admin rights? Reading fan speeds, CPU temperature, drive health and lighting means talking to hardware, which Windows only allows for administrators.

---

## Recommended setup

- Check this page first when a feature is greyed out or missing: it says whether your hardware or Deck is the limit.
- If **Memory** or **Main display** shows an amber line, fix it: both are free speed you already paid for.
- Laptops and handhelds: expect **Partly** and **Not available** on the maker's own controls. This is honest information, not a fault.

---

## Troubleshooting

**The hardware rows are missing.** Deck is not running with administrator rights, or the hardware engine is still starting. Press **Enable administrator access** if it is offered, or wait a few seconds.

**Memory says it runs below its rated speed, but I turned on XMP.** Some memory reports its rated speed only for the standard (JEDEC) profile. If the row shows your XMP speed, all is well; the amber line only appears when the memory runs slower than what it reports as rated.

**The Drives tile says "Not checked yet".** Open [Drive health](drives.md) once; the tile fills in at the next daily refresh.

---

## FAQ

**Does the page change anything on my PC?** No. It only reads hardware information and Deck's own records.

**Will Deck get support for my laptop's fan modes?** The "What Deck can control here" list tells you what is covered today. If your laptop shows **Not available**, a support report from [Settings › About](settings.md#support-report) is what helps to add it.

**Does Deck work with anti-cheat?** Yes. Deck never injects into games or reads their memory.
