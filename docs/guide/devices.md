Where to find it: Devices › Device batteries

# Device batteries

See the battery of your controllers, headsets, mice and keyboards, and choose where those levels show.

Devices are listed most urgent first: low battery, then the lowest levels, then charging devices. Each card shows the device, a ring with its level, its state, and that device's own options. The summary at the top says how many are reporting now (for example **3 of 4 reporting**). Links open **Controller › Battery**, **Lighting › Lighting** and **Lighting › Cooler display** when that hardware is there.

Clicking a battery tray icon or the taskbar widget opens a small battery pop-up. It never takes focus and closes when you click elsewhere or move the pointer away.

## Live, asleep and not seen

Every place that shows a device battery uses the same words:

| State | When | Example |
| --- | --- | --- |
| Live | The device answered Deck's last check. Also **Charging**, plugged in or low. | 89% · live |
| **Asleep** | The device stopped answering. Most wireless mice and headsets sleep when idle; Deck keeps the last level and shows its age. | 89% · asleep · 4 min ago |
| Not seen | No answer for 24 hours. The device leaves the tray, pop-up and widget and moves to **Not connected for a day**. | 89% · not seen · 3 days ago |

Only a live level can trigger a low-battery warning. A device with no level shows **No reading**, never 0 %.

## Battery history and time left

Every device with a percentage keeps a history for 30 days. The history button (the pulse icon) on a card opens a chart; dashed parts are charging, gaps mean the device didn't answer. After half an hour on battery, the card shows how many hours are left (for example "4.5 h left"). When a device finishes charging, Deck says so once (**Say when a device is charged**). During a game it waits.

## Each device's options

- **In tray**: show the device in the tray icon and taskbar widget. Off, it stays on this page only.
- **Warn in games**: show the low-battery warning on a small card over a game.
- **Warn at**: Off, or 5 to 40 % in steps of 5. You get one warning per discharge.
- **Rename**: type a name and press **Save name**. **Use "<name>"** goes back to the device's own name.
- **Forget**: for a device that is asleep or not seen, removes its choices and last level.

A headset Deck knows also lists what its family offers (**Battery**, **Charging**, **Sidetone**, **Mic light**, **Auto off**, **Chat mix**, **EQ**, **Voice prompts**). A check mark means Deck reads it. The list comes from [HeadsetControl](https://github.com/Sapd/HeadsetControl)'s device list.

### Headset controls

Some headsets also get **Controls** on their card, while connected. **Audio › Mixer** links here.

| Headset | Controls |
| --- | --- |
| HyperX Cloud Alpha Wireless | **Sidetone**, **Auto off** (10, 20 or 30 min), **Voice prompts** |
| Logitech G633, G635, G733, G933, G935 | **Sidetone** |

No model has been tried with these controls yet, so they are locked and marked **Needs a tester**. To try them:

1. Turn on **Use untested** on the headset's card.
2. With no game running, try each control. Each change is sent when you let go of the slider or pick a value.
3. Report what happened with **Copy device report**.

These headsets don't report their own values, so the card shows the last value Deck sent. If HyperX NGENUITY or Logitech G HUB is running, the card warns that it may write its own values back. Deck never updates firmware.

## Tray and taskbar

The card at the bottom holds every other battery setting. Rows for the tray icon only show while tray icons are on; rows for the widget only while the widget is on.

| Setting | What it does | Default |
| --- | --- | --- |
| **Show in** | **Tray icon**, **Taskbar widget** or **Both**. | Tray icon |
| **Tray icon style** | **Ring**, **Number**, **Badge** or **Two icons**. | Ring |
| **One icon for all devices** | One tray icon for the most urgent device. Point at it for the full list. | On |
| **Widget style** | **Inline** (icon and percentage in the taskbar's own font), **Stacked** (icon above percentage, narrower) or **Rings**. | Inline |
| **Widget background** | A soft panel behind Inline and Stacked, for see-through taskbars. | Off |
| **Moon on asleep devices** | Adds a small moon after an asleep device in the widget. | Off |
| **Color by level** | Green while charging, red when low. | On |
| **Hide while charging** | Hides charging devices from the tray, pop-up and widget. | Off |
| **Hide when full** | Hides full devices until their level drops. | Off |
| **Say when a device is charged** | One notice when a device finishes charging. | On |
| **Show new devices** | Which kinds show the first time Deck sees them. | Controllers, headsets, mice |
| **Device report** | **Copy device report** (see below). | |

The taskbar widget sits just left of the notification area and moves and hides with the taskbar. It hides when no device is shown or when there is no room. On a crowded taskbar it can cover task buttons.

## What Deck can read

- Controllers: Xbox, PlayStation, GameSir and other pads Windows knows. More on [Controller](controller.md#battery-tab).
- Bluetooth devices that give Windows a level (the number Windows' Bluetooth settings show), plus Bluetooth LE devices with the standard battery service. A headset with no other source uses its hands-free level, marked "Bluetooth hands-free, approximate".
- Logitech wireless mice, keyboards and headsets, on a Unifying, Bolt or Lightspeed receiver or direct.
- Wireless headsets on their USB dongle: SteelSeries Arctis 7, Pro and Nova 7, Corsair Void and HS, HyperX Cloud Alpha Wireless.
- Razer wireless mice (DeathAdder, Viper, Basilisk, Naga, Cobra, Lancehead, Mamba, Pro Click).
- Other USB devices that report a standard battery level, such as some UPS units.

Deck only sends read requests, the same ones the makers' own apps use. Controllers are read every few seconds, Bluetooth devices once a minute, Logitech, Razer and dongles about every 5 minutes. Plugging something in or waking the PC reads them all again. With every tray icon and warning off, nothing is read.

## Copy device report

To ask for support for a device Deck can't read, press **Copy device report** and paste it into a bug report. It lists device ids and descriptors only: no names, Bluetooth addresses, serial numbers or file paths.

## Troubleshooting

**My device isn't listed.** It must have reported a level once. If Windows' Bluetooth settings show no percentage for it, Windows doesn't get one, and many cheap mice and keyboards have none.

**The level doesn't change for a long time.** Bluetooth devices report a new level only now and then.

**I turned on In tray and nothing appears.** The device must have answered in the last 24 hours. Check **Show in**, **Hide while charging** and **Hide when full**.

**My mouse says asleep while I'm using it.** Logitech, Razer and dongle readers ask about every 5 minutes, so it turns live at the next check.

The battery list and widget look were inspired by [Joule](https://github.com/DillanCidral/Joule) (AGPL-3.0) and [BatteryHub](https://github.com/krisgfx9/Wireless-Device-Battery-Monitor) (GPL-3.0); Deck includes none of their code or assets.
