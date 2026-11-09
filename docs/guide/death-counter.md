# Deaths (the death counter)

The death counter counts how often you die in any game, and per boss: tries, wins, time spent, records and a history of every play session. In the games it knows it counts by itself. In every other game you start by counting a death by hand, and Deck can then learn to recognise that game's death screen.

**Where to find it:** sidebar > **Play** > **Deaths**. The page has five tabs: **Now**, **Bosses**, **History**, **Games** and **Settings**.

**Anti-cheat and safety.** The death counter never reads a game's memory and never injects anything into a game. It does one of three things: reads a save file (read-only, never changed), looks at the picture of the game window the way a screen recorder does, or waits for you to press a button or shortcut. The in-game counter is an ordinary click-through window that never takes focus. Deck's keyboard shortcuts use Windows' standard hotkey mechanism, and the controller combo only reads the controller, like any other program that shows controller input.

## Contents

- [How counting works](#how-counting-works)
- [Now tab](#now-tab)
- [Bosses tab](#bosses-tab)
- [History tab](#history-tab)
- [Games tab](#games-tab)
- [Death counter settings](#death-counter-settings)
- [OBS text files](#obs-text-files)
- [Privacy: what is kept and where](#privacy-what-is-kept-and-where)
- [Recommended setup](#recommended-setup)
- [Troubleshooting](#troubleshooting)
- [FAQ](#faq)

## How counting works

Deck has four ways to count a death. You can use any mix of them.

| Way | What it needs | Notes |
|---|---|---|
| **By hand** | Nothing | The **+1 death** button on the Now tab, the tray menu, Home's death controls, the **+1 death shortcut** and the **Controller combo**. Works in every game, and counting a death in a new game is how you tell Deck to start watching it. |
| **Save file** | A game with a save reader | Deck reads the game's save file while the game runs and counts the rise in the death total. Saves are never changed. Built in for Celeste and Dark Souls: Prepare To Die Edition. A rise of more than 20 on the same character at once is not counted, as a safeguard. |
| **Death screen** | The game must be visible to Deck (borderless or windowed) | Deck looks at the game window a few times a second and counts a death when the game shows its death screen ("YOU DIED", "GAME OVER" and so on). Words are read with Windows' own text reader (or the optional OCR pack). A screen with no words, a symbol or a flash can be taught once. |
| **Boss health bar** | Screen watching on | Deck notices a centred boss health bar, reads the name beside it, opens that boss's fight, times the try and closes the fight when the bar empties or a victory banner shows. |

Deck decides a death carefully: a game's own death words in the place it shows them count at once, while common words need two reads in a row. After a death there is a cooldown of about 8 seconds and the screen has to clear before the next one can count, so a long death screen never counts twice.

Deck knows a game by its program (the exe), so the same game bought from Steam, GOG, Game Pass or EA is one game with one history. Fullscreen browsers and video players are never counted as games.

**Games with built-in extras.** Deck ships extras for a list of hard games: where the boss bar and boss name sit, the player's own bars, and the death words. The list includes Dark Souls (Prepare To Die Edition, Remastered, II and III), Demon's Souls, Bloodborne, Elden Ring and Nightreign, Sekiro, Lies of P, Nioh and Nioh 2, Wo Long, Wuchang, Black Myth: Wukong, Phantom Blade Zero, The First Berserker: Khazan, Remnant II, Salt and Sanctuary, Salt and Sacrifice, Ashen, Cuphead and Celeste. The Games tab shows the live list under **Games with presets**, and marks presets that haven't been checked in the game yet. These extras are never a whitelist: any other game works once you count a death in it.

## Now tab

The Now tab is the main view for the game in front (or the last game you played).

- **Count deaths in this game** (switch at the top): turns counting on or off for this one game. A game that is off shows "Not counted". Games Deck can't read yet start off until you turn counting on, count a death or teach a screen.
- **Boss area:** the name of the current boss fight and two big numbers, deaths on **this boss** and in **this game**. The label above it says whether you are "Fighting" (and whether its health bar is up) or "No boss fight".
- **Unconfirmed** chip and **Confirm boss:** when Deck opened a fight by itself from a single read of the screen and isn't sure of the name, it says so. Press **Confirm boss** if the name is right, or rename it under Fight actions.
- **+1 death:** counts a death in the game and in the current fight.
- **Undo death:** takes back the last counted death. Greyed out when there is nothing to undo.
- **Boss defeated:** appears during a fight; marks the boss beaten.
- **Start boss fight** with a **Boss name** box: starts a fight by hand. The **Again:** chips start a fight with a boss name you used before. While a fight is open, **Fight actions** lets you **Rename fight**, **Abandon fight** (stop it without a win) or mark it **Not a boss** (see below).
- **Last tries:** a small bar chart of how long your last tries lasted; the newest is on the right.
- **This session / Last session:** deaths this session, deaths in this game, how long you have been playing, the average time between deaths and the deadliest boss this session.
- **All-time records:** longest try, quickest win (fewest deaths), deadliest boss and most deaths in a session. **Share** copies or saves a picture of the game's numbers.
- **Manage learned screens** opens the Games tab.
- The line at the bottom says how this game is being counted automatically (for example "Counting automatically from the game's save file" or "Watching for death screens and boss health bars"). If it says the screen is unreadable, see [Troubleshooting](#troubleshooting).

**Not a boss.** If Deck opened a fight for something that isn't a boss, use **Not a boss** on the fight. The deaths stay in the game's total and nothing is deleted. When the screen read can't be a real boss, a tick box offers to ignore that name in this game from now on.

## Bosses tab

One card per boss fought in the game, most recent first, with a **Boss** drop-down to jump to one.

Each boss card shows: **Fighting** or **Beaten**, deaths, time on this boss, longest try, the try it was beaten on (or the number of tries), and a line chart of how long each try lasted. If your tries are getting longer, the card says you are learning the fight. For an unbeaten boss it shows how close you got ("phase 2, 18% of its health left") where Deck saw the bar. You can type a **note** for the boss (a strategy, a reminder, up to 500 characters; it saves when you leave the box, and can appear on the card after a death).

Under **Share or merge this boss entry**:

- **Copy boss picture** and **Save boss picture...** make a shareable image of that boss's numbers.
- **Same boss as:** fixes a misread name. If Deck read "aldii" and "Aldrich" is the real name, choose the real boss and press **Combine boss counts**. Deaths and fights are combined, the correction applies to future reads, and the original names stay in History. Undo it with **Undo that**, or later from Settings > Recognition rules & testing.

For games with boss fights the tab also shows **The boss's health bar and name**: **Show where they are** lets you tell Deck where the bar and name sit (see [Teaching and setting up a game](#teaching-and-setting-up-a-game)); **Forget the bar** and **Forget the name box** remove your marks.

## History tab

History is one card per play session: day and time, length, number of deaths, bosses beaten and a small chart of deaths over time. The newest session opens by itself. Inside a session:

- **Fought:** the bosses fought.
- **Attempt splits:** every try with its boss, win or death, length, and the conditions recorded at the time (your CPU and GPU profile and the CPU and GPU temperature, where available).
- A timeline of events: deaths (with the boss and the % health left where known), fights started, wins, abandoned fights, undos and renames. Long runs of deaths are folded; each "Show 10 more deaths" click opens ten.
- Older sessions are marked "about": their lengths are estimated from when deaths were counted, because play time wasn't recorded then.

**Fights to check** lists recent fights that Deck opened by itself and nobody has confirmed. For each: **That's right**, **Rename** or **Not a boss**.

**Correcting mistakes.** Every line has a **More** (three dots) menu. Nothing is ever deleted: a correction strikes a line out or adds a note to the history, and each one is followed by an **Undo that** bar for ten seconds.

| Menu item | What it does |
|---|---|
| That wasn't a death | Strikes the death out; counts, boss cards and stats leave it out. |
| Count it again / Bring this fix back | Reverses the above. |
| Undo this fix | Takes back a correction you made. |
| Rename this fight... | Gives that one past fight another boss name. |
| I won that fight / I didn't win that fight | Sets the fight's result. |
| That wasn't a boss fight... | See Not a boss above. |
| Add a missed death here | Adds one death to that fight. |
| Why is this here? | Explains where the line came from. |
| Leave this line out | Counts and stats are worked out without the line. |

**History file problems.** If a game's history file can't be read or saved, or it changed outside Deck, a notice appears at the top of the page with the choices it needs (for example **Keep Deck's version**, **Use the file on disk**, or **Add them** for deaths counted while the file couldn't be saved). Deck never overwrites a history it can't read: it keeps the old version beside it.

## Games tab

- **Your games:** every game you have counted deaths in, with its total and when it was last counted. **Export** saves that game's history as a CSV file; **Show** switches the other tabs to that game. A game turned off shows an "off" chip.
- The line under the list says how many games the shared library covers.
- **All games:** total deaths, time played and bosses beaten across all games, deaths per week for the last 12 weeks, the deadliest games and the deadliest bosses. **Export everything** saves the lot as CSV.
- **Death-screen library > Add a death screen a friend taught:** paste a share code starting `deck-death-screen:` and press **Add**.
- **Learned screens** for the chosen game (use the **Game** drop-down): the guess card, the Set up steps, the death and victory screens Deck learned, and the teaching card. See below.
- **Games with presets:** the built-in list described above.

### Teaching and setting up a game

Teaching is for a game whose death screen has no readable words, is in an unsupported language, or is only a symbol or flash. You do it once.

1. Count a death by hand (or let Deck count one) while the death screen is still up, or just after.
2. Go to Deaths > **Games** and choose **Show the last 10 seconds**. Deck shows a strip of pictures from just before.
3. Click the picture where the death screen is clearest. Deck learns which part of the screen changed and keeps a small copy of the picture you chose. The rest stays in memory.

You can teach up to three death screens per game and three victory screens. If Deck spots a screen that appeared before several deaths you counted by hand, it asks **Is this the death screen?** Press **Yes, that's it** to count it from now on, or **No** to stop it suggesting that one.

Wrong death counted? Find the screen that did it in the list, press **Forget** (the deaths it counted stay; delete wrong ones in History), then teach the real one.

**Set up (game name)** has optional steps that improve accuracy:

| Step | What it is |
|---|---|
| Your own bars and items, and a boss's posture bar | Drag boxes (up to 8) over your own health bars and item slots so Deck never takes them for a boss. Press **Mark them**, then **Save**. |
| Boss health bar and name | Click the boss's health bar, then drag a box around its name (or use **Name is above the bar** / **Name is below it**). Deck shows what it reads in your box. Do this during or just after a fight. |
| Death screen | Pick it from your last death. |
| Boss kill screen | Pick the victory screen after you mark a boss beaten. **This game has none** if the game shows nothing when a boss dies. |

**Victory screens** make Deck mark the open fight as beaten when they show.

**Sharing.**

- **Share with a friend** copies a share code of your death screens for the game; a friend pastes it under Death-screen library.
- **Submit to the shared library** copies the code and opens the death-screen report form on the public deck-releases GitHub site. Paste the code and submit. It is shared with everyone once the maintainer has checked it. Needs the shared library setting on.
- The shared library holds death screens other players taught. Deck downloads a newer copy at most once a day (one plain request; nothing about you is sent), and every build ships with a copy. If a shared screen is wrong for a game, **Don't use them** turns the library's screens off for that game only; yours still count.

## Death counter settings

These live in **Settings › Death counter**. They are in two columns: counting on the left, the in-game counter on the right. Most rows have a "?" with more detail.

### Counting

| Setting | What it does | Default |
|---|---|---|
| **Death counter** | Master switch for counting, the tray menu, shortcuts and the in-game counter. Turning it off keeps your history. | On |
| **+1 death shortcut** | A key combination that counts a death, also while a game has focus. Use Ctrl, Alt or Win with a key, or an F-key alone. | None |
| **Undo shortcut** | Takes back the last death. | None |
| **Controller combo** | Hold **View** (Select) with **D-pad Down** for one second to count a death, **D-pad Up** for one second to undo. A quick press never counts, and one hold counts once. The game sees these buttons too, so leave it off if View opens a map or menu. Deck only reads the controller. Works only while a counted game is in front. | Off |

### Streaming text files

See [OBS text files](#obs-text-files).

### Automatic counting

| Setting | What it does | Default | Recommended |
|---|---|---|---|
| **Read save files** | Counts deaths from supported saves (Celeste, Dark Souls: PtDE). Saves are only read. | On | Leave on. |
| **Shared death-screen library** | Recognise death screens other players have taught. | On | Leave on unless you want only your own. |
| **Watch for death screens** | While a game is in front, Deck looks at its window a few times a second and reads the middle of the screen once it settles. Pictures stay in memory. | On | Leave on. |
| **Read text with the OCR pack** | A second, optional text reader for names and symbols Windows misses (for example Sekiro's death screen). Turn on, then press **Download** (about 24 MB). Turning it off deletes the pack. | Off | On if boss names or a death screen aren't read. |
| **Watch in** | **Games Deck knows** (catalogue, taught or shared screens, marked areas, games you counted a death in) or **Every game**. Boss fights still need a boss list or a marked bar. | Games Deck knows | Leave, unless a new game isn't being watched. |
| **Find boss fights by themselves** | Opens and times fights when a boss bar appears. | On | Leave on for boss games. |

The last three rows (watch in, OCR pack, boss fights) appear only while **Watch for death screens** is on.

**Recognition rules & testing** (a folded section, shown while screen watching is on) holds:

- **Keep a text log for testing:** writes down what the watcher read and decided, as text only (bar positions, health, recognised words and decisions). No pictures. Off by default, at most 20 MB per game, never sent anywhere. **Delete it** removes the logs without touching your counts.
- **Keep pictures for testing:** saves small grey pictures around deaths and boss names so recognition changes can be tried on your own play. Off by default, deleted after seven days, at most 200 MB. **Delete them** removes them.
- **Not bosses:** names you marked as not bosses. Press a name to let Deck open fights for it again.
- **Ignored in (game):** names ignored in this game. Remove one to allow it again.
- **Same boss in (game):** merged boss names. Remove one to count it separately again.

### Start over

**Reset all death counts** opens a red warning. It wipes counts, fights, bosses, tries, sessions, records and boss notes for every game. Your settings and the death screens Deck learned stay. You must type `reset` to enable the button. A copy of the old history is kept in Deck's data folder. This can't be undone from the page.

### In-game counter

A preview at the top shows the counter and the card as they will look.

| Setting | What it does | Default |
|---|---|---|
| **Show the counter in games** | A counter over the game, on the game's monitor. Clicks pass through and it never takes focus. | On |
| **Style** | **Skull and number**, **Ring** (fills toward the deaths your last boss took) or **Huge number**. | Skull and number |
| **Counts** | During a fight: **This boss**, **The game** or **Both**. | Both |
| **Outside a fight** | **The game's total** or **Nothing**. | The game's total |
| **In every game** | Show it even in games without recorded deaths. Normally it shows only in games Deck knows or where you counted deaths. | Off |
| **Corner** | Top, top left, top right, bottom, bottom left or bottom right. | Top |
| **Size** | 50% to 200%. | 100% |
| **Opacity** | 20% to 100%. | 90% |
| **Red edges on a death** | Briefly flashes the screen edges red. | Off |
| **Show in screenshots and recordings** | Lets recorders and screen shares capture the counter. If you hide it, some recorders stop capturing while it shows, and NVIDIA Instant Replay can switch itself off. | On |

**Card after a death** (folded section):

- **Open the card after a death:** the counter opens into a summary for a few seconds, then returns. Default on.
- **Seconds:** how long it stays, 2 to 10 (default 5).
- **What the card shows** (press a chip to turn a line on or off): **Try number**, **This try's length**, **Boss health left**, **Time on the boss**, **This session**, **Recent tries** (bars), **Highlights** ("Your longest try yet", your 100th death) and **My boss note**. Everything except **My boss note** is on by default.

If the counter is missing in a game, try borderless or windowed mode: games in exclusive fullscreen hide other windows.

## OBS text files

**Write text files for OBS** (Settings > Streaming text files) writes three files into a folder you choose, updated whenever the numbers change:

| File | Contents |
|---|---|
| `deaths.txt` | The game's total deaths. |
| `boss.txt` | The current boss's name (empty between fights). |
| `bosses.txt` | One line per boss: `Boss name: deaths`. |

In OBS, add a **Text (GDI+)** source and tick **Read from file** for each file you want. Choose a folder first (**Output folder** > **Choose folder**); the switch won't turn on without one. Use a dedicated folder. If Deck can't write there, the page says "Couldn't save the text files": pick a writable folder. Off by default.

## Privacy: what is kept and where

- Pictures of the game stay in memory while Deck watches, and are never sent anywhere.
- On disk: each game's history, your boss notes, fingerprints of the death screens you taught plus a small reference picture of each, and (only if you turn them on) the text log and testing pictures described above.
- The only network use is the shared library check (a plain download, at most once a day) and the optional OCR pack download. Nothing about you or your play is sent. The OCR pack's runtime has its telemetry off.
- History is kept in Deck's data folder, one file per game. Deck keeps daily backups for 14 days. If a history file is damaged, Deck sets it aside instead of overwriting it.

## Recommended setup

1. Start the game in **borderless** or **windowed** mode.
2. If it is one of the built-in games, play: Deck counts by itself. Otherwise count one death with **+1 death** (or the tray) to start watching the game.
3. Set a **+1 death shortcut** and an **Undo shortcut** you won't press by accident, or turn on the **Controller combo** if View does nothing in your game.
4. Leave **Read save files**, **Watch for death screens**, **Find boss fights by themselves** and the **Shared death-screen library** on.
5. If boss names read badly, turn on the **OCR pack**.
6. If a game's death screen has no words, teach it once on the Games tab.
7. Streamers: set an output folder for the OBS text files and keep **Show in screenshots and recordings** on.
8. Prefer a quieter screen: leave **Red edges** off (the default), shorten the card's seconds, or turn the card off.

## Troubleshooting

**Nothing is counted automatically.**
- Check that **Death counter** and **Watch for death screens** are on and that the game is in borderless or windowed mode.
- Games Deck doesn't know aren't watched until you count a death in them (or you pick **Watch in > Every game**).
- Read the status line at the bottom of the Now tab. "Game screen unreadable" means Deck sees a black picture: use borderless windowed. "English death screens may be missed" means add English to Windows' language settings. "Save not found" means count deaths by hand for now.

**A name is wrong or a menu is counted as a boss.** Use **Not a boss** on the fight, or rename it under Fight actions. Use **Same boss as** to combine a misread name.

**A death counted twice or counted when I didn't die.** Open History, press the line's menu and choose **That wasn't a death**. If one screen keeps causing it, find it under the game's learned screens and press **Forget**.

**The counter isn't showing in the game.** Use borderless or windowed mode. Check **Show the counter in games**, and **In every game** if the game isn't known.

**The counter shows in my recording and I don't want it** (or the reverse). Change **Show in screenshots and recordings**. Hiding it can make NVIDIA Instant Replay switch itself off.

**The OCR pack download failed.** The row shows the reason and a **Try again** button.

**The OBS text files aren't written.** Pick a folder you can write to.

**A warning about the history file appears.** Choose from the buttons shown; Deck keeps copies of every version it sets aside.

## FAQ

**Is it safe with anti-cheat?** Deck doesn't touch the game: no memory reading, no injection, no hooks into it. It reads save files, looks at the screen picture like a recorder, and reads your keys and controller.

**Does it work in any game?** Yes, once you count a death there. Games with a save reader or built-in extras need no setup. Death screens in Spanish, French, German, Italian, Portuguese and Polish are read with no setup; symbol-only screens need teaching.

**Does it slow my game?** The watcher looks at a small picture a few times a second and reads text at most once a second. Turn off **Watch for death screens** to stop it entirely.

**Can I count deaths without the screen being watched?** Yes: buttons, tray, shortcuts and the controller combo, with automatic counting off.

**Can I fix a wrong count?** Yes: Undo death, the History corrections and merging boss names. Nothing is deleted.

**How do I back up or export my history?** Games tab > **Export** (one game) or **Export everything**, both CSV.

**How do I start over?** Settings > Start over > **Reset all death counts** (type `reset`). Learned screens and settings stay.

**Where else can I count?** Home shows +1 and Undo for games that have a death counter. The tray's **Death counter** menu has **+1 death**, **Undo last death**, **Boss defeated**, **Abandon fight**, **Start boss fight...**, **Count deaths in this game** and **Open death counter...**. The [Game bar](game-bar.md) can also count and fix deaths without leaving the game.

**See also:** [Controller](controller.md), [Game bar](game-bar.md), [Overlay](overlay.md), [Gaming](gaming.md).
