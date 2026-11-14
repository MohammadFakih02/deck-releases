Where to find it: Settings › Device batteries

# Devices

**Settings › Device batteries** shows the battery of your controllers, headsets, mice and keyboards, and decides which of them get a battery icon in the tray and a warning when the level is low. Each device keeps its own choices.

Find it under **Settings** (the button at the bottom of the sidebar), part **Devices**, or click a device's tray icon.

---

## What Deck can read

Deck shows a battery for a device when Windows or the device's own receiver reports one:

- **Controllers:** GameSir, PlayStation, Xbox and other pads Windows knows. The [Controller](controller.md#battery-tab) page has the history and hours left.
- **Bluetooth headsets, mice and keyboards** that give their level to Windows (the same number Windows' own Bluetooth settings show). A Bluetooth device appears only while it is connected.

- **Logitech wireless mice, keyboards and headsets** on a Unifying, Bolt or Lightspeed receiver, or connected directly. Deck asks the device itself for its battery (the same read-only request Logitech's own software uses), with the device's own name. Because these devices are asked rarely to leave them asleep, the level is refreshed about every 5 minutes. A device on a receiver that doesn't answer is hidden and tried again every 5 minutes, so a mouse you switch on after a long time off appears within about 5 minutes.

- **Wireless headsets on their USB dongle:** SteelSeries Arctis 7, Pro and Nova 7 models, Corsair Void and HS headsets, and the HyperX Cloud Alpha Wireless. Deck asks the dongle for the battery with the one read request the maker's own software sends, about every 5 minutes. A headset that is switched off is hidden and asked again every 5 minutes. A dongle that doesn't answer is tried again after 5, 10, 20 and then every 30 minutes. These readers are new and have been built from the makers' documented protocols; if your headset doesn't show, use the device report below.
- **Razer wireless mice** (DeathAdder, Viper, Basilisk, Naga, Cobra, Lancehead, Mamba and Pro Click models, on their dongle or by cable). Deck asks the mouse for its battery level and charging state with the same two read requests Razer's own software uses, about every 5 minutes. A mouse that is asleep or switched off is hidden and tried again after 5, 10, 20 and then every 30 minutes. If Razer Synapse is open at the same time, Deck waits and asks again later.
- **Bluetooth LE devices without a Windows level:** a connected Bluetooth LE mouse, keyboard or other device that gives Windows no battery number but offers the standard Battery Service is asked for it directly, about every 5 minutes. Deck never touches the part of the device that carries your typing and pointing.
- **Devices with a standard battery report**, such as uninterruptible power supplies and some headsets: if the device says in its USB description that it has a battery level, Deck reads it. These are listed last, so a better source for the same device wins.

A device without a number in Windows' Bluetooth settings usually doesn't report its battery to Windows. Deck then tries the device's own Battery Service, but many cheap mice and keyboards have none, and Deck can't show them. If you think a device should report one, use the device report below.

Deck asks every few seconds for controllers, once a minute for Bluetooth devices and about every 5 minutes for Logitech devices and headset dongles. If every tray icon and every warning is off, nothing is read at all.

## Look

| Setting | What it does | Default |
|---|---|---|
| **Tray icon style** | **Number** shows only the level; **Symbol and number** adds a small symbol for the kind of device (controller, headset, mouse, keyboard). | Symbol and number |
| **Colour by level** | Green while charging, red when the level is at or below its warning level. The number is always shown, so colour is never the only hint. | On |
| **Hide while charging** | The icon goes while the device charges and returns when it is unplugged. | Off |
| **Hide when full** | The icon goes at 100% and returns when the level drops. | Off |

## New devices

Pick the kinds that get a tray icon the first time Deck sees a device of that kind: controllers, headsets and mice are on at first; keyboards and other devices are off. This only affects devices Deck has not seen before. A device you have already set up keeps your choice.

## The device list

Every device Deck has seen is listed, connected ones first. Each row shows the device's name, its kind, its level (or **Not connected**), where the reading comes from, and:

- **Name:** type your own name for it. Leave it empty to follow the device's own name. The tray tooltip and the warning use this name.
- **Tray icon:** switch the device's icon on or off.
- **Warn over games:** show the low-battery warning on its own small card over a game.
- **Warn at:** the level that triggers the warning: Never, 5, 10, 15, 20, 30 or 50%. You get one warning per charge; it re-arms when the level has recovered by 5 points.
- **Forget:** removes a device that isn't connected, with its choices. It starts with the defaults if it shows up again.

A device that is away stays in the list, greyed, with the choices you made.

Clicking the tray icon of a controller opens the Controller page; any other device's icon opens this part.

## Copy device report

**Copy device report** puts a short text on the clipboard. It lists the Bluetooth devices (by kind and Windows category, connected or not, and whether they report a battery) and the USB or receiver interfaces that could carry a battery (vendor and product ID, what the maker calls it, and what Deck's readers answered). It never includes the names you gave your devices, Bluetooth addresses, serial numbers or file paths. Paste it into a message when a device shows no battery.

## Troubleshooting

**My device isn't listed.** It must be connected and report a battery. Check Windows' own Bluetooth & devices settings: if no percentage shows there, Windows doesn't get one.

**The level stays the same for a long time.** Bluetooth devices give Windows a new level only now and then, and Deck asks once a minute.

**I switched the tray icon on and nothing appears.** The device must be connected and reporting; check **Hide while charging** and **Hide when full** under Look.
