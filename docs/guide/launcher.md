Where to find it: Settings › Search

# Launcher and search

The search box at the top of Deck is a launcher: it finds apps, games, pages, settings and files, does sums, and runs commands and your saved actions.

There is no page called "Launcher". Its options are in **Settings › Search** ([Settings](settings.md#search)); snippets are on the [Clipboard](clipboard.md) page.

## Using the search box

Open Deck and start typing. Results appear in groups, with the best match selected.

| Key | Action |
|---|---|
| Up / Down | Move the selection. |
| Enter | Run the selected result. If results for your last letters are still arriving, Deck waits for them. |
| Esc | Clear the box. Press it again on an empty box to hide Deck. |

- Click also works: pointing at a result selects it, and the **x** in the box clears the search like Esc. Apps and files have a **Show in Explorer** button; right-click an app for its menu.
- The words you typed are marked, and Deck results show where they live (**Group › Page › Tab**).
- After you open a result, **Back to results** (or the mouse's Back button) brings the results back. Esc on a cleared search returns to the page you were on.
- Click the empty box to see your **Pinned** pages, your 5 most **Recent** pages and the **Windows tools**. The pin button on a page or tab result adds or removes it from **Pinned**.

### How matching works

- Capitals and accents don't matter, and words can come in any order or be cut short (`calib` finds Calibrate).
- Simple plurals match.
- In words of five letters or more, one wrong, missing, extra or swapped letter is forgiven. Words of one to three letters are never guessed.
- Exact names come first, then names that start with what you typed, then other words. A page or tab beats a control with the same words. Eight Deck results show at first; **More Deck results** shows the rest.
- A saved action whose keyword is exactly your first word comes first.
- With no match, the list says **No matches** and suggests up to three nearby pages, with web search below.
- A result for a setting that your options hide opens its page and says why the row isn't shown.

### What is searched

| Group | What it holds |
|---|---|
| **Calculator**, **Conversion** | The answer on top. Enter copies it. |
| **Do it** | Commands such as timers (below). |
| **Apps** | Start menu and Store apps. Apps you open often rise to the top. |
| **Deck** | Every page, tab and setting, plus tools and actions: color picker, text extractor, ruler, Keep awake, dark or light mode, lock, sleep, restart, shut down, speed test, switching sound output, opening a saved workspace, every Windows tweak. Choosing a setting opens its page and lights the row. Old names still work ("Overlay" finds **Performance overlay**). Hidden pages are found only by their full name. Power actions ask first. |
| **Games** | Installed games. They open through their store's launcher. |
| **Files** | Files and folders from Deck's file index (below). From 2 letters. |
| **Quicklink**, **Custom command**, **Chained actions** | Your [saved actions](#saved-actions). |
| **Snippets** | Your saved texts, by name or keyword. |
| **Clipboard** | Text from your clipboard history, from 3 letters. Enter pastes or copies ([Clipboard](clipboard.md)). |
| **Web** | Search the web with the provider chosen in Settings › Search. |

Start with a letter and a space to search one source: `w ` lists open windows (none while a game is in front), `c ` searches only the clipboard, `d ` shows the display controls. A saved action with that keyword wins.

When a source can't answer, one line says so (for example "Files not searched: the file index is turned off.") and the other results still appear. Files from an index more than a day old say how old it is.

### Calculator

Type a sum: `12*7`, `(5+3)^2`, `200 + 10%`, `17 % 5` (remainder), `0xFF`. Enter copies the answer.

### Conversions

Type a number, a unit, `to` (or `in`, `as`, `=`, `->`) and the unit you want:

- Length, weight, volume, area, time, data size, speed, energy and temperature: `12 km to miles`, `70 kg to lb`, `20 c to f`.
- Number bases: `255 to hex`, `0xff to dec`, `10 to bin`.
- Currency: `100 usd to eur`. Rates download from a public service the first time and are cached; offline, the last rates are used.

### Commands

| Type | What it does |
|---|---|
| `timer 10m` (or `t 10m`) | Starts a 10-minute timer. |
| `sleep in 30m`, `shutdown in 1h`, `restart in …`, `lock in …` | Plans that action after a delay, after you confirm. See [Shut down when…](power.md#shut-down-when). |
| `awake 2h` (also `keep awake`, `stay awake`) | Keeps the PC awake for that time. |
| `cancel` or `stop` | Cancels the current plan. |
| `kill discord` (also `close`, `end`) | Offers to end a program by name, after you confirm. Protected system programs aren't offered. |
| A web address such as `example.com` | Offers to open it. |

### Local file search

Deck keeps an index of file names (not their contents) so search can find files. Set it up in **Settings › Search › Local file search**: **File search** turns it on or off, **Search folders** lists the folders, with **Add folder** and **Refresh**. See [Settings](settings.md#local-file-search).

## Saved actions

In **Settings › Search** the **Saved actions** card holds quicklinks, custom commands and chains. Create one with **New quicklink**, **New custom command** or **New chain**; each has **Edit**, **Run** and **Delete**.

Each action has a **Name** and a **Launcher keyword** (no spaces, up to 32 characters, unique; up to 100 actions). Type the keyword in search, plus any extra text, to find it.

Running an action first shows exactly what it will do, then waits for **Run**. The first time you run a command or chain in a session it says "First use this session: review every action before running." If you edit it, you review it again. Afterwards a results box lists each step as done, failed or skipped.

### Quicklink

A web search shortcut. Enter a **Website URL template, with {query}**, such as `https://example.org/search?q={query}`. Typing `keyword some words` opens it with the words in place of `{query}`.

The address must start with `http://` or `https://`, contain no login details, and keep `{query}` out of the host name.

### Custom command

Runs one of your programs.

| Field | Meaning |
|---|---|
| **Full program file (.exe)** | The full path to an `.exe`. |
| **Arguments, one per line; {query} is optional** | Up to 64 arguments, no quotes needed. `{query}` becomes the text after the keyword. |
| **Time limit, seconds** | 1 to 600. The program, and anything it starts, stops at the limit. |

The program runs as your normal account, never as administrator.

### Chains

Up to 16 steps run in order. If a step fails, the rest are skipped. Use **Add step**, **Move up** and **Remove step** to arrange them.

| Step | Does |
|---|---|
| **Switch sound output** | Makes an output the default. **Reset changes** on [Mixer](sound.md) goes back. |
| **CPU profile** | Applies a CPU profile ([CPU](cpu.md)). |
| **GPU profile** | Applies a GPU profile ([GPU](gpu.md)), with the same crash guard as the GPU page. |
| **Power plan** | Switches the Windows power plan. |
| **Open app** | Opens an installed app. |

**Restore power plan** puts back the power plan you had before a chain changed it.

## Snippets

Short texts you reuse. Create them under **Snippets** on the [Clipboard](clipboard.md) page. In search, type the snippet's keyword or name and press Enter to paste it. `{date}`, `{time}`, `{datetime}` and `{clipboard}` are filled in when you use it.

## Recommended setup

- Add 2 or 3 quicklinks for sites you search often.
- Make a "gaming" chain (headset, gaming CPU and GPU profiles, power plan, game launcher) and a "quiet" chain to go back.
- Index only the folders you use.
- Learn `timer`, `awake` and `kill`.

## Troubleshooting

**An app doesn't show.** Type fewer letters. A just-installed app may take a moment.

**Files don't show.** Check that **File search** is on, the folder is in the list, and the page doesn't say **Partly indexed**. Type at least two letters. Only file names are indexed.

**Currency conversion shows nothing.** Connect to the internet once so Deck can get the rates.

**A saved action says the preview expired.** A preview lasts two minutes. Open it again.

**A chain stopped halfway.** The results box says which step failed and why. Fix it (for example, plug in the output device) and run it again.

**A quicklink is refused.** It needs `http://` or `https://`, no login details, and `{query}` outside the host name.

## FAQ

**Are custom commands safe?** They run only what you created. Deck shows the full command, asks for a review the first time and after each edit, runs it as your normal account and stops it at the time limit.

**Does the file index send anything online?** No. It is a list of file names on this PC.

**Can I change a keyword later?** Yes, edit the action.
