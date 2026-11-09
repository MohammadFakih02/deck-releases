# Controller

The Controller page shows your controller (or your keyboard and mouse) on screen over your games, tracks the battery of every controller, and has a live test view with a stick drift check.

**Where to find it:** sidebar > **Play** > **Controller**. Four tabs: **On screen**, **Keys**, **Battery** and **Test**.

**Safety and anti-cheat.** The overlay is an ordinary click-through window that never takes focus. Controllers are read the way games read them (through SDL, with XInput as a fallback), so Deck only listens: your game still receives every button. In keyboard and mouse mode Deck uses Windows Raw Input, which is receive-only: nothing is blocked or changed, and it is registered only while that mode is on. Deck never injects into a game or reads its memory.

**Requirements.** Any controller Windows recognises, by USB or Bluetooth (PlayStation, Xbox, GameSir and other pads). Nothing needs admin rights. The overlay needs the game in **borderless** or windowed mode: overlays are hidden by exclusive fullscreen.

## On screen tab

At the top is the main switch, **Show the controller overlay**, with a status line that tells you what is happening:

- "Off. Turn it on to see your controller over your games."
- "Waiting for a controller (USB or Bluetooth)." or "Showing (controller name) · battery."
- "Showing demo input (no controller needed)." or "Showing keyboard & mouse."
- If Windows reports a device that isn't a controller, it says it isn't recognised as one.

The tray menu has the same switches under **Controller overlay**: **Show overlay**, **Move / resize**, **Controller**, **Keyboard & mouse**, **Demo input** and **Settings...**.

A preview picture on the right shows the overlay exactly as drawn with your settings.

### Look

| Setting | What it does | Default |
|---|---|---|
| **Show** | **Controller**, or **Keyboard & mouse** (pick the keys in the Keys tab). | Controller |
| **Theme** | Colours: **DS4**, **Midnight**, **DualSense**, **Gold**, **Mono**. | DS4 |
| **Style** | **Glass** lets the game show through; **Solid**; **Buttons only** hides the body. | Glass |
| **Layout** (controller mode) | **Controller** is a full controller; **Compact** is a small strip of buttons. | Controller |
| **Controller shape** (controller mode) | The drawing and button names: **Match my controller** follows the one connected, or force **PlayStation** or **Xbox**. | Match my controller |
| **Size** | 50% to 300%, on top of Windows' display scaling. | 100% |
| **Opacity** | 15% to 100%. | 88% |

Size and Opacity apply while you drag the slider.

### Position

| Setting | What it does |
|---|---|
| **Corner** | Six anchors: top left, middle, right and bottom left, middle, right. Default bottom right with a 24 px margin. |
| **Monitor** | **The game's monitor** (follows whatever you are playing) or a specific monitor, listed with its resolution. |
| **Move / resize** | Drag the overlay anywhere, scroll over it to resize, right-click it (or press **Done moving**) when finished. |

### Per game

**Separate position for each game** is off by default. When on, **Move / resize** while a game is in front saves a position and size for that game only; the others keep the default. Each saved game is listed with its corner, size and program, and **Use the default** removes it. With this on, the Look section's size becomes "Size (default)".

### Behaviour

| Setting | What it does | Default |
|---|---|---|
| **Fade when idle** | After 6 seconds without input the overlay fades to 30%. | On |
| **Hide without a controller** (controller mode) | Nothing on screen until a controller connects. | On |
| **Hide from screenshots and recordings** | The overlay is invisible to recorders and screen shares. NVIDIA Instant Replay switches itself off while the overlay is showing if you choose this. | Off |
| **Reset the overlay** | Look, position and selected keys back to how they started. Opens a confirmation. | |

### Recommended

- Streamers: leave **Hide from screenshots and recordings** off so viewers see your inputs, or turn it on if you only want it for yourself (and note the Instant Replay catch).
- Several monitors: keep **The game's monitor**.
- Playing different games with different HUDs: turn on **Separate position for each game**.
- Wide screens or small scale: use **Compact** and a smaller size.

## Keys tab

Keyboard and mouse mode draws the keys you choose, lit while pressed.

