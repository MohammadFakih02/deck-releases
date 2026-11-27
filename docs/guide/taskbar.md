Where to find it: Taskbar › Taskbar

# Taskbar and Clock Contrast

Windows' own taskbar settings, what Windhawk does to the taskbar, and Clock Contrast, which keeps the taskbar clock readable on any background.

The page has two tabs, **Look** and **Clock Contrast**. Tabs for Windhawk's clock, bar style, Start menu and mouse mods appear when Deck can control those mods.

## Look

Windows' own taskbar settings in one place. Deck injects nothing here. Each row is the same setting as in [Windows tweaks](tweaks.md), so it keeps the value from before your change and can be undone there.

- **On the bar:** Taskbar alignment, Search on the taskbar, Task view, Widgets, Chat and Meet now, Badges on taskbar apps, Show desktop in the far corner, Transparency effects.
- **Buttons:** Combine taskbar buttons on the main display and on other displays.
- A row your version of Windows doesn't offer says so instead of showing a control.
- A circular-arrow icon after a name means the change shows only after Explorer restarts. **Restart Explorer** appears when changes wait for it. Deck asks first and won't do it while a game is in front. The taskbar and open folders close for a moment; other apps stay open.
- **Taskbar settings** opens Windows' own taskbar page; **All Windows tweaks** opens the Taskbar part of Windows tweaks.

The Windhawk card sits under these cards.

## Windhawk

Windhawk does the changing; Deck only turns its mods on and off, reads what they do, and can keep Windhawk out of games. By default Windhawk loads into almost every program, so it can reach games installed outside the usual game folders, and anti-cheat may flag that.

- **Top line:** the Windhawk version, how many mods are on, and the game safety state: **Only in the taskbar and Start menu** (Windhawk skips every other program), **Games kept out** (every game Deck knows is excluded), or a warning chip **In N games**. If Windhawk is not installed, the card says **Taskbar mods need Windhawk**.
- **Game safety** shows only when something needs doing, for example "Windhawk can load into 37 games".
  - Show games lists those games (hover a name for its folder).
  - **Only the taskbar and Start menu** is the main fix. Windhawk then skips every program except the Windows shell programs your mods run in (Explorer, Start and Search). A mod that runs anywhere else is named in the confirm and stops working. Your own Windhawk entries stay as they were. Mods then load a moment later, which a few mods don't like; if one breaks, undo the change and use **Keep out of games** instead.
  - When you later turn on a mod that runs in a program Windhawk now skips, the card says so and **Add** lets that program in (shell programs only).
  - **Other ways › Keep out of games** adds only the game folders Deck knows to Windhawk's exclusion list. New games need adding again.
  - Both need administrator. Without it, **Open Windhawk** takes you there.
  - **Restart Windhawk to apply:** Windhawk reads its lists when it starts. Restart the PC, or exit Windhawk from its tray icon and start it again. Deck doesn't restart Windhawk itself.
  - **Undo** is in **What Deck changed**. It restores your exact lists; if you changed them in Windhawk since, it removes only what Deck added.
  - Other findings (a game in Windhawk's inclusion list, a mod that runs outside the shell) are listed under **Change these in Windhawk**.
- **Mods:** each mod with its version, the programs it runs in, and an on/off switch. A chip shows only when something is wrong: **Not loaded** (on, but not loaded into the shell yet, for example after a Windows update) or **Refused** (it runs outside the shell, so Deck won't turn it on). Deck doesn't change mods while a game is in front. Changing a mod needs administrator.
- If the shell kept crashing, a banner says which mod Deck turned off; **Undo** turns it on again.

## Clock Contrast

- **Run Clock Contrast:** on or off. Off gives the clock its normal colors back. While the separate ClockContrast app is running, Deck leaves it alone and the **Live** card says "The separate ClockContrast app is painting the clock. Close it first."
- **Status:** Running or Off, and the painter's state: **Painter working**, **Painter missing**, **Painter too old** (older than 2.2; update it in Windhawk), **Painter problem** or **Clock position unknown** (for a minute or so after a Windows update).
- Behind a full-screen game or video it checks the screen less often but keeps going.
- **Pause behind full-screen games** (off by default): while a game fills the screen, the clock keeps its last colors and the Live card says **Paused: full-screen game in front**.
- **Live:** a sample clock in the chosen colors on the patch behind the clock, the time and date contrast (Lc), light or dark text, where the clock position comes from, how much of one core it uses, and the last changes.
- **Settings:** a preview shows the clock on dark, light, wallpaper and hint-of-color backgrounds and updates while you change anything.
- **Style:** **Subtle** (softer color, a little more contrast), **Balanced** (standard) or **Vivid** (stronger colors). **Custom** shows when your settings match no style.
- **Reaction:** **Calm** (holds a new color about 0.7 s), **Quicker** (about 0.4 s) or **Slow** (about 1.2 s, fewer light/dark flips). **Slower on battery** checks the screen less often when unplugged.
- **Customize** (folded): **Time readability**, **Date readability**, **Colorfulness** (50 to 150 %), **Two colors** (the date gets its own color), **Silver after** (how long a colorless screen waits before the clock turns silver), **Smallest color area**, and **Reset to defaults**.

Changes apply and save at once; there is no Save button. Clock Contrast works on the main screen with the taskbar at the bottom.
