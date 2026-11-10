# Lighting and the cooler display

Two pages in the **Tune** group cover the lights on your PC:

- **Lighting** controls the RGB lights of your motherboard and RAM, ARGB strips and fans on the board's headers, a supported mouse, and other devices through OpenRGB. One effect, one place, instead of a program per brand.
- **Cooler display** drives the little lit display on a supported CPU cooler: temperatures, a clock, text, your own painted design, animations or a music meter.

Both are optional hardware. A page only appears when Deck can use something for it (the Lighting page is always there, because OpenRGB can control devices without a supported board). When Deck finds no lights it can control (no Mystic Light board, no Kingston Fury RAM, no supported Logitech mouse, and no OpenRGB devices), the page starts with **Lighting isn't supported on this PC yet** and a **Copy report** button: laptop keyboard lighting, for example, isn't in Deck yet, and the report tells us what your PC has.

**Where to find them:** sidebar > **Tune** > **Lighting**, and **Tune** > **Cooler display** (only when a supported cooler display is connected).

Related pages: [CPU](cpu.md) and [GPU](gpu.md) (a profile can set a lighting colour), [Fans](fans.md), [Sensors](sensors.md) (heat alerts can flash the lights), [Gaming](gaming.md) (a lighting effect per game), [Death counter](death-counter.md) (flash red on a death).

## Contents

