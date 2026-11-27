Where to find it: Gaming › Death counter

# Death counter

Counts your deaths in any game and per boss, with tries, wins, records and a history of every session.

In the games it knows, Deck counts automatically. In any other game you count one death by hand, and Deck starts watching that game and can learn its death screen.

The page has five tabs: **Now**, **Bosses**, **History**, **Games** and **Counter settings**. The bar above them shows the game (with **Chosen by you** or **Last detected**), how it counts (for example **Screen + boss bars** or **Save file**) and the **Counting on** / **Counting off** switch for that game. **Current game** goes back to the game in front.

Deck never reads a game's memory or injects into it: it reads save files, looks at the game window like a screen recorder, or waits for your button. See the [FAQ](faq.md) for anti-cheat.

## How counting works

You can mix all four ways.

| Way | Needs | Notes |
|---|---|---|
| By hand | Nothing | **+1 death** on Now, the tray menu, Home, the **+1 death shortcut** or the **Controller combo**. Counting a death in a new game makes Deck start watching it. |
| Save file | A game with a save reader | Built in for Celeste and Dark Souls: Prepare To Die Edition. Saves are only read. A jump of more than 20 deaths at once is ignored. |
| Death screen | Borderless or windowed mode | Deck checks the window a few times a second and counts when the death screen shows ("YOU DIED", "GAME OVER"). A screen without words can be [taught once](#teaching-and-setting-up-a-game). |
| Boss health bar | Screen watching on | Deck spots a boss bar, reads the name, times the try and closes the fight when the bar empties or a victory banner shows. |

- A death needs the screen to clear and about 8 seconds to pass before the next one counts, so a long death screen never counts twice.
- A death screen shown with a co-op banner about someone else (a summon or ally) never counts. A death you count by hand always counts.
- Deck knows a game by its program, so the same game from Steam, GOG, Game Pass or EA shares one history.
- Deck ships presets (boss bar and name position, your own bars, death words) for many hard games, including the Dark Souls series, Demon's Souls, Bloodborne, Elden Ring and Nightreign, Sekiro, Lies of P, Nioh 1 and 2, Wo Long, Wuchang, Black Myth: Wukong, Khazan, Remnant II, Salt and Sanctuary, Salt and Sacrifice, Ashen, Cuphead, Celeste and Lords of the Fallen. The Games tab lists them under **Available presets**. Any other game works once you count a death in it.

## Now tab

The game in front, or the last one you played.

- **Count deaths in this game**: the switch in the top bar. A game Deck can't read yet starts off until you turn it on, count a death or teach a screen.
- The boss area shows the current fight and two big numbers: deaths on **This boss** and in **The game**.
- **Unconfirmed** and **Confirm boss**: Deck opened a fight itself and isn't sure of the name. Confirm it, or rename it under **Fight actions**.
- **+1 death** counts a death; **Undo death** takes back the last one; **Boss defeated** marks the boss beaten.
- **Start a boss fight** with a **Boss name** starts a fight by hand. Chips below it offer bosses you named or confirmed before.
- **Fight actions**: **Rename fight**, **Abandon fight** (stop without a win) or **Not a boss** (the deaths stay in the game's total; Deck can ignore that name from now on).
- **Your last tries** (or **Tries on this boss**) with **View charts**, which opens History.
- **This session** and **All-time records** (longest try, quickest win, deadliest boss, most deaths in a session). **Share** copies or saves a picture of the numbers.
- The line at the bottom says how the game is counted, or why it isn't (see [Troubleshooting](#troubleshooting)).

## Bosses tab

One card per boss, newest first. The **Game** picker is shared with Now and History.

Each card shows **Fighting** or **Beaten**, deaths, time on the boss, longest try and the winning try. For an unbeaten boss it shows how close you got where Deck saw the bar. You can add a note (up to 500 characters) that can show on the card after a death. **View charts** opens History for that boss.

Under **Share or merge this boss entry**:

- **Copy boss picture** and **Save boss picture...** make an image of the boss's numbers.
- **Same boss as** fixes a misread name: choose the real boss and press **Combine boss counts**. The fix applies to future reads too. **Undo that** reverses it.

For boss games the tab also has the boss's health bar and name: **Show where they are** marks them, **Forget the bar** and **Forget the name box** remove your marks.

## History tab

- **Tries**: a chart of your tries for **All tries** or one boss.
- **Deaths per day**: a heat map of the last 12 weeks. Click a day to open it.
- One card per session: time, length, deaths, bosses beaten and a deaths-over-time chart. Inside: **Fought**, **Attempt splits** (each try with its result, length, profiles and temperatures) and a timeline of deaths, fights and fixes.
- **Fights to check** lists fights Deck opened itself: **That's right**, **Rename** or **Not a boss**.

### Correcting mistakes

Every line has a **More** menu. Nothing is deleted: a fix strikes a line out or adds a note, and **Undo that** shows for ten seconds.

| Menu item | What it does |
|---|---|
| **That wasn't a death** | Strikes the death out of all counts. |
| **Count it again** | Reverses that. |
| **Undo this fix** | Takes back a correction. |
| **Rename this fight...** | Gives one past fight another boss name. |
| **I won that fight** / **I didn't win that fight** | Sets the result. |
| **That wasn't a boss fight...** | Same as Not a boss. |
| **Add a missed death here** | Adds a death to that fight. |
| **Why is this here?** | Explains where the line came from. |
| **Leave this line out** | Counts and stats ignore it. |

If a history file can't be read or saved, or changed outside Deck, a notice at the top offers the choices (such as **Keep Deck's version**, **Use the file on disk** or **Add them**). Deck never overwrites a history it can't read.

## Games tab

- **Your games**: every game with counted deaths. **Export** saves one game as CSV; **Show** switches the other tabs to it.
- **All games**: totals, deaths per week and the deadliest bosses. **Export everything** saves all as CSV.
- **Death-screen library**: how many games the shared library covers, and **A friend's death screen**: paste a friend's code (it starts `deck-death-screen:`) and press **Add**.
- **Learned screens** for the chosen game: the death and victory screens Deck learned, the setup steps and the teaching card.
- **Available presets**: the built-in list, with **Find a preset**.

### Teaching and setting up a game

Teach a game whose death screen has no readable words, is in another language, or is only a symbol. You do it once.

1. Count a death while the death screen is up, or just after.
2. Open Death counter › **Games** and choose **Show the last 10 seconds**.
3. Click the picture where the death screen is clearest.

Deck keeps up to three death screens and three victory screens per game. If it notices a screen before several deaths you counted by hand, it asks **Is this the death screen?**: **Yes, that's it** or **No**. To remove a wrong one, open the learned screens and press **Forget** (its past deaths stay; fix them in History).

Optional setup steps for better accuracy:

| Step | What to do |
|---|---|
| Your own bars | Press **Mark them**, drag boxes over your health bars and item slots so Deck never takes them for a boss, then **Save**. |
| Boss health bar and name | During or just after a fight, click the boss bar, then drag a box around the name (or **Name is above the bar** / **Name is below it**). |
| Death screen | Pick it from your last death (**Pick another** to change it). |
| **Boss kill screen** | Pick the victory screen after you mark a boss beaten, or select **Game has none**. |

Sharing:

- **Share with a friend** copies a code of your death screens for the game.
- **Submit to the shared library** copies the code and opens the report form on Deck's public releases site. Once checked, it is shared with everyone.
- The shared library updates at most once a day (a plain download; nothing about you is sent). **Don't use them** turns its screens off for one game.

## Counter settings

A live preview of the in-game counter sits beside the settings. Most rows have a "?" with more detail.

### Counting

| Setting | What it does | Default |
|---|---|---|
| **Death counter** | Turns counting, the tray menu, shortcuts and the in-game counter on or off. Your history stays. | On |
| **+1 death shortcut**, **Undo shortcut** | Keys that count or undo a death, also while a game has focus. | None |
| **Controller combo** | Hold View (Select) + D-pad Down for one second to count, + D-pad Up to undo. The game sees the buttons too, so leave it off if View opens a menu. | Off |

### Automatic counting

| Setting | What it does | Default |
|---|---|---|
| **Read save files** | Counts from supported saves. | On |
| **Shared death-screen library** | Recognizes screens other players taught. | Off |
| **Watch for death screens** | Looks at the game window while a game is in front. Pictures stay in memory. | On |
| **Read text with the OCR pack** | A second text reader (about 24 MB) for names and screens Windows misses. Turning it off deletes it. | Off |
| **Watch in** | **Games Deck knows** or **Every game**. | Games Deck knows |
| **Find boss fights automatically** | Opens and times fights when a boss bar appears. | On |

**Recognition rules & testing** (shown while screen watching is on):

- **Keep a text log for testing** (text only, at most 20 MB per game; **Delete it**) and **Keep pictures for testing** (small gray pictures, kept seven days, at most 200 MB; **Delete them**). Both are off and never sent.
- **Not bosses**, **Ignored in** the game and **Same boss in** the game: remove a name to undo it.

### In-game counter

| Setting | What it does | Default |
|---|---|---|
| **Show in games** | A click-through counter on the game's monitor. | On |
| **Style** | **Skull and number**, **Ring** or **Huge number**. | Skull and number |
| **Counts** | During a fight: **This boss**, **The game** or **Both**. | Both |
| **Outside a fight** | **The game's total** or **Nothing**. | The game's total |
| **In every game** | Also for games without deaths. | Off |
| **Corner**, **Size**, **Opacity** | Position (on the game's monitor), 50 to 200 %, 20 to 100 %. | Top, 100 %, 90 % |
| **Red edges on a death** | Flashes the screen edges red. | Off |
| **Show in screenshots and recordings** | Lets recorders and screen shares capture the counter. Hiding it can make NVIDIA Instant Replay turn itself off. | On |

**After a death**: **Open the card after a death** (on) shows a summary for **Seconds** (2 to 10, default 5). **What the card shows** turns lines on or off: **Try number**, **This try's length**, **Boss health left**, **Time on the boss**, **This session**, **Recent tries**, **Highlights** and **My boss note** (off).

### Backups

Deck keeps daily backups of each game's history for 14 days and sets a damaged file aside instead of overwriting it. **Older copies** shows how many copies Deck keeps, with **Open folder**. To restore one, quit Deck, rename the copy to the game's name ending in `.jsonl`, and start Deck. **Second backup folder** (off) also writes every backup to a folder you choose.

### Start over

**Reset all death counts** wipes counts, fights, tries, sessions, records and notes for every game. Type `reset` to enable the button. Settings and learned screens stay, and a copy of the old history is kept.

## OBS text files

**Write text files for OBS** (off by default) writes three files to the **Output folder** you choose with **Choose folder**, updated as the numbers change:

| File | Contents |
|---|---|
| `deaths.txt` | The game's total deaths. |
| `boss.txt` | The current boss (empty between fights). |
| `bosses.txt` | One line per boss: `Boss name: deaths`. |

In OBS, add a Text (GDI+) source and select "Read from file" for each file.

## Privacy

Game pictures stay in memory and are never sent. On disk Deck keeps each game's history, your notes, the screens you taught, and the testing logs if you turn them on. The only downloads are the shared library (once a day at most) and the optional OCR pack.

## Recommended setup

1. Run the game in borderless or windowed mode.
2. In a game Deck knows, just play. Otherwise count one death with **+1 death** to start.
3. Set a **+1 death shortcut** and **Undo shortcut**, or the **Controller combo** if View does nothing in your game.
4. Turn on **Shared death-screen library**.
5. If boss names read badly, turn on the OCR pack. If the death screen has no words, teach it once.

## Troubleshooting

**Nothing is counted automatically.**

- Check that **Death counter** and **Watch for death screens** are on, and the game runs borderless or windowed.
- A game Deck doesn't know isn't watched until you count a death in it, or set **Watch in** to **Every game**.
- Read the line at the bottom of Now. "Game screen unreadable" means Deck sees a black picture: use borderless windowed. "English death screens may be missed" means add English in Windows' language settings.

**A wrong name, or a menu counted as a boss.** Use **Not a boss** or rename the fight. Use **Same boss as** to merge a misread name.

**A death counted twice, or when I didn't die.** In History, open the line's menu and choose **That wasn't a death**. If one learned screen keeps doing it, **Forget** it.

**The counter doesn't show in the game.** Use borderless or windowed mode, and check **Show in games** (and **In every game** for an unknown game).

**The counter shows in my recording.** Turn off **Show in screenshots and recordings**.

**The OCR pack download failed.** The row says why and offers **Try again**.

**The OBS text files aren't written.** Pick a folder you can write to.

## FAQ

**Is it safe with anti-cheat?** Yes: no memory reading, no injection. It reads save files, looks at the screen picture and reads your keys and controller.

**Does it work in any game?** Yes, once you count a death there. Death screens in English, Spanish, French, German, Italian, Portuguese and Polish are read without setup; symbol-only screens need teaching.

**Does it slow my game?** It looks at a small picture a few times a second and reads text at most once a second. Turn off **Watch for death screens** to stop it.

**Can I fix a wrong count?** Yes: **Undo death**, the History menu, and merging names. Nothing is deleted.

**How do I export my history?** Games › **Export** or **Export everything** (CSV).

**Where else can I count?** Home, the tray's Death counter menu and the [Deck bar](game-bar.md).

**How sure is Deck about a count?** Each fight says how it was counted: **Known screen**, **Taught screen**, **Guess from words** (doubt these first) or **By hand**.

See also: [Controller](controller.md), [Deck bar](game-bar.md), [Performance overlay](overlay.md), [Game profiles](gaming.md).
