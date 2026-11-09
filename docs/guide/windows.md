# Windows

The **Windows** page is for tidying your desktop: see every open window, pin one on top, make one see-through, snap windows into neat zones, and save a working arrangement of apps so you can bring it all back with one click.

Find it under **Desktop > Windows** in the sidebar. The page has three tabs: **Open windows**, **Snap zones** and **Workspaces**. A **Refresh** button sits beside the tabs; the open-window list also follows windows opening and closing on its own.

Deck moves windows with ordinary Windows calls, the same ones a snapping tool uses. It does not inject into any program and does not read the memory of any program, so it is safe to use with anti-cheat. Rules that move windows by themselves are paused while a game is in front.

---

## Tab 1: Open windows

The list shows every top-level app window, like the ones Alt+Tab shows. Hidden windows, tool windows, windows without a title, Deck's own windows and the desktop itself are left out. Each row shows the app's icon, the app name, the window title and a small status chip: **Open**, **Minimized**, **Maximized**, **On top**, a see-through percentage, or **Not responding** when Windows says the program has hung.

Click a row to open its controls. One window at a time is open (the first one until you pick another).

### Controls for the picked window

| Control | What it does |
|---|---|
| **Show** | Brings the window to the front (restoring it if minimized) and hides Deck's panel so you can see it. |
| **Centre** | Centres the window on its monitor, keeping its size. |
| **Minimize** | Sends it to the taskbar. |
| **Maximize** / **Restore** | Maximizes the window; if it is already maximized the button reads Restore and puts it back. |
| Snap zone buttons | A small map of the layout chosen on the Snap zones tab, one numbered button per zone. Click a number to place the window in that zone of its own monitor. |
| **On top** | Keeps the window above all others until you turn it off. Windows may refuse this for some protected programs; Deck then says "Windows didn't allow it (the app may run as administrator)". |
| See-through slider (eye icon) | Sets the window's opacity from 20% to 100%. Dragging back to 100% removes the see-through setting Deck added. |
| **Close window** | Asks the window to close, exactly like clicking its X, so the app can ask you to save. A stuck program may ignore it; use [Processes](processes.md) to end it. |

Under the controls is a line of facts about the window: its size and position (or Minimized / Maximized), the monitor number, the process ID (PID) and the memory the program uses.

Good to know:

- **See-through and games.** Making a window see-through marks it as a layered window, which Windows draws a slower way (it can lose variable refresh rate and some fullscreen optimisations). Return to 100% when you are done. Do not use it on a game window.
- **On top** and **see-through** are not remembered; they end when the window closes.
- Every action affects only the window you picked.

### Arrange windows

Beside the list is an **Arrange windows** card (shown when at least one window is open). One click arranges the open windows, the front one first, on the monitor the front window is on. Minimized windows are left alone, except by **Minimize all**.

| Button | Result |
|---|---|
| **Side by side** | The two front windows, half the screen each. |
| **3 columns** | The three front windows in columns. |
| **2 × 2** | The four front windows in a grid. |
| **Main + 2** | The front window big, the next two stacked beside it. |
| **Cascade** | Every window stacked so each title bar shows. |
| **Focus** | The front window fills the screen; every other window is minimized. |
| **Center all** | Every window centred on its monitor, its size kept. |
| **Minimize all** | Every window down to the taskbar. |

