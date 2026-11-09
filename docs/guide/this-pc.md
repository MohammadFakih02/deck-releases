# This PC

The **This PC** page tells you what Deck found in your computer, and, in plain words, what Deck can and cannot control on it. It also holds a weekly health summary and a **support report** you can copy or save when you need help.

Find it under **Watch > This PC** in the sidebar. It is one page with no tabs. Nothing on this page changes your PC, apart from the optional lights test that can be added to a saved report.

Deck runs on very different machines: Intel or AMD processors, NVIDIA, AMD or Intel graphics, desktops, laptops and handhelds. Some features only exist on some of them. This page is where you can see why a feature is missing on yours.

---

## Order of the page

From top to bottom:

1. **PC health this week**
2. **What Deck can do here**
3. **Hardware and access**
4. **Support report**

If Deck is not running with administrator rights, the hardware section is replaced by a **One-time set up** card (see below), but the first, second and last panels still show.

---

## PC health this week

A short list of sentences about the last seven days, built from what Deck has recorded. It refreshes once a day, and drive comparisons start after the first check.

| Line | What it tells you |
|---|---|
| **CPU and GPU temperature** | The highest temperature recorded in the last week and the ten-minute window it happened in. If none was recorded it tells you to open Sensors. |
| **Each drive** | The drive's latest saved health, and whether it has got worse since the first check this week. Life remaining changes are mentioned. |
| **Each volume** | Free space now, and how much more or less than at the first check this week. |
| **Sensor alerts** | How many sensor alerts the retained log recorded (older entries may have rotated out). |
| **Crashes** | How many Deck thread crashes, crash reports and unclean exits (forced closes or power loss) are in the available records. These can overlap. |

Each line has a button that jumps to where you can look further: **Sensors**, **Drives**, **Disk space** or **Support report**. See [Sensors](sensors.md), [Drives](drives.md).

If a line says it cannot compare yet, that is because Deck has no earlier saved check: it never guesses missing history.

---

## What Deck can do here

A table that describes the machine and what Deck can do on it. The first line names the kind of machine (**Laptop** or **Desktop**, the maker and model, and the processor family if known).

Each row has an area, a plain sentence and a chip:

| Chip | Meaning |
|---|---|
| **Works** | Deck can control it fully. |
| **Partly** | Some of it works; the sentence says what. |
| **Not yet** | Deck does not control this on your machine. |

The areas you may see:

- **Processor.** On Intel desktops: turbo and clock presets, and the multiplier on unlocked models. On Intel laptops: turbo and clock presets work, but power limits are often locked by the laptop. On AMD: turbo and clock presets work; AMD power limits and Curve Optimizer are not in Deck yet. Any other processor gets the presets that go through Windows' power plan.
- **Each graphics adapter** by name. NVIDIA: clocks, power limit, fan and overlay readings work. AMD and Intel graphics (card or built-in): Deck reads temperature and load; tuning them is not in Deck yet.
- **Handheld**, on a recognised handheld PC: Deck's pages fit the screen and work by touch, its built-in controls show on the [Controller](controller.md) page when Windows lists them as a controller, and Windows' power mode works. The maker's own power-limit and fan modes are not in Deck yet.
- **Laptop controls**, on a laptop: whether a maker's control interface answered. Fan speed through HP's BIOS works on HP Omen and Victus models; for other makers Deck says plainly that it cannot use their controls yet. Windows' power mode works on all of them.

---

## Hardware and access

Each row is a component, what Deck found, and a capability chip (**Works**, **Unavailable** or **Read only**).

| Row | What it shows |
|---|---|
| **Motherboard** | Maker and model, with the BIOS version. |
| **Processor** | The CPU name, with a note when Deck has one. |
| **Graphics** | The graphics adapter(s). **Unavailable** if Deck has no supported card. |
| **Fans** | How many fans were found and the fan chip on the board. **Works** only when fan control has been checked on this board; "readable; control not verified on this board" is shown otherwise. |
| **Board lighting** | Whether Deck can control the motherboard's RGB lighting. |
| **RAM lighting** | The same for memory sticks. |
| **Cooler display** | Whether a supported liquid cooler display was found. |
| **Memory** | The installed sticks (for example "2 x ..."), with memory in use of total. |
| **Admin rights** | Whether Deck runs with administrator rights. |

