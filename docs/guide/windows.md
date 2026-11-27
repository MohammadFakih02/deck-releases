Where to find it: Windows › Arrange windows

# Arrange windows

Pin, fade and snap windows, arrange them in one click, and save workspaces that bring back your apps, windows and settings.

The page has three tabs: **Open windows**, **Snap & rules** and **Workspaces**. Deck moves windows with ordinary Windows calls, like any snapping tool, and never injects into a program, so it is safe with anti-cheat. Nothing moves automatically while a game is in front.

## Open windows

Every app window Alt+Tab would show, with a status chip: **Minimized**, **Maximized**, **Always on top**, a see-through percentage, or **Not responding**. The list follows windows as they open and close; **Refresh windows** reads it again.

Select a row for its controls:

| Control | What it does |
|---|---|
| **Show** | Brings the window to the front and hides Deck. |
| **Center** | Centers it on its monitor, keeping its size. |
| **Minimize** / **Maximize** / **Restore** | As in the window's own title bar. |
| Zone buttons | One numbered button per zone of your snap layout. |
| **Always on top** | Keeps the window above all others. Windows may refuse this for a program running as administrator. |
| **Opacity** | 20 % to 100 %. At 100 % the see-through setting is removed. |
| **Hide to tray** (in **Options**) | Takes the window off the screen and taskbar while the program runs. |
| **Close window** | Like clicking its X, so the app can ask to save. To end a stuck program, use [Processes](processes.md). |

Below the controls: the window's size and position, monitor, process ID and memory.

- A see-through window is drawn a slower way and can lose variable refresh rate. Don't use it on a game.
- Always on top and see-through end when the window closes.

### Hidden to the tray

Hidden windows are listed under **Hidden to the tray** and in Deck's tray menu, each with **Show**. Every hidden window comes back when Deck quits, or at the next start if Deck closed badly. Games, full-screen windows, Deck itself, the desktop and the taskbar can't be hidden.

### Arrange all windows

One click arranges the open windows on the front window's monitor, front window first. Minimized windows are left alone.

| Button | Result |
|---|---|
| **Side by side** | The two front windows, half the screen each. |
| **3 columns** | The three front windows in columns. |
| **2 × 2** | The four front windows in a grid. |
| **Main + 2** | The front window big, the next two beside it. |
| **Cascade** | Every window stacked so each title bar shows. |
| **Focus** | The front window fills the screen; the rest are minimized. |
| **Center all** | Every window centered, its size kept. |
| **Minimize all** | Every window down to the taskbar. |

