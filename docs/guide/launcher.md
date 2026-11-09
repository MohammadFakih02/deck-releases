# Launcher and search

Deck's search box is a launcher. Open Deck, type, and press Enter. It finds apps, games, Deck's own pages and actions, files, clipboard items and snippets, answers sums and conversions, runs short commands, and runs your own saved links, commands and action chains.

You can use it from any page: the search box sits at the top of Deck. How you open Deck (hot corner, tray icon, Start menu, an optional keyboard shortcut) is in [Settings](settings.md).

There is no page called "Launcher". The things you can set up for it live in **Settings > Search** (web provider, saved actions, folders to search) and **Clipboard > Settings** (snippets).

---

## Using the search box

Start typing. Results appear straight away in groups. The best match is selected.

| Key | Action |
|---|---|
| Up / Down | Move the selection. |
| Enter | Run the selected result. If the results for your last letters are still arriving, Deck waits for them so Enter never runs a result that belonged to the previous letters. |
| Escape | Clear the box; press it again on an empty box to hide Deck. |

Hover and click also work. Apps and files have a small folder button, "Show in folder". Right-click an app for its menu.

### What is searched

| Group | What it holds |
|---|---|
| **Calculator** and **Conversion** | An answer shown on top. Enter copies it. |
| **Do it** | Commands such as timers (below). |
| **Apps** | Start-menu apps and Store apps. Apps you open often rise to the top. |
| **Deck** | Every Deck page (sidebar pages), tools and actions: colour picker, copy text from the screen, ruler, keep awake, dark/light mode, lock, sleep, restart, shut down, clean up, speed test, switching sound output to a named device, opening a saved workspace, every Windows tweak by name, and so on. Power actions ask you to confirm. |
| **Games** | Installed Steam and Epic games. Opens through the store's launcher. |
| **Files** | Files and folders from Deck's own file index (see below). Enter opens; the folder button shows it in Explorer. Needs at least 2 letters. |
| **Quicklink**, **Custom command**, **Chained actions** | Your saved actions (see below). |
| **Snippets** | Your saved texts, found by name or keyword. |
| **Clipboard** | Text from your clipboard history, from 3 letters. Enter pastes (or copies, see [Clipboard](clipboard.md)). |
| **Web** | "Search the web for ..." using the provider chosen in Settings > Search. |

### Calculator

Type a sum: `12*7`, `(5+3)^2`, `200 + 10%` (adds ten percent), `200 - 10%`, `17 % 5` (remainder), hex numbers like `0xFF`. Plain numbers or words are not treated as sums. Enter copies the answer.

### Conversions

Type a number, a unit, `to` (or `in`, `as`, `=`, `->`) and the unit you want:

- Length, weight, volume, area, time, data size, speed, energy and temperature: `12 km to miles`, `5 ft in cm`, `70 kg to lb`, `20 c to f`.
- Number bases: `255 to hex`, `0xff to dec`, `10 to bin`.
- Currency: `100 usd to eur`. Rates are downloaded from a public rate service when you first convert a currency and cached on your PC; with no internet the last cached rates are used.

Enter copies the result.

### Commands

| Type | What it does |
|---|---|
| `timer 10m` (or `t 10m`) | Starts a 10-minute timer. |
| `sleep in 30m`, `shutdown in 1h`, `restart in ...`, `lock in ...` | Makes a plan to do that after a delay (with a confirmation, and it can be cancelled). See [Power](power.md). |
| `awake 2h` (also `keep awake`, `caffeine`, `stay awake`) | Keeps the PC awake for that time. |
| `cancel` or `stop` (while a plan is active) | Cancels the current shutdown/sleep/restart plan. |
| `kill discord` (also `close`, `end`) | Offers to end a running program matching the name. It asks first, because unsaved work is lost. Protected system programs are not offered. |
| A web address such as `example.com` | Offers to open it. |

### Local file search

Deck builds a small file-name index so files can be found from the search box (it does not read file contents). Controls are in **Settings > Search > Local file search**:

| Setting | What it does | Default |
|---|---|---|
| **Find files from the search box** | Turns the index on or off. The line under it shows how many files and folders were read and how long it took. It refreshes every 30 minutes. | On |
| **Folders search looks in** | The folders to index. **Add folder** and the **x** next to each folder change the list. **Refresh now** re-reads them. | Desktop, Documents, Pictures, Videos, Music and OneDrive of your account |

Program folders, `node_modules`, `.git`, build output and AppData are skipped. If the file limit is reached or some folders cannot be read, the page says "Partly indexed" and names the folders: choose fewer folders or fix permissions, then refresh.

---

## Settings > Search

### Web search