A note tells you how many windows were arranged. Arrangements are one-off actions; to bring a layout back later, save a [workspace](#tab-3-workspaces).

---

## Tab 2: Snap zones

Snap zones divide the screen into areas. Drag a window by its title bar over a zone, release, and it fills the zone. It works on the monitor the cursor is on and respects the taskbar.

### Settings

| Setting | What it does | Default | Recommended |
|---|---|---|---|
| **Snap windows into zones while dragging** | Turns drag-to-snap on or off. The zone buttons in the Open windows tab work either way. | On | On. |
| **When to show the zones** | **Tap right mouse button** or **Every drag**. | Tap right mouse button | Tap right mouse button for most people: the zones do not appear every time you merely move a window. Choose Every drag if you snap constantly. |
| **Layout** | The layout used for dragging and for the zone buttons. | Halves | The one you use most; change it any time. |

How dragging works:

- **Tap right mouse button** (the default): start dragging a window, tap the right mouse button once to show the zones (tap again to hide them), then release the left button over a zone.
- **Every drag**: the zones show as soon as you start dragging; release over a zone.
- A banner reads "release over a zone to snap · right-click hides zones" while the zones show.
- If you release outside every zone, the window stays where you dropped it.

To turn the feature off, switch off "Snap windows into zones while dragging".

### The built-in layouts

| Layout | Zones |
|---|---|
| **Halves** | Two zones, left and right, half each. |
| **Focus + side** | A large left zone (68%) and a narrow right one (32%). |
| **Thirds** | Three equal columns. |
| **Wide center** | A narrow left (20%), a wide middle (60%), a narrow right (20%). Good for ultrawide monitors. |
| **Quarters** | Four corners. |
| **Main + stack** | A large left zone (60%) and two stacked zones on the right. |

### Open an app in its own zone

Below the layout choice is the window rules section.

| Setting | What it does | Default |
|---|---|---|
| **Open an app in its own zone** | When a window of a chosen app opens, Deck moves it into the zone you saved for that app. | Off |

To add a rule, pick an open app, a layout and a zone, then press **Remember**. The rule is listed as "Zone N of layout name". Press **Remove** to delete it. If a rule's layout or zone no longer exists, the row says "Its layout or zone is gone. Remove it or remember it again."

Behaviour you should know about:

- Each window is moved once, a moment after it appears. If you move it afterwards it stays where you put it.
- Only real windows with a title bar are moved; tool windows, pop-ups and minimized windows are not.
- Deck's own windows are never moved.
- Nothing moves while a game is in front.
- You can have up to 60 rules.
- Deck notices new windows through a Windows event that only reports that a window was shown. It sees no keystrokes and no mouse input.

### Remember windows for each set of monitors

| Setting | What it does | Default |
|---|---|---|
| **Remember windows for each set of monitors** | Keeps the arrangement of your open windows for the monitors connected now, and puts the windows back when the same set of monitors returns (a dock, a TV). | Off |

How it works:

- While the setting is on and the monitors have stayed the same for about 20 seconds, Deck saves where your windows are for that monitor set and keeps it up to date as you rearrange.
- When a monitor set that Deck has seen before comes back and stays steady, it moves matching open windows back and shows a "Windows put back" notification.
- Up to 8 monitor sets are kept, each with up to 60 windows. Nothing is saved or restored while a game is in front.
- **Connected now** names the monitors currently connected. **Remember windows now** saves immediately; **Put them back now** restores the saved arrangement for this set immediately.
- Each remembered set is listed with how many windows it holds and when it was kept. **Forget** deletes one.
- It only moves windows of programs that are already open; it launches nothing. To launch programs too, use a [workspace](#tab-3-workspaces).

Both window rules are stored in `window-rules.json` beside Deck's settings.

---

## Tab 3: Workspaces

A workspace saves which apps are open and where their windows are. Opening it brings everything back: it moves windows that are already open and launches the ones that are not.

### Save and open

1. Open and arrange your apps the way you want them.
2. Press **Save open windows** and give the workspace a name (for example Coding, Gaming, Chill).
3. Later, press **Open** on its row.

Each row shows the apps' icons, the number of windows, and short chips for extras ("Closes ...", "Sound to ...", "Keeps the PC awake").

### What is saved

For each window: the program, its title, its position and size, and whether it was normal, maximized or minimized. Windows Store system windows are skipped. If a saved position is on a monitor that is not connected now, the window is left where it is instead of being thrown off screen.

### What Open does, in order

1. Closes the apps listed under "Close these apps when opening", if any.
2. Switches the sound output, if one is set.
3. Turns Keep awake on, if set.
4. Matches saved windows to open windows by title first, then by order, so several windows of the same app each get their own saved place.
5. Launches programs that are not running (one launch per program, as your normal user, not elevated) and waits up to 20 seconds for their windows to appear, then places them.
6. Shows a notification saying how many windows were placed, which programs could not be started (for example the program was moved or uninstalled) and which were slow to appear.

### The "..." menu on each workspace

| Item | What it does |
|---|---|
| **Edit** | Opens the workspace editor (below). |
| **Replace with open windows** | Overwrites the saved windows with what is open now, keeping the name and the extras. |
| **Delete** | Deletes the workspace after asking. Only the saved layout is deleted; no program is touched. |

### Edit workspace

| Field | What it does |
|---|---|
| **Name** | The workspace's name. |
| **Close these apps when opening (they get the chance to save first)** | Comma-separated program names, for example `EpicGamesLauncher.exe, Steam.exe`. ".exe" is added if you leave it off. Deck asks them to close like clicking X, so they can save, waits up to about 8 seconds, then ends leftovers that have no window (tray helpers). A program still showing a window, probably a "save changes?" box, is left open and named in the notification. |
| **Switch sound to** | An output device. "Leave it" does nothing. See [Sound and mic](sound.md). |
| **Keep the PC awake** | Turns Keep awake on while the workspace is open. You turn it off yourself on the [Power](power.md) page. |

### Recommended setup

- Turn **Snap windows into zones** on with **Tap right mouse button** and the **Halves** or **Thirds** layout. Add **Open an app in its own zone** for the three or four apps you always want in the same place (a chat app, a music player).
- If you use a laptop with a dock or a TV, turn on **Remember windows for each set of monitors**.
- Make one workspace per activity (work, play, streaming). Use **Close these apps** to shut launchers and heavy background apps in a gaming workspace.

---

## Troubleshooting

**A window is not in the list.** The list only shows normal app windows. Tool windows, windows without a title and Deck's own are hidden. Minimized windows are listed.

**"Windows didn't allow it" when turning On top on.** Windows refused to change that window, which can happen with protected or higher-privileged programs.

**Dragging does not show zones.** Check that "Snap windows into zones while dragging" is on, and remember that in the default mode you have to tap the right mouse button during the drag.

**A window snapped with the wrong size.** A window with a fixed size may not fill the zone. The zone is worked out from the monitor the cursor is on while dragging, and from the window's own monitor for the zone buttons.

**An app does not open in its zone.** Make sure "Open an app in its own zone" is on, the rule is listed as "Zone N of ...", and no game is in front. A window you moved yourself is not moved again. Programs that open a splash screen first may use up their one move on the splash; remember the rule again while the main window is open.

**A workspace launched nothing.** Programs that are not running are launched from the exact path saved. If the program moved or was uninstalled, the notification names it. Fix it with **Replace with open windows**.

**A workspace put windows in odd places.** Arrange them again and press **Replace with open windows**.

## FAQ

**Is this safe with anti-cheat?** Yes. Deck only asks Windows to move or resize windows and watches for "window shown" events. It never injects into or reads from games. Automatic window moves are paused while a game is in front.

**What does Deck change on my PC?** Only the position, the on-top flag and the opacity of windows you choose. Workspaces can also switch your default sound output and keep the PC awake, if you ask them to.

**Does it work with multiple monitors?** Yes. Snapping and arranging use the monitor of the window (or the cursor); monitor numbers are shown in each window's info line.

**Does it survive a restart?** Layouts, rules, remembered monitor sets and workspaces are saved to disk. Which windows are on top or see-through is not.