To bring an arrangement back later, save a [workspace](#workspaces).

## Snap & rules

Snap zones divide the screen. Drag a window over a zone and release; it fills the zone on the monitor under the pointer.

| Setting | What it does | Default |
|---|---|---|
| **Snap while dragging** | Drag-to-snap on or off. Zone buttons work either way. | On |
| **When to show the zones** | **Tap right-click** (tap the right button during a drag to show or hide the zones) or **Every drag**. | Tap right-click |
| **Layout** | **Halves**, **Focus + side** (68/32), **Thirds**, **Wide center** (20/60/20, for ultrawides), **Quarters** or **Main + stack**. | Halves |

Release outside every zone and the window stays where you dropped it.

### Fill the zones

**Fill the zones with open windows** puts the open windows, front first, into the free zones on each monitor. Windows already in a zone stay. **Undo** puts them back. A window running as administrator can't be moved and is named.

**Export zones** and **Import zones** move layouts between PCs; importing adds layouts and never replaces yours.

### App zone rules

When a window of a chosen app opens, Deck moves it into that app's zone. Off by default.

1. Turn on **App zone rules**.
2. Under **New rule**, type or pick the app (for example `code.exe`), then click a zone.
3. Choose **When**: **Place it when it opens** or **Keep it in the zone** (moved back if it leaves, not while you drag).
4. Optionally narrow it by **Title** or **Window class** (is exactly or contains).
5. Press **Add rule**.

- The most specific matching rule wins. Up to 60 rules.
- A window you move yourself after placement stays put.
- Only real windows with a title bar are moved; Deck's own windows and games never are.
- If a rule shows **Layout or zone is gone**, remove it and add it again.

### Excluded apps

Windows listed here (by **Program**, **Title** or **Window class**) are never moved by snap zones, rules or Fill the zones. Up to 60 entries.

### Monitor sets

**Use this layout when these monitors are connected** ties a **Snap layout** or a **Workspace** to the monitors connected now: pick one and press **Use it for these monitors**. A few seconds after the set changes (a dock, a TV), the open windows are arranged that way.

**Remember windows for each set of monitors** (off by default) saves where your windows are for each set and puts them back when the same set returns.

- **Connected now** names the current monitors. **Remember windows now** saves at once; **Restore windows** restores at once.
- Up to 8 sets of 60 windows. **Forget** deletes one.
- It moves only windows already open. To start programs too, use a workspace.

## Workspaces

A workspace saves which apps are open and where their windows are. **Open** brings it back: it moves open windows and starts the missing apps. A workspace is also a desktop scene: the same **Open** can switch CPU and GPU profiles, close apps, switch the sound output, set brightness, turn notifications off and keep the PC awake.

### Save and open

1. Arrange your apps.
2. Press **Save open windows** and name it (Coding, Gaming, Chill).
3. Later, press **Open** on its row.

Each row shows the apps, the window count and chips for the extras ("CPU: …", "Closes …", "Sound to …", "Brightness 70%", "Notifications off", "Keeps the PC awake").

### What Open does, in order

1. Switches the CPU profile, then the GPU profile.
2. Closes the apps you listed.
3. Switches the sound output.
4. Sets the brightness of every monitor that allows it.
5. Turns notifications off.
6. Turns on Keep awake.
7. Places saved windows on matching open windows (by title, then order).
8. Starts missing programs as your normal user and places their windows (waiting up to 20 seconds).

Each part runs even if one before it failed, and a part already as wanted isn't touched. A window saved on a monitor that isn't connected stays where it is. Afterwards the card shows **Last opened**: each part (**Set**, **Already set** or **Failed**) and each window (**Placed**, **Started and placed**, **Failed** or **Not moved**).

### Now and Restore

**Now** compares each part with your PC: **Same** or **Differs**, with both values. After **Open**, **Restore** puts back only what that Open changed: profiles, sound output, brightness, notifications, Keep awake and windows that were already open. A part you changed yourself since shows **Changed since** and is left alone. Closed apps don't reopen.

### The More menu

- **Edit** opens the editor.
- **Replace with open windows** saves what is open now, keeping the name and extras.
- **Delete** removes the workspace after asking. Only the saved layout is deleted.

### Edit workspace

| Field | What it does |
|---|---|
| **Name** | The workspace's name. |
| **Close these apps when opening** | Program names, comma-separated (`Steam.exe, EpicGamesLauncher.exe`). Deck asks them to close so they can save, waits about 8 seconds, then ends leftover tray helpers. An app still showing a "save changes?" box is left open and named. |
| **Switch sound to** | An output device, or **Leave it**. See [Mixer](sound.md). |
| **CPU profile** / **GPU profile** | A profile to switch to, or **Leave it**. |
| **Brightness** | 10 to 100 % for monitors that allow it, or **Leave it**. |
| **Notifications off (Do not disturb)** | Turns off Windows' app notifications; Restore turns them back on. |
| **Keep awake** | Keeps the PC awake. Turn it off on [Keep awake](power.md) or with Restore. |
| **Start order** | For each app that isn't running: **Order** (1 starts first, 0 last) and **Delay (s)**. |

## Recommended setup

- Keep **Snap while dragging** on with **Tap right-click** and **Halves** or **Thirds**. Add app zone rules for the few apps you always want in one place.
- With a dock or a TV, turn on **Remember windows for each set of monitors**.
- Make one workspace per activity. In a gaming workspace, close launchers and heavy background apps.

## Troubleshooting

- **A window isn't listed.** Tool windows, windows without a title and Deck's own are left out.
- **Always on top or a move is refused.** Windows blocks changes to programs running as administrator.
- **Dragging shows no zones.** Check **Snap while dragging**, and in **Tap right-click** mode tap the right button during the drag.
- **A window doesn't fill its zone.** Some windows have a fixed size.
- **An app doesn't open in its zone.** Check **App zone rules** is on and no game is in front. An app with a splash screen may spend its move on the splash; use **Keep it in the zone**.
- **A workspace started nothing.** The program moved or was uninstalled; the notification names it. Use **Replace with open windows**.

## FAQ

- **Safe with anti-cheat?** Yes. Deck only asks Windows to move windows and never touches games.
- **What does Deck change?** Only window position, on-top and opacity, plus what a workspace sets; Restore undoes those.
- **Does it survive a restart?** Layouts, rules, monitor sets and workspaces do. On-top and see-through don't.