- **Show on screen > Input:** switch between **Controller** and **Keyboard & mouse** (you can pick keys before switching).
- **Keys to show:** a drawing of the keyboard. Click a key to show or hide it. The counter shows how many are shown ("16 of 71 shown", for example). **All keys** shows every key (function, letters, numbers, punctuation, arrows); **Starting set** returns to the 16 keys most games use (1, 2, 3, 4, Tab, Q, W, E, R, Shift, A, S, D, F, Ctrl, Space); **None** clears them.
- **Show the mouse:** buttons, scrolling and movement beside the keys (on by default). Input is read with Windows Raw Input, which only listens.
- **Switch to keyboard & mouse** appears when the overlay is still showing your controller.

## Battery tab

Every controller that reports a battery appears here, lowest first.

- The first controller is shown large with its percentage (with "Charging" when plugged in), where the reading came from, and an estimate of the hours left. The estimate needs 30 minutes of use and a 5% drop while connected. **Battery history** lists past readings.
- **Other controllers** lists the rest, each with its own reading.
- A warning appears when a battery is at 15% or lower and not charging.

The battery settings live in **Settings › Games** (*Controller battery*):

| Setting | What it does | Default |
|---|---|---|
| **A tray icon per controller** | One tray icon per controller with the percentage inside, green while charging, red when low. Clicking one opens the Controller page. | On |
| **Warn when a battery gets low** | A warning once per charge, at 15%. | On |
| **Show the warning over games** | Shows the warning on its own card over the game. Shown while low-battery warnings are on. | Off |

Deck reads batteries from several sources every two seconds (GameSir vendor data, PlayStation reports, Windows' gaming input, Bluetooth battery data and XInput), combines them per controller and drops a controller that stops answering. It works with GameSir, PlayStation, Xbox and other pads Windows knows, without any vendor software. If both the tray icons and the overlay are off, battery reading is off too.

## Test tab

A live view that updates several times a second, and works with the overlay off.

- The controller's name, battery and, under **Device details**, the vendor and product ID and whether it is read through SDL or XInput.
- **Left stick** and **Right stick:** a dot showing the position and X/Y numbers from -1.00 to 1.00 (left and up are negative).
- **Triggers:** L2 and R2 from 0.00 (released) to 1.00 (fully pressed).
- **Button input:** every button lights up while pressed (Cross/A, Circle/B, Square/X, Triangle/Y, D-pad, L1/LB, R1/RB, L3, R3, Share/View, Options/Menu, PS/Guide, Touchpad).
- **Stick drift check:** rest the controller on a flat surface with the sticks untouched and press **Measure stick drift**. It measures for about five seconds and suggests a dead zone for each stick, for example "left 6%, right 4%". Use those numbers in your game's dead-zone setting. Needs a connected controller and **Demo input** off.

Nothing in the Test tab is sent to the game or changed.

## Phone layouts

The phone as a controller, and the phone's keyboard and controller layouts, are set up on the [Phone](phone.md) page, not here.

## Troubleshooting

**The overlay isn't showing.** Check the main switch. In controller mode, **Hide without a controller** hides everything until one connects. Check the monitor. Use borderless or windowed mode in the game.

**"Waiting for a controller".** Connect it by USB or Bluetooth and press a button. If the status says it isn't recognised as a controller, Windows sees a different kind of device.

**It draws the wrong controller shape.** Set **Controller shape** to PlayStation or Xbox.

**No battery shown.** Switch the controller on, or plug in its receiver. Some devices don't report a battery. Battery reading is on only while the overlay or the tray icons are on.

**Time left says it needs 30 minutes.** The estimate needs 30 minutes of use and a 5% drop while connected.

**The tray icon doesn't show.** Turn on **A tray icon per controller** (Settings › Games); a controller must have reported a battery.

**The overlay shows in my recording / doesn't show.** Change **Hide from screenshots and recordings**.

## FAQ

**Is the overlay safe with anti-cheat?** It is an ordinary window and Deck only reads the controller or keyboard (receive-only). It never injects into or reads from a game.

**Does the game still get my buttons?** Yes. Nothing is blocked or changed.

**Does it work in exclusive fullscreen?** No. Overlays hide in exclusive fullscreen; use borderless.

**Does it cost frames?** It redraws at up to 60 times a second while visible, less when idle, and only a few times a second while hidden with no controller. When off it does nothing.

**Can I use it for the death counter?** The controller combo for counting deaths is a separate setting in [Deaths](death-counter.md) (hold View with D-pad Down).

**See also:** [Overlay](overlay.md), [Game bar](game-bar.md), [Deaths](death-counter.md), [Phone](phone.md).