This section appears when the hardware engine is running.

### One-time set up

If the section is replaced by a card titled **One-time set up** saying "Hardware control needs admin rights", press **Set up**. Windows asks for administrator permission once, Deck creates a start-up task and restarts itself with those rights. After that Deck starts with admin rights at sign-in and the card does not come back. The installer does this for you, so you usually only see it if you launched Deck some other way. See [Getting started](getting-started.md).

If your platform cannot support hardware control at all, the card says why instead.

Why admin rights? Reading fan speeds, CPU temperature, drive health and lighting means talking to hardware, which Windows only allows for administrators.

---

## Support report

A text report that answers "what is this machine and what did Deck find?" without a second round of questions. Attach or paste it when you report a problem.

- **Copy report** puts the report on the clipboard so you can paste it into a chat or an issue.
- **Save report** writes it to a file in Deck's data folder and shows the file in Explorer.
- **Include crash files (may contain private data)** adds Deck's crash reports. The box starts ticked only if you have already agreed to include crash files since Deck started; otherwise it is off. When you copy the report, crash text is added to the end (with personal details blanked out). When you save, the report and the crash files go into one zip file.
- If your PC has lighting Deck can control, **Save report** asks first whether to add a **lights test**: the lights cycle red, green and blue for about 15 seconds and then return. Use it for lighting problems. **Cancel**, **Save without it** and **Add the test** are your choices.

The report has these parts: Deck (version, whether it runs as admin, whether the hardware engine, the PawnIO driver and the NVIDIA engine run, shortcut keys), Windows (edition and build), Computer (type, board and BIOS, battery, processor, memory, graphics), Machine (what Deck detected: processor family, maker, graphics kinds, which maker interfaces answered), Hardware (what the engine found: fans, sensors, lighting), Overlay (whether RivaTuner is installed and running), Drives (model, health, temperature, hours), Runs (this run and the previous one, safe mode), Deck memory, Background workers, Problems this run, and the last 80 log lines.

It contains **no personal data**: file paths are shortened and drive serial numbers are left out. Read it before you share it if you are unsure.

Below the buttons a short note lists any Deck background worker that is not running normally, followed by the number running without a crash.

---

## Recommended setup

- Check this page first when a feature is greyed out, missing or "Not yet": it says whether your hardware or Deck is the limit.
- Make sure **Admin rights** shows that Deck runs with them.
- Keep **Include crash files** off unless someone asks for them.
- Laptops and handhelds: expect "Partly" and "Not yet" on the maker's own controls. This is honest information, not a fault.

---

## Troubleshooting

**The hardware table is missing.** Deck is not running with administrator rights, or the hardware engine is still starting ("Finding hardware..."). Press **Set up** if it is offered, or wait a few seconds.

**Fans say "Readable; control not verified".** Deck can read the fan chip but has not confirmed that it may change speeds on this board. Deck does not control a fan it is unsure about.

**My graphics card shows "Partly".** Deck reads AMD and Intel graphics but cannot tune them yet. NVIDIA cards get the full set.

**PC health this week has no drive comparison.** It needs at least two saved checks. Check again tomorrow.

**The report is not saved.** Make sure Deck's data folder (`%APPDATA%\Deck`) is writable.

---

## FAQ

**Is the support report safe to post publicly?** It leaves out file paths and drive serial numbers, and it holds hardware and Windows details. It is meant to be shared, but check it first if you want to be sure.

**Does the page change anything on my PC?** No. The only action that does anything is the optional 15-second lights test saved with a report.

**Will Deck get support for my laptop's fan modes?** The "What Deck can do here" table tells you what is covered today. If your laptop is listed as "Not yet", the report you save here is what helps to add it.

**Does Deck work with anti-cheat?** Yes. Deck never injects into games or reads their memory. This page only reads hardware information and Deck's own records.
