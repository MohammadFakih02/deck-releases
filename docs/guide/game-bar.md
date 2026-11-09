# Game bar

The game bar is a panel that slides over your game with one-click controls: mute the microphone, switch audio output, change CPU or GPU profile, pick a frame limit, skip a song, free memory, count a death and more. You can change common settings without leaving the game and without opening Deck's main window.

It is **off until you turn it on**. You then open it with a controller combination, a keyboard shortcut, Deck's tray menu or the phone remote.

**Where to find it:** sidebar > **Play** > **Game bar**. The page has three tabs, **Widgets**, **Layout & look** and **Opening**, beside a live preview of the bar.

Related pages: [Gaming](gaming.md), [Overlay](overlay.md), [Death counter](death-counter.md), [Controller](controller.md), [Phone](phone.md).

## Contents

- [How the bar behaves over a game](#how-the-bar-behaves-over-a-game)
- [Turning it on](#turning-it-on)
- [Opening and using it](#opening-and-using-it)
- [The Widgets tab](#the-widgets-tab)
- [The widgets, one by one](#the-widgets-one-by-one)
- [The Layout & look tab](#the-layout--look-tab)
- [The Opening tab](#the-opening-tab)
- [The preview](#the-preview)
- [Recommended setup](#recommended-setup)
- [Troubleshooting](#troubleshooting)
- [FAQ](#faq)

## How the bar behaves over a game

The bar is a window that stays on top but **does not take the focus**. The game stays in front, so it does not minimise, pause or "tab out". You use the bar with the controller or the mouse. Clicking it does not activate it.

Two details protect you from stray clicks in games that read the mouse directly (many shooters and rhythm games). With **Keep clicks off the game** on (the default), the bar takes the focus only while the pointer is over it and hands it back to the game when the pointer leaves, so a click on the bar never also acts in the game. With **Take the keyboard** on, the bar takes the focus when it opens instead, so the keyboard works (Esc closes it).

The bar is also the same kind of window as Deck's controller overlay and notifications: an ordinary on-top window, with no hooks into the game.

**Exclusive fullscreen.** A game in true exclusive fullscreen is drawn past the desktop, and nothing can be drawn over it without injecting into the game, which Deck never does. Use **borderless fullscreen** (or windowed fullscreen) for the bar to appear.

## Turning it on

Open Game bar and switch on **Use the game bar**. The line under the switch tells you how to open it ("Press <key> to open.", "Hold <combo> to open." or "Open from the tray menu."). Turning it on:

- adds a **Game bar** item to Deck's tray menu,
- turns on your controller combination (by default **Select + Start**) and your keyboard shortcut, if you set one,
- lets the phone remote open it.

**Open it now** (above the preview) works even when the bar is turned off, so you can try it first.

## Opening and using it

| Way to open | Details |
|---|---|
| **Controller combination** | Hold the chosen two buttons while a game is in front, for the set time. The same hold closes it. The controller is only read; your game still receives the same buttons, including the opening combination. |
| **Keyboard shortcut** | Your own key, even while a game is in front. |
| **Tray menu** | Deck's tray icon > Game bar. |
| **Phone remote** | Tap Game bar in the phone remote ([Phone](phone.md)). |
| **Open it now** | The button on the Game bar page. |

**Closing:** use the same shortcut or combination again, press **B**, press the close button, or press **Esc** when the bar has the keyboard. If you opened it over a game, switching away from the game also closes it. It can also close by itself after a time without input (see [Close by itself](#the-opening-tab)).

**With a controller** the bar opens with its first control picked. The left stick or the D-pad moves around it (holding a direction repeats), **A (Cross)** presses the picked control, **B (Circle)** closes, and **LB / RB** jump between widgets. On a slider, left and right change the value. While you use the controller, the bar's footer reads "D-pad moves · A presses · B closes · LB/RB jump". As soon as you move the mouse again it goes back to mouse mode.

**With the mouse** the footer reads "Point and click · the game gets the focus back when you move away".

The bar is drawn again only when something it shows changes. If its widgets are taller than the screen, the bar never scrolls; its text shrinks (to half at the least) until they fit.

## The Widgets tab

Widgets are the controls and readings in the bar, listed from top to bottom. A counter shows how many are shown.

- **Pick a widget** to open its settings: click its name. Click a widget in the preview to open the same settings.
- **Reorder** with the up and down arrows, or drag a row.
- The **switch** on a row hides or shows the widget without losing its settings.
- The **bin** removes the widget.
- **Add** lists the widget types that are not in the bar yet, as buttons. You can have one of each type.
- **Back to the default widgets** restores the default set.

Every widget has these settings:

| Setting | What it does |
|---|---|
| **Width** | How many of the bar's columns it takes (1, 2 or Full), when the bar has more than one column. |
| **Size** | Small, Medium or Large. Larger sizes show more (for example the cover art in Now playing, or bigger reading tiles). |
| **Title** | Shows or hides the widget's heading. |

plus the options of its type, below.

**The default widgets:** Controls (microphone and overlay switches), Profiles, Frame limit, Sound output (two devices), Free memory, Volume (two apps) and Now playing (without cover or progress bar). If you saved a layout of your own, "Back to the default widgets" is how you get the newer default back.

## The widgets, one by one

### Now playing

Pause music or skip tracks without leaving your game. Shows the current track, artist and, optionally, the app. Options: **Cover**, **App name**, **Progress bar**, **Buttons** (previous, play/pause, next). It shows "Nothing is playing" when no music is playing. The cover is shown only at Medium and Large size.

### Volume

Adjust game, chat and music volume separately. A slider and a mute button for **Everything (master)** and for the apps that are playing sound. Options: **Everything (master)**, **Apps listed** (0 to 10, default 4; the default bar uses 2), **Percent**, and **Apps never listed** (click an app to hide it from the bar for good; click again to list it). Apps appear in the list while they play sound.

### Microphone

Mute your default microphone with one press. The button reads "Mic on" or "Mic off". Option: **Level slider**. If the PC has no default microphone, the widget has nothing to show.

### Sound output

Switch between speakers, headphones and other sound outputs. The current one is ticked. Option: **Devices listed** (1 to 8, default 3).

### Free memory

Moves idle memory from programs aside and clears Windows' standby cache, using Deck's existing memory clean (the same one as **Free memory now** on [Gaming](gaming.md#the-apps-to-close-tab)). Runs once per press and reports the amount freed. Apps stay open, but they may briefly pause while loading data back into memory. Try it when memory is nearly full; Windows normally manages memory on its own.

### Readings

Check frame rate, temperatures and load at a glance. Option: **Shown**, in the order you pick them: FPS, CPU temp, GPU temp, GPU load, CPU load, Memory, CPU power, CPU clock. The FPS reading needs RivaTuner measuring the game (see [Overlay](overlay.md)). A reading the PC does not have shows "-".

### Frame limit

Sets RivaTuner's global frame limit and turns the limiter on in one press; **Off** turns it off but keeps the number. Option: **Limits offered**, a list of numbers between 10 and 1000, separated by commas (default 30, 60, 90, 120, 144; at most 10 values). A lower cap can reduce heat, fan noise and uneven frame delivery. Needs RivaTuner installed. A game with its own RivaTuner profile can have a separate limit. See [Frame limiter](overlay.md#frame-limiter).

### Fan preset

Switch between your saved fan presets. The current preset is highlighted. Needs fan control on this PC; see [Fans](fans.md).

### Profiles

Apply a saved CPU or GPU performance profile with one press, to switch between quieter operation and higher performance while playing. Options: **CPU profiles** and **GPU profiles** (show or hide each group), and **CPU profiles shown** / **GPU profiles shown** (pick which to offer; choose none to show all). Only profiles saved in Deck appear, and the active profile always shows. See [CPU](cpu.md) and [GPU](gpu.md).

### Controls

Keep your most-used switches together. Options: **On / Off under each** (a state line under each switch) and **Shown**, in the order you pick them:

- **Controller overlay**: show or hide the [controller overlay](controller.md).
- **Move the controller overlay**: the bar closes so you can drag the overlay; right-click to finish.
- **Death counter**: turn the [death counter](death-counter.md) on or off.
- **Readings overlay**: turn the [overlay](overlay.md) on or off.
- **Microphone**: mute or unmute.
- **Boost**: start or stop [Game mode](gaming.md#game-mode).
- **Frame limiter**: turn the RivaTuner limiter on or off (shows the limit).
- **Keep awake**: keep the PC and screen awake (see [Power](power.md)).

By default Controls shows the microphone and readings overlay.

### Death counter

Count deaths and correct the last fight. Shows the game's total and name, a **+1 death** button and an undo button, then (if a fight is open) the boss and the tries so far. Options: **Current fight**, **+1 and Undo**, **Fixes: won, not a boss, gave up** (three buttons for correcting what Deck detected, with an **Undo that fix** that shows for a few seconds), and **Teach in Deck** (closes the bar and opens the death counter so you can teach it this game's screens). If the counter is off, the widget says so and offers **Turn it on**. See [Death counter](death-counter.md).

### Controller overlay

Show, move or resize the controller overlay. Options: **Move and resize** (the bar closes so you can drag it; right-click when done), **Controller or keyboard** (switch between the controller and keyboard and mouse display), **Size slider** and **Opacity slider**. A button shows "Showing" or "Hidden".

### FPS drops

See why your FPS just dropped: the likely cause of each dip, from [Why did my FPS drop?](gaming.md#why-did-my-fps-drop). Option: **Drops listed** (1 to 6, default 3). Needs RivaTuner measuring the game. With no drops it shows "No drops in this game so far".

### Clock

Check the time without leaving your game. Options: **Seconds** and **Date**.

## The Layout & look tab

### Layout

| Setting | What it does | Default |
|---|---|---|
| **Shape** | **Full height** fills the screen edge. **Floating card** is only as tall as its widgets and leaves more of the game visible. A floating card's window is exactly the card, so the game keeps every click around it. | Full height |
| **Side** | Left or Right. | Right |
| **Height on the screen** | Top, Middle or Bottom (floating card only). | Middle |
| **Width** | 300 to 640 px. | 400 px |
| **Columns** | 1, 2 or 3 columns of widgets; a widget can span one or more. | 2 |

### Look

| Setting | What it does | Default |
|---|---|---|
| **Text size** | The preferred size of the bar's text and controls, 70 % to 150 %. If widgets are too tall for the screen, the bar shrinks them. Fewer widgets or more columns give them room. | 100 % |
| **Frosted glass** | Blurs the game behind the bar. | On |
| **Opacity** | How strongly the bar's colour covers the blur (20 to 100 %). With frosted glass off, how much of the game shows through: the minimum becomes 55 %, so the text stays readable. | 70 % |
| **Accent** | Deck's own accent, or one of eight colours. | Deck's accent |

Both shapes use the same widgets, width and text size.

## The Opening tab

| Setting | What it does | Default |
|---|---|---|
| **Controller** | The combination to open and close the bar: **Off**, **Select + Start**, **L3 + R3** or **Select + L3**. On PlayStation controllers Select is the Create button and Start the Options button. | Select + Start |
| **Hold for** | How long both buttons must stay pressed, 300 to 1500 ms (shown when a combination is chosen). A longer hold helps prevent accidental openings. A held combination opens the bar once; release it before using it again. | 600 ms |
| **Keyboard shortcut** | Opens or closes the bar, also while a game is in front. Click the box, press the keys, **Esc** cancels, **Backspace** clears. Use Ctrl, Alt or Win with another key, or an F-key alone. Clearing it leaves the controller, tray and phone available. | None |
| **Take the keyboard** | The bar takes keyboard focus when it opens. Esc closes it. Use it only if your game tolerates losing focus; games that minimise on losing focus may minimise when the bar opens. | Off |
| **Keep clicks off the game** | The bar takes focus while the pointer is over it and gives it back when the pointer leaves, so a click on the bar never acts in the game. Hidden when *Take the keyboard* is on. Turn it off if the game minimises when it loses focus. Deck's own panel and notifications follow this setting too. | On |
| **Close by itself** | Closes the bar after Never / 10 s / 20 s / 30 s / 1 min without input. Mouse and controller input restart the timer. | Never |
| **Opening hints** | A brief notification names your shortcut or controller combination after a game comes to the front, for your first three games. It opens without taking the keyboard. Hints stop after three game sessions, even after a restart; turning the setting off pauses the reminders and turning it on again keeps the count. | On |

## The preview

The preview on the right is a small copy of your screen with the bar drawn as it will really appear: same width, same text, same shrinking when the widgets do not fit. It does not scroll, and it follows every change as you make it. In the preview nothing is pressed: clicking a widget selects it so you can edit it.

**Open it now** opens the real bar so you can try the controls. Close it with the same shortcut or combination, **B**, the close button, or **Esc** when the bar has the keyboard.

## Recommended setup

- **Controller players:** keep **Select + Start** (or **L3 + R3** if you do not use Select), hold 600 ms, a floating card on the side opposite your game's HUD, and keep **Take the keyboard** off.
- **Keyboard and mouse players:** set a keyboard shortcut that the game does not use (for example Ctrl+Alt plus a letter, or an F-key), keep **Keep clicks off the game** on, and choose a shorter **Close by itself** time such as 20 s.
- **Mic and music first:** put Controls, Microphone, Sound output and Now playing at the top; hide the rest.
- **Competitive players:** keep the bar to Controls and Readings in a floating card, so it covers as little of the game as possible.
- **Handhelds and small screens:** use 1 column and a larger text size, and open it with the controller combination.
- **Always:** use borderless fullscreen in the game, and test with **Open it now** before relying on a shortcut in a match.

## Troubleshooting

**The bar does not appear over my game.** Check that the game runs in borderless or windowed fullscreen, not exclusive fullscreen, and that **Use the game bar** is on. Try **Open it now** with the game in front.

**The game minimises when the bar opens.** Turn off **Take the keyboard**. If it still does, turn off **Keep clicks off the game** too.

**Clicks on the bar also hit the game.** Turn on **Keep clicks off the game** and make sure **Take the keyboard** is off.

**The controller combination does nothing.** The combination is read only while a game is in front, and the controller has to be one Deck can read (see [Controller](controller.md)). Check the chosen combination matches your controller's buttons (Select and Start are Create and Options on PlayStation controllers), and try a longer or shorter **Hold for**.

**My keyboard shortcut was refused.** Deck checks that the combination can be registered and is not taken. Choose a different one.

**A widget shows nothing or "Nothing is playing" / "No outputs".** Widgets only appear where the PC has the thing: a default microphone, sound outputs, fan presets, a playing media app, or RivaTuner for FPS and the frame limit. In the preview, empty widgets still show so you can set them up.

**A widget is missing from the Add list.** You can have only one of each type, so a type already in the bar is not offered.

**The bar's text is small.** With many widgets the bar shrinks its text to fit the screen height. Remove widgets, use more columns or a wider bar.

**The hint does not show.** Hints appear for your first three game sessions only, and only when **Opening hints** is on.

## FAQ

**Is the game bar safe with anti-cheat?** Deck never injects into games. The bar is an ordinary window on top of the game, and the controller is read passively (the game still receives every press, including the opening combination). The bar does not read or write the game's memory.

**What is different from Windows' Game Bar?** It is Deck's own panel, with controls for Deck's features (profiles, frame limiter, death counter, controller overlay, Game mode) and your own layout. Deck keeps Windows' Game Bar's own windows out of RivaTuner's hooks, but does not replace it.

**Can I use the bar without a controller?** Yes: use the keyboard shortcut, the tray menu, the phone, or **Open it now**.

**Can the bar change things outside the game?** The widgets act on Deck's features and on Windows' sound and microphone settings; the bar itself does not change the game.

**Where are the settings saved?** Every change on the page is saved at once; the bar picks it up the next time it draws.