- [What you need](#what-you-need)
- [The Lighting page](#the-lighting-page)
- [Effects](#effects)
- [Game reactions](#game-reactions)
- [Affected zones and strip lengths](#affected-zones-and-strip-lengths)
- [What overrides your effect](#what-overrides-your-effect)
- [Mouse lighting and Test my mouse](#mouse-lighting-and-test-my-mouse)
- [OpenRGB devices](#openrgb-devices)
- [The cooler display](#the-cooler-display)
- [What Deck changes, and how to undo it](#what-deck-changes-and-how-to-undo-it)
- [Recommended setups](#recommended-setups)
- [Troubleshooting](#troubleshooting)
- [FAQ](#faq)

## What you need

| Feature | Needs |
|---|---|
| Board lighting (12 V RGB header, two ARGB headers) | **Administrator rights**, and an **MSI Mystic Light** board whose USB controller is `1462:7D43`. Other boards are not driven by Deck; use OpenRGB for them. |
| RAM lighting | **Kingston Fury / HyperX** modules with RGB, on a PC whose chipset exposes an **Intel SMBus** (Deck reads them through the hardware driver). A plain, non-RGB kit has nothing to light, and the RAM switch is then hidden. |
| Mouse lighting | A **Logitech** mouse with colour-effect lighting. Other mice show "No supported mouse lighting found" and the Test my mouse tool. |
| OpenRGB devices | The free [OpenRGB](https://openrgb.org) program running with its SDK server turned on. |
| Cooler display | A USB LCD cooler with USB id `0416:8001` (the Thermalright Peerless Assassin 120 Digital is the one Deck was built with), and administrator rights. |
| Screen, Music and Game effects | Nothing extra. Screen colours come from the desktop, music from the sound the PC plays. |

Board, RAM and display control go through a small signed hardware driver (PawnIO) that Deck installs when you set up admin access. Until you do, the Lighting page shows **One-time set up: Hardware control needs admin rights** with a **Set up** button. One admin prompt, and Deck never asks again.

**Close other RGB software.** Manufacturer RGB programs (MSI Center, Mystic Light, and for the cooler display TRCC) fight over the same controller. Deck's board loop re-checks every five seconds that the Mystic Light controller still holds Deck's configuration and rewrites it if not, but two programs writing at once still flicker. Run one at a time.

## The Lighting page

**Top card.** A dot in the current colour, the current effect's name (or "Lights are off"), and a line for the board and one for the RAM (for example "RAM: 2 RGB stick(s) at 0x60, 0x61"). The **Lights off** button (turns into **Turn lights on**) switches every light Deck drives off at once. It takes effect immediately, is remembered, and is also in the tray menu as **Lights off**. It does not need Apply.

**Effect settings, zones, mouse and OpenRGB panels** (below the preview). Lighting settings are a **draft**: **nothing reaches the lights until you press Apply** in the bar at the bottom ("Changes aren't on the hardware yet."); **Undo changes** drops the draft. The mouse panel has its own **Apply mouse effect** button.

**Preview.** A row of six fans, each with an LED ring and spinning blades, running the chosen effect with its colour and speed. It is only a picture: **Stop preview** and **Start preview** leave your real lights running. Music, Game, Screen and Temperature use made-up sample data ("Sample audio", "Sample game scene", "Sample screen colours", "Sample CPU temperature") so you see the kind of movement. If your system asks for reduced motion, or Deck is in its low-spec mode, the preview starts stopped.

### Defaults

| Setting | Default |
|---|---|
| Effect | Rainbow |
| Brightness | 100 % |
| Speed | 40 |
| Colour | #009BDE (a blue) |
| Zones | Board 12 V RGB, ARGB header 1, ARGB header 2 and RAM all on |
| LEDs per ARGB header | 60 each |
| Music style | Level meter, rainbow colours, sensitivity 100 % |
| Game effect while playing | Off |
| Game audio only | On |
| Game effect sound | Pulse |
| OpenRGB | Off |

## Effects

Pick an **Effect** (**?**) from the list. Each has a one-line description under the list.

| Effect | What it does |
|---|---|
| **Static** | One colour. |
| **Breathing** | Fades your colour in and out. |
| **Rainbow** | Every colour, flowing. |
| **Color Cycle** | All LEDs change colour together. |
| **Wave** | Your colour runs along the strips. |
| **Comet** | A light with a tail chases around. **Comet colours:** **My colour**, **Cycle** or **Rainbow**. |
| **Temperature** | Blue when cool (30 C or below) through green and yellow to red when hot (80 C or above), following the CPU temperature. |
| **Music** | Follows whatever is playing. See below. |
| **Screen** | Matches the colours on your screen, each LED showing its part of the screen from left to right. |
| **Game** | Reacts to the game's sound. See [Game reactions](#game-reactions). |
| **Off** | Dark, but the board keeps its own settings. |

Other controls on the panel:

- **Colour**: shown for effects that use your colour (Static, Breathing, Wave, Music, Game and Comet on **My colour**). A colour picker, plus swatches for common colours.
- **Brightness** (**?**): 0 to 100 %. All lights change together. Dimmer is easier on the eyes at night, and some strips look washed out at full.
- **Speed** (**?**): 1 to 100 for the effects that move. Hidden for Static and Off.

**Music effect** (shown when Music is the effect):

| Setting | What it does |
|---|---|
| **Style** | **Level meter**, **Pulse**, **Beat flash**, **Bass & treble**, **Spectrum** or **Centre burst**. |
| **Rainbow colours** | On: colours follow the music. Off: your chosen colour. |
| **Sensitivity** (**?**) | 25 to 400 %. Quiet music needs more; loud music needs less. Higher is brighter and jumpier at the same volume. |

**How the screen and sound are read.**

- **Screen colours** come from Windows' desktop duplication (a small shrunken copy of the frame, well under 1 % CPU), with a slower fallback if duplication isn't available (for example during a UAC prompt, in some exclusive-fullscreen switches, or on an HDR desktop). Nothing is saved or sent.
- **Music** listens to the level of the sound your speakers play (a "loopback" capture) and splits it into bass, mids and treble with beat detection. It only listens while the effect uses it, and it keeps no recording.

## Game reactions

A panel called **Game reactions**.

| Setting | What it does | Default |
|---|---|---|
| **Flash red on a death** | Flashes the board lights red for two seconds when the [death counter](death-counter.md) counts a death. | Off |
| **Game effect while playing** (**?**) | When a full-screen or borderless game is in front, the lights switch to the Game effect and flash with its sound, like shots and explosions. Your normal effect returns when the game closes or you switch away. A **Game in front** chip shows while it is on. | Off |
| **Game effect sound** (**?**) | How lights react: **Off** (steady), **Pulse**, **Impact**, **Shockwave** or **Bass glow**. Impact and Shockwave suit shooters; Pulse or Bass glow suit calmer games. | Pulse |
| **Game audio only** (**?**) | The Game effect listens to the game's own sound only, not music or voice chat. Without it, Discord voices and Spotify make the lights flash too. | On |

How Deck measures the game's sound: it reads the **volume meter** that Windows keeps for that program (the same level Windows' own mixer shows). It does not inject into the game, read its memory, or touch its files.

## Affected zones and strip lengths

**Affected zones** (**?**): which lights Deck drives.

- **Board 12V RGB**, **ARGB header 1**, **ARGB header 2**
- **RAM** (only shown when the RAM's RGB controller answers)

Leave out lights another program controls, or ones you want dark. A light you turn off here keeps whatever it last showed.

**ARGB strip lengths** (a fold): **LEDs on ARGB 1** and **LEDs on ARGB 2**, 1 to 120 each (default 60). Count every fan and strip chained on that header. Wave and Comet need it to run smoothly along the whole chain. Too low and the chain's end stays dark; too high and the effect runs off the end and looks slow.

## What overrides your effect

Your saved effect is never changed by these; they sit on top and then step aside. In order of strength:

1. **Lights off** (the button or tray item): everything dark.
2. **A flash**: a few seconds of red when a **heat alert** fires (if **Flash the board lights red** is on in [Sensors](sensors.md) alerts, or an alert rule asks for it), or when **Flash red on a death** counts a death. The flash is at full brightness.
3. **A profile colour**: when the active CPU or GPU profile has **Use a lighting colour while this profile is active** on, the lights show that one colour (Static). A GPU profile's colour wins over a CPU profile's. When the profile ends, your previous effect returns.
4. **The Game effect**, when **Game effect while playing** is on and a game is in front.
5. Your chosen effect.

[Gaming](gaming.md) can also switch the lighting effect for a game and put it back afterwards.

## Mouse lighting and Test my mouse

The **Mouse** panel (on the Lighting page) drives the onboard lighting of supported **Logitech** mice (over their own HID++ protocol: colour LED effects). Deck asks each mouse which effects and lighting zones it has and only offers those. It never touches onboard profiles, DPI or firmware.

For each supported mouse:

| Setting | What it does |
|---|---|
| **Effect** | The effects the mouse offers, from **Static**, **Breathing**, **Colour cycle**, **Strobe / flash** and **Off**. |
| **Colour** | For Static, Breathing and Strobe. |
| **Brightness** | 1 to 100 %. Not for Off. |
| **Speed** | 1 to 100 % for Breathing, Colour cycle and Strobe. Higher makes the effect repeat faster. |
| **Apply mouse effect** | Sends the effect. It is **saved to the mouse**, which keeps it when Deck is closed. A line shows "Effect saved to the mouse." or what went wrong. |

If other mouse software is running, a note says it "may override these lights". Close it if the colours don't stick.

**Test my mouse** (shown when no supported mouse is found, and at the bottom of the panel): checks lighting support **without changing your mouse**. It reads only what Windows already knows about connected mice (device names, IDs, connection type) and the cached descriptor Windows keeps; it sends nothing to a device and reads nothing from one. It lists each mouse with a chip: **Supported**, **Not supported yet** or **Not checked**. **Full mouse report** (a fold) holds a text report with **Copy report**: share it to help get your mouse supported. Read it before posting it, since it lists your device names and IDs.

## OpenRGB devices

**OpenRGB devices** (bottom of the Lighting page) lets Deck also drive devices managed by [OpenRGB](https://openrgb.org): other motherboards, GPUs, keyboards, fans and so on.

1. In OpenRGB, turn on the **SDK server**.
2. In Deck, switch on **Also control OpenRGB devices**.
3. Leave **Server address** at `127.0.0.1` (this PC) and **Server port** at `6742`, unless your server is elsewhere (then enter its IP address). The address field accepts `localhost` or an IP address.
4. Press **Apply**. A status line says whether the server answers ("Waiting for the SDK server. Apply settings to connect." until it does).
5. Pick **Devices to control** (**All devices** or one; **Refresh device list** rereads them) and **What to show**: **Follow Deck lighting**, **One colour** (then **Device colour**) or **Turn lights off**.

Off by default. Deck only talks to the address you enter.

## The cooler display

A supported cooler has a small display made of 84 lit segments: two rows (top for the CPU, bottom for the GPU), each with a label, a 3-digit number, a degree symbol or a percent sign. This page controls what it shows. A **Preview** of the display redraws about twelve times a second so you can see your changes. If no display is connected, a banner says "No cooler display connected. You can still edit the preview below." The display needs **Apply** for its settings like the other hardware pages, except the **Display is on / off** switch, which acts at once and is remembered (the tray also has **Cooler display off**).

**Display power**

| Setting | What it does |
|---|---|
| **Display is on / off** | Switches the display. Immediate. |
| **Shows** (**?**) | What the display shows: **Sensors**, **Clock**, **Text**, **Design**, **Animation**, **Music meter** or **Rotate**. The preview updates at once; the cooler follows after **Apply**. |

**What each content does** (its own panel beside the preview):

| Content | Options |
|---|---|
| **Sensors** | **Readings on the display**: four fixed slots, CPU temperature, CPU load, GPU temperature, GPU load. Switch each on or off, move it up or down, remove it, or add it back from **Add a reading...**. The cooler has four fixed sensor slots, so this controls order and visibility, not new readings. |
| **Clock** | **24-hour** (default on), and **Bottom row**: **Date**, **Seconds**, **CPU temp**, **GPU temp** or **Off**. |
| **Text** | **Top line** and **Bottom line** (up to 40 characters; the default top line is "HELLO"), and **Scroll text that doesn't fit**. |
| **Design** | Click or drag over the preview to paint with the colour from **Paint**; right-click erases (black is off). **Clear**, **Fill**, and **Copy the sensors view** (turns what it shows now into a design to edit). |
| **Animation** | **Spinner**, **Chase**, **Sparkle**, **Wave** or **Snake**. |
| **Music meter** | Style: **Bars**, **Spectrum**, **Pulse**, **Beat flash** or **Levels**. |
| **Rotate** | Tick the contents to cycle through, and **Each for** 2 to 60 seconds (default 8). |

**Colour and brightness**

| Setting | What it does | Default |
|---|---|---|
| **Colour behaviour** (**?**) | **Custom**, **Rainbow**, **Color cycle**, **Breathing**, **By temperature** (a warning light you can see across the room), **By load**, or **Same as lighting** (matches your RGB effect). | By temperature |
| **Colour** | For Custom and Breathing. | #009BDE |
| **Brightness** (**?**) | 0 to 100 %. | 100 % |
| **Colour motion** > **Colour speed** (**?**) | How fast scrolling text, spinners and colour cycles move. Readings still update at the same rate. | 40 |
| **Fahrenheit** | Temperatures on the display in degrees F. | Off |

**Night and alerts**

| Setting | What it does | Default |
|---|---|---|
| **Dim at night** (**?**) | Between **From** and **Until** the display uses **Night brightness**. Works across midnight. | Off, 23:00 to 07:00 at 20 % |
| **Flash red when CPU gets hot** (**?**) | The display flashes red once the CPU reaches **Flash from** (50 to 105 C), whatever it shows. It stops as soon as the CPU cools below the limit. | Off, at 90 C |
| **Show important messages** | For 8 seconds shows SHUT SOON, TIMER DONE, DONE (downloads), ALERT or HEAT when those events happen. | Off |

## What Deck changes, and how to undo it

| Deck changes | How to undo it |
|---|---|
| Sends colours to the board's Mystic Light controller and writes its configuration | Turn effects off with **Off** or **Lights off**; quit Deck. The board's own settings are kept (Off only darkens the lights). |
| Sends colours to RAM sticks (Kingston) | Same. |
| Saves a mouse effect to a Logitech mouse's onboard memory | Choose another effect (or **Off**) and **Apply mouse effect**. |
| Sends to OpenRGB | Turn **Also control OpenRGB devices** off. |
| Drives the cooler display | Switch **Display is on** off, or quit Deck and let the vendor's tool take over. |
| Settings are stored in Deck's settings folder under `hardware` | Delete or change them in Deck; uninstalling Deck stops all of it. |

Nothing here can damage hardware: lighting only changes colours.

## Recommended setups

**Most people:** pick one effect you like (Static or Breathing in one colour, or Rainbow), keep brightness moderate, turn on **Game effect while playing** if you want the lights to react in games.

**Quiet bedroom or night use:** lower **Brightness**, use **Temperature** (a calm colour that only shifts when the CPU does) or **Off**, and set **Dim at night** on the cooler display. **Lights off** from the tray is one click.

**Streamers:** use a profile colour per GPU or CPU profile so the lights tell you which mode the PC is in, and **Flash red on a death** with the [death counter](death-counter.md).

**Several RGB programs on one PC:** let Deck own the Mystic Light board and RAM, and use OpenRGB for anything else, so only one program talks to each device.

## Troubleshooting

**The Lighting page has no board or RAM.** Deck found no supported controller. The top card shows the board and RAM status line. The board needs the MSI Mystic Light controller `1462:7D43`, RAM needs Kingston Fury/HyperX RGB modules and an Intel SMBus. Use OpenRGB for other hardware.

**The board ignores colours.** Another program (MSI Center, a manufacturer app) may be fighting for the controller. Close it. Deck rewrites its configuration if the controller loses it.

**RAM status says "no RGB controller answered on the SMBus (non-RGB kit?)".** The modules are Kingston but have no RGB controller Deck can talk to.

**RAM says some sticks are "not answering ... writes paused".** Deck pauses writes to a stick that doesn't answer and retries every few seconds. If it keeps happening, close other RGB programs.

**My mouse isn't listed.** Only Logitech mice with colour-effect lighting are supported. Run **Test my mouse** to see what Deck detects, and share the report.

**The mouse colour reverts.** Other mouse software may override it ("may override these lights" appears under the controls). Close it.

**OpenRGB says "Waiting for the SDK server".** Start OpenRGB, turn on its SDK server, check the address and port, press **Apply**, then **Refresh device list**.

**The Game effect doesn't start.** It needs a full-screen or borderless window in front (not a normal window), and **Game effect while playing** must be on. A **Game in front** chip appears while it is active.

**The cooler display shows nothing.** The page says "No cooler display connected" when Deck doesn't see USB device `0416:8001`. Close TRCC (Thermalright's program) if it is running: it fights for the same display.

**Changes don't show on the lights.** Press **Apply**. Lighting edits are a draft until you do (except **Lights off**, the mouse's **Apply mouse effect** and the display's on/off switch).

## FAQ

**Does lighting work in games with anti-cheat?** Deck never injects into games or reads their memory. The Game effect uses Windows' volume meter for the game's program. The board, RAM and display are reached through Deck's hardware driver; for the one anti-cheat client that refuses to run next to that driver (FACEIT), Deck stops using it while that client runs. See [Fans](fans.md#what-happens-with-anti-cheat).

**Does it use a lot of CPU?** Screen colours use well under 1 % CPU. Lights that do not change (Static, Off) are not resent every frame.

**Are my lights remembered after a restart?** Deck saves your effect and applies it when it starts with Windows.

**Why is my lighting colour sometimes overridden?** A heat alert flash, a death flash, a profile colour, or the Game effect is on top of your effect. See [What overrides your effect](#what-overrides-your-effect).

**Can I control the lights from the tray or my phone?** The tray has **Lights off** and, for the cooler display, **Cooler display off**.

**Does the screen effect record my screen?** No. Deck takes a tiny averaged strip of colours, does not save it and never sends it anywhere.

**Is the mouse test safe?** Yes: it only reads what Windows already stores about your mice. Nothing is sent to a device.