| Setting | What it does | Default |
|---|---|---|
| **Search provider** | The site used for the "Search the web" result: Google, DuckDuckGo, Bing, Brave or YouTube. | Google |

---

## Quicklinks, custom commands and chains

Under **Settings > Search** there is a panel called **Quicklinks, custom commands and chained actions**. Each one has a name and a **keyword** (no spaces, up to 32 characters; each keyword must be unique; up to 100 saved actions). Type the keyword in the search box, followed by any extra text, and the action shows in the results. Typing part of the name also finds it.

Choosing a saved action first shows a **preview** of exactly what it will do, then asks you to press **Run**. Quicklinks run straight after you confirm. For commands and chains, the first time you run one the box says "First use this session: review every action before running." Deck remembers that you reviewed that exact action; if you edit it, it asks again. When it finishes, a Results box lists every step as done, failed or skipped.

The panel lists each action as `keyword · name` with **Edit**, **Run** and **Delete** buttons. **New quicklink**, **New custom command** and **New chain** create one.

### Quicklink

A web search shortcut. Give it a **Website URL template, with {query}**, for example `https://example.org/search?q={query}`. Typing `keyword some words` opens that address with the words safely encoded in place of `{query}`.

Rules: it must start with `http://` or `https://`, must not contain a username or password, and `{query}` must be in the path or query string, not the host name. Quicklinks open in your default browser.

### Custom command

Runs one program of yours.

| Field | Meaning |
|---|---|
| **Full program file (.exe)** | The full path to an `.exe`. A relative path is refused. |
| **Arguments, one per line; {query} is optional** | Up to 64 arguments, one per line, no quotes needed. `{query}` is replaced by the text you typed after the keyword. |
| **Time limit, seconds** | From 1 to 600. The program, including programs it starts, is stopped at the limit. |

The program runs as your normal signed-in user, never as administrator, and is placed in a job that ends with the time limit. Deck shows the exact command line in the preview before running.

### Chained actions

Runs up to 16 steps in order. If one step fails, the rest are skipped ("Not run because an earlier step failed"). The step types:

| Step | Does |
|---|---|
| **Switch sound output** | Makes an output device the default. Use **Undo sound changes** on [Sound and mic](sound.md) to go back. |
| **CPU profile** | Applies one of your CPU profiles. See [CPU](cpu.md). |
| **GPU profile** | Applies one of your GPU profiles. See [GPU](gpu.md). |
| **Power plan** | Switches the Windows power plan. |
| **Open app** | Launches an app from your installed apps. |

Use **Move up** and **Remove step** to arrange steps. **Undo chain's power plan** (in the panel) puts back the power plan that was active before the first chain changed it.

CPU and GPU steps use the same checked switch as the profile pages, including their crash guards.

---

## Snippets

Short, reusable texts. Create them under **Settings › Desktop › Snippets** (see [Clipboard](clipboard.md)). In the search box, type the snippet's keyword (or part of its name) and press Enter on the result: it pastes (or copies, depending on the Clipboard "On double-click or Enter" setting). In the text, `{date}`, `{time}`, `{datetime}` and `{clipboard}` are filled in at the moment you use it.

---

## Recommended setup

- Add 2 or 3 quicklinks for sites you search often (a video site, a documentation site, a map).
- Make a "gaming" chain: switch sound to your headset, apply your gaming CPU and GPU profiles, switch the power plan, open your game launcher. Make a "quiet" chain to undo it. Each is one keyword away.
- Keep the file index to the folders you really use; fewer folders means a fast, complete index.
- Learn the `timer`, `awake` and `kill` commands.

## Troubleshooting

**The app I want does not show.** Try fewer letters. If an app was only just installed, give Deck a moment and search again.

**Files do not show.** Check **Find files from the search box** is on, the folder is in the list and the page does not say "Partly indexed". Search needs at least two letters. File names only are indexed.

**Currency conversion says nothing.** It needs rates. Connect to the internet once so Deck can download and cache them.

**A saved action says the preview expired.** A preview lasts two minutes. Open it again and run.

**My chain stopped halfway.** A step failed; the result box says which and why. Fix that step (for example the output device is unplugged) and run again.

**A quicklink is refused.** The address needs `http://` or `https://`, no login details, and `{query}` outside the host name.

## FAQ

**Is it safe to run custom commands?** They are only what you create. Deck shows the full command line, asks for review the first time and again after any edit, runs it as your normal user (not administrator) and stops it at the time limit.

**Does the file index send anything online?** No. It is a list of file names on this PC.

**Does anything in the launcher touch games?** No. Launching a game just opens it through its store, like double-clicking its shortcut.

**Can I change the keyword later?** Yes, edit the action. Keywords must be unique.
