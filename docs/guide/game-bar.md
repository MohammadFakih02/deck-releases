Where to find it: Gaming › Deck bar

# Deck bar

A panel that slides over your game with one-click controls: mic, sound output, profiles, frame rate limit, music, death counter and more.

The bar is off until you turn it on. The page has three tabs, **Widgets**, **Layout & look** and **Opening**, under a live preview of the bar over a game screen. Beside the preview are the bar's switch, how it opens, **Open now** and the bar style.

Related pages: [Game profiles](gaming.md), [Performance overlay](overlay.md), [Death counter](death-counter.md), [Controller](controller.md), [Phone](phone.md).

## How the bar behaves over a game

- The bar stays on top but does not take the focus, so the game does not minimize, pause or tab out.
- With **Focus the bar on hover** on (the default), the bar takes the focus only while the pointer is over it, so a click on the bar never also acts in the game.
- With **Use keyboard in the bar** on, the bar takes the focus when it opens, so the keyboard works and Esc closes it.
- It needs borderless or windowed fullscreen. Nothing can be drawn over a game in exclusive fullscreen without injecting into it, which Deck never does.

## Turning it on

1. Open **Gaming › Deck bar** and turn on the switch next to the preview.
2. The line under it says how the bar opens, for example "Hold Select + Start for 0.6 s." or "Opens from the tray menu only."

Turning it on adds **Deck bar** to the tray menu, turns on your controller combination and shortcut, and lets the phone remote open it. **Open now** works even while the bar is off, so you can try it first.

## Opening and using it

| Way to open | Details |
|---|---|
| Controller | Hold the two buttons set in **Hold to open** while a game is in front. The same hold closes it. The game still gets every press. |
| **Shortcut** | Your own key, also while a game is in front. |
| Tray menu | Deck's tray icon › **Deck bar**. |
| Phone remote | Tap Deck bar in the [phone remote](phone.md). |
| **Open now** | The button on this page. |

To close it, use the same shortcut or combination, press B, press the close button, or press Esc when the bar has the keyboard. Switching away from the game also closes it, and **Close automatically** can close it after a time without input.

With a controller: the left stick or D-pad moves (hold to repeat), A presses, B closes, LB and RB jump between widgets, and left and right change a slider. The footer then reads "D-pad moves · A presses · B closes · LB/RB jump". Moving the mouse switches back to mouse mode.

The bar never scrolls. When the widgets are taller than the screen, its text shrinks (to half at most) until they fit.

## The Widgets tab

**On your bar** lists the widgets from top to bottom; **Not on your bar** holds the rest.

- Click a widget's name, or the widget in the preview, to open its settings.
- Reorder with the arrows (**Move up · Alt+↑**, **Move down · Alt+↓**) or drag a row.
- **Take it off the bar** moves a widget to **Not on your bar** and keeps its settings. Click it there to add it back. You can have one of each widget.
- **Reset widgets** brings back the default set.

Every widget has **Width** (how many columns it spans, when the bar has more than one), **Size** (**Small**, **Medium**, **Large**; larger shows more, such as the cover in Now playing) and **Title** (the heading above it), plus its own options:

| Widget | What it does and its options |
|---|---|
| **Now playing** | Track, artist and play buttons. **Cover** (Medium and Large only), **App name**, **Progress bar**, **Buttons**. Shows "Nothing is playing" when nothing plays. |
| **Volume** | A slider and mute for **Everything (master)** and for apps playing sound. **Apps listed** (0 to 10), **Percent**, and **Apps never listed** (click an app to hide it for good). |
| **Microphone** | Mutes your default mic: **Mic on** / **Mic off**. Option **Level slider**. |
| **Sound output** | Switches between outputs; the current one is checked. **Devices listed** (1 to 8). |
| **Free memory** | Frees idle memory and Windows' standby cache once per press, like **Free memory now** on [Game profiles](gaming.md#the-apps-to-close-tab), and says how much was freed. Apps stay open but may pause briefly. |
| **Sensors** | **Shown**, in the order you pick: FPS, CPU temp, GPU temp, GPU load, CPU load, Memory, CPU power, CPU clock. FPS needs RivaTuner ([Performance overlay](overlay.md)). A value the PC doesn't have shows "-". |
| **Frame rate limit** | Sets RivaTuner's limit and turns the limiter on in one press; **Off** turns it off. **Limits offered**: up to 10 numbers from 10 to 1000, with commas between them (default 30, 60, 90, 120, 144). See [Frame limiter](overlay.md#frame-limiter). |
| **Fan preset** | Switches between saved fan presets. Needs fan control ([Fans](fans.md)). |
| **Profiles** | Applies a saved CPU or GPU profile. **CPU profiles**, **GPU profiles**, **CPU profiles shown**, **GPU profiles shown** (none picked: every profile). |
| **Quick toggles** | Three big buttons: **Overlay**, **Mic** (**Muted** or **Live**) and **Profile** (steps to the next saved CPU profile, or GPU profile; needs two or more). Options **Overlay**, **Mute mic**, **Profile**. |
| **Controls** | Your most-used switches: **Controller overlay**, **Move the controller overlay**, **Death counter**, **Performance overlay**, **Microphone**, **Deck game mode**, **Frame rate limiter**, **Keep awake**. Options **Shown** and **On / Off under each**. |
| **Death counter** | The game's total, **+1 death** and undo, and the open fight. **Current fight**, **+1 and Undo**, **Fixes: won, not a boss, gave up** (with **Undo that fix** for a few seconds), **Teach in Deck**. When counting is off it offers **Turn it on**. |
| **Controller overlay** | **Showing** or **Hidden**. **Move and resize** (the bar closes; right-click when done), **Controller or keyboard**, **Size slider**, **Opacity slider**. |
| **FPS drops** | The likely cause of each recent dip, from [Why did it stutter?](gaming.md#why-did-it-stutter). **Drops listed** (1 to 6). Needs RivaTuner. Shows "No drops in this game so far" when there are none. |
| **Clock** | **Seconds** and **Date**. |

The default bar has Controls, Profiles, Frame rate limit, Sound output, Free memory, Volume and Now playing.

## The Layout & look tab

**Bar style** offers four styles: **Full height, right**, **Full height, left**, **Floating card, right** and **Floating card, left**. A floating card is only as tall as its widgets, and the game keeps every click around it.

| Setting | What it does | Default |
|---|---|---|
| **Height on the screen** | **Top**, **Middle** or **Bottom** (floating card only). | Middle |
| **Width** | 300 to 640 px. | 400 px |
| **Columns** | 1, 2 or 3; a widget can span one or more. | 2 |
| **Text size** | 70 % to 150 %. The bar shrinks it when the widgets don't fit. | 100 % |
| **Frosted glass** | Blurs the game behind the bar. | On |
| **Opacity** | How strongly the bar's color covers the blur. | 70 % |
| **Accent** | Deck's accent or one of eight colors. | Deck's accent |

## The Opening tab

| Setting | What it does | Default |
|---|---|---|
| **Hold to open** | The controller combination: **Off**, **Select + Start**, **L3 + R3** or **Select + L3**. On PlayStation controllers Select is Create and Start is Options. | Select + Start |
| **Hold time** | How long to hold the buttons, 0.3 to 1.5 s. A longer hold avoids opening by accident. | 0.6 s |
| **Shortcut** | Opens and closes the bar, also over a game. Click the box and press the keys; Esc cancels, Backspace clears. Use Ctrl, Alt or Win with a key, or an F-key alone. | None |
| **Use keyboard in the bar** | The bar takes keyboard focus when it opens; Esc closes it. Games that minimize when they lose focus may minimize. | Off |
| **Focus the bar on hover** | The bar takes the focus only while the pointer is over it. Hidden while **Use keyboard in the bar** is on. Turn it off if the game minimizes when it loses focus. | On |
| **Close automatically** | Closes the bar after **Never**, 10 s, 20 s, 30 s or 1 min without input. | Never |
| **Opening hint** | Once, early in your next game, a small card names your shortcut or combination. Clicks pass through it. It turns itself off after showing or when you open the bar. | On |

## The preview

The preview draws the bar exactly as it will appear: same width, text and shrinking. Clicking a widget in it selects the widget instead of pressing it. **Open now** opens the real bar.

## Recommended setup

- Controller players: keep **Select + Start** (or **L3 + R3**), a floating card on the side away from the game's HUD, and **Use keyboard in the bar** off.
- Keyboard and mouse players: pick a shortcut the game doesn't use (Ctrl+Alt plus a letter, or an F-key), keep **Focus the bar on hover** on, and set **Close automatically** to 20 s.
- Competitive players: keep only Controls and Sensors, in a floating card.
- Handhelds and small screens: 1 column and larger text.
- Always use borderless fullscreen in the game, and try **Open now** before a match.

## Troubleshooting

**The bar does not appear over my game.** Switch the game to borderless or windowed fullscreen, check that the bar is turned on, and try **Open now** with the game in front.

**The game minimizes when the bar opens.** Turn off **Use keyboard in the bar**. If it still does, turn off **Focus the bar on hover** too.

**Clicks on the bar also hit the game.** Turn on **Focus the bar on hover** and turn off **Use keyboard in the bar**.

**The controller combination does nothing.** It works only while a game is in front and with a controller Deck can read ([Controller](controller.md)). Check the buttons and try another **Hold time**.

**My shortcut was refused.** Another program already uses it. Pick a different one.

**A widget is empty.** A widget needs what it controls: a default mic, sound outputs, fan presets, a playing media app, or RivaTuner for FPS and the frame rate limit. The preview still shows empty widgets so you can set them up.

**The text is small.** With many widgets the bar shrinks its text to fit. Remove widgets, add columns or widen the bar.

**The hint does not show.** It shows once, only with a shortcut or combination set. Turn **Opening hint** on again to see it at your next game.

## FAQ

**Is the Deck bar safe with anti-cheat?** It is an ordinary window on top of the game; Deck never injects into games or reads their memory, and the controller is only read. See the [FAQ](faq.md).

**How is it different from Windows' Game Bar?** It is Deck's own panel, with controls for Deck's features and your own layout. It does not replace Windows' Game Bar.

**Can I use it without a controller?** Yes: use the shortcut, the tray menu, the phone or **Open now**.

**Where are the settings saved?** Every change is saved at once; the bar uses it the next time it draws.
