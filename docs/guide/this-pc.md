Where to find it: PC status › This PC

# This PC

Your PC's parts at a glance, how it did this week, and what Deck can and cannot control on it.

It is one page with no tabs, and nothing on it changes your PC. Check it first when a feature is missing or grayed out: it says whether your hardware or Deck is the limit. The support report is in [Settings › About](settings.md#support-report).

## Order of the page

1. **Device specifications**
2. **This week** beside **What Deck controls**
3. **PCIe links**
4. **Latency test**

## Device specifications

Processor, graphics, memory and motherboard (or laptop) are tiles at the top. Each fixed drive is a tile with its free space and a bar, with a **Low** chip when less than a tenth is free. The other facts are rows in two columns:

| Row | What it shows |
|---|---|
| **Motherboard** (or **Laptop**) | Maker and model. |
| **Processor** | The CPU name. |
| **Graphics** | Each graphics adapter with its memory, and the NVIDIA driver version when Deck can read it. |
| **Memory** | Size and speed. An amber line means it runs below its rated speed: turn on XMP (Intel) or EXPO (AMD) in the BIOS. |
| **Storage** | Total size and the free space on each drive. If Deck shows a parts list it read earlier, the line says when. |
| **Main display** (and **Display** for each other monitor) | Name, resolution and refresh rate. If the monitor can run faster than it does now, the row says so with **Open Display**. |
| **Windows** | Edition, version and build. |
| **BIOS** | Maker, version and date. |
| **Running for** | Time since the last restart. |

**Copy specs** puts the list on the clipboard as plain text, ready for a forum post or a support chat.

Sizes are decimal (1 GB is 1,000,000,000 bytes, as drive makers count), the same figures as Disk space and Drive health. Windows Explorer counts in binary, so its numbers read about 7 % lower.

## This week

Five tiles about the last seven days. The summary refreshes once a day. A chip in the corner says **Fine**, **Check** or **Act now**; hover a tile for the full sentence, click it to open the details.

| Tile | What it tells you | Opens |
|---|---|---|
| **Temperatures** | The highest CPU and GPU temperature, with its band: **Normal**, **Warm** or **Hot** (warm from 80 °C on a processor and 75 °C on a graphics card, hot from 90 °C and 85 °C, the same bands as everywhere in Deck). | [Sensors](sensors.md) |
| **Drives** | **All healthy**, or which drives need attention (caution or bad health, or worse this week). | [Drive health](drives.md) |
| **Disk space** | The drive with the least free space, and when it was checked. | Disk space |
| **Alerts** | How many of your sensor alerts went off. | [Sensors](sensors.md) › Alerts |
| **Deck** | Deck's own crashes and unexpected exits. | [Settings › About](settings.md#support-report) |

Drive comparisons start after the first saved check; Deck never guesses missing history.

## What Deck controls

One tile per part with a short detail and a chip. The count in the corner says how many parts work. Hover a tile for the reason and the way Deck reads and controls it (for example NVIDIA's graphics library or your laptop maker's interface).

| Chip | Meaning |
|---|---|
| **Works** | Deck can control it. |
| **Partly** | Some of it works; the detail says what. |
| **Read only** | Deck can read it but not change it. |
| **Not available** | Deck does not control this on your PC. |
| **Not checked** | Deck has not checked it yet. |

**Not available** and **Not checked** are gray: information, not warnings.

The tiles you may see:

- **Processor.** Intel desktops: turbo and clock presets, and the multiplier on unlocked models. Intel laptops: the presets work, but power limits are often locked by the laptop. AMD: the presets work; AMD power limits and Curve Optimizer are not in Deck yet. Other processors: presets through the Windows power plan.
- **Graphics card.** NVIDIA: clocks, power limit, fan and overlay values work. AMD and Intel graphics: Deck reads temperature and load; tuning is not in Deck yet.
- **Handheld**, on a recognized handheld PC: pages fit the screen and work by touch, built-in controls show on [Controller](controller.md) when Windows lists them as a controller, and Windows' power mode works. The maker's power-limit and fan modes are not in Deck yet.
- **Laptop controls**, on a laptop: fan speed through HP's BIOS works on Omen and Victus. For other makers the tile says Deck can't use their controls yet.
- **Fans**: the number of fans and the fan chip. **Works** when control has been checked on this board, **Partly** when Deck can read the fans but control is not checked yet.
- **Board lighting**, **RAM lighting** and **Cooler display**: whether Deck found them.
- **Administrator**: **Can change hardware** when Deck runs as administrator.

### Administrator access

Without administrator, Deck can only read the hardware. The **Administrator** tile then shows **Restart as administrator**: Windows asks once, then Deck creates its startup task and restarts with the rights. The installer normally does this for you. See [Why Deck needs administrator](getting-started.md#why-deck-needs-administrator).

## PCIe links

The link of the graphics card and of each NVMe drive (such as "PCIe Gen4 x4"), the most it supports, and a chip: **Full speed**, **Lowered while idle**, **Below its maximum** or **Below max under load**. Cards lower their link while idle, so check again under load; some M.2 slots share lanes. The card is left out when Windows reports no link.

## Latency test

**Start test** measures, inside Deck's window, the rate the window really redraws at (**Window refresh**, with missed frames) and your mouse's report rate while you move it over the box (**Mouse reports**). It stops when you press **Stop**, leave the page or hide the window. Windows can hold a window below the display's rate when it is behind others or on battery saver. The test touches no game and installs no hook.

## Troubleshooting

**The hardware tiles are missing.** Deck is not running as administrator, or the hardware engine is still starting. Press **Restart as administrator** if it is offered, or wait a few seconds.

**Memory says it runs below its rated speed, but XMP is on.** Some memory reports its rated speed only for the standard (JEDEC) profile. If the row shows your XMP speed, all is well.

**The Drives tile says "Not checked yet".** Open [Drive health](drives.md) once; the tile fills in at the next daily refresh.

## FAQ

**Does the page change anything?** No. It only reads hardware information and Deck's own records.

**Will Deck support my laptop's fan modes?** The **What Deck controls** card shows what is covered today. If your laptop shows **Not available**, a support report from [Settings › About](settings.md#support-report) helps to add it.

**Is Deck itself healthy?** See [Diagnostics › Crashes](crashes.md#deck-health).
