Where to find it: Lighting › Lighting

# Lighting and the cooler display

Set one lighting effect for your motherboard, memory, ARGB fans, mouse and OpenRGB devices, and choose what your cooler's little display shows.

The Lighting group has two pages:

- **Lighting**: the RGB lights of the board and RAM, ARGB strips and fans on the board's headers, a supported mouse, and other devices through OpenRGB.
- **Cooler display**: the lit display on a supported CPU cooler (temperatures, a clock, text, a design, animations or a music meter).

When Deck finds nothing it can light, the page says **Lighting isn't supported on this PC yet**, with **Copy report** and **Open GitHub issues** so support can be added. Laptop keyboard lighting isn't in Deck yet.

Related pages: [CPU](cpu.md) and [GPU](gpu.md) (a profile can set a lighting color), [Sensors](sensors.md) (heat alerts can flash the lights), [Game profiles](gaming.md) (an effect per game), [Death counter](death-counter.md).

## What you need

| Feature | Needs |
|---|---|
| Board lighting (12 V RGB header, two ARGB headers) | An MSI Mystic Light board (USB controller `1462:7D43`) and administrator. Use OpenRGB for other boards. |
| RAM lighting | Kingston Fury or HyperX RGB modules on a PC with an Intel SMBus, and administrator. |
| Mouse lighting | A Logitech mouse with color lighting. |
| OpenRGB devices | The free [OpenRGB](https://openrgb.org) program with its SDK server on. |
| Cooler display | A USB LCD cooler with id `0416:8001` (such as the Thermalright Peerless Assassin 120 Digital), and administrator. |

Without administrator the page shows **Needs administrator** with **Restart as administrator**. See [Why Deck needs administrator](getting-started.md#why-deck-needs-administrator).

Close other RGB software (MSI Center, Mystic Light, and TRCC for the cooler display): two programs writing the same controller flicker. A line at the top of each page names a running vendor program (iCUE, Armoury Crate, NZXT CAM, G HUB and others) with **Pause** for this session; **Start again** or a restart brings it back.

## The Lighting page

At the top, a picture of a PC shows the chosen effect on its zones, with **Effect now**, **Brightness** and **Zones on**. **Turn lights off** (then **Turn lights on**) darkens every light Deck drives at once, without Apply; the tray has the same as **Lights off**.

**Lighting zones** turns each zone on or off: **Board**, **ARGB 1**, **ARGB 2** and **Memory** (when the RAM's controller answers). A zone you turn off keeps what it last showed.

Below: **Effects**, **Effect settings**, **Reactions**, **Lights Deck controls**, **Mouse effects** and **OpenRGB devices**.

Lighting edits are a draft: nothing reaches the lights until you press **Apply hardware changes** in the bar at the bottom. **Discard pending changes** drops them. **Turn lights off**, **Apply mouse effect** and the display's on switch act at once.

**Lights Deck controls** lists each zone with **On** or **Off** and, for ARGB 1 and ARGB 2, the number of lights (1 to 120, default 60). Count every fan and strip chained on that header, so Wave and Comet run smoothly along the whole chain.

Defaults: Rainbow, brightness 100 %, speed 40, color #009BDE, all zones on, OpenRGB off.

## Effects

| Effect | What it does |
|---|---|
| **Static** | One color. |
| **Breathing** | Fades your color in and out. |
| **Strobe** | Flashes your color, at most three times a second (faster flashing can trigger seizures). OpenRGB devices flash too. |
| **Rainbow** | Every color, flowing. |
| **Color cycle** | All LEDs change color together. |
| **Wave** | Your color runs along the strips. |
| **Comet** | A light with a tail chases around. **Comet colors**: My color, Cycle or Rainbow. |
| **Temperature** | Blue when the CPU is cool (30 °C or below) to red when hot (80 °C or above). |
| **Music** | Follows whatever is playing. |
| **Screen** | Matches the colors on your screen, left to right. |
| **Game** | Reacts to the game's sound. See [Reactions](#reactions). |
| **Off** | Dark, but the board keeps its own settings. |

**Effect settings** has **Color** (for effects that use one), **Brightness** (0 to 100 %) and **Speed** (1 to 100, for effects that move). For Music: **Style** (**Level meter**, **Pulse**, **Beat flash**, **Bass & treble**, **Spectrum** or **Centre burst**), **Rainbow colors** and **Sensitivity** (25 to 400 %; quiet music needs more).

Screen colors come from a tiny shrunken copy of the desktop (well under 1 % CPU). Music and Game listen to the sound level only while the effect uses it. Nothing is recorded, saved or sent.

## Reactions

The first three flash the lights on a Deck event, then your effect comes back. Never more than three flashes a second.

| Setting | What it does | Default |
|---|---|---|
| **Heat alert** | Red for 8 seconds when a heat alert fires. Needs the alert on in [Sensors](sensors.md). | Off |
| **Death counted** | Red for 2 seconds when the [death counter](death-counter.md) goes up. | Off |
| **Profile change** | The new CPU or GPU profile's color for 2 seconds (white without one). | Off |
| **In-game effect** | While a full-screen or borderless game is in front, the lights switch to the Game effect. **Game in front** shows while it is on. | Off |
| **Reaction style** | How the Game effect reacts: **Off**, **Pulse**, **Impact**, **Shockwave** or **Bass glow**. Impact and Shockwave suit shooters. | Pulse |
| **Game audio only** | Listens to the game's own sound, not music or voice chat. | On |

Deck reads the game's level from the volume meter Windows keeps for each program. It never touches the game.

## What overrides your effect

From strongest to weakest; your saved effect is never changed:

1. **Turn lights off**.
2. A flash from **Reactions** or an alert rule, at full brightness.
3. A profile color: a CPU or GPU profile with **Lighting color** on shows that one color. A GPU profile's color wins.
4. The Game effect, with **In-game effect** on.
5. Your chosen effect.

[Game profiles](gaming.md) can also switch the effect for one game.

## Mouse lighting

**Mouse effects** drives the lighting of supported Logitech mice. Deck asks each mouse which effects it has and offers only those; it never touches profiles, DPI or firmware.

- **Effect**: from **Static**, **Breathing**, **Color cycle**, **Strobe** (0.5 to 3 flashes a second) and **Off**.
- **Color**, **Brightness** and **Speed** where the effect uses them.
- **Apply mouse effect** saves the effect to the mouse, which keeps it when Deck is closed ("Effect saved to the mouse.").
- **Save brightness only** keeps the brightness for the next effect and sends nothing now.

If other mouse software runs, a note says it may override these lights.

**Test my mouse** checks support without changing your mouse: it reads only what Windows already knows. Each mouse gets **Supported**, **Not supported yet** or **Not checked**. **Full mouse report** has **Copy report** to share; it lists device names and IDs, so read it before posting.

## OpenRGB devices

Lets Deck drive other boards, graphics cards, keyboards and fans through [OpenRGB](https://openrgb.org).

1. In OpenRGB, turn on the SDK server.
2. In Deck, turn on **OpenRGB devices**.
3. Leave **Server address** at `127.0.0.1` and **Server port** at `6742` unless your server runs elsewhere.
4. Press **Apply hardware changes**. Until it connects the card says "Waiting for the SDK server. Apply settings to connect."
5. Pick **Devices to control** (**All devices** or one; **Refresh device list** reads them again) and **What to show**: **Follow Deck lighting**, **One color** (with **Device color**) or **Turn lights off**.

Deck only talks to the address you enter.

## The cooler display

A small display of lit segments: a top row for the CPU, a bottom row for the GPU. A **Preview** shows your changes live. Without a display the page says **No cooler display found**; check the USB cable and close TRCC. Settings need **Apply hardware changes**, except **Display on**, which acts at once (the tray has **Cooler display off**).

**Shows** picks the content; **Display content** sets its options:

| Content | Options |
|---|---|
| **Sensors** | **Four fixed slots** (CPU temperature, CPU load, GPU temperature, GPU load): show, hide, reorder or remove them, and add one back. |
| **Clock** | **24-hour**, and a **Bottom row**: **Date**, **Seconds**, **CPU temp**, **GPU temp** or **Off**. |
| **Text** | **Top line** and **Bottom line** (up to 40 characters), and **Scroll text that doesn't fit**. |
| **Design** | Click or drag on the preview to paint with the **Paint** color; black is off. **Clear picture**, **Fill**, **Copy the sensors view**. |
| **Animation** | **Spinner**, **Chase**, **Sparkle**, **Wave** or **Snake**. |
| **Music meter** | **Bars**, **Spectrum**, **Pulse**, **Beat flash** or **Levels**. |
| **Rotate** | Cycles through the contents you select, **Each for** 2 to 60 seconds. |

**Color and brightness**

| Setting | What it does | Default |
|---|---|---|
| **Color behavior** | **Custom**, **Rainbow**, **Color cycle**, **Breathing**, **Strobe**, **By temperature**, **By load** or **Same as lighting**. | **By temperature** |
| **Color** | For Custom, Breathing and Strobe. | #009BDE |
| **Brightness** | 0 to 100 %. | 100 % |
| **Color speed** | How fast scrolling text, spinners and color cycles move. | 40 |
| **Fahrenheit** | Temperatures in °F. | Off |

**Night and alerts**

| Setting | What it does | Default |
|---|---|---|
| **Dim at night** | **Night brightness** between **From** and **Until**. | Off, 23:00 to 07:00 at 20 % |
| **Flash red when hot** | Flashes red once the CPU reaches **Flash from** (50 to 105 °C). | Off, 90 °C |
| **Show important messages** | For 8 seconds shows SHUT SOON, TIMER DONE, FILE DONE, DONE, ALERT or HEAT, then your content returns. **Preview** draws a message on the page only. | Off |

## What Deck changes and how to undo it

| Deck changes | How to undo it |
|---|---|
| Colors on the Mystic Light board and RAM | Choose **Off**, **Turn lights off**, or quit Deck. The board keeps its own settings. |
| An effect saved on a Logitech mouse | Choose another effect (or **Off**) and **Apply mouse effect**. |
| OpenRGB devices | Turn **OpenRGB devices** off. |
| The cooler display | Turn **Display on** off, or quit Deck. |

Lighting only changes colors; it can't damage hardware.

## Recommended setups

- **Most people:** one effect you like, moderate brightness, and **In-game effect** if you want the lights to react in games.
- **Night use:** lower **Brightness**, use **Temperature** or **Off**, and **Dim at night** on the cooler display.
- **Streamers:** a **Lighting color** per CPU or GPU profile, and **Death counted**.
- **Several RGB programs:** let Deck own the Mystic Light board and RAM, and OpenRGB the rest.

## Troubleshooting

**No board or RAM.** Deck found no supported controller. Use OpenRGB for other hardware.

**The board ignores colors.** Another program (MSI Center, a maker's app) is fighting for the controller. Close it or **Pause** it.

**RAM sticks are "not answering".** Deck pauses writes to that stick and tries again every few seconds. Close other RGB programs.

**My mouse isn't listed.** Only Logitech mice with color lighting are supported. Run **Test my mouse** and share the report.

**OpenRGB says "Waiting for the SDK server".** Start OpenRGB, turn on its SDK server, check the address and port, press **Apply hardware changes**, then **Refresh device list**.

**The Game effect doesn't start.** It needs a full-screen or borderless game in front and **In-game effect** on.

**The cooler display shows nothing.** Check the USB cable and close TRCC.

**Changes don't show on the lights.** Press **Apply hardware changes**.

## FAQ

**Is it safe with anti-cheat?** Deck never touches games. For the one anti-cheat that refuses Deck's hardware driver, see [Fans › What happens with anti-cheat](fans.md#what-happens-with-anti-cheat).

**Does it use a lot of CPU?** No. Screen colors use well under 1 %, and unchanging lights aren't sent again every frame.

**Are my lights remembered after a restart?** Yes, Deck applies your effect when it starts.

**Does the screen effect record my screen?** No. Deck takes a tiny strip of averaged colors and never saves or sends it.
