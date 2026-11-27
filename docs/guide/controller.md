Where to find it: Devices › Controller

# Controller

Show your controller (or keyboard and mouse) on screen over games, follow its battery and test its sticks and timing.

Four tabs: **On screen**, **Keys**, **Battery** and **Test**.

Any controller Windows recognizes works, by USB or Bluetooth. Nothing needs administrator. The overlay is a click-through window that never takes focus; Deck only listens to the controller, so your game still gets every button. It needs the game in borderless or windowed mode, because exclusive fullscreen hides overlays.

## On screen

The main switch is **Show the controller overlay**. The line under it says what is happening, for example **Waiting for a controller**, the controller's name and battery, **Demo input** or **Keyboard & mouse**.

Three chips show which part works:

| Chip | Good | Problem |
| --- | --- | --- |
| **Device** | **Found** | **Not found** |
| **Input** | **Arriving** (input in the last 5 seconds) | **None lately** |
| **Overlay** | **Visible** | **Not visible**, or **Turned off** (with a **Show overlay** button) |

The preview shows the overlay as it will be drawn. In the tray menu, the **Controller** submenu (in the Gaming group) has **Show controller input**, **Move / resize**, **Controller**, **Keyboard & mouse** and **Demo input**.

### Look

| Setting | What it does | Default |
| --- | --- | --- |
| **Show** | **Controller**, or **Keyboard & mouse** (pick the keys on **Keys**). | Controller |
| **Theme** | **Classic**, **Midnight**, **White**, **Gold** or **Mono**. | Classic |
| **Style** | **Glass** lets the game show through; **Solid**; **Buttons only** hides the body. | Glass |
| **Layout** | A full controller, or **Compact**, a small strip of buttons. | Full controller |
| **Controller shape** | **Match my controller**, or always **PlayStation** or **Xbox**. | Match my controller |
| **Size** | 50 % to 300 %, on top of Windows' display scaling. | 100 % |
| **Opacity** | 15 % to 100 %. | 88 % |

### Position

- **Corner**: six places on the top and bottom edges. Pick one on the preview. Default: bottom right.
- **Monitor**: **The game's monitor** (follows what you play) or a fixed monitor.
- **Move / resize**: drag the overlay, scroll over it to resize, then right-click it or press **Done moving**.

### Per game

**Own position per game** (off by default): **Move / resize** while a game is in front saves a place and size for that game only. **Use default** removes a game's own place.

### Behavior

| Setting | What it does | Default |
| --- | --- | --- |
| **Fade when idle** | Fades to 30 % after 6 seconds without input. | On |
| **Hide without a controller** | Nothing on screen until a controller connects. | On |
| **Hide from captures** | Recorders and screen shares don't see the overlay. NVIDIA Instant Replay pauses while it shows. | Off |
| **Reset the overlay** | Look, position and keys go back to how they started. | |

Streamers: leave **Hide from captures** off so viewers see your inputs.

## Keys

Keyboard and mouse mode draws the keys you choose, lit while pressed.

- Click a key on the drawing to show or hide it. The counter says how many are shown.
- **Starting set** is the 16 keys most games use. **Movement** is W A S D, Space, Shift and Ctrl. **All keys** shows every key. **Clear keys** clears them.
- **Show the mouse** adds the buttons, scrolling and movement (on by default).

Switch the overlay's mode with **Show** on the On screen tab.

## Battery tab

Every saved controller, on the same cards as [Device batteries](devices.md), with the same options. Below the cards is the **Battery % history** of the live controller with the lowest level. The time left needs 30 minutes of use and a 5 % drop; until then it says **Time left: learning**.

Deck reads controller batteries every two seconds without any vendor software. If the tray icons and the overlay are both off, nothing is read.

## Test

A live view that works with the overlay off. Nothing here is sent to the game.

- The controller's name, battery and ID, and whether Deck reads it through SDL or XInput.
- **Left stick** and **Right stick**: position from −1.00 to 1.00. **Triggers**: 0.00 to 1.00.
- **Buttons**: the overlay's drawing, lit live.

**Stick drift:**

1. Put the controller on a flat surface without touching the sticks.
2. Press **Measure stick drift**.
3. After five seconds Deck suggests a dead zone for each stick. Use it in your game's dead-zone setting.

**Input timing:**

1. Pick **Cable** or **Wireless**.
2. Press **Test timing** and keep a stick moving in circles for ten seconds.
3. The result is **Steady**, **Some gaps** (a wait over 50 ms) or **Unsteady** (over 150 ms, or a dropout). One result is kept for each link.

It never runs while a game is in front.

The phone as a controller is set up on [Phone](phone.md).

## Troubleshooting

**The overlay isn't showing.** Check the main switch and the chips. **Hide without a controller** hides it until one connects. Use borderless or windowed mode in the game.

**Waiting for a controller.** Connect it and press a button. If it says "not recognized", Windows sees a different kind of device.

**It draws the wrong shape.** Set **Controller shape** to PlayStation or Xbox.

**No battery shown.** Switch the controller on or plug in its receiver. Some controllers don't report a battery.

**The tray icon doesn't show.** Turn on **In tray** on the controller's card in Devices › Device batteries, and check **Show in** under **Tray and taskbar**.

## FAQ

**Is it safe with anti-cheat?** Yes. It is an ordinary window, and Deck only reads the controller or keyboard. It never touches the game.

**Does it cost frames?** Very little: up to 60 redraws a second while visible, fewer when idle, none when off.

**Can I count deaths with the controller?** That is a [Death counter](death-counter.md) setting.
