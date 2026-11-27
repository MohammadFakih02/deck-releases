# Changelog

All notable changes to Deck. Setups for each version are on the [Releases](https://github.com/MohammadFakih02/deck-releases/releases) page.

## 5.0.0 — 2026-11-27
- Fixed: Performance overlay's Format, Look and Behaviour tabs no longer stay on their loading placeholder the first time you open them.
- Search finds every page's current labels again.
- Phone app: on Tecno, Infinix and itel phones, Settings › Connection has a new step that opens the phone's power saving page, where choosing No Restrictions for Deck stops the phone from freezing it in the background.
- Updates are signed: from 5.0.0 on, Deck installs an update only when it carries a valid signature from the Deck maintainer's key.
- League of Legends and Valorant can show the chosen sensor overlay in Deck's own click-through window while RivaTuner is held closed. It follows the game's foreground window and the chosen corner, colours, font and zoom, stays inside the game window and hides at once when another window comes to the front; if the window cannot be made, Deck tries again after a minute; with Deck running as administrator, Windows frame events supply FPS, frame time and frame statistics (Reset averages clears them too); Deck's log says when the window shows and why it hides; its text uses RivaTuner's font height, zoom, thin shadow and raised small units, leaves out the frame-time graph, and falls back to Consolas when the chosen font is missing; unavailable frame figures and the graph show dashes.
- Fixed: a stalled RivaTuner start cannot hold the lifecycle lock in front of Deck's shutdown and hardware hand-back; an already admitted start may finish after quit.
- Fixed: checking for RivaTuner cannot deadlock Deck through its own windows, and Open RivaTuner still restores it after a Vanguard game interrupts reopening, even with autostart off.
- Fixed: RivaTuner cannot start past a Vanguard hold or be newly admitted after Deck shutdown begins, delayed game checks retain autostart, and Activity shows the reason and remedy when RivaTuner cannot close or start.
- RivaTuner is politely closed while League of Legends or Valorant runs because Riot Vanguard blocks it, and starts again afterwards if it was running or set to start with Deck.
- Fixed: the controller overlay no longer appears for a few seconds when Deck starts. On the Controller page it shows within a second of opening the page.
- Fixed: games could freeze for a second or more every few seconds while Deck was open. Deck asked every drive for its temperature each second (every 3 seconds in a game), and some drives stall while answering. It now asks once a minute; read and write rates still update every second.
- Alerts on a drive's temperature that wait some seconds now need drive readings that cover that time, so they can come up to a minute or two later. A sleeping drive's last reading no longer counts as a new one; other alerts fire when they always did.
- For contributors: the engineering notes on threads, crash handling and tests describe the code as it is now.
- For contributors: the engineering notes no longer overstate what the command, crash-order and callback checks prove.
- For contributors: one instruction file for every coding tool (`AGENTS.md`), an acceptance standard in `CONTRIBUTING.md`, an engineering playbook, and a merge gate that checks a larger change was designed, challenged, tested and reviewed before it is merged.
- For contributors: `tools/quality/ledger.py` tracks an owner assignment requirement by requirement (every line of the assignment must belong to a row; a row counts as verified only with evidence; a row set aside needs the owner's recorded approval).
- For contributors: `tools/quality/refs.py` fails when an instruction or area file names a file that does not exist (build output aside).
- For contributors: the engineering evaluation (`tools/testing/eng-eval`) builds its own blind grading packets and records the grades.
- For contributors: the contracts check no longer fails in a fresh worktree on Windows (it compared line endings).
- For contributors: `tools/merge/diffcheck.py` checks a branch's real git diff before a merge (files outside the brief's scope, protected gates and rules, weakened tests, generated files, leftovers); the merge checklist runs it.
- For contributors: the code carries no comments any more (only `SAFETY:` notes on unsafe code and JSDoc types); a ratchet keeps new ones out. Search finds about 30 more buttons and settings that its source scan used to miss.
- For contributors: no test depends on code comments any more (tests cut source at code, not at comment banners), so comments can be removed without breaking tests.
- For contributors: saved files from Deck 4.0 to 4.6 (game sessions, PC to PC, Project sync, death counter, clipboard, network history, batteries, phone, startup undo, lighting restore and more) are now loaded in tests, and three search checks that missed pass again.
- Diagnostics no longer says background tasks stopped after a game ends or Clock Contrast is turned off; one time rule that fails no longer stops the others, and Clock Contrast shows as off if its worker gave up.
- Background features that stopped for good after an internal error now start again on their own (virtual display, Clock Contrast, window zones, the log, startup watch, time rules), and a restart no longer repeats a hot-corner action, a game bar toggle, a sound rule, data-usage bytes or a game session.
- Security: a path from Deck's pages can no longer reach this PC's own network shares or admin shares (`\\localhost\C$`), where Windows' own folder rights would be skipped. Program checks still check every other program when one program's file can't be named, and launcher actions saved in older versions keep working.
- Security: Deck's windows only ever show Deck's own pages; links to anything else open in your browser.
- Security: files, folders, programs and startup entries sent from Deck's pages are checked before Deck acts on them with admin rights (full paths only, no `..`), and Deck starts its own helper programs by full path.
- For contributors: one written engineering standard and comment policy for every change (CONTRIBUTING.md), checked by two new code counters: no excuse comments, no new switched-off lints.
- For contributors: every Windows callback now runs under the panic guard (none left unguarded).
- For contributors: the Home Week/Month page test no longer fails on a busy PC.
- Search finds about 500 more settings and controls, including everything on the rebuilt Power pages.
- For contributors: tests can no longer write into the user's own folders or scheduled tasks (profile shortcuts, Start menu, Desktop, AppData, Claude Code and Codex settings): a test build resolves them all in its own temp folder, and a lint keeps it that way; 35 more commands have reply tests.
- For contributors: the saved files that put fans, GPU, CPU, game rules, Target FPS, displays and sound back after a crash now have tests that load files saved by 4.0 to 4.6; unused code kept alive by `allow(dead_code)` was removed or limited to the tests.
- A page whose data comes after the time limit shows it as soon as it arrives, without pressing Try again; Programs and Battery health get longer to answer the first time.
- A page whose data never arrives now says "Deck didn't answer in time." with Try again after 30 seconds, instead of loading for good.
- A bug in one of Deck's Windows callbacks (window lists, pop-up windows, the zones and Wi-Fi watchers, music and volume events) no longer closes Deck or stops fan control: the callback is skipped and the problem is logged once.
- Right after Deck starts, it no longer asks for the same page data several times while preparing pages in the background.
- For contributors: `tools\check.ps1 -Area <area>` runs only one area's checks; build times and the slowest crates are in `docs/DEVELOPING.md`.
- Session reports: the game history keeps the last 500 sessions; older ones are let go when a new one is added, but each game's total play time and session count stay the same. Sessions you named, pinned as a baseline, marked as a benchmark or used in a timed run or a before & after step are always kept, as is each game's most recent session, and the daily energy table is kept in full.
- Two saves of the same file at the same moment can no longer collide and lose one; a few more of Deck's small files (the profile icons and shortcut runner, the PC to PC menu and Claude Code skill, Output EQ's saved original, the virtual display's settings, save backup records and one-time markers) are now saved whole or not at all.
- Hardware: pressing Start again twice no longer starts two restarts at once (the second says "Already starting."), and its messages read right for the GPU.
- Hardware: Start again now waits while Deck is still handing the fans or GPU back after a stuck driver call ("Still handing the fans back. Try again in a minute."), and works on PCs without a fan chip; its refusals are short.
- Hardware: when fan or GPU control stops after an error (a crash of its worker or a stuck driver call), the Fans, Lighting, Cooler display, Sensors, GPU pages and Home now say so with a **Start again** button. It restarts only when it is safe: the stuck worker has ended and the fans or card are confirmed back with the BIOS or driver; otherwise it says why. Quitting no longer waits more than 5 seconds for a stuck hardware worker.
- Fans: if the sensor reader stops answering, fans stop following its last (frozen) temperatures after 10 seconds: they follow the board's CPU sensor or run at full speed.
- For contributors: a test runs the watchdog's own wait against a stand-in process that is killed, quits with "recover only", or says goodbye, and checks what it releases each time.
- For contributors: the whole Rust test suite also passes when all tests run in one process (`cargo test`), not only one process per test.
- Updates: a failed install started right after Deck opens now keeps showing its error until Deck tries that version again, instead of switching back to "available".
- Arrangements: when Deck can't save, Undo no longer offers a way back that was already used.
- Two quick changes to the clipboard's app lists (plain-text paste, on-copy clean-ups) can no longer save out of order and lose one; a saved list another program holds open is no longer replaced by an empty one; quitting waits up to 2 seconds for such a save to finish.
- When another program has one of Deck's small saved files open, changes to it (clipboard app lists, wake-on-LAN PCs, sound rules and profiles, saved actions, Output EQ) now say "Couldn't save: another program has the file open." instead of seeming to work and being lost; a refused entry (not an .exe, a full list) no longer rewrites the file.
- Session reports: the list's top row shows "Playing now" as soon as the page knows a game is running, instead of briefly saying "Why did it stutter?" next to it.
- For contributors: Power and Audio now update the numbers that change each second in place instead of redrawing the page, so scrolling, an open menu and focus are no longer interrupted; they share small UI parts (`kit.js`) and design tokens (`tokens.css`), and five unused Audio style sheets are gone; no screen looks different. Settings changed from the phone or Settings still show on Power at once.
- For contributors: every code-health check now has a test proving it catches a violation; four old plans moved to `docs/plans/archive/`; the line count reports docs on their own.
- For contributors: the update, start-up and uninstall tests also pass when all tests run in one process, and the uninstall list check catches more kinds of change.
- For contributors: tests for updates that fail, going back to the previous version, what an uninstall removes, a start with damaged settings or a crashing worker, and a second Deck started while one runs.
- For contributors: the device-battery readers share one report log, one HID link and one freshness rule (95 fewer lines); no screen or saved file changes; their tests also pass when all tests run in one process.
- PC to PC transfer and Project sync each log a PC with a wrong code on their own again (one no longer hides the other's line).
- For contributors: PC to PC transfer and Project sync now share one copy of their network encryption and framing code; nothing looks or behaves differently and the two PCs still talk to older versions.
- Graphics card fans the driver refuses to take back after a stop stay marked as Deck's, so quitting still hands them back.
- Quitting Deck while fan or GPU control is stuck now hands the hardware back first, and if that fails the backup watchdog releases it after Deck has ended, without counting it as a crash or restarting Deck.
- If the fan or GPU control stops answering for 20 seconds while Deck holds a fan speed, Deck now stops it, tries to hand the fans back to the BIOS and the driver (several times, with the watchdog as backup) and tells you the result: restart Deck, or restart the PC if the fans may be stuck.
- For contributors: 4 commands nothing called, 15 repeated command registrations, 4 old first-start settings flags and an unused library were removed; no screen looks different and old settings files still load. The command type list is regenerated.
- Handing the fans back to the BIOS a second time (after a crash and then quitting, or by the watchdog after Deck already did it) no longer sets them to full speed.
- For contributors: 14 commands that take Deck's app state (CPU/GPU profile save and delete, game filters, clipboard groups, backup flush and more) now have reply tests through Tauri's mock runtime.
- For contributors: the codebase plan's progress table is up to date (two new batches); the search index is regenerated; the allow-list file check ignores line endings.
- For contributors: `docs/engineering/COMMANDS.md` lists all 569 commands with rights, untrusted inputs and run kind, and 35 commands that had no test now have reply tests on a temp data folder.
- For contributors: the codebase plan's progress table is up to date; the search index is regenerated.
- For contributors: 26 JavaScript functions and constants that nothing used were removed (about 120 lines); no screen looks different.
- For contributors: a clippy fix in the start-up machine probe.
- Security: each Deck window can now call only the commands its own page uses; the volume, toast, zones and now-playing windows can no longer reach hardware, file or update commands (the main window keeps every command its page uses).
- For contributors: `docs/engineering/FEATURES.md` lists every feature with the test that proves it still works.
- For contributors: about 1,380 lines of style rules that matched nothing in the app were removed; no screen looks different.
- For contributors: the architecture doc lists who owns each hardware, file, window and network resource and what happens when its owner fails.
- For contributors: `tools/quality/fnmap.py` lists every function an area lost, moved, renamed, changed or gained between two commits.
- Programs › Built-in apps and › App updates no longer freeze when Windows gives back nothing: they show the error with Try again instead of asking again on every redraw.
- For contributors: fixtures for 16 saved files and recorded PC-to-PC and Project sync frames, with round-trip tests (`docs/engineering/STORES.md`).
- For contributors: every test has a size tag (`[fast]`, `[fake]`, `[ui]`, `[slow]`, `[live]`, `[lint]`), browser tests are `*.ui.test.mjs`, `node tools/testing/run-tests.mjs fast` runs the quick set without a browser, and `cargo nextest run --profile fast` skips the slow Rust tests.
- For contributors: codebase plan version 4 and the `deck-rebuild` skill (the prompts for each reconstruction role).
- For contributors: the screenshot diff shoots every page from a fresh load, so a partial run compares like with like.
- A crash inside the GPU fan step no longer leaves the GPU fans pinned: the crash handler waits at most 2 s for the fan lock, then hands them back. A crash in a lighting, music, screen, game, power or cooler-display worker no longer stops fan control.
- For contributors: `tools/quality/costs.py` lists code lines per feature (`docs/engineering/feature-costs.md`).
- For contributors: `tools/quality/ratchets.py` and a lint test keep raw thread spawns, raw file writes, string errors, unguarded callbacks, long functions and two-way module pairs from growing.
- Lighting, Fans and Settings open at once after Deck starts: they no longer wait for the PC's hardware details, which Deck now reads in the background at start.
- For contributors: `docs/engineering/areas/` has a context pack for each of the 15 largest code areas.
- For contributors: one route list (`tools/testing/routes.mjs`) for every UI test tool, and `shotdiff.mjs`, a screenshot diff of every page in dark and light (stable across two runs).
- For contributors: the codebase plan's final version (`docs/plans/CODEBASE_PLAN.md`).
- For contributors: `docs/engineering/ARCHITECTURE.md` describes the target shape of the code (layers, a feature's parts, one way for each job).
- For contributors: `tools/quality/cratefit.py` checks how well today's modules fit the planned crate split.
- For contributors: `tools/quality` has the official line count and a Rust module graph script.
- Lower CPU use while Deck is hidden: the overlay worker no longer reads network speed when nothing shows it, and reads processor load more cheaply.
- Screen on your phone: **Fit PC to this phone** (Screen menu, off by default). While you watch, the PC's screen takes your phone's shape through the virtual display, so there are no black bars. The PC's monitors go dark meanwhile and come back when you stop, leave, go to another app, turn it off, or Deck quits (also after a crash, at the next start).
- For contributors: the UI test sandboxes know the kept-read names.
- A page you are looking at updates when its kept data changes behind it (Apps, Display, Startup, Taskbar, Power, This PC, Project sync, Crashes).
- For contributors: the page timer and screenshot list cover every page.
- Screen on your phone: the PC's pointer no longer flickers while Clock Contrast is on. Clock Contrast pauses while a phone views the screen and carries on afterwards.
- Pages open at once: Deck keeps every page's data in memory (a little more RAM), shows it the moment you open the page and looks again behind it, redrawing only when something changed. After start-up and each time Deck is shown it reads the pages in the background, the ones you open most first, never while a game is in front.
- Faster pages: Apps, Display, Startup, Taskbar, Power, This PC, Project sync, Crashes and Game profiles' Apps to close open on what Deck last knew (and read again behind it), so they no longer wait for a program start or a device read; the Apps list and Windows' startup measurements are saved for the next start. The clipboard list, overlay state and Windhawk reads no longer run on the main thread.
- Android app: cards for **Deaths** (+1, Undo), **Batteries** and **Alerts** on the PC page, your **output profiles** on Sound › Mixer, **+5** on a running timer and **Snooze 15 min** on a plan. A **Stats** page with the PC's live numbers in big tiles (open it from the numbers card), **Volume keys control the PC** and **Media controls on the lock screen** (both in Settings › PC controls) and a **Wake the PC** button when the PC doesn't answer (needs a pairing link made by this version of Deck).
- Android app: the PC icon uses the accent color, Voice's **Clean and stop** has its icon and Voice's light is no longer grey while Voice is on.
- Phone (web page and Android app): the PC's **Microphones** in Sound: mute, level, boost where the driver has it, and which one apps and games or calls use. **PC clipboard** now gets what is on the PC clipboard right now (nothing for private copies or text over 1 MB). The Android notification has **Mute voice** while Voice is on.
- Phone web page and Android app: the same look as the desktop (Aurora colors, Sora and Manrope fonts, rounder cards, pill chips, round slider knob, sentence-case card titles with a glowing dot). Chakra Petch is gone from both.
- Phone web page: four tabs (PC, Screen, Sound, Send). A new state from the PC no longer redraws the whole page, so your finger's button, the scroll and a sound's flash stay put. Volume sliders no longer flood the PC and keep where you put them. Clean up asks with Deck's own box, haptic ticks on taps, a custom timer length, **+5** on a running timer, **Snooze 15 min** on a shutdown plan, Restart and Shut down in their own Power card.
- Phone: a **Deaths** card (+1 and Undo), **Batteries**, **Alerts** and your **output profiles** on the web page.
- Screen on your phone (web page and Android app): a **Gestures** cheat sheet, the zoomed picture follows the pointer, three-finger tap is a middle click and three fingers swiping up open the keyboard, **Pointer speed**, scroll that keeps going after you lift your fingers and **Natural scroll**, typing that survives swipe typing and suggestions with a keys row above the keyboard, a bigger menu handle that remembers its side, quality as buttons (the detailed choices only for Custom), a "Weak connection" note, **Lock the PC when I disconnect**, **Fill** and a view that turns with the phone, a tap ring, and **Lock** instead of Ctrl+Alt+Del (Windows blocks that one). The Android app also keeps the Screen view in a small window when you leave it while only watching.
- Phone page: **Copy link** under the QR code, for the Android app's "Enter the link by hand". The app's steps and messages name the PC's real places (Connections › Phone › ...), its splash screen is dark, the last line of a page is no longer hidden behind the tab bar, album art shows on the PC tab, and the master volume is called "Device volume".
- Phone: Voice and the soundboard are on the phone, in the web page and the Android app (Sound > Voice): turn Voice on or off (Deck refuses with its reason, for example when CABLE Input is your default output), Mute, Stop all, Clean and stop, a light that shows you are talking, the Processing switch, voice effects with icons (starred first), the soundboard with search, Favorites, Short and Long, each sound's length, a bar that fills while it plays and a second tap that stops just that sound, Others hear and You hear levels, and Say it (up to 500 characters, never saved or logged).
- Phone: Chat mix (Game to Chat balance) in the Sound part, and the soundboard reaches up to 500 sounds instead of 120, with a note when more are on the PC.
- Phone web page: it reconnects at once when you come back to it, and a message stays on screen as long as it needs to be read.
- Screen on your phone no longer freezes on its first picture when Deck's debug log is on.
- Phones that reconnect often no longer fill up the PC's phone sessions (everyone got "All phone sessions are in use"): each phone keeps a few and the oldest one makes room.
- When this PC's address changes, phones with the new Android app stay paired: Deck keeps its key when it makes a new certificate, and pairing links now also carry the key's fingerprint. Phones paired with an older app need to scan the code once more.
- The Android app sleeps while it is in the background: a PC that doesn't answer is tried every 5 seconds at first, then less often up to every 5 minutes, the home network is scanned only after a network change or once an hour, and the PC sends its state every 5 seconds instead of every 1.5.
- The Android app tells the PC its name and version: "Update the app" appears when the app is too old for Deck, and "The PC is busy" instead of "can't reach" when it has no room.
- Android: a notice "Deck paused" when Android's time limit stops the background link; buttons in the notification, widget and tiles still work when the app is closed; scanning a new code replaces the old entry of the same PC; a certificate change is explained when you scan again; the Pad and Keys link waits longer after the PC says no; a refused phone mic no longer shows as on; the PC shows the phone's model in its questions.
- Phone: play, pause and skip work when two players share one Windows name (two browser windows); a plan like "Sleep in 30 min" counts on the PC's clock; plans made on the PC for a task, Deck's downloads, a transfer or a folder show their words on the phone.
- Phone: files shared to Deck from another app are copied first, so they still send after the share sheet closes; the camera turns off after pairing; Power's hold to shut down no longer asks a second time; a refused camera or mic offers Open settings; Deck asks for notifications once a PC is paired.
- Phone: the video format you pick on a phone applies to that phone only (it used to switch every phone to JPEG); screenshots no longer stall the Send button; wording uses US spelling, "Deck bar" and "Resume".
- The Android app finds the PC again on the home network: one fallback to Tailscale no longer replaces the home address, and phones already stuck on it repair themselves. It tries home first on every reconnect and when the network changes.
- The Screen view keeps its zoom, control mode and keys bar through a short drop of the connection, and retries 1, 2, 4, 8 s then every 15 s with the reason shown. Home or away is judged by the route actually used.
- The Phone page warns when this PC's network is set to Public and opens Windows' network settings.
- Phone screen view: the picture no longer freezes after the PC changes picture size (it used to need leaving and rejoining); when the PC sends pictures that do not arrive for 3 seconds, the phone asks for a fresh one and says "Waiting for the PC's picture" (a still screen is not a problem).
- Phone screen view: a change of picture size no longer stops the video for a moment on phones whose decoder supports it, the phone asks the PC for a smaller picture when its decoder can't take the size or can't keep up, JPEG pictures no longer hold up the connection, and Stats shows the decode time.
- A page you come back to after 10 minutes or more opens on its first tab instead of the tab you left it on hours ago.
- For contributors: the Autotune pitch sum uses fixed-size chunks (lint fix); search index regenerated after the cancel merge.
- For contributors: two unused functions removed; search index and command types regenerated.
- Loading placeholders no longer flash: a grey skeleton only appears when data are more than 0.3 s late, and then stays at least 0.4 s; fast pages draw straight in.
- Startup analysis, the file search refresh and the game-server ping test can be stopped with a Stop button; leaving a page never stops a running task.
- For contributors: the backend rules list the kept-answer and open-on-what-is-known rules once.
- For contributors: `tools/testing/live-speed.mjs` times every page's backend calls on the running app.
- Home and Game profiles fill in faster: the games list, a game's frame limit, CPU profile pictures and the Death counter's folder sizes are kept instead of read on every open, and the first open after a start is prepared ahead while the PC is idle.
- Slow pages open at once: Startup analysis, Clean up, Power & time and Diagnostics > Crashes draw their frame and what Deck already knows straight away, and the slow readings (startup log, folder sizes, wake details, Windows event log) fill in as they arrive. Startup analysis and Clean up remember their last result for the next start; the startup log reads run together instead of one by one.
- Voice: Autotune uses about half the processor time it did, Terrible mic and Robot a little less, and the voice wakes a little faster when a call starts after it was resting.
- Gaming opens with fewer redraws: its background reads share one redraw per frame.
- For contributors: command types regenerated for the new startup-analysis command.
- Search knows the labels changed by the speed and click fixes.
- Pages show their content sooner: Clean up no longer rescans the running programs once per browser on every refresh and keeps the Recycle Bin size for a moment; Disk space does not re-read every saved scan on each visit; Game profiles opens at once and fills in its PC-settings devices as they arrive; Startup analysis opens on the last result of this session (with its time) instead of analysing again.
- Lighter still in the background: the hot corner looks at the pointer less often while it is far from every corner, and the anti-cheat check reads Windows' list of program names directly. Nothing is switched off: fan curves, heat protection, alerts and per-core readings update as often as before.
- Lighter in the background: the sensor round visits each processor core once instead of twice, still motherboard lights are refreshed 5 times a second instead of 30 (moving effects and color changes are as smooth as before), and the graphics-driver watcher no longer lists every running program by itself.
- Lighter in the tray: while Deck's window is closed, its page hands its memory back to Windows after two minutes and takes it again when you open Deck; the page stays loaded, so it opens as it was left.
- Home no longer piles up memory: every visit to Home used to keep the previous Home's contents alive in the background (about 1,000 page elements each time), and several other pages kept one old copy of themselves. After opening every page once Deck's window now holds less than a quarter of the page elements it did.
- Less memory for long sessions: song names in Chinese, Japanese, Korean, Indic scripts, symbols or emoji no longer cost about 70 MB for the rest of the session once one is shown over a game; the file search index is about 45 % smaller; soundboard clips prepared for instant play (up to 46 MB) are freed when Mic and Soundboard is switched off.
- Snap zones switched off: Deck no longer keeps a hidden overlay window (and its web view process) for them. Switch them on and the overlay is ready at once, before the next drag.
- Faster pages: opening a page or tab takes about 40 % less time on a busy PC (measured over all 101 pages and tabs with the processor slowed four times), Home most of all. Pages that read several things (Clean up, Keep awake, Timers, Startup apps, Network, Arrange windows, Drive health and others) now ask for them together, so their data shows after one wait instead of several.
- Lighter while open: Home no longer rebuilds every tile each second, only the ones whose numbers changed; flipping a switch restyles its row instead of the whole page; the Mic level bar no longer makes the page lay itself out on every frame.
- Nothing runs in a hidden window: Lighting's preview, the cooler display preview, the Mic meters, the controller test and the once-a-second refresh now stop completely while Deck is hidden in the tray, and go on when it is back. The Lighting preview also paints only the previews that are on screen.
- Apps › Installed works with the mouse again: the filter, sort and Uninstall buttons and every app row answer the click (before, a click anywhere on the page selected the last app in the list).
- Game profiles: the favorite star and the More button on a game row can be clicked.
- Performance overlay in a small window: the preview no longer covers the settings under it.
- Hover: tabs, switches and tick boxes that are on, open folds and about 30 kinds of buttons (Home's quick actions, mute, hotkey boxes, color swatches, clipboard entries and others) now show that the pointer is on them. Fold bars show the hand.
- Easier to hit: tick boxes and their labels, the overlay's corner dots, the equalizer's handles and Home's volume sliders answer on at least 24 px.
- Search works with the mouse: pointing at a result selects that result and a click opens it (before, pointing anywhere selected the last row, "Search the web", and a click ran it). The pin and Show in Explorer buttons on a result work.
- Search: a pointer left resting over the results no longer takes the selection while you type or use the arrow keys, so Enter opens the first result; the wheel no longer changes the selection; the list stays where you scrolled it when more results arrive or after More Deck results; a double-click opens a result once.
- Search: a clear button (x) in the box empties it and returns to the page you were on, like Esc. Clicking the empty box always opens Pinned, Recent and Windows tools, and a click on their headings no longer closes them.
- Mic: the noise gate and compressor use less CPU while you talk; the sound is the same.
- Lighter while you play: with a game in front and Deck's window hidden, Deck's background work wakes the PC far less often. The volume flyout now waits for Windows to say the volume changed instead of checking 20 times a second, the hot corner stops watching the pointer while a full-screen app is in front (and is back the moment you leave it), chat mix at balance 0 no longer reads every app's volume every 2 seconds, the taskbar battery widget rests while a full-screen app covers the taskbar, and the hardware threads sleep through their pauses instead of waking 10 times a second. With the lock-key flyout on as well, the volume is only read again when Windows reports a change. Fan, sensor and GPU timing is unchanged.
- Chat mix: with the balance in the middle nothing is held any more, so every app simply keeps its own volume.
- Hot corner: a pointer left resting in a corner behind a full-screen game no longer counts when you leave the game; move out of the corner and back.
- Starting (measured on one PC: ready in 0.9 s, was 2.7 s): Deck no longer waits for Windows' task tool on its main thread (about 0.6 s sooner to ready), asks it 5 times instead of 9, and reads the list of browsers from the registry directly.
- Mic and Soundboard cost almost nothing while unused: when no app records the cable, no sound is playing, Hear myself is off and the page is closed, Deck now stops its audio streams and lets go of the microphone instead of keeping them running (this was about half of Deck's CPU use during a game). They start again right away when an app listens, a sound plays or you open the page, so a sound pressed after a quiet spell plays from its start.
- Less disk writing while you play: Deck used to rewrite its whole game history every 30 seconds; now it saves only the running session that often.
- For contributors: scripts measure what Deck itself costs the PC (`tools/testing/perf`): CPU, wake-ups, memory and threads, which thread is behind them, and an idle baseline in one command.
- Taskbar: the device battery icons and the taskbar widget now change color together with the clock when they follow Clock Contrast (they used to lag by up to 5 seconds).
- Smoother inside pages: switches slide, selected buttons and tick boxes fade, bars glide to a new value, and rows you add, remove or reorder fade and glide instead of jumping. Dialogs, menus, help cards and folds now ease out as well as in, and the Saved mark draws its tick in. Switching pages and tabs is still instant.
- Search knows the pages and labels changed by the motion work.
- With Windows' animation effects off, Deck keeps gentle fades and drops sliding and scaling. **Reduce effects** still turns all motion off.
- Labels now match the guide: Equalizer, Show in Explorer, Settings › CPU and GPU, Needs administrator.
- Developers: DECK.md is split into a short core and one rules file per area in `.claude/rules/`; the label check reads them too.
- User guide: every page rewritten to match the app's current labels, about half as long, with sections for the new Mic page, Mixer › Devices, Power use, Crashes, Lag spikes, desktop scenes, bulk uninstall, tweak drafts and more.
- For contributors: end-to-end tests on the real app (`tools/e2e/run.ps1`), run on a separate test copy of Deck that leaves your settings and hardware alone.
- Help: every **?** explanation is shorter (a third fewer words, none over 60), with the same safety notes.
- Wording: the same thing has one name everywhere, including the tray menu and Windows notifications. Error messages say what went wrong and what to do ("Couldn't copy the link."); confirm boxes ask the action ("Reset widgets?"); paused downloads and transfers **Resume**; missing values say **No data**; the Lighting effect is **Color cycle**.
- Buttons that repeat something after an error say **Try again**; buttons that re-read a list say **Refresh**.
- Headset controls unlock with **Use untested** on each headset's card (for testers).
- Search no longer offers the old Microphones and Mic processing tabs; their controls open the new Mic page or Mixer › Devices.
- Disk space: the arrow beside a folder opens it again (it had been broken since 3.3.0).
- Windows tweaks: a setting with its own value now shows it, for example **Custom: 300** for the menu delay or your own DNS servers.
- Clean up: selecting a category lists its largest files and folders, with size and age, before you clean.
- While a game runs, a disk scan, app updates, a workspace that closes apps, a display mode change and fan measuring first ask with one **A game is running** box.
- Apps: the installed list is one Tab stop (arrow keys move between apps), and picking an app no longer redraws the whole list.
- Project sync: **Restore** in Protection puts one file back from a saved copy; the file as it was is kept as a copy too.
- After an update, **What is new** in Settings › About also lists **What moved**, with a button to open each moved setting or page.
- Volume pop-up: "Not available" after a failed change now clears after two seconds instead of staying until the next pop-up.
- Screen tools: the first tab is now called **Capture**.
- Sidebar order can be changed without dragging: **Arrange** in Settings › General, or Alt+arrow keys on a sidebar group or page tab.
- Phone: the connection-limits card is now called **Connection limits**, and the chrome://flags steps for installing the home screen app only show under **No Install app?**.
- Display: **Auto HDR** next to a monitor's HDR switch opens Windows' own HDR settings, where Auto HDR is switched.
- Benchmarks (Unigine, 3DMark, Cinebench), stress tests (FurMark, OCCT), store launchers, crash reporters and engine editors no longer show up as games or start Deck game mode. The list is under Game profiles › Games › Built-in list, where you can count one as a game again.
- Wording pass 2: help text and error messages use US spelling and Select instead of Tick.
- Wording pass 2, Startup: Startup apps shows **At most** beside the total; shorter Startup optimizer rows; Windows tweaks alert offers **Details** and **Apply again**.
- Wording pass 2, Clean up: shorter category lines; Disk space **Free up space**.
- Wording pass 2, Windows: workspace Now / Last opened / Restore lists are one line per item; **Start order** in the workspace editor; **Color preset** on the monitor menu.
- Wording pass 2, Settings: quieter hot corner rows; Weekly backup says passwords and keys are left out.
- Wording pass 2, Connections: Project sync conflicts offer **Use this PC's version** / **Use their version**.
- Wording pass 2, Taskbar: shorter pop-up rows; Windhawk's warning reads **In N games**.
- Wording pass 2, Diagnostics: stale network values read **Stale · 5 h ago**; Crashes **Refresh**; Network **Trace** and **Games**.
- Wording pass 2, PC status: alert rules use **conditions** (Add condition), **Built-in alerts**, Drive health **Drive details**.
- Wording pass 2, Devices: device cards say **In tray** and **Warn in games** (were Shown and In games); Controller › Test **Input timing**.
- Wording pass 2, Audio: shorter Mixer, Mic and Soundboard descriptions in search.
- Wording pass 2, Lighting: Cooler display **Flash red when hot**.
- Wording pass 2, Hardware: **Reset all hardware** says what it resets (was Reset to default), GPU **Power limit** (was Power allowance), clearer power-limit mismatch line.
- Wording pass 2, Gaming: shorter labels on Game profiles (Game priority, Custom, Pick a game), Performance overlay (Sensors, Show overlay, Frame rate limit on/off), Death counter and Deck bar (Open now); the misspelled "centerd" is fixed.
- Wording pass 2: Home's PC readings tile is now **PC status**.
- Search knows the new Mic page, Recent captures, scenes and headset controls; the Mic card's ? explains the level marks.
- Mic processing sounds more natural by default: noise suppression at 80 % (no more comb effect when it is below 100 %), noise gate off and softer when on, EQ off, a lighter compressor. **Reset to natural sound** puts a changed mic chain back, with Undo.
- AMD graphics cards show more readings on Sensors: hot spot and memory temperature, core and memory clock, power, fan speed and memory used, when the card reports them.
- AIO coolers: with liquidctl installed in Program Files, Sensors shows the pump speed and liquid temperature. Deck only reads them.
- Bluetooth headsets that give Windows no battery level can show one from their hands-free connection, marked approximate.
- Settings › About has a Tester mode for people testing Deck on new hardware: it shows what Deck detected and copies a short tester report with no paths, names or serial numbers.
- Audio is now **Mixer · Mic · Soundboard**. The new **Mic** page has no tabs: it says what others hear right now, has one Processing switch (off passes your plain mic through instead of going silent), your mic with level, input volume and a 5-second test, a setup check with one-click fixes (first run shows numbered steps), the stages acting on your voice now with their settings in place, and your effect (**None** replaces Clean). Windows mic jobs (default for apps and calls, mute, boost, Listen, rename, on/off) moved to **Mixer › Devices** (was Outputs & rules). Old links open the new places.
- Pages that are still reading show grey placeholders shaped like their content instead of "Loading…", zeros or "No reading", and the content fades in where the placeholders were, so nothing jumps. Buttons that start slow work (scans, tests, installs, apply) all show the same spinner and "…ing" label while they run; every dialog fades in.
- Workspaces are desktop scenes: one Open can also switch CPU and GPU profiles, set the brightness and turn notifications off, besides closing apps, switching the sound output and keeping the PC awake. Each part shows its own result; **Now** shows what differs from your PC, and **Restore** puts back only what the workspace changed.
- Headset controls on Devices › Device batteries: sidetone, auto power-off and voice prompts for the HyperX Cloud Alpha Wireless, sidetone for Logitech G633, G635, G733, G933 and G935 (whose battery now shows too). Not tried on these headsets yet: **Try untested** on the card unlocks them for testers.
- Mouse lighting: Strobe now flashes 0.5 to 3 times a second, like the board's Strobe, and is listed only for mice that report the effect it uses.
- Charts: every readings chart says **now**, **min** and **max** in the same words, under the chart on Sensors › Graphs; the CPU and GPU charts grow to the height of the readings beside them.
- Deck bar: the opening hint shows once, at your next game, as a small card drawn over the game (it never takes the focus). It turns itself off after it shows or when you open the bar; **Opening hint** on the Deck bar page turns it on again.
- Hardware pages say "Reading…" instead of "Loading…", "Not measured" or "Unavailable" until the first reading arrives (fans' signal line, curve preview, CPU power used, the CPU and GPU "Not measured" chips).
- Screen tools: **Recent captures** keeps your last 10 Ruler measurements and Text extractor texts to copy again. Kept on this PC only, sealed for your account, never logged; **Clear** deletes them.
- Windows tweaks: **Draft changes** now reviews each tweak's effect and tradeoff before Apply, applies them in the order chosen, and lists each result with its own Undo.
- Keyboard: Tab now reaches the page after the search box's grid of pinned pages and Windows tools (it used to drop focus on every page).
- Clearer text in a few places: the inspector's small heading, Startup's "Enabled" and the Clean up icons now meet contrast in every theme. In a narrow window the page's scrollbar is no longer cut off.
- Wording: **Put back** is now **Undo** (What Deck changed: **Undo all**); "ticked" apps are "selected"; one name, **Frame rate limit**; "by itself" reads "automatically"; shorter setting names (**Temperature alerts**, **Log to file**, **Stand-up reminder**, **Eye-rest reminder**); US spelling throughout.
- Third-party notices now list the Sora and Manrope fonts and the remaining MPL-2.0 and CDLA licensed libraries.
- Disk space: the arrow in front of a folder opens and closes it in the tree again.
- Tweaks: a preset this PC already matches says so when you point at its button.
- Phone remote: tests now prove that keys, mouse buttons and the controller are let go when a phone disconnects, that a phone can reconnect at once, and that a slow line never builds up a queue of pictures.
- GPU: when Reset GPU fails, the page keeps showing the profile that is still active and says what is still set. Duplicating a CPU mode reports a failure instead of making a copy without the mode's settings.
- Startup optimizer: sign-in tasks and automatic services are each one row with their names inside, instead of many rows with the same text.
- Display: Digital vibrance and monitor sliders no longer jump back to a preview value after you let go; a monitor that reports a broken brightness or contrast range is no longer written to.
- In Windows Safe Mode Deck changes no fans, lights or graphics card settings; the hardware pages say so.
- Settings › About › Diagnostics: log areas have plain names instead of internal ids. Cards for hardware Deck can't control yet say the report goes to Deck's GitHub issues and open that page.
- Taskbar › Clock Contrast: when the separate ClockContrast app is painting the clock, the Live card says so instead of "Off".
- Drive health: the ? says warnings are off until you turn them on.
- Voice effects and Soundboard: no more loose text on the page; setup steps sit in the Voice card with details behind ?.
- The vendor-app warning on Lighting, Fans and CPU no longer pops in late and shifts the page.
- Network opens on Lag spikes: the last spike, where it started (this PC, router, provider or past it), what else was running, and fast pings in games (Off, Low or Normal). Long app and game names stay inside the cards. Lag while busy now tests upload too.
- Diagnostics has a Crashes page (Timeline, Profiles, Deck health) next to Session reports and Network.
- Diagnostics has a **Crashes** page beside Session reports and Network, with three tabs: **Timeline** (Windows crash records of the last 30 days: pick one to see its details beside the list, with the sources read, Read again, Copy report and Reliability history), **Profiles** (Record Windows crash reports, crashes per profile and the crash history, formerly Profile stability under Session reports) and **Deck health**. The sidebar shows "N new" on Diagnostics for unseen crash records, and the crash notice in Activity opens Crashes.
- Session reports: the list holds only sessions. Show latest only, Include sessions under 1 minute and the two report options moved into a ⚙ menu at the top of the list; Deck game mode history is now **Deck game mode runs** in the game filter, each run with its own figures. Menus with on/off items now show each item's state with a check box.
- Network: new first tab **Lag spikes** answers "why did I lag?". The last spike leads: when, how long and in which game; the delay before and at its worst, lost pings and whether the game got no data; the path **This PC → Router → Provider → Internet** with where it started; what else was happening (other apps' uploads and downloads, Windows Update and Delivery Optimization by name, Wi-Fi scans, moves and drops); and one **Suspected** cause. A list of the last 24 hours sits below, with one **Record lag** switch.
- Network: **Fast pings in games** (Off, Low about 4 kb/s, Normal about 14 kb/s, default Normal) catches 2 to 5 second spikes the one-minute recorder missed, only while a game is in front and recording is on. With Data per app on, Deck also sees when the game got no data from the same Windows network events Task Manager reads; it never reads or touches the game.
- Network: the recorder now also pings your provider's first router, so a spike can be placed at your router, your provider or beyond.
- Network: Overview is now **Connection**; its verdict counts today's lag spikes instead of a 24-hour "Good" that hid them, and "Now" reads **Last minute**. Your targets are **Watched targets · recorded**; Tests' Ping is **Live ping**.
- Lag while busy: now tests uploads too, uses 4 streams for 6 seconds each way, and grades on Waveform's scale (A+ to F). Fixed: on fast lines (over about 300 Mb/s) it no longer fails with "the download was too slow"; it says when the line is faster than the check, and **Line not filled** when it moved under half of your last speed test.
- Session reports: the network lane (now with lag spikes) is on by default.
- Search finds the redesigned session report rows.
- New page **PC status › Power use**: the whole PC's power right now, energy and cost today and this month, this month by part, a list per day, and the price, power supply and monitors settings, with **Apps on battery** on laptops. It is the one home for these: Game profiles' Power section and Keep awake now link to it, and Home's **Energy** label opens it.
- Fixed layouts: the icon in every details panel header (no longer clipped inside a box), the Processes table under its details panel, Clipboard image cards piling up, the Chat mix level label, the refresh-rate "Fewer rates" button (now a link under the rates) and Digital vibrance (now 50-100 % like NVIDIA's control panel).
- Death counter: Counter settings is its own tab instead of a fold under Now. The time-per-try chart no longer draws its labels and dot stretched.
- Performance overlay: slider values no longer overlap their unit ("32 chars", "2 lines"); scales read "1 … 24 lines".
- Apps to close: the selected app's icon is drawn exactly like the list's, no longer cropped.
- Game profiles no longer has the idle game mode bar or the Ready to play strip at the top; the session bar shows only while Deck game mode is on, and Ready to play stays on Home.
- Session reports: a report is now one column of cards with nothing folded inside another: a summary (grade, main cause, average FPS, 1% low, hitches), the timeline, **What caused stutters** (click a cause to filter), one **Moments** table, frame times, this game over time, **Details** and **Tools**. A moment's raw readings open from **All readings**; explanations moved behind **?**.
- Session reports: the session tools are one row of buttons (Rename, Pin as baseline, Export, Compare with, Mark as benchmark, Before / after); steps and timed runs show only once there are some.
- Session reports: a frame that spanned time Deck didn't read (the game in the background, loading, or Deck's reader delayed) no longer counts as one long frame. It made the 1% low read 1 FPS and the slowest frame several seconds. Older partly read sessions hide those figures and say "Frames read for 17 of 70 min".
- Game profiles: the last session card no longer holds a copy of the report; **Open full report** opens that session in Session reports.
- Device batteries: a GameSir controller no longer shows a second "Xbox 360 Controller" card from its dongle.
- Device batteries: a mouse or headset in use no longer shows as asleep after one missed answer; Deck asks again after 30 seconds. The moon after an asleep device on the taskbar widget is now a setting, off by default.
- Search finds the new taskbar widget wording.
- Taskbar battery widget: it is now part of the taskbar, so it no longer disappears after you click the taskbar, Start or Show desktop, and slides with an auto-hidden taskbar instead of blinking off and on. It takes the clock's color when Clock Contrast recolors the clock, asleep devices stay at full strength with a small moon, captions are larger, and pointing at it shows a highlight like the taskbar's own buttons; a click anywhere on it opens the list.
- Battery rings now fill from the left like every other ring, so the empty part is always on the right.
- Developers: CONTRIBUTING.md, AGENTS.md and a pull request checklist describe the code rules.
- Search opens the overlay limits in Look.
- Search finds the merged Overlay Look warnings, the editor header and Export my setup.
- Search finds the slow-PC history, laptop app power and the uninstall cleanup card.
- Developers: a process-deadline test no longer depends on PowerShell modules.
- Search finds the new v5 features and the new sidebar groups.
- Updates are signed: from the first release that carries Deck's update key, Deck installs an update only when its signature checks out, so a tampered or swapped setup on the release page is thrown away and your Deck keeps running. Older versions update to it as usual.
- Processes › Right now: each finding links to what caused it (**Select** picks the program in the list; busy background programs open **Startup apps**; memory and disk open Windows' Resource Monitor), with **Startup apps**, **Resource Monitor** and **Reliability history** always one click away. **Earlier** shows the last 24 slow moments Deck saw while the page was open, with the same links; **Forget** clears them.
- Power & time › Keep awake (laptops): **Apps on battery** estimates each app's draw in watts while unplugged, from its share of the processor and graphics against what the battery and sensors measure, with the screen and the rest on their own line. Desktops don't show it.
- Apps: after you uninstall an app (one or several), **Deck still points at it** lists Deck's own game profiles, workspaces, pinned items, window rules and sound rules that still name it. **Remove** clears them in one step and **Undo** puts them back.
- Every round gauge now looks like Home's PC readings: one ring with a thick coloured arc, rounded ends, a quiet track and the value inside, without tick marks or 0/100 labels. This covers the battery rings on Device batteries and Controller, the memory ring in Apps to close, and the rings on App updates, Store apps, Disk space, Clean up, Apps and Built-in apps. A missing reading shows its words over an empty ring, never 0 %.
- Performance overlay: the **Warnings** tab is now the **Turn red when…** section at the end of **Look**, with a **Color by load** switch on the Load card. Old links to Warnings open Look.
- CPU and GPU profile editors: the **Profile** tab is gone; the icon, **Name** and **Shortcut key** sit in the editor's header beside **Save**, and **Desktop shortcut**, **Start menu** and **Lighting color** are under its **...** button.
- Open folds no longer have a colored stripe down the left side; their heading and a light tint mark them.
- Taskbar › Clock Contrast: **Pause behind full-screen games** (off by default) stops reading the screen while a game fills it.
- A brand-new install starts with PC to PC (and, as before, the phone remote) off until you turn it on. Updates keep your settings.
- Phone › Screen: choosing **Control** says once what it allows ("A paired phone can then click and type on this PC as you; it pauses while a game is in front.").
- Death counter: only real deaths and only your own count. A death screen read together with a co-op banner about a phantom, summon, ally or partner is left out, and Lords of the Fallen's pull into Umbral is not a death (not checked in the game yet).
- Vendor apps that also control fans, power or lights (Armoury Crate, iCUE, G HUB, MSI Center and others): the warning line on CPU, Fans, Lighting, Cooler display and the Performance overlay has a **Pause** button. It asks first with the list of services and programs that stop, stops them for this session only, and **Start again** (on the line or in **What Deck changed**) brings them back; a restart of the PC does too. Nothing is uninstalled or turned off at Windows start, and Pause is refused while a game is in front.
- Settings › Data & recovery: **Export my setup** and **Import my setup**. Pick the parts with tick boxes (settings and profiles, fans and lighting, death counter history, clipboard history, checked files), then **Save to a file** or **Send to another PC** through PC to PC; importing lists the file's parts and restores only the ticked ones.
- Chat mix shows the level of both sides.
- The sidebar has more, smaller groups, so no tab row needs a **More** menu any more: **Lighting** (Lighting, Cooler display) has its own group next to Hardware; Desktop is now **Windows** (Arrange windows, Display, Screen tools) and **Taskbar** (Taskbar, Music & volume pop-ups, Clipboard); Maintenance is now **Clean up** (Clean up, Disk space, Apps) and **Startup** (Startup apps, Startup optimizer, Windows tweaks). Every group shows all its pages; your sidebar order, hidden areas and links carry over, and searching the old names still works.
- Controller › Test: a **Delivery** test. Pick **Cable** or **Wireless**, press **Test delivery** and keep a stick moving for ten seconds: Deck shows fresh readings a second, the longest wait and dropouts, with one result per link side by side (Steady, Some gaps or Unsteady). It only listens and never runs with a game in front.
- Session reports: **Timed runs**. While a game plays, name a run, pick 30 s to 5 min and the scene, and press **Start run**; Deck measures that stretch of the session's own frames (average, 1 % and 0.1 % lows, hitches, worst frame) and stops by itself. **Compare runs** sets two side by side and warns when the games, lengths or scenes differ.
- Session reports: the timeline shows **hardware limits** (GPU power or heat limit, CPU at 95 °C, video memory nearly full) and, with connection quality added to reports, **network moments** on the same time axis, each marked Seen; short or unrecorded sessions say "Network: not enough data".
- Save backups: copies are also made when a game starts without Deck game mode and before a game rule applies. A copy waits while the game is still writing its saves and tries again if the files change mid-copy; it is skipped over the size limit or with under 1 GB free, and the game's Saves section shows when and why.
- Typing anywhere in Deck goes to search, but never while a field, a drop-down, a menu or a shortcut recorder has the keys. The first time you close Deck's window a note says it is still running in the tray; the first time the hot corner opens Deck, a line says so.
- Soundboard: **Say it** speaks what you type into the call with one of Windows' own voices (pick the voice and Slow, Normal or Fast). Nothing is downloaded or saved.
- Mixer: **Chat mix**, one dial between your voice-chat apps (Discord to start with) and the game, like a headset's ChatMix wheel. It scales each app's own volume and puts it back when turned off. There is no per-app equalizer: Equalizer APO works per output device.
- Devices: a headset's card shows what its family offers (battery, charging, sidetone, mic light, auto off, chat mix, EQ), from HeadsetControl's device list. Deck still sends no settings to headsets.
- Clipboard: **Paste stack**. Turn it on, copy several things, then **Copy next** puts them back one at a time, oldest first, to paste with Ctrl+V. Password-manager copies never join it.
- Display: **Identify** shows each display's number on its screen for 2 seconds. It never takes the focus and is refused while a game is in front.
- Network, Connection quality: **Your targets**, up to three addresses of your own (a game server, a VPN) pinged with the recorder, shown as delay and probe loss for the last 24 hours.
- Settings, Data & recovery: every kind of Deck's data shows the limit it is held to, and Clean up lists **Deck's game artwork** (unticked).
- Apps: **bulk uninstall**. Press **Pick several**, tick apps and **Review**: each app shows what depends on it (a launcher's games, startup entries, Deck game profiles and workspaces), and an app the others need goes last. Deck then runs each app's own uninstaller in turn and lets it ask ("2 of 5"); nothing is removed quietly, and Deck asks first for a Store app. Each app ends **Removed**, **Cancelled** or **Failed**; a cancelled or failed one stops the queue. Windows runtimes and drivers can't be ticked. Nothing starts while a game is in front.
- Shut down when...: three new conditions name the job they wait for: **Deck's downloads finish** (Store apps, Deck updates), **A transfer finishes** (PC to PC, copies to a drive) and **A folder stops changing** (a download manager's folder, an export). The running plan shows the job and its progress; a job that fails, is cancelled or whose folder disappears calls the plan off with the reason. The 60-second warning with Cancel stays.
- Disk space › Make room: say "I need 80 GB free on D:" and the plan shows what is free now, what is still needed and the space you would **really** get back: caches that refill, hardlinked and online-only files count as zero, compressed files count their size on disk.
- Network › Data per app: the selected app shows **Last seen** and bars for **Data per day** over 7 or 30 days; list rows say when an app last moved data, and apps not seen in 30 days keep their last day.
- Fans: a **Noise test** per fan. The fan steps from 20 % to 100 %; press **I hear it** at the first step you can hear. **Keep curves under N %** then holds that fan's curves at the last quiet step (off by default; lets go above 80 C).
- GPU: **Find my undervolt** steps the voltage down 25 mV at a time at your card's stock clock under load (about 20 minutes) and saves the lowest stable step as a new profile. It refuses while a game is in front, has a Stop button and always ends at stock or on the result; a restart mid-test starts the card at stock and reports the last stable step.
- CPU and GPU: a profile shows **Crashed twice this week** when the PC, a game or the graphics driver crashed while it was on. Hard resets count even without Windows crash reports on. Deck never turns a profile off by itself.
- Lighting: **Reactions** flash the lights on a heat alert, a death counted or a profile change (the new profile's colour), each with its own switch, off by default, never more than three flashes a second.
- Energy: the figures are now a whole-PC estimate. CPU and GPU stay measured; memory, drives, board, fans, pump, lights and USB are estimated, and the power supply's loss is added from its 80 PLUS rating (pick yours; Gold 750 W by default). A game's **Power** section in Game profiles shows the split, with the power supply next to it; the Home tile's tooltip shows it too. Monitors can be counted with your own figure.
- Settings: PC to PC, Phone and Project sync settings moved onto their own pages, so each is set in one place. PC to PC's are in a **PC to PC settings** fold under Send, Project sync's in a **Sync settings** fold under Status (both remember whether they are open), the phone's power commands under Connect and its upload limits under Transfers. The PC to PC and Project sync switches now appear only on their pages. Settings › Connections keeps **Outside actions**. The GPU's **Profile when Deck starts** is now under GPU › Your profiles.
- Death counter: "Counter missing?" is now a **?** on the preview. Game profiles, Session reports and Clipboard settings cards have heading icons like the rest of the page.
- Search finds settings at their new pages and the new Taskbar Look tab.
- Settings: a feature's own settings now sit on its page, so each setting is in one place. Game profiles settings are at the end of Games, report options on Session reports, the death counter's settings in a **Counter settings** fold at the end of Now (it remembers whether it is open), **Keybinds in games** on the Soundboard, clipboard settings under the history and **Install Store updates when downloaded** with Store app updates. Settings keeps the app-wide parts; old links and search open the new places.
- Output equalizer: a **Headphones** list with AutoEq corrections for 16 popular headphones (from the AutoEq project), offline; the curve fills the ten bands and **Earlier curve** brings back the one before. Pasting a profile stays for other models.
- Taskbar: a new **Look** tab with Windows' own taskbar settings (alignment, search, Task view, Widgets, badges, Show desktop, transparency, combining buttons), the same settings and undo as Windows tweaks, plus **Restart Explorer** when a change waits for it (asks first, not while a game is in front).
- Phone: the pairing steps now say the browser will warn "not private" and to choose Advanced › Proceed; the phone page explains "Not secure" once.
- Diagnostics shows a dot in the sidebar after a new unexpected shutdown, bugcheck, crash dump or hardware error, until you open Crashes and hardware errors.
- Home: the game card leaves out the CPU and GPU profile chips in the Playing layout too when that layout shows the CPU & GPU profiles tile.
- The Back button shows the whole page name.
- Search finds the new Maintenance and Navigation features.
- Navigation: when a group's tab row does not fit the window, its last tabs move into a **More** menu at the end of the row instead of scrolling out of sight; the page you are on always stays in the row.
- Navigation: **Back**. After a jump to another page (a search result, a Settings button, a Home tile) a **Back to <page>** button sits at the start of the tab row, or **Back to results** after a search. The mouse's Back button and Alt+Left also go back, inside Deck's window only. CPU and GPU editors still ask about unsaved changes first.
- Search: the words you typed are marked in the results. With the box empty, search lists your **Pinned** pages and 5 most **Recent** pages above the Windows tools; pin a page or tab from its result.
- Sidebar: below 1000 px wide the sidebar shrinks to a row of icons (names as tooltips), leaving more room for the page. **Settings › General › Sidebar style** chooses Automatic, Labels or Icons.
- Settings › General: **Keyboard shortcuts** lists every Deck shortcut in one place, with **Used twice** when two share a key and **Taken by another app** when another program holds it.
- Old links to moved pages, Settings parts and renamed tabs keep opening the right place (one table behind every link).
- Game profiles: a game that was removed is no longer kept as the selected game; the page opens on the game in front or the first one.
- Search finds the battery history, voice idle state and cooler display messages.
- After the PC wakes: the check now also covers fans, lighting, monitor brightness (monitors that answered over DDC/CI before) and the phone server, and tries a failed one again after 2, 6 and 20 s without holding up the others. It now runs by itself a few seconds after every wake (before, only **Check now** ran it).
- Startup optimizer: each finding says in one sentence what it cost and when ("Adds 2.4 s at sign-in; open it when needed instead."), so rows no longer repeat the same text; security software shows **Keep** with its reason and is never pointed at Startup apps; the same item listed twice shows once.
- Startup optimizer: new **Vs last start** card compares the last start with the one before: start time change and what became new, slower, faster or no longer slow.
- Apps › App updates: **Scoop** and **Chocolatey** cards list out-of-date packages when that manager is installed, with **Copy command** for the update line. Deck never installs or updates through them; Chocolatey asks its feed only when you press **Check**.
- Windows tweaks: seven new current-user tweaks: Language list for websites, Notifications on the lock screen, Apps Windows adds by itself, Ask before merging folders, AutoPlay, Control Panel view and Key repeat speed. Each reads back its value and undoes exactly.
- Device batteries: plugging in a device or receiver, or waking the PC from sleep, reads the batteries again within a few seconds instead of waiting up to 5 minutes (once per burst of changes; devices that failed keep their wait).
- Device batteries: each device card's history button opens its battery history under the cards for the last 24 h, 7 d or 30 d. Deck now keeps one reading every 30 minutes for 30 days next to the minute readings of the last 15 hours.
- Device batteries: **Warn at** offers Off or 5 to 40 %, and a warning re-arms only once the level has risen 10 points above it (or the device charges), so a reading that wobbles around the level warns once. Levels saved before keep working.
- Device batteries: the device report (for asking support for a device) lists the HID devices no battery reader answered for first, by ids and descriptors only (vendor and product ID, USB or Bluetooth, interface, usage page, report sizes); it no longer includes product names.
- Voice: while no app records VB-CABLE, the voice pauses its noise suppression and effect to save CPU (an **Idle** chip shows it) and starts again within a quarter of a second once a call app or game opens the cable. Sounds keep playing.
- Voice: a cable that is unplugged or reset while the voice runs is noticed and reopened instead of leaving the voice silent; an error inside the voice processing is caught (the voice goes on fresh), and after three in a minute the voice turns itself off and puts your default mic back instead of affecting the rest of Deck.
- Hardware pages: **Apply hardware changes** now tells you whether the settings reached the disk. A short **Saved** mark replaces the toast; when the save fails (for example a read-only settings folder) the bar says **Not saved** with the reason, nothing changes, and the controls go back to the saved values. CPU and GPU profile, Boost and per-game PC settings changes report a failed save the same way.
- Cooler display: **Show important messages** now covers finished PC to PC transfers (FILE DONE; it used to show a cut-off "TRANS"), and the HEAT message uses the display's °F when chosen. **Preview** shows any message on the page's picture for 8 seconds without sending it to the cooler.
- Sensors: the Alerts sliders, the alert-rule limits, the heat warning line and the Graphs temperature chart follow your temperature unit (°F when chosen).
- Drive health: the SMART attributes table fits a narrow window without sideways scrolling, its fold stays as you left it, and the drive temperature alert, chart and chip use your temperature unit.
- Developers: the preview harness draws the Cooler display with its real digits (it showed every segment lit), with a test that reads them back.
- Lighting: the light-count fields have room for three digits. Home: the Quick actions **?** is no longer cut.
- Search finds the new temperature bands and mode names.
- Search finds the device battery settings on the Devices page.
- Search finds the new Windhawk mode, Strobe lighting and the curve keyboard controls.
- Taskbar: Windhawk can now be told to stay out of every program but the taskbar and Start menu (**Only the taskbar and Start menu**), so it can't reach any game, including ones Deck doesn't know. Deck adds `*` to Windhawk's exclusion list and the programs your mods run in to its inclusion list, keeps your own entries, and can put both lists back from What Deck changed. A mod turned on later gets a one-click Add. Keep out of games moved under Other ways.
- Lighting: a new Strobe effect flashes your color, from one flash every two seconds up to three a second (never faster, for photosensitive safety). It is also a Cooler display color behavior, and devices following Deck through OpenRGB flash along.
- Processes: rows show the program's own name (Discord rather than Discord.exe; hover for the file name), and background helpers an app started (such as Steam's web helper) sit under that app in Running apps.
- Fan curves: edit them with the keyboard (Tab to a point, arrows to move, Delete to remove, Insert to add) or by touch (press and hold a point to remove it). Screen readers read each point. The GPU voltage curve editor has a screen-reader name and a bigger touch target.
- GPU and CPU overclocks: if Deck can't save its crash guard file, a risky profile is no longer applied (it says why). Before, the overclock went on anyway and a crash restart could bring it back.
- Device batteries: the Inline and Stacked taskbar widget now draws like the taskbar itself: Windows' own device icons (Segoe Fluent Icons, MDL2 Assets on Windows 10) and the taskbar's font, sharp at every display scale, in the taskbar's text color. The charging bolt and full check are small marks after the number; the caption for two devices of one kind is cut cleanly into the icon's corner.
- Device batteries: **Show in** picks Tray icon, Taskbar widget or Both. Taskbar widget alone hides the battery tray icons (Deck's own tray icon stays). Saved choices carry over: widget off is Tray icon, widget on is Both.
- Device batteries: every device-battery setting is now on the Devices page, in one **Tray and taskbar** card (tray and widget looks, what hides them, new devices, the device report). Settings no longer has a Device batteries part, and the Controller battery link in Settings › Gaming is gone; old links open the Devices page. The per-device switch is now called **Shown**.
- Device batteries: the taskbar widget follows the taskbar at once: it hides as soon as an auto-hidden taskbar starts to slide away and comes back when it is all the way in, instead of lagging behind it.
- Temperatures now say whether they are fine: a **Normal**, **Warm** or **Hot** chip or icon beside the temperature on Home, This PC, the CPU and GPU pages, Sensors and Drive health. The limits depend on the part (processor, graphics card, drive) and match the starter alerts.
- Charts show their numbers: the GPU clock chart on Sensors > Graphs fills its panel from the first reading and its scale fits the clock; the CPU and GPU clock charts no longer start at 0; temperature, load and power legends give each line's lowest to highest; History and the drive temperature chart give the latest, lowest and highest value.
- No more "not available" flash on start: Fans, Lighting, Cooler display, Sensors and the CPU and GPU tiles say "Reading…" until the first hardware reading arrives.
- Built-in mode names mean the same on CPU and GPU: the GPU's Fastest is now **Performance** and Normal is **Balanced**; the CPU's Ultra saver is now **Low power**. The Home tile is now **CPU & GPU profiles**. Your shortcuts and game profiles keep working.
- Fans: a **Show unconnected fans** switch lists the headers with no speed reading and says why (off by default).
- Taskbar: the Clock Contrast settings card is simpler. A preview shows the clock on four sample backgrounds and changes as you adjust. One Style choice (Subtle, Balanced, Vivid), then Reaction and Slower on battery; the fine settings sit under Customize with plain values and a ? each. Changes apply at once and save themselves, so Save and Discard are gone.
- Device batteries: the taskbar widget has a new default look, "Inline": each device's icon and percentage in the taskbar's own text color, like the taskbar's icons (red when low, a bolt while charging, a check when full on power, dimmer when asleep). "Stacked" puts the icon above the number; "Rings" keeps the earlier look. "Widget background" helps on see-through taskbars. Ideas from BatteryHub.
- Device batteries: the tray pop-up is much smaller (one row per device, a small "Open Devices" link) and opens centered on the icon you clicked.
- Taskbar: the Windhawk card is short when all is well (version, mods on, games kept out). **Keep out of games** adds the games Deck knows to Windhawk's exclusion list in one click, keeps your own entries, and can be put back from What Deck changed. The game list is behind Show games; mod rows show a chip only when something is wrong.
- Taskbar: Clock Contrast no longer says the Windhawk painter is too old when it is a locally built mod (it read the version only from Windhawk's catalog list).
- The shared death-screen library is now opt-in: new installs start with it off (turn it on in the Death counter settings). Installs that already had it keep their setting.
- Search finds the new voice effect, save backup and never-suggest settings.
- Every side panel (microphones, voice effects, app rules, workspaces, apps, startup, clean up, tweaks) opens with the same header as the selected row.
- Deck bar: labels on lit toggle tiles are crisp and readable, also with a custom accent color.
- Selected-item headers on Microphones, Voice effects, App rules, Workspaces, Windows tweaks and the Maintenance pages now share one look.
- Voice effects: each effect's menu has Move up and Move down (saved; the tray and the phone list follow the order).
- Game profiles: an optional "Voice effect" per game (PC settings > Voice). It switches your voice effect when the game starts and puts the earlier one back after (also after a crash). Off by default; a missing mic leaves the voice as it is and says so.
- Voice safety: What Deck changed shows "CABLE Output is the default mic" with your earlier mic and a Put back button; the voice refuses to start while CABLE Input is the default output; updates wait while the voice talked in the last 10 minutes; sound files over 200 MB are refused; broken phone mic samples can no longer poison the mix.
- Voice: Mic processing shows a short hint to set Discord's Noise Suppression (Krisp) to None while noise suppression or an effect is on.
- Game profiles: a fresh install with a game and no profile shows one "Starting point" card (Balanced, Performance, Leave my PC alone). Nothing applies until you click one, and the choice fills the Default profile, which you can change afterwards. Existing profiles are untouched.
- Death counter: the 12-week heat map now fills from a per-day series (90 days) instead of the newest 60 sessions, so older weeks are no longer hatched when they have data. Older days show their deaths, sessions and time played.
- Apps to close: "Never suggest" on an app keeps it off the suggestions and out of "Close them now". The list shows in Settings > Gaming (click one to allow it again) and goes with Settings > Data & recovery exports.
- Save backups (off by default): Deck copies a game's save folder when the game starts (before it changes anything) and when it closes, keeps dated copies per game with a size limit, and restores one with a click (a copy of the current saves is made first). Pick the folder per game under Game profiles > a game > Saves. Files only; nothing touches the game itself.
- Phone screen share: much less lag and blur. Fewer pictures wait on the way (3, was 12), the newest screen wins, quality follows the connection quickly (cut when pictures get late, climb slowly while the screen moves), motion keeps the full size at normal Wi-Fi speeds, and the picture sharpens a moment after the screen stops. No key picture dips every 5 seconds.
- Phone screen share: the phone no longer gets stuck on the heavy JPEG video after one slow start. It asks for a new picture and tries again; a JPEG saved by the old version is cleared once.
- Phone screen share: Smooth, Balanced and Sharp all adapt (no fixed 4 or 15 Mb/s), one tap sets one preset, and a new install starts on Balanced instead of "Custom".
- Phone screen view (browser): the menu is a two-column grid with an icon and a name on every item.
- Phone screen view: controls redone like Chrome Remote Desktop. The picture fills the screen with one small edge handle that opens a single labeled menu (Keyboard, Mouse mode, Keys, Quality, Screen, Sound, Stats, Full screen, Control, Disconnect). Trackpad mode is the default (slide to move with acceleration, tap to click, two-finger tap right-click, two-finger scroll, pinch zoom, tap-and-slide drag, three-finger tap for the keyboard); Touch mode is a switch. Typing goes straight to the PC, a connected keyboard and mouse wheel work, and Control and mouse mode are remembered. Same on Android and the browser page.
- Search: clicking the search icon always opens search (the folded icon closed again at once, and the icon in the full box did nothing).
- Settings: all 14 parts share one layout (same rail, links row, group headers and rows).
- Phone and browser remote: "Claude Code settings are waiting" no longer sticks on screen with buttons that do nothing. Questions only the PC can answer show as a short note saying to answer them in Deck on the PC.
- Claude Code sync no longer asks again and again about plugins' own per-PC files (plugin store, plugin data, catalog cache). They are no longer synced, and questions already waiting about them go away.
- Search finds the new Gaming settings (frame rate limit, notifications off, Pick something, Quick toggles, death backups).
- Internal: three UI tests brought up to date with the current wording and layout.
- Sensors: a long source description opens from the standard info button.
- Page header: when the tabs and tools do not fit on one row, the tools move under the tabs instead of hiding a tab.
- Page header: one tidy row at every width. Tabs start-aligned, the page's own icon buttons right after them, search, Activity, tour, pin and close end-aligned. When the row is full the search folds into an icon (click or Ctrl+K opens it), then Activity becomes an icon with a count; tabs scroll sideways rather than wrap. Windows 760 px wide or narrower put the tools on one row under the tabs, on the same left edge.
- Soundboard: no thin vertical line left of the ... button in a sound tile (the app-wide disabled-button border showed on tiles that cannot play); hover tints the whole tile.
- Microphones: notes keep their icon and text on one line with the button on the right; "Extra mic gain" shows Not available on the right like other values.
- Performance overlay: the corner is picked on a small screen with a dot in each corner instead of a block of four buttons.
- Death counter: space between the Bosses filter and the list.
- Tests: a guard keeps heat map day cells inside their grid slot.
- The panel beside a list (Selected app, overlay reading, game) now starts with a head that looks exactly like the selected row in the list: same icon tile, name style, accent bar and tint.
- Settings: all 14 parts now have one shape: title, an optional one-line fact, one "On their own pages" row of links, then groups with an icon and a short title and rows with the name on the left and the control in one 220 px column on the right. The summary cards (counts, charts, previews, memory meter) are gone; what a setting needs is a row (Indexed files, Saved on this PC, Version, Window mode, Theme and Accent color). The part list is a rail at 1000 px and wider and a drop-down below, on every part (Audio too). "Snap zones" reads "Snap & rules". Three group titles are shorter (New items, After a death, Outside actions; Paste as text and Copy cleanup on Desktop). A new test keeps every part on this shape.
- Death counter: heat map days you played no longer grow into the gaps and merge with the next day (the app-wide 32 px button minimum no longer applies to grid cells).
- Gaming: optional detailed after-game summary (peak temperatures, average FPS, hitches), off by default (Settings > Gaming).
- Game profiles: a PC-settings option to turn Windows notifications off while a game runs and back on after (also after a crash); off by default.
- Game profiles: Pick something suggests a Playing or Backlog game from your play time, with a Short filter.
- Game profiles: the default frame rate limit now lives on the Default profile (Performance); Performance overlay > Behavior keeps its on/off key and a link.
- Death counter: Settings shows how many older history copies Deck keeps, their size and folder (Open folder), and an optional second backup folder every backup is also written to.
- Deck bar: new Quick toggles widget with overlay on/off, mute mic and next profile (new widget; guide, help and search updated).
- Deck bar: an older saved list holding a hidden and a shown copy of one widget no longer drops the shown one.
- Sensors: a reading's long source description is an info icon instead of text spilling over the numbers.
- Network: the delay tiles wrap to two rows when the card is narrow, so values never spill.
- Home: PC readings are now Grafana-style arc gauges: a 300-degree arc open at the bottom with a thick rounded stroke, quiet track, softly graded value arc with a glow at its end and a faint center glow, a bold centered number with the unit beside it and the part name inside the ring; glows and motion are off with reduced motion or Reduce effects. Detail rows stay evenly spaced and divider-free.
- Game profiles: a game's star and menu show on hover or when selected; favorites keep their star.
- Death counter: Bosses sort by Recent, Most deaths or A-Z and filter All, Active or Beaten (sort is a dropdown beside Find a boss); the game picker reads "Follow the game in front"; the empty state shows how counting starts in three steps; Now shows the fight's confidence chip; Games says "Open on Now".
- Session reports: rows show "Little data" under 2 minutes and a crash marker when Windows logged a crash during the session; "Show latest only" keeps each game's newest session; short sessions say "(from N min)" after the hourly hitch rate.
- Game profiles: each game row has a menu with "Session reports for this game" and "Not a game"; Close apps shows which ticked apps it closes with an "Edit list" link; the idle strip offers "Turn on automatic profiles".
- Performance overlay: the Layout tab is now called Format.
- CPU and GPU: the Power & limits tab is now Sensors; a turbo overclock shows on the applied profile; the Cores tab has a heat strip.
- Fans: each fan shows its last 60 seconds and can fold its settings; Combine two curves and Follow another fan read as sentences.
- Vendor apps that may override CPU, fan or lighting settings now get one warning line each.
- Sensors: reading rows show where the value comes from; Graphs adds a GPU clock chart; Alerts offers CPU too hot, GPU too hot and Fan stopped starters; the CSV help explains # rows.
- This PC: Control paths is on the page. Processes: a Check files menu on the selected program.
- Lighting: Lights Deck controls lists each zone with its light count; Cooler display picks content from a Shows menu.
- Soundboard: a banner says when MicDrop blocks sounds; the delay and CPU chips say estimated and measured.
- Arrange windows: the Snap zones tab is Snap & rules; a workspace shows its Last opened result; new app rules stay hidden while app rules are off.
- Display: long refresh-rate lists show the common rates first, with an All rates button.
- Controller: the on-screen preview sits on a checkered backdrop.
- Windows tweaks: the details panel shows a downside only when there is one; Network tiles read Now, Average, Jitter, Loss.
- Tweaks: each row shows a one-line effect and a small warning chip only when the tradeoff is real; the details panel has both and Related pages. Network overview: Delay now, Average, Jitter, Probe loss. Settings part "About" keeps its short name.
- Clean up: Windows system caches sit under their own "Windows (needs admin)" heading. Space: each drive shows when it was scanned, a Quick wins row, and duplicates have "First copy only".
- Apps: pinned apps and the last update run are listed under App updates. Crashes: "No crashes recorded" when the log is empty.
- Startup optimizer: "Other startup items (N)". Network overview: Internet and Router delay now. Settings: parts Gaming and About & support, and an "Also set on other pages" footer. PC to PC: "Find on this network".
- Settings: four hot-corner rows (action and delay each), "Running as admin" on About; Show Project sync lives only in Features.
- Power: "What woke this PC" on Keep awake, a Break length choice in Break reminders.
- PC to PC: the Activity tab is now Transfers; more than three requests fold into "N more waiting". Network tabs: Overview, Game servers, Tests, Data per app.
- Tweaks filter "Off now" is "Not Windows default"; Boot optimizer "Undo fixes" is "Saved fixes"; Project sync says nothing was changed for a missing folder.
- Search: sensor history opens Graphs, temperature alerts opens Sensors Alerts, and always on top leads to Arrange windows.
- Processes: long program names end in an ellipsis and the table keeps its width.
- Home: Clock keeps its full title, with Week | Month on a separate row.
- Home: Quick actions use Text extractor, Ruler and Turn off display; longer tile labels wrap at spaces.
- Home: Light mode shows its Windows state or Not available.
- Home: CPU and GPU shortcut keys stay right-aligned beside their profile labels without overlap.
- Processes: program names use a single line with ellipsis and a full-name tooltip.
- Network: Overview cards fill complete rows, with connection history above the app and address cards.
- This PC: parts, volumes and specification rows fill available space without empty grid cells.
- GPU: Clock & limits keeps the clock and power limit without repeating the top sensor values.
- GPU: the live chart stays compact and shows Collecting until ten valid samples arrive.
- Fans: disabled trials show their reason in a chip and tooltip.
- Fans: the trigger-rule help button stays beside Cool speed.
- Fans: the reporting count is a live chip in the page head.
- Lighting: color swatches use two even rows.
- Lighting: effect tiles fill each row without an empty cell.
- Lighting: mouse help buttons stay beside their labels and actions.
- Lighting: Effect settings no longer repeats the selected effect name.
- CPU: missing readings use dashes with one Not measured chip per panel.
- CPU: per-core bars are labeled Load % and expose their live meter values.
- Hardware: Asked and measured shows one Verified summary in its head.
- Hardware: CPU and GPU profile panels align at the top and keep their content height.
- Arrange windows: window cards fill partial rows without leaving a grid hole.
- Snap zones: the connected monitor set name appears once above both sets of controls.
- Display: monitor cards keep their content height and stack at full width at 760 px.
- Clipboard: the Paste as dropdown fits its card and its menu can open fully.
- Clipboard: the history list and Selected pane share a height, with history scrolling inside its list.
- Taskbar: Fix in Windhawk opens the installed app normally as the signed-in user; the button is hidden when it is not installed.
- Keep awake: after-wake results use a Check row with status and Check now; per-part explanations are behind ?.
- Battery health: report availability and dates use label/value rows, with explanations behind ?.
- Power plans: Warn me before is the single warning-time setting; the duplicate draft warning is removed.
- Timers & breaks: Break reminders rows use the card's standard spacing.
- Screen tools: Locked files uses spacing tokens and removes extra margins and nested padding.
- Startup optimizer: delay figures wrap within their cards without clipping.
- Startup optimizer: Startup impact is inside its card.
- Startup optimizer: No starts recorded is shown only when no starts are recorded.
- Startup apps: summary tiles and impact keys fill partial rows without grid holes.
- Windows tweaks: one Show values toggle controls the entire history list.
- Clean up: the selected total is shown once when everything found is selected.
- Performance overlay: Corner uses a position grid outside the live preview, keeping every reading clear.
- Game profiles, Sessions: session titles, metadata and verdict chips occupy separate rows and wrap at narrow widths.
- Death counter: chart tick labels, try labels and legends have separate spacing.
- Death counter: the try-chart explanation is behind a question mark.
- Death counter: session and try charts live on History; View charts on Now and Bosses preserves the game or boss selection.
- Death counter, Games: the All games summary fills its width when there are no deadliest bosses.
- Controller, Battery: reuses Devices battery cards and their options, while keeping detailed history and its list.
- Devices: every icon action beside the tabs has an action-name tooltip and screen-reader label.
- Devices: a live-reading coverage bar and question mark replace the verdict sentence.
- Settings, Audio: compact navigation keeps the short form from leaving an empty column.
- Settings, Features: summary rows and the final sidebar-map item fill the grid.
- Phone, Connect: pairing and the empty phone list fill separate rows while waiting for a connection.
- Internal: CPU/GPU identity and Right now tests follow the current wording while retaining layout and behavior checks.
- Wording: leftover British spellings in the guide fixed; Startup apps groups say Enabled / Disabled like Task Manager.
- Wording: Audio, Desktop and Power & time pages use the names other apps use (Mic processing, Input volume, Hear myself, Ruler, Text extractor, Night light, Always on top, Excluded apps) and US spelling.

- Wording: Maintenance, Connections and Settings use the names Windows and other well-known apps use (Undo, Scan again, Remove files, Accent color, Reduce effects, Update automatically, Needs administrator) and US spelling. Windows tweaks are renamed after Windows 11 Settings and Winaero Tweaker (for example Show seconds in the clock, Enhance pointer precision, Hardware-accelerated GPU scheduling, Restart automatically after updates, Allow downloads from other PCs), with shorter effect lines.
- Wording: the **Game bar** page is now **Deck bar** (no clash with Xbox Game Bar). US spelling and common app terms across Home, Gaming and Devices: Custom profile, Frame rate limit, Update interval, Choose sensors, Undo, Select none, Not connected for a day. The Game profiles and CPU/GPU pickers use different group names (Power modes, Built-in modes).

- Wording, Hardware and PC status: **Sensors** instead of "readings", **Not measured** for missing values, **Reset to default** instead of "Back to stock", **Ramp up / Ramp down**, **Current** column, **Needs administrator** and **Restart as administrator**, **End task**, **Device specifications**, **Temperature alerts**, **Efficient cores**, RPM, and US spelling (color, behavior, canceled) on these pages, in help, tours and the guide.
- Internal: tests updated for the shorter pop-up and Startup apps wording (no visible change).
- Home PC readings: the ring and its number are centered as one unit, and Network has the same build as the other readings (a gauge of download against the fastest seen, with Down, Up and Peak rows).
- Death counter: the Death-screen library card has its status in the header and one row to paste and add a friend's code.
- Taskbar: the Clock Contrast Live card is a full-width band with the colors it picked (swatches, Lc, hex) and says whether Clock Contrast is off or not running yet.
- New: Deck's plain white battery tray icons take Clock Contrast's color while it runs; red and green ones keep theirs. Switch: **Tray icons follow Clock Contrast** (Taskbar and Settings > Desktop).

- Death counter: the Deaths per day squares no longer grow into each other on days with deaths.
- Desktop and Power pages, second review pass: **Taskbar** lists the games Windhawk does not exclude once (one chip, one name per game, five shown and **Show N more**) and has no tab row for its single tab; Clock Contrast says "Close ClockContrast first" beside its switch. **Arrange windows**: Place and Options are buttons, the empty Workspaces state is one card. **Display**: more than eight refresh rates are a dropdown, Picture sits under Display mode, the DDC/CI note is said once. **Music & volume pop-ups**: the preview shows on Placement only, the pop-up chips are real toggles, music apps show a state chip. **Clipboard**: the hint is behind "?", **Clear all** is in the History items header, an empty history is one card, **Pin to screen** is **Float on screen**. **Screen tools**: Copy text sits under an empty Colors card. **Keep awake**: without admin it shows a **Needs admin** chip and **Restart as admin**. **Shut down when**: row hints are behind "?".
- Death counter: games show their art (picker, games list, selected game) found the same way Game profiles finds it, also for games without a store id. Garbled boss names such as "Tro ka" are no longer listed under Deadliest bosses. The lists use the shared selected-row look, one short line per game, and the setup count shows a tick only when complete. Learned screens use one action cell on every row; "Game has none" is a checkbox. The range bar's latest mark is a tick, not a knob.
- Session reports: saved moments show 5 with **Show N more**, frame data gaps are one row, each row has one grid and says its kind once. The no-verdict line is shorter, **Compare** says "Needs 2 sessions" when disabled, and every game's row uses its art when Deck has it.
- Devices: the battery bar with a knob under each gauge is gone, a single device keeps a card-sized width, Rename and Forget have labels, the small battery chart has a caption, and the "Tray icons" count is out of the summary.
- Controller: segments on On screen share one width, the overlay's state word sits next to its switch, and picked keys are filled while others are outlined.
- CPU and GPU: every built-in mode now has a **Use** button like your profiles, the modes card no longer has an empty band under its title, the selected profile has an accent bar instead of a full outline, GPU profile lines show three values at most, the **Overclock** chip reads **Above stock**, and the average on the Readings chart is named above the chart instead of on the line.
- CPU and GPU Readings: Temp, Load and Power are no longer repeated in the Measured now card.
- Fans: Safeguards is one row above the fans, fans sit in two columns, Slow-down and Combine charts and the calibration charts have titles and axes, and Stop case fans no longer draws a second read-only bar. Not-measured fans show no marker.
- Cooler display: the title is always **Cooler display**, with a **Not connected / On / Off** chip.
- Sensors: the table and the cores sit at full width (no row descriptions, a small key, no sideways scroll); Processes program icons share one tile.
- Sensors: part names wrap to two lines, **Graphs** has **Charts / Table**, the table time column stays on one line, and without admin rights the page shows the processor, memory and disk readings that need none.
- Processes: "Right now" shows chips, "Not checked" is a chip, long window titles end in an ellipsis.
- Network › Tests: read-only scales show a marker instead of a knob, one line per ping row, the last reading stays visible when stale.
- This PC: the latency test button sits in its card head; the week and controls cards share a row height.
- This PC: **Control paths** is part of **What Deck controls** now (one list; the reason is in the row's hover text), the count includes fans and lighting that need admin rights, and words no longer break in the middle.
- Drive health without admin rights shows the last stored check (the same one This PC shows) and "Needs admin to refresh" instead of "No drives could be read".
- Network › Overview: each unusual moment is one compact row (delay before → during → after, router chip); the readings are behind **Show values**; **Show N more** after five.
- Processes: the page scrolls as one (no list and inspector scroll boxes); the file count says "94 programs, 91 files".
- Sensors: reading source names moved to hover text, **Alerts** draft bar sits in the page instead of covering rows.
- Read-only bars (battery under each device gauge, GPU at most, Death counter Shortest/Longest, Network ping and speed, Game servers, fan Stop case fans, Cooler display color bar) mark "now" with a thin tick, never a round slider knob.
- One "Needs admin" look everywhere: a chip, one line and one **Restart as admin** button (Fans, Lighting, Cooler display, Sensors, This PC, Drive health, Home, Keep awake).
- Charts: the average is a key in the legend row under the chart (CPU/GPU live chart, Sensors, Death counter tries, Controller battery), no longer a label on the data line.
- Tables keep whole words (no "Microphone" split over two lines); Settings choices show the selected one filled; at 760 px the header's close button is no longer clipped.
- Voice: a MicDrop that holds the cable shows one chip, **MicDrop is using the cable**, with a "?" and a **Quit MicDrop** button, on Voice effects, Mic chain and Soundboard (no red sentence, not repeated).
- Audio and Voice pages: the headers of Outputs & rules, Microphones and Voice are cards; the switch for Auto switching sits beside On/Off; device names no longer break inside "VB-CABLE".
- Voice effects: the microphone strip shows the microphone you picked even while Voice is off; Pitch is one draggable bar; A/B and menu buttons line up on every stage.
- Soundboard: one pad size, two-line names, "Show N more" after 24 sounds. Phone Voice card: On/Mute in its head, effects two across.
- Soundboard times: one duration format (4:19, 1:28:03), and the thin bar under a sound shows its length against the longest sound.
- Mixer: every app row has the same output cell, the live level is a thin line under the slider, and the Output equalizer is one curve with ten handles.
- PC to PC: the **Waiting for you** card shows on Send only (other tabs show a "N waiting for you" chip); one secondary button look on PC to PC, Phone and Project sync; both PC cards share one layout and long PC names get an ellipsis; failed transfers show a **Stopped** chip with the reason behind "?"; Activity lines have a time column; the Apps tab keeps its Send bar in view.
- Phone: Screen settings put each control on its label's row (Screen access is now **Off / View / Control**); the Speaker & mic steps moved behind "?"; **VB-CABLE off** is a chip; the "Update the phone app" banner shows on Connect only (a ! on its tab elsewhere).
- Project sync: the clock-difference warning is a **Clocks N min apart** chip with "?" and **Open time settings**; Protection says "Versions not read" once; the tab row appears once sync is on; zero-count session filters are hidden.
- Settings: Games, CPU and GPU, Desktop and Connections page links show a word beside their icon; heroes no longer repeat rows below them (hot corner, Not games, +1 death, update state, Clipboard history); About fold bars have inner padding; the Connections card is **Sending**; **Free up memory** says **Needs admin** beside it.
- Home, Clock: **Week | Month** is a small segmented toggle in the tile head (remembered); Performance overlay, Items: **Order | Select** replaces the lone Select button.
- Home, PC readings: the four readings stay in one row; a missing CPU reading is a dash with one **Admin** chip under the rows, and **Network** is left out when the Network widget is on the board. The CPU and GPU profile cards keep their full labels and show the rest as chips.
- Ready to play (Game profiles and Home) is one component: only checks that need a look are chips, every fine one is a single **N OK** chip that lists them when pressed; the **?** and refresh button stay on the title line.
- Game profiles: the filter chips are one scrolling row under the search; the "Same as default" dropdown text is **Default (value)**; every dropdown ends at the same edge; **GPU at most** is a filled bar without a knob; **On start** has its **?** next to its name; Other game folders has one **Try / Apply** group and a bin icon; the four profile tabs scroll in one row in a narrow window.
- Apps to close: both action buttons are the same width with their own **?**; the settings tiles are titled with a chip for the value; the last run is two chips; in a narrow window the app details open under the selected row.
- Performance overlay: Layout, Look and Warnings show a compact preview strip; RivaTuner and vendor-app warnings are chips (**G HUB: lighting**) with **Close G HUB** (asks first) and a **?**; corner pads hide where long readings cover them; **Corner** and its four choices fill the row; the number and its unit are one field; color and switch tiles fill the row; theme thumbnails keep their text readable; the "now" marker on warning limits is a tick, not a second knob; the reading inspector follows the selected reading.
- Game bar: a widget is on the bar or in **Not on your bar** (the x on a row moves it there, pressing a tile adds it back); **Hold to open** puts its choices under the label with short names; Layout & look and Opening show a compact preview; section titles use the normal title color.
- Maintenance, Startup optimizer and Startup apps: the hero and the side panels are cards again; warnings are short chips with the full text behind **?** (the same message is shown once); empty "Not recorded" tiles are gone; **Startup apps** shows one **Windows hasn't measured yet** chip instead of repeating it, and **New at startup** has its own switch for the watch.
- Maintenance, Apps › Store: **Updates** and **Get Store apps** are cards; **Open Store** and **Update all in Store** sit in one **Microsoft Store** card; the check time reads "today 11:43 AM"; the download ring and zero tiles show only while something runs.
- Maintenance, Windows tweaks: the values table keeps "key removed" inside its column and shows "not set" for every empty value; the details panel no longer repeats the description above the gain / give-up lines; a mixed row has a switch and **⋯** with **All Off** / **All On**; several long effect lines are short; the restart banner is a chip; Changed by Deck hides zero tiles and calls undated changes **Earlier**.
- Maintenance, Clean up and Disk space: one-tile groups share a row; no repeated size chip or Include "Kept" wording; drive gauges say "used"; duplicate finder results are chips.
- Disk space and Timers no longer show the word "null" when a part has nothing to show.
- Readability: red words (danger buttons such as **Uninstall app**, **End app** and **Quit Deck**, failed chips, Security tags) are a lighter red that stays readable on every theme, including Nord and Graphite. The selected-app label in inspectors, file-type letters in Apps and category icons in Clean up are brighter, and the letter shown for a game without art sits on a darker square.
- No dashed outlines on buttons any more: **Set shortcut** fields, **Scan a folder…** on Disk space, the corner pads in the overlay preview and on the controller drawing, New rule and Save open windows in Arrange windows, and disabled buttons all use solid outlines.
- Windows tweaks in a narrow window: the category row is a dropdown beside the search box instead of a row that scrolled sideways with cut names.
- Project sync › Projects in a narrow window: a project folder and its **Move…** button share one line.
- Device batteries: the empty band between each battery bar and the options under it is gone.
- Rows that mix buttons and columns (Mixer channels, the death counter buttons) keep their own column spacing, so their columns line up.
- Settings › Connections and the PC to PC and Project sync pages: shorter card titles (**This PC**, **Receiving**, **From coding apps**, **How PCs connect**, **Client sessions**).
- Game bar page: the "The game" label in the preview is readable.
- Search: results for the old Screen tools › Shortcuts tab are gone; Windows tools are found from the search box.
- PC status, This PC: the page is cards now. **Your PC** shows the processor, graphics, memory and motherboard as tiles, each drive as a tile with a free-space bar (a **Low** chip when nearly full), and the other facts in two columns. **What Deck can control here** is now **What Deck controls**: one tile per part with its name and one chip side by side (a part reported twice shows once). **This week** sits beside it, **Control paths** beside **PCIe links** (reasons and notes behind **?**), and the latency test is **Latency test** with two result tiles and a solid mouse box.
- PC status, Processes: **Check program files** is a card. The four scans are tiles you press (icon, name, where it runs); **VirusTotal** without a key says **Needs a key** on its tile, the key button sits on the **Scan all N files** line, and **Check a file…** stands apart under **One file**. What each check sends is behind **?**. The selected-app panel is 380 px wide at 1280, headed **Selected app** with the program's name, with a **Safety** row and a **Program file** path that breaks only at folder separators. Program names line up with their numbers; **Sort by safety** toggles.
- PC status, Drive health: the evidence and the speed test are cards again. Values a drive does not report are one chip (for example **5 not reported**, names behind **?**) instead of a tile each; **Trend · 90 days**, **Endurance** (with **Save** beside the two fields) and the temperature chart are tiles; the speed test's sentences became chips (**Temporary file**, **A game in front stops it**, **Writes up to N GB**) with the details behind **?**; the warning strip reads one line with an **Every 10 min** chip.
- PC status, Sensors: the read-only range bars mark "now" with a tick instead of a round knob. Alerts: each part is a card, long descriptions are short lines or behind **?**, **Delete alert** is a bin button, and the test-message button says why it is off beside it. Graphs: the fan card shows a **5 of 7 connectors** chip; the history and frametime notes are shorter.
- Settings, Notifications: the drive warning rows no longer repeat their titles in a description.
- New voice effect **Autotune** (Audio › Voice effects › Effects): pulls your voice to the nearest note of a key and scale for the "robot singer" sound. Pick the key on a row of twelve notes (the scale's notes lit), the scale (Chromatic, Major, Minor, Pentatonic), **Strength** and **Retune speed** (0 ms = hard snap). It adds about 12 ms of delay.
- Phone remote: the **Voice** card is now a full soundboard and effect picker. Every effect is a button (starred ones marked, the one in use filled) and the sounds are a grid of pads, favorites first; a tap plays the sound on the PC and the pad flashes. **Stop all**, **Mute** and **Clean voice** stay.
- Audio › Voice effects › Mic chain: the chain is a strip of numbered stages in signal order with each one's state and main value; every stage is its own card (switch, sliders, ⋯ menu with **Put back as it came**, an **A/B** hold button). The Devices card is three pickers without repeated names; the Discord tips are three short rows with the details behind "?".
- Audio › Mixer › App volumes: every row lines up on one grid. Rows without an output picker (System sounds, some apps) no longer have a shorter, shifted slider.
- Audio pages say less: explanations moved behind "?" (Live level, exclusive mode for the equalizer, Mic check, starred effects, automatic switching, System sounds, Put back changes, control hints in Voice effects); output rules show their profile and "back when it closes" as chips; the Voice status chips read "40 ms delay" and "CPU 3%". Renamed: **Check mic on calls**, **Remember app volumes**, **Auto switching**, **Refresh**, **Add rule**, **Put back all**, **Mic check**, **Hear it on speakers**, **CABLE as default mic**, **Devices on/off**.
- Soundboard: one search-and-filter bar (Favorites, Short, Long, Clear); with sound keys set, **Allow in games** opens their setting; **Stop all** shows only while sounds can play; long file-style names such as AUD-20230926-WA0000 break at the dashes, not mid-word; the side column is cards.
- Microphones: the list and the selected mic are cards; the Mic check result shows numbers first.

- Home, PC readings: each part has its own column (ring, name, three rows) so values no longer run into the next column; the ring end labels are gone, units share one style, and **Energy** shows three figures (or **No reading yet**). The fourth column is now called **VRAM**.
- Home, Performance profiles: the profile picker is the standard dropdown; the line under it is a read-only meter (**Max speed** / **Power limit** with the percentage), no knob. The "No game profile is active" line is gone; **Set by** *game* shows when a game profile set them.
- Home, Quick actions: **Keep awake** and **Light mode** are whole-tile switches; the other actions are plain buttons in two even rows. The Playing layout's **Overlay** and **Game bar** work the same way.
- Home: the game banner no longer repeats the CPU and GPU profile chips when the Performance profiles tile is on Home. **Ready to play?** keeps its text readable in narrow windows. Edit Home's hint is one line; the keyboard keys are behind its "?".
- Game profiles › Power: energy figures are tiles, the price row is shorter, and **Per day** shows the last five days in one aligned list (date, bar, hours, kWh) with **Show N more**.
- The search box at the top of Home is no longer cut short in narrow windows.
- Display: each monitor is one card with clear panels for Display mode, Picture, Monitor settings, Input & speakers and Night & tests. Refresh rates are equal buttons that stay readable when not chosen, labels and values are brighter, and the monitor's own settings sit in two columns with the value next to each slider.
- Windows tools (Task Manager, Windows Settings, Terminal, Environment variables, Sound devices, Network adapters, Power options, Installed apps, Downloads, Snipping Tool) moved from Screen tools › Shortcuts to the search box: click the empty box to see them, or type a name.
- Settings › Desktop: the double-click choice reads **Paste** or **Copy only**.
- Desktop pages read faster: shorter labels and notes, explanations behind "?" buttons, and every section in a card (Arrange windows, Taskbar, Music & volume pop-ups, Clipboard, Screen tools).

- Connections pages read at a glance: every block sits in a card, setup steps are numbered strips, notes became chips or a **?**, and long titles are short.
- PC to PC: **Share link** picks **This Wi-Fi** or **Internet** with equal buttons and a chip that says who can open the link. Apps and Copy my look show a one-line **Send to** row instead of the whole PC list, Apps has one search-and-filter bar, and Copy my look is three tiles.
- Project sync: Sessions has one search box with filter chips and counts; project folders line up as label and path.
- Phone: shorter labels (**Phone connection**, **Smooth / Sharp**, **No monitor**), home-screen install and RustDesk steps fold away, and the speaker and mic how-to is two step strips with troubleshooting behind **?**.
- Clean up: while sizes are measured the ring counts them ("3/9 measured") and sizes still coming in pulse instead of repeating "Measuring..."; you can tick categories meanwhile, and Review clean up says why it waits. "Caches and old reports" is now **Caches & reports**.
- Disk space: a cleaner map. Only the top folders carry a name bar, tiny files are lumped into one Small files block, labels never cut a word, and a color key under the map names the file types.
- Apps: the selected app shows its size, version, date and folder as plain rows, problems as chips, and a grayed Uninstall says why right beside it. One filter bar with chips replaces the search plus segment row.
- Startup optimizer: the start timeline's notes are short chips (date, firmware, Windows + sign-in) with the details behind "?"; the button reads Analyze again.
- Startup apps, Built-in apps and Store apps: shorter titles and notes; the startup impact bar has a key.
- Controller › Test shows your controller with the overlay's own drawing (same theme and shape), lighting buttons, filling triggers and moving the sticks as you press them. Device cards, the Keys tab and Controller › Battery show each controller's real drawing too (Xbox, DualSense or DualShock) instead of a thin outline.
- Each device's options (tray icon, warning while playing, warning level, rename, forget) are now on its card in Devices › Device batteries. Settings › Device batteries keeps the tray look, icons for new devices and the device report.
- Devices and Controller pages say less and show more: shorter labels, state as chips, help behind "?", sections on cards, and the controller hero's switch sits beside its title. Tray icon styles are named Ring, Two icons, Number and Badge.
- Game profiles: the game's picture shows in full behind its name; status and tags are clean pills (**+ Tag** to add one). "Ready to play" is one row of chips, and **On start** shows what a profile changes as chips. Less text everywhere on the page.
- Apps to close: **Close N apps now** asks first and lists the apps; when nothing is ticked it says why right under the button.
- Performance overlay › Items: one list of every reading with one switch each (on = on the overlay); readings that are off fold under their part. The selected reading's panel carries its name and splits its own settings from the ones its part shares.
- Overlay presets cut to six clear goals (FPS only, Smoothness, Essentials, One line, Every core, Full detail), each pictured by the overlay itself with your readings. Color looks and arrangements use the same real pictures.
- Overlay Look: colors spread across the card as tiles; switches sit next to their words; reading names line up on the left. Overlay and Game bar settings sit in cards, with shorter labels.

- Death counter: one bar on top shows the game's picture, the game, who picked it, how it counts (**Screen + boss bars**, **Save file**...) and the on/off switch. The Now tab shows the game's art behind the count; **This session** and **All-time records** are separate cards. Every part of the four tabs sits in a card, and notes moved behind **?**.
- Settings › Death counter: the corner picker shows all six corners again.
- Session reports: less to read. Notes under the timeline, the stutter cards' advice and the explanations under the session tools are chips or sit behind **?**. Long names wrap instead of being cut.
- Network: Unusual moments list what happened at the same time as chips. Data per app and Game servers are drawn as cards; chart legends, test notes and the trace caveat moved behind **?**; Lag while busy keeps its test details in a fold.
- Fans › Calibrate & extras: a **Measure all fans** button measures every fan that reports a speed, one after another, with progress and **Stop measuring**. Fans not measured yet have shorter cards, in their own row.
- Lighting: the zone switches sit in a row above the picture of the PC instead of on top of it, and every section is its own card. **LEDs per connection** has its own small card.
- CPU and GPU: built-in modes are one list; each row shows what the mode changes (for example **No turbo** and **15 W**) instead of the same clock cap on every card. Import buttons are in a menu beside **New profile**; **Restore factory GPU settings** is the **Factory GPU** button.
- Hardware pages read faster: one-line warnings with a **?** for the details, chips instead of sentences, cards around every section, live readings marked with a tick instead of a slider knob, and chart titles that name the reading (**GPU clock**).
- Dropdowns look the same everywhere: a calm closed state (the ring only when you tab to it), a menu with a gap, shadow and a check on the chosen item, and group headings that fold.
- Game profiles: one search box and one row of filter chips that combine, with a Clear button. The selected game has a side bar instead of an outline. Segmented controls have equal-width segments.
- The controller overlay page's (i) button now opens its note. The sidebar picks up a little of the page's color.
- Windows tweaks opens at once: the page draws from the last known state and shows **Checking...** while it reads the PC again in the background. The network-adapter lookup that blocked every minute (a PowerShell call, about a second) now asks Windows directly.
- Windows tweaks rows read as the thing and its state (**Copilot button: Hidden**, **Activity history: On**) with the switch worded by its result. Reviews show each change as **Now → New** and the button says what happens (**Apply 5 changes**, **Undo any time**).
- Windows tweaks: the selected-tweak panel is wider (380 px), value names stay on one line, **Draft changes** is a toggle button, and the "changed settings back" notice shows once.
- The selected tweak shows its registry values directly in one compact table (key, value, now, each state, Windows default); the folded **Details** and **Registry values** are gone.

- Every chart now has a title with what it measures, the unit and what it is about (for example **Deaths per week**, **Time survived per try**, **Samsung SSD temperature (°C)**), values you can read, and short dates on the axis.
- Death counter: the session and weekly bar charts show their numbers; empty slots stay empty and a single busy slot becomes a plain sentence. The day grid keeps equal gaps, with the selected day outlined inside its cell.
- Game bar timeline pins no longer overlap on busy sessions: close moments merge into one numbered pin.
- Drive temperature history draws dashed bridges and dots across times with no readings. Average lines on graphs put their label on a solid pill away from the data. Cramped moments on the Game bar timeline join into one numbered pin. Chart colors are checked for being clearly different.
- Keep awake is rebuilt: one status card with an **On / Off** chip, the big state line and, when off, the quick starts right in it (**30 min**, **1 hour**, **2 hours**, **4 hours**, **until off**); when on, the time left, how it ends (**Until 23:30**) and **Stop**. Below, three equal cards: **For a duration**, **Until downloads finish**, **While an app runs** (its start button says **Choose an app first** beside it until you pick one).
- After the PC wakes shows the result as a chip in its heading (**All fine** / **1 failing**) next to **Check now**; only failing parts show their reason. The stopwatch's **Lap** says **Start it first** while stopped.
- Shut down when…: **Start plan** and **Discard changes** sit in the **Build a plan** card next to a chip with the warning you will get; option rows lost the notes that repeated their names; Quick picks keep their details in a tooltip.
- Settings: each part's summary band is a card with headed sections (**Window mode**, **Hot corner**, **Theme**, **Highlight color**, **Memory**...). Row notes that repeated the row name are gone (General, Appearance, Features, Data & recovery). Notifications shows each warning as one line with an **On / Off** chip. The end-of-part line is a chip: **All at defaults** or **N changed from default**. The shortcut button's text is centered, hot-corner and search chips are no longer dashed, **Reset order** says **Already the default** when there is nothing to reset, and Backups' three buttons share one row.
- Renamed: **Quicklinks, custom commands and chained actions** is now **Saved actions**; Notifications' **Tell me about new startup items** and **Tell me when an app first uses the network** are **New startup items** and **App first uses the network**.
- No more floating text on Power & time and Settings: every block now sits in a card. Windows sleep shows its two values as tiles with a note row and an Open settings button.

- Less reading: Power & time, Settings and About lose their helper paragraphs and long row descriptions. Notes moved behind a small ? button next to the heading (Windows sleep, What woke this PC, After the PC wakes, Time rules, Break reminders). Release notes on About show the bold line of each item, with More for the rest.
- Fixed: the overlay preview's top-right and bottom-right corners can be clicked again.
- The microphone check shows it is starting, counts down its five seconds, and shows the result, or why it could not run (for example another app holds the microphone).
- When a session has no verdict, one line says how much of it Deck read frames for and why the rest is missing. Frames a slow check still received now count.
- Fixed: Session reports, Sensors and several pages jumped when they redrew.
- Boss names only the screen read (not confirmed, not on the game's own boss list) are hidden from "Again" and "Fought" instead of shown as bosses.
- Every profile that is not active has a **Use** button.
- Clean up no longer says "Not measured" while measuring, and counts the same categories everywhere.

- Fixed: pressing Open it now on the Game bar several times could freeze and close Deck. Buttons now show they are busy until their action finishes.

- The search box and Activity button in the top bar keep their full text on pages with many tabs; the bar moves to its own row instead of shrinking, and long tab rows wrap instead of hiding tabs.
- Settings > Connections lists **Actions from outside Deck**: every action with **Copy command** and **Copy link**, and an **Allow deck:// links** switch (off by default; Deck checks with Windows that it took effect).
- Settings marks a setting that differs from the default with **Changed from default** and a **Back to default** button, and says **Nothing to put back** when none differ.
- Disk space lists **Saved scans** (drive or folder, when, folders compared) with **Scan again**.
- Power & time shows a **Plan timeline** and **Timer timeline** (waiting, warning, action, and why it is on hold), and **After the PC wakes** with the check Deck runs after sleep and a **Check now** button.
- Unusual network moments say what the name lookup, a second internet address and Wi-Fi did at the same time, which game was running, and what may have caused it (always marked **possible**). A failing name server (DNS) is named in plain words.
- The connection graph shows each period as a band from the lowest to the highest delay, with the middle marked and stripes for pings that got no reply.
- Activity has **Other recent changes**: changes Deck made from the tray, the phone or before the window reloaded.
- Fixed: **Open it now** on Gaming > Game bar could do nothing on the first press and freeze Deck when pressed again. Presses while the bar is opening are ignored; the button shows it is busy and says if the bar opened on another screen or may be hidden by a game in exclusive fullscreen. Buttons that start a preview or action (flyout previews, Move / resize, demo input) now also stay disabled until they finish.
- Search finds the new Taskbar page and the new controls on every redesigned page.

### Taskbar page
- New **Desktop › Taskbar** page: Windhawk's version and mods with on/off switches (only shell mods, checked afterwards), a check that Windhawk stays out of your games, and a banner with **Put back** if the shell kept crashing.
- Its **Clock Contrast** tab runs the clock-color helper from Deck: status, a Run switch, a live sample with the colors and contrast it picked, and settings you can try, then **Save**, **Discard** or **Reset to defaults**. It says plainly that it checks less often behind full-screen games but never stops.
### Gaming
- "Ready to play?" card on Gaming and as a Home tile: each check says Ok, Look at this or Unknown, with its reason and an Open link. Check again is off while a game is in front.
- Game profiles: "Games in other folders" (Add a folder, a name pattern, Try, Apply, Remove) lists the games found by each rule; a found game says which rule found it, and is listed once.
- Game profiles: games with an anti-cheat show why frame data and priority changes are off, under "Put the game first" and Target FPS.
- Performance overlay: RivaTuner's state (text slot, frame feed) and one warning for each running vendor app that can fight Deck's settings.
- Session reports: name a session, pin it as a baseline and compare with it, mark it as a benchmark run with a scene note, run Before and after a change steps, compare two sessions, export CSV or JSON, and see the frame-time distribution as a chart or table.
### Audio and Devices
- Mixer › Outputs & rules: the App outputs grid now fits long app and output names (names shorten with the full name on hover, output headings wrap to two lines) and the page stacks into one column on narrow windows.
- Mixer › Outputs & rules: a rule that is working says "In force now", "Putting the output back" while Deck returns your outputs, or "Could not put back" with what to do.
- Devices: devices not seen for a day say "Last seen N days ago".
- Settings › Device batteries: a "Say when a device is charged" switch (on by default) turns the charged notice off.
- Mixer: an Output equalizer card with ten band sliders, a Spatial sound settings button, a "While (game) is the game in front" rule label, "More outputs" when there are many outputs and "Show quiet apps" when there are many apps.
- Voice: sounds show their key, a "Sound keys work in games" switch (in Settings › Audio), "Hold to hear without this stage" on each mic stage, and the delay and CPU chips say whether they are estimated or measured.
- Devices: battery cards show "About N h left" with a small history line; Controller shows Device, Input and Overlay chips; controller themes are named Classic and White.
### Maintenance screens
- Power & time › Time rules: the time fields show the full time (for example 11:00 PM).
- Settings › About: **What Deck exposes** lists every port, firewall rule, scheduled task and service Deck has opened, with a word and icon for each.
- Power & time › Timers & breaks: **Time rules** switch fans, lighting or volume at a set time, with a log and Undo.
- Startup apps: **New at startup** lists new startup items with Keep, Disable and Undo; Settings › Notifications has the switch.
- Network: saved lag results can be labeled, compared and deleted; Settings › Notifications can tell you when an app first uses the network.
- Apps › App updates: Skip this version, Stop skipping and Unpin sit under each app. Deck health on Crashes is a short list of rows.
### Connections
- Fixes: the "Fix:" label in the check lists no longer breaks, the sync preview stops saying it is working once the result shows, and the home folder reads "~ (home folder)" in Project sync reviews.
- PC to PC: each transfer shows a word (Queued, Sending, Verified, Interrupted, Failed, Declined...) and failed or declined sends have Retry. New Send clipboard, Refresh and "Why isn't my PC listed?" (a read-only check list with a fix for each problem). Trust this PC in one click for PCs found over Tailscale, a size cap for trusted PCs, and Pair on Deck PCs in the network list.
- Settings > Connections: "Work with LocalSend" (off by default) says when its port is taken by another program.
- Project sync: see what the last sync changed, preview the next one, resolve conflicts with Keep mine / Keep theirs, Verify now per project, a leave-out list per project, and a warning when another PC's clock is off.
- Phone: "Why can't my phone reach this PC?", a live Screen strip (round trip, frames, data), a "Phone app too old" notice, a heads-up about the browser's "connection is not private" page beside the QR code, Start from a layout, and a Run on PC button type.

### Hardware pages
- CPU and GPU: a Back to stock button lists every part and says whether it really came back; Export profile… and Import profile… share a profile as text (an imported profile is checked against this PC and added switched off); CPU profiles can be tried for 60 seconds with Apply temporarily; Power & limits and Readings show what was asked next to what was measured.
- Fans: Try for 60 s runs only the pending fan changes and undoes itself unless you keep them; a Trigger rule speed mode; a fan that lost its temperature source says so and lets you pick another; Asked and measured rows.
- Sensors: each reading names its source, says when it stopped updating and tags fan outputs Controllable; a CPU limit line shows what holds the clock down.
- This PC: PCIe link of the graphics card and NVMe drives, and a Control paths table. The GPU Readings tab shows the PCIe link too.
- Drive health: drives read with your own smartctl say so, and "Not available" tells how to get a reading.
- CPU, Fans, Lighting and Cooler display name any running vendor program (iCUE, Armoury Crate and others) that can reset Deck's settings. Mouse lighting can save its brightness without touching the mouse.
### Layout fixes
- Network: the Before / During / After lines of an unusual moment wrap instead of running under the next column, and stack when the pane is narrow.
- Drop-downs show a long name on one line with an ellipsis (full name as a tooltip); Home's Sound output no longer overflows its tile.
- Stutter timeline: the numbered moment pins no longer cover the legend; the game search box fits its frame.
- Home: a profile card's "CPU profile" / "GPU profile" label no longer runs into its shortcut keys.
- Maintenance: the big figure at the top of each page no longer touches its label.
- Clipboard: file entries show the full path as a tooltip.
- Search: typing a label that many controls share, such as "Size", lists the exact matches first.
- Session reports: the stutter timeline no longer fails to draw when a session has moments.
- Sensors: the Graphs tab keeps its Graphs / Table switch.
### Safety and reports
- Internal: a Project sync test that failed now and then is fixed (no change to how sync works).
- A copy of your settings is saved before every update (Settings > Backup > Copies from before updates; the last 5 are kept). If the copy fails, the update still goes ahead and says so.
- Crashes: stop codes now show their name (for example MEMORY_MANAGEMENT), the four parameters from the dump and a one-line meaning; a power loss or hard reset with no dump says so.
- Power > Keep awake shows what woke the PC last, wake timers and devices allowed to wake it; a read Windows refuses says "could not be read".
- Session reports name each background app Deck slowed and what it was put back to (also after a crash and restart).
- Sensors: readings older than 5 seconds show their age and source, fan outputs are tagged Controllable, and Fans says "BIOS control since" when an anti-cheat holds them. On Intel CPUs a line says what is holding the CPU clock back (power limit, heat, current).
### Sensors
- The recording to `monitor.csv` (still off by default) now marks when it starts, when a game starts and stops, and when a profile or a fan mode changes, and adds the lowest, average and highest of every reading at the end of each game session. Marker rows start with `#`; they carry no paths or window titles.
- Sensors > Graphs has a **Table** view with the same samples as the graphs, newest first. A missed reading says "No reading".

### Hardware (the pages follow with the redesign)
- Behind the scenes: the graphics card's and NVMe drives' PCIe link (current and maximum, with a note when idle lowers it), export and import of one CPU or GPU profile as a file (import checks every value against your card or CPU and never applies it), and a fan Trigger rule (fan to X % above a temperature, back to Y % below a lower one).
### Sound and devices
- **Output rules put things back.** A rule for a program (when it starts, or while it is the game in front) switches the output and brings the earlier outputs, app outputs and volumes back when the program closes, also after a restart or crash. Nothing switches while a game is in front unless the rule is for that game; an output that is not connected changes nothing and Deck says so. Game profiles can also move named apps to their own outputs while the game runs.
- **Sound output in the tray menu** (Hardware submenu, Sound output): pick the default playback device without opening Deck; Deck reads it back and reports a failure. No keyboard shortcut.
- **Battery history for every device**, not only controllers: the estimated time left for headsets, mice and keyboards, and a "charged" notice once per charge (never while a game is in front). Each device's history stays under 50 KB.
- **Windows spatial sound**: a button on Mixer › Playback that opens Windows' own Sound settings.
- **Sound keys**: give a soundboard sound its own key (default none). Keys work while the voice is on and are released while a game is in front, unless you turn on "Sound keys work in games".
- **Output equalizer** (needs the free Equalizer APO, which you install yourself; off by default): Flat, Bass, Footsteps and Voice presets, A/B bypass, and a button that puts your earlier file back. Paste an AutoEq profile's ParametricEq.txt to use it as the curve. Deck writes only its own `deck-eq.txt`; you add one `Include` line to Equalizer APO's config.
### Desktop
- Search: type `w ` to find an open window and bring it forward, `c ` for the clipboard only, `d ` for the display controls. Your own search keywords win over these letters. Nothing is listed while a game is in front.
- Search says which source could not be searched ("Files not searched: the file index is turned off.") while the others still answer, marks files from an old index as Stale, and shows a preview of the selected result.
- Arrange windows: app rules can keep a window in its zone, match by window title or class, and there is a list of windows that are never moved. Windows that run as administrator are listed once instead of being retried.
- Arrange windows: workspaces list what happened to every window after opening (placed, started, failed, not moved) and can start apps in a set order after a delay.
- Arrange windows: "Fill zones with open windows" (with Undo), a layout or workspace per set of monitors that is put back a few seconds after you plug or unplug a monitor, and snap zones to and from a file.
- Arrange windows, Snap zones: buttons for Fill the zones with open windows (with Undo), Export zones and Import zones; a line for windows that could not be moved; the list "Windows that are never moved" with a form to add to it; a layout or workspace for each set of monitors; app rules can be kept in a zone and matched by title or class. Windows hidden to the tray are listed with a Show button.
- Screen tools: "Close all" for pins and mirrors; color Copy buttons use Deck's own formatting.
- Clipboard: the on-copy rules and paste-as-plain-text lists are easier to read; a bad `re:` pattern shows its message under the search box.
- Hot corners: each of the four corners can open Deck, show the desktop, lock, turn the screens off or sleep, with its own delay. Only opening Deck can work over a fullscreen game, and only if you allow it.
### Connections (backend; the redesigned pages add the buttons)
- PC to PC: a trusted PC now only skips the question for files under a size limit (default 1 GB) that are not programs, installers or scripts; those always ask. Rows report Queued / Sending / Verified / Interrupted / Failed honestly, any unfinished send can be retried, the clipboard text can be sent as a message (shown with a Copy button, never pasted), Refresh announces the PC again, and a checklist explains a PC that is not listed.
- Project sync: a list of conflicts with both versions, per-file results of the last sync, Preview changes and Verify now (nothing is touched), a hidden folder marker so a renamed or missing folder deletes nothing, a per-project ignore list, and a clock-difference warning.
- Phone: a checklist for "why can't my phone reach this PC" (port, Windows-reserved ports, network type, Firewall rule, addresses) and the stream numbers for a status strip.
### Maintenance and diagnostics
- Lag while busy keeps its results: each run is saved with its grade and date, you can label it (for example "new router") and compare two runs side by side.
- Apps: winget-pinned apps are shown and never updated by Update all, and you can skip one version of an app; a newer version brings it back. Pin and unpin go through winget.
- App updates wait while a game is in front ("Waiting for the game to close") and carry on after; the result list of the last run is kept.
- Power: a plan can show why it is paused with the number ("Download at 340 KB/s, limit 100"). A timer that ran out while the PC slept says so. A plan no longer counts the time the PC slept as quiet time, and a warning that ran out in sleep warns again instead of acting.
- After waking from sleep Deck checks audio devices and the graphics card settings and retries what did not come back, without waiting for a game to close first.
- Connection quality also times a name lookup and pings a second internet address (only while recording is on), so a router, DNS and internet problem can be told apart. Wi-Fi signal, link speed and disconnect events are marked on Unusual moments, which also name the game session and possible causes. The graph keeps fastest, middle and slowest reply per 10 minutes.
### Drives
- Drive health can read a drive Windows gives no health data for (many USB enclosures, odd NVMe) through smartctl, if you installed smartmontools yourself. Those readings say "Health read with smartctl". Deck never installs or bundles it and never writes to a drive.

### PC status
- This PC has a Latency and refresh test: the refresh rate your Deck window really redraws at and your mouse's report rate, measured only inside Deck's window. It runs when you press Start and stops when you leave the page.

### Clean up
- New Clean up rows: Microsoft Teams, Epic Games Launcher and Battle.net caches, and (with admin rights) the Delivery Optimization cache, the Windows Update download cache and Windows' PC-wide error reports. None is ticked at first, each shows its size before anything is deleted, and an open app is skipped until you close it.
### Connections
- **Actions from outside Deck**: `deck.exe --do <action>` and `deck://do/<action>` links run one action from a fixed list (open a page, switch a CPU or GPU profile, mute the mic or sound, change the output, game bar, Keep awake, lock, sleep, screen off). Nothing outside the list runs; links are off until you turn them on and never lock or sleep the PC; opening a page waits while a game is in front.
- **Run on PC buttons** for the phone's layouts use the same list. Sleep and lock follow the phone remote's power setting.
- **Starter layouts** for the phone: Presenter, Media and Browser copy into layouts you can edit.
- **Work with LocalSend** (off by default): phones with the stock LocalSend app, iPhones included, can send files to Deck. Each offer asks first, and the port is open only while the switch is on.
### Phone and checks
- The phone remote now says which protocol it speaks and the oldest phone app it still serves; an app that announces an older one is told in plain words to update instead of failing oddly. The phone protocol is written down in `docs/PHONE_PROTOCOL.md`.
- A read-only "what Deck exposes" report lists the ports Deck listens on, its firewall rules, scheduled tasks and services, and flags anything unexpected.
### Maintenance, diagnostics and power
- Alerts can stay quiet during games: sensor and drive alerts wait while a game is in front and show once, together, after you leave it (Sensors > Quiet during games).
- A path trace is refused while a game is in front.
- Windows tweaks: "Put back since this date" and "Put back since the last Deck update" undo later changes newest first and list any that could not be put back.
- Time rules (no page yet): switch a fan preset, a lighting effect or the volume at a set time, once a day, also after sleep, never during a game, with Undo.
- Deck health on Session reports: unexpected closes, stopped background tasks, the last errors and the update state.
- Startup watch (off by default, no page yet): one quiet notice when something adds itself to startup. It never changes anything by itself.
- First-seen network app notice (off by default, no page yet): one notice with the program name and size when a program with no recent traffic starts sending or receiving.
- Disk "What grew" is still there after a restart.

### Behind the scenes
- Search index rebuilt for the combined features. Lint clean after the merges.
- A wording glossary (`docs/GLOSSARY.md`) and a check that warns on over-long labels and on words that conflict with it. The guide FAQ now explains why Deck does not remap keys or mouse buttons.
- Saving a file retries briefly when Windows reports "access denied" for a moment while the old copy is released.
- A no-focus-steal test checks that Deck's overlay windows never take focus, with a gated script for a real display-mode run.
### New
- This PC lists every control path with what Deck reads, what it can change, and why anything is missing (processor, each graphics adapter, laptop controls, motherboard chips). The support report carries the same lines.
- The controller page shows three separate answers: controller found, input arriving, overlay visible.
- Audio › Voice effects says "Not available on this mic" where the extra-gain slider cannot exist, labels the delay as estimated and shows the voice's measured processor use while it runs.
- Screen tools: pin an area (or a clipboard picture) to the screen as a small always-on-top window that never takes the keyboard, and mirror part of another window live.
- Arrange windows: Hide to tray for a window, with Show in the tray menu; games and full-screen windows can't be hidden, and nothing stays hidden after Deck quits or restarts.
- Clipboard: copies can be put in named groups (kept like pinned ones), `re:` and a pattern searches with a regular expression, and per app you can switch on three safe clean-ups on copy (remove link tracking, trim spaces, keep only plain text), all off by default. Snippets are now picked in the Clipboard page to copy them.
- Clipboard history, its images and your snippets are now encrypted on disk for your Windows account. An older history is converted at the first start. Backups leave clipboard history out unless you turn that on in the backup settings, and then only save it in a backup with a password.
- Display: each monitor has its own brightness range, so 50 % can look the same on different panels, and the page says up front whether DDC/CI is available, off in the monitor's menu, or not supported. The brightness schedule follows the range.
- Screen tools: the ruler reads true pixels on every monitor, also at the size apps draw at on a scaled screen; a picked color can copy as hex, RGB or HSL; Copy screen text lets you choose the language and keep or join the lines.

### Behind the scenes
- Tests prove that copied clipboard text never reaches the log, the problem summary or any file except the history itself.
- Developer tools: an accessibility gate (`tools\testing\ui-preview\a11y.mjs`, run by `tools\check.ps1 -Release`) with the written standard in `docs/ACCESSIBILITY.md`; it fails on unnamed controls, keyboard traps, low contrast and clipped text at 125 to 200 % text size.
- Developer tools: a docs check (`tools	esting\check-docs.mjs`, part of `tools\check.ps1`) fails when a sidebar page has no guide page, a tour points at a missing page, or a new label is not in the guide.
### Gaming
- **Death counter**: each fight shows how far to trust its count (known screen, taught screen, guess from words, by hand), with the reason on hover. Counts are unchanged; old fights say "Counted before Deck wrote down why".
- **Ready to play?** A read-only card on Game profiles lists sound output, microphone, refresh rate, power plan, Game Mode, free disk, pending restart, busy programs, driver age and VPN as Ok / Look at this / Unknown, each with a link to the page that fixes it. With a game in front it reads nothing and shows the last check.
- **Games in other folders**: add a folder and a name pattern (for example `*.exe`) and every sub-folder with a matching program is listed as a game "found by rule". Remove the folder and they go. Nothing is sent over the network.
- **Performance overlay**: says when another program holds all of RivaTuner's text slots, and when RivaTuner has sent no new frames for a while. It only reads; it changes nothing in RivaTuner.
- **Session reports**: name a session ("after fan change"), pin one as the game's baseline and compare any later session with it (1 % and 0.1 % lows, or "Not comparable" when the lengths or games differ), see the frame-time distribution as a chart or a table, and export a session summary as CSV or JSON (no folders or PC name inside).

- **Game library**: the list under Game profiles is in sections (Playing now, Own profile, All other), and you can save the filter you have set (list choice, tag, search) under a name and reopen it with one click. Up to 12 saved filters; they survive a restart.

### Behind the scenes
- Before-and-after steps (name a step, end it, and Deck compares the five minutes of play before and after, or says "Not comparable" when the length, game version, frame limit or screen mode differ), a benchmark label with a scene note and a two-session comparison with a warning when the lengths differ, and a read-only check for other vendor suites that also write fans, power limits or lights. All work on data Deck already keeps; no screen for them yet.
- Saving a file retries briefly when Windows reports "access denied" for a moment while the old copy is released.
- Death counter detector tests now run on committed synthetic banner pictures (three sizes, two languages, no game art).
- Code lint is clean again (no behavior change).
### Taskbar
- **Clock Contrast now lives inside Deck** (off until you turn it on): it picks the taskbar clock's colors from your screen and hands them to the Clock Contrast Windhawk mod, which paints them. No separate program or logon task is needed. If the standalone ClockContrast is already running, Deck leaves it alone and does not start a second one. The Taskbar page that controls it comes with the redesign. You can tune how readable the time and date are, how colorful, how much color counts, how fast it reacts, when a colorless screen turns it silver, and whether it slows down on battery; Try, Save, Discard and Reset are provided.

### Behind the scenes
- Code lint is clean again (no behavior change), including the new Clock Contrast code.
- Failure tests for the voice (no cable, other sample rates, exclusive mode refused, unplugged mics, damaged settings) and for the default-mic crash recovery. If Deck cannot save the record of your own default microphone, it no longer switches the default to the cable.
- A shared test kit (`faultkit.rs`) switches a fake PC off after every saved step of GPU, CPU, fan, display and sound changes, and checks that the next start puts everything back; `docs/plans/FAULT_MATRIX.md` lists what is and is not covered.
- Developer tools: `tools\check.ps1` also runs the wiring, search, Node unit-test and navigation-color checks; a real-app capture tool (`real-capture.mjs`) and layout audit (`audit.mjs`) replace scratch scripts; preview test pages no longer land in the source folder.

### Hardware
- **Back to stock**: tray > Hardware > Back to stock (when Deck runs as admin) hands the fans to the BIOS, puts the graphics card back to its defaults, returns the processor to its original Windows power plan with no Deck limits, and switches Deck's lighting triggers off. Each part reports its own result, and a part that did not go back says what is still applied.
- A graphics card or processor that holds less power than you asked for is now reported ("Asked 120 W, card allows 100 W"), not counted as applied. Fixed-speed fans are checked against what the fan chip reports.

### Fans
- A fan now remembers its temperature source by name. If a driver or Deck update re-orders or removes a motherboard sensor, the fan keeps reading the same sensor, or, when that sensor is gone, goes back to the BIOS and is flagged instead of quietly following a different temperature.

### Phone and safety
- Shell guard: when Windhawk has a mod on and Explorer crashes 3 times in 2 minutes (or once, naming a mod), Deck turns that mod off and tells you, with a button to turn it back on. Deck refuses to turn on a Windhawk mod that runs outside the Windows shell (no page for it yet).
- New installs start with the phone remote off until you turn it on (Phone page). Installs that already use it keep their setting.
- "Put the game first" and Target FPS are hidden, and not applied, for games with a known anti-cheat (Easy Anti-Cheat, BattlEye, Vanguard and popular titles).
- Copy my look no longer carries Windhawk's own Include/Exclude lists, so a friend's game exclusions are never overwritten.
### Windows tweaks and sound
- Switching the sound output and applying a Windows tweak now check the result before saying it worked: Deck reads the real setting back, and if Windows kept the old output or value you see what is still set instead of a success message. A tweak that needs a restart says it was sent but not confirmed yet.

### Devices
- Device batteries no longer flicker between a reading and "Not connected". A mouse or headset that falls asleep and stops answering keeps its last reading with its age, such as "89% · asleep · 4 min ago", in the tray, the battery pop-up, the taskbar widget and both Device batteries pages. It is shown as not seen only after 24 hours without an answer. Last readings are kept across restarts.
- Every battery surface now uses the same words for the same state: live, charging, low battery, asleep with its age, or not seen. A remembered reading never sets off a low-battery warning.
- Redesigned battery pop-up and taskbar widget: a ring gauge around each device's symbol in the state's color, a big percentage, one status line with a dot and a word, the most urgent device first, and asleep devices drawn dimmer with their age.
- Settings › Device batteries shows each device as a tidy card (ring, name, status, then its tray, warning and rename controls in one row), with the device list first. Names are changed with **Rename**, in place, instead of an always-open empty field.

### Games
- Why did it stutter? now notices alt-tabs and other windows taking focus. The session timeline shows each time the game left the foreground as a hatched band, with a summary line ("Left the game 4 times, 2 min total; Discord took focus twice"). A stutter, drop or pause during that time, or within 3 seconds of coming back, is explained as "You switched to <app>" or "<app> took focus". Time out of focus is still left out of the smooth/rough grade.
- Pages no longer show an explanation line under their tabs; links to other pages and to Settings are now small icons at the end of the tab row. On pages without their own tabs they sit right after the group tabs.
- Home (2026-11-20 depth pass): the default arrangement now matches the approved design in three even rows (game | Now playing; PC readings | Sound | Performance profiles; Quick actions | Clock | Network). The game band keeps its played / sessions / this week strip in the corner, with the death counter as a compact chip at the top and frame-rate facts on the store line. Now playing shows a gradient art square and a round play button; profile cards show their scale and summary. Saved layouts are unchanged.
- Home has a new Aurora layout with a game and music band, ticked PC gauges, energy figures, compact Sound and profile cards, action tiles, a week clock and a labeled network chart. Saved tile positions remain intact. Edit Home adds Arrange, List view, a tile gallery and Line up rows; tile controls pause while arranging. Missing readings stay unavailable (and never wrap or take headline size), card titles are never cut off, and pinned apps have visible option buttons.
- Game profiles > Games now matches the approved design more closely: a large game title with its color behind it, game and app counts on the tabs, "Copy settings from…" next to "Use default settings", and "Open full report" on the last-session card. Status and tags filters open from a button beside the search box.

- Pages no longer show an explanation line under their tabs; links to other pages and to Settings are now small icons at the end of the tab row. On pages without their own tabs they sit right after the group tabs.
- Rebuilt Game profiles > Games with a grouped library that becomes a picker on narrow windows, a compact artwork head, an editor before session figures, visible per-setting inheritance and reset actions, and a temperature scale. Unrecorded FPS stays explicit; all four editor sections and session details remain available.
- Sensors now has a device rail, a large live reading with its chart, range tiles and a range column, plus compact core lists. Narrow windows use a device picker. Graphs groups temperatures and fan readings more compactly; Alerts separates notification destinations and explains when a test message is unavailable. Every reading, statistics mode and existing control remains available.
- CPU and GPU now use Aurora workspaces: compare the applied profile with live readings, choose numeric built-in modes and manage saved profiles in a compact list. Readings gain low/average/high scales and labeled charts. Profile editors keep Save visible above long settings and curves, with live CPU readings and clear unsaved changes. Overclock profiles use an explicit Use button.
- Cooling pages get real new layouts (2026-11-20). Fans › Curves: the chosen curve is a large chart with fan chips above it (click a fan to open its curve), the speed it gives now, the fans on it, and its shape as figures; slow-down rules come with a small picture of what they do, quiet hours with a day strip, case-fan stop with a scale. Fans › Calibrate & extras: a summary of measured fans, then one card per fan with its measured range as a scale and a speed chart; combining curves shows both curves and the result. Lighting: a drawing of the PC with each lit zone as an on/off chip, an effect gallery where every tile runs its own small preview, and the chosen effect's color, brightness and speed beside it. Cooler display: the screen drawn large as on the cooler, with what it shows picked above and each reading switched on or off on the screen itself; color shown as a strip with the live reading, night dimming as a day strip, the heat flash on a scale. Nothing else changed: same settings, Apply and Discard, confirms and no-reading states.
- Pages no longer show an explanation line under their tabs; links to other pages and to Settings are now small icons at the end of the tab row. On pages without their own tabs they sit right after the group tabs.
- Fans, Lighting and Cooler display rebuilt in the Aurora look: fans are one card each with live speed, mode, temperature source and per-fan ramp limits; curve editor with a fan-assignment rail; combine, measure (with a confirm and progress) and preview cards; lighting and cooler display split into work area plus device rails. Apply and Discard behave as before.
- Diagnostics depth pass (2026-11-20): Session reports is now a list of sessions (game picture, time, verdict, average FPS, with search and a game filter) beside the chosen report, which opens on a hero band (verdict, average FPS, 1% and 0.1% lows, hitches, time lost, slowest frame, Compare and What changed), then the timeline, what the stutters share as cards, the moments, this game over time and the session's details. Crashes and Deck game mode history are entries in the same list. Network: Overview leads with download, upload and a one-word connection verdict over the last 24 hours, beside the quality chart, today's top apps and the PC's addresses; Tests are four cards with a big last result and a delay scale; Data per app has a totals band and an app list with an inspector (share, download and upload, today / 7 days / 30 days); Game servers puts the lowest delay big with a delay scale.
- Pages no longer show an explanation line under their tabs; links to other pages and to Settings are now small icons at the end of the tab row. On pages without their own tabs they sit right after the group tabs.
- PC status rebuilt in the Aurora look (Processes, Drive health, This PC, Diagnostics > Network): Processes is one program list with an inspector and a summary band, Drive health is a drive list beside one evidence panel with the speed test per drive, This PC leads with the parts, Network gets a labeled quality chart and a sortable per-app table.
- PC status rebuilt in the Aurora look (Processes, Drive health, This PC, Diagnostics > Network): Processes is one program list with an inspector and a summary band, Drive health is a drive list beside one evidence panel with the speed test per drive, This PC leads with the parts, Network gets a labeled quality chart and a sortable per-app table. Searching Deck no longer lists running program names as settings.
- Audio depth pass (2026-11-20): Microphones now opens on a band with the apps-and-games mic's level ring, its jobs and tiles (calls mic, mics on, last check, check before calls), then a microphone list beside the selected mic (level, extra gain, job cards, the five-second check drawn on a level scale). Outputs & rules opens on the automatic-switching band and routes apps on a grid (one row per app, one column per output). Voice effects, Mic chain and Soundboard share a band showing the voice's path (mic, effect, sounds, others) with a live level on each link; effects show what they let through (frequency band or pitch scale); Mic chain puts stages, the selected stage and devices in three columns; Soundboard keeps sound levels, Playing now and board totals beside the pads, and each pad shows its length.
- Audio pages rebuilt in the Aurora look: Mixer (device strip, master and app channels beside Now playing), Outputs & rules (app outputs beside automation, profiles and rules, put-back band), Microphones (role summary and per-mic workspaces), Voice effects (effect rail beside inspector, mic-chain signal rail), Soundboard (favorites and all-sounds banks, per-pad stop and progress).

- Settings parts now open with a summary band that shows their state as a picture (window modes and the hot corner, the theme gallery, what search covers, your game library, the death counter preview, active CPU and GPU profiles with memory, device battery rings, the warning list, clipboard fill, a storage ring chart with backups, linked PCs, the version and update state), with the settings below as cards in two columns. In General, click a window mode or a screen corner in the band to choose it.
- Settings has a new look: one surface per part, a clearer Features list, a Notifications overview whose rows open each warning's page, About and Data layouts, and danger actions at the end.
- Performance overlay, Game bar and Apps to close get new layouts. Overlay: a large game-screen preview at the top whose corners move the overlay, with the overlay switch, live FPS and tiles beside it; readings list beside an inspector for the selected reading (value, order, line, color, unit, warning); presets, layouts and color themes as galleries of small overlays; Warnings as range scales with a draggable limit and the reading now; Behavior opens with RivaTuner's state and your in-game keys. Game bar: a large bar preview over a game at the top, the bar's list beside the widget library, a gallery of bar styles, and a card per way to open it with the keys drawn. Apps to close: a memory ring with about how much the ticked apps hold, Close and Free memory beside it, and the app list beside the selected app's details (memory share, why it is suggested, Close it / Leave it open).
- Performance overlay, Game bar and Apps to close rebuilt in the Aurora look: state bands, preview beside the editors, range controls with numbers, widget library tiles, and a clearer app list with a memory bar.
- Death counter › Now and History go further (2026-11-20): Now leads with a big death count, the try number and +1 / Undo beside a fight panel with a chart of your tries, a shortest-to-longest scale and the fight's records, then this session and all-time records as tiles. History opens on a 12-week calendar of deaths per day with its totals; pick a day (on the calendar or in the days list) to see its sessions, deaths over time and timeline.
- Death counter pages have a new layout: a game bar above the tabs, a count and fight panel on Now, a boss list with details on Bosses, day cards on History, and a stats band with a games list on Games.
- Controller › On screen rebuilt around a game-screen preview: the overlay sits where it will appear, the six corners are targets on the screen itself, and the state, size, opacity, corner and monitor read as tiles beside it; themes are color swatches. Controller › Keys: the two modes are illustrated cards, the keyboard and mouse are drawn large (click a key, or the mouse, to show or hide it), and presets are chips, with a new Movement preset (WASD, Space, Shift, Ctrl).
- Devices pages redesigned: battery cards with gauges on Device batteries; Controller has a preview-led On screen page, a Show switch on Keys, known controllers on Battery and a live controller drawing on Test.
- Pages no longer show an explanation line under their tabs; links to other pages and to Settings are now small icons at the end of the tab row.
- Desktop pages go deeper (2026-11-20): Snap zones shows the chosen layout large on a screen beside the layout gallery, with app rules as a list and an inspector where you pick or move a rule by selecting its zone; Workspaces shows a gallery of to-scale workspace maps and an inspector with each saved window, Open and Edit; Music & volume pop-ups open with a large screen preview, what is on and where; Clipboard opens with a summary of what you copy and a week of copies; Screen tools has a tool rail and a color studio with hex, RGB, HSL and contrast on white and black.
- Pages no longer show an explanation line under their tabs; links to other pages and to Settings are now small icons at the end of the tab row. On pages without their own tabs they sit right after the group tabs.
- Pages no longer show an explanation line under their tabs; links to other pages and to Settings are now small icons at the end of the tab row.
- Desktop has a new Aurora layout: Arrange windows gets an "Arrange all" strip, a window inspector with a clickable snap map, a layout gallery and to-scale workspace maps; Display shows a monitor picker with Display mode and Picture side by side; Music & volume pop-ups sit beside a live layout preview; Clipboard is a searchable history beside an inspector; Screen tools have start buttons, a color inspector and a clearer Locked files picker.
- Maintenance pages rebuilt with new layouts (2026-11-20): Clean up shows a donut of what was found and a grid of category tiles with a details panel; Disk space keeps drive cards with usage rings on top, a large map beside a file-type donut, and the folder list under them; Startup apps and Installed apps are a list with a details panel and impact or size bars; Startup optimizer charts where the last start's time went, ranks findings as cards and charts recent starts; App updates, Built-in apps and Store apps get summary bands, cards and download progress rings; Windows tweaks categories are compact rows with a details panel, and Changed by Deck is a timeline by date with Put back on each change.
- Pages no longer show an explanation line under their tabs; links to other pages and to Settings are now small icons at the end of the tab row. On pages without their own tabs they sit right after the group tabs.
- Maintenance pages redesigned: a summary band on each page, clearer cards, size bars on Clean up, Disk tools split into a switcher (duplicates, what grew, empty folders, broken shortcuts, make room), and the Windows tweaks links to Apps got distinct icons.

- Power & time rebuilt in the Aurora look (2026-11-20): Keep awake opens with a status card beside Windows sleep settings, then durations and events, and Windows requests grouped by process with counts (first 6, Show all); Timers & breaks has a next-to-ring summary, presets, timer rows with progress and +5 min, stopwatch and break reminders in a side rail; Shut down when… is a sentence builder with grouped conditions, options split into condition and safety panels, and quick picks.
- Pages no longer show an explanation line under their tabs; links to other pages and to Settings are now small icons at the end of the tab row.

### Maintenance
- Session reports: the game filter is labeled "Filter by game".
- App-wide look moved to Aurora (refined): bundled Sora and Manrope, glass cards, a fixed sky tinted by each group's hue, sentence-case headings; page layouts are unchanged. Text contrast checked on all eight themes.
- Split page scripts into smaller files for continued interface work; page behavior and styling are unchanged.
- Split supplemental page code into smaller modules for the redesign, preserving existing behavior and appearance.
- Prepared backend support for temporary CPU settings, 60-second fan trials, Pair from LAN discovery and held mic-stage comparison; page controls follow in the redesign.

### Devices
- Device batteries defaults to one clean state ring for the weakest device, with a weakest-first tooltip. The recent two-icon default migrates once; per-device icons and all earlier styles remain selectable.
- Click a battery icon for a compact native pop-up with device rings, names, status/reading age and large percentages. Charging stays green at full; stale readings dim. The pop-up never takes focus and stays hidden during fullscreen apps.
- Optional **Taskbar widget** in Settings ? Device batteries shows symbols and percentages beside the tray, horizontally or vertically. It follows the taskbar and hides with auto-hide, fullscreen apps or no shown devices.
- Visual direction inspired by Joule (AGPL-3.0); no code or assets copied.

### Pages
- Pages no longer open with a big title and description: the page tabs and content start right under the top row, which now holds search and the window buttons.

### Fixes
- Game profiles no longer list the same game twice (Fortnite, Counter-Strike 2 and others); the entries merge and keep your settings.
- Data per app no longer counts traffic that stays on this PC (Deck's own phone link), and one game or launcher shows as one row.
- Session reports say "Not counted for this game" instead of 0 deaths when the death counter did not watch the game; the game filter shows game names.
- Hitches per hour and the smoothness comparison wait for a minute of data.
- Fans show "No reading" instead of 0 and Curves say "All 8 fans" when all use one; fans without an RPM reading cannot be calibrated.
- Home: tiles do nothing while arranging, the clock has no leading zero, and sending all PC sound to CABLE Input asks first.
- Clipboard tabs show their own counts, and a failed load no longer says nothing was copied.
- Arrange windows lists one row per window; Keep awake groups identical requests; the Clean badge appears only after a measurement.
- Controller battery lists known pads and Test says when no controller is connected.
- PC to PC stops waiting after three minutes without an answer, explains connection and version failures, and records each send step. Compatible older protocols still work.
- Command-line sends follow their own transfer ID, wait for its final result and leave the running app's transfer history alone. Keep the command open until it finishes.
- Turning on a present virtual display with a driver error restarts that device with a disable/enable cycle, using one administrator prompt when needed.
- CPU profiles keep name and shortcut fields first. Desktop and Start menu switches line up in both profile editors.
- Turbo boost shows its mode and keeps it when switched off and back on. Change the mode in Advanced.
- Long audio device names, voice errors and app volume rows fit narrow windows.
- Voice shows why sounds cannot play when it is on but audio has stopped.
- Bosses shows the selected game and lets you choose another game.
- Drive hours say Not counted when the drive reports zero despite other signs of use.
- Processes says Unavailable until CPU and memory readings arrive.
- Stopped pings show the last run. Live readings show their age in seconds when under a minute.

### Connections
- Open **Devices on this network** on PC to PC to find nearby phones, TVs, printers and Deck PCs. Names stay on this PC. Close the card to stop looking.
- Discovery pauses during games and explains when Windows marks a network Public. Saved Wake-on-LAN PCs have a **Wake** button.

- Choose which Project sync items keep older copies in Settings > Connections. Each starts off, with a size limit, max age and Open versions for recovery on this PC.
- Project sync holds large deletions and batches where every file looks changed. Activity says how many are waiting; open Project sync to Apply anyway or Cancel. Nothing in a held batch is applied.


- PC to PC has a Wake readiness card for this PC: Fast Startup, armed devices, last wake source, wake timers and sender addresses. It reads when the page opens and changes nothing.
- Fast Startup says it may prevent wake. Failed reads say they could not be read. Phone pairing links can include wake addresses for future phone support.
### Power & time
- Groundwork for the Power page redesign: a shutdown plan can be pushed back, and timers can be extended, paused and resumed (the buttons come with the redesign).
- PCs with a battery show design and full charge capacity, cycle count, a monthly trend and available sleep drain sessions in Keep awake.
- Reports refresh at most once a day when you open the page, outside games. Missing readings stay unavailable. Capacity drops past a 5% step appear in Activity.

### PC status
- **Processes** shows each program's **GPU** and **Disk** use, sortable like the other columns. Right now names a program using half the graphics card or 50 MB/s of disk. A program Windows gave no reading for shows a dash with the reason, never 0; a PC without these counters says "n/a". Measuring runs only while the page is open and needs no administrator rights.

- Drive health shows changes in SMART counters over up to 90 recorded days. It warns about new sector and media errors, reported uncorrectable errors and low spare blocks.
- Choose NVMe warning levels in Settings > Notifications. The 80% and 90% life-used levels are suggestions. Drive warnings still start off.
- Drive warnings appear in Activity and can go to ntfy or Discord when you enable Drive warnings in Notifications out. Missing SMART data says “Not available”.

### Hardware
- **Fan ramp limits.** Each fan has Step up and Step down rates under Fans > Speeds, both off by default. Set how fast its speed may change, or use Put back to default. Heat and missing readings still go straight to full speed.
### Maintenance
- Split page styles into area sheets while preserving their contents and cascade order; appearance and behavior are unchanged.
- **Safer duplicate finder (Disk space).** A file that can't be read is counted as "couldn't be read" and is never matched. Several names for one file (hardlinks) are no longer listed as duplicates of each other. Online-only cloud files are never opened, since reading one starts a download; the page says "N cloud-only files skipped". Files are compared by size, then a 4 KB start-and-end fingerprint, then the full contents in 2 MB steps, so **Cancel duplicate check** stops within one step and groups that weren't fully compared are marked "not finished" with nothing to move. The check runs at low disk priority and stops if a game comes to the front.
- **Find empty folders** and **Find broken shortcuts** on Disk space, from the last scan. Each result opens a review where you pick what goes; items move to the Recycle Bin only, are checked again just before they move, and the outcome shows in Activity ("N moved to Recycle Bin, M failed"). Empty folders inside Windows, Program Files, ProgramData or AppData, folders named with a leading dot and folders holding a desktop.ini are never offered (apps often expect them); the page says how many were skipped. Folders or shortcuts Deck can't judge (unreadable, online-only, shortcuts to apps or unplugged drives) are never listed.

### Pages
- **Fans**: fan settings are one table with a single header row, fans without a reading are dimmed, and the new ramp limits sit in a fold that says how many fans are limited.
- **Session reports**: rows line up again, old reports show one clear message, and a session with very little saved frame data says so instead of drawing an empty chart.
- **CPU** and **GPU**: the applied profile comes first, the editor's rarely needed settings are labeled as such (CPU folds are now **Clock limits** and **Windows plan settings**), the lighting color switch comes after the name, and built-in modes use two or more columns on narrow windows.
- **Arrange windows**: the picked window has its own panel, snap zones are drawn as real layouts, and settings that need a switch say so.
- **Home**: tiles fit their content better, and in Edit Home the clock stays visible and the list of tiles lines up.
- **Clean up** is one tidy list with a heading per group instead of a stack of boxes. Lines that apply to a whole group are said once, empty groups fold away like the rest, and while sizes are being measured the page says so.
- **Settings** reads in one column at a comfortable width, without doubled headings. On narrow windows the list of parts becomes compact chips.
- **Sensors**: Heat check is a slim strip, every device shows on narrow windows, and Alerts has shorter cards with a one-line intro. "Send it out" is now **Send to phone or chat**.
- **Network**: Unusual moments has its own section, the quality strip has a legend, the live graph uses KB/s when traffic is low, and long ping host names wrap.

### Network

- **Trace the path** from an Unusual moment or the Network page. Watch up to 30 hops to the internet-ping target, with addresses, probe loss and delay. Stop at any time and keep partial results; the last five traces stay on this PC.
- A game or Deck microphone relay prompts before a trace starts. Hop loss that disappears farther along says **This hop may ignore pings (often normal)**. Results name no cause and say **No route** when the path is unreachable. IPv4 only.

### Reliability
- Internal: two timing-sensitive tests (a beam retry and a process-deadline check) have wider margins, and the offscreen preview's fake backend now answers the Sensors Alerts and History cards.
- Unreadable memory totals say **Memory unavailable**, missing startup timings say **Unavailable**, and music player or system card support checks offer **Try again** when they fail.
- Sound level meters stay empty and faint when Windows cannot read them. A measured zero still means silence.
- The cooler display leaves a row dark when its temperature or load color has no reading. Phone speaker quiet mode leaves the PC's sound alone when its original mute state cannot be read, instead of risking an unwanted unmute later.
- **No more made-up volumes.** When Windows will not tell Deck a volume or whether something is muted, the Sound tile on Home, the Sound page, the game bar and the volume pop-up now say **Unavailable** and turn the slider or mute button off, instead of showing 0 %, full volume or "unmuted". The microphone check before a call no longer says a microphone is muted when Deck simply could not read it.
- **Stale data says so.** If Deck stops receiving live readings, Home says how old the volume numbers are, and the hardware pages show their readings as Unavailable instead of freezing them.
- **Failures are named.** A graphics card whose voltage curve cannot be read says so in the profile editor, "Copy my look" offers Try again instead of waiting on "Checking…", and the Home profile tile and the overlay font list say when they could not load.
- Internal: tests now switch a pretend PC off at every write of a tweak apply and a tweak Undo, and cut a PC to PC transfer after each block, in the middle of one, before the rename and before the receipt, then check the recovery. They use in-memory fakes and a temp folder only; no change in Deck itself. They found one gap, listed in `docs/plans/SAFETY_NET_PLAN.md`, now fixed (next line).
- **Undo after a crash.** If Deck or the PC stopped in the middle of applying a Windows tweak, Undo no longer asks you to review a setting that Deck itself had just changed. A setting that something else changed afterwards is still shown for review and is never overwritten without your OK.

### Activity
- **Activity beside search** brings current changes and their existing Put back actions together with recent results and notifications. Each entry is titled with its own message, repeats group with a count, entries show times and page links, and unseen failures show **N failed** until you open it. History stays in memory, up to 100 entries for seven days; sensitive content is omitted or masked. It opens only when asked and creates no extra pop-ups.

### Home
- **Edit Home works from the keyboard.** The All Home tiles list now has a height for each tile as well as width, Move up and Move down name the tile, and Deck announces each move, resize, hide and reset. Two thirds is a width choice, and Fit no longer pushes the hide button off narrow tiles.

### Diagnostics
- **Crashes and hardware errors** in Session reports shows the last 30 days of Windows hardware errors, crashes, display resets, unexpected shutdowns and readable dump summaries. Filter by kind or open a row for its event ID and details. A dump module is a hint, not proof of a cause.
- History reads pause during games and sessions. Sources that need admin rights say so. New entries since your last look appear in Activity without a pop-up. Copied crash reports leave out local file and device details.
- Internal: a test of the Gaming page's session report and game library runs cleanly again (no change in Deck itself).
- **Network tests warn before they run.** The speed test and Lag while busy now say, before you press Start, how long they run and how much they download, and that your connection will be busy. If a game is in front or Deck's phone mic or voice is using your microphone, the card lists what the test would disturb and waits for **Run anyway** or **Cancel**. Nothing starts or changes your network by itself.
- **Right now on Processes.** A small card points out programs using a large share of the processor or memory, full memory, several busy background programs and available high disk activity. Each finding says **Seen** or **Possible**; missing or old readings say **Not enough data**. It lists what it cannot see, changes nothing and uses readings Deck already has.
- **Fair session comparisons.** A word above the table says **Like for like**, **Rough comparison** or **Not comparable**, with short reasons from recorded settings and play time. Different known frame limits or main display modes, or missing FPS readings, keep the numbers visible but replace better/worse claims with **Not comparable**. Short sessions, several changes at once, older sessions without recorded settings, and one session on battery while the other was plugged in are marked as rough. One driver, game-version or profile change can still be compared; the label does not prove an effect.
- **Heat check on Sensors › All readings.** A small card says when something stands out: a temperature at its limit, clocks falling while the processor or graphics card runs near its limit, or a fan at its highest speed while the temperature keeps rising. Each line says how sure Deck is (**Seen**, **Possible** or **Not enough data**), and one faint line names the readings this PC doesn't report. Otherwise it says nothing unusual stands out. It only reads what Deck already measures, changes nothing, and follows your °C/°F setting.
- **Why did it stutter? is more careful about causes.** Each cause and pattern now carries a word: **Seen** (the reading or Windows log entry was there), **Possible** (an indirect sign, such as shader-cache changes or driver time) or **Not enough data**. Wording says what was seen and what it may mean: "Shader caches changed during the stutter" instead of "The game was compiling shaders", "Driver work was high on one core" instead of "A driver held up a processor core". Older sessions show Possible.
- **Says what it could not watch.** Under the verdict, one faint line names any signal missing from the session (Windows event log, shader caches, driver and memory counters, other programs' graphics use), so a quiet session is not mistaken for one Deck could not look into.
- **Unusual moments in Connection quality.** With Record history on, Diagnostics > Network > Overview lists the unusual moments of the last 24 hours: internet pings that got no reply, two or more of a minute's five that went unanswered, or a delay well above the usual, with how long ago and how long it lasted, whether the router answered normally at the same time, and the samples around it under Details. It states what the pings showed, never a cause, and uses only the pings Record history already makes.
- **Copy report.** One button copies a plain-text report of those moments. IP and MAC addresses, Windows user folders and your PC name are removed first.
- **Add connection quality to session reports (new, off by default).** Turn it on in Settings › Games. When Record history (Diagnostics › Network › Connection quality) is also on, a game's session report gets one *Network* line: how many internet pings were answered during the session and a plain statement of what the readings show, or "Not enough evidence to say". It sends no extra pings.
- **Record history keeps the last 24 hours in detail.** Besides the 10-minute averages, Deck now keeps one small sample per minute for up to 24 hours (at most 1,440), so a spike can be looked at later. The Connection quality card says how many it is keeping. Clear history deletes them too. Nothing is added to what Deck pings and nothing is uploaded.
- **Network readings say when they are missing.** The Network page no longer shows 0 ms, 0% loss or a good grade without a reading: a ping without an answer says *No reply*, a host not measured yet says so, an old reading says *Stale* with its age, and an unavailable value says *Unavailable*.
- **Pings keep the reason they failed.** Behind the scenes, a ping that did not answer now records whether it timed out, was unreachable or could not resolve the name, plus when it was taken. The Network page looks the same for now.
- **"Lost" is now "probe loss".** Unanswered pings are labeled as probe loss, with a short explanation: routers and servers can block pings, so they do not prove a game lost packets. Region game-server delays are marked as stand-ins.

### Search
- Searching for microphone, speakers, shortcuts, hotkeys or FPS drops lands on the right page.

### Navigation
- Internal: documented page layout patterns and added unused shared spacing styles; pages look and work as before.
- **Every page starts the same way.** Title, then its one-line description, then search and the page buttons, then the tabs. The description no longer squeezes into a narrow column beside the search box, and on narrower windows the search drops under it. The "Deck sees ..." bar on Game profiles now wraps its buttons onto their own row instead of becoming a thin column.
- **Devices** has a live Device batteries page and the Controller page. Battery preferences stay in Settings; Lighting and Cooler display stay in Hardware with links from Device batteries. Battery tray clicks keep their destinations.
- **Diagnostics** owns Session reports (including Why did it stutter? and session comparisons) and Network. Game profiles links to the reports; existing session, network, search, tray, notification and Home links keep working.
- All eleven sidebar areas scroll in compact windows. Saved orders and hidden-page choices carry over to Devices and Diagnostics.
- **Audio** has four pages: **Mixer** (Playback and Outputs & rules), **Microphones**, **Voice effects** (Effects and Mic chain) and **Soundboard**, with a link to Music & volume pop-ups in Desktop. Nothing inside them changed, only where you find it; old links, search words, the tray's Voice menu and a page you hid before stay where they were.
- **Connections** brings PC to PC, Phone and Project sync together. Settings stays alone at the bottom; Project sync keeps its hidden-unless-on default.
- Saved sidebar orders place new areas beside their default neighbors, and hidden sound and connection pages stay hidden after upgrading.

### Gaming
- Stutter recording keeps fresh game frames when Windows cannot identify the foreground window. Normal 2-3 second sampling no longer creates unknown coverage.
- Hitches of 250 ms or more, including multi-second frames, save without waiting for steady history. Nearby trouble groups together; a session keeps its 20 worst moments.
- **Whole PC froze** moments record when Deck's own wake-up check was at least half a second late, with available readings from before the pause and nearby Windows faults. Scheduling pressure or sleep can also delay the check; it does not prove a cause. Frame-data gaps have their own label.
- GPU reset checks now read Windows events directly without launching a program. Tailscale status refresh waits while a game is in front and resumes afterwards.
- Session reports keep gaps when frame data stops arriving and explain when the frame source was unavailable while the game was in front. Sparse recordings no longer get a whole-session smoothness grade.
- **Organize your games** in the Games tab: favorite games stay first, with progress statuses and your own tags. Filter the list by favorites, status or tag alongside Find a game. Choices save at once and stay separate from each game's profile.

- **See what changed between sessions.** The comparison now lists recorded driver, game version, CPU/GPU profile, frame-limit and Deck-version changes under **What was different**. Unknown details are left out; older sessions explain what they did not record. Graphics driver versions currently come from NVIDIA; game changes use the executable's file version or, if absent, its modified date. Frame limits come from RivaTuner, not in-game settings.
- **Compare two sessions of the same game.** In "Why did it stutter?", pick an earlier bar under *This game over time* to see it beside this session: average FPS, 1% and 0.1% lows, hitches an hour, time lost to hitches and play time, each with how much better or worse it got. Useful for checking a driver, setting or frame-limit change: play the same part before and after. Short sessions are marked as rough, and missing measures say *Unavailable* rather than showing a guess.

### Voice & soundboard
- **MicDrop is now part of Deck**, under Audio as **Voice & soundboard**. Three tabs bring together voice effects, a mic chain (noise suppression, gate, EQ, compressor and limiter) and a soundboard with separate levels for you and others.
- **Controls in the tray and on your phone:** the Desktop tray menu has a Voice submenu, and the phone remote shows a Voice card while it runs, with effects, mute, stop sounds, clean voice and sound buttons with favorites first. The phone microphone goes through the voice's mic chain and effects too.
- **Get VB-CABLE from the page.** Deck downloads VB-Audio's own package and opens its setup. An optional switch makes CABLE Output the default mic while the voice runs and puts the old mic back afterwards, or at the next start after a crash. It starts off.
- **Bring in MicDrop's settings:** import its sounds, effects, mic chain and device choices without changing MicDrop's own files. Quit MicDrop first; importing does not turn the voice on.

### PC to PC
- **Sending from the command line waits for its own transfer.** `deck.exe --pc-send` reported on the oldest transfer in the saved list instead of the one it had just started, so it could print "Done" with another file's name at once and quit while the other PC was still asking. The receiving PC was then left with an offer nobody was waiting for. It now follows only the new transfer to the end.

### Phone app (0.5.0, 0.5.1)
- **Staying connected on phones that close apps on their own.** Settings has a new "Stay connected" card with three one-time steps, each opening its screen and showing ✓ when done: let Deck run in the background, turn Deck on in the phone's Auto-start list (Tecno, Infinix and itel Phone Master; Xiaomi, Oppo/Realme, Vivo, Huawei/Honor and Samsung lists; shown only when the phone has one), and Battery → Unrestricted (also turn off "Stop app when idle"). On Tecno, Infinix and itel, a phone given Deck's one-time permission from a PC adds Deck to the freezer's exemption list by itself. Tecno's freezer was found pausing Deck in the background, which dropped the link and showed "Looking for your PC".
- The app's version is now 0.5.0, so phones show the new build as an update.

- **Main screen:** Quick actions come right after the stats; Power is a small neutral button so the PC name fits; one line under each stat ring; seek buttons read 10s with rewind/forward icons; All apps sits on the volume line; profile tiles leave out the profile already on and have room for their numbers; open profile lists no longer touch the next card.
- **App size and Text size** (Settings): 100/90/80/70% for everything, and Small/Normal/Large/Larger for text alone. Below 100% the stat rings and Quick action buttons grow back into free space.
- **Stay connected:** the Auto-start step no longer claims to be done (phones don't report it); the freezer exemption is shown separately and checked after it is written.
- **Disconnects:** the app logs why each link ended; the home-again check can't stall the link and switches back without a delay.

### Phone remote (PC)
- **Fewer phone drops:** the Tailscale address is read from a cache refreshed in the background, so a slow `tailscale status` no longer holds up the phone's updates; turning the phone remote on while it runs no longer restarts it; after a restart the usual port is retried before another. The log says why each phone left and warns when building the phone's state takes over 3 s.

### Releases
- **The phone app is no longer carried over by mistake.** 4.6.0's `Deck.apk` was 4.5.0's app, so the new phone app never reached phones. Releasing now stops when the app changed and no new `Deck.apk` is given, or when its version number wasn't raised.
- The code checks that run before a release pass again (an unused leftover was removed).

## 4.6.0 — 2026-11-17

### Power & time
- **Shut down when a task says it's done.** A new condition for **Shut down when…**: Deck waits for the programs that signal it, and acts only when every one has been finished for the minutes you set. Made for long jobs in coding tools, which keep working in the background after they seem to stop.
  - **One switch per tool.** Deck can add its signal to Claude Code and Codex for you and take it out again; your other settings in those tools are left as they are. Any other program or script can send the same signal with one command shown on the page.
  - **It knows the difference between done and paused.** A task with background jobs still running, or one that will wake itself up again, is still working. A task waiting for your permission or your reply holds the plan (or counts as done after the minutes you choose). A task that stopped with an error or a usage limit holds the plan unless you say it counts as done.
  - **You see who it waits for,** with a **Don't count** button beside each task. Signals sent while Deck is closed are picked up when it starts.

### Gaming
- **"Why did it stutter?" (was "Why did my FPS drop?") is rebuilt to explain a whole session, not only single dips.**
  - **A verdict for every session:** Smooth, Mostly smooth, Some stutter or Rough, a one-line diagnosis, and the figures behind it: average, 1% and 0.1% lows, hitches per hour, the share of time lost to hitches and the slowest frame.
  - **A timeline of the session:** FPS with its 1% low, every hitch, everything Windows logged, and a numbered pin for each saved moment. Point at it for the figures of that stretch; click a pin to open the moment.
  - **What the stutters have in common:** a hitch that comes back on a timer (the classic sign of RGB, fan-control and monitoring apps, Wi-Fi scanning or a device reconnecting, which Deck names when it lines up), shader compiling, one cause that keeps coming back, and driver or drive resets.
  - **Many more causes, read from Windows without touching the game:** the graphics driver saving new shaders, drivers holding up a processor core, memory read back from disk, another program using the graphics card, a program that just started, and the system event log (graphics driver resets and errors, a device connecting by name, drive resets, hardware errors, the firmware limiting the processor, battery and mains switches, Windows Update and Defender).
  - **What to try for each cause,** with a button to the Deck page that helps (Apps to close, Free memory, Fans, GPU, Drive health, Network, Startup apps).
  - **Moments are numbered like their pins,** with a count of their causes you can click to show only those, and a strip of the slowest frame of each half second around each one.
  - **This game over time:** hitches per hour for its last twelve sessions, whether this one was smoother or rougher than usual, and whether shader stutters are fading.
  - **Session reports** open the same view for that session.
  - The panel no longer flickers while the Sessions tab redraws every second during a game; an open session report no longer shows "Loading" again each time.
- **"Why did it stutter?" lists only what you would notice.** It used to record any single late frame, so a steady 60 FPS game filled the list with entries like "60 → 62 FPS". Now a drop must stay down (a fifth under the usual speed for a second and a half, or a third under for half a second), and a stutter needs one long frame of 100 ms or more, or two shorter hitches close together.
  - **Drops and stutters are told apart:** a stutter reads "Stutter at 60 FPS · longest frame 85 ms" instead of two nearly equal speeds, and a speed is never shown going up.
  - **Menus, cutscenes and frame limits are left out:** a smooth lower speed while the graphics card and processor have less to do is the game easing off.
  - **One bad stretch is one entry** (trouble within 10 seconds merges), and a long session keeps its 20 worst moments instead of its 20 latest.

- **Game names and pictures:** a game found through Windows’ list of installed programs no longer carries the installer’s additions in its name (“XCOM Enemy Within version 1.0” is now “XCOM Enemy Within”). A game that Steam sells as an add-on of another had no picture on Home and in Game profiles; it now uses the pictures of the game it belongs to.

### Flyouts
- **The music flyout no longer opens when a song ends by itself** with **When the next song starts** switched off. Some players stop for a second while the next song loads; Deck took that for a pause and a resume and showed the card for each. A pause the player takes on its own right after a song change, and the resume that follows it, are no longer announced. Pausing yourself still shows the card.

### Game pictures and detection
- **Pictures that failed once are no longer missing for a week.** A picture asked for while the internet was down (just after logon) or while a site was busy was remembered as "none"; now Deck tries again later. Pictures already missed that way are asked for again once.
- **More games get their pictures:** the picture you set in Steam yourself comes first; older and newer Steam layouts on your PC are read; newer Steam games whose pictures moved to new addresses are found; Epic pictures from all of Epic's image servers and kinds load; and a game known only by its program's name is also looked up by its folder's name.
- **Gentler on the sites:** one picture request at a time, the same picture asked for by two cards is fetched once, and nothing is asked for a while after the network failed or a site said to slow down.
- **Steam's own word on what is a game.** Steam apps the store calls software (Wallpaper Engine, Blender) are no longer listed, and new games are never left out for a name nobody listed. Names are now matched as whole words, so games like *Assassin's Creed Origins* are no longer mistaken for a launcher.
- **Fewer false games:** Wallpaper Engine's window and anti-cheat starters (such as Fortnite's EasyAntiCheat starter) are no longer recorded as games, and old sessions of them are hidden. *Crash Bandicoot* and *Call of Duty: Vanguard* are no longer mistaken for a crash reporter and an anti-cheat. New games without a store are recognised by what only games ship (DLSS, FSR, XeSS, GameMaker, Ren'Py, FNA, MonoGame, LÖVE).

### Pages
- **Open folds are one box.** A folded section that is open now keeps its settings inside the same border as its title bar, with a line down the side, so it is clear where it starts and ends.
- **Controller overlay page is shorter.** Per game moved beside Look and Position, so the two columns end together instead of the right one running a third of a screen further; **Reset overlay** is a button that asks first instead of a fold.
- **Death counter › Games: the Game picker shows the game whose screens are shown.** A game with no deaths yet was missing from the picker, which then showed another game's name above it.
- **Battery tray icons follow the taskbar:** on a light taskbar they are a dark battery on white (they were a white battery with a dark rim, muddy there), and switching Windows between light and dark redraws them.
  - **One icon for all devices** (Settings › Devices › Look): a single tray icon for the device with the least battery; pointing at it lists every device, the weakest first.
- **Sensors › All readings redesigned.** A device's readings are one table grouped by what they measure, the unit shown once beside the current figure, then Lowest, Average and Highest. The Cores and Fans tables show performance and efficiency cores under their own headings, and a switch chooses between **Now and highest** and **Lowest, average, highest** (this replaces the long "Minimum and average per item" list underneath). **Where these readings come from** is a plain list: each collector once, and only the readings that stopped updating are named.
- **Windows tweaks name what a press does:** an on/off setting shows its state (**On** / **Off**) and a **Turn off** or **Turn on** button instead of a switch; a setting with mixed parts has **Turn all off** and **Turn all on**.
- **Disabled buttons and drop-downs look disabled:** a dashed outline and faded words, instead of looking almost like the enabled ones.
- **Smaller layout fixes:** a button beside a labelled field lines up with the field (Display's night colour and test pattern); the Game servers list lines up with the rest of its card.
- **Death counter › Games is tidier:** each game's deaths are shown once (All games keeps only the deadliest bosses); the shared library's count sits in the Death-screen library fold; the stray "+1 death" row at the bottom is gone (adding a death is on Now); Learned screens is one card with sections instead of cards inside a card; "2 of 3" reads "2 (keeps up to 3)"; **Pick another** once a screen is learned; the kill-screen choice is a real button (**This game has none**); and only the guess question's **Yes, that's it** is highlighted.
- **CPU and GPU editors read properly in narrow windows:** a slider row's label and description sit above its slider instead of being squeezed beside it (the CPU editor's descriptions broke every two words); GPU labels keep their help mark after the last word, values like "+500 MHz → 11001" fit on one line, and the "Runs at … at most" note has its padding back.
- **Death-screen library says where a friend's code comes from** (Share with a friend, under that game's learned screens) and sits inside its fold without a second frame.
- **Controller › Test: Device details no longer flickers** under the pointer, and the test redraws only when a reading changes and never during a click.
- **Windows tweaks: the category list no longer flickers** when you switch categories.
- **No line above the first setting of a card** on the Performance overlay and status pages.
- **Scrolling no longer jumps back while a page updates.** Pages that refresh every second, like **Recent sessions** while a game runs, pulled the scroll back a little each time; they now wait until you stop scrolling.

### PC to PC, phone and Project sync
- **PC and phone transfers:** Verify the PC at the selected address, fail unreadable project offers safely, reserve receiving folders, verify resumed files, and remember completed uploads and transfers so a lost reply cannot duplicate them. Empty projects keep their root folder. Phone control releases held mouse buttons when paused, upload cleanup only removes Deck part files, and pending Android layout edits survive other clients' broadcasts. Connection and storage errors explain what to check.

- **Workspace / Project sync:** Keeps edits made during sync and versions received from different PCs, preserves session branches, and waits for complete backups, folder scans and cloud uploads before passing changes on.

- **PC to PC:** Control opens a paired PC's screen in your browser after its user allows it, over the home network or Tailscale. Phone and Screen settings on that PC still apply.

- **PC to PC:** Compact recipient, offer, transfer, sharing and app layouts adapt to narrow windows.

- **PC to PC:** Incoming offers clear when the connection ends, and a failed connection reports that the sender should try again.


## 4.5.0 — 2026-11-14

### Clearer controls and steadier pages
- **Deck recovers while starting:** when its background part is slow or unavailable, a plain message appears and Deck retries with increasing delays, opening by itself when it answers.
- **Script errors use plain words** with the full details kept in the log. Missing readings show a dash, and an incomplete timer no longer shows NaN in the sidebar.
- **Switches say On or Off** beside the control; rows that already spell out the state keep their own wording. Empty tick boxes and off switches have stronger outlines across all eight themes.
- **Page titles stay on one line:** the search row moves underneath when needed, and hovering a shortened title shows its full name.
- **Keyboard focus is easier to follow** on navigation, profile cards, app rows and preview choices. Scrolled pages keep their place when readings refresh or controls redraw.

### Search
- **Search finds every control, not only the pages you have already opened.** Capitals and accents do not matter ("Clípboárd" finds Clipboard), words can be in any order, simple plurals match, and one wrong, missing or swapped letter is forgiven in words of five letters or more ("tempezature" finds Sensors). Short words are never guessed at.
- **Better order:** the strongest page or tab match leads individual controls. **Fan** and **fans** lead to Fans, **HDR** to Display, **theme** to Settings > Appearance, and **uninstall** to Apps > Installed. Other matches keep their order and variety. Eight Deck results show first, with a **More Deck results** row.
- **Landing is exact:** a result for a setting opens its page and tab, opens any fold around it, scrolls to it and marks it for a moment. If the setting is not shown with your current options, Deck says so instead of landing nowhere.
- **Nothing found** now says so and offers up to three nearby page or tab names beside the web search.
- **Typing quickly is steadier:** only the newest search runs, an old answer can no longer replace a newer one, and Enter runs the row you see. Saved quicklink keywords beat ordinary name matches, and an app and a Deck page are ranked by the same rule. The finder inside Settings uses the same matching.

### Gaming
- **Performance overlay:** corner choices form a screen-shaped map. The status and preview explain whether RivaTuner is drawing over a game, waiting for one or stopped, and when the preview is smaller than the real overlay. **Frame limit** has its own section under Behaviour, with the current global limit and a clearer explanation of per-game limits.
- **Controller › On screen** fits more settings beside the preview, with corner choices arranged like the screen's edges.
- **Death counter › Games** folds learned death and victory pictures behind a count and the last-learned time.
- **Game bar:** each preview widget is one keyboard choice, with a visible focus ring.

### Hardware and PC status
- **Shorter CPU and GPU pages:** compact built-in modes and applied-profile rows show more at once. Requested settings are clearly separate from measured readings.
- **Profile editors:** Back to CPU asks before dropping unsaved edits. The GPU editor distinguishes unsaved edits, settings being tried, later edits and partial failures; its cancel button says what it will discard or restore.
- **Missing readings and devices** have clearer explanations and next steps, including read-only fans, cooler display connections and a retry when This PC cannot read the parts list.
- **Fans › Fan speeds is rearranged:** every fan is a tile of the same size with one line each: its name, its RPM and the control signal it is sending ("25% signal", a signal and not a measured speed). A tile names its mode only when it differs from the **All fans** choice. A fan reading 0 is dimmed and says "No reading". Columns are chosen so the last row is never a single tile.
- **Lighting:** the preview is now above the settings, so a change shows without scrolling back.
- **Fans, Lighting and Cooler display wording:** the help says **Apply hardware changes** where it said "Apply", and the fan preview is called "Preview a curve" (button **Run preview**).

### Switches, sliders and editors now tell the truth
These came out of reading every page's code and clicking through the installed app.
- **A switch that could not make its change goes back** to where it was and says why, instead of staying flipped. A second click while the first change is still being made is ignored. This covers Sound & mic, Windows rules, Network history, the Send-to menu, Phone, the Death counter's per-game switch, the Performance overlay's RivaTuner tray switch and Windows tweaks.
- **A setting that fails to save leaves the page showing the real value.**
- **Settings saves are retried.** If Deck cannot write its settings, a notification says **Settings could not be saved** and Deck keeps trying (after 2, 4 ... up to 60 seconds) until the folder is writable. A settings file Deck cannot read is no longer replaced by defaults.
- **The CPU and GPU editors ask before dropping edits** whichever way you leave: Back, the sidebar, a page tab, a search result, or opening another profile's editor. **Keep editing** and Escape leave everything as it was. The GPU editor puts the card back to the saved profile first if a test is on it.
- **Sliders:** letting go outside the window no longer leaves the page waiting. Home volume sliders send fewer writes while you drag and end on the exact value. Display **Brightness** and **Contrast** end on the value you released, and go back to the monitor's real value when it refuses.
- **Free-space figures agree.** Disk space, Drive health and This PC show the same decimal GB for the same drive (This PC used to divide by 1024 and call it GB, so it read about 7% lower). Disk space says when the scan was made and shows the current free space beside it; This PC's weekly Disk space tile says when it was checked, and no longer calls the lowest-free drive "the fullest".
- **Notifications never drop the shutdown warning.** When more than four are showing, the oldest other one goes, not the shutdown or sleep warning with its Cancel button.
- **Failures you could not see are now shown:** starting a Clean up scan, ending a locked process that Windows refuses, copying to a refused clipboard, adding a ping address or host when the setting cannot be saved, a failed Apps to close or Built-in apps list (with **Try again**), a failed Sensors history read (with **Try again**).

### Page fixes
- **Death counter:** the automatic-counting line says counting is off when it is off for that game; **Confirm boss** reads "Confirm boss: <name>". Every Death counter setting has a **?**.
- **Game bar:** the **Drops** widget shows how long ago a dip was, not a huge number; letting go of a slider outside the bar no longer stops it refreshing or closing; the **Deaths** widget says when the counter cannot be read instead of offering to turn it on; every widget has a **?**.
- **Game profiles:** **Why did my FPS drop?** says it covers the current or last session; **Apps to close** loads once per visit and has **Refresh** and **Try again**.
- **Performance overlay:** opening **Start from a preset** no longer throws the page down.
- **Clipboard:** the arrow keys, Delete and Enter work after you click an item, and act on the item that has focus.
- **Disk space:** recycling a folder you have open drops it from the tree, the type list and the bar. **Build a space plan** asks for a number instead of sending nothing.
- **Clean up:** the **Show N with nothing to clean** button's spoken name matches its words and keeps focus when the count changes.
- **Display:** a scale the monitor refuses puts the list back; an emptied schedule time box is ignored.
- **Apps and Windows tweaks:** the filter and sort groups have their own names for screen readers; the Windows tweaks filter is "Show which tweaks".
- **Fans:** Calibrate no longer redraws another page while it measures, and an empty fan list no longer breaks the extras tab.
- **Network:** **Lag while busy** no longer piles up redraws; App updates without winget says so once.
- **Settings:** Features › Desktop › **Review window rules** opens the rules tab; the Settings tour finds its step; **Check every** in Project sync reads "1 minute".
- **Help:** 21 **?** marks were added (every Game bar widget, Virtual display, nine Death counter settings) and 68 existing ones were corrected against the code (button names, defaults, limits, what turning something off does).

### Maintenance, Settings and Power & time
- **Clean up** folds long groups of measured-empty rows behind a Show button, keeping selected and unmeasured rows visible. The review describes only the selected kinds of clean-up.
- **Disk space:** the folder explorer comes before Disk tools.
- **Apps:** row details wrap, missing uninstall options have an explanation, and selecting an app keeps keyboard focus. The filter says it searches this list by name or publisher, and the details explain when a filter hides your selection.
- **Startup apps and Startup optimizer** distinguish an empty list, no search matches and a failed reading, with clearer startup-state wording and an **Analyse** button.
- **Settings › Features** uses columns and shorter related links; pages hidden with their whole area say **Hidden with area**. Connections uses columns in wider windows.
- **Timers and shutdown plans** show the clock time they are waiting for, including the day when needed, and explain what Cancel stops.

### Under the hood
- **Quieter logs:** a CPU custom power-limit clamp warns once for the same requested and held limits; Target FPS reports a missing reading once per episode. Music pop-up timing details are logged only on activity or when a stage is slow.
- **Better game detection:** settings and editor front ends, including a wallpaper program's settings window, and known wallpaper renderers no longer start game sessions automatically.
- **Steadier window placement:** a correctly maximised window is no longer moved back because its outer frame extends past the monitor.
- **Less background work:** Tailscale state is checked at most every five minutes while Deck's main window is hidden or Tailscale is not running. PC to PC skips peer discovery while switched off.
- **Lighter while hidden:** with the music pop-up on and no song loaded, Deck no longer watches the skip keys and checks for a player every 5 seconds instead of every second. Pages stop asking for updates while the window is hidden and refresh when it opens. A switched-off game bar, hot corner, battery list or plain-copy helper does almost nothing, and the shares file is saved only when it changes.
- **Hardware and files fail loudly, not quietly:** switching a CPU or GPU profile from the page returns the real outcome, including a profile that was saved but could not be applied; an unreadable GPU crash mark holds a risky profile instead of being treated as missing; snippet and sound-profile saves report a failed write and change nothing in memory, and a device preference with one invalid field is rejected whole instead of half-applied; Deck's stores no longer write an empty file when serialising fails; caches that could be cut short are written atomically.
- **Commands stay off the UI thread:** audio, display, startup, network and search commands run on blocking threads; process waits for Windows tasks, setup snapshots and icon refreshes have time limits.
- **Bad input cannot crash Deck:** damaged NTFS file-table records, non-ASCII curve and registry text, oversized numbers (timers, ids, ports, DWORD values), a bitmap with an impossible height and a malformed installer code are rejected with an explanation.
- **Busy flags clear after a failure:** a failed index, Clean up scan, speed test, lag check or calibration launch no longer leaves the feature stuck busy.
- **Testing tools and developer guide:** `tools/testing/check-wiring.mjs` (UI calls against Rust commands, setting keys, events and ids, with its own tests), `tools/testing/check-search.mjs` with its `search-*.mjs` helpers and the generated `ui/search-index.js` (regenerate with `--write-index`), `docs/DEVELOPING.md` and `docs/TESTING-CHECKLIST.md`.

## 4.1.0 — 2026-11-12

- **Tidier app list (Maintenance › Apps):** Uninstall, Review removal and the folder button sit on one line at the right, in the same place on every row; the install date is no longer cut off, and an unknown date is left out instead of saying "Unknown".
- **Windows tweaks use switches:** a setting that is simply on or off is a switch, like the rest of Deck. The On | Off buttons with "Off" filled in looked like a switch turned on.
- **What Deck changed says what changed:** each row shows **Now** and **Before** in plain words ("Ads and news in Edge — Now: Off, Before: On"; "Fan speeds — Now: Deck sets them, Before: the motherboard") with its area above it, instead of "From" and "Ends" notes.
- **A tidier top bar:** the "Deck is changing N things" button sits on the search row instead of a line of its own, so Edit Home and the other buttons line up, and the search box is longer on every page. **Settings › Appearance › Show what Deck is changing** hides it (What Deck changed stays in the tray menu).
- **Quieter page row:** the row of pages in a group lost its box; the open page is filled in and the group name is grey with a dot in the group's colour.
- **Search waits for you:** opening Deck no longer focuses the search box; clicking it or typing still starts a search.
- **Clearer controls:** sticky panels cover the content beneath them, option toggles have a filled selection, and page section tabs keep their underline.
- **Change counts explain their scope:** the top-bar tooltip lists the areas it counts, and Windows tweaks says its count covers Windows settings.
- **This PC:** storage sizes match Windows, C: comes first, peak times show local hours and minutes, unavailable controls use neutral chips, and the weekly tiles line up.

### Every page, checked
Every page and tab was read top to bottom, scrolled, and fixed where it was wrong, cut off or unclear:
- **Gaming:** the overlay preview's buttons have names and no longer cover the readings; Game bar sliders show their range; empty shortcut boxes say Set shortcut; death counter and session numbers line up.
- **Hardware:** CPU, GPU and fan profile summaries read in plain words ("41% power · fans 30%", "No speed limit"); GPU modes are listed slowest to fastest; lighting status lines are plain sentences.
- **PC status:** sizes on Disk space, Clean up and drive pages use the same units as Windows; a nearly full drive says so; latency tests say Testing… while they run; Deck itself is labelled in Processes.
- **Desktop:** microphone, clipboard and flyout buttons have text labels, duplicate media sessions are gone, the sliders line up.
- **Maintenance and Power & time:** the force-close switch says unsaved work is lost; update tabs share one Check for updates; uninstalling Deck, runtimes or drivers warns more clearly; apps without an icon get a letter.
- **Home, Phone and PC to PC:** the pairing card shows once above the tabs, the PC to PC switch sits in it, the transfer log is behind Show log.
- **Settings:** plain labels for opacity and appearance, the death counter settings in one column, clearer Store update wording.
- **Windows tweaks:** the category list scrolls on its own and keeps the selected one in view; settings that are partly on show Mixed; long options fit on one line and say which is Windows' default; Unpin all and turning Recall off ask first; a changed setting says what it was before; fewer, clearer tags.

### Easier to find your way
- **Plain names for everything.** The sidebar groups are now Gaming, Hardware, PC status, Desktop, Maintenance and Power & time, and pages say what they are: Game profiles, Performance overlay, Death counter, Drive health, Arrange windows, Sound & mic, Music & volume pop-ups, Windows tweaks, Project sync. The old names still work in search, and your own order of groups and pages is kept.
- **Every page says what it is for** in one sentence under its title.
- **A group opens its first page**, every time, and the row of pages above it is labelled "Pages in Gaming" (or whichever group you are in).
- **CPU and GPU start with the one-click modes**, each with a line on what you get (quieter, cooler, faster). Your own profiles are below them.
- **Deck game mode is honest when it has nothing to do:** it says no changes are selected and offers Choose changes, instead of reporting itself as on.
- **Fans and Lighting:** Quieter fans is on the Speeds tab, and Lighting opens with Colour. Labels use plain words (the technical name is in the ? help), and buttons say what they do: Apply hardware changes, Discard pending changes.
- **Search finds everything:** every tab and every setting is a result, with the place it leads to (for example Network › Tests, or Settings › Device batteries), and opening one takes you to the exact row, highlighted. Technical terms and the old page names work too. The finder inside Settings finds settings the same way.
- **Show only what you use:** Settings › Features hides whole areas or single pages from the sidebar, search, Home and the tray menu. Hiding never stops or changes anything; each row says what keeps running and where its switch is. Show everything brings it all back.
- **A shorter tray menu,** with the common actions first.
- **What Deck changed:** when Deck is changing something on your PC, a chip in the top bar says so ("Deck is changing 3 things"). It opens the list with Put back for each change and Put everything back. The list says which kinds of change it does not cover yet.
- **"I want my PC to be…" on Home:** Quieter, Faster in games or Use less power. Each shows exactly what it would change before you apply it, and can be put back. (New installs get it when the PC has CPU or GPU modes; add it to an existing Home in Edit Home.)
- **One name for each thing, and words that say what happens:** Deck game mode (no longer also called Boost), Put back for restoring what was there before, Discard for dropping unsaved edits. About 45 settings gained a line that says what they do, and buttons name what they act on ("Apply selected tweaks", "Stop scan").
- **Settings is in the same order as the sidebar,** with Features near the top; Devices is now called Device batteries.
- **Fixed:** the top bar wrapped the window's close button onto a line of its own and kept an empty row when Deck changes nothing; the suggested CPU and GPU mode (Balanced, Normal) was painted like the selected one; a page's own tab row was announced to screen readers as "Pages in <group>".
- **The guide has a new first page, Find your way around,** and every guide page starts with where to find the thing it describes.

### This PC, rebuilt
- **Your PC at a glance:** a spec sheet with the board or laptop model, processor, graphics with its driver version, memory with the speed it runs at, storage, every display with its resolution and refresh rate, Windows with its build, the BIOS with its date, and how long since the last restart. **Copy specs** puts it on the clipboard as plain text.
- **Free speed it points out:** memory running below its rated speed (turn on XMP or EXPO) and a monitor running below its highest refresh rate (with Open Display) get an amber line.
- **This week as five tiles** (Temperatures, Drives, Disk space, Sensor alerts, Deck) instead of a list of sentences, each with Fine, Check or Act now, opening its page when clicked. Times are your local time.
- **One list of what Deck can control here** (Works, Partly, Read only, Not available) instead of two tables with different words.
- **The support report moved to Settings › About**, next to Diagnostics.

### New start
- **A new start for new installs:** Deck opens on Home with a short introduction (what Deck is, how to open it again) and a First steps list for this PC. Both can be dismissed for good. Tours no longer start by themselves; they are on each page's tour button.
- **A simpler Home** for new installs: Sound, Pinned & frequent apps, PC readings and Power & timers, with music and the current game only when there is something to show. Your existing Home is untouched; Edit Home offers Try simpler Home, and Cancel puts yours back.

### Added
- **Logitech batteries:** wireless Logitech mice, keyboards and headsets on a Unifying, Bolt or Lightspeed receiver (or connected directly) now show their battery in Settings › Device batteries and the tray. Deck only sends read requests, about every 5 minutes per device, and a device that doesn't answer is hidden and asked less and less often.
- **Device readers are gentler:** a headset, mouse or receiver whose connection fails is no longer written to every 2 seconds; it is left alone for 5 minutes and then for longer. A headset reply is only taken when it echoes the request, so a volume knob or another program's traffic is never read as a battery level. A Logitech battery status of "charged" no longer counts as charging.
- **More batteries:** a connected Bluetooth LE device that gives Windows no battery level is now asked for the standard Battery Service level (about every 5 minutes, never the typing and pointing part), and devices with a standard HID battery report (uninterruptible power supplies, some headsets) show up too, ranked below every other source.
- **Razer mouse batteries:** Razer wireless mice (DeathAdder, Viper, Basilisk, Naga, Cobra, Lancehead, Mamba, Pro Click) now show their battery and charging state, read about every 5 minutes with the two read requests Razer's own software uses. A call that doesn't return in time is cut off and that mouse is left alone until Deck restarts.
- **Headset batteries:** wireless headsets on their USB dongle (SteelSeries Arctis 7, Pro and Nova 7, Corsair Void and HS, HyperX Cloud Alpha Wireless) now show their battery, read about every 5 minutes with the one request the maker's own software uses. A headset that is switched off disappears from the tray. A Logitech mouse or keyboard switched on after a long time off now appears within about 5 minutes (it could take up to 30).
- **Settings › Device batteries:** one place for the battery of your controllers, headsets, mice and keyboards (with Colour by level, the icon is green while charging and red when low). Choose the tray icon style and which kinds of device get an icon; for each device set its name, tray icon, warning level (Never to 50%) and whether the warning shows over games; forget devices that are away; copy a device report (without names, addresses or serial numbers) when a device shows no battery. The Controller battery switches in Settings › Games became a link to it. Copying the report never freezes Deck, and the keyboard focus stays on the control you changed.
- **Device batteries (in progress):** the controller battery code now covers any device kind; Bluetooth headsets, mice and keyboards that report a battery are now read, like controllers, and only while connected (the Controller page's battery switches keep working). Each device can have its own tray icon, with a symbol for its kind (controller, headset, mouse, keyboard); clicking a controller's icon opens the Controller page, any other opens Settings.

### Changed
- **Deck quits faster**, and so installs and updates finish sooner: it no longer waits up to a second for its fan and sensor readings to finish before handing the fans back to the BIOS, and the setup checks every tenth of a second whether Deck has closed.
- **Deck starts a little faster:** the list of drives is read just after the start instead of during it (it could also wake a sleeping hard disk).
- **No more short freezes of the window and tray** when Tailscale is installed: reading its address ran on the thread that draws them.

### Fixed
- **Virtual display turns on again after a restart.** A virtual display that was off when the PC restarted couldn't be turned on any more: Windows doesn't load a turned-off virtual device after a restart, and turning it on stopped with "The device is not connected". Deck now sees this and makes the device again from the driver that is already installed (nothing is downloaded; one admin prompt when Deck runs without admin rights).

## 4.0.3 — 2026-11-10

### Fixed
- **Updates work again.** Since 4.0.0, a Deck installed in Program Files downloaded an update to 100% and then stopped with "The setup could not be retained": the small record kept for Go back was refused in Deck's own protected updates folder. Copies on 4.0.0 or 4.0.2 can't update themselves to this version, so install 4.0.3 once from the release page; updates work by themselves after that. Old setups in that folder are cleaned up again too.
- **Media flyout volume (with "Volume with music" set to one card):** the level shows whole percents while you drag (it showed numbers like 40.963855421686745%), and it no longer jumps back to the old level in the middle of a drag.
- **USB drives can be ejected again while Deck runs.** Deck kept every disk open for its drive temperature and speed readings, so Windows said "This device is currently in use". It now opens a disk only for each reading and closes it at once, and finds disks plugged in or removed while it runs (every 30 s).

### Changed
- **Sensors › All readings:** the device list and the details scroll separately, each within the window, so every device in the list can be reached while the details stay put.
- Releases can be published by either maintainer (the publish step no longer needs one particular GitHub account), and from a maintainer's PC when the automatic build service is unavailable.

### Added
- **Android app on the release page:** every release now attaches the app as `Deck.apk` with its checksum, so the Phone page's "Get the Android app" QR code works. It is signed with Deck's own release key: if you installed an earlier test copy of the app, uninstall it once first (Android refuses an update signed with a different key), then pair again.

## 4.0.2 — 2026-11-10

### Added
- **Starter profiles:** a fresh install with no profiles of your own gets three editable CPU and GPU profiles once (Gaming, Everyday, Quiet), copied from the built-in modes this PC has.
- **Support report:** new parts list the makers' control and lighting apps, the firmware's ACPI devices and every HID device with its IDs and report sizes (read from Windows only, no serial numbers), so laptop fans and keyboard lighting can be added.

### Changed
- **Active changes** is now a Home tile, hidden by default: turn it on in Edit Home and place and size it like any other tile. The tray's Active changes opens the list in a window, even while the tile is hidden.
- **Fans and Lighting** no longer vanish or sit empty on PCs Deck can't control yet (most laptops): they say "not supported on this PC yet", why, and offer **Copy report**.
- **Edit Home and Customize** have a **Cancel** button next to Done: it puts back every change made since editing began (positions, sizes, which tiles show, a Reset layout).

## 4.0.0 — 2026-11-10

The biggest Deck update so far: a target-FPS power saver, a Startup optimizer, a drive speed test, crash reports and backups, per-game PC settings, sound outputs per app, display schedules, launcher actions, fan calibration and alert rules, and a long list of fixes. Everything new that changes hardware, runs in games or sends anything over the network is off until you turn it on. It also includes 3.7.5, which was never released on its own.

Not in this version: the Android app isn't attached to this release yet, so the Phone page's QR code works again once it is. Not built on purpose: anything that reads a game through RivaTuner beyond what Deck already did, a paste stack (it needs keyboard injection), HowLongToBeat, chat bots, sending alerts by email (ntfy and Discord work), translations.

### Added
- **User guide online:** a full manual for every page and setting, with recommended setups, an FAQ and troubleshooting, published with each release. Open it from Settings › About or by searching "guide" in Deck.
- **Page tours:** the first time you open a page, a few short steps light up its main parts with a sentence each (Next, Back, Skip, or Skip all tours). The ✦ button next to search plays a page's tour again; Settings › General turns first-visit tours off or starts them over.
- **Why did my FPS drop?** (Gaming > Sessions, and a game bar widget): after a stutter or dip it shows the moment ("12 s ago · 144 → 61 FPS") and the likely cause with the readings behind it: GPU power limit or heat, full video memory, one CPU thread maxed, a busy background app, heavy disk or download activity, or "No clear cause". Session reports keep their drops. It only uses readings Deck already takes, and nothing runs when no game is open.
- **Game bar, one-click essentials:** the default bar now has mic mute, overlay on/off, CPU and GPU profiles, frame limits, sound output, Free memory, volume and music. For the first three games a small hint names the shortcut that opens it (never takes focus; can be turned off). Saved custom layouts are kept: "Back to the default widgets" gets the new set.
- **Mouse lighting effects:** Static, Breathing, Colour cycle, Strobe and Off with brightness and speed, run by the mouse itself on supported Logitech mice.
- **Startup findings you can act on:** ranked by measured delay, with short advice per item and "Turn off at sign-in" for your own apps. Windows, security and driver components are marked Keep.
- **Windows:** pick an app and a snap zone and its windows open straight into that zone; "Remember windows for each set of monitors" puts your windows back when a set of monitors returns (a dock, a TV). Both off by default.
- **Network:** data used by each app (today, 7 and 30 days), connection quality over time (router and internet delay, jitter, lost replies, kept 30 days), and a "Lag while busy" test graded A to F.
- **Apps:** "Update your apps" updates the apps winget has newer versions of, one by one with a result each; before uninstalling a Visual C++, .NET or DirectX runtime Deck says which installed apps use it.
- **Tweaks:** save your tweaks to a file and open one on another PC (you tick what to apply; each keeps its Undo); after a Windows update the notice says which settings Windows put back.
- **Clipboard:** "Paste as plain text" for chosen apps puts the plain version of formatted text at the top of the history (Deck sends no keys).
- **PC to PC:** the accept card shows what is inside an offer (biggest files, types, a warning for programs); a PC without enough free space refuses up front; optional "Send to PC" in Explorer's right-click menu.
- **Sound:** choose which output each app plays on; save output profiles (default output, calls output, each app's output and volume) and apply them in one click with Undo; optional rules that switch output when a headset or dock connects or an app starts, and optional memory of each app's volume (both off by default); **Check mic for 5 seconds** shows peak, noise floor and clipping (nothing is recorded to disk).
- **Display:** a per-monitor schedule for brightness and warmth through the day, optional dimming when idle, night colour, an input switch that offers only the inputs the monitor lists, and full-screen test patterns (Esc closes). Brightness and colour go back exactly when Deck quits or after a crash; Undo puts back the input.
- **Launcher:** quicklinks (a web address with `{query}`), custom commands (a program, its arguments and a time limit) and chained actions (sound output, CPU/GPU profile, power plan, open app). Commands and chains show exactly what will run and ask the first time and after any edit.
- **Clipboard:** "Change it" previews a text item as formatted JSON, comma-separated lines, without link tracking, or with private details hidden (the original stays); "Copy text from this image" reads text from a history image; optional "Wipe codes and keys after a minute"; **snippets** with `{date}`, `{time}`, `{clipboard}` placeholders, pasted from the launcher.
- **Wake a PC:** PCs Deck has seen on your home network that are off or asleep now show a Wake button (Wake-on-LAN).
- **Processes:** a one-line "what is this" for common Windows and desktop programs.
- **Startup apps** show how many seconds an app slowed the last Windows starts, from Windows' own measurements.
- **Shut down when an app finishes its work:** waits until the app has been busy, then until it stays under a CPU percentage for the minutes you set, or closes.
- **Rest your eyes every 20 minutes** (off by default): a 20-20-20 reminder that waits while a game or video is in front.
- **Fans:** run a fan on the highest, lowest or average of two curves, or make it follow another fan; an "Ignore short spikes" preset; **quiet hours** that cap curve-driven fans at night unless the PC gets warm; **Rehearse a curve** plots what a fan would do (climb, short spike, lost sensor, cool-down) without touching the fans; **Calibrate a fan** measures its speed at each step and its stop and start points, then warns later if it turns slower than before.
- **Sensor alert rules** on any reading ("above or below X for N seconds", several tests together) that can show a notification, send a message out, flash the lights red or switch a CPU or GPU profile.
- **Notifications out:** send alerts, drive warnings, shutdown-plan warnings and "Deck closed unexpectedly" to an ntfy topic or a Discord webhook (off by default, each kind opt-in, with a test button).
- **Sensor history:** a day, a week or a month of CPU and GPU temperature, load and power. All readings now explains where each reading comes from, what it means and how fresh it is.
- **CPU:** the live panel shows what the profile asks for against the clock the CPU runs at, and names what is holding it back.
- **Lighting:** optional red flash on heat alerts or when the death counter counts a death, an optional colour per CPU/GPU profile, and OpenRGB devices can follow Deck's lighting through OpenRGB's SDK server (off by default).
- **Weekly health card** on This PC: the last seven days of temperatures, drive checks, free space, sensor alerts and crashes, with links to the details.
- **Cooler display:** optional short messages for important events (shutdown soon, timer done, downloads and PC to PC transfers finished, alerts, heat).
- **Target FPS power saver** (Gaming, per game, off by default): set a target such as 60, 90, 120 or 144 FPS, and while that game is in front Deck lowers the GPU power limit and the CPU's long-term power limit step by step as long as the game stays comfortably above the target, and raises them again when it drops below. It never goes below safe floors. The original limits come back when you leave the game, alt-tab, change a profile, the PC gets hot, Deck quits, or after a crash. It only lowers a limit the hardware actually runs into (a GPU-bound game gets a lower GPU limit; the CPU limit stays), and the page shows the FPS now next to the limits. Needs an NVIDIA GPU and RivaTuner's frame-rate reading (Deck adds nothing to the game). Tested with Unigine Heaven held at one spot, target 100 FPS: the GPU went from 240 W to 100 W while the game stayed at about 168 FPS, and closing it or switching away put back exactly 240 W and 130 W. **Simulate** shows what it would do on sample traces without touching the hardware. The game is recognised from the window in front, so RivaTuner briefly reporting another program (or a reading that is a moment late) no longer hands the limits back and starts over; the log says why each hand-back happened. It reacts within one to two seconds, starts from the limits that held the target last time for that game, may raise the GPU above its profile (up to the card's maximum) when the game needs it, and stops going lower when the frames get uneven (the slowest 1 % of the last three seconds), even if the average is fine. Optional per game: "Go below the lowest power limit" also holds the core clock lower, down to the Minimum mode "Measure this card" found. Picking a profile yourself turns Target FPS off for that game until it restarts.
- **Startup optimizer** (Clean > Startup optimizer): how long your last Windows starts took (firmware, Windows, sign-in), a history of the last ten, what slowed them down by Windows' own measurements, and advice for each cause. Safe fixes (Explorer's startup delay, Fast Startup, delayed start for optional updater services) are opt-in, each with an exact Undo and an Undo all.
- **PC settings per game:** a game can switch the fan preset, lighting effect, display mode, HDR, digital vibrance and sound output while it runs; everything goes back when it closes, when Deck quits, and after a crash.
- **Playtime:** Gaming and Home show total and weekly hours per game and the last session.
- **Session report** after a game closes: time played, highest temperatures, energy used and deaths.
- **Energy and cost:** Home and Gaming show energy used today and this month, with an optional price per kWh.
- **Profile stability log** (optional): warns when a CPU or GPU profile was active during repeated game crashes or driver resets.
- **Death counter:** text files for OBS, and attempt splits per session with the profiles and temperatures at the time.
- **Controller:** a low-battery warning over games (optional), a stick drift check with a suggested dead zone, and battery history with hours left.
- **Game bar:** new Fan preset widget.
- **Crash reports:** if Deck closes unexpectedly it saves a crash report on your PC and tells you. Nothing is sent anywhere, and crash files only join a support report if you choose.
- **Back up and restore Deck** from Settings, with optional weekly backups to a folder you choose. Secrets stay out unless you add a password, which encrypts the backup. You review a backup before restoring it, and the current settings are saved first.
- **Go back to the previous version** from Settings > About, follow **beta releases**, and see **what is new** once after each update.
- **Active changes** (tray and Home) lists everything Deck is holding right now, with a Release button for each.
- **Deck's storage** in Settings shows how much space each part of Deck uses, with a cap and a Clear button for the artwork cache.
- **Settings > Diagnostics** turns on detailed logging for one area; Deck records its own and WebView2's memory use every hour.
- A short **introduction** at the top of Settings on first run (Show introduction brings it back).
- **Drive speed test** on the Drives page: sequential and random 4K, read and write (SEQ1M Q8T1/Q1T1, RND4K Q32T1/Q1T1), with history per drive. The test file bypasses the cache and is deleted even if Deck closes mid-test.
- **Drives:** TBW life estimate, temperature history with an alert, and a verified-copy plan for drives that start failing (copies your files to another drive and checks every one).
- **Disk space:** find duplicate files (recycle them, or replace them with a hardlink; the replaced copy goes to the Recycle Bin), see what grew since the last scan, build a "make room for N GB" plan, and see what deleting a selection would really free.
- **Anti-cheat friendly:** when FACEIT is running, Deck hands the fans back to the BIOS and stops using its hardware driver, says why, and resumes when FACEIT closes. If Windows blocks the driver, Deck says so instead of showing missing fans.
- **One hardware owner per PC:** if a second Windows user also runs Deck, only one controls the fans and lights; the other says so and takes over when it quits.
- **Keep awake** lists what else is keeping the PC awake.
- **Sensors: "Slow readings during games"** (on by default) reads drive counters and idle fan chips every 3 seconds while a game is in front; manual fan curves keep their one-second timing.
- **Get the Android app by QR code:** the Phone page has a "Don't have the Android app yet?" section. Scanning its code downloads the newest app from the public release page.
- **Low delay for the phone as speaker:** a new switch plays at about 120 ms instead of 300, at any sound quality. Weak Wi-Fi may cause small gaps.
- **Test my mouse:** the Lighting page's Mouse card now always shows, with a button that tells whether Deck supports your mouse and a report to copy and send so support can be added. It only reads what Windows knows; nothing is sent to the mouse. `Deck.exe --mouse-probe` prints the same report.
- **Logitech mouse lighting:** the Lighting page gets a Mouse card, shown only when a Logitech mouse answers, with Off, a solid colour and a brightness slider. Each zone's result is shown, and G HUB or another RGB program running is noted. Deck sets it only when you press a button.
- **Ask on the PC before a phone powers it off:** a new Phone page switch (off by default). With it on, a phone's shutdown, restart, sleep, hibernate or scheduled power-off waits for Allow on a notification on the PC. No answer in 30 seconds, a closed notification, or a new phone key means it does not happen, and the phone is told it is waiting. Lock and screen off are not asked.

### Changed
- **One Settings page for everything.** Settings now has parts listed on the left (General, Appearance, Search, Games, Death counter, CPU and GPU, Desktop, Notifications, Connections, Data & recovery, About) and a **Find a setting** box. The Settings tabs of CPU, GPU, Deaths, Clipboard, PC to PC and Workspace Sync, and the loose settings on other pages (Gaming options and crash records, controller battery, phone power and upload limits, drive health warnings, Store app auto-install), moved there. Pages that are settings in themselves (Overlay, Game bar, Flyouts, Fans, Lighting) stay, linked from their part.
- **Gaming › Games, redone:** Game mode is one slim bar on top, your games are a compact list on the left (with the default profile at the top), and the picked game fills the right with its picture, figures and settings. Games without a picture show a plain gamepad instead of a broken file icon.
- **CPU and GPU charts** (CPU › Cores, GPU › Readings) have numbers on both axes, fill their panel, and can show the clock, temperature, load or power.
- **Much less text everywhere.** Every title, description and "?" help in the app was rewritten to a length budget: a setting's line says what it does in one sentence, and the detail sits behind the "?". Over 400 long passages were cut; nothing that warns about hardware or data was dropped.
- **More tabs, shorter pages:** CPU, GPU and Fans, Network, Sound and mic, Windows, Phone, Settings, Screen tools, Apps, Flyouts and the Game bar are split into tabs, and each page reopens on the tab you used last. The Games tab in Gaming is grouped into Performance, Power, While playing and PC settings.
- **Session reports** are grouped by day with length, average FPS and 1 % low, newest first with Show more.
- **Controller page:** one keyboard with all keys instead of "Keys to show" plus "More keys".
- **Sensors:** "Where these readings come from" explains each source once and is readable; rows no longer get cut off, and columns line up.
- **Drives and Network** have tidier spacing; missing values show as small hints instead of big text. The search box and buttons at the top of each page match the rest of the app.
- **Workspace Sync** when off is a short pitch with one button; the details are in a fold.
- **GPU page, easier to read:** the profile editor opens with a strip that says what each section does (Power, Speed, Memory, Fan; changed ones are highlighted, a click jumps there), shows the four sections side by side in two rows, and puts the voltage curve and fan curve full width underneath, so nothing hides far down the page. Built-in modes is one fold under Your profiles, as on the CPU page, with all eight modes in it (the four everyday ones first) instead of a second "All modes" fold inside it.
- **CPU, GPU and Startup optimizer:** the page buttons sit in a row under the title, so the top bar keeps only search, pin and close like every other page.
- Damaged saved files are kept aside and the last good copy is loaded; background workers that crash restart themselves and are listed in This PC.
- Deck checks an update's digital signature when it has one, in addition to its checksum.
- A settings file written by a newer Deck is left untouched; this version loads defaults and won't save over it.
- High-contrast themes, reduced motion and Windows' text size setting are respected.
- Clean up lists NVIDIA, AMD and DirectX shader caches separately, Steam's shader cache per game, and game crash dumps per game.
- Deck leaves a sleeping laptop NVIDIA GPU asleep and the GPU page shows "GPU asleep".
- On ARM64 Windows the hardware pages are hidden with the reason; on Windows N the music features say the Media Feature Pack is missing.
- Errors from Windows are explained in plain words with a next step.
- Tweaks refuse to turn off services that Windows Update, the Store, Defender and licensing need.
- Undo in Tweaks asks before it overwrites a setting you changed after Deck applied it.
- Shortcuts another app has taken are marked, and Deck registers them again after sleep.
- Fan control and input polling keep their timing when Windows puts Deck in Efficiency mode.
- File search says when some folders could not be read or the file limit was reached.
- The phone-controller driver message points at ViGEmBus's final release and explains its retired updater.
- The hand cursor is only on real buttons and links, not on whole rows and cards.
- The log now says what asked for each skip (media key, Deck, the phone remote, a shortcut), so an unexpected card can be traced.
- **The phone link is encrypted only and signed per request (method and query included).** This needs the matching Android app version; older apps must update, and the old browser page stops working until reloaded from the PC. The phone port no longer serves anything over plain HTTP (only a short page that moves the browser to https), pairing links are always `https://` with the PC's fingerprint, and without a certificate the phone connection doesn't start and the Phone page says why.

### Fixed
- Game pictures no longer flicker or sit empty while a page refreshes, and games Deck found by their program (such as "Roblox Game Client" or "osu!(lazer)") now get their artwork. A game with no picture shows its program's icon.
- Switching a game bar widget off no longer makes it vanish from the list and from Add; it stays in the list, dimmed, until you remove it.
- A video playing under the pointer on a video site (a muted preview) no longer shows as now playing: a browser only counts once it makes sound. The song already shown keeps showing if you mute it.
- Play time no longer shows "2 h 44.7833 min".
- A stray "null" no longer shows on the Controller page without a controller.
- The Fans page no longer says fans aren't available for a moment at start-up; hardware pages show a quiet loading line instead.
- "Test my mouse" no longer jumps to the top of the page.
- The game bar preview grows back after switching from Floating card to Full height.
- **The overlay no longer freezes or shows twice.** RivaTuner also drew it inside NVIDIA's own overlay window (the "Press Alt+Z" pop-up and its notifications), which lies over the game and only redraws now and then: a frozen copy covered the live overlay, or the two showed on top of each other, and turning the overlay off and on didn't help. Deck now keeps NVIDIA's, AMD's and Xbox Game Bar's overlay windows out of RivaTuner, as it already did for launchers. An overlay window already open when Deck updates keeps the old copy until it restarts (or the PC does).
- Home shows play time as "26 min" or "1 h 5 min" instead of "26.35 min" and "0.44 h", and the energy figures are one short line under PC readings instead of rows squeezed into the tile.
- The GPU page no longer warns that the power limit differs from the profile when the profile asks for less than the card's minimum (41% of 240 W asks for 98 W; the card runs at its lowest, 100 W).
- With a GPU profile on, Deck checked Windows' event log for driver resets every 5 seconds (a short program start each time, games included); it now looks at most every 30 seconds.
- **Deck's window could stay empty** after an update that changed the order Deck's page parts load in (a Gaming setting read before it existed). Each page's first tab is now defined in one place.
- **Installing or updating could stop with "Deck couldn't create its scheduled tasks"** on PCs where Windows elevates admins without asking (3.7.5). The check of Deck's folder asked Windows for more access to the signed-in user's token than Windows gives; it now asks only for what the check needs.
- Fans, Lighting, Drives and This PC no longer stop drawing when one of their readings is missing.
- The Clean up tab no longer makes the window stutter once a second when the Recycle Bin holds many files.
- An invalid reading (not a number) can no longer crash the game ping test, the network speed test, the GPU curve editor, the overlay's top list or fan curve sorting.
- A drive that first becomes readable already unhealthy now warns.
- **Drive health:** Deck no longer wakes sleeping hard drives to read their health; USB drive warnings wait for a second bad reading and say they may be wrong; a drive going from unknown to caution or bad now warns.
- **Sensor recording** no longer starts over at 50 MB: it moves to a new numbered file and keeps the five latest.
- A stuck Windows management query can no longer hang the machine probe; the support report names what was skipped.
- Deck follows a moved or renamed Downloads folder (PC to PC inbox, file search, clean-up).
- Two different screenshots with the same edges are no longer treated as one clipboard entry.
- Files VirusTotal had not seen are looked up again after a week.
- The calculator reads `max(1,234)` as two numbers.
- Opening a workspace puts each window of the same app in its own saved place.
- The session summary's FPS per watt only uses moments where both were measured.
- Saving Deck's files rides out a virus scanner holding the file for a moment.
- **Building from source:** running the tests no longer opens a "Windows cannot find" box with an error sound.
- **Music card when a song changes by itself:** the moment a player stops while loading the next song no longer opens a Paused card. A pause in a new song's first two seconds shows only if it holds.
- **Mouse lights can be turned back on:** after Off, the button becomes Turn on, and moving the brightness slider lights the mouse again.
- **VB-CABLE setup:** it could not start from its protected folder; Deck now starts the checked setup with its own admin rights, or says why it can't.
- **Uninstalling:** Deck no longer offers leftovers while an uninstaller that relaunched itself from Temp is still running.
- **Screen view:** a small picture on a fast connection no longer loses H.264 because the bitrate went over the encoder's limit.
- **Phone power approvals:** Allow on PC can't be reused or answer a newer request, and is refused while a phone has control of the PC. A plan's "Do now" follows the same rules.
- **Received setups and zips:** extraction counts the real unpacked size, runs without admin rights, and a snapshot's undo only restores the listed settings.
- **Uninstalling a program no longer runs a user-written uninstaller with admin rights.** An uninstaller listed only for your account, or one in a folder a normal program could change, is started as you; if it can't be started that way Deck says so instead of running it elevated.
- **A zip received with Install is unpacked without admin rights,** into a fresh folder that is kept only if it worked. Zips with too many files, too much data, paths leading outside the folder or symbolic links are refused with the reason.
- **Applying a received setup leaves Windhawk off by default** and warns that mods run as code inside other programs. Its files are copied to an admin-only folder before they are checked and used, and the result says whether mods were applied.
- **Getting VB-CABLE** unpacks and checks the setup in a folder only administrators can enter, and the signer's name must match exactly.
- **Getting VB-CABLE no longer loads PowerShell modules from your user folders** while Deck runs as administrator. It uses Windows' own PowerShell and only the system modules.
- **The built-in PawnIO driver file name can't be changed to a path,** and the file is compared in full and not written through a link.
- **Making a new phone key now stops downloads and uploads already running.** A large download kept sending, and an upload could still finish and appear in the inbox; half-sent uploads are removed too.
- **The old phone key no longer stays in plain text in settings backups.** The backup and any damaged-file copy are sealed, and if Windows can't seal a secret, settings, PC to PC, Workspace Sync and file check results are left as they were, and the phone certificate isn't made, instead of being saved in plain text.
- **Turning the phone remote off now disconnects phones already connected.** They could keep controlling the PC until they left.
- **Setups from another PC stay within what they're meant to change.** A received setup could write other registry values, including programs that start with Windows. It's now limited to its own list, and winget ids from another PC can't be read as options.
- **Workspace Sync:** a damaged settings file is set aside rather than replaced by a new key, and two more settings that can run commands now wait for approval.
- **PC to PC:** a damaged settings file or device key is kept aside rather than overwritten.
- **Failed actions now say so** across the app, rather than doing nothing, and buttons no longer stay stuck after a failure.
- **Search:** pasting thousands of brackets can't crash Deck.
- **Screen on your phone** follows a resolution change or a screen being unplugged while streaming.
- **Fans:** if the fan thread fails while Deck is closing, fans are still handed back to the BIOS.
- **Kingston Fury RGB:** a stick that stops answering is retried every 30 seconds rather than on every frame.
- **Phone page:** only http and https links open from the shared list, and messages no longer claim success when the phone wasn't connected.
- **Startup apps:** one very long entry no longer hides the ones after it.

## 3.7.0 — 2026-11-07

A safety release: fans, power actions, undo and the phone connection, checked piece by piece.

### Added
- **"Are you sure?" before power actions:** shut down, restart, sleep, hibernate and sign out now ask first, from Deck, the quick panel, search and the phone page. Plans ask when you set them, naming the action and when it runs.
- **Allow power commands from phones:** a new switch on the Phone page, on by default. Off, phones can still lock the PC and turn its screen off.
- **Upload limits:** optional limits on the Phone page for each file and for the From phone folder.
- **Display changes go back by themselves:** a new resolution, refresh rate or rotation returns to the old one unless you press Keep, even if the page closes.
- **QR codes carry the PC's certificate fingerprint:** a phone app that reads it is protected from its first connection. Older apps and the phone page ignore it.

### Changed
- **GPU fan safety:** a fixed speed or a fan curve now gives way to 100% at 85 °C or when the temperature can't be read, until the card is back at 80 °C. Zero-RPM stays as it was while the card is cool and its temperature is known.
- **Custom CPU power limits can't exceed the limits the board started with.** Existing higher values are held at that limit.
- **The PC's speakers come back sooner** after a phone stops playing: at once on Stop, and in 2 seconds rather than 5 if the phone just disappears.
- **Recall's switch now says what it does:** turning it off deletes existing snapshots, which Undo can't bring back. It moved to Advanced.
- Several tweak descriptions were corrected to say what the tweak really does, and one policy now only shows on the Windows editions it works on.

### Fixed
- **Case fans:** a fan stopped by a curve no longer stays stopped when all temperature readings disappear, and old board readings no longer count once the chip stops answering.
- **A cancelled shutdown could come back** after a restart, and a plan replaced within the same second could be mixed up with the old one.
- **Sleeping during a shutdown countdown** could shut the PC down on waking. A missed countdown is now cancelled with a notice.
- **`shutdown in 1d` and `shutdown in -1m`** were both read as 60 seconds. Search now refuses what it doesn't fully understand.
- **Game profiles:** a game ending at the wrong moment could get its profile back after closing, two games with the same file name no longer share a rule, and a crash or power cut during a game now restores the card's earlier settings. GPU changes also check they reach the same card on PCs with two.
- **Uninstall:** CPU power plans and the minimum-clock lock are now put back. Removing Deck no longer leaves a cap or floor behind with nothing guarding it.
- **Tweak undo:** a tweak now stops before changing anything if it can't save what it needs for Undo. DNS Undo covers IPv6 and still works after you change network adapter, and stopping a service is checked.
- **App removal can't preselect shared folders** or services another app owns, and a registry backup must exist before anything is deleted.
- **Clean up:** the Rust build cache only removes real build output, even when its folder setting points somewhere unusual. Installers moved to the Recycle Bin no longer count as freed space.
- **Clipboard:** exclusions are checked while holding the clipboard, unreadable markers count as excluded, and very large items are skipped.
- **Store apps:** a downloaded package is rechecked and held until it's installed.
- **PC to PC:** resuming a transfer now needs the same PC that was approved.
- **Support reports** no longer include file paths.
- **Phones:** resetting the pairing code now disconnects phones that were already connected, and upload temp files can't overwrite each other.
- **Setup:** updating from a very old per-user install no longer runs a file from that folder with admin rights.

## 3.6.4 — 2026-11-06

### Added
- **Choose which apps count as music:** Desktop > Flyouts lists the media apps Windows has right now, each with Auto, Always or Never.
- **Show music card from the tray:** see the current song without opening a page. Show uses the player's actual playing or paused state, or a labelled sample when no song is available, and respects the fullscreen setting.
- **Song end tolerance:** an Advanced control in Music allows for players that crossfade or finish early. Existing settings keep the four-second default.
- **Media keys always reach the player (off by default):** Windows gives play, next, previous and stop to the window in front first, and a frozen one keeps them. With this on, Deck sends them straight to the player. Other programs that use those keys won't get them.

### Fixed
- **The music card reacts to a skip at once.** Pressing next or previous now opens the card straight away saying "Skipping" or "Going back", and it names the song as soon as the player does.
- **Small flyouts keep their coloured icon.** Caps Lock and other small cards had a near-black circle in place of your accent colour.
- **Media keys work with Deck in front.** Play/pause, next, previous and stop stopped at Deck's window and never reached your music app.
- **Music rules match their description.** Recognised music apps need no artist or duration; other apps need an artist and at least 45 seconds, or an unknown duration. Browsers are a fallback when no qualifying non-browser session is available, including paused songs. Always and Never remain explicit overrides.
- **Launchers and apps set to Never are gone from the rest of Deck too,** including Home and the game bar.
- **Song names no longer wait for artwork.** Pictures load separately, reject late results for another song, and hold back a previous song's cover while the player updates it. Late artist metadata does not announce the same song twice.
- **Resume and playback changes requested through Deck respond without the pause debounce.** Unsolicited pauses retain the guard against a player's skip flicker.
- **Skip and song-end preferences also apply while a card is already open.** Known skips from Deck's controls take priority near the end; short read gaps advance the previous playing position, and known seeks reject a briefly stale timeline.
- **Flyout delivery and closing are ordered.** Old snapshots, acknowledgements and queued window operations cannot replace a newer opening. Display time starts after the page responds; missing later draw acknowledgements also recover the window.
- **Cards switch to native drawing when a game or fullscreen window comes forward.** Show follows the same game policy. Native fades can reverse without flashing and respect Windows animation effects and Low spec.
- **Volume controls handle captured drags, cancellation, fast writes and failures.** A short interaction lease keeps a drag alive outside the card. Master output and player volume have distinct labels; ambiguous player mixer matches are hidden. Controls target exact Windows media sessions even when apps share an identity.
- **App choices and hardware availability refresh while Flyouts is open.** Missing readings preserve their baselines, unknown battery charge is no longer shown as 100%, and unavailable previews are labelled samples. Microphone feedback says Muted or Unmuted.
- **Placement adapts to work-area, monitor and DPI changes.** Cards scale to fit small work areas, keep paired cards together, and avoid Deck notifications when room exists. Secondary text has measured contrast on supported card tints.
- **Disabled flyout workers wait for events instead of checking settings every 400 ms.** Artwork reads, media control calls and player-volume requests stay off the UI runtime's active work.

## 3.6.3 — 2026-11-05

### Fixed
- **"When a song ends and the next one starts" now holds.** A song that ended by itself could count as a skip, so the card showed with that setting off. It happened whenever another program had a media entry (Riot Client keeps a paused one), when the next song's length arrived before its name, and when the next song passed through "paused" on its way to playing.
- **A launcher is no longer taken for a song.** A media entry that only gives the program's own name, as Riot Client's does, is ignored, so it can't open the music flyout.

## 3.6.2 — 2026-11-05

### Added
- **Volume and music as one card:** "One card" under Show volume with it puts a thin volume bar under the song instead of opening a second flyout. You can drag it, scroll on the card, or click the speaker to mute. With nothing playing, volume shows by itself.
- **The player's own volume on the music flyout (off by default):** a small slider under the buttons, for just the app that's playing. It's that app's level in Windows' volume mixer, so the slider inside the app doesn't move.

### Fixed
- **Changing the position or the arrangement moves flyouts already on screen.** A card already open stayed where it was while the other went to the new place, and the two could overlap. Both now work out their places the same way, and a change takes effect at once instead of up to a second later.
- **The volume flyout changes colour when the song changes,** not at the next pause or volume change. It now follows the song while it's open.
- **Flyouts now show over games that use all of the graphics card.** They opened but stayed invisible, and only one already on screen when you tabbed in could be seen. Over a game they're now drawn without the web engine, and they don't cost frames while they're open: Warframe went from 187 to 179 fps with one up (a web card forced through cost 55 fps and caused stutter).
- **Flyouts show over Deck's own window** as they do over any other program.
- **"Show in folder" opens the right folder with the file selected.** Any path with a space opened Documents instead, which included every file received from the phone (`Downloads\From phone`). A file that has since gone opens the nearest folder still there.
- **Caps Lock and the other short flyouts** no longer sit in a place kept for the music flyout when it isn't there, and they're smaller: two short words no longer fill a wide card.
- **Boss names that animate or are thin are recognised.** Warframe's Jackal read differently each time and never opened a fight. What the reads agree on now counts, even if they aren't one after the other.
- **A fight is no longer renamed to something one bad read made up.**
- **The death counter no longer keeps a processor core busy** while a game fills the graphics card (up to 97% of one core, now about 9% typically with the same fight). The counter's own cost in frames couldn't be measured in Warframe: 171 fps with it on, 168 with it off.

### Changed
- **The volume flyout matches the music flyout:** white on the colour of the song's cover.
- **A song's picture and colour are kept for 10 minutes,** one song at a time, so the card has the right ones as soon as it opens.

## 3.6.0 — 2026-11-05

### Added
- **Flyouts (Desktop > Flyouts, all off by default):** small cards that never take the focus, for music, volume, microphone, sound device, lock keys, brightness, airplane mode and charger, each with its own time on screen. They follow what Windows reports, so a change from any key or program counts, and they stack instead of overlapping. The volume one can be dragged, scrolled and muted. Deck can also hide Windows' own volume pop-up, off by default.
- **Choose when the music flyout shows:** when you skip, when a song ends and the next one starts, or both. They're told apart by how close the song was to its end, so a skip in the last few seconds counts as ending.
- **Volume and music can open together:** one above or below the other, whichever one changed. Separate unless you ask.
- **Music flyout:** a card coloured from the cover when the song changes, however you skipped: keyboard, player, phone or controller. It opens as soon as the new name is in, about a second or less after a skip, never showing the old song as the new one, and the cover follows a moment later. It has previous, play/pause, next and seeking. It never takes the focus, and over games and fullscreen windows clicks pass through it, or choose Overlay text to put no window over the game at all. It stays out of the way during presentations, Do not disturb, and while the player or Deck is in front. In true exclusive fullscreen, where no window can be drawn, the song also appears in the Overlay if that's on.
- **Apps built on a web engine now show their real name** as the source of what's playing, instead of "Web app".

### Fixed
- **Missing artwork on Home and in the game bar:** a song whose picture arrived just after its name stayed without one until the next song.
- **A hung media player can't hold up Deck's media controls:** Windows media calls now give up after 1.5 seconds.
- **Two apps built on a web engine playing at once:** Deck's controls now reach the one that is playing, instead of whichever Windows lists first.
- **Accented letters in the in-game overlay** (é, ñ) now show instead of "?".
- **A dialog over a game could hide Deck's panel.**
- **The hot corner and other full-screen checks took the desktop for a full-screen app** on some setups.

## 3.5.2 — 2026-11-04

### Added
- **Phone remote:** app icons for the mixer (`/appicon`, only for apps playing sound now), a picture sent from the phone can also go on the PC's clipboard, the state carries the PC's Tailscale address so a phone remembers it before leaving home, and its memory in GB.

### Fixed
- **Phone remote:** a media player that's slow to answer no longer stops the phone's live state until it does. Actions run on the side, and one that takes over 5 s says so.

## 3.5.1 — 2026-11-04

### Changed
- **The Xbox pad in the controller overlay is redrawn:** a cleaner shape, a dark plate between the bumpers with a light on it and a lit Xbox button, soft rings round the controls, a chunky d-pad, A, B, X and Y ringed in their own colours, and taller triggers. On the white theme the sticks and d-pad sit in dark collars.
- **You can see which way a stick is pushed:** a bright arc on the ring round the stick points the way it's going, the knob shows a lit dot, and the knob travels further on the Xbox and DualSense pads. At rest none of it shows.
- **The PlayStation pads are tidied up:** the sticks are a little smaller, and the D-pad and face buttons have more room.

### Fixed
- **Overlaps in the controller overlay:** the DS4's stick rings ran off the shell, sat off-centre on their sticks and crowded the D-pad and face buttons; the DualSense's light bars touched the touchpad and the square button nearly touched a light bar; its bumper tips floated off the shell; the PS button now lines up with the sticks.

## 3.5.0 — 2026-11-03

### Added
- **Handheld gaming PCs:** Deck recognises the ROG Ally, Legion Go, MSI Claw, Steam Deck, AYANEO, OneXPlayer, Zotac Zone and GPD Win, and This PC says what works there. On any touchscreen, buttons that only appeared under the mouse are always shown, and small buttons, switches and "?" are easier to tap. The power limit (TDP) and fan modes of the makers' own apps aren't in Deck yet.
- **The support report says more about what went wrong:** how the previous run ended (quit cleanly, closed by an update, or ended without quitting, with what the watchdog recorded), which background jobs crashed or stopped, and this run's problems by area with the first and the latest ones, before the log's last lines.
- **This PC says what Deck can do on this machine:** the processor and its generation, each graphics adapter (built-in or card), the laptop's maker, and in plain words what works, what partly works and what isn't in Deck yet. The support report carries the details, including which maker controls the laptop has, so support for more machines can be added.

### Changed
- **Charts have their own colours:** CPU and download are blue, GPU and upload magenta, memory cyan and VRAM violet, the same on Home, Sensors, Network and the CPU and GPU pages. The GPU no longer shares the "all good" green, nor VRAM the warning amber, and download is no longer a different colour on each page.
- **Chips read normally:** game names, profile names and other labels in chips keep their own capitals instead of being shown in small capitals ("GPU: AB Profile 5", not "GPU AB PROFILE 5").
- **Status colours follow the theme:** green, amber and red tints on chips, warnings and hints use the theme's own status colours, so they match in Graphite and Nord.
- **The clock on Home** keeps your timers and "Staying awake" when the tile is short (the calendar goes first), and centres what's left.
- **Opacity fades one layer.** The panel's background is the only thing that fades; buttons, switches, readings and text stay solid, instead of each item having its own see-through background on top of another.
- **The core clock and the other speed settings are a panel on the CPU page**, not a fold you had to find.
- **Folds stand out:** "Advanced" and the other folds are bordered bars with a bold title and an arrow, everywhere (also on the footer pages and Tweaks' "More presets").
- **"Back to GPU" and "Back to CPU" are real buttons**, and the close button shows the same in every mode.
- **The death counter's "+N more deaths" opens 10 at a time.**
- **Games without a death profile start with the death counter off** until you turn it on, count a death or teach a screen.
- **Pages say each thing once and line up:** Deaths shows this session's numbers in a card like the records under it; the Overlay page's reading groups are small labels under the list's heading; Controller's keys say "16 of 27 shown" once and its Test tab names the battery; Lighting's preview no longer repeats the effect's description; Disk space no longer repeats the drive's size and free space under the summary; the Startup apps panel says what its switch does instead of the app's name again; every card heading is the same colour, with or without an icon; Phone's folds open with the same arrow as everywhere else.
- **The GPU editor's half-width panels** keep each setting's name and "?" on one line, with the slider under them.
- **Long names** in Processes end with "…" (the full name is in the panel), the "End app" button no longer repeats the app's name, and a long profile name on CPU and GPU stops at two lines.
- **Help for Lighting's effect and game sound and the cooler display's colour speed**, like the other hardware settings.
- **"Jump to" on Windows and Screen tools** stops with the section's heading in view, not under the top edge.
- **Missing readings on Drives** ("Not reported") are small grey text, not a large number split over two lines.
- **Display's picture sliders line up** whatever value each one shows.
- **Tune's tools** (icon picker, existing plans, Afterburner import, card measuring) open under the panel you used, not at the top of the page.

### Fixed
- **Deck cut off in the bottom right corner with Windows animations off.** With "Animation effects" turned off in Windows (Settings > Accessibility > Visual effects), the quick panel opened with its corner in the middle of the screen and ran off the edge. It's centred again.
- **Problems that used to leave no trace are logged:** a background job whose loop ends, the fan chip or the GPU fan curve failing and working again, a fan curve left without a temperature (handed to the BIOS meanwhile), a page that couldn't load or draw, and errors in the game bar and snap-zones windows. Repeats are counted instead of written each time.
- **A crash hands the fans and the GPU back before anything is written to the log.**
- **A page whose data can't be read no longer says "Loading…" forever.** CPU, GPU, Fans, Lighting, Cooler display, Sensors and the other pages say what went wrong and offer Try again; a page that still draws (Deaths, PC to PC and others) shows the same message above it instead of looking empty or switched off. Drives no longer blames admin rights when reading the drives failed.
- **Closing the GPU editor after "Try it"** tells you if the card couldn't be put back, instead of leaving the tested settings on quietly.
- **The GPU editor no longer reads the card every second while Deck is hidden** (say, while you play).
- **"chrome is open"** on Clean up reads "Chrome is open"; the Processes panel says "File not scanned yet" instead of "Not checked yet"; Cooler display no longer shows a lone "–" under the preview when no display is connected.
- **Scrolling a readings table no longer jumps back to the top.** Sensors' readings and the other pages with live numbers (CPU, GPU, Fans, Overlay) keep each inner list where you scrolled it when the numbers update.
- **Clicks on the game bar, Deck or a notification no longer reach the game** in games that read the mouse directly (osu! and many shooters): while you point at them they take the focus, and the game gets it back when you move away. "Keep clicks off the game" on the Game bar page turns this off.
- **"Move controller overlay" in the game bar** closes the bar so you can move it.
- **Frosted glass in the game bar** shows the game blurred behind it again, instead of grey or black.
- **Switches overlapping their labels** in settings rows.
- **The overlay drawn several times over** in the League of Legends client and other launchers (Steam, Epic, Battle.net, EA app, Ubisoft Connect, GOG Galaxy, Xbox app, Overwolf and more): RivaTuner leaves them alone. Restart a client that was already open.
- **Games in folders with letters outside English** (é, ü, Arabic, Chinese...) weren't found from Windows' list of games or installed programs.
- **The game bar and notifications on laptops with screen scaling** are put back if Windows moves them as they appear, as Deck's panel already was.
- **The page no longer jumps** when a sheet or editor closes and hands the focus back.
- **A dropdown kept its glow** after you picked from it with the mouse.
- **Background jobs restart after an error.** If one of Deck's watchers crashes (closing Deck over a game, the hot corner, Gaming, Power's timers and plans, saving settings, the overlay's readings, the game bar's controller combo and others), it starts again by itself after a few seconds, instead of stopping until Deck restarts.
- **A damaged data file is kept, not overwritten.** If the death counter's game list, notes or taught screens, the play-time history, the GPU's measured curves or Afterburner's imported data can't be read, Deck sets the file aside and logs it instead of starting empty and saving over it. The measured curves are also saved safely now, so a crash mid-save can't cut them off.
- **This PC no longer waits forever on a PC whose WMI is broken:** the machine check gives WMI 8 seconds.
- **The hot corner with several monitors** only opens Deck at an outer corner of the desktop, not where the mouse passes from one monitor to the next.
- **A pinned Deck whose monitor was unplugged** comes back on the monitor the mouse is on instead of off-screen.
- **AMD processors:** the CPU page no longer offers Intel's power limits there (they did nothing); Saver and Performance still set Windows' power mode.
- **Windows installed on another drive:** Epic and Riot games, and Windhawk in PC to PC, are found where Windows keeps them, not only on C:.
- **Network's game list** was cut off at the bottom, and its "relay servers" note was shown twice.
- **Small screens:** the Game bar page stacks its preview under the settings sooner, and the overlay's preset cards and long process names stay inside their boxes.

## 3.3.1 — 2026-11-02

### Changed
- **The game bar never scrolls.** When its widgets are taller than the screen, its text gets smaller until they fit. The preview on Play > Game bar is now a small copy of your screen, so it shows exactly how the bar will fit, and it no longer scrolls on its own: the page has one scroll, and changing a setting no longer makes it jump.
- **Opacity fades only the backgrounds.** Below 100 % the screen behind shows through Deck's surfaces (frosted), while text, colours and readings stay at full strength; before, the whole panel faded and looked washed out.
- **Clearer PC sound on the phone.** The sound is fitted to the phone's rate with a smooth curve instead of straight lines between samples, which dulled the highs, and Auto picks uncompressed sound from 3 Mb/s (it was 8).
- **Fewer cut-outs with the phone as the speaker.** Without pictures to keep in step with, it uses the phone's playback mode and a bigger cushion.

### Added
- **Phone as speaker with the screen off.** "Screen can turn off" in the phone's Speaker and mic card: the phone may sleep while it plays, like a music app, with controls on the lock screen.

### Fixed
- **Deck stuck open over a game.** Opened over a game it never had the focus, so clicking elsewhere didn't close it; now a click outside Deck or switching to another program does.
- **Recording a keyboard shortcut over a game.** "Press the keys" now asks for the keyboard, so the keys arrive. This also lets you set the game bar's key, which is what opens it in games played with mouse and keyboard.
- **The game bar's size at other text sizes.** Below 100 % the bar ran past the bottom of the screen and hid its hint line; above, it stopped short. A floating card now also grows when a widget is added while it's open.
- **Deck opening in the bottom right corner on some laptops.** When Windows changes the window's size as it appears (a screen with other scaling), Deck puts it back.
- **Workspace Sync "peer no longer has that chunk".** Browser caches and WebView profiles inside a project (`EBWebView`, `GPUCache`, `Code Cache` and the like) aren't synced any more; each PC makes its own. A file that keeps changing while it's copied is tried again at the next sync instead of marking the sync as having problems.
- **Sidebar labels.** A hint such as "No limits" next to Tune uses the free space instead of being cut at a fixed width.

## 3.3.0 — 2026-11-02

### Added
- **Game bar: a panel over your game for quick switches.** Turn it on in Play > Game bar (it's off until you do), then hold Select + Start on the controller (or L3 + R3, or Select + L3), press your own key, use the tray menu or tap Game bar in the phone remote. The game stays in front: the bar doesn't take the focus, so games don't minimise or tab out. Use it with the controller (it opens with its first button picked; D-pad or stick to move, A to press, B to close, LB/RB to jump) or the mouse; a click outside closes it.
  - **Death counter without leaving the game:** +1 death, undo ("that wasn't a death"), and for the current fight Won, Not a boss and Gave up, each with "Undo that fix"; "Teach in Deck" opens the death counter's Games page.
  - **Controls:** one-press tiles for the controller overlay, moving the controller overlay, the death counter, the readings overlay, your mic, Boost, the frame limiter and keeping the PC awake.
  - **Controller overlay:** show or hide it, move and resize it, controller or keyboard and mouse, size and opacity.
  - **More widgets:** Now playing, Volume, Microphone, Sound output, Readings (FPS, temperatures, loads, memory, power, clock speed), Frame limit, Profiles (pick which CPU and GPU profiles appear) and Clock.
  - **Make it yours:** add, hide, remove and reorder widgets (drag them or use the arrows), one of each; set each one's width (1 to 3 columns), size and title and what it shows. Full-height panel or floating card (top, middle or bottom), left or right, width, columns, text size, frosted glass (Windows blurs the game behind it), opacity and accent; the combo and how long to hold it, a shortcut, closing by itself, and an option to take the keyboard. All with a live preview: click a widget in it to edit it.
- **Edit phone layouts in Deck.** Phone → Keyboard layouts has Edit and New layout: the layout opens on a drawing of the phone held sideways, where you drag buttons to move them, drag a corner to size them, and set their keys, kind, colour, size and opacity on the side. Undo, Cancel and Save are on top; saving sends it to every connected phone.
- **Move the phone controller's sticks and buttons.** Phone → Controller layout opens the on-screen controller on the same drawing: drag any stick, button or the d-pad where your thumbs want it and size it. Every phone uses it when held sideways; "Put every part back" undoes it all.
- **See the themes before you pick one.** Settings opens with Appearance: every theme is drawn as a small Deck window in its own colours, and each accent shows its name.
- **Turn speakers and mics on or off.** The Sound and mic page has an on/off list for playback devices and for microphones, the same as Windows' Enable and Disable. Devices that are off stay in the list so you can turn them back on, and the page says how many are off.
- **A new icon for Deck:** a deck of cards seen from the side, green cards under a blue top card, with no background tile. It's in the taskbar, the tray, the Start menu, the setup, the phone remote, the sidebar and the corner pop-ups. After updating, Deck asks Windows once to refresh its icon cache, so pinned and Start menu icons change too.

### Changed
- **Disk space looks and works more like a file explorer.** The folder list, the file types and the map sit in one panel. One click on the map selects that file or folder and opens the folders above it in the list, scrolled to it; a bar under the list shows its path and size with Show in Explorer, Open and Recycle. Double-click opens a folder or shows a file. The map draws sharper, with shaded tiles, folder names with their sizes, and outlines for what you point at and what is picked.
- **Sliders and colours apply while you drag.** Controller overlay size and opacity, the death counter's size and opacity, mic level and boost, vibrance, brightness, contrast and monitor settings, and the overlay's margins, zoom, opacity, graph sizes and colours change as you move them instead of when you let go.
- **The phone QR code is bigger** and sits centred with its caption under it.
- **Panels can fit their content.** While arranging a page, "Fit every panel" makes every panel as tall as what's in it and closes the gaps, and a panel you've resized has a Fit button on its bar. A fitted panel keeps fitting as its content changes.
- **The sidebar title** shows Deck's icon next to a cleaner "Deck".
- **The phone remote has Deck's look:** the same colours, fonts and icon, section titles with each group's colour, squarer buttons and sliders, and bigger readings. The fonts come from Deck, so the page still works without the internet.

### Fixed
- **Opening Deck over a game no longer tabs you out.** When a game is in front, the shortcut opens Deck without taking the focus, so the game doesn't minimise; click a text box when you want to type. The shortcut again, the close button or a click outside closes it.
- **The Start menu shows the new icon.** After this update Deck asks the Start menu to read its shortcuts again, so the old icon there goes too.
- **Media keys work while Deck is in front.** Play/pause, next, previous and the volume keys reached Deck's window and stopped there; they now go to your music app as usual.
- Colour swatches and theme previews that set their colours through style variables showed no colour (this also kept the fan icon spinning at one speed).
- **Editing a panel no longer jumps the page.** Opening an editor, saving, rearranging Home and live redraws all keep your scroll position, on Home and every page with panels. Choose PC readings now opens in its own panel instead of at the top of Home.

## 3.2.2 — 2026-11-02

Death counter fixes from a friend's Phantom Blade Zero run, a download button for the OCR pack, and new controller shapes.

### Added
- **OCR pack: a Download button, progress and a confirmation.** Turning the OCR toggle on shows a Download button with its size. The download shows a progress bar with how much is done, then "Downloaded. The OCR pack is on.". If it fails, the page says so and offers Try again.
- **Controller overlay: real DualSense and Xbox Series shapes.** A PlayStation 5 pad is drawn as a DualSense, with its wide touchpad, light bar and mute light. An Xbox pad has its own body, a round d-pad, the Xbox button with its logo, and shoulders and triggers in the right places. A DualShock 4 still gets the DualShock 4 shape. The shapes are lit from above, so buttons look domed instead of flat.

### Fixed
- **The death counter's pill shows in every game Deck has a profile for,** even before a death is counted.
- **A boss bar outside a fight no longer starts one.** A fight needs a coloured bar and, in games with a boss list, a name from that list. Scenes that only look like a boss bar stopped showing "Fighting" and a "0/1" count.
- **A beaten boss counts as a kill straight away,** when its bar empties and stays empty. Before, it waited about two minutes for the game's phase timer. If the boss comes back, the kill is taken back.
- **Boss names from the game's list only.** A garbled read is no longer kept as a boss name in a game that has a list.
- **Bars that jump around** (Elden Ring, Dark Souls 1, Sekiro, Lies of P) open their fights more often. No kill that was counted before is lost.

Phantom Blade Zero's death counter, fixed.

### Fixed
- **Phantom Blade Zero: deaths weren't counted** unless the optional OCR pack was on. The place Deck looked for "DEAD" was too small for the word in English and German.
- **Phantom Blade Zero: the Iron Fiend and Jade Dancer fight wasn't seen.** Deck now finds the two bars side by side, follows the fight when one of them falls, and counts it as one fight with one win. Their names and the Chief Disciple's second phase are on its boss list.

## 3.2.0 — 2026-11-01

The death counter rebuilt, and installing Deck made simple.

### Changed
- **Installing, updating and removing Deck are one short flow in one window.** The setup says what it will do and has one button: Install, Update, Reinstall or Replace. Installing over an existing Deck updates it in place, with no "uninstall first?" page and no "Deck is running" box. Updates from inside Deck stay hidden, and the file-in-use errors are gone
- **Uninstalling leaves nothing behind:** tasks, shortcuts, firewall rules, the PawnIO driver if Deck installed it, logs and browser data all go. A tick box also deletes your settings, profiles and death history
- **Death counter, games Deck doesn't know:** they aren't watched until you count a death in one, mark something on its page or pick "Every game", since not every game has anything to count
- **Death counter, how it decides:** a game's own words in the place it shows them count at once, and the common words need two reads. It's ready again as soon as the banner has gone, so games that restart fast don't lose deaths
- **Death counter, boss fights:** a fight opens from the bar, even before its name can be read ("Unnamed boss"). A bar that empties shows "Defeated?" and the win is written after 2 minutes, or at once on a victory banner. Another boss arriving in that time is the same fight's next phase, so Radagon and the Elden Beast are one fight
- **Death counter, revives:** in a boss fight, a revive (Sekiro) no longer counts as a death. Deck sees the same boss's bar still dropping after the death screen and takes the count back. Only the real death counts
- **Death counter, boss names:** a read close to a name on the game's boss list takes that name. A boss that isn't on the list, such as a modded one, is still detected from its bar and name

### Added
- **Built-in game profiles:** where the boss bar, boss name, player UI and death screen are for a list of soulslikes, including Dark Souls 1 to 3, Sekiro, Elden Ring, Nightreign, Lies of P, Phantom Blade Zero and Black Myth: Wukong, worked out from gameplay footage. Parts that couldn't be confirmed are left out. None of this has been checked in the real games yet. Black Myth: Wukong shows a different quote at each death and only three are known, so some deaths there need counting by hand
- **Set up a game:** a card for each game with its steps (your own bars and items, the boss's bar and name, the death screen, the kill screen). Each is optional and shows what Deck reads in the box you draw. Bosses with two bars (health and posture) are handled
- **A popup for a death Deck reads in a game it's still learning.** It takes no focus, and left alone the death stays counted. It offers "Not a death" and "Set up this game"
- **Fights to check:** the History tab lists recent fights Deck wasn't sure of, each one click to settle
- **OCR pack (optional):** Settings on the Deaths page can download about 24 MB of better text reading. It reads more boss names, and Sekiro's death screen, which Windows' own reading can't. Lies of P's death screen still needs teaching once. It stays through updates, and turning it off or uninstalling Deck removes it
- **Screen shapes:** built-in positions follow the game's window on ultrawide and 16:10 screens
- **Daily backups** of each game's death history, kept for 14 days, and a "Leave this line out" fix in History that deletes nothing

### Fixed
- **Game detection:** osu! and osu! lazer count as games, and so does a game in a borderless window that nothing listed, when its own folder shows it's a game: Unity, Unreal, Godot, a game store's or anti-cheat's files
- **Playing now:** a game stays "Playing now" while you alt-tab or look at Deck, and Game mode starts by itself even if you switch away right after launching. It no longer says "Playing now" after a game closed while Game mode stayed on
- **Gaming:** game names sit on a soft fade over the cover instead of a dark box

### Added
- **Death counter:** death screens in Spanish, French, German, Italian, Portuguese and Polish are read with no setup

## 3.1.1 — 2026-10-31

### Changed
- **Downloads and updates** come from a new public home, [deck-releases](https://github.com/MohammadFakih02/deck-releases): updates, the shared death-screen library, and bug, idea and death-screen reports all go there. The source code is now private. A copy older than this one won't find updates by itself, so install this version once from there
- **Publishing:** releases reach the public repo through `tools/publish-release.py`
- **Local installs:** a release setup can now replace a copy installed with `install.ps1`

## 3.1.0 — 2026-10-30

Fixes from a full review of the new look, page by page.

### Added
- **Your own scrollbars, switches, tick boxes and sliders:** Deck draws them itself now, in the same cut-corner shape, and the scrollbar takes each page's colour
- **Xbox controller shape:** the controller overlay draws an Xbox pad as well as a DualShock, and the new "Match my controller" choice picks by the name of the one connected
- **Lighting preview:** six fans, each with its LED ring and spinning blades, running the chosen effect with its colour and speed, with a start and stop button
- **Sound and mic:** playback devices and microphones sit side by side, each with Collapse and Expand

### Changed
- **Help "?":** opens as a small panel beside the button, so it never moves the page or gets cut off
- **Rows:** a row with a name is clickable all over (running apps, installed apps, startup apps, folders), and names start at the left
- **Home:** the game panel sits on top, with its art, time played and sessions, and shows a death counter only for games that have one; Power & timers keeps its options
- **Gaming:** game status and last session sit beside the games, and wide pictures show whole
- **Disk space:** a picked drive gets the whole page until you go back, with folders above a larger space map
- **Apps:** buttons stay in the same place on every row and in the side panel; rows keep space at their edges
- **Store apps and updates:** panels run the page's full width and the page scrolls. Each update is one line with its Wait for Install, and the reason a check failed opens on request
- **Clean up:** one page that scrolls, with the total and its buttons staying at the top
- **Scrollbars:** the page's scrollbar is on the window's edge and a list's scrollbar is on its panel's edge. Processes, Apps to close and Built-in apps scroll with the page
- **Overlay:** "Start from a preset" comes first
- **Phone:** connection beside the features, with a smaller QR code next to its instructions
- **PC to PC settings:** panels fill two columns without gaps
- **Controller preview:** shows the overlay's real picture
- **Tweaks, Sensors:** panels use the window's height instead of a fixed one
- **Buttons:** a row with a main button keeps all its buttons the same height

### Fixed
- **Which programs are games:** Deck now also goes by the list of games Windows keeps itself and the catalogue of games with bosses, so osu!, Need for Speed and others count, windowed or not. Launchers, crash reporters, installers and programs without a window no longer count, and neither do apps that just cover the screen while the graphics card is busy. A new **Not a game** button on Home takes a program off (Gaming lists them to take back), Add game still adds one by hand, and old false entries are hidden
- **Sound on Home showed no apps:** one row too many hid them all. A short panel now gives up one app at a time, and the game in front and whatever you've just heard come first
- **Games with anti-cheat:** Windows refuses to open them, so they were missing from the sound lists and from game detection. Deck now finds them another way
- **Store updates:** the list wasn't compared with what's installed, so an app already updated stayed listed and trying it again failed. An app Microsoft has no package for no longer reads as a busy server, a stopped check no longer says every app is up to date, and apps that couldn't be checked show their name instead of a code
- **Clean up:** "is open" follows the app closing without measuring again
- **Clipboard:** the hint bar no longer covers the end of the list
- **Wrong game pictures:** a loose picture search could show another game's art
- **Rows on top of each other** in long lists: Clipboard, PC to PC and Phone
- **Sensors:** CPU and GPU showed no temperature in the list, and tables showed a broken degree sign
- **Temperature choice in Settings** showed "?C" and "?F"
- **Scrolling** jumped back up on pages that redraw while a help panel was open
- **Switching dark and light:** the button answers at once and repeated presses no longer freeze the PC
- **Mute** shows at once instead of up to a second later
- **Blue boxes** around the search bar and after mouse clicks
- **This PC** table header, the Store's Updates heading and an orphaned "?" on GPU modes

## 3.0.0 — 2026-10-30

Deck 3.0 is a new look for the whole app: a new menu, every page redesigned, new fonts and motion. Every feature from 2.9 is still there. More UI fixes follow in 3.0.x updates.

### Changed
- **A new menu:** seven groups (Home, Play, Tune, Watch, Desktop, Clean, Power) with a live hint beside each (Live while a game runs, your CPU profile, your next timer), and each group's pages as tabs above the page. Arrow keys move through both. Your saved order, hidden pages and panel customisation are kept.
- **Motion:** menus and dropdowns grow out of the button that opened them, buttons, tabs and chips respond when pressed, and help panels and folds ease in when you open them. Page switches stay instant. With Windows' reduced motion on, only fades remain.
- **Easier to read and use:** text on coloured fills (the calendar's today, badges, active icons) and the calendar's other-month days have more contrast in every theme; disabled controls are clearer; buttons no longer touch; long names end in "…" with the full name on hover, and long text no longer pushes past its card.
- **Power and footer pages:** Keep awake separates durations and event watching; Timers places the stopwatch and break reminders below a wider timer form. Shutdown plans use compact selectors and a sticky action bar. PC to PC gains recipient cards, grouped apps and Activity with received items and logs. Workspace Sync puts incoming review first. Phone uses compact columns and inline setup. Settings has General, Search and About; profile preferences, Home tiles and clipboard settings link to their own pages. Larger reviews and the first-start look picker open inline.
- **Clean pages:** clearer cleanup selection and inline review, a compact disk map and folder tables, attention-first installed apps, paired built-in app panels, and Store updates beside app search. Startup separates its list from launch details. Tweaks gains a review/presets/undo overview, current-value controls and inline Advanced reviews. Existing cleanup, uninstall, download, startup and Windows settings remain available.
- **Desktop pages:** Windows gains compact snap-zone controls and inline workspace actions beside its open-window list. Display pairs monitor controls and shows Keep/Go back inside the affected monitor. Sound and mic uses horizontal volume rows and paired mic cards. Clipboard gains type tabs, an inspector, search scope and its own Settings tab; the old Settings location links there. Screen tools groups colour actions, locked files and Windows shortcuts. Existing controls remain available.
- **Watch pages:** Sensors gains a device rail, reading tables, individual graphs and paired alert/logging settings with clearer draft and retry controls. Processes puts app details and actions beside the lists, with inline file checks. Network pairs connection/speed and game servers above ping; revealing the public IP removes the Hidden label. Drives uses warning-first health cards, and This PC separates hardware capabilities from support reports. Existing controls remain available.
- **Tune pages:** CPU and GPU place the applied profile beside measured readings and use inline profile editors. Fans gains live speed tiles and a full-width curve. Lighting groups zones beside effects with inline colour editing; cooler display separates preview, content, colour and night settings, with reading-list menus. Existing tuning, shortcuts and hardware controls remain available.
- **Play pages:** Gaming gains artwork cards, an applied-profile panel and paired profile settings. Overlay uses five tabs with colours in Look and graph controls beneath Frametime. Controller has a compact preview, battery summary and clearer live input panels. Deaths moves learned screens to Games and opens boss sharing, merging, recognition rules and count reset inline. Existing actions and settings remain available.
- **Home dashboard:** running or last-game artwork, current profile and frame-limit chips, and death counts with +1/Undo. PC readings sit above paired power, performance and utility panels. Edit Home keeps existing arrangements and adds a complete tile list; PC settings, pinned-app actions and layout reset open inline.
- **Page frame and notifications:** compact search beside page titles, wide Home search with Edit Home, separate page tabs and section links, and scroll-edge fades. Help opens inside its panel. Notifications and snap zones use the shared fonts, theme colours and compact corners; saved navigation order and panel customisation remain available.
- **Shared visual theme:** offline display and body fonts, compact rounded controls, frosted panels, quieter separators and group-coloured headings, tabs and sidebar markers across all eight themes. Accent choices still colour controls. Buttons keep their labels whole and narrow label/value rows wrap more reliably.
- **Consistent dropdowns and menus:** solid theme-coloured lists replace native select popups throughout the main window and dialogs, with arrow-key navigation, Enter, Escape, focus return and placement inside the window. Profile mode groups remain collapsible.
- **Faster, steadier checks for contributors:** the Rust tests are 158 instead of 730 (merged by topic; hand-run hardware probes and tests that depended on how fast the machine is removed) and run in about 4 s instead of 14. The automated UI tests were removed; the UI is checked by screenshots and measurements.
- **Faster local builds:** `install.ps1` now builds with a new `local` profile (optimised, incremental): after a change Deck rebuilds in about a minute instead of about six. The published setup is built as before.
- **Faster releases:** a release no longer runs the tests again (it checks that CI passed for that commit) and reuses dependencies compiled ahead on `main`; the release build uses 16 code generation units instead of 4.

### Removed
- **The MoboCtl import** (the one-time settings import and driver hand-over from MoboCtl): MoboCtl no longer exists. Nothing else changes for hardware control.

### Fixed
- A profile picker opened from a button partly out of view could reach past the bottom of the window; its list now always stays inside.
- **Home's Performance tile** said "Make a CPU or GPU profile" after Deck started, until you opened the CPU page. It now loads your profiles itself.
- **The GPU page could stay hidden** after Deck started (and from Tune's tabs) when the page missed the "hardware ready" signal. Deck now asks again until the hardware is ready.
- **Network › Game servers** cut off each server's latency ("50 ms · 20% l…") behind a sideways scrollbar.
- **Home tile headers** no longer push their link (Details, Timers, Processes) under the title in narrow tiles.
- **Startup apps:** an administrator-only app's label read "On ? Administrator needed"; it now reads "On · admin only".

## 2.9.67 — 2026-10-28

### Added
- **Shut down when… is fully adjustable.** Every condition has Options: the speed under which traffic counts as quiet, how long an untouched unfinished file or Steam download counts as paused, extra folders to watch, CPU / GPU / disk limits, how long an app must stay closed, whether a controller or playing media counts as being at the PC, the length of the warning (or none), keeping the PC awake while it waits, waiting while you play, and closing apps that hold a shutdown up. Your choices are remembered.
- **New conditions:** the graphics card goes idle (GPU renders, video exports) and the disk goes quiet (installs, unpacking). **Then wait until the PC is idle** after a download or an app closing, for a download that installs or unpacks afterwards.
- **Keep awake until downloads finish:** how long after the last download it ends, and the speed under which nothing counts as downloading, are now settings.

### Fixed
- **Shut down when downloads finish never fired on some PCs.** Steam leaves folders in `steamapps\downloading` after a paused, cancelled or uninstalled update, and Deck took any of them for a running download, all night. Now a Steam download counts only when Steam says the game is updating and something was written lately; an unfinished browser file only while it is still being written (a paused download or an old .tmp no longer blocks it).
- **Plans are more careful and more reliable.** A plan now keeps the PC awake while it waits (Windows' sleep timer stopped the download and the plan); the warning is called off when the download resumes, the app opens again or you come back; it waits while a fullscreen game or video is in use and gives a fresh warning after; "An app closes" waits for the app to have run and stay closed (it fired at once before); "The network goes quiet" counts uploads, as it said; speeds and CPU are averaged so one spike or dip doesn't decide; "I've been away" counts a controller and no longer fires at once after 49.7 days of uptime; a plan survives Deck updating overnight, and one from before a Windows restart or sign-in is dropped instead of acting on the PC just turned on; "Do it now" can't run a plan that was replaced. Plans are now in the log (set, cancelled, met, waiting).

## 2.9.6 — 2026-10-28

### Added
- **Frame rate limit (Gaming): your monitors' own refresh rates** are in the list, each with a step just under it (3 FPS less, for G-Sync / FreeSync), e.g. "240 FPS · your monitor" and "237 FPS · just under your monitor"; with more than one monitor each is named.
- **Hide modes / Show modes**: a small eye button on the right of the CPU and GPU pages' Modes header folds all the built-in modes away and brings them back; each page remembers it.
- **The built-in modes sit behind one "Modes" row in profile lists** (Apply a profile at start, Plugged in / On battery, each game's GPU and CPU profile in Gaming): a click opens it, and it is already open when a mode is the one picked. The tray's CPU and GPU profile menus have a Modes submenu.
- **Low power and Lowest power (GPU modes)**, below Saver, for lighter games, video and the desktop. Low power keeps Saver's memory speed and holds the core at 60 % of Saver's speed; Lowest power also drops the memory to its low step (810 MHz on RTX 30 cards), with the core at about three quarters of Saver's. Both use fewer watts than Saver, but also give fewer frames per watt: Saver's core is already at its lowest voltage. On an RTX 3080 in Warframe at Ultra settings, 810 MHz memory gave 43 fps at 69 W.
- **Minimum (GPU mode)** for light games like League of Legends: the memory at its very lowest step (405 MHz on RTX 30 cards), where the driver also holds the core low (420 MHz at most on an RTX 3080; the mode shows the speed the driver allows). On an RTX 3080 in League, 134-160 fps for 37-39 W, against 375 fps at 94 W in Normal and 272 fps at 57 W in Lowest power. Heavier games drop to a few frames in it.
- **Measure this card (GPU page, next to Modes).** In about a minute Deck finds where your card is most efficient: for full speed memory and for Saver's memory speed, the lowest voltage the card really runs at under load and the fastest speed it keeps there. Efficient and Saver then use those speeds instead of estimates from the driver's table. The card is put at stock while it measures and is never set faster than stock; your profile goes back on afterwards, and a game coming to the front stops it. It also measures the modes below Saver under a game-like load: Low power gets the slowest speed that keeps 85 % of Saver's work per watt, Lowest power and Minimum the fastest speed their memory can keep busy, so each card gets its own speeds instead of fixed shares of Saver's. It takes about three minutes and needs nothing extra: only the graphics driver and Windows' own Direct3D. The result is kept per card and driver (measure again after a driver update), and each mode says whether its speed was measured or estimated.
- **Efficient (GPU mode).** The memory stays at full speed and the core is held at the fastest speed it reaches at its lowest voltage, worked out from the card's own table. The most frames per watt at full memory speed: on an RTX 3070 in FurMark, 154 fps at 146 W against 126 fps at 257 W stock; an RTX 3080 in Warframe, 149 fps at 148 W.

### Fixed
- **Switching GPU profiles in a game no longer resets the graphics driver.** While a profile changed, the old speed lock came off before the new memory speed was on: going from Lowest power to a 100 W profile with a +265 MHz offset let an RTX 3080 boost for a moment with the offset at speeds it isn't stable at, and the game crashed ("Windows has restarted your GPU driver"). Deck now holds the core at a safe 1050 MHz during a switch and sets the power limit, curve and memory before it lets go. Note: an overclock offset that is only safe under a low power limit can still reset the driver in light games, where the limit doesn't hold the core back; give such a profile a highest speed.
- **The GPU modes fit their cards.** Seven or more modes in one row left each card too narrow (names cut off, labels sticking out); they now wrap into rows.
- **A page opens at its top.** Going to another page kept the last page's scroll position, so a short page could open scrolled down with its buttons out of view.
- **Efficient and Saver on cards whose driver table is off.** On an RTX 3080 the table pointed Efficient at 1545 MHz and Saver at 1095 MHz, while the card really runs 1365 / 1350 MHz at its lowest voltage. In Warframe 1350 MHz gave 10 % more frames per watt than 1545 (0.85 against 0.78 fps per watt). Measuring the card fixes both.
- **Saver no longer drops the power limit to the card's lowest.** On an RTX 3080 the lowest limit (100 W) left about 40 W for the core once the memory had its share, and the core fell to 450 MHz: 62 fps at 102 W in Warframe, fewer frames per watt than Normal. The lower speeds already do the saving, so Saver keeps the card's own limit (a card whose speeds can't be locked still gets the lowest limit). Saver's memory speed is now the one clearly below full speed that still feeds games (5001 MHz on RTX 30 cards), also where it doesn't lower the core's voltage: in Warframe it gave 0.93 fps per watt on an RTX 3080 against 0.85 at full memory, at the same core speed.
- **A GPU curve profile without a speed lock no longer reports "Core clock lock: invalid value".** The undervolt cap mistook the flat bottom of the card's own curve for an undervolt and asked for a lock below the lowest speed the card allows.
- **GPU undervolt curves stay undervolted.** A curve that holds one speed from a low voltage up (Afterburner style) tilted upwards as the card warmed, and the card climbed to over 1 V for a few MHz: on an RTX 3070, 930 MHz at 1031 mV and 72 W. Deck now also caps the speed where such a curve turns flat, and moves the cap as the card warms or cools: 870 MHz at 750 mV and 49 W on the same card.
- **A GPU profile stays on when Deck restarts** (after an update or a crash restart). Quitting gave its speed and memory locks back to the driver, and Deck went on showing the profile as on while the card ran without them; it is now applied again.
- **GPU profile switches no longer mix or undo each other.** Two switches at once (a shortcut key held down) each rewrote the whole curve, and the check for a driver reset could put the previous profile back a moment after you picked another one.
- **Saver (GPU) keeps games playable.** It held the memory at its 810 MHz step, which cut fps to about a fifth. It now uses the card's most efficient speeds, worked out from the driver's own table: a memory speed that still feeds games but lets the core run at a lower voltage (5001 MHz on an RTX 30 card), and the fastest core speed at that voltage. **Ultra saver is gone** (memory and core at their lowest: about a twelfth of the fps).

## 2.9.5 — 2026-10-27

### New
- **Gaming** (was Game boost): a **profile for each game**, switched on when the game starts and back when it closes. Each game can have its own **graphics card** mode or profile, **processor and power plan** (a CPU profile, or Windows' fastest plan), **frame rate limit**, **game priority** and what frees up the PC (**close apps**, **background apps** at lower priority, **free memory** off / when low / on, **pause Deck's downloads**); anything not set follows the **Default profile**. Laid out like a game library: your games on the left with their artwork, the picked game on the right with its figures and settings, each change saved at once (and applied at once when the game is running).
- **Your games are found by themselves**: Steam, Epic, Riot (League of Legends, VALORANT, Teamfight Tactics, …), and games from EA, Battle.net, Ubisoft, GOG, Rockstar and other publishers; others once you play them with Deck running, or add one by its program. The list is kept, so it shows at once, and rechecked in the background; an uninstalled game drops off.
- **Game artwork for every game**: Steam's and Epic's own, then PCGamingWiki's official covers, the Steam store, GOG's catalogue and Wikipedia, without any account or key. Pictures of the wrong shape are framed, not cropped.
- **Frame rate limit per game**: kept by the **NVIDIA driver** itself (the Control Panel's Max Frame Rate: it works even when Deck isn't running and nothing hooks into the game), or in **RivaTuner**'s profile for the game on other graphics cards.
- **Game priority**: the game gets the processor and the graphics card before other programs while it runs (Windows' own priority settings, any graphics card), put back after.
- **Session figures**: each session's time, average FPS, 1% low, GPU watts, **FPS per watt** and highest temperatures, per game and under Sessions.
- **Built-in CPU modes** on the CPU page: **Performance**, **Balanced**, **Quiet**, **Saver** and **Ultra saver**, the same on every PC, usable everywhere a profile is (tray, phone, Gaming, plugged in / on battery). Copy one to make your own.
- **The GPU page's live readings** sit on the right like the CPU page's: the core clock with its history, temperature, load, power **against the power limit in force** (and whether that limit is what holds the card back), memory, fan, voltage and video memory.
- **Controller overlay: a position for each game** (optional): Move / resize while a game is running keeps that place and size for that game only.
- **Free memory now** on Gaming → Apps to close does the full clean (every program's idle memory and the cache, as Clear RAM does), separate from closing apps.
- **Built-in GPU modes** on the GPU page: **Fastest**, **Normal**, **Quiet**, **Saver** and **Ultra saver**, worked out by Deck from your card's own limits and speeds (Fastest uses whatever headroom the card has: its highest power limit and/or temperature limit; a mode that would come out the same as another on a card is left out, so a card that allows no changes has only Normal). One click puts a mode on the card, and modes work everywhere a profile does: the tray, the phone, a shortcut key, desktop and Start menu shortcuts, Gaming and "Apply a profile at start". Their settings can't be changed (another card gets its own); **Copy to my profiles** in a mode's ⋯ menu makes an editable copy. Your own and Afterburner's profiles are under **Your profiles**.
- **A new GPU profile editor**: four blocks, **Power**, **Speed**, **Memory** and **Fan**, each setting with a plain name, its technical name under it (power target, core clock lock, memory clock offset…), a dot when it differs from the card's own and a reset. **Start from** fills a new profile with a mode's settings. A banner says whether the profile is safe or an overclock, and the first overclock is explained once (Cancel takes it back). **On the card now** shows watts, speed, memory speed, temperature, fan and load every second, and after **Try it** what the card does with the profile. The header is one row (icon, name, shortcut key); desktop and Start menu shortcuts are under More (also in the CPU editor).
- **Lower speeds in GPU profiles** (NVIDIA): **Highest speed** and **Memory speed** (Card decides, Full, Half, Low, Lowest) use NVIDIA's clock locks (what `nvidia-smi -lgc` and `-lmc` do), so the card can use less than the lowest power limit its driver accepts (100 W on an RTX 3080). The memory runs only at the speeds its firmware has (on an RTX 3080: 405, 810, 5001 and 9251/9501 MHz); a memory offset moves only the top steps (on an RTX 3080 down to 8501 MHz), so the editor shows it only there, with the speed it gives, and says so at the other steps. Fan choices: Card decides, Quiet, Cool, Fixed or your own curve. The Speed block says the fastest the card will run and which setting decides it; on the voltage curve, Highest speed is a red line the curve can't be drawn or dragged above (editing trims it there; Undo takes that back), and when Highest speed is below the whole curve the graph makes way for a note with "Turn off Highest speed" and "Drop the curve". A grey area shows where the curve can't go (NVIDIA lets each point move at most 1000 MHz from stock, so at high voltages it can't go below about 1000 MHz), and a point at that limit says so. When Highest speed is so low that no offset, curve or voltage boost can change anything (for example at the card's lowest speed), those are hidden behind a note that says why, with Clear them and Turn off Highest speed. The curve's Hold / Shift inputs moved behind **Curve tools** and say they only reshape the curve. Locks are let go when Deck quits, on Back to stock (also locks set by nvidia-smi), and after a crash. Every NVIDIA card gets the locks its generation supports: the core lock on GTX 16 / RTX 20 and newer, the memory lock on RTX 30 and newer; the speeds offered are the card's own.
- **Sound is now Sound and mic**: every microphone with its level, mute, **boost** (when the driver has one), **which mic apps and games use and which calls use**, a **Test** that makes its meter move (records for up to a minute, keeps nothing) and **Hear it on the speakers** (Windows' "Listen to this device"). Playback and recording devices can be **renamed**.
- **Virtual display** (Phone page, optional, not installed unless you ask): a screen made by a free, signed driver (Virtual Display Driver 25.7.23), so the phone's Screen view and remote desktop still show something with the monitor unplugged or a laptop's lid closed. Off, **When no monitor is connected** (turns on by itself and off again when a monitor comes back) or Always. Deck checks the download's checksum and signature before installing, and Uninstall removes the device and the driver.
- **More monitor settings** (Display page, per monitor): the monitor's own settings over DDC/CI, what its menu changes: **sharpness**, **colour preset**, **red / green / blue gain**, **speaker volume** and **input** (it asks before switching away from this PC), only those the monitor lists, with its own choices. On NVIDIA cards also **digital vibrance** (the Control Panel's colour saturation, 50-100 %).
- **Cancel for long jobs**: Deck's own update download, installing RustDesk, the virtual display and VB-CABLE, Clean up (measuring and cleaning) and the Store update check stop at their next safe point and say so. A step Windows already runs (an installer) finishes.

### Fixed
- **Store updates:** App Installer (and other apps whose Store bundle is numbered differently from the app inside it) is no longer offered as an update to the version already installed: Deck reads the version inside the bundle. Deck asks Microsoft's update service as a normal PC, not an Insider one.
- **Phone screen:** switching between H.264 and JPEG stays on the screen you picked (it went back to screen 1); turning Control off no longer clicks the PC (which paused a video); a picture that went grey and smeared mends itself within 5 seconds (was up to 30).
- **Virtual display:** switching it on or off shows the result at once (it took up to 10 seconds), and a switch Deck makes by itself shows on the card too.
- **Windows page:** a window's transparency keeps showing its real value after Deck is hidden and shown, and closed windows leave the list by themselves.
- **CPU profile editor:** Clock floor, Overclock turbo and Hold the cap in games are under Advanced (it opens by itself when one of them is set).
- **Mode cards** (CPU and GPU) sit on one row with their whole text.
- **The CPU profile editor keeps its place.** Changing a setting (dragging the power limit sliders, the power limit buttons, Turbo boost) scrolled the page back up; the page now stays where it is, and the slider keeps the keyboard focus.
- **Dialogs no longer close when you select text with the mouse** and let go outside the dialog (the profile editors, rename and confirm boxes): only a click that starts and ends on the dark background closes one.
- A stray **"null"** no longer shows under Gaming's Full power button (when "Turn on by itself" is off) or under its memory bar, in Home's media tile for a stream with no length, or on the Phone page's remote desktop card.
- **Fans:** "follows ?" stays on one line next to the sensor it follows.
- **Processes:** in a small window the Network column fits (its header and the upload/download figures were cut off), and memory figures no longer wrap onto two lines.
- **GPU:** the memory clock tile no longer cuts its value off ("10,501 M…") in a small window.
- **Tweaks:** the category tiles show how many settings changed under the name instead of squeezing it.
- **Death counter → Settings:** the "Not bosses" list (and "Ignored in" / "Same boss in") put the names under the text; the text was squeezed to one word per line.
- **Processes → Network:** speeds in the units chosen in Settings, like the Network page, rounded (small speeds showed long decimals such as 341.3333333 B/s).

## 2.9.0 — 2026-10-26

### New
- **Tweaks: 54 more, in 19 categories under three headings** (Clean up, Look & feel, How it works). New categories: **App permissions**, **Ads & suggestions**, **Browsers**, **Desktop**, **Keyboard & mouse** and **Performance**; long ones (File Explorer, Taskbar, Right-click menu, Desktop) have sub-headings. New, Winaero Tweaker style: hide right-click entries (Open in Terminal, Cast to Device, Restore previous versions, Scan with Microsoft Defender, Troubleshoot compatibility, Ask Copilot, Edit in Notepad, Edit with Photos, Add to Favorites); desktop icons (This PC, your user folder, Network, Control Panel, Recycle Bin); full-quality JPG wallpapers; Windows version on the desktop; no " - Shortcut" on new shortcuts; thumbnails or icons; Office.com files in Home; side pane shows all folders / follows the open folder; folder windows in their own process; reopen folders at sign-in; colour for compressed files; copy window with details; no "Look for an app in the Store"; Show desktop corner, badges and flashing on the taskbar; shake to minimise; menu delay; Toggle Keys and Filter Keys shortcuts; key repeat delay; scroll the window under the pointer; start-up apps without the 10-second wait; power throttling; automatic maintenance; restart after a blue screen; error reports; the improvement program; online tips in Settings; device makers' installers; the drag tray; Modern Standby or classic sleep. **Windows Update, as in Winaero Tweaker**: automatic updates by themselves, download and ask before installing, ask before downloading, or **Off: only when you check** (Windows' own policy: nothing is checked, downloaded or installed by itself, "Check for updates" still works, and the service stays on so Store apps, drivers and optional features keep working); stay on a Windows version (24H2, 25H2); wait 7–30 days before monthly updates and 3–12 months before a new Windows version (Pro); a warning before update restarts; updates for other Microsoft products; downloads on metered connections; skip the Malicious Software Removal Tool. Two more presets: **Debloat** and **File Explorer power user** (checklists, as before).
- **Game boost turns on by itself when a game starts** (Game boost → "Turn on by itself", off unless you turn it on): once a game has been in front for a few seconds. Turned off by hand during a game, it leaves that game alone until the game has been closed for a couple of minutes. When Full power is off and a game runs, the page says "Deck sees <game>" and the button turns it on for that game.
- **Game boost pauses Deck's own downloads** while Full power is on (on by default) and carries them on afterwards, so a Store download doesn't take the game's bandwidth.
- **Recent sessions** on the Game boost page: which game, how long, how many apps were closed and how much memory was freed, and whether it turned on by itself.
- **Network column in Processes**: upload and download per program, sortable (needs Deck running as administrator; it reads Windows' own network events, nothing is sent anywhere).
- **The Windows page is one page** with its three parts (open windows, snap zones, workspaces) and **arrangements**: side by side, columns, grid, main + side, cascade, focus, centre and minimise all, for the windows you tick. Each window shows its size, position, monitor, process id and memory, with a Maximise button.
- **More display controls** (Desktop → Display): resolution (a changed one goes back by itself after 15 seconds unless you keep it), scale, orientation, contrast (monitors that support it), and **Turn screens off**.
- **Game servers: many more games and a list that works with them**: search, pin your games to the top, the first 12 then "Show all", New World and Lost Ark (Amazon's own servers), "any game on Amazon servers" (24 regions) and "any game on Valve's network", and **Add a game** with the network it plays on.
- **Keyboard overlay: every key** (Controller → Keys): F-keys, the number row, punctuation, Enter, Backspace and the arrows, with **All keys**, **Starting set** and **None**.
- **Store apps: an app you already have says so in search** (Installed), with **Check for update**, **Update** and **Uninstall** for that one app. **Pause all** / **Resume all** for downloads, an **Install** button on a downloaded update, **Install when downloaded** (on: as before; off: updates wait for Install) and per app **Wait for Install** to keep one app from installing by itself.
- **Startup apps lists Store apps** (WhatsApp, Spotify from the Store, Teams and others), with the same switch as the rest.
- **Help on the Apps page**: the ? tips explain Uninstall, Advanced uninstall, what an app needs, Store apps and updates.
- **An on-screen keyboard on the phone's controller page.** Tap the keyboard button in its top bar: full keyboard, a small gaming set (WASD, mouse buttons, a mouse pad, scroll), and buttons of your own: any key or combo (Ctrl+Shift+Esc), mouse buttons, a trackpad area, scrolling, typed text and macros ("ctrl+c, wait 200, ctrl+v"). Each button holds while touched, fires once, or stays on until pressed again. Edit mode: drag to move, drag the corner to resize, remove (one by one or in Remove mode), duplicate, undo, add whole sets. Size and opacity are per layout. Layouts are kept on the PC (Phone page → Keyboard layouts, where they can be renamed, deleted, copied to another PC and imported) and can be tied to a game: when it comes to the front the phone shows its layout. Keys are paused while a game is in front unless "Allow keys in games" is on: when a game comes to the front, whatever the phone holds is let go at once and a macro that is playing stops. The phone sends everything it holds, whole and twice a second; the PC lets go of every key when it stops hearing from the phone.
- **"That wasn't a death" in the death counter's History**, with **Undo that**. A death taken back this way is struck out and marked "not counted" instead of deleted, and every count, boss card and stat leaves it out; "Count it again" or "Undo that" brings it back. "−1 death" (the button, your shortcut, the controller combo) still means exactly what it always did: it takes back the latest death that still counts, and skips one you already struck out. Old histories count exactly as before.
- **A boss name you give is never changed by the screen.** Renaming a fight (or tapping **Yes, that's it** on a name read off the screen, shown with "?") makes the name yours: the screen keeps following the boss's bar but stops voting on its name, right away and after a restart. Renames from before this version keep their precedence too. Names read off the screen and not confirmed show "?".
- **Fix a past boss fight from its line in History** (its menu): **Rename this fight** (that fight only), **I won that fight** / **I didn't win**, **That wasn't a boss fight**, **Add a missed death here**, and **Why is this here?** on every line, which says where the line came from as the history wrote it down (your shortcut, your controller, the death screen you taught, the save file, the boss's health), and says so when an old line didn't record it. **Same boss as…** on a boss card now makes a name rule instead of rewriting lines: the names read stay in the history, and the rule can be removed. **Not a boss** keeps the fight's deaths for the game and can also ignore that name in this game from now on, offered (ticked) only when the name read can't be one of your real bosses there. Every fix is a new line in the history, nothing is deleted, and **Undo that** takes back the last one; this game's ignored names and name rules are listed in Settings with Remove.

- **Keep a text log for testing** (Deaths → Settings, off unless you turn it on): while Deck watches a game, it writes down what it read and what it made of it, as text: where a boss bar was and how full, the words read next to it (each of the three ways it reads them, with where each line was) and in the middle of the screen, and each decision. Never a picture. It stays on this PC (`%LOCALAPPDATA%\Deck\deaths-recordings`), at most 20 MB a game, nothing is sent anywhere, and **Delete it** removes it. It lets a change to boss detection be replayed and scored on real play before it ships.

### Fixed
- **Locked files finds what holds a file or folder.** It only asked Windows' Restart Manager, which misses programs that just have a folder open or run from it; it now also looks through every open file handle (as Process Explorer does) and says for each program whether it **has it open** or **runs from here**.
- **File and folder pickers open in front of Deck**, not behind it (Deck stays on top; it now steps back while a Windows dialog is open, also for Share to phone and Save as).
- **Long lists keep their place when the page refreshes.** The clipboard history (now drawn 120 items at a time with "Show more") jumped back to the selected item on every refresh, and the Tools page jumped back to its section; any page that redraws now keeps the scroll of its inner lists, and a section is scrolled to once per visit.
- **The death counter never loses or overwrites a game's history.** A line Deck can't read (edited by hand, cut off by a crash, or written by a newer Deck) was dropped the next time a death was saved, and so was any field Deck didn't know; a history that couldn't be read at that moment (locked by another program, or not plain text) counted as empty, and the next death saved a one-line file over it. Now every line and field Deck doesn't understand stays exactly as it was, and lines Deck didn't change are written back byte for byte. A history that can't be read is left alone: new deaths are kept in `<game>.jsonl.pending` and added once it can be read. Before a history is replaced, Deck checks that it is still the file it last wrote and keeps the old one (`.bak` from the start of the session, `.prev` from before the last save); if something else changed it, nothing is overwritten and the Deaths page asks which version to keep. Deck never deletes these copies. The Deaths page says when a history couldn't be read or saved, and what was kept where. Deck 2.8.4 and older still drop lines they can't read: going back to one of them can lose what a newer Deck wrote (the copies stay).
- **The Store update check gives the same answer every time.** Microsoft's update service is a pool of servers and many of them have an old catalog, so the same question is answered with the newest version of an app or with the one before it (Raw Image Extension 2.5.42 or 2.5.35, HEVC Video Extensions 2.4.151 or 2.4.110), whatever the host name, connection or cookie. The Store catalog is as old as those servers and has no download links. Deck now asks several times and keeps the newest version listed (8 answers for an app updated in the last 120 days, 4 for the rest when the first answer shows no update), and remembers the newest version it has seen for each app (Deck\store\seen.json, forgotten after a month) so an update seen once stays on offer when a later check only reaches old servers. Installing an update asks again until the version seen before is listed.
- PC to PC → Settings → **Let Claude Code use PC to PC** told Claude Code to run Deck from the old per-user folder, where Deck no longer is. It now names `C:\Program Files\Deck`, and a skill already installed is updated when PC to PC starts.

### Changed
- **A false boss can no longer feed itself.** A name read off the screen opened a fight on a single read when it looked like a boss already in the history (60% of its letters in order), and every name the screen had ever read counted, including menu and item lines taken for a boss once ("Deep Shadow Pauldrons"). Now only names you gave or confirmed count (a fight you started, renamed, confirmed with **Yes, that's it** or named from History, and your **Same boss as** rules), not ones only the screen read nor renames from before Deck recorded who made them, and a read must be that name or a letter off: "Margit's Shackle" isn't Margit, and "aldii" isn't taken as "Xaldin" on one read. Every other name is read twice the same before a fight opens, as names new to a game always were. Nothing in the history changes.
- **Each line of a death counter history has an id** (`"id":"e12"`), given once in the order of the file and never changed, so a fix can point at exactly that line. Existing histories get theirs at the first save, after a copy of the file as it was is kept for good (`<game>.jsonl.pre-ids.bak`); no count or stat changes. "Delete this line" now deletes the line by its id, so it can't hit another line if the history changed since it was shown.
- The docs are fewer and match the code again: the contributor rules are in `DECK.md` §0 (no separate CONTRIBUTING.md), the trust boundaries are part of `SECURITY.md`, each feature's design and plan are one file in `docs/design/`, and the audits are one `docs/audits.md`.
- Three commands nothing in Deck used any more are gone (the old games list, and the hardware report and lights test that the support report now covers).

## 2.8.4 — 2026-10-23

### New
- **Tick the apps to update** (Maintenance → Apps → Store apps & updates): every update has a checkbox (all ticked to start with), with "N of M ticked", **Tick all** / **Untick all**, and the update button becomes "Update N selected here". The Microsoft Store's own "Update all" can't skip apps, so Deck asks before using it while some are unticked and names them.

### Fixed
- **Store "updates" that were only another version number are gone.** Microsoft lists many apps a second time under a different kind of number (Windows Terminal 3001.24.12741.0 for the 1.24.12741.0 you have, Calculator 2021.2607 for 11.2607, Snipping Tool 2022.2608.41 for 11.2608.41), and Deck took the highest number. Those are the same build and are no longer offered. One listed under another numbering but with a clearly higher build part (Realtek Audio Control 1.52.357 → 2.54.397) is still shown, flagged "Different version numbering", and not ticked.
- **A Store update that Windows refuses now says why.** "A prerequisite for an install could not be satisfied" (0x80073CFD) told nothing; Deck now reads the package's own list of needs and names what this PC lacks (a driver, a framework package, or a newer Windows), and says the app on this PC is unchanged. Example: Realtek Audio Control 2.54.397 needs the driver Realtek-RealtekRS5HSA.inf, which this PC doesn't have.
- **Leftover downloads are removed.** Downloads of updates that were dropped, never installed or can never install stay in Deck's store folder for good (1.1 GB of them on one PC). Deck now removes the folders nothing needs after every check and after "Clear finished", and a package Windows refuses for a missing driver or newer Windows is deleted right away, since "Try again" could never work.
- **The right build of an app is followed.** One Store listing holds packages for several Windows versions under different numbering (Calculator 11.x for Windows 11, 2021.x for Windows 10; Realtek 1.5x and 2.5x), and Deck took the highest number. It now follows the numbering of the installed app (Realtek's update is 1.54.396, not 2.54.397, which needs a driver this PC lacks), versions are compared as four numbers ("1.0" equals "1.0.0.0"), and an app installed twice is checked once.
- **No download for a version that isn't newer.** Microsoft's update service sometimes answers with an older list than a moment before (the newest version missing). Before downloading, Deck checks that the version is really newer than the installed one, asks again a few times if not, and otherwise stops with a clear message instead of downloading the same version.
- **The Store catalog lookup is retried too**, and its errors no longer show the whole web address. A Store listing with no package of its own is counted as not checkable, not as a failure, and the failure note lists each different reason.
- **Faster checks:** the list of installed packages is read once per check instead of once per app.
- **"N apps couldn't be checked … status code 500".** Microsoft's update service sometimes answers a server error or turns requests away when it is busy; Deck gave up on the first one. Now each request is tried up to 4 times with waits in between, Deck asks four apps at a time instead of six and reuses its session cookie, and the apps still turned away are asked about once more, one at a time, at the end ("Asking again for N apps…"). If some still fail, the note names them, says what the error means and that Deck already tried several times, and has a **Try those again** button.

## 2.8.3 — 2026-10-23

### Fixed
- **Death counter: menus, prompts and item banners are no longer taken for bosses** (seen in Dark Souls II: "Inventory", "Rest at bonfire", "Pick an item", "Shop", item pick-up banners, an overlay's "10ms"). Text beside a bar that starts with a button's picture read as a letter, a clipped prompt, letters read one by one, an overlay reading (ms, fps, MB…) or a menu word is not a name, and a name Deck hasn't seen before must be read twice in a row before a fight opens on it, so a banner that changes or goes away opens nothing.
- **Death counter: deaths whose banner fades in over a moving scene are read.** Deck only read the screen once the picture had settled, which a slow death fade over a still-moving, darkening scene never does, so some deaths were never counted. A sudden dimming now makes Deck read the screen about every 0.7 s for the next 6 seconds, settled or not.

## 2.8.2 — 2026-10-22

### New
- **Check a file** (System → Processes → *Check a file…*): pick any file and run the same four checks as the Safety column (signature, AV engines, Defender, VirusTotal with your key) once, privately. The file's path, fingerprints and results are kept in memory only and forgotten when the window closes; the file itself never leaves the PC, and the online checks ask by fingerprint.
- **Processes are grouped like Task Manager**: *Apps* (programs with a window) and *Background processes*, with counts. A program with several processes has a chevron that opens each one (PID, CPU, memory) with its own **End**, which says whether Windows ended it. This replaces the "Apps with windows only" switch.

### Changed
- **Leftover search is more careful.** A folder found only by its name is offered but not ticked when it holds 3000 or more files (browser profiles, caches, game data), or, in data folders like AppData and ProgramData, 5 or more programs. A name that sits inside another installed program's longer name ("Foo" for "Foo Pro") is not ticked either, and the row says which program.
- The Processes table keeps the program name readable in a narrow window.
- **More programs can be checked.** Protected services (csrss, lsass, MsMpEng, the "System" process and others) used to show "—" in the Safety column because Deck couldn't read their file; Deck now asks Windows the way Task Manager does, (asking by process id, which needs no access to the process and also works without administrator rights), so every program has a file to check. The kernel's own processes (System, Registry, Memory Compression, System Idle Process, Secure System) have no file; they are checked through the kernel file they run from (`ntoskrnl.exe`, `securekernel.exe`), and their rows say so. That shows whether the kernel file is genuine and unchanged; a file check can't see malware that exists only in kernel memory. The checks bar still says how many programs can't be checked, and hovering it names them. It now counts **files** ("Check all 86 files") and says why that is fewer than the programs listed ("89 programs listed: 4 kernel parts share 1 kernel file"), and the Signatures result line names the unsigned programs and the ones whose signature doesn't hold.

### Fixed
- A cancelled or refused uninstall no longer leaves the "Deck was closed during the advanced uninstall" warning on the Apps page.
- The do-nothing stand-in used to repair a broken Windows Installer uninstall is never put inside Windows' own folders.
- Game Boost no longer picks a browser Windows has registered (a portable one missing from Deck's list) as the running game.
- A tweak that failed partway puts back the part of the failing step that had already changed, not only the earlier steps.
- The all-programs file check says "Nothing to check" when no file can be read.

## 2.8.1 — 2026-10-22

### New
- **Safety checks for running programs** (System → Processes). Each check is optional and runs for every program at once; the results sit side by side in a new **Safety** column:
  - **Signatures**: who signed each program (Windows' own check), or **Unsigned**, or **Bad signature** when the file changed after it was signed.
  - **AV engines**: the share of antivirus engines that flag the file, from Team Cymru's Malware Hash Registry. Free, no key, about a second for everything.
  - **Defender**: Microsoft Defender scans each program file. Nothing is removed or changed.
  - **VirusTotal** (optional, with your own free API key): detections like "0/72", 4 files per request (16 a minute on a free key), the riskiest programs first; click a result for the full report. Dropped connections are retried; files looked up before are skipped.
  - Only a file's fingerprint leaves the PC, never the file. Results are kept per file and checked again only when the file changes.
  - **Sort by risk**: click the Safety header (Defender threats first, then detections, broken signatures, unsigned).
- **Death counter: "Watch in"** (Death counter → settings). By default the screen is only watched in games Deck knows how to read: games on its list, games with death screens taught or shared, and games you've counted a death in yourself. "Every game" brings back the old behaviour.

### Changed
- **Every uninstall now looks for leftovers** (Maintenance → Apps), not only Advanced: afterwards you get the list of what's left and pick what to keep and what to delete, or a box saying nothing was left. Deck comes back to the front when the uninstaller finishes, and the result stays on screen until you close it.
- **Windows Installer uninstalls say what really happened.** Deck keeps Windows' full log and explains failures in plain words (cancelled, already gone, another install running, needs admin, the installer package missing, the exact error from the log). When another install is still running it says so instead of starting.
- **Broken Windows Installer uninstalls repair themselves where possible**: when a program's folder was deleted earlier and its uninstall needs a file that was in it (error 1721/1722), Deck puts a do-nothing stand-in there, lets Windows finish, and removes the stand-in. A stuck Windows Installer service (error 1601) is restarted once.

### Fixed
- **Leftover search could tick a publisher's whole folder** (for example a shared "Autodesk" folder holding other products) when an app recorded that folder as its install folder. A publisher's name never counts as one app's name now, and a recorded install folder is ticked only when it carries the app's name or holds its uninstaller (an add-on installed into a game's folder no longer offers the game). Folders in Documents are never ticked. The leftover list is wider and long paths wrap.
- **The death counter showed up over fullscreen videos in browsers it didn't know** (Waterfox and others): every browser Windows has registered is now left alone, plus more browsers, players and apps (LibreWolf, Floorp, Zen, Thorium, Stremio, Kodi, Plex, Spotify, Discord and others). This also keeps Game boost from treating them as games.

## 2.8.0 — 2026-10-22

Everything in 2.7.9 (below), plus:

### Added
- **The death counter finds boss fights by itself** (Deaths → Settings → Find boss fights by themselves, with screen watching on): when a boss's health bar comes up, Deck reads the boss's name next to it and opens that boss's fight, times the try from when the bar showed up, ends it at a death, and counts a win when the bar empties and goes away (or a victory banner shows). Bosses with phases or cutscenes stay one try. For a game whose bar sits somewhere unusual, show Deck the bar and the name once on a picture. Names you mark "Not a boss" are left alone.

### Changed
- **Deck's own updates show a progress bar** (Settings → About → Updates): how far the download is, in percent and MB.
- **The overlay key shows the overlay at once**, also in busy games (Helldivers 2): RivaTuner's own "show" switch is now flipped the moment the key is pressed, for 64-bit games first, instead of after Deck's next sensor read.
- **Deck's log says much more**, so a problem can be found from the log alone: failed web requests and programs, failed buttons and page errors, profile switches, updates, the phone remote's connections and refusals, share links, Game boost, Clean up, display and startup-app changes, the hardware engine starting and handing the fans back, controllers coming and going, and the death counter's watching. Passwords, keys and tokens are masked, your user name is taken out of paths and the PC's name out of every line, and a line that keeps repeating is counted instead of filling the log. The support report now includes the last 80 lines. For even more detail, put an empty file named `debug` in `%LOCALAPPDATA%\Deck\logs`.

### Fixed
- Settings → Updates: pressing **Check now** while an update was downloading or installing brought the **Install** button back as if nothing had started. Check now now leaves a running install alone.
- **Apps → Advanced uninstall** could offer one of your own folders as a leftover: when a program recorded Documents, Desktop, Downloads or a whole drive as its install folder, that folder was offered, ticked. Your own folders (also when moved to another drive), and anything that holds one, are never offered or removed now. A folder named after the app in Documents (often your own work, like a notes vault) and an install folder right on a drive (`D:\Games`) are still listed, but unticked.
- Phone remote: a phone becoming a controller held up the other phones' connections for up to 2 seconds while Windows numbered it.
- Transfer's own log (`log.txt`) grew without limit; it now keeps two files of 2 MB.
- The death counter could keep Windows' text reader busy for minutes at a time, reading bars that aren't a boss's (a flickering HUD bar, an enemy's bar that moves with it) over and over. After a bar with no name, the next one is read only after a short wait, and a real boss's fight still starts from when its bar showed up.
- The death counter no longer takes a game's own messages for a boss ("Bot Drop Detected" in Helldivers 2), drops names made of reader noise ("Ei.atL1"), and takes a stray accent out of a name ("Mutatéd" becomes "Mutated").
- Deaths → Now: the big numbers sat in black boxes. The page is laid out again: the game, its fight and both counters in one card, the session's numbers in a card like Records, and the session's deadliest boss no longer looks like the all-time one.
- Every overlay key press logged "the 32-bit helper couldn't set RivaTuner's switch" although it had: the helper's "changed it" answer was read as a failure.

### Changed (performance)
- The controller overlay checks for a controller 4 times a second instead of 20 while it is hidden and none is connected.
- The in-game overlay's loop sleeps until it is woken, instead of checking 40 times a second whether something changed.

## 2.7.9 — 2026-10-21

### Added
- **Apps** (Maintenance → Apps): everything installed on the PC, with search, sorting by name, size or date, and Desktop / Store filters.
  - **Uninstall** runs the app's own uninstaller and waits until it has really finished (also uninstallers that copy themselves to Temp first).
  - **Advanced** uninstall: the uninstaller first, then a search for what the app left behind: its folders (Program Files, ProgramData, AppData, Documents), its registry settings, Start menu and desktop shortcuts, and Windows services that run from its folder. You tick what goes; folders go to the Recycle Bin, and registry keys and services are saved to a .reg backup first. Only names that match the app exactly are offered, and nothing another installed app uses.
  - Apps whose uninstaller is missing can still have their entry and leftovers removed.
  - **Apps missing from Windows' list** (known to Windows Installer, but their entry was removed by a cleanup tool or a half-finished uninstall) are listed too and uninstall normally; apps whose folder is gone are marked **Files gone**. A **Needs attention** filter shows just these.
  - Built-in apps and Store apps moved here from Tweaks (tabs **Built-in apps** and **Store apps & updates**).
- **Store app updates** (Apps → Store apps & updates): checks every Store app against Microsoft's servers and lists the ones with a newer version and its size. **Update** downloads and installs it without the Store; **Update all here** goes one app at a time; **Update all with the Microsoft Store** asks the Store to do it. Each app shows its progress (size, speed, time left), can be stopped and carried on later from where it stopped, and has its download links to copy. The list and the downloads survive Deck closing or crashing. Apps that couldn't be checked, and why, are listed instead of being counted as up to date.
- **Phone as a controller without the screen** (phone remote → Screen → Use as a controller): just the controller, on its own connection, so a press reaches the PC with the least delay; the round trip is shown in ms. Several phones become several controllers (Player 1 to 4, shared with real controllers and DS4Windows), each phone showing its player number. Size, opacity, a background (colour or photo) and the layout (follow the phone, or always sideways) are remembered on each phone; holding the phone upright gives an upright layout.
- **Tweaks explain themselves:** every tweak says, in plain words, what you gain and what you give up.
- **Hide after opening an app** (Settings → General, quick panel): off keeps Deck open after starting apps, files or links from it.
- PC to PC: a transfer cut off by Deck closing (or cancelled) has **Carry on**, which sends only what the other PC is missing; the transfer list survives restarts.

### Changed
- **Tweaks are checkboxes** worded as what Deck does ("Show hidden files and folders"): ticked is Deck's change, unticked is Windows' own setting. Lists of choices mark Windows' default.
- Apps, files and links opened from Deck's search start in the background: Deck no longer stops responding while an app asks for administrator rights, and the UAC prompt comes to the front.
- Workspace Sync's problems say what happened and what to do (for example a cloud folder switched on with no folder chosen).
- Phone remote: full screen notices when the browser quietly left it, and says so when the browser doesn't allow it. Files sent to the phone stay listed after Deck restarts, and an interrupted download on the phone can continue (Deck now tells the browser the file is unchanged).
- An advanced uninstall that Deck was closed in the middle of is offered to finish on the Apps page.

### Fixed
- **Open RivaTuner** closed RivaTuner by force, which could leave Deck or a browser frozen. It now asks RivaTuner to close, and Deck's own windows are kept out of RivaTuner's hooks.
- "Update all with the Microsoft Store" seemed to do nothing when the "Don't update Store apps by themselves" tweak was on (Windows blocks the Store's background updates then). Deck now says so and offers what works; otherwise it reports which apps the Store started or cancelled.
- "Open in Store" for paid apps did nothing.

### Also in this version
- **Phone remote, Screen view:** an on-screen controller in the PlayStation layout (two sticks, D-pad, face buttons, L1/R1/L2/R2, L3/R3, Share, PS, Options; several fingers at once), with its size and opacity in Settings. The PC sees it as an Xbox controller (needs the ViGEmBus driver). **Hold click** keeps the left button down while your finger is on the screen. F1 to F24 in the Keys bar. **Control in games** lets taps and keys reach a game in front (off by default).
- **Workspace Sync for Claude Code** (was "Claude Code sync") carries more than conversations now, so a project can be picked up on another PC:
  - **Project files** (Settings → What to sync, off until you turn it on): each project's folder is kept the same on your PCs, without `.git` and build output. Folders over 40,000 files or 3 GB, a drive, or your user folder are never copied. Deleted files go to the trash folder on the other PCs, and switching it off deletes nothing. **Build files** (target, node_modules, .venv…) can be included too.
  - **Per project:** switch a project's sessions off and keep its memory and files syncing, to start a new session on the other PC and carry on with the project. Its files can be switched off on their own as well.
  - **Programs:** each PC shares which Rust toolchains, targets and components, cargo tools, Node and global npm packages, Python, pipx tools and Git it has. The Status tab lists what another PC has and this one doesn't, with Install (a PowerShell window with your normal rights; nothing installs on its own).
  - **Tailscale is visible:** Settings has an "Over Tailscale, from anywhere" switch with its state (not installed / not connected / which of your PCs are on it, with Get or Open Tailscale), the Status tab shows "Away from home", each PC says whether it is reached over the home network or Tailscale, and PC to PC shows the same. The cloud folder works with any synced folder (OneDrive, Google Drive, Dropbox, MEGA, pCloud, Syncthing).
  - **MCP servers** (yours and each project's, from `.claude.json`) sync with the settings, and wait for your OK like hooks and plugins do. Added on two PCs at once, both lists are kept.
  - **Git history:** files are copied without `.git`; on a PC whose copy has no git, Projects offers **Get git history** (connects the folder to the same remote and branch, files untouched).
  - **Safer with different PCs:** a project folder only guessed from another PC waits until you keep or move it before files arrive, and a guess under the other PC's user folder becomes the same place under this PC's. Build files aren't copied between an ARM and an Intel/AMD PC. A project stops copying when its drive has under 2 GB free. Rust toolchains are compared as "stable" and the like, so each PC installs its own kind. The program check also covers Microsoft's C++ build tools, which Rust needs.
  - **Far fewer disk writes:** the sync state is saved only when it changed, and the file-hash cache at most every 10 minutes (before, about 1.2 MB was rewritten every cycle even when nothing changed).
  - A project's own `.claude` settings, hooks and `.mcp.json` wait for your OK too; `.claude/settings.local.json` stays on each PC.

### Changed
- The design notes moved to `docs/design/`.

### Security
- Updated the TLS certificate checks (rustls-webpki 0.103.16, webpki-roots 1.0.10) for RUSTSEC-2026-0381 and RUSTSEC-2026-0382: distrusted emSign intermediates could have been accepted.

## 2.7.5 — 2026-10-20

### Added
- **Your phone as the PC's speaker or microphone** (Deck → Phone → Speaker and mic, both off until you turn them on; the phone remote gets a Speaker and mic card). **Speaker:** the phone plays the PC's sound, with a switch to turn the PC's own speakers off while it plays (they come back when it stops, even if Deck closes meanwhile). **Mic:** the phone's mic becomes a mic on the PC, with echo and noise cancelling, so Discord, games and calls can use it; pick "CABLE Output" in an app, or turn on "Make it the default mic while the phone talks" (your mic comes back after). Over Wi-Fi, about a tenth of a second late. The mic needs VB-CABLE, VB-Audio's free virtual cable, because Windows only lists a microphone that a driver makes: Deck turns on one that is installed but off, or downloads VB-Audio's own setup for you (its licence doesn't allow building it into Deck's setup).
- **Tweaks** (Maintenance → Tweaks): 132 Windows settings in 13 categories (privacy, Start and search, taskbar, File Explorer, right-click menu, appearance, multitasking, gaming, AI and Copilot, updates, network, system, advanced), from Win11Debloat and Chris Titus Tech's WinUtil, each checked, plus Deck's own. Every switch shows what Windows is set to right now ("Partly" when another tool set part of it), what it changes, its risk and whether it needs Explorer restarted, a sign-out or a restart. **Every change can be undone to exactly what it was before** (one by one or all at once), also months later; Deck notices when a Windows update changes a tweak back and offers to apply it again. Presets (Privacy, Clean Start & taskbar, Gaming, Quiet Windows) and "Recommended" open as checklists, never as one click that does everything. A restore point is offered before Advanced tweaks. Options that don't exist on this Windows version or this PC are hidden. Tweaks also turn up in Deck's search, and a PC to PC setup carries them to your other PC. Deck never removes Edge or WebView2, turns Windows Update or Defender off, or runs scripts from the internet.
- **Built-in apps:** remove Clipchamp, News, the Xbox apps and the rest (Win11Debloat's list with its safe / optional / needed rating), and reinstall any of them later.
- **Store apps without the Microsoft Store** (Tweaks → Get Store apps), like store.rg-adguard.net: search the Store, then Install, Download (to Downloads\Store apps), send to FluxDM, or copy the links. The files come straight from Microsoft's own servers, only the ones this PC is missing (usually just the app), checked against Microsoft's checksums, with a progress bar, speed and time left. Free apps only; desktop apps from the Store install with winget.
- **The phone remote also answers on https** (same address, `https://`). Phones allow the mic only on secure pages; Deck makes its own certificate, so the phone warns once ("not private") the first time.

### Changed
- **Store apps download about six times faster:** each file comes in 8 parts at once (Microsoft's servers give one connection only so much; WhatsApp's 311 MB took about 27 minutes on one). A cancelled or failed download has **Carry on** / **Try again** and continues where it stopped.

### Fixed
- PC to PC's "restart Explorer" after applying a setup started Explorer with Deck's admin rights; Windows now restarts it as you.
- Settings → Updates said "GitHub's answer wasn't understood" on every check after the first while no new version was out (GitHub's "nothing new" answer was read as a broken one). Updating itself wasn't affected.
- Turning the phone remote off and on moved it to the next port (the old one stayed open), so a phone's saved link stopped working.
- Undoing *Variable refresh rate* also undid *Windowed game optimizations* when both were changed (they share one DirectX setting); each now puts back only its own part.
- Deck's own updates (and the RustDesk setup) gave up after 60 seconds (5 minutes for RustDesk) of downloading, so on a slow line a release bigger than about 10 MB could never install by itself. Now only a connection that stalls for a minute ends them.
- Game boost could end an unrelated program that had just started and been given the ID of an app boost was closing (Windows reuses process IDs); it now checks the program first.
- RustDesk's, Tailscale's and winget's command lines that hang (a stuck service) no longer freeze the Remote desktop page or PC to PC: every program Deck runs has a time limit.
- Timers and Tweaks that shut down, restart or sign out said "done" even when Windows refused (another shutdown already scheduled); they now say why.
- The phone mic stayed "on" but silent when VB-CABLE went away mid-call; the phone now reconnects and says why. When Windows doesn't restart Explorer by itself (some debloat scripts turn that off), Deck starts it without its admin rights. Installing Store apps and VB-CABLE's setup no longer fail for a Windows user name with an apostrophe.

### Security
- **Tweaks' undo list can't be used to change Windows behind your back.** Undo writes the saved values back with Deck's admin rights, and the list lives in your own folder, where any program could edit it. Deck now keeps its fingerprint where only administrators can write; a list changed by something else is set aside (Tweaks says so) and never used, and undo only ever touches what that tweak itself changes.
- **"Unpin everything from Start" and Store downloads work with your rights only** in your folders (a folder swapped for a link can't make Deck read or write elsewhere).

## 2.7.0 — 2026-10-20

### Added
- **A new in-game death counter.** Pick how it looks: a skull with a big number (the default), a ring that fills toward the deaths your last boss took, or one huge number. It can count this boss, the whole game, or both side by side, and shows the game's total between fights (or nothing).
- **The card after a death.** When you die, the counter opens into a card for a few seconds: the boss, your next try, its deaths, how long that try lasted, your time on the boss, deaths this session, bars for your last 10 tries, and a highlight like "Your longest try yet" or "100th death in this game". Every line can be switched off, and so can the card.
- **Red edges on a death** (off by default): the screen's edges glow red for a moment.
- **A live preview** of the counter and the card next to their settings, drawn by the same code as in the game.
- **Play sessions.** Deck notes when you play each game; the History tab is now one card per session (how long, deaths, bosses beaten, deaths over time) with the events inside, instead of a long list. Older history gets sessions worked out from when your deaths were counted.
- **Boss cards** instead of the table: deaths, time, longest try, which try beat it, and a line of how long each try lasted, so you can see yourself learning a fight. Each boss can have a note (a strategy, a reminder), and the card after a death can show it.
- **Records** on the Now tab (longest try, quickest win, deadliest boss, most deaths in a session) and this session's numbers.
- **All games together** on the Games tab: total deaths, time played, bosses beaten, deaths per week, the deadliest games and bosses.
- **Share and export.** "Share" copies (or saves) a picture of a game's or a boss's numbers; "Export" saves a game's history, or everything, as a spreadsheet file.

## 2.6.1 — 2026-10-20

### Fixed
- **Death counter: dark death screens are read.** Windows' text recognition read nothing from a dim red banner on a dark screen ("KHAZAN HAS FALLEN"); Deck now makes the middle of the picture high-contrast before reading it, and a long phrase may have a letter or two misread. The First Berserker: Khazan is recognised outside Steam too.
- **Teaching a death screen works in dark games and when you count late.** Deck keeps the last 20 seconds (it was 10). When the whole screen fades at death, Deck learns the words or symbol that stand out on it instead of refusing it as "one flat colour", and ignores the character and scene behind them, which differ at every death.
- **Death screens keep their colour.** Pictures were turned grey by brightness, which made red words dull; Deck now uses each spot's brightest colour, and the teaching pictures are shown in colour.

### Changed
- **Games are known by their program only.** The death counter no longer uses Steam or Epic numbers or library lists: a game is its exe, the same in every store, named from the program's description, its install folder or its window title. Deck's list of games with their own death screens or save readers is now the 17 it knows by exe (an Easy Anti-Cheat launcher no longer counts as Elden Ring). Death screens taught under an older Steam key need teaching again.
## 2.6.0 — 2026-10-20

### Fixed
- **No more "Set up" after an install or an update.** The setup is the one place that asks for admin rights: it makes Deck's admin tasks itself and starts Deck hidden through them. Before, the setup started Deck as a normal user and every install showed the Set up banner again. A Deck started without admin rights (the setup's "Run Deck" box, a shortcut) while the tasks exist now hands over to the admin task by itself.
- **Deck comes back after a crash or a graphics driver update.** If something ends Deck, the watchdog gives the fans back to the BIOS and then starts Deck again, hidden. It waits for a running driver installer to finish first. After three such ends in ten minutes it stops and Deck starts with the fans on the BIOS and no overclock until you turn hardware control on (a toast says why). The log now says how Deck ended (crash kind and the DLL, or "ended by another program").
- **A driver install no longer hits Deck's GPU calls.** While NVIDIA's (or AMD's, Intel's) driver setup runs, Deck makes no GPU calls, and restarts itself once afterwards so the new driver is used and the profile is applied again.
- **The controller's real name in the "Connected" message** (a GameSir dongle said "XInput Controller #1").
- **The overlay's CPU clocks now really match MSI Afterburner.** 2.5.10 measured the average clock each core ran at, which comes out a few % below Afterburner's on a boosting CPU (5.1 GHz against 5.29), and the thread lines still used Windows' estimate. Afterburner shows each core's current speed step times the bus clock; the overlay now reads the same (Intel), so the CPU clock, every thread line and the core table show the same figures as Afterburner. The CPU page keeps the measured average.
- **Claude Sync no longer calls the same version "older".** It compares build times, so another build of the same version (a test build) showed "runs an older Deck (2.5.10; this PC has 2.5.10)". It now says the other PC runs a different build of that version.
- **A core's load in the overlay's core table is its busiest thread's.** The average of a P-core's two threads showed a game's main thread at 100 % as 50 %, hiding a CPU-bound game.

### Changed
- **"Like MSI Afterburner" looks like MSI Afterburner:** its layout (clock, CPU, a line per thread, RAM, FPS, GPU, MEM, then the frametime graph), its default colours, a white framerate, small thread numbers (CPU₁) and a small "Frametime" above the graph with the frametime after it. The framerate figures (min, average, lows) are left off, as Afterburner shows them only while benchmarking; add them back in Items.
- New look options: **Small thread numbers** (Layout), **Afterburner layout** for the graph (Graph), and a colour of its own for the framerate number.

### Added
- **Death counter: the same game in every store.** A game is known by its program, so a Steam, GOG, Game Pass or EA copy is the same game, with the same history and death screens. Fullscreen browsers and video players are never counted as games (a video of someone dying doesn't count), one death seen by the screen and pressed on your key counts once, and "WASTED" no longer matches "WANTED".
- **Updates from GitHub.** Deck looks once a day for a newer release and installs it by itself when no game or fullscreen program is in front: no prompt, no window, and it is back in the tray a moment later. The download is checked against the release's SHA-256 first. Settings → About shows the state, "Check now", "Install" and a switch to turn it off. A Deck without admin tasks only tells you and installs on your click (one admin prompt). The first install of this version is manual; updates come on their own after that.
- **Controller overlay** (Monitor → Controller). Controller Overlay, the separate app, is now part of Deck: your controller's buttons, sticks and triggers on screen over your games, in the same DualShock 4 look, with every theme, style, layout, size, corner and monitor setting it had, idle fade, Move / resize by dragging, demo input and keyboard & mouse mode. The tray menu has it under **Controller overlay**. Your Controller Overlay settings are brought over the first time Deck starts; uninstall the old app whenever you like.
- **Controller battery for any controller.** One tray icon per controller that reports its battery, phone style, and the same level on the overlay's battery pill. Reads GameSir dongles directly, PlayStation controllers from what they already send (nothing is written to them), and Xbox and Bluetooth controllers through Windows. Like a phone, the level never jumps up after switching the controller off and on; a warning comes once per charge at 15%. The Battery tab lists every controller and where its level comes from.
- **Test tab:** the controller the overlay reads, live (buttons, sticks, triggers), with or without the overlay on.
- The overlay stays out of screenshots and recordings unless you turn that off.
- **Death counter** (Monitor → Deaths). Count your deaths in any game, per boss. Start a boss fight, and every death counts toward it until you mark it defeated or abandon it, including deaths on the way back. Stats per boss: deaths, attempts, wins, deaths before the first kill and time. Count from the tray menu (Death counter), two keyboard shortcuts you choose, a controller combo (hold Select + D-pad Down for a second; Select + Up undoes), or the page; every count can be undone, and the history can be edited. A small counter shows over the game ("Malenia · 14"), click-through and hidden from recordings unless you want it in them. Any game works; Deck recognises Steam and Epic games by name and knows 320 hard games. **Counts by itself:** Deck watches the game's window for death screens ("YOU DIED", "GAME OVER", "WASTED"… plus a game's own, for a first set of games) and runs Windows' built-in text recognition only when the picture settles; Celeste and Dark Souls: Prepare to Die Edition are counted from their save files. Nothing it sees is recorded or saved, and both can be turned off. **Teach it a death screen:** for a game whose death screen has no words (Sekiro's), count the death yourself, then click the clearest of the last 10 seconds' pictures on the Deaths page; Deck counts that screen by itself from then on (up to 3 per game, shareable with friends as a code). **Shared library:** submit what you taught to everyone (a button that copies the code and opens a GitHub form; it is added after review), and Deck picks up new death screens from Deck's public GitHub page at most once a day (a plain download, nothing about you is sent; turn it off in Deaths → Settings).
- **GPU memory controller load** ("FB usage" in Afterburner) as an overlay item (NVIDIA).

## 2.5.10 — 2026-10-19

### Fixed
- **CPU clocks now match MSI Afterburner and HWiNFO.** Deck showed Windows' estimate of each thread's clock, which runs a few % low and jumps around (4.8-5.2 GHz on P-cores and 3.2-3.9 GHz on E-cores where Afterburner showed a steady 5.29 and 3.99). Deck now reads each core's own cycle counters, as Afterburner does, on Intel and AMD; Windows' figure is only used without the driver.

## 2.5.9 — 2026-10-18

### Fixed
- **CPU clocks read about 20 % low under some power plans.** Deck measured against Windows' "current" CPU clock, which a power plan lowers, instead of the CPU's fixed base clock. In a game, cores at 2.69 GHz (HWiNFO) showed 2.15 GHz on the overlay, the CPU page and Sensors. Now checked against HWiNFO core by core.
- **The overlay's framerate could come from a different program than its lows and average**, for example a launcher drawing faster than the game. FPS, frametime, game RAM and the framerate figures now all follow the same game.
- **The framerate no longer stays frozen** on a game that stopped drawing (alt-tabbed, paused or closed).
- **A new game no longer starts with the previous game's frames** in its average and lows.
- **The preview's API and resolution are the game's own.** They used to say "D3D12" and the desktop's size for every game. With no game, the preview's graph is empty instead of a made-up line.
- **Long overlays are no longer cut off in the middle.** RivaTuner 7.3.5 and newer get the 32 KB text field; on older versions, whole lines are left off the end instead of breaking the colours of everything after the cut.
- **Hiding RivaTuner's tray icon no longer starts a process every 5 seconds**, also while gaming.
- **RivaTuner installed outside its default folder is found.**

### Changed
- **The frametime graph is MSI Afterburner's:** RivaTuner's own graph of every frame, which it redraws with each frame, so it moves as smoothly as the game. Deck used to send it about 12 points a second, which looked choppy. It uses your style, height, width and top.
- **The graph sits on a line of its own**, labelled FT and lined up with the other lines, with the live frametime in front unless the overlay already shows it.
- **The graph's top on Auto is four average frames** (33 ms at 120 FPS): a normal frame sits a quarter of the way up and stutter stands out. RivaTuner's own autoscale followed the slowest frame on screen, so one hitch flattened the rest. A fixed top shows the framerate it stands for ("16 ms · 63 FPS").
- **"Shows the last" and "Smooth the line" are gone:** RivaTuner keeps its own frame history.

## 2.5.8 — 2026-10-18

### Changed
- **The CPU page is reworked.**
  - **A live column stays in view** while you scroll or edit: clock with its last minute, temperature, load, power, the power limit in force and who set it (your motherboard or the active profile), and every core's clock and load.
  - **"Held at the power limit"** appears when the CPU draws all the watts it may under load, so a low motherboard limit is no longer invisible.
  - **Profiles are edited on the page**, not in a popup: an edit button on each card opens the settings under the profiles, with an "Unsaved" mark and Save / Discard.
  - **Plain settings first:** clock caps, Turbo boost on/off, energy preference, power limits and extras. Windows' processor states, parked cores and the five turbo modes are folded under Advanced.
  - **A slider's end means off:** all the way right is "No cap", all the way left is "Off" for the clock floor (was "Keep the clock at least") and the overclock.
  - **"Plan's own" energy preference shows the plan's real value** ("Plan's own · 33"), with a note when it leans to saving.
  - **"Stock" power limits are now "Motherboard"** and show the board's own watts. Custom PL1/PL2 go above 253 W when the board's own limits do.
  - **Warnings** for settings that cancel each other (a cap below the overclock, a clock floor above the cap). "Hold the cap in games" only shows when the profile caps.

### Fixed
- **A clock cap at the CPU's top turbo no longer caps.** A profile saved with its cap slider at the top (5,300 MHz on an i5-14600KF) still held the CPU at that clock and blocked any overclock. Such caps now count as no cap when saving and applying, once Deck has read the CPU's real top turbo.
- **E-core clocks read about a quarter too low** in the overlay, on Sensors and in the per-thread rows (2.97 GHz for an E-core really at 4.0 GHz on an i5-14600KF). Windows measures every core's performance against the CPU's base clock, and Deck multiplied the E-cores' by their own lower one.
### Testing
- **`install.ps1` no longer does nothing when Deck is running.** It printed a warning and stopped, so a developer install often left the old version in place. It now closes Deck itself, retries the copy until the installed Deck.exe matches the build (and says so in a window that stays open if it can't), and starts Deck again.

## 2.5.7 — 2026-10-18

> **When you update:** if you typed your own PC to PC pairing code or Claude Code sync key, it keeps working. A new one you type must now pass the "too easy to guess" check.

### Security
- **Programs can't borrow Deck's admin rights through winget.** Deck ran `winget` (PC to PC → Apps) by name, which finds a copy in a folder any of your programs can write to. It now runs winget only from App Installer's own protected folder.
- **Remote desktop setup can't be hijacked through PowerShell.** Deck's admin PowerShell steps could load commands from your Documents folder before Windows' own. They now load commands only from Windows' folder, and take no folder from the environment.
- **RustDesk's installer is checked where it can't be swapped.** It is copied into a protected folder, kept locked while it is checked and installed, and must carry GitHub's checksum and RustDesk's own signature (not just any valid one).
- **Hardware settings can't skip the "changed outside Deck" check.** A test switch (`DECK_PROFILE`) that your programs could set made Deck read hardware settings from a fresh folder it then trusted. An admin Deck now ignores it.
- **The 32-bit RivaTuner helper** starts only from Deck's own folder when Deck runs as admin.
- **Keys on disk are sealed with Windows (DPAPI).** This PC's PC to PC key, the pairing code, the phone key and the sync key no longer sit in plain text in AppData, so a copied profile or backup doesn't carry them. Older files are sealed the first time Deck starts.
- **Typed pairing codes and sync keys that are easy to guess are turned down** (repeats, runs like 1234 or ABCD, or few different characters). PC to PC and Claude Code sync serve at most 64 connections at once, and a stranger has 10 seconds to prove the code.
- **Exploit mitigations:** Deck and its helper are built with Control Flow Guard, and Deck with CET shadow-stack support.

### Fixed
- **CPU clocks in the overlay and on Sensors show the real clock.** The main CPU clock and every P-core / E-core row read a register that stays at the top turbo step (5.30 / 4.00 GHz on a 14600KF) while a core naps, so they never moved. They now come from the same live Windows reading as the thread rows: a core shows its busiest thread's clock.

### Testing
- The UI test suites wait up to 30 seconds for headless Edge to start (a slow CI runner timed out at 10), and the notification-window test always closes its Edge, even when it fails.

## 2.5.6 — 2026-10-18

> **When you update:** update every PC that uses PC to PC or Claude Code sync, since old and new versions can't talk to each other. Then re-pair your PCs once (trusted PCs and "always allow" are asked again; "never" choices are kept). If Deck was installed per user before, click **Set up** once more after the update. The phone page reloads itself once.

### Security
- **The phone can no longer run programs on the PC.** A phone could ask Deck to "open" any file path by pretending to answer a "File from your phone" notification. The phone now answers only its own kind of notification (media, power, timers, text), and the "Open" button on a received file works only for a file that really arrived from that phone and only from the PC itself. Accepting transfers and applying a held GPU overclock are PC-only decisions now.
- **An elevated Deck ignores WebView2 flags from the environment.** When Deck runs as admin it no longer reads `WEBVIEW2_*` variables (any program running as you can set them, and a debugging port there would expose every command Deck has). The live-testing debug port now comes from Deck's own command line (`--cdp-port`).
- **Programs can't borrow Deck's admin rights through your files.** When Deck works in your folders (phone uploads, files from another PC, Claude Code sync, share links, Clean up, the Recycle Bin, its own settings), it does only what your everyday account could do. A folder swapped for a link can't redirect it into Windows' own files.
- **Deck won't share, send or serve a file your everyday account can't open**, and won't zip a folder that contains links.
- **Hardware settings changed outside Deck wait for you.** If another program edits Deck's fan, CPU or GPU settings, Deck keeps the fans on the BIOS and applies no overclock until you click **Apply them** on the PC.
- **The phone key no longer travels over the network.** The phone signs every request instead, and a recorded request can't be sent again. The phone page also refuses requests a web page sends by pointing one of its own internet names at your PC (DNS rebinding).
- **Each PC has its own key for PC to PC.** Trust and "always allow" now belong to that one PC, not to anything that knows the pairing code. Pairing codes and the Claude Code sync key are also much slower to guess.
- **Installers from another PC always ask on this PC**, even from a trusted PC, and run through Windows' normal admin prompt, never with Deck's own rights.
- **Claude Code sync holds risky changes.** If another PC's sync would change what Claude Code runs or may do without asking (hooks, plugins, status line, permissions), you see "Claude Code settings from <PC> are waiting" with **Apply** or **Keep this PC's**.
- **Share links:**
  - A one-time link can't be downloaded twice at the same time.
  - Home-only links can't be reached from the internet.
  - Funnel turns itself off at start unless an internet link is open.
- **Deck checks RivaTuner's shared memory before using it**, so a program pretending to be RivaTuner can't make Deck read or write outside it.
- **GPU and power libraries load only from Windows' own folder** (or NVIDIA's), never from a folder you or a program could write to.
- **"Open as your normal account" never falls back to admin.** If Explorer can't take a launch, Deck says so instead of starting the program with admin rights.
- **TLS library updated** (rustls 0.23.46) for four advisories published on 2026-10-14 (RUSTSEC-2026-0346 to 0349).
- **The RustDesk password no longer appears on PowerShell's command line.**

### Changed
- **Tools is one page.** Screen tools, Locked files and Windows panels are no longer separate tabs, and the page has a fresh look.
- **The setup installs for all users, in `C:\Program Files\Deck`.** It asks for admin once, and quietly removes an older per-user copy while keeping your settings.
- **Set up refuses an unsafe install.** If Deck sits in a folder your everyday account can change, Set up explains why it won't give it admin rights. Admin tasks that already point at such a copy are removed at start, with the notice "Deck's admin start was turned off".
- **PC to PC → Settings:** the switch for installing without asking from trusted PCs is gone, since installers always ask now.

### New
- **CPU profiles for plugged in and on battery** (CPU page, on PCs with a battery). Pick a profile for each; Deck switches when you plug in or unplug, and a profile you choose yourself stays until the next change. **Profiles also apply on battery** (on by default) makes a profile cap the CPU the same way on battery; turn it off to keep Windows' own battery values in each plan.
- **Fan watchdog.** If Deck is ended from Task Manager, the fans go back to the BIOS and the GPU fan back to the driver within seconds. While hardware control is on, a second small `deck.exe` in Task Manager is the watchdog.
- **Deck keeps a log** in `%LOCALAPPDATA%\Deck\logs`, and the This PC support report includes its last lines.
- **A "Shut down when…" plan survives a Deck restart.** It starts waiting again from the beginning.

### Fixed
- **Building from source** works with Rust 1.99 (its new clippy check failed the build in CI), and the tests pass when run as admin.
- **Overlay "Threads" table showed fake clocks.** Every thread read its base clock (for example 3500 MHz on P-cores and 2600 MHz on E-cores) whatever it was really doing, so a CPU cap looked like it did nothing. It now shows each thread's live clock, the way Task Manager measures it, with or without admin rights.
- **Overlay "Game RAM" measured the wrong program** when another window was in front (a screenshot tool, Discord). It now measures the game RivaTuner is drawing in, and shows nothing if the game's anti-cheat hides it.
- **The CPU clock without admin rights** read too high when an E-core was the busiest core.
- **Bigger click targets** on the Disk space tree arrows, the Home tile settings button and the overlay tick boxes; screen readers now name both "send text" boxes.
- **Settings survive a bad shutdown.** If `settings.json` is damaged (for example by a hard reset mid-save), Deck keeps the damaged file, restores the last good copy, and otherwise keeps every setting it can still read instead of silently resetting everything. Each save now keeps a backup of the previous version and is written so a crash leaves a whole file, never a half-written one.
- **The GPU/CPU crash guard fails safe.** If its record file is damaged, Deck now holds a risky overclock back at boot instead of re-applying it — the exact situation the guard is meant for.
- **Pairing codes and the phone key** are generated without the slight bias the old method had, and Deck now stops with a clear error if the system's random number generator fails rather than making a guessable token.
- **Themes:** button and chip borders on hover, switches, sliders, progress bars, scrollbars, the calendar, toasts and app placeholders kept the default theme's blue-grey in every theme. They now take each theme's own colours.
- **The overlay key could fail to switch RivaTuner** on a PC without Microsoft's Visual C++ runtime: Deck's small 32-bit RivaTuner helper needed it. The helper now carries its own copy, like Deck.
- **Clipboard page slow with a huge item.** A copied log of 200,000+ characters went onto the page in full and made the page take about 0.2 s to open. Cards now show the start of an item, and the preview the first 20,000 characters (with a note); Copy and Paste still use all of it.
- **Sidebar badges** (a running timer, Keep awake on, a plan set, a phone connected, a PC waiting) were squeezed out next to long page names. They now sit on the page's icon: a number for a count, a dot for on or set (hover it for the word).
- **More files survive a bad shutdown.** Your clipboard history, the list of items received from a phone or another PC, and the Game boost restore-state are now written the same crash-safe way as settings, so a hard reset mid-save can't truncate them.

## 2.5.5 — 2026-10-16

### Changed
- **Overlay page, redesigned.** It was one long column of seven sections (about four screens of scrolling).
  - **Top strip:** the overlay switch and RivaTuner's state, with the keys you use in game: show or hide, and the frame limit (limit, on/off and its key).
  - **Preview:** bigger, and it stays in view while you edit, with the quick looks under it.
  - **Settings:** seven short tabs: Items, Layout, Look, Colours, Graph, Warnings, Behaviour. Deck remembers the last tab you used.
  - **Denser lists:** the item list is compact, with move and remove buttons showing on hover. "Add readings" opens when you want it.

### Fixed
- **Docs:** the README describes the new Overlay page and the framerate limiter, and has a new Overlay screenshot. It also says the CPU readings need admin.
- **Home → PC tile on a PC where Deck isn't running as admin:** the CPU card showed only "20 threads", with no clock, power or temperature, and gave no reason. Those readings need admin, so the card now says *Needs admin* and sets it up when clicked. The tile's customize dialog says the same.
- **Open RivaTuner did nothing** (the mouse showed a busy cursor for a moment) when RivaTuner's own *Start minimized* option is on: it restarted straight into the tray, whose icon Deck may hide. Deck now turns that option off for this one start and puts it back once the window is open.
- **Framerate limit key only turned the limiter on:** when Deck couldn't read RivaTuner's switch it took it as "off", so every press meant "turn on". Deck now reads the switch from RivaTuner's 64-bit hooks (and remembers what it set last), so the key turns it off again.
- **Framerate limit didn't reach a running RivaTuner:** Deck wrote the limit into RivaTuner's profile file, which RivaTuner only reads when it starts (its window still showed 0). Deck now also sets it through RivaTuner's own profile interface, so RivaTuner and running games use it at once.
- **Shortcut keys on a laptop's built-in numpad:** Fn + 9 (Page Up) was saved as "Num9", which never fires because Windows gets Page Up. The recorder now saves the key the numpad key actually sends (Page Up, Home, End, arrows…). Fn itself never reaches Windows, so there's nothing to "allow": press Fn + the key and the recorder now saves the right one.
- **Phone page settings looked unchangeable:** a click on a Screen view option (picture size, smoothness, bitrate…) was saved, but the page kept showing the old choice until something else redrew it. The page now redraws right away.
- **Fold-out sections closed by themselves** whenever a page redrew (for example the Phone page when a phone connected). Open sections now stay open.
- A setting that **failed to save** no longer shows as if it had been changed.
- **Bitrate → Type…:** pressing Cancel (or typing something that isn't a number) set the bitrate to Auto; it now keeps the bitrate. Empty still means Auto.
- **Phone limits:** two phones connecting at the same moment could both get the last place; a phone that was turned away could still send and download files. Both closed.
- **Screen view:** tap then drag on a window's title bar or a file could act as a double-click (maximize, open) on the PC; a long press during tap-then-drag right-clicked instead of dragging.
- **Shortcuts in full-screen games:** quick taps are seen more reliably, and a shortcut held while a game came to the front no longer runs again.

## 2.5.4 — 2026-10-16

### New
- **Who can connect** (Phone page): how many phones may connect at home and how many away (no limit, 1, 2, 3 or 5 each), and two switches: a phone at home shuts out phones away, or a phone away shuts out phones at home. A phone that is turned away sees why and tries again every 10 seconds.

### Fixed
- **Overlay key and other Deck shortcuts didn't work in League of Legends** (and other games that switch off Windows shortcuts while they are in front). While a full-screen game is in front, Deck now also watches its shortcut keys itself and runs one Windows didn't deliver (the rest of the time it only checks once a second whether a game came to the front). Still no keyboard hooks.
- **Phones connected** counted connections, not phones (the remote, its Screen view and its sound each added one), and didn't say where they were. It now counts each phone once and shows how many are at home and how many away.
- **Screen view on the phone:** sliding a finger held the left mouse button down (dragging or selecting on the PC). Sliding now just moves the pointer, like a laptop touchpad; tap, then touch again and slide, to drag.

## 2.5.3 — 2026-10-15

### Fixed
- **Lighting controls did nothing** (every effect, on or off, and the lights test too) while Deck said "Motherboard RGB connected". The board's lighting controller had lost the configuration Deck writes when it connects, and then ignores every colour sent to it without any error. Deck now checks every 5 seconds that the board still holds its configuration and writes it again when it doesn't.
- A **lights test** that never finished (the controller stopped answering) kept all lighting frozen and refused a new test until Deck restarted. The hold is now always released: the test gives up after 40 seconds, and a hold older than a minute is cleared by the lighting loop.

## 2.5.2 — 2026-10-15

### Fixed
- **Setup and uninstaller still said "Failed to kill Deck"** when Deck had no `\Deck\Quit` task yet (2.5.1 only adds it once it has started with admin rights). The setup / uninstaller now first uses that task and, if it isn't there, closes Deck by running `deck.exe --quit` as admin (one Windows prompt). Note: an uninstaller belongs to the version that is installed, so a Deck older than 2.5.1 still needs to be closed from the tray once; installing 2.5.2 over it replaces that uninstaller.

## 2.5.1 — 2026-10-15

### Fixed
- **Setup and uninstaller could not close Deck** ("Failed to kill Deck. Please close it first"): Deck runs with admin rights, the setup does not, so Windows refused to end it. They now close Deck through a new admin task (`\Deck\Quit`), which also hands the fans back to the BIOS. Deck adds the task itself the next time it starts with admin rights.

## 2.5.0 — 2026-10-15

### New
- **PC to PC** (bottom of the sidebar, above Phone; on by default): send files, folders, installers, apps and your Windows setup between your PCs, with Deck on both and the same pairing code. They find each other on the home network by themselves (or by address), and everything is encrypted with the pairing code.
  - **Send**: files and installers (optionally **installed on arrival**: silently when the installer allows it; the other PC asks first unless it trusts this one), whole folders (shows what goes first; skips build output such as `target` or `node_modules`; can send only new or changed files, and delete on the other PC what's gone here, after its user agrees), or a piece of text.
  - **Browse** the other PC's shared folders and copy from them; nothing is shared until you add a folder, and each PC is asked, always allowed or never allowed.
  - **Apps**: pick apps installed here; the other PC installs them itself with winget, skipping the ones it has (retries network errors; "Retry failed").
  - **Setup**: sends this PC's look (dark mode, accent, taskbar and Explorer options), wallpaper and Windhawk mods; the other PC picks what to apply, backs up first and can undo.
  - **Received**: install, install silently, extract, apply a setup, show or delete the files. Offers and requests waiting for an answer show as notifications with Accept / Decline.
  - Transfers resume after a dropped connection; progress, speed and time left show live.
  - **Everything asks first** (Accept / Decline, also as a notification), unless you trust the sending PC: **for a week, a month, 6 months or always**, from the prompt or Settings → Trusted PCs. Deleting files on your PC is always asked.
  - **Away from home**: your other PCs on Tailscale (the same private network the phone remote uses) are found by themselves; no cloud folder needed.
  - **Command line** for scripts and Claude Code: `deck.exe --pc-list`, `--pc-send <path> [--to PC] [--all] [--sync] [--install]`, `--pc-get <path> --from PC`; prints progress and a clear result (exit code 0 = done). **Let Claude Code use PC to PC** (Settings) installs a short Claude Code skill so Claude can send files or a whole project, dependencies included, when asked.
  - A single file arrives in a folder named without its extension.
  - **Phone transfers continue after a dropped connection**: the phone sends in 8 MB pieces the PC keeps, retries by itself and goes on from what the PC already has (picking the same file again later continues too), with speed and time left. Downloads to the phone and share-link downloads can be continued by the browser (byte ranges). The command line shows time left.
  - **Share link**: a file or folder for someone who isn't one of your PCs. They open a link in any browser (no Deck needed) and download; the link works once or until it ends (1 hour, 1 day or 7 days), on this Wi-Fi, or over the internet through Tailscale Funnel (only the shared file is published, and only while a link is open). A folder is zipped first; a download that breaks off doesn't use the link up; you get a notification when it's downloaded, and can stop a link any time.
- **Claude Code sync** (under Desktop, hidden until shown in Settings → Sidebar or switched on; off by default): for Claude Code on more than one PC. Keeps its conversations, memory and settings the same on your PCs (directly on the network, or through a cloud-synced folder), rewriting project paths so /resume works on each PC.
  - Encrypted with a sync key only your PCs know; sign-in details and per-PC files are never synced.
  - **Session lock**: a conversation open on one PC can't be continued on another by mistake (Claude Code is stopped with an explanation; **Take over** overrides it). **Tell Claude** which PC it runs on.
  - **Sessions** (search, where each one lives, delete here or on all PCs), **Projects** (each project's folder on this PC; move, stop syncing, delete everywhere), **Status** and **Log**.
  - It adds two small hooks to Claude Code's settings while on, and takes them out when switched off or when Deck is uninstalled. Settings from the standalone ClaudeSync app are taken over the first time; it won't start while that app runs.
- **Screen on your phone** (Phone page, off by default): see the PC's screen live in the phone remote, at home or away (Tailscale), and with **View and control** use it too.
  - **Control starts off** on the phone every time, so watching can't click anything by accident; the Control button turns it on.
  - Tap to click, hold for right-click, drag to drag, two fingers to scroll; pinch to zoom in on small text.
  - **Full screen**: hides the bars until you leave it, with small buttons on the edge for control, the keyboard and leaving.
  - **Sound** (off until you turn it on on the phone): the PC's sound plays on the phone, as one continuous stream (no clicks between pieces; the PC's and phone's clocks are evened out without skipping), with a small delay that adapts to the connection and to how the phone plays sound (from 120 ms; after a dropout it grows by as long as the sound was missing, up to 1 s while just watching, since the picture waits for the sound, and 0.3 s while controlling the PC; it shrinks again after half a minute without one; sound that falls behind catches up by leaving out silent moments; dropouts are counted in the status line). The PC also stops sending pictures while earlier ones are still queued on the line, so a bitrate above what the connection carries can't hold up the sound or your taps. **Best** (uncompressed, ~1.5 Mb/s), **Good** (~400 kb/s), **Medium** (24 kHz stereo, ~200 kb/s) or **Low** (16 kHz mono, ~70 kb/s); **Auto** picks one from the connection.
  - **Lip sync**: while only watching, each picture waits for the moment its sound plays on the phone. With Control on the picture stays instant instead.
  - **Bitrate**: **Auto** (measures the connection and follows it, from a slow DSL line up to full quality at home), a fixed limit from 30 Mb/s down to 0.5 Mb/s, or one typed in. When it's tight: **Smooth** keeps the chosen frame rate, even on a 1 Mb/s line (the picture gets smaller and blurrier: 30 fps at 1 Mb/s is about 320 px); **Sharp** keeps text readable: the screen's own resolution at good quality, with fewer pictures (about 5 a second at 8 Mb/s, 10 from 15 Mb/s, 2 on a slow line).
  - **H.264 video** (Video: H.264, the default; JPEG stays as a fallback): the same 30 fps picture takes a fraction of the data, so a 1 Mb/s DSL line shows 30 fps at about 640 px (60 fps at 480 px, text still readable at Smooth). Uses the graphics card's encoder (NVIDIA, AMD, Intel) and the Windows software one if there is none; if an encoder fails Deck moves to the next, then to JPEG, and tells the phone. The phone decodes with WebCodecs when its browser allows it (secure pages), and otherwise with its own decoder in the page (WebAssembly: any browser, plain home address included), drawing each picture as it arrives like JPEG, so nothing stalls, jumps or replays old pictures; a phone that decodes too slowly is sent narrower pictures. Browsers without WebAssembly use the browser's video player. Key pictures (several times a normal one) come only when needed. Smooth keeps the frame rate and shrinks the picture; Sharp keeps the picture and lowers the frame rate (not under 8).
  - **15, 24, 30 or 60 fps**. Pictures only go out when the screen changes, so 60 shows in games, scrolling and 60 fps video.
  - At home it uses the home network even when the phone opened the Tailscale code.
  - Type with the phone's keyboard, plus a bar of keys and shortcuts (Esc, Win, arrows, Copy, Paste, Alt+Tab, Task Manager…).
  - Every monitor can be picked; picture size **Full** (the screen's own resolution, the default), **Medium** or **Small**. Full keeps colour detail at high quality, so small text stays readable.
  - Pictures are captured on one thread and compressed on two others, so the frame rate follows the screen (the status line shows both: "49 fps (screen 59)").
  - Light on the PC and the connection: nothing is sent while the screen doesn't change, and a picture only goes out once the phone has shown the last one.
  - Control pauses while a game is in front (watching still works): Deck never sends input into games, because anti-cheat systems watch for that.
  - The PC shows a notice while a phone is watching, and the Phone page shows how many are. Windows hides the lock screen and admin prompts from every app, so the phone says so instead.
- **See and control this PC** (Phone page): remote desktop through RustDesk (free, open source), from your phone or another computer.
  - Deck installs RustDesk for you. The download is checked against GitHub's fingerprint and RustDesk's signature.
  - It shows the addresses to type in: **At home** (your home network) and **Away from home** (Tailscale), plus the RustDesk ID.
  - Switches for **Allow remote desktop** (off stops RustDesk completely, also after a restart), **Connect by address** (straight to this PC, not through RustDesk's servers) and **Hide tray icons** (RustDesk and Tailscale keep working; their state shows in Deck instead).
  - Set the password from Deck, with short steps for the phone.
- **The phone remote works away from home** through Tailscale, a free private network between your own devices; nothing is opened to the internet.
  - The Phone page's code has **At home** and **Away (Tailscale)** tabs.
  - Until a phone is on your Tailscale, the Away tab shows how to put it there. Its code opens a "Get Tailscale" page: the App Store on iPhones; on Android the Play Store and a direct download from Tailscale's own site, for countries where the Play Store doesn't offer it. It also shows the account to sign in with.
  - Once the phone is on it, its name shows under the code, connected or offline.
- **Hide RivaTuner's tray icon** (Overlay → Behaviour): RivaTuner keeps running with no icon in the taskbar corner, not even under the arrow, and Deck keeps it gone when RivaTuner or Explorer restarts. Turn the switch off and the icon comes back straight away. **Open RivaTuner** next to it opens RivaTuner's own settings. It restarts RivaTuner to do that, so a game's overlay blinks for a moment.

### Fixed
- **Framerate limit key** (Overlay → Behaviour): turns RivaTuner's framerate limiter on and off in games, like Afterburner's limiter key did, with the limit right next to it and a switch. Afterburner's limiter key is taken over by the Afterburner import.
- **Overlay closer to Afterburner**: the framerate and frametime (filled in by RivaTuner) line up in the same column as the other numbers; RivaTuner's own statistics line ("0:27:42 (5 cur, …)") is switched off, as Deck shows those figures itself; the "Like MSI Afterburner" look has a slim graph.
- **Overlay: numbers no longer touch their units** (°C, %, MHz): small units get a small gap of their own size, in the game and the preview.
- **Overlay preview colours now match the game**: a number's prefix and its unit are in the label colour (they took the part's colour in the preview), small units are drawn at RivaTuner's size and raised like in the game, the frametime graph takes the label colour (or the framerate colour with part colours), and a colour that isn't valid falls back to the default as it does in the game.
- Phone remote: the skip buttons next to pause jump 10 s back and forward when the player has no previous/next track (a video in a browser), and quick taps add up; the home page shows CPU and GPU power in watts, and the CPU's package temperature instead of its usage.
- Phone Screen view: the bar keeps the actions (close, full screen, control, sound, keyboard, keys); bitrate, frame rate, slow-connection choice, picture size, video and sound quality are in one Settings panel, each with a line saying what it does.
- Phone Screen view, Auto bitrate: measures the connection first (a short burst the phone answers piece by piece; under a second on a 1 Mb/s line) and uses 80 % of it, leaving 20 % free; on a slow line (under 3 Mb/s) it never climbs past that, so it no longer overshoots and lags while finding the limit. Measured again every 5 minutes; the status line shows the measured line. A set bitrate is the most H.264 uses; it still backs off when the line is busy. The phone's sound takes its share out of the picture's.
- Phone remote away from home was slow (buttons lagged, sent text didn't arrive): every update carried the playing track's artwork, ~170 KB every 1.5 s, more than a 1 Mb/s home upload. The phone now fetches the artwork once a track; updates are ~2 KB.
- Phone sound no longer counts a dropout at every pause in the PC's sound (the first 1.5 s of silence is now sent as silence), and its smallest delay is 80 ms.
- **The phone couldn't connect: scanning the code loaded forever.** Windows Firewall blocked it. When Deck starts with admin rights at logon, Windows never shows its "Allow access" question, so nothing allowed the phone in. Deck now adds its own firewall rule (home and work networks only, not public ones).
- **File pickers opened behind Deck** ("Send a file", Browse buttons) while Deck was on top. They now open in front of it.
- **Deck opened while taking a screenshot** with Win+Shift+S, Snipping Tool or tools like ShareX, Lightshot and Greenshot, when the box started or ended in the hot corner. The corner now ignores screenshot tools, and after a click or drag in the corner it waits until the pointer leaves.

## 2.0.0 — 2026-10-14

The big update. It installs over Deck 1.x and keeps all your settings, profiles and layouts.

### New
- **Make Deck yours**: on first start (and once after this update) Deck asks for your theme, accent colour, opacity, opening animation and low-spec mode. All of it can be changed later in Settings → General.
- **8 themes** (Settings → General → Colour): Midnight (the default), Graphite, OLED black, Pure black, Nord, Forest, Plum and Ember. Your accent colour stays the same.
- **Opacity**: how see-through Deck is, set separately for pinned and not pinned (30–100 %).
- **Opening animations**: Zoom (the default), Fade, Pop, Rise, Drop, Flip, Swirl, Blur in, or None, with a Preview button.
- **Low-spec mode** (Settings → General → Performance, off by default): for older or slower PCs. No animations or soft shadows, and live readings and graphs update every 3 seconds instead of every second. Everything still works.
- **The pin works in both modes.**
  - Quick panel: Deck becomes a small floating window on top of everything, with nothing dimmed around it, so you can use other apps while it stays open.
  - App window: Deck stays on top of other windows.
- **Home, arranged your way**:
  - Drag any tile anywhere, including under each other.
  - Resize tiles both wider and taller from the corner.
  - A guide line shows where a tile will snap to line up with its neighbours.
  - Tiles never overlap: the ones in the way move down.
  - When a tile is made small, its less important parts fold away neatly instead of overflowing.
- **New default Home layout** for new installs and for anyone who never arranged Home.
- **PC tile cards** (Home): CPU, Memory, GPU and VRAM cards, all in the same style: usage, then clock and power (for example "5.3 GHz · 33 W"), then temperature, and a graph. Their rows line up across cards. The new button in the tile's corner turns cards on or off, reorders them, adds a Network card, and hides the drives list.
- **Drives** (Monitor → Drives): the health of every HDD and SSD (S.M.A.R.T.).
  - Shows health, temperature, power-on hours, data written, wear and the warning signs (reallocated, pending and uncorrectable sectors, media errors).
  - It remembers past readings, so a problem that came and went still shows.
  - Optional notifications when a drive's health gets worse (off by default).
- **Disk space, much faster**:
  - On NTFS drives Deck reads the drive's file table directly (the way WizTree does), so a full drive scans in seconds.
  - The treemap is laid out like WizTree's, with **File types** and **Folders** views and a back button.
  - The drive picker switches drives instantly.
- **Overlay has its own page** (Monitor → Overlay).
  - It can install RivaTuner for you.
  - The overlay key now also flips RivaTuner's own "Show on-screen display" switch, so the overlay turns on and off reliably.
- **Sidebar categories can be reordered**: drag a group or a page to move it. Settings → General has a Reset to put the sidebar back. Every group starts folded on a new install, for a short menu.
- **Support report** (This PC) now includes:
  - drive health and past drive problems;
  - the PC's maker, model and type (laptop, desktop…);
  - a quick lights test.

### Changed
- **Power & time** is now the last sidebar group, after Maintenance.
- **Sensors** opens on All readings.
- **Game boost**:
  - "Free memory" now only works when memory is actually short (85 % or more in use). With room to spare it does nothing, since trimming would only make background apps slow to come back.
  - "Turn off by itself" also ends Full power after 3 hours if no game ever showed up.
  - Deck now also spots games it doesn't know, when the program in front keeps the graphics card busy.
  - Picking a CPU profile under "Switch profiles while it's on" turns off "Fastest power plan", because the CPU profile brings its own power plan. The page now says so, instead of the switch just going off.
- **Overlay settings fit narrow windows**: button groups, sliders and the font list move under their label instead of spilling past the card.
- The default sidebar is narrower (180 px).

### Fixed
- **Network speeds were wrong (often double).** Windows lists some adapters twice: packet-capture tools such as Npcap and Wireshark add a filter layer that repeats the same traffic. Deck now counts only real network adapters, each once, using Windows' own counters. With Ethernet and Wi-Fi both connected their traffic adds up. An adapter you plug in starts counting from its next reading, with no false spike. One you remove simply stops counting.
- **RAM lighting ignored Deck after a cold boot**, for example staying lit when lights were set to off. Right after Windows starts, the memory's RGB controllers can be too slow to answer, and Deck never looked for them again. Deck now keeps looking for 10 minutes after startup or wake, and never disturbs sticks it already found.
- **Resizing a Home tile sometimes jumped back** and had to be done twice. A settings refresh in the middle of a drag overwrote the new size.
- **A resized tile went back to full size** after you let go.
- Tiles flickered while dragging.
- Numbers overlapped labels in small tiles.
- Long app names, like "Microsoft Edge WebView2", pushed the volume number out of the Sound tile.
- **The pin did nothing**: its button crashed when clicked.
- The overlay key (Page Up) didn't toggle RivaTuner's on-screen display.
- Deck no longer forces an extra full-window repaint every time it opens, unless the window actually comes up blank.

## 1.1.2 — 2026-10-14

### Changed
- **Sidebar regrouped** so each group has one job: **Hardware** (CPU, GPU, Fans, Lighting, Cooler display), **Monitor** (Sensors, Processes, Network, This PC), **Desktop** (Windows, Display, Clipboard, Sound), **Power & time** (Keep awake, Timers & breaks, Shut down when…) and **Maintenance** (Disk space, Clean up, Startup apps, Tools). The pages themselves are unchanged. Folded groups open again once, since the group names changed.

## 1.1.1 — 2026-10-13

### Fixed
- **RAM and motherboard lighting stopped following Deck after sleep.** RAM RGB sticks lose power in sleep and go back to their own built-in effect, and Deck never took them over again. Deck now re-detects the RAM and reconnects the board lighting a few seconds after the PC wakes from sleep or hibernate.

## 1.1.0 — 2026-10-13

### New
- **Units** (Settings → General → Units): clock speeds in MHz or GHz, network speed in Mb/s (bits) or MB/s (bytes), temperatures in °C or °F. They apply to every page, the sensor table, the phone and the in-game overlay. Numbers you type in yourself (GPU offsets, curve editors, fan curves, temperature limits) stay in MHz and °C.
- **Comet colours** (Lighting → Comet): your own colour, **Cycle** (the comet runs through the colours) or **Rainbow** (a rainbow tail that turns as it flies).

### Faster
- **Hidden windows no longer draw frames.** The page heartbeat used a frame loop that kept the hidden window rendering at the monitor's refresh rate (up to 300 times a second) the whole time Deck sat in the tray. It now checks one frame every 4 seconds. Idle CPU use drops from about 15–20 % of one core to a few percent.
- **Screen and Game lighting** read the screen with DXGI desktop duplication: about 0.3 ms per sample instead of about 23 ms with GDI (20 samples a second while a game runs), and nothing at all while the screen doesn't change. GDI stays as the fallback.

### Fixed
- A long profile name next to CPU or GPU in the sidebar squeezed the page name to "G…" and wrapped onto two lines. The name now shrinks with "…" (hover shows it in full).
- The in-game overlay showed network speed in MB/s while the app showed Mb/s; both now follow the Units setting.

## 1.0.0 — 2026-10-13

The first public release.

### New
- **Power graph** on Sensors → Graphs: CPU package and GPU board power over the last 5 minutes.
- **Frametimes panel**: the last 600 frames, with Now, Average, 1% low, 0.1% low, Lowest and Highest.
- **Customize** on Home and Sensors → Graphs: drag panels to move them, drag the corner to resize, hide panels and bring them back, or put everything back. Drag the sidebar's edge to change its width.
- **Overlay item picking and grouping**: tick several items (Shift-click picks a range), move them together, put them on one line under your own label, or remove them at once.
- **In-game frametime graph** drawn by Deck: 120 points over 5 s to 1 minute (default 10 s), smoothed or showing every hitch, and as wide as the overlay text (or a width you set).
- **Reset key** for the framerate figures, plus Reset buttons on the Frametimes panel and the overlay settings. Handy at the start of a match or a benchmark run.
- **"?" tips** on Fans, Lighting, Cooler display, Sensors, the overlay settings, Game boost and Settings (about 90 in total).

### Fixed
- Average FPS, 1% / 0.1% lows, lowest and highest never worked. They are now read straight from RivaTuner's per-game frametime history and follow the game you are playing.
- A pause (minimising, a loading screen) no longer drags the figures down.
- The overlay now shows within a few milliseconds of switching it on, instead of 1–3 seconds.
- Missing values showed as "?" in the overlay; they now show "-".
- Game RAM sits on the RAM line in the overlay.

## 0.2.0 — 2026-10-12

### New
- **Hardware control**, replacing MSI Afterburner and the motherboard fan tool:
  - CPU profiles (power plans plus clock caps, power limits, a minimum-clock lock with heat guard, turbo-ratio overclock).
  - NVIDIA GPU profiles (power and temperature limits, clock offsets or a voltage/frequency curve, voltage, fan), with Afterburner import and a crash guard.
  - Fans (curves, fixed speeds, presets, always released to the BIOS on quit), Mystic Light and Kingston Fury RGB, USB LCD coolers, sensors with graphs, alerts and CSV logging.
  - Switching from profile cards, the tray, hotkeys, desktop shortcuts, the phone and Game boost.
- **In-game overlay** through RivaTuner: 47 readings, layouts, colours, quick looks including "Like MSI Afterburner", and a live preview.
- **Keep awake** and **Shut down when…** redesigned, with live readings and a 60-second cancel warning. Plans survive a restart.
- **Network** page on one screen: live rates, speed test, ping with Start / Stop, game-server ping.
- **Windows** and **Tools** pages with tabs (open windows, snap zones, workspaces; screen tools, locked files, Windows panels).
- "?" tips on every CPU and GPU setting; a real font list for the overlay.

### Fixed
- Clicks lost when a page refreshed under the mouse; keyboard focus kept across refreshes; accessible names and focus rings everywhere.
- Search: Enter ran the previous result; typo tolerance; kill / close now ask first.
- Calculator: `200 + 10%` = 220.
- Clean up never pre-ticks the Recycle Bin; Disk space locks Windows' own folders.
- Processes that Windows marks critical can never be ended.
- Only a playback device can be made default, never a microphone.

### Removed
- The Apps, Games and Notes pages (apps and games are still in search and on Home). Saved notes are kept in the settings file.

## 0.1.1 — 2026-10-07

### Fixed
- Protection against blank white or black windows from WebView2: browser flags on every window, a repaint nudge after showing, and a watchdog that recovers a window that stops painting.

## 0.1.0 — 2026-09-28

- First version: tray app with hot corner, launcher and search, Home dashboard, clipboard history, sound mixer, timers, keep awake, shut down when…, windows and snap zones, display, processes, startup apps, network, disk space, clean up, screen tools, phone remote, and **Game boost**.
# Changelog

All notable changes to Deck. Setups for each version are on the [Releases](https://github.com/MohammadFakih02/deck-releases/releases) page.

## Unreleased
- Gaming opens with fewer redraws: its background reads share one redraw per frame.

- Pages no longer show an explanation line under their tabs; links to other pages and to Settings are now small icons at the end of the tab row.

- Connections pages redesigned: PC to PC shows who is waiting and which PCs are online above every tab, Phone Connect lists your phones, and Project sync starts with what needs your attention.

### Maintenance
- App-wide look moved to Aurora (refined): bundled Sora and Manrope, glass cards, a fixed sky tinted by each group's hue, sentence-case headings; page layouts are unchanged. Text contrast checked on all eight themes.
- Split page scripts into smaller files for continued interface work; page behavior and styling are unchanged.
- Split supplemental page code into smaller modules for the redesign, preserving existing behavior and appearance.

### Devices
- Device batteries defaults to one clean state ring for the weakest device, with a weakest-first tooltip. The recent two-icon default migrates once; per-device icons and all earlier styles remain selectable.
- Click a battery icon for a compact native pop-up with device rings, names, status/reading age and large percentages. Charging stays green at full; stale readings dim. The pop-up never takes focus and stays hidden during fullscreen apps.
- Optional **Taskbar widget** in Settings ? Device batteries shows symbols and percentages beside the tray, horizontally or vertically. It follows the taskbar and hides with auto-hide, fullscreen apps or no shown devices.
- Visual direction inspired by Joule (AGPL-3.0); no code or assets copied.

### Pages
- Pages no longer open with a big title and description: the page tabs and content start right under the top row, which now holds search and the window buttons.

### Fixes
- CPU profiles keep name and shortcut fields first. Desktop and Start menu switches line up in both profile editors.
- Turbo boost shows its mode and keeps it when switched off and back on. Change the mode in Advanced.
- Long audio device names, voice errors and app volume rows fit narrow windows.
- Voice shows why sounds cannot play when it is on but audio has stopped.
- Bosses shows the selected game and lets you choose another game.
- Drive hours say Not counted when the drive reports zero despite other signs of use.
- Processes says Unavailable until CPU and memory readings arrive.
- Stopped pings show the last run. Live readings show their age in seconds when under a minute.

### Connections
- Open **Devices on this network** on PC to PC to find nearby phones, TVs, printers and Deck PCs. Names stay on this PC. Close the card to stop looking.
- Discovery pauses during games and explains when Windows marks a network Public. Saved Wake-on-LAN PCs have a **Wake** button.

- Choose which Project sync items keep older copies in Settings > Connections. Each starts off, with a size limit, max age and Open versions for recovery on this PC.
- Project sync holds large deletions and batches where every file looks changed. Activity says how many are waiting; open Project sync to Apply anyway or Cancel. Nothing in a held batch is applied.


- PC to PC has a Wake readiness card for this PC: Fast Startup, armed devices, last wake source, wake timers and sender addresses. It reads when the page opens and changes nothing.
- Fast Startup says it may prevent wake. Failed reads say they could not be read. Phone pairing links can include wake addresses for future phone support.
### Power & time
- Groundwork for the Power page redesign: a shutdown plan can be pushed back, and timers can be extended, paused and resumed (the buttons come with the redesign).
- PCs with a battery show design and full charge capacity, cycle count, a monthly trend and available sleep drain sessions in Keep awake.
- Reports refresh at most once a day when you open the page, outside games. Missing readings stay unavailable. Capacity drops past a 5% step appear in Activity.

### PC status
- **Processes** shows each program's **GPU** and **Disk** use, sortable like the other columns. Right now names a program using half the graphics card or 50 MB/s of disk. A program Windows gave no reading for shows a dash with the reason, never 0; a PC without these counters says "n/a". Measuring runs only while the page is open and needs no administrator rights.

- Drive health shows changes in SMART counters over up to 90 recorded days. It warns about new sector and media errors, reported uncorrectable errors and low spare blocks.
- Choose NVMe warning levels in Settings > Notifications. The 80% and 90% life-used levels are suggestions. Drive warnings still start off.
- Drive warnings appear in Activity and can go to ntfy or Discord when you enable Drive warnings in Notifications out. Missing SMART data says “Not available”.

### Hardware
- **Fan ramp limits.** Each fan has Step up and Step down rates under Fans > Speeds, both off by default. Set how fast its speed may change, or use Put back to default. Heat and missing readings still go straight to full speed.
### Maintenance
- Split page styles into area sheets while preserving their contents and cascade order; appearance and behavior are unchanged.
- **Safer duplicate finder (Disk space).** A file that can't be read is counted as "couldn't be read" and is never matched. Several names for one file (hardlinks) are no longer listed as duplicates of each other. Online-only cloud files are never opened, since reading one starts a download; the page says "N cloud-only files skipped". Files are compared by size, then a 4 KB start-and-end fingerprint, then the full contents in 2 MB steps, so **Cancel duplicate check** stops within one step and groups that weren't fully compared are marked "not finished" with nothing to move. The check runs at low disk priority and stops if a game comes to the front.
- **Find empty folders** and **Find broken shortcuts** on Disk space, from the last scan. Each result opens a review where you pick what goes; items move to the Recycle Bin only, are checked again just before they move, and the outcome shows in Activity ("N moved to Recycle Bin, M failed"). Empty folders inside Windows, Program Files, ProgramData or AppData, folders named with a leading dot and folders holding a desktop.ini are never offered (apps often expect them); the page says how many were skipped. Folders or shortcuts Deck can't judge (unreadable, online-only, shortcuts to apps or unplugged drives) are never listed.

### Pages
- **Fans**: fan settings are one table with a single header row, fans without a reading are dimmed, and the new ramp limits sit in a fold that says how many fans are limited.
- **Session reports**: rows line up again, old reports show one clear message, and a session with very little saved frame data says so instead of drawing an empty chart.
- **CPU** and **GPU**: the applied profile comes first, the editor's rarely needed settings are labelled as such (CPU folds are now **Clock limits** and **Windows plan settings**), the lighting colour switch comes after the name, and built-in modes use two or more columns on narrow windows.
- **Arrange windows**: the picked window has its own panel, snap zones are drawn as real layouts, and settings that need a switch say so.
- **Home**: tiles fit their content better, and in Edit Home the clock stays visible and the list of tiles lines up.
- **Clean up** is one tidy list with a heading per group instead of a stack of boxes. Lines that apply to a whole group are said once, empty groups fold away like the rest, and while sizes are being measured the page says so.
- **Settings** reads in one column at a comfortable width, without doubled headings. On narrow windows the list of parts becomes compact chips.
- **Sensors**: Heat check is a slim strip, every device shows on narrow windows, and Alerts has shorter cards with a one-line intro. "Send it out" is now **Send to phone or chat**.
- **Network**: Unusual moments has its own section, the quality strip has a legend, the live graph uses KB/s when traffic is low, and long ping host names wrap.

### Network

- **Trace the path** from an Unusual moment or the Network page. Watch up to 30 hops to the internet-ping target, with addresses, probe loss and delay. Stop at any time and keep partial results; the last five traces stay on this PC.
- A game or Deck microphone relay prompts before a trace starts. Hop loss that disappears farther along says **This hop may ignore pings (often normal)**. Results name no cause and say **No route** when the path is unreachable. IPv4 only.

### Reliability
- Internal: two timing-sensitive tests (a beam retry and a process-deadline check) have wider margins, and the offscreen preview's fake backend now answers the Sensors Alerts and History cards.
- Unreadable memory totals say **Memory unavailable**, missing startup timings say **Unavailable**, and music player or system card support checks offer **Try again** when they fail.
- Sound level meters stay empty and faint when Windows cannot read them. A measured zero still means silence.
- The cooler display leaves a row dark when its temperature or load colour has no reading. Phone speaker quiet mode leaves the PC's sound alone when its original mute state cannot be read, instead of risking an unwanted unmute later.
- **No more made-up volumes.** When Windows will not tell Deck a volume or whether something is muted, the Sound tile on Home, the Sound page, the game bar and the volume pop-up now say **Unavailable** and turn the slider or mute button off, instead of showing 0 %, full volume or "unmuted". The microphone check before a call no longer says a microphone is muted when Deck simply could not read it.
- **Stale data says so.** If Deck stops receiving live readings, Home says how old the volume numbers are, and the hardware pages show their readings as Unavailable instead of freezing them.
- **Failures are named.** A graphics card whose voltage curve cannot be read says so in the profile editor, "Copy my look" offers Try again instead of waiting on "Checking…", and the Home profile tile and the overlay font list say when they could not load.
- Internal: tests now switch a pretend PC off at every write of a tweak apply and a tweak Undo, and cut a PC to PC transfer after each block, in the middle of one, before the rename and before the receipt, then check the recovery. They use in-memory fakes and a temp folder only; no change in Deck itself. They found one gap, listed in `docs/plans/SAFETY_NET_PLAN.md`, now fixed (next line).
- **Undo after a crash.** If Deck or the PC stopped in the middle of applying a Windows tweak, Undo no longer asks you to review a setting that Deck itself had just changed. A setting that something else changed afterwards is still shown for review and is never overwritten without your OK.

### Activity
- **Activity beside search** brings current changes and their existing Put back actions together with recent results and notifications. Each entry is titled with its own message, repeats group with a count, entries show times and page links, and unseen failures show **N failed** until you open it. History stays in memory, up to 100 entries for seven days; sensitive content is omitted or masked. It opens only when asked and creates no extra pop-ups.

### Home
- **Edit Home works from the keyboard.** The All Home tiles list now has a height for each tile as well as width, Move up and Move down name the tile, and Deck announces each move, resize, hide and reset. Two thirds is a width choice, and Fit no longer pushes the hide button off narrow tiles.

### Diagnostics
- **Crashes and hardware errors** in Session reports shows the last 30 days of Windows hardware errors, crashes, display resets, unexpected shutdowns and readable dump summaries. Filter by kind or open a row for its event ID and details. A dump module is a hint, not proof of a cause.
- History reads pause during games and sessions. Sources that need admin rights say so. New entries since your last look appear in Activity without a pop-up. Copied crash reports leave out local file and device details.
- Internal: a test of the Gaming page's session report and game library runs cleanly again (no change in Deck itself).
- **Network tests warn before they run.** The speed test and Lag while busy now say, before you press Start, how long they run and how much they download, and that your connection will be busy. If a game is in front or Deck's phone mic or voice is using your microphone, the card lists what the test would disturb and waits for **Run anyway** or **Cancel**. Nothing starts or changes your network by itself.
- **Right now on Processes.** A small card points out programs using a large share of the processor or memory, full memory, several busy background programs and available high disk activity. Each finding says **Seen** or **Possible**; missing or old readings say **Not enough data**. It lists what it cannot see, changes nothing and uses readings Deck already has.
- **Fair session comparisons.** A word above the table says **Like for like**, **Rough comparison** or **Not comparable**, with short reasons from recorded settings and play time. Different known frame limits or main display modes, or missing FPS readings, keep the numbers visible but replace better/worse claims with **Not comparable**. Short sessions, several changes at once, older sessions without recorded settings, and one session on battery while the other was plugged in are marked as rough. One driver, game-version or profile change can still be compared; the label does not prove an effect.
- **Heat check on Sensors › All readings.** A small card says when something stands out: a temperature at its limit, clocks falling while the processor or graphics card runs near its limit, or a fan at its highest speed while the temperature keeps rising. Each line says how sure Deck is (**Seen**, **Possible** or **Not enough data**), and one faint line names the readings this PC doesn't report. Otherwise it says nothing unusual stands out. It only reads what Deck already measures, changes nothing, and follows your °C/°F setting.
- **Why did it stutter? is more careful about causes.** Each cause and pattern now carries a word: **Seen** (the reading or Windows log entry was there), **Possible** (an indirect sign, such as shader-cache changes or driver time) or **Not enough data**. Wording says what was seen and what it may mean: "Shader caches changed during the stutter" instead of "The game was compiling shaders", "Driver work was high on one core" instead of "A driver held up a processor core". Older sessions show Possible.
- **Says what it could not watch.** Under the verdict, one faint line names any signal missing from the session (Windows event log, shader caches, driver and memory counters, other programs' graphics use), so a quiet session is not mistaken for one Deck could not look into.
- **Unusual moments in Connection quality.** With Record history on, Diagnostics > Network > Overview lists the unusual moments of the last 24 hours: internet pings that got no reply, two or more of a minute's five that went unanswered, or a delay well above the usual, with how long ago and how long it lasted, whether the router answered normally at the same time, and the samples around it under Details. It states what the pings showed, never a cause, and uses only the pings Record history already makes.
- **Copy report.** One button copies a plain-text report of those moments. IP and MAC addresses, Windows user folders and your PC name are removed first.
- **Add connection quality to session reports (new, off by default).** Turn it on in Settings › Games. When Record history (Diagnostics › Network › Connection quality) is also on, a game's session report gets one *Network* line: how many internet pings were answered during the session and a plain statement of what the readings show, or "Not enough evidence to say". It sends no extra pings.
- **Record history keeps the last 24 hours in detail.** Besides the 10-minute averages, Deck now keeps one small sample per minute for up to 24 hours (at most 1,440), so a spike can be looked at later. The Connection quality card says how many it is keeping. Clear history deletes them too. Nothing is added to what Deck pings and nothing is uploaded.
- **Network readings say when they are missing.** The Network page no longer shows 0 ms, 0% loss or a good grade without a reading: a ping without an answer says *No reply*, a host not measured yet says so, an old reading says *Stale* with its age, and an unavailable value says *Unavailable*.
- **Pings keep the reason they failed.** Behind the scenes, a ping that did not answer now records whether it timed out, was unreachable or could not resolve the name, plus when it was taken. The Network page looks the same for now.
- **"Lost" is now "probe loss".** Unanswered pings are labelled as probe loss, with a short explanation: routers and servers can block pings, so they do not prove a game lost packets. Region game-server delays are marked as stand-ins.

### Search
- Searching for microphone, speakers, shortcuts, hotkeys or FPS drops lands on the right page.

### Navigation
- Internal: documented page layout patterns and added unused shared spacing styles; pages look and work as before.
- **Every page starts the same way.** Title, then its one-line description, then search and the page buttons, then the tabs. The description no longer squeezes into a narrow column beside the search box, and on narrower windows the search drops under it. The "Deck sees ..." bar on Game profiles now wraps its buttons onto their own row instead of becoming a thin column.
- **Devices** has a live Device batteries page and the Controller page. Battery preferences stay in Settings; Lighting and Cooler display stay in Hardware with links from Device batteries. Battery tray clicks keep their destinations.
- **Diagnostics** owns Session reports (including Why did it stutter? and session comparisons) and Network. Game profiles links to the reports; existing session, network, search, tray, notification and Home links keep working.
- All eleven sidebar areas scroll in compact windows. Saved orders and hidden-page choices carry over to Devices and Diagnostics.
- **Audio** has four pages: **Mixer** (Playback and Outputs & rules), **Microphones**, **Voice effects** (Effects and Mic chain) and **Soundboard**, with a link to Music & volume pop-ups in Desktop. Nothing inside them changed, only where you find it; old links, search words, the tray's Voice menu and a page you hid before stay where they were.
- **Connections** brings PC to PC, Phone and Project sync together. Settings stays alone at the bottom; Project sync keeps its hidden-unless-on default.
- Saved sidebar orders place new areas beside their default neighbours, and hidden sound and connection pages stay hidden after upgrading.

### Gaming
- Session reports keep gaps when frame data stops arriving and explain when the frame source was unavailable while the game was in front. Sparse recordings no longer get a whole-session smoothness grade.
- **Organise your games** in the Games tab: favourite games stay first, with progress statuses and your own tags. Filter the list by favourites, status or tag alongside Find a game. Choices save at once and stay separate from each game's profile.

- **See what changed between sessions.** The comparison now lists recorded driver, game version, CPU/GPU profile, frame-limit and Deck-version changes under **What was different**. Unknown details are left out; older sessions explain what they did not record. Graphics driver versions currently come from NVIDIA; game changes use the executable's file version or, if absent, its modified date. Frame limits come from RivaTuner, not in-game settings.
- **Compare two sessions of the same game.** In "Why did it stutter?", pick an earlier bar under *This game over time* to see it beside this session: average FPS, 1% and 0.1% lows, hitches an hour, time lost to hitches and play time, each with how much better or worse it got. Useful for checking a driver, setting or frame-limit change: play the same part before and after. Short sessions are marked as rough, and missing measures say *Unavailable* rather than showing a guess.

### Voice & soundboard
- **MicDrop is now part of Deck**, under Audio as **Voice & soundboard**. Three tabs bring together voice effects, a mic chain (noise suppression, gate, EQ, compressor and limiter) and a soundboard with separate levels for you and others.
- **Controls in the tray and on your phone:** the Desktop tray menu has a Voice submenu, and the phone remote shows a Voice card while it runs, with effects, mute, stop sounds, clean voice and sound buttons with favourites first. The phone microphone goes through the voice's mic chain and effects too.
- **Get VB-CABLE from the page.** Deck downloads VB-Audio's own package and opens its setup. An optional switch makes CABLE Output the default mic while the voice runs and puts the old mic back afterwards, or at the next start after a crash. It starts off.
- **Bring in MicDrop's settings:** import its sounds, effects, mic chain and device choices without changing MicDrop's own files. Quit MicDrop first; importing does not turn the voice on.

### PC to PC
- **Sending from the command line waits for its own transfer.** `deck.exe --pc-send` reported on the oldest transfer in the saved list instead of the one it had just started, so it could print "Done" with another file's name at once and quit while the other PC was still asking. The receiving PC was then left with an offer nobody was waiting for. It now follows only the new transfer to the end.

### Phone app (0.5.0, 0.5.1)
- **Staying connected on phones that close apps on their own.** Settings has a new "Stay connected" card with three one-time steps, each opening its screen and showing ✓ when done: let Deck run in the background, turn Deck on in the phone's Auto-start list (Tecno, Infinix and itel Phone Master; Xiaomi, Oppo/Realme, Vivo, Huawei/Honor and Samsung lists; shown only when the phone has one), and Battery → Unrestricted (also turn off "Stop app when idle"). On Tecno, Infinix and itel, a phone given Deck's one-time permission from a PC adds Deck to the freezer's exemption list by itself. Tecno's freezer was found pausing Deck in the background, which dropped the link and showed "Looking for your PC".
- The app's version is now 0.5.0, so phones show the new build as an update.

- **Main screen:** Quick actions come right after the stats; Power is a small neutral button so the PC name fits; one line under each stat ring; seek buttons read 10s with rewind/forward icons; All apps sits on the volume line; profile tiles leave out the profile already on and have room for their numbers; open profile lists no longer touch the next card.
- **App size and Text size** (Settings): 100/90/80/70% for everything, and Small/Normal/Large/Larger for text alone. Below 100% the stat rings and Quick action buttons grow back into free space.
- **Stay connected:** the Auto-start step no longer claims to be done (phones don't report it); the freezer exemption is shown separately and checked after it is written.
- **Disconnects:** the app logs why each link ended; the home-again check can't stall the link and switches back without a delay.

### Phone remote (PC)
- **Fewer phone drops:** the Tailscale address is read from a cache refreshed in the background, so a slow `tailscale status` no longer holds up the phone's updates; turning the phone remote on while it runs no longer restarts it; after a restart the usual port is retried before another. The log says why each phone left and warns when building the phone's state takes over 3 s.

### Releases
- **The phone app is no longer carried over by mistake.** 4.6.0's `Deck.apk` was 4.5.0's app, so the new phone app never reached phones. Releasing now stops when the app changed and no new `Deck.apk` is given, or when its version number wasn't raised.
- The code checks that run before a release pass again (an unused leftover was removed).

## 4.6.0 — 2026-11-17

### Power & time
- **Shut down when a task says it's done.** A new condition for **Shut down when…**: Deck waits for the programs that signal it, and acts only when every one has been finished for the minutes you set. Made for long jobs in coding tools, which keep working in the background after they seem to stop.
  - **One switch per tool.** Deck can add its signal to Claude Code and Codex for you and take it out again; your other settings in those tools are left as they are. Any other program or script can send the same signal with one command shown on the page.
  - **It knows the difference between done and paused.** A task with background jobs still running, or one that will wake itself up again, is still working. A task waiting for your permission or your reply holds the plan (or counts as done after the minutes you choose). A task that stopped with an error or a usage limit holds the plan unless you say it counts as done.
  - **You see who it waits for,** with a **Don't count** button beside each task. Signals sent while Deck is closed are picked up when it starts.

### Gaming
- **"Why did it stutter?" (was "Why did my FPS drop?") is rebuilt to explain a whole session, not only single dips.**
  - **A verdict for every session:** Smooth, Mostly smooth, Some stutter or Rough, a one-line diagnosis, and the figures behind it: average, 1% and 0.1% lows, hitches per hour, the share of time lost to hitches and the slowest frame.
  - **A timeline of the session:** FPS with its 1% low, every hitch, everything Windows logged, and a numbered pin for each saved moment. Point at it for the figures of that stretch; click a pin to open the moment.
  - **What the stutters have in common:** a hitch that comes back on a timer (the classic sign of RGB, fan-control and monitoring apps, Wi-Fi scanning or a device reconnecting, which Deck names when it lines up), shader compiling, one cause that keeps coming back, and driver or drive resets.
  - **Many more causes, read from Windows without touching the game:** the graphics driver saving new shaders, drivers holding up a processor core, memory read back from disk, another program using the graphics card, a program that just started, and the system event log (graphics driver resets and errors, a device connecting by name, drive resets, hardware errors, the firmware limiting the processor, battery and mains switches, Windows Update and Defender).
  - **What to try for each cause,** with a button to the Deck page that helps (Apps to close, Free memory, Fans, GPU, Drive health, Network, Startup apps).
  - **Moments are numbered like their pins,** with a count of their causes you can click to show only those, and a strip of the slowest frame of each half second around each one.
  - **This game over time:** hitches per hour for its last twelve sessions, whether this one was smoother or rougher than usual, and whether shader stutters are fading.
  - **Session reports** open the same view for that session.
  - The panel no longer flickers while the Sessions tab redraws every second during a game; an open session report no longer shows "Loading" again each time.
- **"Why did it stutter?" lists only what you would notice.** It used to record any single late frame, so a steady 60 FPS game filled the list with entries like "60 → 62 FPS". Now a drop must stay down (a fifth under the usual speed for a second and a half, or a third under for half a second), and a stutter needs one long frame of 100 ms or more, or two shorter hitches close together.
  - **Drops and stutters are told apart:** a stutter reads "Stutter at 60 FPS · longest frame 85 ms" instead of two nearly equal speeds, and a speed is never shown going up.
  - **Menus, cutscenes and frame limits are left out:** a smooth lower speed while the graphics card and processor have less to do is the game easing off.
  - **One bad stretch is one entry** (trouble within 10 seconds merges), and a long session keeps its 20 worst moments instead of its 20 latest.

- **Game names and pictures:** a game found through Windows’ list of installed programs no longer carries the installer’s additions in its name (“XCOM Enemy Within version 1.0” is now “XCOM Enemy Within”). A game that Steam sells as an add-on of another had no picture on Home and in Game profiles; it now uses the pictures of the game it belongs to.

### Flyouts
- **The music flyout no longer opens when a song ends by itself** with **When the next song starts** switched off. Some players stop for a second while the next song loads; Deck took that for a pause and a resume and showed the card for each. A pause the player takes on its own right after a song change, and the resume that follows it, are no longer announced. Pausing yourself still shows the card.

### Game pictures and detection
- **Pictures that failed once are no longer missing for a week.** A picture asked for while the internet was down (just after logon) or while a site was busy was remembered as "none"; now Deck tries again later. Pictures already missed that way are asked for again once.
- **More games get their pictures:** the picture you set in Steam yourself comes first; older and newer Steam layouts on your PC are read; newer Steam games whose pictures moved to new addresses are found; Epic pictures from all of Epic's image servers and kinds load; and a game known only by its program's name is also looked up by its folder's name.
- **Gentler on the sites:** one picture request at a time, the same picture asked for by two cards is fetched once, and nothing is asked for a while after the network failed or a site said to slow down.
- **Steam's own word on what is a game.** Steam apps the store calls software (Wallpaper Engine, Blender) are no longer listed, and new games are never left out for a name nobody listed. Names are now matched as whole words, so games like *Assassin's Creed Origins* are no longer mistaken for a launcher.
- **Fewer false games:** Wallpaper Engine's window and anti-cheat starters (such as Fortnite's EasyAntiCheat starter) are no longer recorded as games, and old sessions of them are hidden. *Crash Bandicoot* and *Call of Duty: Vanguard* are no longer mistaken for a crash reporter and an anti-cheat. New games without a store are recognised by what only games ship (DLSS, FSR, XeSS, GameMaker, Ren'Py, FNA, MonoGame, LÖVE).

### Pages
- **Open folds are one box.** A folded section that is open now keeps its settings inside the same border as its title bar, with a line down the side, so it is clear where it starts and ends.
- **Controller overlay page is shorter.** Per game moved beside Look and Position, so the two columns end together instead of the right one running a third of a screen further; **Reset overlay** is a button that asks first instead of a fold.
- **Death counter › Games: the Game picker shows the game whose screens are shown.** A game with no deaths yet was missing from the picker, which then showed another game's name above it.
- **Battery tray icons follow the taskbar:** on a light taskbar they are a dark battery on white (they were a white battery with a dark rim, muddy there), and switching Windows between light and dark redraws them.
  - **One icon for all devices** (Settings › Devices › Look): a single tray icon for the device with the least battery; pointing at it lists every device, the weakest first.
- **Sensors › All readings redesigned.** A device's readings are one table grouped by what they measure, the unit shown once beside the current figure, then Lowest, Average and Highest. The Cores and Fans tables show performance and efficiency cores under their own headings, and a switch chooses between **Now and highest** and **Lowest, average, highest** (this replaces the long "Minimum and average per item" list underneath). **Where these readings come from** is a plain list: each collector once, and only the readings that stopped updating are named.
- **Windows tweaks name what a press does:** an on/off setting shows its state (**On** / **Off**) and a **Turn off** or **Turn on** button instead of a switch; a setting with mixed parts has **Turn all off** and **Turn all on**.
- **Disabled buttons and drop-downs look disabled:** a dashed outline and faded words, instead of looking almost like the enabled ones.
- **Smaller layout fixes:** a button beside a labelled field lines up with the field (Display's night colour and test pattern); the Game servers list lines up with the rest of its card.
- **Death counter › Games is tidier:** each game's deaths are shown once (All games keeps only the deadliest bosses); the shared library's count sits in the Death-screen library fold; the stray "+1 death" row at the bottom is gone (adding a death is on Now); Learned screens is one card with sections instead of cards inside a card; "2 of 3" reads "2 (keeps up to 3)"; **Pick another** once a screen is learned; the kill-screen choice is a real button (**This game has none**); and only the guess question's **Yes, that's it** is highlighted.
- **CPU and GPU editors read properly in narrow windows:** a slider row's label and description sit above its slider instead of being squeezed beside it (the CPU editor's descriptions broke every two words); GPU labels keep their help mark after the last word, values like "+500 MHz → 11001" fit on one line, and the "Runs at … at most" note has its padding back.
- **Death-screen library says where a friend's code comes from** (Share with a friend, under that game's learned screens) and sits inside its fold without a second frame.
- **Controller › Test: Device details no longer flickers** under the pointer, and the test redraws only when a reading changes and never during a click.
- **Windows tweaks: the category list no longer flickers** when you switch categories.
- **No line above the first setting of a card** on the Performance overlay and status pages.
- **Scrolling no longer jumps back while a page updates.** Pages that refresh every second, like **Recent sessions** while a game runs, pulled the scroll back a little each time; they now wait until you stop scrolling.

### PC to PC, phone and Project sync
- **PC and phone transfers:** Verify the PC at the selected address, fail unreadable project offers safely, reserve receiving folders, verify resumed files, and remember completed uploads and transfers so a lost reply cannot duplicate them. Empty projects keep their root folder. Phone control releases held mouse buttons when paused, upload cleanup only removes Deck part files, and pending Android layout edits survive other clients' broadcasts. Connection and storage errors explain what to check.

- **Workspace / Project sync:** Keeps edits made during sync and versions received from different PCs, preserves session branches, and waits for complete backups, folder scans and cloud uploads before passing changes on.

- **PC to PC:** Control opens a paired PC's screen in your browser after its user allows it, over the home network or Tailscale. Phone and Screen settings on that PC still apply.

- **PC to PC:** Compact recipient, offer, transfer, sharing and app layouts adapt to narrow windows.

- **PC to PC:** Incoming offers clear when the connection ends, and a failed connection reports that the sender should try again.


## 4.5.0 — 2026-11-14

### Clearer controls and steadier pages
- **Deck recovers while starting:** when its background part is slow or unavailable, a plain message appears and Deck retries with increasing delays, opening by itself when it answers.
- **Script errors use plain words** with the full details kept in the log. Missing readings show a dash, and an incomplete timer no longer shows NaN in the sidebar.
- **Switches say On or Off** beside the control; rows that already spell out the state keep their own wording. Empty tick boxes and off switches have stronger outlines across all eight themes.
- **Page titles stay on one line:** the search row moves underneath when needed, and hovering a shortened title shows its full name.
- **Keyboard focus is easier to follow** on navigation, profile cards, app rows and preview choices. Scrolled pages keep their place when readings refresh or controls redraw.

### Search
- **Search finds every control, not only the pages you have already opened.** Capitals and accents do not matter ("Clípboárd" finds Clipboard), words can be in any order, simple plurals match, and one wrong, missing or swapped letter is forgiven in words of five letters or more ("tempezature" finds Sensors). Short words are never guessed at.
- **Better order:** the strongest page or tab match leads individual controls. **Fan** and **fans** lead to Fans, **HDR** to Display, **theme** to Settings > Appearance, and **uninstall** to Apps > Installed. Other matches keep their order and variety. Eight Deck results show first, with a **More Deck results** row.
- **Landing is exact:** a result for a setting opens its page and tab, opens any fold around it, scrolls to it and marks it for a moment. If the setting is not shown with your current options, Deck says so instead of landing nowhere.
- **Nothing found** now says so and offers up to three nearby page or tab names beside the web search.
- **Typing quickly is steadier:** only the newest search runs, an old answer can no longer replace a newer one, and Enter runs the row you see. Saved quicklink keywords beat ordinary name matches, and an app and a Deck page are ranked by the same rule. The finder inside Settings uses the same matching.

### Gaming
- **Performance overlay:** corner choices form a screen-shaped map. The status and preview explain whether RivaTuner is drawing over a game, waiting for one or stopped, and when the preview is smaller than the real overlay. **Frame limit** has its own section under Behaviour, with the current global limit and a clearer explanation of per-game limits.
- **Controller › On screen** fits more settings beside the preview, with corner choices arranged like the screen's edges.
- **Death counter › Games** folds learned death and victory pictures behind a count and the last-learned time.
- **Game bar:** each preview widget is one keyboard choice, with a visible focus ring.

### Hardware and PC status
- **Shorter CPU and GPU pages:** compact built-in modes and applied-profile rows show more at once. Requested settings are clearly separate from measured readings.
- **Profile editors:** Back to CPU asks before dropping unsaved edits. The GPU editor distinguishes unsaved edits, settings being tried, later edits and partial failures; its cancel button says what it will discard or restore.
- **Missing readings and devices** have clearer explanations and next steps, including read-only fans, cooler display connections and a retry when This PC cannot read the parts list.
- **Fans › Fan speeds is rearranged:** every fan is a tile of the same size with one line each: its name, its RPM and the control signal it is sending ("25% signal", a signal and not a measured speed). A tile names its mode only when it differs from the **All fans** choice. A fan reading 0 is dimmed and says "No reading". Columns are chosen so the last row is never a single tile.
- **Lighting:** the preview is now above the settings, so a change shows without scrolling back.
- **Fans, Lighting and Cooler display wording:** the help says **Apply hardware changes** where it said "Apply", and the fan preview is called "Preview a curve" (button **Run preview**).

### Switches, sliders and editors now tell the truth
These came out of reading every page's code and clicking through the installed app.
- **A switch that could not make its change goes back** to where it was and says why, instead of staying flipped. A second click while the first change is still being made is ignored. This covers Sound & mic, Windows rules, Network history, the Send-to menu, Phone, the Death counter's per-game switch, the Performance overlay's RivaTuner tray switch and Windows tweaks.
- **A setting that fails to save leaves the page showing the real value.**
- **Settings saves are retried.** If Deck cannot write its settings, a notification says **Settings could not be saved** and Deck keeps trying (after 2, 4 ... up to 60 seconds) until the folder is writable. A settings file Deck cannot read is no longer replaced by defaults.
- **The CPU and GPU editors ask before dropping edits** whichever way you leave: Back, the sidebar, a page tab, a search result, or opening another profile's editor. **Keep editing** and Escape leave everything as it was. The GPU editor puts the card back to the saved profile first if a test is on it.
- **Sliders:** letting go outside the window no longer leaves the page waiting. Home volume sliders send fewer writes while you drag and end on the exact value. Display **Brightness** and **Contrast** end on the value you released, and go back to the monitor's real value when it refuses.
- **Free-space figures agree.** Disk space, Drive health and This PC show the same decimal GB for the same drive (This PC used to divide by 1024 and call it GB, so it read about 7% lower). Disk space says when the scan was made and shows the current free space beside it; This PC's weekly Disk space tile says when it was checked, and no longer calls the lowest-free drive "the fullest".
- **Notifications never drop the shutdown warning.** When more than four are showing, the oldest other one goes, not the shutdown or sleep warning with its Cancel button.
- **Failures you could not see are now shown:** starting a Clean up scan, ending a locked process that Windows refuses, copying to a refused clipboard, adding a ping address or host when the setting cannot be saved, a failed Apps to close or Built-in apps list (with **Try again**), a failed Sensors history read (with **Try again**).

### Page fixes
- **Death counter:** the automatic-counting line says counting is off when it is off for that game; **Confirm boss** reads "Confirm boss: <name>". Every Death counter setting has a **?**.
- **Game bar:** the **Drops** widget shows how long ago a dip was, not a huge number; letting go of a slider outside the bar no longer stops it refreshing or closing; the **Deaths** widget says when the counter cannot be read instead of offering to turn it on; every widget has a **?**.
- **Game profiles:** **Why did my FPS drop?** says it covers the current or last session; **Apps to close** loads once per visit and has **Refresh** and **Try again**.
- **Performance overlay:** opening **Start from a preset** no longer throws the page down.
- **Clipboard:** the arrow keys, Delete and Enter work after you click an item, and act on the item that has focus.
- **Disk space:** recycling a folder you have open drops it from the tree, the type list and the bar. **Build a space plan** asks for a number instead of sending nothing.
- **Clean up:** the **Show N with nothing to clean** button's spoken name matches its words and keeps focus when the count changes.
- **Display:** a scale the monitor refuses puts the list back; an emptied schedule time box is ignored.
- **Apps and Windows tweaks:** the filter and sort groups have their own names for screen readers; the Windows tweaks filter is "Show which tweaks".
- **Fans:** Calibrate no longer redraws another page while it measures, and an empty fan list no longer breaks the extras tab.
- **Network:** **Lag while busy** no longer piles up redraws; App updates without winget says so once.
- **Settings:** Features › Desktop › **Review window rules** opens the rules tab; the Settings tour finds its step; **Check every** in Project sync reads "1 minute".
- **Help:** 21 **?** marks were added (every Game bar widget, Virtual display, nine Death counter settings) and 68 existing ones were corrected against the code (button names, defaults, limits, what turning something off does).

### Maintenance, Settings and Power & time
- **Clean up** folds long groups of measured-empty rows behind a Show button, keeping selected and unmeasured rows visible. The review describes only the selected kinds of clean-up.
- **Disk space:** the folder explorer comes before Disk tools.
- **Apps:** row details wrap, missing uninstall options have an explanation, and selecting an app keeps keyboard focus. The filter says it searches this list by name or publisher, and the details explain when a filter hides your selection.
- **Startup apps and Startup optimizer** distinguish an empty list, no search matches and a failed reading, with clearer startup-state wording and an **Analyse** button.
- **Settings › Features** uses columns and shorter related links; pages hidden with their whole area say **Hidden with area**. Connections uses columns in wider windows.
- **Timers and shutdown plans** show the clock time they are waiting for, including the day when needed, and explain what Cancel stops.

### Under the hood
- **Quieter logs:** a CPU custom power-limit clamp warns once for the same requested and held limits; Target FPS reports a missing reading once per episode. Music pop-up timing details are logged only on activity or when a stage is slow.
- **Better game detection:** settings and editor front ends, including a wallpaper program's settings window, and known wallpaper renderers no longer start game sessions automatically.
- **Steadier window placement:** a correctly maximised window is no longer moved back because its outer frame extends past the monitor.
- **Less background work:** Tailscale state is checked at most every five minutes while Deck's main window is hidden or Tailscale is not running. PC to PC skips peer discovery while switched off.
- **Lighter while hidden:** with the music pop-up on and no song loaded, Deck no longer watches the skip keys and checks for a player every 5 seconds instead of every second. Pages stop asking for updates while the window is hidden and refresh when it opens. A switched-off game bar, hot corner, battery list or plain-copy helper does almost nothing, and the shares file is saved only when it changes.
- **Hardware and files fail loudly, not quietly:** switching a CPU or GPU profile from the page returns the real outcome, including a profile that was saved but could not be applied; an unreadable GPU crash mark holds a risky profile instead of being treated as missing; snippet and sound-profile saves report a failed write and change nothing in memory, and a device preference with one invalid field is rejected whole instead of half-applied; Deck's stores no longer write an empty file when serialising fails; caches that could be cut short are written atomically.
- **Commands stay off the UI thread:** audio, display, startup, network and search commands run on blocking threads; process waits for Windows tasks, setup snapshots and icon refreshes have time limits.
- **Bad input cannot crash Deck:** damaged NTFS file-table records, non-ASCII curve and registry text, oversized numbers (timers, ids, ports, DWORD values), a bitmap with an impossible height and a malformed installer code are rejected with an explanation.
- **Busy flags clear after a failure:** a failed index, Clean up scan, speed test, lag check or calibration launch no longer leaves the feature stuck busy.
- **Testing tools and developer guide:** `tools/testing/check-wiring.mjs` (UI calls against Rust commands, setting keys, events and ids, with its own tests), `tools/testing/check-search.mjs` with its `search-*.mjs` helpers and the generated `ui/search-index.js` (regenerate with `--write-index`), `docs/DEVELOPING.md` and `docs/TESTING-CHECKLIST.md`.

## 4.1.0 — 2026-11-12

- **Tidier app list (Maintenance › Apps):** Uninstall, Review removal and the folder button sit on one line at the right, in the same place on every row; the install date is no longer cut off, and an unknown date is left out instead of saying "Unknown".
- **Windows tweaks use switches:** a setting that is simply on or off is a switch, like the rest of Deck. The On | Off buttons with "Off" filled in looked like a switch turned on.
- **What Deck changed says what changed:** each row shows **Now** and **Before** in plain words ("Ads and news in Edge — Now: Off, Before: On"; "Fan speeds — Now: Deck sets them, Before: the motherboard") with its area above it, instead of "From" and "Ends" notes.
- **A tidier top bar:** the "Deck is changing N things" button sits on the search row instead of a line of its own, so Edit Home and the other buttons line up, and the search box is longer on every page. **Settings › Appearance › Show what Deck is changing** hides it (What Deck changed stays in the tray menu).
- **Quieter page row:** the row of pages in a group lost its box; the open page is filled in and the group name is grey with a dot in the group's colour.
- **Search waits for you:** opening Deck no longer focuses the search box; clicking it or typing still starts a search.
- **Clearer controls:** sticky panels cover the content beneath them, option toggles have a filled selection, and page section tabs keep their underline.
- **Change counts explain their scope:** the top-bar tooltip lists the areas it counts, and Windows tweaks says its count covers Windows settings.
- **This PC:** storage sizes match Windows, C: comes first, peak times show local hours and minutes, unavailable controls use neutral chips, and the weekly tiles line up.

### Every page, checked
Every page and tab was read top to bottom, scrolled, and fixed where it was wrong, cut off or unclear:
- **Gaming:** the overlay preview's buttons have names and no longer cover the readings; Game bar sliders show their range; empty shortcut boxes say Set shortcut; death counter and session numbers line up.
- **Hardware:** CPU, GPU and fan profile summaries read in plain words ("41% power · fans 30%", "No speed limit"); GPU modes are listed slowest to fastest; lighting status lines are plain sentences.
- **PC status:** sizes on Disk space, Clean up and drive pages use the same units as Windows; a nearly full drive says so; latency tests say Testing… while they run; Deck itself is labelled in Processes.
- **Desktop:** microphone, clipboard and flyout buttons have text labels, duplicate media sessions are gone, the sliders line up.
- **Maintenance and Power & time:** the force-close switch says unsaved work is lost; update tabs share one Check for updates; uninstalling Deck, runtimes or drivers warns more clearly; apps without an icon get a letter.
- **Home, Phone and PC to PC:** the pairing card shows once above the tabs, the PC to PC switch sits in it, the transfer log is behind Show log.
- **Settings:** plain labels for opacity and appearance, the death counter settings in one column, clearer Store update wording.
- **Windows tweaks:** the category list scrolls on its own and keeps the selected one in view; settings that are partly on show Mixed; long options fit on one line and say which is Windows' default; Unpin all and turning Recall off ask first; a changed setting says what it was before; fewer, clearer tags.

### Easier to find your way
- **Plain names for everything.** The sidebar groups are now Gaming, Hardware, PC status, Desktop, Maintenance and Power & time, and pages say what they are: Game profiles, Performance overlay, Death counter, Drive health, Arrange windows, Sound & mic, Music & volume pop-ups, Windows tweaks, Project sync. The old names still work in search, and your own order of groups and pages is kept.
- **Every page says what it is for** in one sentence under its title.
- **A group opens its first page**, every time, and the row of pages above it is labelled "Pages in Gaming" (or whichever group you are in).
- **CPU and GPU start with the one-click modes**, each with a line on what you get (quieter, cooler, faster). Your own profiles are below them.
- **Deck game mode is honest when it has nothing to do:** it says no changes are selected and offers Choose changes, instead of reporting itself as on.
- **Fans and Lighting:** Quieter fans is on the Speeds tab, and Lighting opens with Colour. Labels use plain words (the technical name is in the ? help), and buttons say what they do: Apply hardware changes, Discard pending changes.
- **Search finds everything:** every tab and every setting is a result, with the place it leads to (for example Network › Tests, or Settings › Device batteries), and opening one takes you to the exact row, highlighted. Technical terms and the old page names work too. The finder inside Settings finds settings the same way.
- **Show only what you use:** Settings › Features hides whole areas or single pages from the sidebar, search, Home and the tray menu. Hiding never stops or changes anything; each row says what keeps running and where its switch is. Show everything brings it all back.
- **A shorter tray menu,** with the common actions first.
- **What Deck changed:** when Deck is changing something on your PC, a chip in the top bar says so ("Deck is changing 3 things"). It opens the list with Put back for each change and Put everything back. The list says which kinds of change it does not cover yet.
- **"I want my PC to be…" on Home:** Quieter, Faster in games or Use less power. Each shows exactly what it would change before you apply it, and can be put back. (New installs get it when the PC has CPU or GPU modes; add it to an existing Home in Edit Home.)
- **One name for each thing, and words that say what happens:** Deck game mode (no longer also called Boost), Put back for restoring what was there before, Discard for dropping unsaved edits. About 45 settings gained a line that says what they do, and buttons name what they act on ("Apply selected tweaks", "Stop scan").
- **Settings is in the same order as the sidebar,** with Features near the top; Devices is now called Device batteries.
- **Fixed:** the top bar wrapped the window's close button onto a line of its own and kept an empty row when Deck changes nothing; the suggested CPU and GPU mode (Balanced, Normal) was painted like the selected one; a page's own tab row was announced to screen readers as "Pages in <group>".
- **The guide has a new first page, Find your way around,** and every guide page starts with where to find the thing it describes.

### This PC, rebuilt
- **Your PC at a glance:** a spec sheet with the board or laptop model, processor, graphics with its driver version, memory with the speed it runs at, storage, every display with its resolution and refresh rate, Windows with its build, the BIOS with its date, and how long since the last restart. **Copy specs** puts it on the clipboard as plain text.
- **Free speed it points out:** memory running below its rated speed (turn on XMP or EXPO) and a monitor running below its highest refresh rate (with Open Display) get an amber line.
- **This week as five tiles** (Temperatures, Drives, Disk space, Sensor alerts, Deck) instead of a list of sentences, each with Fine, Check or Act now, opening its page when clicked. Times are your local time.
- **One list of what Deck can control here** (Works, Partly, Read only, Not available) instead of two tables with different words.
- **The support report moved to Settings › About**, next to Diagnostics.

### New start
- **A new start for new installs:** Deck opens on Home with a short introduction (what Deck is, how to open it again) and a First steps list for this PC. Both can be dismissed for good. Tours no longer start by themselves; they are on each page's tour button.
- **A simpler Home** for new installs: Sound, Pinned & frequent apps, PC readings and Power & timers, with music and the current game only when there is something to show. Your existing Home is untouched; Edit Home offers Try simpler Home, and Cancel puts yours back.

### Added
- **Logitech batteries:** wireless Logitech mice, keyboards and headsets on a Unifying, Bolt or Lightspeed receiver (or connected directly) now show their battery in Settings › Device batteries and the tray. Deck only sends read requests, about every 5 minutes per device, and a device that doesn't answer is hidden and asked less and less often.
- **Device readers are gentler:** a headset, mouse or receiver whose connection fails is no longer written to every 2 seconds; it is left alone for 5 minutes and then for longer. A headset reply is only taken when it echoes the request, so a volume knob or another program's traffic is never read as a battery level. A Logitech battery status of "charged" no longer counts as charging.
- **More batteries:** a connected Bluetooth LE device that gives Windows no battery level is now asked for the standard Battery Service level (about every 5 minutes, never the typing and pointing part), and devices with a standard HID battery report (uninterruptible power supplies, some headsets) show up too, ranked below every other source.
- **Razer mouse batteries:** Razer wireless mice (DeathAdder, Viper, Basilisk, Naga, Cobra, Lancehead, Mamba, Pro Click) now show their battery and charging state, read about every 5 minutes with the two read requests Razer's own software uses. A call that doesn't return in time is cut off and that mouse is left alone until Deck restarts.
- **Headset batteries:** wireless headsets on their USB dongle (SteelSeries Arctis 7, Pro and Nova 7, Corsair Void and HS, HyperX Cloud Alpha Wireless) now show their battery, read about every 5 minutes with the one request the maker's own software uses. A headset that is switched off disappears from the tray. A Logitech mouse or keyboard switched on after a long time off now appears within about 5 minutes (it could take up to 30).
- **Settings › Device batteries:** one place for the battery of your controllers, headsets, mice and keyboards (with Colour by level, the icon is green while charging and red when low). Choose the tray icon style and which kinds of device get an icon; for each device set its name, tray icon, warning level (Never to 50%) and whether the warning shows over games; forget devices that are away; copy a device report (without names, addresses or serial numbers) when a device shows no battery. The Controller battery switches in Settings › Games became a link to it. Copying the report never freezes Deck, and the keyboard focus stays on the control you changed.
- **Device batteries (in progress):** the controller battery code now covers any device kind; Bluetooth headsets, mice and keyboards that report a battery are now read, like controllers, and only while connected (the Controller page's battery switches keep working). Each device can have its own tray icon, with a symbol for its kind (controller, headset, mouse, keyboard); clicking a controller's icon opens the Controller page, any other opens Settings.

### Changed
- **Deck quits faster**, and so installs and updates finish sooner: it no longer waits up to a second for its fan and sensor readings to finish before handing the fans back to the BIOS, and the setup checks every tenth of a second whether Deck has closed.
- **Deck starts a little faster:** the list of drives is read just after the start instead of during it (it could also wake a sleeping hard disk).
- **No more short freezes of the window and tray** when Tailscale is installed: reading its address ran on the thread that draws them.

### Fixed
- **Virtual display turns on again after a restart.** A virtual display that was off when the PC restarted couldn't be turned on any more: Windows doesn't load a turned-off virtual device after a restart, and turning it on stopped with "The device is not connected". Deck now sees this and makes the device again from the driver that is already installed (nothing is downloaded; one admin prompt when Deck runs without admin rights).

## 4.0.3 — 2026-11-10

### Fixed
- **Updates work again.** Since 4.0.0, a Deck installed in Program Files downloaded an update to 100% and then stopped with "The setup could not be retained": the small record kept for Go back was refused in Deck's own protected updates folder. Copies on 4.0.0 or 4.0.2 can't update themselves to this version, so install 4.0.3 once from the release page; updates work by themselves after that. Old setups in that folder are cleaned up again too.
- **Media flyout volume (with "Volume with music" set to one card):** the level shows whole percents while you drag (it showed numbers like 40.963855421686745%), and it no longer jumps back to the old level in the middle of a drag.
- **USB drives can be ejected again while Deck runs.** Deck kept every disk open for its drive temperature and speed readings, so Windows said "This device is currently in use". It now opens a disk only for each reading and closes it at once, and finds disks plugged in or removed while it runs (every 30 s).

### Changed
- **Sensors › All readings:** the device list and the details scroll separately, each within the window, so every device in the list can be reached while the details stay put.
- Releases can be published by either maintainer (the publish step no longer needs one particular GitHub account), and from a maintainer's PC when the automatic build service is unavailable.

### Added
- **Android app on the release page:** every release now attaches the app as `Deck.apk` with its checksum, so the Phone page's "Get the Android app" QR code works. It is signed with Deck's own release key: if you installed an earlier test copy of the app, uninstall it once first (Android refuses an update signed with a different key), then pair again.

## 4.0.2 — 2026-11-10

### Added
- **Starter profiles:** a fresh install with no profiles of your own gets three editable CPU and GPU profiles once (Gaming, Everyday, Quiet), copied from the built-in modes this PC has.
- **Support report:** new parts list the makers' control and lighting apps, the firmware's ACPI devices and every HID device with its IDs and report sizes (read from Windows only, no serial numbers), so laptop fans and keyboard lighting can be added.

### Changed
- **Active changes** is now a Home tile, hidden by default: turn it on in Edit Home and place and size it like any other tile. The tray's Active changes opens the list in a window, even while the tile is hidden.
- **Fans and Lighting** no longer vanish or sit empty on PCs Deck can't control yet (most laptops): they say "not supported on this PC yet", why, and offer **Copy report**.
- **Edit Home and Customize** have a **Cancel** button next to Done: it puts back every change made since editing began (positions, sizes, which tiles show, a Reset layout).

## 4.0.0 — 2026-11-10

The biggest Deck update so far: a target-FPS power saver, a Startup optimizer, a drive speed test, crash reports and backups, per-game PC settings, sound outputs per app, display schedules, launcher actions, fan calibration and alert rules, and a long list of fixes. Everything new that changes hardware, runs in games or sends anything over the network is off until you turn it on. It also includes 3.7.5, which was never released on its own.

Not in this version: the Android app isn't attached to this release yet, so the Phone page's QR code works again once it is. Not built on purpose: anything that reads a game through RivaTuner beyond what Deck already did, a paste stack (it needs keyboard injection), HowLongToBeat, chat bots, sending alerts by email (ntfy and Discord work), translations.

### Added
- **User guide online:** a full manual for every page and setting, with recommended setups, an FAQ and troubleshooting, published with each release. Open it from Settings › About or by searching "guide" in Deck.
- **Page tours:** the first time you open a page, a few short steps light up its main parts with a sentence each (Next, Back, Skip, or Skip all tours). The ✦ button next to search plays a page's tour again; Settings › General turns first-visit tours off or starts them over.
- **Why did my FPS drop?** (Gaming > Sessions, and a game bar widget): after a stutter or dip it shows the moment ("12 s ago · 144 → 61 FPS") and the likely cause with the readings behind it: GPU power limit or heat, full video memory, one CPU thread maxed, a busy background app, heavy disk or download activity, or "No clear cause". Session reports keep their drops. It only uses readings Deck already takes, and nothing runs when no game is open.
- **Game bar, one-click essentials:** the default bar now has mic mute, overlay on/off, CPU and GPU profiles, frame limits, sound output, Free memory, volume and music. For the first three games a small hint names the shortcut that opens it (never takes focus; can be turned off). Saved custom layouts are kept: "Back to the default widgets" gets the new set.
- **Mouse lighting effects:** Static, Breathing, Colour cycle, Strobe and Off with brightness and speed, run by the mouse itself on supported Logitech mice.
- **Startup findings you can act on:** ranked by measured delay, with short advice per item and "Turn off at sign-in" for your own apps. Windows, security and driver components are marked Keep.
- **Windows:** pick an app and a snap zone and its windows open straight into that zone; "Remember windows for each set of monitors" puts your windows back when a set of monitors returns (a dock, a TV). Both off by default.
- **Network:** data used by each app (today, 7 and 30 days), connection quality over time (router and internet delay, jitter, lost replies, kept 30 days), and a "Lag while busy" test graded A to F.
- **Apps:** "Update your apps" updates the apps winget has newer versions of, one by one with a result each; before uninstalling a Visual C++, .NET or DirectX runtime Deck says which installed apps use it.
- **Tweaks:** save your tweaks to a file and open one on another PC (you tick what to apply; each keeps its Undo); after a Windows update the notice says which settings Windows put back.
- **Clipboard:** "Paste as plain text" for chosen apps puts the plain version of formatted text at the top of the history (Deck sends no keys).
- **PC to PC:** the accept card shows what is inside an offer (biggest files, types, a warning for programs); a PC without enough free space refuses up front; optional "Send to PC" in Explorer's right-click menu.
- **Sound:** choose which output each app plays on; save output profiles (default output, calls output, each app's output and volume) and apply them in one click with Undo; optional rules that switch output when a headset or dock connects or an app starts, and optional memory of each app's volume (both off by default); **Check mic for 5 seconds** shows peak, noise floor and clipping (nothing is recorded to disk).
- **Display:** a per-monitor schedule for brightness and warmth through the day, optional dimming when idle, night colour, an input switch that offers only the inputs the monitor lists, and full-screen test patterns (Esc closes). Brightness and colour go back exactly when Deck quits or after a crash; Undo puts back the input.
- **Launcher:** quicklinks (a web address with `{query}`), custom commands (a program, its arguments and a time limit) and chained actions (sound output, CPU/GPU profile, power plan, open app). Commands and chains show exactly what will run and ask the first time and after any edit.
- **Clipboard:** "Change it" previews a text item as formatted JSON, comma-separated lines, without link tracking, or with private details hidden (the original stays); "Copy text from this image" reads text from a history image; optional "Wipe codes and keys after a minute"; **snippets** with `{date}`, `{time}`, `{clipboard}` placeholders, pasted from the launcher.
- **Wake a PC:** PCs Deck has seen on your home network that are off or asleep now show a Wake button (Wake-on-LAN).
- **Processes:** a one-line "what is this" for common Windows and desktop programs.
- **Startup apps** show how many seconds an app slowed the last Windows starts, from Windows' own measurements.
- **Shut down when an app finishes its work:** waits until the app has been busy, then until it stays under a CPU percentage for the minutes you set, or closes.
- **Rest your eyes every 20 minutes** (off by default): a 20-20-20 reminder that waits while a game or video is in front.
- **Fans:** run a fan on the highest, lowest or average of two curves, or make it follow another fan; an "Ignore short spikes" preset; **quiet hours** that cap curve-driven fans at night unless the PC gets warm; **Rehearse a curve** plots what a fan would do (climb, short spike, lost sensor, cool-down) without touching the fans; **Calibrate a fan** measures its speed at each step and its stop and start points, then warns later if it turns slower than before.
- **Sensor alert rules** on any reading ("above or below X for N seconds", several tests together) that can show a notification, send a message out, flash the lights red or switch a CPU or GPU profile.
- **Notifications out:** send alerts, drive warnings, shutdown-plan warnings and "Deck closed unexpectedly" to an ntfy topic or a Discord webhook (off by default, each kind opt-in, with a test button).
- **Sensor history:** a day, a week or a month of CPU and GPU temperature, load and power. All readings now explains where each reading comes from, what it means and how fresh it is.
- **CPU:** the live panel shows what the profile asks for against the clock the CPU runs at, and names what is holding it back.
- **Lighting:** optional red flash on heat alerts or when the death counter counts a death, an optional colour per CPU/GPU profile, and OpenRGB devices can follow Deck's lighting through OpenRGB's SDK server (off by default).
- **Weekly health card** on This PC: the last seven days of temperatures, drive checks, free space, sensor alerts and crashes, with links to the details.
- **Cooler display:** optional short messages for important events (shutdown soon, timer done, downloads and PC to PC transfers finished, alerts, heat).
- **Target FPS power saver** (Gaming, per game, off by default): set a target such as 60, 90, 120 or 144 FPS, and while that game is in front Deck lowers the GPU power limit and the CPU's long-term power limit step by step as long as the game stays comfortably above the target, and raises them again when it drops below. It never goes below safe floors. The original limits come back when you leave the game, alt-tab, change a profile, the PC gets hot, Deck quits, or after a crash. It only lowers a limit the hardware actually runs into (a GPU-bound game gets a lower GPU limit; the CPU limit stays), and the page shows the FPS now next to the limits. Needs an NVIDIA GPU and RivaTuner's frame-rate reading (Deck adds nothing to the game). Tested with Unigine Heaven held at one spot, target 100 FPS: the GPU went from 240 W to 100 W while the game stayed at about 168 FPS, and closing it or switching away put back exactly 240 W and 130 W. **Simulate** shows what it would do on sample traces without touching the hardware. The game is recognised from the window in front, so RivaTuner briefly reporting another program (or a reading that is a moment late) no longer hands the limits back and starts over; the log says why each hand-back happened. It reacts within one to two seconds, starts from the limits that held the target last time for that game, may raise the GPU above its profile (up to the card's maximum) when the game needs it, and stops going lower when the frames get uneven (the slowest 1 % of the last three seconds), even if the average is fine. Optional per game: "Go below the lowest power limit" also holds the core clock lower, down to the Minimum mode "Measure this card" found. Picking a profile yourself turns Target FPS off for that game until it restarts.
- **Startup optimizer** (Clean > Startup optimizer): how long your last Windows starts took (firmware, Windows, sign-in), a history of the last ten, what slowed them down by Windows' own measurements, and advice for each cause. Safe fixes (Explorer's startup delay, Fast Startup, delayed start for optional updater services) are opt-in, each with an exact Undo and an Undo all.
- **PC settings per game:** a game can switch the fan preset, lighting effect, display mode, HDR, digital vibrance and sound output while it runs; everything goes back when it closes, when Deck quits, and after a crash.
- **Playtime:** Gaming and Home show total and weekly hours per game and the last session.
- **Session report** after a game closes: time played, highest temperatures, energy used and deaths.
- **Energy and cost:** Home and Gaming show energy used today and this month, with an optional price per kWh.
- **Profile stability log** (optional): warns when a CPU or GPU profile was active during repeated game crashes or driver resets.
- **Death counter:** text files for OBS, and attempt splits per session with the profiles and temperatures at the time.
- **Controller:** a low-battery warning over games (optional), a stick drift check with a suggested dead zone, and battery history with hours left.
- **Game bar:** new Fan preset widget.
- **Crash reports:** if Deck closes unexpectedly it saves a crash report on your PC and tells you. Nothing is sent anywhere, and crash files only join a support report if you choose.
- **Back up and restore Deck** from Settings, with optional weekly backups to a folder you choose. Secrets stay out unless you add a password, which encrypts the backup. You review a backup before restoring it, and the current settings are saved first.
- **Go back to the previous version** from Settings > About, follow **beta releases**, and see **what is new** once after each update.
- **Active changes** (tray and Home) lists everything Deck is holding right now, with a Release button for each.
- **Deck's storage** in Settings shows how much space each part of Deck uses, with a cap and a Clear button for the artwork cache.
- **Settings > Diagnostics** turns on detailed logging for one area; Deck records its own and WebView2's memory use every hour.
- A short **introduction** at the top of Settings on first run (Show introduction brings it back).
- **Drive speed test** on the Drives page: sequential and random 4K, read and write (SEQ1M Q8T1/Q1T1, RND4K Q32T1/Q1T1), with history per drive. The test file bypasses the cache and is deleted even if Deck closes mid-test.
- **Drives:** TBW life estimate, temperature history with an alert, and a verified-copy plan for drives that start failing (copies your files to another drive and checks every one).
- **Disk space:** find duplicate files (recycle them, or replace them with a hardlink; the replaced copy goes to the Recycle Bin), see what grew since the last scan, build a "make room for N GB" plan, and see what deleting a selection would really free.
- **Anti-cheat friendly:** when FACEIT is running, Deck hands the fans back to the BIOS and stops using its hardware driver, says why, and resumes when FACEIT closes. If Windows blocks the driver, Deck says so instead of showing missing fans.
- **One hardware owner per PC:** if a second Windows user also runs Deck, only one controls the fans and lights; the other says so and takes over when it quits.
- **Keep awake** lists what else is keeping the PC awake.
- **Sensors: "Slow readings during games"** (on by default) reads drive counters and idle fan chips every 3 seconds while a game is in front; manual fan curves keep their one-second timing.
- **Get the Android app by QR code:** the Phone page has a "Don't have the Android app yet?" section. Scanning its code downloads the newest app from the public release page.
- **Low delay for the phone as speaker:** a new switch plays at about 120 ms instead of 300, at any sound quality. Weak Wi-Fi may cause small gaps.
- **Test my mouse:** the Lighting page's Mouse card now always shows, with a button that tells whether Deck supports your mouse and a report to copy and send so support can be added. It only reads what Windows knows; nothing is sent to the mouse. `Deck.exe --mouse-probe` prints the same report.
- **Logitech mouse lighting:** the Lighting page gets a Mouse card, shown only when a Logitech mouse answers, with Off, a solid colour and a brightness slider. Each zone's result is shown, and G HUB or another RGB program running is noted. Deck sets it only when you press a button.
- **Ask on the PC before a phone powers it off:** a new Phone page switch (off by default). With it on, a phone's shutdown, restart, sleep, hibernate or scheduled power-off waits for Allow on a notification on the PC. No answer in 30 seconds, a closed notification, or a new phone key means it does not happen, and the phone is told it is waiting. Lock and screen off are not asked.

### Changed
- **One Settings page for everything.** Settings now has parts listed on the left (General, Appearance, Search, Games, Death counter, CPU and GPU, Desktop, Notifications, Connections, Data & recovery, About) and a **Find a setting** box. The Settings tabs of CPU, GPU, Deaths, Clipboard, PC to PC and Workspace Sync, and the loose settings on other pages (Gaming options and crash records, controller battery, phone power and upload limits, drive health warnings, Store app auto-install), moved there. Pages that are settings in themselves (Overlay, Game bar, Flyouts, Fans, Lighting) stay, linked from their part.
- **Gaming › Games, redone:** Game mode is one slim bar on top, your games are a compact list on the left (with the default profile at the top), and the picked game fills the right with its picture, figures and settings. Games without a picture show a plain gamepad instead of a broken file icon.
- **CPU and GPU charts** (CPU › Cores, GPU › Readings) have numbers on both axes, fill their panel, and can show the clock, temperature, load or power.
- **Much less text everywhere.** Every title, description and "?" help in the app was rewritten to a length budget: a setting's line says what it does in one sentence, and the detail sits behind the "?". Over 400 long passages were cut; nothing that warns about hardware or data was dropped.
- **More tabs, shorter pages:** CPU, GPU and Fans, Network, Sound and mic, Windows, Phone, Settings, Screen tools, Apps, Flyouts and the Game bar are split into tabs, and each page reopens on the tab you used last. The Games tab in Gaming is grouped into Performance, Power, While playing and PC settings.
- **Session reports** are grouped by day with length, average FPS and 1 % low, newest first with Show more.
- **Controller page:** one keyboard with all keys instead of "Keys to show" plus "More keys".
- **Sensors:** "Where these readings come from" explains each source once and is readable; rows no longer get cut off, and columns line up.
- **Drives and Network** have tidier spacing; missing values show as small hints instead of big text. The search box and buttons at the top of each page match the rest of the app.
- **Workspace Sync** when off is a short pitch with one button; the details are in a fold.
- **GPU page, easier to read:** the profile editor opens with a strip that says what each section does (Power, Speed, Memory, Fan; changed ones are highlighted, a click jumps there), shows the four sections side by side in two rows, and puts the voltage curve and fan curve full width underneath, so nothing hides far down the page. Built-in modes is one fold under Your profiles, as on the CPU page, with all eight modes in it (the four everyday ones first) instead of a second "All modes" fold inside it.
- **CPU, GPU and Startup optimizer:** the page buttons sit in a row under the title, so the top bar keeps only search, pin and close like every other page.
- Damaged saved files are kept aside and the last good copy is loaded; background workers that crash restart themselves and are listed in This PC.
- Deck checks an update's digital signature when it has one, in addition to its checksum.
- A settings file written by a newer Deck is left untouched; this version loads defaults and won't save over it.
- High-contrast themes, reduced motion and Windows' text size setting are respected.
- Clean up lists NVIDIA, AMD and DirectX shader caches separately, Steam's shader cache per game, and game crash dumps per game.
- Deck leaves a sleeping laptop NVIDIA GPU asleep and the GPU page shows "GPU asleep".
- On ARM64 Windows the hardware pages are hidden with the reason; on Windows N the music features say the Media Feature Pack is missing.
- Errors from Windows are explained in plain words with a next step.
- Tweaks refuse to turn off services that Windows Update, the Store, Defender and licensing need.
- Undo in Tweaks asks before it overwrites a setting you changed after Deck applied it.
- Shortcuts another app has taken are marked, and Deck registers them again after sleep.
- Fan control and input polling keep their timing when Windows puts Deck in Efficiency mode.
- File search says when some folders could not be read or the file limit was reached.
- The phone-controller driver message points at ViGEmBus's final release and explains its retired updater.
- The hand cursor is only on real buttons and links, not on whole rows and cards.
- The log now says what asked for each skip (media key, Deck, the phone remote, a shortcut), so an unexpected card can be traced.
- **The phone link is encrypted only and signed per request (method and query included).** This needs the matching Android app version; older apps must update, and the old browser page stops working until reloaded from the PC. The phone port no longer serves anything over plain HTTP (only a short page that moves the browser to https), pairing links are always `https://` with the PC's fingerprint, and without a certificate the phone connection doesn't start and the Phone page says why.

### Fixed
- Game pictures no longer flicker or sit empty while a page refreshes, and games Deck found by their program (such as "Roblox Game Client" or "osu!(lazer)") now get their artwork. A game with no picture shows its program's icon.
- Switching a game bar widget off no longer makes it vanish from the list and from Add; it stays in the list, dimmed, until you remove it.
- A video playing under the pointer on a video site (a muted preview) no longer shows as now playing: a browser only counts once it makes sound. The song already shown keeps showing if you mute it.
- Play time no longer shows "2 h 44.7833 min".
- A stray "null" no longer shows on the Controller page without a controller.
- The Fans page no longer says fans aren't available for a moment at start-up; hardware pages show a quiet loading line instead.
- "Test my mouse" no longer jumps to the top of the page.
- The game bar preview grows back after switching from Floating card to Full height.
- **The overlay no longer freezes or shows twice.** RivaTuner also drew it inside NVIDIA's own overlay window (the "Press Alt+Z" pop-up and its notifications), which lies over the game and only redraws now and then: a frozen copy covered the live overlay, or the two showed on top of each other, and turning the overlay off and on didn't help. Deck now keeps NVIDIA's, AMD's and Xbox Game Bar's overlay windows out of RivaTuner, as it already did for launchers. An overlay window already open when Deck updates keeps the old copy until it restarts (or the PC does).
- Home shows play time as "26 min" or "1 h 5 min" instead of "26.35 min" and "0.44 h", and the energy figures are one short line under PC readings instead of rows squeezed into the tile.
- The GPU page no longer warns that the power limit differs from the profile when the profile asks for less than the card's minimum (41% of 240 W asks for 98 W; the card runs at its lowest, 100 W).
- With a GPU profile on, Deck checked Windows' event log for driver resets every 5 seconds (a short program start each time, games included); it now looks at most every 30 seconds.
- **Deck's window could stay empty** after an update that changed the order Deck's page parts load in (a Gaming setting read before it existed). Each page's first tab is now defined in one place.
- **Installing or updating could stop with "Deck couldn't create its scheduled tasks"** on PCs where Windows elevates admins without asking (3.7.5). The check of Deck's folder asked Windows for more access to the signed-in user's token than Windows gives; it now asks only for what the check needs.
- Fans, Lighting, Drives and This PC no longer stop drawing when one of their readings is missing.
- The Clean up tab no longer makes the window stutter once a second when the Recycle Bin holds many files.
- An invalid reading (not a number) can no longer crash the game ping test, the network speed test, the GPU curve editor, the overlay's top list or fan curve sorting.
- A drive that first becomes readable already unhealthy now warns.
- **Drive health:** Deck no longer wakes sleeping hard drives to read their health; USB drive warnings wait for a second bad reading and say they may be wrong; a drive going from unknown to caution or bad now warns.
- **Sensor recording** no longer starts over at 50 MB: it moves to a new numbered file and keeps the five latest.
- A stuck Windows management query can no longer hang the machine probe; the support report names what was skipped.
- Deck follows a moved or renamed Downloads folder (PC to PC inbox, file search, clean-up).
- Two different screenshots with the same edges are no longer treated as one clipboard entry.
- Files VirusTotal had not seen are looked up again after a week.
- The calculator reads `max(1,234)` as two numbers.
- Opening a workspace puts each window of the same app in its own saved place.
- The session summary's FPS per watt only uses moments where both were measured.
- Saving Deck's files rides out a virus scanner holding the file for a moment.
- **Building from source:** running the tests no longer opens a "Windows cannot find" box with an error sound.
- **Music card when a song changes by itself:** the moment a player stops while loading the next song no longer opens a Paused card. A pause in a new song's first two seconds shows only if it holds.
- **Mouse lights can be turned back on:** after Off, the button becomes Turn on, and moving the brightness slider lights the mouse again.
- **VB-CABLE setup:** it could not start from its protected folder; Deck now starts the checked setup with its own admin rights, or says why it can't.
- **Uninstalling:** Deck no longer offers leftovers while an uninstaller that relaunched itself from Temp is still running.
- **Screen view:** a small picture on a fast connection no longer loses H.264 because the bitrate went over the encoder's limit.
- **Phone power approvals:** Allow on PC can't be reused or answer a newer request, and is refused while a phone has control of the PC. A plan's "Do now" follows the same rules.
- **Received setups and zips:** extraction counts the real unpacked size, runs without admin rights, and a snapshot's undo only restores the listed settings.
- **Uninstalling a program no longer runs a user-written uninstaller with admin rights.** An uninstaller listed only for your account, or one in a folder a normal program could change, is started as you; if it can't be started that way Deck says so instead of running it elevated.
- **A zip received with Install is unpacked without admin rights,** into a fresh folder that is kept only if it worked. Zips with too many files, too much data, paths leading outside the folder or symbolic links are refused with the reason.
- **Applying a received setup leaves Windhawk off by default** and warns that mods run as code inside other programs. Its files are copied to an admin-only folder before they are checked and used, and the result says whether mods were applied.
- **Getting VB-CABLE** unpacks and checks the setup in a folder only administrators can enter, and the signer's name must match exactly.
- **Getting VB-CABLE no longer loads PowerShell modules from your user folders** while Deck runs as administrator. It uses Windows' own PowerShell and only the system modules.
- **The built-in PawnIO driver file name can't be changed to a path,** and the file is compared in full and not written through a link.
- **Making a new phone key now stops downloads and uploads already running.** A large download kept sending, and an upload could still finish and appear in the inbox; half-sent uploads are removed too.
- **The old phone key no longer stays in plain text in settings backups.** The backup and any damaged-file copy are sealed, and if Windows can't seal a secret, settings, PC to PC, Workspace Sync and file check results are left as they were, and the phone certificate isn't made, instead of being saved in plain text.
- **Turning the phone remote off now disconnects phones already connected.** They could keep controlling the PC until they left.
- **Setups from another PC stay within what they're meant to change.** A received setup could write other registry values, including programs that start with Windows. It's now limited to its own list, and winget ids from another PC can't be read as options.
- **Workspace Sync:** a damaged settings file is set aside rather than replaced by a new key, and two more settings that can run commands now wait for approval.
- **PC to PC:** a damaged settings file or device key is kept aside rather than overwritten.
- **Failed actions now say so** across the app, rather than doing nothing, and buttons no longer stay stuck after a failure.
- **Search:** pasting thousands of brackets can't crash Deck.
- **Screen on your phone** follows a resolution change or a screen being unplugged while streaming.
- **Fans:** if the fan thread fails while Deck is closing, fans are still handed back to the BIOS.
- **Kingston Fury RGB:** a stick that stops answering is retried every 30 seconds rather than on every frame.
- **Phone page:** only http and https links open from the shared list, and messages no longer claim success when the phone wasn't connected.
- **Startup apps:** one very long entry no longer hides the ones after it.

## 3.7.0 — 2026-11-07

A safety release: fans, power actions, undo and the phone connection, checked piece by piece.

### Added
- **"Are you sure?" before power actions:** shut down, restart, sleep, hibernate and sign out now ask first, from Deck, the quick panel, search and the phone page. Plans ask when you set them, naming the action and when it runs.
- **Allow power commands from phones:** a new switch on the Phone page, on by default. Off, phones can still lock the PC and turn its screen off.
- **Upload limits:** optional limits on the Phone page for each file and for the From phone folder.
- **Display changes go back by themselves:** a new resolution, refresh rate or rotation returns to the old one unless you press Keep, even if the page closes.
- **QR codes carry the PC's certificate fingerprint:** a phone app that reads it is protected from its first connection. Older apps and the phone page ignore it.

### Changed
- **GPU fan safety:** a fixed speed or a fan curve now gives way to 100% at 85 °C or when the temperature can't be read, until the card is back at 80 °C. Zero-RPM stays as it was while the card is cool and its temperature is known.
- **Custom CPU power limits can't exceed the limits the board started with.** Existing higher values are held at that limit.
- **The PC's speakers come back sooner** after a phone stops playing: at once on Stop, and in 2 seconds rather than 5 if the phone just disappears.
- **Recall's switch now says what it does:** turning it off deletes existing snapshots, which Undo can't bring back. It moved to Advanced.
- Several tweak descriptions were corrected to say what the tweak really does, and one policy now only shows on the Windows editions it works on.

### Fixed
- **Case fans:** a fan stopped by a curve no longer stays stopped when all temperature readings disappear, and old board readings no longer count once the chip stops answering.
- **A cancelled shutdown could come back** after a restart, and a plan replaced within the same second could be mixed up with the old one.
- **Sleeping during a shutdown countdown** could shut the PC down on waking. A missed countdown is now cancelled with a notice.
- **`shutdown in 1d` and `shutdown in -1m`** were both read as 60 seconds. Search now refuses what it doesn't fully understand.
- **Game profiles:** a game ending at the wrong moment could get its profile back after closing, two games with the same file name no longer share a rule, and a crash or power cut during a game now restores the card's earlier settings. GPU changes also check they reach the same card on PCs with two.
- **Uninstall:** CPU power plans and the minimum-clock lock are now put back. Removing Deck no longer leaves a cap or floor behind with nothing guarding it.
- **Tweak undo:** a tweak now stops before changing anything if it can't save what it needs for Undo. DNS Undo covers IPv6 and still works after you change network adapter, and stopping a service is checked.
- **App removal can't preselect shared folders** or services another app owns, and a registry backup must exist before anything is deleted.
- **Clean up:** the Rust build cache only removes real build output, even when its folder setting points somewhere unusual. Installers moved to the Recycle Bin no longer count as freed space.
- **Clipboard:** exclusions are checked while holding the clipboard, unreadable markers count as excluded, and very large items are skipped.
- **Store apps:** a downloaded package is rechecked and held until it's installed.
- **PC to PC:** resuming a transfer now needs the same PC that was approved.
- **Support reports** no longer include file paths.
- **Phones:** resetting the pairing code now disconnects phones that were already connected, and upload temp files can't overwrite each other.
- **Setup:** updating from a very old per-user install no longer runs a file from that folder with admin rights.

## 3.6.4 — 2026-11-06

### Added
- **Choose which apps count as music:** Desktop > Flyouts lists the media apps Windows has right now, each with Auto, Always or Never.
- **Show music card from the tray:** see the current song without opening a page. Show uses the player's actual playing or paused state, or a labelled sample when no song is available, and respects the fullscreen setting.
- **Song end tolerance:** an Advanced control in Music allows for players that crossfade or finish early. Existing settings keep the four-second default.
- **Media keys always reach the player (off by default):** Windows gives play, next, previous and stop to the window in front first, and a frozen one keeps them. With this on, Deck sends them straight to the player. Other programs that use those keys won't get them.

### Fixed
- **The music card reacts to a skip at once.** Pressing next or previous now opens the card straight away saying "Skipping" or "Going back", and it names the song as soon as the player does.
- **Small flyouts keep their coloured icon.** Caps Lock and other small cards had a near-black circle in place of your accent colour.
- **Media keys work with Deck in front.** Play/pause, next, previous and stop stopped at Deck's window and never reached your music app.
- **Music rules match their description.** Recognised music apps need no artist or duration; other apps need an artist and at least 45 seconds, or an unknown duration. Browsers are a fallback when no qualifying non-browser session is available, including paused songs. Always and Never remain explicit overrides.
- **Launchers and apps set to Never are gone from the rest of Deck too,** including Home and the game bar.
- **Song names no longer wait for artwork.** Pictures load separately, reject late results for another song, and hold back a previous song's cover while the player updates it. Late artist metadata does not announce the same song twice.
- **Resume and playback changes requested through Deck respond without the pause debounce.** Unsolicited pauses retain the guard against a player's skip flicker.
- **Skip and song-end preferences also apply while a card is already open.** Known skips from Deck's controls take priority near the end; short read gaps advance the previous playing position, and known seeks reject a briefly stale timeline.
- **Flyout delivery and closing are ordered.** Old snapshots, acknowledgements and queued window operations cannot replace a newer opening. Display time starts after the page responds; missing later draw acknowledgements also recover the window.
- **Cards switch to native drawing when a game or fullscreen window comes forward.** Show follows the same game policy. Native fades can reverse without flashing and respect Windows animation effects and Low spec.
- **Volume controls handle captured drags, cancellation, fast writes and failures.** A short interaction lease keeps a drag alive outside the card. Master output and player volume have distinct labels; ambiguous player mixer matches are hidden. Controls target exact Windows media sessions even when apps share an identity.
- **App choices and hardware availability refresh while Flyouts is open.** Missing readings preserve their baselines, unknown battery charge is no longer shown as 100%, and unavailable previews are labelled samples. Microphone feedback says Muted or Unmuted.
- **Placement adapts to work-area, monitor and DPI changes.** Cards scale to fit small work areas, keep paired cards together, and avoid Deck notifications when room exists. Secondary text has measured contrast on supported card tints.
- **Disabled flyout workers wait for events instead of checking settings every 400 ms.** Artwork reads, media control calls and player-volume requests stay off the UI runtime's active work.

## 3.6.3 — 2026-11-05

### Fixed
- **"When a song ends and the next one starts" now holds.** A song that ended by itself could count as a skip, so the card showed with that setting off. It happened whenever another program had a media entry (Riot Client keeps a paused one), when the next song's length arrived before its name, and when the next song passed through "paused" on its way to playing.
- **A launcher is no longer taken for a song.** A media entry that only gives the program's own name, as Riot Client's does, is ignored, so it can't open the music flyout.

## 3.6.2 — 2026-11-05

### Added
- **Volume and music as one card:** "One card" under Show volume with it puts a thin volume bar under the song instead of opening a second flyout. You can drag it, scroll on the card, or click the speaker to mute. With nothing playing, volume shows by itself.
- **The player's own volume on the music flyout (off by default):** a small slider under the buttons, for just the app that's playing. It's that app's level in Windows' volume mixer, so the slider inside the app doesn't move.

### Fixed
- **Changing the position or the arrangement moves flyouts already on screen.** A card already open stayed where it was while the other went to the new place, and the two could overlap. Both now work out their places the same way, and a change takes effect at once instead of up to a second later.
- **The volume flyout changes colour when the song changes,** not at the next pause or volume change. It now follows the song while it's open.
- **Flyouts now show over games that use all of the graphics card.** They opened but stayed invisible, and only one already on screen when you tabbed in could be seen. Over a game they're now drawn without the web engine, and they don't cost frames while they're open: Warframe went from 187 to 179 fps with one up (a web card forced through cost 55 fps and caused stutter).
- **Flyouts show over Deck's own window** as they do over any other program.
- **"Show in folder" opens the right folder with the file selected.** Any path with a space opened Documents instead, which included every file received from the phone (`Downloads\From phone`). A file that has since gone opens the nearest folder still there.
- **Caps Lock and the other short flyouts** no longer sit in a place kept for the music flyout when it isn't there, and they're smaller: two short words no longer fill a wide card.
- **Boss names that animate or are thin are recognised.** Warframe's Jackal read differently each time and never opened a fight. What the reads agree on now counts, even if they aren't one after the other.
- **A fight is no longer renamed to something one bad read made up.**
- **The death counter no longer keeps a processor core busy** while a game fills the graphics card (up to 97% of one core, now about 9% typically with the same fight). The counter's own cost in frames couldn't be measured in Warframe: 171 fps with it on, 168 with it off.

### Changed
- **The volume flyout matches the music flyout:** white on the colour of the song's cover.
- **A song's picture and colour are kept for 10 minutes,** one song at a time, so the card has the right ones as soon as it opens.

## 3.6.0 — 2026-11-05

### Added
- **Flyouts (Desktop > Flyouts, all off by default):** small cards that never take the focus, for music, volume, microphone, sound device, lock keys, brightness, airplane mode and charger, each with its own time on screen. They follow what Windows reports, so a change from any key or program counts, and they stack instead of overlapping. The volume one can be dragged, scrolled and muted. Deck can also hide Windows' own volume pop-up, off by default.
- **Choose when the music flyout shows:** when you skip, when a song ends and the next one starts, or both. They're told apart by how close the song was to its end, so a skip in the last few seconds counts as ending.
- **Volume and music can open together:** one above or below the other, whichever one changed. Separate unless you ask.
- **Music flyout:** a card coloured from the cover when the song changes, however you skipped: keyboard, player, phone or controller. It opens as soon as the new name is in, about a second or less after a skip, never showing the old song as the new one, and the cover follows a moment later. It has previous, play/pause, next and seeking. It never takes the focus, and over games and fullscreen windows clicks pass through it, or choose Overlay text to put no window over the game at all. It stays out of the way during presentations, Do not disturb, and while the player or Deck is in front. In true exclusive fullscreen, where no window can be drawn, the song also appears in the Overlay if that's on.
- **Apps built on a web engine now show their real name** as the source of what's playing, instead of "Web app".

### Fixed
- **Missing artwork on Home and in the game bar:** a song whose picture arrived just after its name stayed without one until the next song.
- **A hung media player can't hold up Deck's media controls:** Windows media calls now give up after 1.5 seconds.
- **Two apps built on a web engine playing at once:** Deck's controls now reach the one that is playing, instead of whichever Windows lists first.
- **Accented letters in the in-game overlay** (é, ñ) now show instead of "?".
- **A dialog over a game could hide Deck's panel.**
- **The hot corner and other full-screen checks took the desktop for a full-screen app** on some setups.

## 3.5.2 — 2026-11-04

### Added
- **Phone remote:** app icons for the mixer (`/appicon`, only for apps playing sound now), a picture sent from the phone can also go on the PC's clipboard, the state carries the PC's Tailscale address so a phone remembers it before leaving home, and its memory in GB.

### Fixed
- **Phone remote:** a media player that's slow to answer no longer stops the phone's live state until it does. Actions run on the side, and one that takes over 5 s says so.

## 3.5.1 — 2026-11-04

### Changed
- **The Xbox pad in the controller overlay is redrawn:** a cleaner shape, a dark plate between the bumpers with a light on it and a lit Xbox button, soft rings round the controls, a chunky d-pad, A, B, X and Y ringed in their own colours, and taller triggers. On the white theme the sticks and d-pad sit in dark collars.
- **You can see which way a stick is pushed:** a bright arc on the ring round the stick points the way it's going, the knob shows a lit dot, and the knob travels further on the Xbox and DualSense pads. At rest none of it shows.
- **The PlayStation pads are tidied up:** the sticks are a little smaller, and the D-pad and face buttons have more room.

### Fixed
- **Overlaps in the controller overlay:** the DS4's stick rings ran off the shell, sat off-centre on their sticks and crowded the D-pad and face buttons; the DualSense's light bars touched the touchpad and the square button nearly touched a light bar; its bumper tips floated off the shell; the PS button now lines up with the sticks.

## 3.5.0 — 2026-11-03

### Added
- **Handheld gaming PCs:** Deck recognises the ROG Ally, Legion Go, MSI Claw, Steam Deck, AYANEO, OneXPlayer, Zotac Zone and GPD Win, and This PC says what works there. On any touchscreen, buttons that only appeared under the mouse are always shown, and small buttons, switches and "?" are easier to tap. The power limit (TDP) and fan modes of the makers' own apps aren't in Deck yet.
- **The support report says more about what went wrong:** how the previous run ended (quit cleanly, closed by an update, or ended without quitting, with what the watchdog recorded), which background jobs crashed or stopped, and this run's problems by area with the first and the latest ones, before the log's last lines.
- **This PC says what Deck can do on this machine:** the processor and its generation, each graphics adapter (built-in or card), the laptop's maker, and in plain words what works, what partly works and what isn't in Deck yet. The support report carries the details, including which maker controls the laptop has, so support for more machines can be added.

### Changed
- **Charts have their own colours:** CPU and download are blue, GPU and upload magenta, memory cyan and VRAM violet, the same on Home, Sensors, Network and the CPU and GPU pages. The GPU no longer shares the "all good" green, nor VRAM the warning amber, and download is no longer a different colour on each page.
- **Chips read normally:** game names, profile names and other labels in chips keep their own capitals instead of being shown in small capitals ("GPU: AB Profile 5", not "GPU AB PROFILE 5").
- **Status colours follow the theme:** green, amber and red tints on chips, warnings and hints use the theme's own status colours, so they match in Graphite and Nord.
- **The clock on Home** keeps your timers and "Staying awake" when the tile is short (the calendar goes first), and centres what's left.
- **Opacity fades one layer.** The panel's background is the only thing that fades; buttons, switches, readings and text stay solid, instead of each item having its own see-through background on top of another.
- **The core clock and the other speed settings are a panel on the CPU page**, not a fold you had to find.
- **Folds stand out:** "Advanced" and the other folds are bordered bars with a bold title and an arrow, everywhere (also on the footer pages and Tweaks' "More presets").
- **"Back to GPU" and "Back to CPU" are real buttons**, and the close button shows the same in every mode.
- **The death counter's "+N more deaths" opens 10 at a time.**
- **Games without a death profile start with the death counter off** until you turn it on, count a death or teach a screen.
- **Pages say each thing once and line up:** Deaths shows this session's numbers in a card like the records under it; the Overlay page's reading groups are small labels under the list's heading; Controller's keys say "16 of 27 shown" once and its Test tab names the battery; Lighting's preview no longer repeats the effect's description; Disk space no longer repeats the drive's size and free space under the summary; the Startup apps panel says what its switch does instead of the app's name again; every card heading is the same colour, with or without an icon; Phone's folds open with the same arrow as everywhere else.
- **The GPU editor's half-width panels** keep each setting's name and "?" on one line, with the slider under them.
- **Long names** in Processes end with "…" (the full name is in the panel), the "End app" button no longer repeats the app's name, and a long profile name on CPU and GPU stops at two lines.
- **Help for Lighting's effect and game sound and the cooler display's colour speed**, like the other hardware settings.
- **"Jump to" on Windows and Screen tools** stops with the section's heading in view, not under the top edge.
- **Missing readings on Drives** ("Not reported") are small grey text, not a large number split over two lines.
- **Display's picture sliders line up** whatever value each one shows.
- **Tune's tools** (icon picker, existing plans, Afterburner import, card measuring) open under the panel you used, not at the top of the page.

### Fixed
- **Deck cut off in the bottom right corner with Windows animations off.** With "Animation effects" turned off in Windows (Settings > Accessibility > Visual effects), the quick panel opened with its corner in the middle of the screen and ran off the edge. It's centred again.
- **Problems that used to leave no trace are logged:** a background job whose loop ends, the fan chip or the GPU fan curve failing and working again, a fan curve left without a temperature (handed to the BIOS meanwhile), a page that couldn't load or draw, and errors in the game bar and snap-zones windows. Repeats are counted instead of written each time.
- **A crash hands the fans and the GPU back before anything is written to the log.**
- **A page whose data can't be read no longer says "Loading…" forever.** CPU, GPU, Fans, Lighting, Cooler display, Sensors and the other pages say what went wrong and offer Try again; a page that still draws (Deaths, PC to PC and others) shows the same message above it instead of looking empty or switched off. Drives no longer blames admin rights when reading the drives failed.
- **Closing the GPU editor after "Try it"** tells you if the card couldn't be put back, instead of leaving the tested settings on quietly.
- **The GPU editor no longer reads the card every second while Deck is hidden** (say, while you play).
- **"chrome is open"** on Clean up reads "Chrome is open"; the Processes panel says "File not scanned yet" instead of "Not checked yet"; Cooler display no longer shows a lone "–" under the preview when no display is connected.
- **Scrolling a readings table no longer jumps back to the top.** Sensors' readings and the other pages with live numbers (CPU, GPU, Fans, Overlay) keep each inner list where you scrolled it when the numbers update.
- **Clicks on the game bar, Deck or a notification no longer reach the game** in games that read the mouse directly (osu! and many shooters): while you point at them they take the focus, and the game gets it back when you move away. "Keep clicks off the game" on the Game bar page turns this off.
- **"Move controller overlay" in the game bar** closes the bar so you can move it.
- **Frosted glass in the game bar** shows the game blurred behind it again, instead of grey or black.
- **Switches overlapping their labels** in settings rows.
- **The overlay drawn several times over** in the League of Legends client and other launchers (Steam, Epic, Battle.net, EA app, Ubisoft Connect, GOG Galaxy, Xbox app, Overwolf and more): RivaTuner leaves them alone. Restart a client that was already open.
- **Games in folders with letters outside English** (é, ü, Arabic, Chinese...) weren't found from Windows' list of games or installed programs.
- **The game bar and notifications on laptops with screen scaling** are put back if Windows moves them as they appear, as Deck's panel already was.
- **The page no longer jumps** when a sheet or editor closes and hands the focus back.
- **A dropdown kept its glow** after you picked from it with the mouse.
- **Background jobs restart after an error.** If one of Deck's watchers crashes (closing Deck over a game, the hot corner, Gaming, Power's timers and plans, saving settings, the overlay's readings, the game bar's controller combo and others), it starts again by itself after a few seconds, instead of stopping until Deck restarts.
- **A damaged data file is kept, not overwritten.** If the death counter's game list, notes or taught screens, the play-time history, the GPU's measured curves or Afterburner's imported data can't be read, Deck sets the file aside and logs it instead of starting empty and saving over it. The measured curves are also saved safely now, so a crash mid-save can't cut them off.
- **This PC no longer waits forever on a PC whose WMI is broken:** the machine check gives WMI 8 seconds.
- **The hot corner with several monitors** only opens Deck at an outer corner of the desktop, not where the mouse passes from one monitor to the next.
- **A pinned Deck whose monitor was unplugged** comes back on the monitor the mouse is on instead of off-screen.
- **AMD processors:** the CPU page no longer offers Intel's power limits there (they did nothing); Saver and Performance still set Windows' power mode.
- **Windows installed on another drive:** Epic and Riot games, and Windhawk in PC to PC, are found where Windows keeps them, not only on C:.
- **Network's game list** was cut off at the bottom, and its "relay servers" note was shown twice.
- **Small screens:** the Game bar page stacks its preview under the settings sooner, and the overlay's preset cards and long process names stay inside their boxes.

## 3.3.1 — 2026-11-02

### Changed
- **The game bar never scrolls.** When its widgets are taller than the screen, its text gets smaller until they fit. The preview on Play > Game bar is now a small copy of your screen, so it shows exactly how the bar will fit, and it no longer scrolls on its own: the page has one scroll, and changing a setting no longer makes it jump.
- **Opacity fades only the backgrounds.** Below 100 % the screen behind shows through Deck's surfaces (frosted), while text, colours and readings stay at full strength; before, the whole panel faded and looked washed out.
- **Clearer PC sound on the phone.** The sound is fitted to the phone's rate with a smooth curve instead of straight lines between samples, which dulled the highs, and Auto picks uncompressed sound from 3 Mb/s (it was 8).
- **Fewer cut-outs with the phone as the speaker.** Without pictures to keep in step with, it uses the phone's playback mode and a bigger cushion.

### Added
- **Phone as speaker with the screen off.** "Screen can turn off" in the phone's Speaker and mic card: the phone may sleep while it plays, like a music app, with controls on the lock screen.

### Fixed
- **Deck stuck open over a game.** Opened over a game it never had the focus, so clicking elsewhere didn't close it; now a click outside Deck or switching to another program does.
- **Recording a keyboard shortcut over a game.** "Press the keys" now asks for the keyboard, so the keys arrive. This also lets you set the game bar's key, which is what opens it in games played with mouse and keyboard.
- **The game bar's size at other text sizes.** Below 100 % the bar ran past the bottom of the screen and hid its hint line; above, it stopped short. A floating card now also grows when a widget is added while it's open.
- **Deck opening in the bottom right corner on some laptops.** When Windows changes the window's size as it appears (a screen with other scaling), Deck puts it back.
- **Workspace Sync "peer no longer has that chunk".** Browser caches and WebView profiles inside a project (`EBWebView`, `GPUCache`, `Code Cache` and the like) aren't synced any more; each PC makes its own. A file that keeps changing while it's copied is tried again at the next sync instead of marking the sync as having problems.
- **Sidebar labels.** A hint such as "No limits" next to Tune uses the free space instead of being cut at a fixed width.

## 3.3.0 — 2026-11-02

### Added
- **Game bar: a panel over your game for quick switches.** Turn it on in Play > Game bar (it's off until you do), then hold Select + Start on the controller (or L3 + R3, or Select + L3), press your own key, use the tray menu or tap Game bar in the phone remote. The game stays in front: the bar doesn't take the focus, so games don't minimise or tab out. Use it with the controller (it opens with its first button picked; D-pad or stick to move, A to press, B to close, LB/RB to jump) or the mouse; a click outside closes it.
  - **Death counter without leaving the game:** +1 death, undo ("that wasn't a death"), and for the current fight Won, Not a boss and Gave up, each with "Undo that fix"; "Teach in Deck" opens the death counter's Games page.
  - **Controls:** one-press tiles for the controller overlay, moving the controller overlay, the death counter, the readings overlay, your mic, Boost, the frame limiter and keeping the PC awake.
  - **Controller overlay:** show or hide it, move and resize it, controller or keyboard and mouse, size and opacity.
  - **More widgets:** Now playing, Volume, Microphone, Sound output, Readings (FPS, temperatures, loads, memory, power, clock speed), Frame limit, Profiles (pick which CPU and GPU profiles appear) and Clock.
  - **Make it yours:** add, hide, remove and reorder widgets (drag them or use the arrows), one of each; set each one's width (1 to 3 columns), size and title and what it shows. Full-height panel or floating card (top, middle or bottom), left or right, width, columns, text size, frosted glass (Windows blurs the game behind it), opacity and accent; the combo and how long to hold it, a shortcut, closing by itself, and an option to take the keyboard. All with a live preview: click a widget in it to edit it.
- **Edit phone layouts in Deck.** Phone → Keyboard layouts has Edit and New layout: the layout opens on a drawing of the phone held sideways, where you drag buttons to move them, drag a corner to size them, and set their keys, kind, colour, size and opacity on the side. Undo, Cancel and Save are on top; saving sends it to every connected phone.
- **Move the phone controller's sticks and buttons.** Phone → Controller layout opens the on-screen controller on the same drawing: drag any stick, button or the d-pad where your thumbs want it and size it. Every phone uses it when held sideways; "Put every part back" undoes it all.
- **See the themes before you pick one.** Settings opens with Appearance: every theme is drawn as a small Deck window in its own colours, and each accent shows its name.
- **Turn speakers and mics on or off.** The Sound and mic page has an on/off list for playback devices and for microphones, the same as Windows' Enable and Disable. Devices that are off stay in the list so you can turn them back on, and the page says how many are off.
- **A new icon for Deck:** a deck of cards seen from the side, green cards under a blue top card, with no background tile. It's in the taskbar, the tray, the Start menu, the setup, the phone remote, the sidebar and the corner pop-ups. After updating, Deck asks Windows once to refresh its icon cache, so pinned and Start menu icons change too.

### Changed
- **Disk space looks and works more like a file explorer.** The folder list, the file types and the map sit in one panel. One click on the map selects that file or folder and opens the folders above it in the list, scrolled to it; a bar under the list shows its path and size with Show in Explorer, Open and Recycle. Double-click opens a folder or shows a file. The map draws sharper, with shaded tiles, folder names with their sizes, and outlines for what you point at and what is picked.
- **Sliders and colours apply while you drag.** Controller overlay size and opacity, the death counter's size and opacity, mic level and boost, vibrance, brightness, contrast and monitor settings, and the overlay's margins, zoom, opacity, graph sizes and colours change as you move them instead of when you let go.
- **The phone QR code is bigger** and sits centred with its caption under it.
- **Panels can fit their content.** While arranging a page, "Fit every panel" makes every panel as tall as what's in it and closes the gaps, and a panel you've resized has a Fit button on its bar. A fitted panel keeps fitting as its content changes.
- **The sidebar title** shows Deck's icon next to a cleaner "Deck".
- **The phone remote has Deck's look:** the same colours, fonts and icon, section titles with each group's colour, squarer buttons and sliders, and bigger readings. The fonts come from Deck, so the page still works without the internet.

### Fixed
- **Opening Deck over a game no longer tabs you out.** When a game is in front, the shortcut opens Deck without taking the focus, so the game doesn't minimise; click a text box when you want to type. The shortcut again, the close button or a click outside closes it.
- **The Start menu shows the new icon.** After this update Deck asks the Start menu to read its shortcuts again, so the old icon there goes too.
- **Media keys work while Deck is in front.** Play/pause, next, previous and the volume keys reached Deck's window and stopped there; they now go to your music app as usual.
- Colour swatches and theme previews that set their colours through style variables showed no colour (this also kept the fan icon spinning at one speed).
- **Editing a panel no longer jumps the page.** Opening an editor, saving, rearranging Home and live redraws all keep your scroll position, on Home and every page with panels. Choose PC readings now opens in its own panel instead of at the top of Home.

## 3.2.2 — 2026-11-02

Death counter fixes from a friend's Phantom Blade Zero run, a download button for the OCR pack, and new controller shapes.

### Added
- **OCR pack: a Download button, progress and a confirmation.** Turning the OCR toggle on shows a Download button with its size. The download shows a progress bar with how much is done, then "Downloaded. The OCR pack is on.". If it fails, the page says so and offers Try again.
- **Controller overlay: real DualSense and Xbox Series shapes.** A PlayStation 5 pad is drawn as a DualSense, with its wide touchpad, light bar and mute light. An Xbox pad has its own body, a round d-pad, the Xbox button with its logo, and shoulders and triggers in the right places. A DualShock 4 still gets the DualShock 4 shape. The shapes are lit from above, so buttons look domed instead of flat.

### Fixed
- **The death counter's pill shows in every game Deck has a profile for,** even before a death is counted.
- **A boss bar outside a fight no longer starts one.** A fight needs a coloured bar and, in games with a boss list, a name from that list. Scenes that only look like a boss bar stopped showing "Fighting" and a "0/1" count.
- **A beaten boss counts as a kill straight away,** when its bar empties and stays empty. Before, it waited about two minutes for the game's phase timer. If the boss comes back, the kill is taken back.
- **Boss names from the game's list only.** A garbled read is no longer kept as a boss name in a game that has a list.
- **Bars that jump around** (Elden Ring, Dark Souls 1, Sekiro, Lies of P) open their fights more often. No kill that was counted before is lost.

Phantom Blade Zero's death counter, fixed.

### Fixed
- **Phantom Blade Zero: deaths weren't counted** unless the optional OCR pack was on. The place Deck looked for "DEAD" was too small for the word in English and German.
- **Phantom Blade Zero: the Iron Fiend and Jade Dancer fight wasn't seen.** Deck now finds the two bars side by side, follows the fight when one of them falls, and counts it as one fight with one win. Their names and the Chief Disciple's second phase are on its boss list.

## 3.2.0 — 2026-11-01

The death counter rebuilt, and installing Deck made simple.

### Changed
- **Installing, updating and removing Deck are one short flow in one window.** The setup says what it will do and has one button: Install, Update, Reinstall or Replace. Installing over an existing Deck updates it in place, with no "uninstall first?" page and no "Deck is running" box. Updates from inside Deck stay hidden, and the file-in-use errors are gone
- **Uninstalling leaves nothing behind:** tasks, shortcuts, firewall rules, the PawnIO driver if Deck installed it, logs and browser data all go. A tick box also deletes your settings, profiles and death history
- **Death counter, games Deck doesn't know:** they aren't watched until you count a death in one, mark something on its page or pick "Every game", since not every game has anything to count
- **Death counter, how it decides:** a game's own words in the place it shows them count at once, and the common words need two reads. It's ready again as soon as the banner has gone, so games that restart fast don't lose deaths
- **Death counter, boss fights:** a fight opens from the bar, even before its name can be read ("Unnamed boss"). A bar that empties shows "Defeated?" and the win is written after 2 minutes, or at once on a victory banner. Another boss arriving in that time is the same fight's next phase, so Radagon and the Elden Beast are one fight
- **Death counter, revives:** in a boss fight, a revive (Sekiro) no longer counts as a death. Deck sees the same boss's bar still dropping after the death screen and takes the count back. Only the real death counts
- **Death counter, boss names:** a read close to a name on the game's boss list takes that name. A boss that isn't on the list, such as a modded one, is still detected from its bar and name

### Added
- **Built-in game profiles:** where the boss bar, boss name, player UI and death screen are for a list of soulslikes, including Dark Souls 1 to 3, Sekiro, Elden Ring, Nightreign, Lies of P, Phantom Blade Zero and Black Myth: Wukong, worked out from gameplay footage. Parts that couldn't be confirmed are left out. None of this has been checked in the real games yet. Black Myth: Wukong shows a different quote at each death and only three are known, so some deaths there need counting by hand
- **Set up a game:** a card for each game with its steps (your own bars and items, the boss's bar and name, the death screen, the kill screen). Each is optional and shows what Deck reads in the box you draw. Bosses with two bars (health and posture) are handled
- **A popup for a death Deck reads in a game it's still learning.** It takes no focus, and left alone the death stays counted. It offers "Not a death" and "Set up this game"
- **Fights to check:** the History tab lists recent fights Deck wasn't sure of, each one click to settle
- **OCR pack (optional):** Settings on the Deaths page can download about 24 MB of better text reading. It reads more boss names, and Sekiro's death screen, which Windows' own reading can't. Lies of P's death screen still needs teaching once. It stays through updates, and turning it off or uninstalling Deck removes it
- **Screen shapes:** built-in positions follow the game's window on ultrawide and 16:10 screens
- **Daily backups** of each game's death history, kept for 14 days, and a "Leave this line out" fix in History that deletes nothing

### Fixed
- **Game detection:** osu! and osu! lazer count as games, and so does a game in a borderless window that nothing listed, when its own folder shows it's a game: Unity, Unreal, Godot, a game store's or anti-cheat's files
- **Playing now:** a game stays "Playing now" while you alt-tab or look at Deck, and Game mode starts by itself even if you switch away right after launching. It no longer says "Playing now" after a game closed while Game mode stayed on
- **Gaming:** game names sit on a soft fade over the cover instead of a dark box

### Added
- **Death counter:** death screens in Spanish, French, German, Italian, Portuguese and Polish are read with no setup

## 3.1.1 — 2026-10-31

### Changed
- **Downloads and updates** come from a new public home, [deck-releases](https://github.com/MohammadFakih02/deck-releases): updates, the shared death-screen library, and bug, idea and death-screen reports all go there. The source code is now private. A copy older than this one won't find updates by itself, so install this version once from there
- **Publishing:** releases reach the public repo through `tools/publish-release.py`
- **Local installs:** a release setup can now replace a copy installed with `install.ps1`

## 3.1.0 — 2026-10-30

Fixes from a full review of the new look, page by page.

### Added
- **Your own scrollbars, switches, tick boxes and sliders:** Deck draws them itself now, in the same cut-corner shape, and the scrollbar takes each page's colour
- **Xbox controller shape:** the controller overlay draws an Xbox pad as well as a DualShock, and the new "Match my controller" choice picks by the name of the one connected
- **Lighting preview:** six fans, each with its LED ring and spinning blades, running the chosen effect with its colour and speed, with a start and stop button
- **Sound and mic:** playback devices and microphones sit side by side, each with Collapse and Expand

### Changed
- **Help "?":** opens as a small panel beside the button, so it never moves the page or gets cut off
- **Rows:** a row with a name is clickable all over (running apps, installed apps, startup apps, folders), and names start at the left
- **Home:** the game panel sits on top, with its art, time played and sessions, and shows a death counter only for games that have one; Power & timers keeps its options
- **Gaming:** game status and last session sit beside the games, and wide pictures show whole
- **Disk space:** a picked drive gets the whole page until you go back, with folders above a larger space map
- **Apps:** buttons stay in the same place on every row and in the side panel; rows keep space at their edges
- **Store apps and updates:** panels run the page's full width and the page scrolls. Each update is one line with its Wait for Install, and the reason a check failed opens on request
- **Clean up:** one page that scrolls, with the total and its buttons staying at the top
- **Scrollbars:** the page's scrollbar is on the window's edge and a list's scrollbar is on its panel's edge. Processes, Apps to close and Built-in apps scroll with the page
- **Overlay:** "Start from a preset" comes first
- **Phone:** connection beside the features, with a smaller QR code next to its instructions
- **PC to PC settings:** panels fill two columns without gaps
- **Controller preview:** shows the overlay's real picture
- **Tweaks, Sensors:** panels use the window's height instead of a fixed one
- **Buttons:** a row with a main button keeps all its buttons the same height

### Fixed
- **Which programs are games:** Deck now also goes by the list of games Windows keeps itself and the catalogue of games with bosses, so osu!, Need for Speed and others count, windowed or not. Launchers, crash reporters, installers and programs without a window no longer count, and neither do apps that just cover the screen while the graphics card is busy. A new **Not a game** button on Home takes a program off (Gaming lists them to take back), Add game still adds one by hand, and old false entries are hidden
- **Sound on Home showed no apps:** one row too many hid them all. A short panel now gives up one app at a time, and the game in front and whatever you've just heard come first
- **Games with anti-cheat:** Windows refuses to open them, so they were missing from the sound lists and from game detection. Deck now finds them another way
- **Store updates:** the list wasn't compared with what's installed, so an app already updated stayed listed and trying it again failed. An app Microsoft has no package for no longer reads as a busy server, a stopped check no longer says every app is up to date, and apps that couldn't be checked show their name instead of a code
- **Clean up:** "is open" follows the app closing without measuring again
- **Clipboard:** the hint bar no longer covers the end of the list
- **Wrong game pictures:** a loose picture search could show another game's art
- **Rows on top of each other** in long lists: Clipboard, PC to PC and Phone
- **Sensors:** CPU and GPU showed no temperature in the list, and tables showed a broken degree sign
- **Temperature choice in Settings** showed "?C" and "?F"
- **Scrolling** jumped back up on pages that redraw while a help panel was open
- **Switching dark and light:** the button answers at once and repeated presses no longer freeze the PC
- **Mute** shows at once instead of up to a second later
- **Blue boxes** around the search bar and after mouse clicks
- **This PC** table header, the Store's Updates heading and an orphaned "?" on GPU modes

## 3.0.0 — 2026-10-30

Deck 3.0 is a new look for the whole app: a new menu, every page redesigned, new fonts and motion. Every feature from 2.9 is still there. More UI fixes follow in 3.0.x updates.

### Changed
- **A new menu:** seven groups (Home, Play, Tune, Watch, Desktop, Clean, Power) with a live hint beside each (Live while a game runs, your CPU profile, your next timer), and each group's pages as tabs above the page. Arrow keys move through both. Your saved order, hidden pages and panel customisation are kept.
- **Motion:** menus and dropdowns grow out of the button that opened them, buttons, tabs and chips respond when pressed, and help panels and folds ease in when you open them. Page switches stay instant. With Windows' reduced motion on, only fades remain.
- **Easier to read and use:** text on coloured fills (the calendar's today, badges, active icons) and the calendar's other-month days have more contrast in every theme; disabled controls are clearer; buttons no longer touch; long names end in "…" with the full name on hover, and long text no longer pushes past its card.
- **Power and footer pages:** Keep awake separates durations and event watching; Timers places the stopwatch and break reminders below a wider timer form. Shutdown plans use compact selectors and a sticky action bar. PC to PC gains recipient cards, grouped apps and Activity with received items and logs. Workspace Sync puts incoming review first. Phone uses compact columns and inline setup. Settings has General, Search and About; profile preferences, Home tiles and clipboard settings link to their own pages. Larger reviews and the first-start look picker open inline.
- **Clean pages:** clearer cleanup selection and inline review, a compact disk map and folder tables, attention-first installed apps, paired built-in app panels, and Store updates beside app search. Startup separates its list from launch details. Tweaks gains a review/presets/undo overview, current-value controls and inline Advanced reviews. Existing cleanup, uninstall, download, startup and Windows settings remain available.
- **Desktop pages:** Windows gains compact snap-zone controls and inline workspace actions beside its open-window list. Display pairs monitor controls and shows Keep/Go back inside the affected monitor. Sound and mic uses horizontal volume rows and paired mic cards. Clipboard gains type tabs, an inspector, search scope and its own Settings tab; the old Settings location links there. Screen tools groups colour actions, locked files and Windows shortcuts. Existing controls remain available.
- **Watch pages:** Sensors gains a device rail, reading tables, individual graphs and paired alert/logging settings with clearer draft and retry controls. Processes puts app details and actions beside the lists, with inline file checks. Network pairs connection/speed and game servers above ping; revealing the public IP removes the Hidden label. Drives uses warning-first health cards, and This PC separates hardware capabilities from support reports. Existing controls remain available.
- **Tune pages:** CPU and GPU place the applied profile beside measured readings and use inline profile editors. Fans gains live speed tiles and a full-width curve. Lighting groups zones beside effects with inline colour editing; cooler display separates preview, content, colour and night settings, with reading-list menus. Existing tuning, shortcuts and hardware controls remain available.
- **Play pages:** Gaming gains artwork cards, an applied-profile panel and paired profile settings. Overlay uses five tabs with colours in Look and graph controls beneath Frametime. Controller has a compact preview, battery summary and clearer live input panels. Deaths moves learned screens to Games and opens boss sharing, merging, recognition rules and count reset inline. Existing actions and settings remain available.
- **Home dashboard:** running or last-game artwork, current profile and frame-limit chips, and death counts with +1/Undo. PC readings sit above paired power, performance and utility panels. Edit Home keeps existing arrangements and adds a complete tile list; PC settings, pinned-app actions and layout reset open inline.
- **Page frame and notifications:** compact search beside page titles, wide Home search with Edit Home, separate page tabs and section links, and scroll-edge fades. Help opens inside its panel. Notifications and snap zones use the shared fonts, theme colours and compact corners; saved navigation order and panel customisation remain available.
- **Shared visual theme:** offline display and body fonts, compact rounded controls, frosted panels, quieter separators and group-coloured headings, tabs and sidebar markers across all eight themes. Accent choices still colour controls. Buttons keep their labels whole and narrow label/value rows wrap more reliably.
- **Consistent dropdowns and menus:** solid theme-coloured lists replace native select popups throughout the main window and dialogs, with arrow-key navigation, Enter, Escape, focus return and placement inside the window. Profile mode groups remain collapsible.
- **Faster, steadier checks for contributors:** the Rust tests are 158 instead of 730 (merged by topic; hand-run hardware probes and tests that depended on how fast the machine is removed) and run in about 4 s instead of 14. The automated UI tests were removed; the UI is checked by screenshots and measurements.
- **Faster local builds:** `install.ps1` now builds with a new `local` profile (optimised, incremental): after a change Deck rebuilds in about a minute instead of about six. The published setup is built as before.
- **Faster releases:** a release no longer runs the tests again (it checks that CI passed for that commit) and reuses dependencies compiled ahead on `main`; the release build uses 16 code generation units instead of 4.

### Removed
- **The MoboCtl import** (the one-time settings import and driver hand-over from MoboCtl): MoboCtl no longer exists. Nothing else changes for hardware control.

### Fixed
- A profile picker opened from a button partly out of view could reach past the bottom of the window; its list now always stays inside.
- **Home's Performance tile** said "Make a CPU or GPU profile" after Deck started, until you opened the CPU page. It now loads your profiles itself.
- **The GPU page could stay hidden** after Deck started (and from Tune's tabs) when the page missed the "hardware ready" signal. Deck now asks again until the hardware is ready.
- **Network › Game servers** cut off each server's latency ("50 ms · 20% l…") behind a sideways scrollbar.
- **Home tile headers** no longer push their link (Details, Timers, Processes) under the title in narrow tiles.
- **Startup apps:** an administrator-only app's label read "On ? Administrator needed"; it now reads "On · admin only".

## 2.9.67 — 2026-10-28

### Added
- **Shut down when… is fully adjustable.** Every condition has Options: the speed under which traffic counts as quiet, how long an untouched unfinished file or Steam download counts as paused, extra folders to watch, CPU / GPU / disk limits, how long an app must stay closed, whether a controller or playing media counts as being at the PC, the length of the warning (or none), keeping the PC awake while it waits, waiting while you play, and closing apps that hold a shutdown up. Your choices are remembered.
- **New conditions:** the graphics card goes idle (GPU renders, video exports) and the disk goes quiet (installs, unpacking). **Then wait until the PC is idle** after a download or an app closing, for a download that installs or unpacks afterwards.
- **Keep awake until downloads finish:** how long after the last download it ends, and the speed under which nothing counts as downloading, are now settings.

### Fixed
- **Shut down when downloads finish never fired on some PCs.** Steam leaves folders in `steamapps\downloading` after a paused, cancelled or uninstalled update, and Deck took any of them for a running download, all night. Now a Steam download counts only when Steam says the game is updating and something was written lately; an unfinished browser file only while it is still being written (a paused download or an old .tmp no longer blocks it).
- **Plans are more careful and more reliable.** A plan now keeps the PC awake while it waits (Windows' sleep timer stopped the download and the plan); the warning is called off when the download resumes, the app opens again or you come back; it waits while a fullscreen game or video is in use and gives a fresh warning after; "An app closes" waits for the app to have run and stay closed (it fired at once before); "The network goes quiet" counts uploads, as it said; speeds and CPU are averaged so one spike or dip doesn't decide; "I've been away" counts a controller and no longer fires at once after 49.7 days of uptime; a plan survives Deck updating overnight, and one from before a Windows restart or sign-in is dropped instead of acting on the PC just turned on; "Do it now" can't run a plan that was replaced. Plans are now in the log (set, cancelled, met, waiting).

## 2.9.6 — 2026-10-28

### Added
- **Frame rate limit (Gaming): your monitors' own refresh rates** are in the list, each with a step just under it (3 FPS less, for G-Sync / FreeSync), e.g. "240 FPS · your monitor" and "237 FPS · just under your monitor"; with more than one monitor each is named.
- **Hide modes / Show modes**: a small eye button on the right of the CPU and GPU pages' Modes header folds all the built-in modes away and brings them back; each page remembers it.
- **The built-in modes sit behind one "Modes" row in profile lists** (Apply a profile at start, Plugged in / On battery, each game's GPU and CPU profile in Gaming): a click opens it, and it is already open when a mode is the one picked. The tray's CPU and GPU profile menus have a Modes submenu.
- **Low power and Lowest power (GPU modes)**, below Saver, for lighter games, video and the desktop. Low power keeps Saver's memory speed and holds the core at 60 % of Saver's speed; Lowest power also drops the memory to its low step (810 MHz on RTX 30 cards), with the core at about three quarters of Saver's. Both use fewer watts than Saver, but also give fewer frames per watt: Saver's core is already at its lowest voltage. On an RTX 3080 in Warframe at Ultra settings, 810 MHz memory gave 43 fps at 69 W.
- **Minimum (GPU mode)** for light games like League of Legends: the memory at its very lowest step (405 MHz on RTX 30 cards), where the driver also holds the core low (420 MHz at most on an RTX 3080; the mode shows the speed the driver allows). On an RTX 3080 in League, 134-160 fps for 37-39 W, against 375 fps at 94 W in Normal and 272 fps at 57 W in Lowest power. Heavier games drop to a few frames in it.
- **Measure this card (GPU page, next to Modes).** In about a minute Deck finds where your card is most efficient: for full speed memory and for Saver's memory speed, the lowest voltage the card really runs at under load and the fastest speed it keeps there. Efficient and Saver then use those speeds instead of estimates from the driver's table. The card is put at stock while it measures and is never set faster than stock; your profile goes back on afterwards, and a game coming to the front stops it. It also measures the modes below Saver under a game-like load: Low power gets the slowest speed that keeps 85 % of Saver's work per watt, Lowest power and Minimum the fastest speed their memory can keep busy, so each card gets its own speeds instead of fixed shares of Saver's. It takes about three minutes and needs nothing extra: only the graphics driver and Windows' own Direct3D. The result is kept per card and driver (measure again after a driver update), and each mode says whether its speed was measured or estimated.
- **Efficient (GPU mode).** The memory stays at full speed and the core is held at the fastest speed it reaches at its lowest voltage, worked out from the card's own table. The most frames per watt at full memory speed: on an RTX 3070 in FurMark, 154 fps at 146 W against 126 fps at 257 W stock; an RTX 3080 in Warframe, 149 fps at 148 W.

### Fixed
- **Switching GPU profiles in a game no longer resets the graphics driver.** While a profile changed, the old speed lock came off before the new memory speed was on: going from Lowest power to a 100 W profile with a +265 MHz offset let an RTX 3080 boost for a moment with the offset at speeds it isn't stable at, and the game crashed ("Windows has restarted your GPU driver"). Deck now holds the core at a safe 1050 MHz during a switch and sets the power limit, curve and memory before it lets go. Note: an overclock offset that is only safe under a low power limit can still reset the driver in light games, where the limit doesn't hold the core back; give such a profile a highest speed.
- **The GPU modes fit their cards.** Seven or more modes in one row left each card too narrow (names cut off, labels sticking out); they now wrap into rows.
- **A page opens at its top.** Going to another page kept the last page's scroll position, so a short page could open scrolled down with its buttons out of view.
- **Efficient and Saver on cards whose driver table is off.** On an RTX 3080 the table pointed Efficient at 1545 MHz and Saver at 1095 MHz, while the card really runs 1365 / 1350 MHz at its lowest voltage. In Warframe 1350 MHz gave 10 % more frames per watt than 1545 (0.85 against 0.78 fps per watt). Measuring the card fixes both.
- **Saver no longer drops the power limit to the card's lowest.** On an RTX 3080 the lowest limit (100 W) left about 40 W for the core once the memory had its share, and the core fell to 450 MHz: 62 fps at 102 W in Warframe, fewer frames per watt than Normal. The lower speeds already do the saving, so Saver keeps the card's own limit (a card whose speeds can't be locked still gets the lowest limit). Saver's memory speed is now the one clearly below full speed that still feeds games (5001 MHz on RTX 30 cards), also where it doesn't lower the core's voltage: in Warframe it gave 0.93 fps per watt on an RTX 3080 against 0.85 at full memory, at the same core speed.
- **A GPU curve profile without a speed lock no longer reports "Core clock lock: invalid value".** The undervolt cap mistook the flat bottom of the card's own curve for an undervolt and asked for a lock below the lowest speed the card allows.
- **GPU undervolt curves stay undervolted.** A curve that holds one speed from a low voltage up (Afterburner style) tilted upwards as the card warmed, and the card climbed to over 1 V for a few MHz: on an RTX 3070, 930 MHz at 1031 mV and 72 W. Deck now also caps the speed where such a curve turns flat, and moves the cap as the card warms or cools: 870 MHz at 750 mV and 49 W on the same card.
- **A GPU profile stays on when Deck restarts** (after an update or a crash restart). Quitting gave its speed and memory locks back to the driver, and Deck went on showing the profile as on while the card ran without them; it is now applied again.
- **GPU profile switches no longer mix or undo each other.** Two switches at once (a shortcut key held down) each rewrote the whole curve, and the check for a driver reset could put the previous profile back a moment after you picked another one.
- **Saver (GPU) keeps games playable.** It held the memory at its 810 MHz step, which cut fps to about a fifth. It now uses the card's most efficient speeds, worked out from the driver's own table: a memory speed that still feeds games but lets the core run at a lower voltage (5001 MHz on an RTX 30 card), and the fastest core speed at that voltage. **Ultra saver is gone** (memory and core at their lowest: about a twelfth of the fps).

## 2.9.5 — 2026-10-27

### New
- **Gaming** (was Game boost): a **profile for each game**, switched on when the game starts and back when it closes. Each game can have its own **graphics card** mode or profile, **processor and power plan** (a CPU profile, or Windows' fastest plan), **frame rate limit**, **game priority** and what frees up the PC (**close apps**, **background apps** at lower priority, **free memory** off / when low / on, **pause Deck's downloads**); anything not set follows the **Default profile**. Laid out like a game library: your games on the left with their artwork, the picked game on the right with its figures and settings, each change saved at once (and applied at once when the game is running).
- **Your games are found by themselves**: Steam, Epic, Riot (League of Legends, VALORANT, Teamfight Tactics, …), and games from EA, Battle.net, Ubisoft, GOG, Rockstar and other publishers; others once you play them with Deck running, or add one by its program. The list is kept, so it shows at once, and rechecked in the background; an uninstalled game drops off.
- **Game artwork for every game**: Steam's and Epic's own, then PCGamingWiki's official covers, the Steam store, GOG's catalogue and Wikipedia, without any account or key. Pictures of the wrong shape are framed, not cropped.
- **Frame rate limit per game**: kept by the **NVIDIA driver** itself (the Control Panel's Max Frame Rate: it works even when Deck isn't running and nothing hooks into the game), or in **RivaTuner**'s profile for the game on other graphics cards.
- **Game priority**: the game gets the processor and the graphics card before other programs while it runs (Windows' own priority settings, any graphics card), put back after.
- **Session figures**: each session's time, average FPS, 1% low, GPU watts, **FPS per watt** and highest temperatures, per game and under Sessions.
- **Built-in CPU modes** on the CPU page: **Performance**, **Balanced**, **Quiet**, **Saver** and **Ultra saver**, the same on every PC, usable everywhere a profile is (tray, phone, Gaming, plugged in / on battery). Copy one to make your own.
- **The GPU page's live readings** sit on the right like the CPU page's: the core clock with its history, temperature, load, power **against the power limit in force** (and whether that limit is what holds the card back), memory, fan, voltage and video memory.
- **Controller overlay: a position for each game** (optional): Move / resize while a game is running keeps that place and size for that game only.
- **Free memory now** on Gaming → Apps to close does the full clean (every program's idle memory and the cache, as Clear RAM does), separate from closing apps.
- **Built-in GPU modes** on the GPU page: **Fastest**, **Normal**, **Quiet**, **Saver** and **Ultra saver**, worked out by Deck from your card's own limits and speeds (Fastest uses whatever headroom the card has: its highest power limit and/or temperature limit; a mode that would come out the same as another on a card is left out, so a card that allows no changes has only Normal). One click puts a mode on the card, and modes work everywhere a profile does: the tray, the phone, a shortcut key, desktop and Start menu shortcuts, Gaming and "Apply a profile at start". Their settings can't be changed (another card gets its own); **Copy to my profiles** in a mode's ⋯ menu makes an editable copy. Your own and Afterburner's profiles are under **Your profiles**.
- **A new GPU profile editor**: four blocks, **Power**, **Speed**, **Memory** and **Fan**, each setting with a plain name, its technical name under it (power target, core clock lock, memory clock offset…), a dot when it differs from the card's own and a reset. **Start from** fills a new profile with a mode's settings. A banner says whether the profile is safe or an overclock, and the first overclock is explained once (Cancel takes it back). **On the card now** shows watts, speed, memory speed, temperature, fan and load every second, and after **Try it** what the card does with the profile. The header is one row (icon, name, shortcut key); desktop and Start menu shortcuts are under More (also in the CPU editor).
- **Lower speeds in GPU profiles** (NVIDIA): **Highest speed** and **Memory speed** (Card decides, Full, Half, Low, Lowest) use NVIDIA's clock locks (what `nvidia-smi -lgc` and `-lmc` do), so the card can use less than the lowest power limit its driver accepts (100 W on an RTX 3080). The memory runs only at the speeds its firmware has (on an RTX 3080: 405, 810, 5001 and 9251/9501 MHz); a memory offset moves only the top steps (on an RTX 3080 down to 8501 MHz), so the editor shows it only there, with the speed it gives, and says so at the other steps. Fan choices: Card decides, Quiet, Cool, Fixed or your own curve. The Speed block says the fastest the card will run and which setting decides it; on the voltage curve, Highest speed is a red line the curve can't be drawn or dragged above (editing trims it there; Undo takes that back), and when Highest speed is below the whole curve the graph makes way for a note with "Turn off Highest speed" and "Drop the curve". A grey area shows where the curve can't go (NVIDIA lets each point move at most 1000 MHz from stock, so at high voltages it can't go below about 1000 MHz), and a point at that limit says so. When Highest speed is so low that no offset, curve or voltage boost can change anything (for example at the card's lowest speed), those are hidden behind a note that says why, with Clear them and Turn off Highest speed. The curve's Hold / Shift inputs moved behind **Curve tools** and say they only reshape the curve. Locks are let go when Deck quits, on Back to stock (also locks set by nvidia-smi), and after a crash. Every NVIDIA card gets the locks its generation supports: the core lock on GTX 16 / RTX 20 and newer, the memory lock on RTX 30 and newer; the speeds offered are the card's own.
- **Sound is now Sound and mic**: every microphone with its level, mute, **boost** (when the driver has one), **which mic apps and games use and which calls use**, a **Test** that makes its meter move (records for up to a minute, keeps nothing) and **Hear it on the speakers** (Windows' "Listen to this device"). Playback and recording devices can be **renamed**.
- **Virtual display** (Phone page, optional, not installed unless you ask): a screen made by a free, signed driver (Virtual Display Driver 25.7.23), so the phone's Screen view and remote desktop still show something with the monitor unplugged or a laptop's lid closed. Off, **When no monitor is connected** (turns on by itself and off again when a monitor comes back) or Always. Deck checks the download's checksum and signature before installing, and Uninstall removes the device and the driver.
- **More monitor settings** (Display page, per monitor): the monitor's own settings over DDC/CI, what its menu changes: **sharpness**, **colour preset**, **red / green / blue gain**, **speaker volume** and **input** (it asks before switching away from this PC), only those the monitor lists, with its own choices. On NVIDIA cards also **digital vibrance** (the Control Panel's colour saturation, 50-100 %).
- **Cancel for long jobs**: Deck's own update download, installing RustDesk, the virtual display and VB-CABLE, Clean up (measuring and cleaning) and the Store update check stop at their next safe point and say so. A step Windows already runs (an installer) finishes.

### Fixed
- **Store updates:** App Installer (and other apps whose Store bundle is numbered differently from the app inside it) is no longer offered as an update to the version already installed: Deck reads the version inside the bundle. Deck asks Microsoft's update service as a normal PC, not an Insider one.
- **Phone screen:** switching between H.264 and JPEG stays on the screen you picked (it went back to screen 1); turning Control off no longer clicks the PC (which paused a video); a picture that went grey and smeared mends itself within 5 seconds (was up to 30).
- **Virtual display:** switching it on or off shows the result at once (it took up to 10 seconds), and a switch Deck makes by itself shows on the card too.
- **Windows page:** a window's transparency keeps showing its real value after Deck is hidden and shown, and closed windows leave the list by themselves.
- **CPU profile editor:** Clock floor, Overclock turbo and Hold the cap in games are under Advanced (it opens by itself when one of them is set).
- **Mode cards** (CPU and GPU) sit on one row with their whole text.
- **The CPU profile editor keeps its place.** Changing a setting (dragging the power limit sliders, the power limit buttons, Turbo boost) scrolled the page back up; the page now stays where it is, and the slider keeps the keyboard focus.
- **Dialogs no longer close when you select text with the mouse** and let go outside the dialog (the profile editors, rename and confirm boxes): only a click that starts and ends on the dark background closes one.
- A stray **"null"** no longer shows under Gaming's Full power button (when "Turn on by itself" is off) or under its memory bar, in Home's media tile for a stream with no length, or on the Phone page's remote desktop card.
- **Fans:** "follows ?" stays on one line next to the sensor it follows.
- **Processes:** in a small window the Network column fits (its header and the upload/download figures were cut off), and memory figures no longer wrap onto two lines.
- **GPU:** the memory clock tile no longer cuts its value off ("10,501 M…") in a small window.
- **Tweaks:** the category tiles show how many settings changed under the name instead of squeezing it.
- **Death counter → Settings:** the "Not bosses" list (and "Ignored in" / "Same boss in") put the names under the text; the text was squeezed to one word per line.
- **Processes → Network:** speeds in the units chosen in Settings, like the Network page, rounded (small speeds showed long decimals such as 341.3333333 B/s).

## 2.9.0 — 2026-10-26

### New
- **Tweaks: 54 more, in 19 categories under three headings** (Clean up, Look & feel, How it works). New categories: **App permissions**, **Ads & suggestions**, **Browsers**, **Desktop**, **Keyboard & mouse** and **Performance**; long ones (File Explorer, Taskbar, Right-click menu, Desktop) have sub-headings. New, Winaero Tweaker style: hide right-click entries (Open in Terminal, Cast to Device, Restore previous versions, Scan with Microsoft Defender, Troubleshoot compatibility, Ask Copilot, Edit in Notepad, Edit with Photos, Add to Favorites); desktop icons (This PC, your user folder, Network, Control Panel, Recycle Bin); full-quality JPG wallpapers; Windows version on the desktop; no " - Shortcut" on new shortcuts; thumbnails or icons; Office.com files in Home; side pane shows all folders / follows the open folder; folder windows in their own process; reopen folders at sign-in; colour for compressed files; copy window with details; no "Look for an app in the Store"; Show desktop corner, badges and flashing on the taskbar; shake to minimise; menu delay; Toggle Keys and Filter Keys shortcuts; key repeat delay; scroll the window under the pointer; start-up apps without the 10-second wait; power throttling; automatic maintenance; restart after a blue screen; error reports; the improvement program; online tips in Settings; device makers' installers; the drag tray; Modern Standby or classic sleep. **Windows Update, as in Winaero Tweaker**: automatic updates by themselves, download and ask before installing, ask before downloading, or **Off: only when you check** (Windows' own policy: nothing is checked, downloaded or installed by itself, "Check for updates" still works, and the service stays on so Store apps, drivers and optional features keep working); stay on a Windows version (24H2, 25H2); wait 7–30 days before monthly updates and 3–12 months before a new Windows version (Pro); a warning before update restarts; updates for other Microsoft products; downloads on metered connections; skip the Malicious Software Removal Tool. Two more presets: **Debloat** and **File Explorer power user** (checklists, as before).
- **Game boost turns on by itself when a game starts** (Game boost → "Turn on by itself", off unless you turn it on): once a game has been in front for a few seconds. Turned off by hand during a game, it leaves that game alone until the game has been closed for a couple of minutes. When Full power is off and a game runs, the page says "Deck sees <game>" and the button turns it on for that game.
- **Game boost pauses Deck's own downloads** while Full power is on (on by default) and carries them on afterwards, so a Store download doesn't take the game's bandwidth.
- **Recent sessions** on the Game boost page: which game, how long, how many apps were closed and how much memory was freed, and whether it turned on by itself.
- **Network column in Processes**: upload and download per program, sortable (needs Deck running as administrator; it reads Windows' own network events, nothing is sent anywhere).
- **The Windows page is one page** with its three parts (open windows, snap zones, workspaces) and **arrangements**: side by side, columns, grid, main + side, cascade, focus, centre and minimise all, for the windows you tick. Each window shows its size, position, monitor, process id and memory, with a Maximise button.
- **More display controls** (Desktop → Display): resolution (a changed one goes back by itself after 15 seconds unless you keep it), scale, orientation, contrast (monitors that support it), and **Turn screens off**.
- **Game servers: many more games and a list that works with them**: search, pin your games to the top, the first 12 then "Show all", New World and Lost Ark (Amazon's own servers), "any game on Amazon servers" (24 regions) and "any game on Valve's network", and **Add a game** with the network it plays on.
- **Keyboard overlay: every key** (Controller → Keys): F-keys, the number row, punctuation, Enter, Backspace and the arrows, with **All keys**, **Starting set** and **None**.
- **Store apps: an app you already have says so in search** (Installed), with **Check for update**, **Update** and **Uninstall** for that one app. **Pause all** / **Resume all** for downloads, an **Install** button on a downloaded update, **Install when downloaded** (on: as before; off: updates wait for Install) and per app **Wait for Install** to keep one app from installing by itself.
- **Startup apps lists Store apps** (WhatsApp, Spotify from the Store, Teams and others), with the same switch as the rest.
- **Help on the Apps page**: the ? tips explain Uninstall, Advanced uninstall, what an app needs, Store apps and updates.
- **An on-screen keyboard on the phone's controller page.** Tap the keyboard button in its top bar: full keyboard, a small gaming set (WASD, mouse buttons, a mouse pad, scroll), and buttons of your own: any key or combo (Ctrl+Shift+Esc), mouse buttons, a trackpad area, scrolling, typed text and macros ("ctrl+c, wait 200, ctrl+v"). Each button holds while touched, fires once, or stays on until pressed again. Edit mode: drag to move, drag the corner to resize, remove (one by one or in Remove mode), duplicate, undo, add whole sets. Size and opacity are per layout. Layouts are kept on the PC (Phone page → Keyboard layouts, where they can be renamed, deleted, copied to another PC and imported) and can be tied to a game: when it comes to the front the phone shows its layout. Keys are paused while a game is in front unless "Allow keys in games" is on: when a game comes to the front, whatever the phone holds is let go at once and a macro that is playing stops. The phone sends everything it holds, whole and twice a second; the PC lets go of every key when it stops hearing from the phone.
- **"That wasn't a death" in the death counter's History**, with **Undo that**. A death taken back this way is struck out and marked "not counted" instead of deleted, and every count, boss card and stat leaves it out; "Count it again" or "Undo that" brings it back. "−1 death" (the button, your shortcut, the controller combo) still means exactly what it always did: it takes back the latest death that still counts, and skips one you already struck out. Old histories count exactly as before.
- **A boss name you give is never changed by the screen.** Renaming a fight (or tapping **Yes, that's it** on a name read off the screen, shown with "?") makes the name yours: the screen keeps following the boss's bar but stops voting on its name, right away and after a restart. Renames from before this version keep their precedence too. Names read off the screen and not confirmed show "?".
- **Fix a past boss fight from its line in History** (its menu): **Rename this fight** (that fight only), **I won that fight** / **I didn't win**, **That wasn't a boss fight**, **Add a missed death here**, and **Why is this here?** on every line, which says where the line came from as the history wrote it down (your shortcut, your controller, the death screen you taught, the save file, the boss's health), and says so when an old line didn't record it. **Same boss as…** on a boss card now makes a name rule instead of rewriting lines: the names read stay in the history, and the rule can be removed. **Not a boss** keeps the fight's deaths for the game and can also ignore that name in this game from now on, offered (ticked) only when the name read can't be one of your real bosses there. Every fix is a new line in the history, nothing is deleted, and **Undo that** takes back the last one; this game's ignored names and name rules are listed in Settings with Remove.

- **Keep a text log for testing** (Deaths → Settings, off unless you turn it on): while Deck watches a game, it writes down what it read and what it made of it, as text: where a boss bar was and how full, the words read next to it (each of the three ways it reads them, with where each line was) and in the middle of the screen, and each decision. Never a picture. It stays on this PC (`%LOCALAPPDATA%\Deck\deaths-recordings`), at most 20 MB a game, nothing is sent anywhere, and **Delete it** removes it. It lets a change to boss detection be replayed and scored on real play before it ships.

### Fixed
- **Locked files finds what holds a file or folder.** It only asked Windows' Restart Manager, which misses programs that just have a folder open or run from it; it now also looks through every open file handle (as Process Explorer does) and says for each program whether it **has it open** or **runs from here**.
- **File and folder pickers open in front of Deck**, not behind it (Deck stays on top; it now steps back while a Windows dialog is open, also for Share to phone and Save as).
- **Long lists keep their place when the page refreshes.** The clipboard history (now drawn 120 items at a time with "Show more") jumped back to the selected item on every refresh, and the Tools page jumped back to its section; any page that redraws now keeps the scroll of its inner lists, and a section is scrolled to once per visit.
- **The death counter never loses or overwrites a game's history.** A line Deck can't read (edited by hand, cut off by a crash, or written by a newer Deck) was dropped the next time a death was saved, and so was any field Deck didn't know; a history that couldn't be read at that moment (locked by another program, or not plain text) counted as empty, and the next death saved a one-line file over it. Now every line and field Deck doesn't understand stays exactly as it was, and lines Deck didn't change are written back byte for byte. A history that can't be read is left alone: new deaths are kept in `<game>.jsonl.pending` and added once it can be read. Before a history is replaced, Deck checks that it is still the file it last wrote and keeps the old one (`.bak` from the start of the session, `.prev` from before the last save); if something else changed it, nothing is overwritten and the Deaths page asks which version to keep. Deck never deletes these copies. The Deaths page says when a history couldn't be read or saved, and what was kept where. Deck 2.8.4 and older still drop lines they can't read: going back to one of them can lose what a newer Deck wrote (the copies stay).
- **The Store update check gives the same answer every time.** Microsoft's update service is a pool of servers and many of them have an old catalog, so the same question is answered with the newest version of an app or with the one before it (Raw Image Extension 2.5.42 or 2.5.35, HEVC Video Extensions 2.4.151 or 2.4.110), whatever the host name, connection or cookie. The Store catalog is as old as those servers and has no download links. Deck now asks several times and keeps the newest version listed (8 answers for an app updated in the last 120 days, 4 for the rest when the first answer shows no update), and remembers the newest version it has seen for each app (Deck\store\seen.json, forgotten after a month) so an update seen once stays on offer when a later check only reaches old servers. Installing an update asks again until the version seen before is listed.
- PC to PC → Settings → **Let Claude Code use PC to PC** told Claude Code to run Deck from the old per-user folder, where Deck no longer is. It now names `C:\Program Files\Deck`, and a skill already installed is updated when PC to PC starts.

### Changed
- **A false boss can no longer feed itself.** A name read off the screen opened a fight on a single read when it looked like a boss already in the history (60% of its letters in order), and every name the screen had ever read counted, including menu and item lines taken for a boss once ("Deep Shadow Pauldrons"). Now only names you gave or confirmed count (a fight you started, renamed, confirmed with **Yes, that's it** or named from History, and your **Same boss as** rules), not ones only the screen read nor renames from before Deck recorded who made them, and a read must be that name or a letter off: "Margit's Shackle" isn't Margit, and "aldii" isn't taken as "Xaldin" on one read. Every other name is read twice the same before a fight opens, as names new to a game always were. Nothing in the history changes.
- **Each line of a death counter history has an id** (`"id":"e12"`), given once in the order of the file and never changed, so a fix can point at exactly that line. Existing histories get theirs at the first save, after a copy of the file as it was is kept for good (`<game>.jsonl.pre-ids.bak`); no count or stat changes. "Delete this line" now deletes the line by its id, so it can't hit another line if the history changed since it was shown.
- The docs are fewer and match the code again: the contributor rules are in `DECK.md` §0 (no separate CONTRIBUTING.md), the trust boundaries are part of `SECURITY.md`, each feature's design and plan are one file in `docs/design/`, and the audits are one `docs/audits.md`.
- Three commands nothing in Deck used any more are gone (the old games list, and the hardware report and lights test that the support report now covers).

## 2.8.4 — 2026-10-23

### New
- **Tick the apps to update** (Maintenance → Apps → Store apps & updates): every update has a checkbox (all ticked to start with), with "N of M ticked", **Tick all** / **Untick all**, and the update button becomes "Update N selected here". The Microsoft Store's own "Update all" can't skip apps, so Deck asks before using it while some are unticked and names them.

### Fixed
- **Store "updates" that were only another version number are gone.** Microsoft lists many apps a second time under a different kind of number (Windows Terminal 3001.24.12741.0 for the 1.24.12741.0 you have, Calculator 2021.2607 for 11.2607, Snipping Tool 2022.2608.41 for 11.2608.41), and Deck took the highest number. Those are the same build and are no longer offered. One listed under another numbering but with a clearly higher build part (Realtek Audio Control 1.52.357 → 2.54.397) is still shown, flagged "Different version numbering", and not ticked.
- **A Store update that Windows refuses now says why.** "A prerequisite for an install could not be satisfied" (0x80073CFD) told nothing; Deck now reads the package's own list of needs and names what this PC lacks (a driver, a framework package, or a newer Windows), and says the app on this PC is unchanged. Example: Realtek Audio Control 2.54.397 needs the driver Realtek-RealtekRS5HSA.inf, which this PC doesn't have.
- **Leftover downloads are removed.** Downloads of updates that were dropped, never installed or can never install stay in Deck's store folder for good (1.1 GB of them on one PC). Deck now removes the folders nothing needs after every check and after "Clear finished", and a package Windows refuses for a missing driver or newer Windows is deleted right away, since "Try again" could never work.
- **The right build of an app is followed.** One Store listing holds packages for several Windows versions under different numbering (Calculator 11.x for Windows 11, 2021.x for Windows 10; Realtek 1.5x and 2.5x), and Deck took the highest number. It now follows the numbering of the installed app (Realtek's update is 1.54.396, not 2.54.397, which needs a driver this PC lacks), versions are compared as four numbers ("1.0" equals "1.0.0.0"), and an app installed twice is checked once.
- **No download for a version that isn't newer.** Microsoft's update service sometimes answers with an older list than a moment before (the newest version missing). Before downloading, Deck checks that the version is really newer than the installed one, asks again a few times if not, and otherwise stops with a clear message instead of downloading the same version.
- **The Store catalog lookup is retried too**, and its errors no longer show the whole web address. A Store listing with no package of its own is counted as not checkable, not as a failure, and the failure note lists each different reason.
- **Faster checks:** the list of installed packages is read once per check instead of once per app.
- **"N apps couldn't be checked … status code 500".** Microsoft's update service sometimes answers a server error or turns requests away when it is busy; Deck gave up on the first one. Now each request is tried up to 4 times with waits in between, Deck asks four apps at a time instead of six and reuses its session cookie, and the apps still turned away are asked about once more, one at a time, at the end ("Asking again for N apps…"). If some still fail, the note names them, says what the error means and that Deck already tried several times, and has a **Try those again** button.

## 2.8.3 — 2026-10-23

### Fixed
- **Death counter: menus, prompts and item banners are no longer taken for bosses** (seen in Dark Souls II: "Inventory", "Rest at bonfire", "Pick an item", "Shop", item pick-up banners, an overlay's "10ms"). Text beside a bar that starts with a button's picture read as a letter, a clipped prompt, letters read one by one, an overlay reading (ms, fps, MB…) or a menu word is not a name, and a name Deck hasn't seen before must be read twice in a row before a fight opens on it, so a banner that changes or goes away opens nothing.
- **Death counter: deaths whose banner fades in over a moving scene are read.** Deck only read the screen once the picture had settled, which a slow death fade over a still-moving, darkening scene never does, so some deaths were never counted. A sudden dimming now makes Deck read the screen about every 0.7 s for the next 6 seconds, settled or not.

## 2.8.2 — 2026-10-22

### New
- **Check a file** (System → Processes → *Check a file…*): pick any file and run the same four checks as the Safety column (signature, AV engines, Defender, VirusTotal with your key) once, privately. The file's path, fingerprints and results are kept in memory only and forgotten when the window closes; the file itself never leaves the PC, and the online checks ask by fingerprint.
- **Processes are grouped like Task Manager**: *Apps* (programs with a window) and *Background processes*, with counts. A program with several processes has a chevron that opens each one (PID, CPU, memory) with its own **End**, which says whether Windows ended it. This replaces the "Apps with windows only" switch.

### Changed
- **Leftover search is more careful.** A folder found only by its name is offered but not ticked when it holds 3000 or more files (browser profiles, caches, game data), or, in data folders like AppData and ProgramData, 5 or more programs. A name that sits inside another installed program's longer name ("Foo" for "Foo Pro") is not ticked either, and the row says which program.
- The Processes table keeps the program name readable in a narrow window.
- **More programs can be checked.** Protected services (csrss, lsass, MsMpEng, the "System" process and others) used to show "—" in the Safety column because Deck couldn't read their file; Deck now asks Windows the way Task Manager does, (asking by process id, which needs no access to the process and also works without administrator rights), so every program has a file to check. The kernel's own processes (System, Registry, Memory Compression, System Idle Process, Secure System) have no file; they are checked through the kernel file they run from (`ntoskrnl.exe`, `securekernel.exe`), and their rows say so. That shows whether the kernel file is genuine and unchanged; a file check can't see malware that exists only in kernel memory. The checks bar still says how many programs can't be checked, and hovering it names them. It now counts **files** ("Check all 86 files") and says why that is fewer than the programs listed ("89 programs listed: 4 kernel parts share 1 kernel file"), and the Signatures result line names the unsigned programs and the ones whose signature doesn't hold.

### Fixed
- A cancelled or refused uninstall no longer leaves the "Deck was closed during the advanced uninstall" warning on the Apps page.
- The do-nothing stand-in used to repair a broken Windows Installer uninstall is never put inside Windows' own folders.
- Game Boost no longer picks a browser Windows has registered (a portable one missing from Deck's list) as the running game.
- A tweak that failed partway puts back the part of the failing step that had already changed, not only the earlier steps.
- The all-programs file check says "Nothing to check" when no file can be read.

## 2.8.1 — 2026-10-22

### New
- **Safety checks for running programs** (System → Processes). Each check is optional and runs for every program at once; the results sit side by side in a new **Safety** column:
  - **Signatures**: who signed each program (Windows' own check), or **Unsigned**, or **Bad signature** when the file changed after it was signed.
  - **AV engines**: the share of antivirus engines that flag the file, from Team Cymru's Malware Hash Registry. Free, no key, about a second for everything.
  - **Defender**: Microsoft Defender scans each program file. Nothing is removed or changed.
  - **VirusTotal** (optional, with your own free API key): detections like "0/72", 4 files per request (16 a minute on a free key), the riskiest programs first; click a result for the full report. Dropped connections are retried; files looked up before are skipped.
  - Only a file's fingerprint leaves the PC, never the file. Results are kept per file and checked again only when the file changes.
  - **Sort by risk**: click the Safety header (Defender threats first, then detections, broken signatures, unsigned).
- **Death counter: "Watch in"** (Death counter → settings). By default the screen is only watched in games Deck knows how to read: games on its list, games with death screens taught or shared, and games you've counted a death in yourself. "Every game" brings back the old behaviour.

### Changed
- **Every uninstall now looks for leftovers** (Maintenance → Apps), not only Advanced: afterwards you get the list of what's left and pick what to keep and what to delete, or a box saying nothing was left. Deck comes back to the front when the uninstaller finishes, and the result stays on screen until you close it.
- **Windows Installer uninstalls say what really happened.** Deck keeps Windows' full log and explains failures in plain words (cancelled, already gone, another install running, needs admin, the installer package missing, the exact error from the log). When another install is still running it says so instead of starting.
- **Broken Windows Installer uninstalls repair themselves where possible**: when a program's folder was deleted earlier and its uninstall needs a file that was in it (error 1721/1722), Deck puts a do-nothing stand-in there, lets Windows finish, and removes the stand-in. A stuck Windows Installer service (error 1601) is restarted once.

### Fixed
- **Leftover search could tick a publisher's whole folder** (for example a shared "Autodesk" folder holding other products) when an app recorded that folder as its install folder. A publisher's name never counts as one app's name now, and a recorded install folder is ticked only when it carries the app's name or holds its uninstaller (an add-on installed into a game's folder no longer offers the game). Folders in Documents are never ticked. The leftover list is wider and long paths wrap.
- **The death counter showed up over fullscreen videos in browsers it didn't know** (Waterfox and others): every browser Windows has registered is now left alone, plus more browsers, players and apps (LibreWolf, Floorp, Zen, Thorium, Stremio, Kodi, Plex, Spotify, Discord and others). This also keeps Game boost from treating them as games.

## 2.8.0 — 2026-10-22

Everything in 2.7.9 (below), plus:

### Added
- **The death counter finds boss fights by itself** (Deaths → Settings → Find boss fights by themselves, with screen watching on): when a boss's health bar comes up, Deck reads the boss's name next to it and opens that boss's fight, times the try from when the bar showed up, ends it at a death, and counts a win when the bar empties and goes away (or a victory banner shows). Bosses with phases or cutscenes stay one try. For a game whose bar sits somewhere unusual, show Deck the bar and the name once on a picture. Names you mark "Not a boss" are left alone.

### Changed
- **Deck's own updates show a progress bar** (Settings → About → Updates): how far the download is, in percent and MB.
- **The overlay key shows the overlay at once**, also in busy games (Helldivers 2): RivaTuner's own "show" switch is now flipped the moment the key is pressed, for 64-bit games first, instead of after Deck's next sensor read.
- **Deck's log says much more**, so a problem can be found from the log alone: failed web requests and programs, failed buttons and page errors, profile switches, updates, the phone remote's connections and refusals, share links, Game boost, Clean up, display and startup-app changes, the hardware engine starting and handing the fans back, controllers coming and going, and the death counter's watching. Passwords, keys and tokens are masked, your user name is taken out of paths and the PC's name out of every line, and a line that keeps repeating is counted instead of filling the log. The support report now includes the last 80 lines. For even more detail, put an empty file named `debug` in `%LOCALAPPDATA%\Deck\logs`.

### Fixed
- Settings → Updates: pressing **Check now** while an update was downloading or installing brought the **Install** button back as if nothing had started. Check now now leaves a running install alone.
- **Apps → Advanced uninstall** could offer one of your own folders as a leftover: when a program recorded Documents, Desktop, Downloads or a whole drive as its install folder, that folder was offered, ticked. Your own folders (also when moved to another drive), and anything that holds one, are never offered or removed now. A folder named after the app in Documents (often your own work, like a notes vault) and an install folder right on a drive (`D:\Games`) are still listed, but unticked.
- Phone remote: a phone becoming a controller held up the other phones' connections for up to 2 seconds while Windows numbered it.
- Transfer's own log (`log.txt`) grew without limit; it now keeps two files of 2 MB.
- The death counter could keep Windows' text reader busy for minutes at a time, reading bars that aren't a boss's (a flickering HUD bar, an enemy's bar that moves with it) over and over. After a bar with no name, the next one is read only after a short wait, and a real boss's fight still starts from when its bar showed up.
- The death counter no longer takes a game's own messages for a boss ("Bot Drop Detected" in Helldivers 2), drops names made of reader noise ("Ei.atL1"), and takes a stray accent out of a name ("Mutatéd" becomes "Mutated").
- Deaths → Now: the big numbers sat in black boxes. The page is laid out again: the game, its fight and both counters in one card, the session's numbers in a card like Records, and the session's deadliest boss no longer looks like the all-time one.
- Every overlay key press logged "the 32-bit helper couldn't set RivaTuner's switch" although it had: the helper's "changed it" answer was read as a failure.

### Changed (performance)
- The controller overlay checks for a controller 4 times a second instead of 20 while it is hidden and none is connected.
- The in-game overlay's loop sleeps until it is woken, instead of checking 40 times a second whether something changed.

## 2.7.9 — 2026-10-21

### Added
- **Apps** (Maintenance → Apps): everything installed on the PC, with search, sorting by name, size or date, and Desktop / Store filters.
  - **Uninstall** runs the app's own uninstaller and waits until it has really finished (also uninstallers that copy themselves to Temp first).
  - **Advanced** uninstall: the uninstaller first, then a search for what the app left behind: its folders (Program Files, ProgramData, AppData, Documents), its registry settings, Start menu and desktop shortcuts, and Windows services that run from its folder. You tick what goes; folders go to the Recycle Bin, and registry keys and services are saved to a .reg backup first. Only names that match the app exactly are offered, and nothing another installed app uses.
  - Apps whose uninstaller is missing can still have their entry and leftovers removed.
  - **Apps missing from Windows' list** (known to Windows Installer, but their entry was removed by a cleanup tool or a half-finished uninstall) are listed too and uninstall normally; apps whose folder is gone are marked **Files gone**. A **Needs attention** filter shows just these.
  - Built-in apps and Store apps moved here from Tweaks (tabs **Built-in apps** and **Store apps & updates**).
- **Store app updates** (Apps → Store apps & updates): checks every Store app against Microsoft's servers and lists the ones with a newer version and its size. **Update** downloads and installs it without the Store; **Update all here** goes one app at a time; **Update all with the Microsoft Store** asks the Store to do it. Each app shows its progress (size, speed, time left), can be stopped and carried on later from where it stopped, and has its download links to copy. The list and the downloads survive Deck closing or crashing. Apps that couldn't be checked, and why, are listed instead of being counted as up to date.
- **Phone as a controller without the screen** (phone remote → Screen → Use as a controller): just the controller, on its own connection, so a press reaches the PC with the least delay; the round trip is shown in ms. Several phones become several controllers (Player 1 to 4, shared with real controllers and DS4Windows), each phone showing its player number. Size, opacity, a background (colour or photo) and the layout (follow the phone, or always sideways) are remembered on each phone; holding the phone upright gives an upright layout.
- **Tweaks explain themselves:** every tweak says, in plain words, what you gain and what you give up.
- **Hide after opening an app** (Settings → General, quick panel): off keeps Deck open after starting apps, files or links from it.
- PC to PC: a transfer cut off by Deck closing (or cancelled) has **Carry on**, which sends only what the other PC is missing; the transfer list survives restarts.

### Changed
- **Tweaks are checkboxes** worded as what Deck does ("Show hidden files and folders"): ticked is Deck's change, unticked is Windows' own setting. Lists of choices mark Windows' default.
- Apps, files and links opened from Deck's search start in the background: Deck no longer stops responding while an app asks for administrator rights, and the UAC prompt comes to the front.
- Workspace Sync's problems say what happened and what to do (for example a cloud folder switched on with no folder chosen).
- Phone remote: full screen notices when the browser quietly left it, and says so when the browser doesn't allow it. Files sent to the phone stay listed after Deck restarts, and an interrupted download on the phone can continue (Deck now tells the browser the file is unchanged).
- An advanced uninstall that Deck was closed in the middle of is offered to finish on the Apps page.

### Fixed
- **Open RivaTuner** closed RivaTuner by force, which could leave Deck or a browser frozen. It now asks RivaTuner to close, and Deck's own windows are kept out of RivaTuner's hooks.
- "Update all with the Microsoft Store" seemed to do nothing when the "Don't update Store apps by themselves" tweak was on (Windows blocks the Store's background updates then). Deck now says so and offers what works; otherwise it reports which apps the Store started or cancelled.
- "Open in Store" for paid apps did nothing.

### Also in this version
- **Phone remote, Screen view:** an on-screen controller in the PlayStation layout (two sticks, D-pad, face buttons, L1/R1/L2/R2, L3/R3, Share, PS, Options; several fingers at once), with its size and opacity in Settings. The PC sees it as an Xbox controller (needs the ViGEmBus driver). **Hold click** keeps the left button down while your finger is on the screen. F1 to F24 in the Keys bar. **Control in games** lets taps and keys reach a game in front (off by default).
- **Workspace Sync for Claude Code** (was "Claude Code sync") carries more than conversations now, so a project can be picked up on another PC:
  - **Project files** (Settings → What to sync, off until you turn it on): each project's folder is kept the same on your PCs, without `.git` and build output. Folders over 40,000 files or 3 GB, a drive, or your user folder are never copied. Deleted files go to the trash folder on the other PCs, and switching it off deletes nothing. **Build files** (target, node_modules, .venv…) can be included too.
  - **Per project:** switch a project's sessions off and keep its memory and files syncing, to start a new session on the other PC and carry on with the project. Its files can be switched off on their own as well.
  - **Programs:** each PC shares which Rust toolchains, targets and components, cargo tools, Node and global npm packages, Python, pipx tools and Git it has. The Status tab lists what another PC has and this one doesn't, with Install (a PowerShell window with your normal rights; nothing installs on its own).
  - **Tailscale is visible:** Settings has an "Over Tailscale, from anywhere" switch with its state (not installed / not connected / which of your PCs are on it, with Get or Open Tailscale), the Status tab shows "Away from home", each PC says whether it is reached over the home network or Tailscale, and PC to PC shows the same. The cloud folder works with any synced folder (OneDrive, Google Drive, Dropbox, MEGA, pCloud, Syncthing).
  - **MCP servers** (yours and each project's, from `.claude.json`) sync with the settings, and wait for your OK like hooks and plugins do. Added on two PCs at once, both lists are kept.
  - **Git history:** files are copied without `.git`; on a PC whose copy has no git, Projects offers **Get git history** (connects the folder to the same remote and branch, files untouched).
  - **Safer with different PCs:** a project folder only guessed from another PC waits until you keep or move it before files arrive, and a guess under the other PC's user folder becomes the same place under this PC's. Build files aren't copied between an ARM and an Intel/AMD PC. A project stops copying when its drive has under 2 GB free. Rust toolchains are compared as "stable" and the like, so each PC installs its own kind. The program check also covers Microsoft's C++ build tools, which Rust needs.
  - **Far fewer disk writes:** the sync state is saved only when it changed, and the file-hash cache at most every 10 minutes (before, about 1.2 MB was rewritten every cycle even when nothing changed).
  - A project's own `.claude` settings, hooks and `.mcp.json` wait for your OK too; `.claude/settings.local.json` stays on each PC.

### Changed
- The design notes moved to `docs/design/`.

### Security
- Updated the TLS certificate checks (rustls-webpki 0.103.16, webpki-roots 1.0.10) for RUSTSEC-2026-0381 and RUSTSEC-2026-0382: distrusted emSign intermediates could have been accepted.

## 2.7.5 — 2026-10-20

### Added
- **Your phone as the PC's speaker or microphone** (Deck → Phone → Speaker and mic, both off until you turn them on; the phone remote gets a Speaker and mic card). **Speaker:** the phone plays the PC's sound, with a switch to turn the PC's own speakers off while it plays (they come back when it stops, even if Deck closes meanwhile). **Mic:** the phone's mic becomes a mic on the PC, with echo and noise cancelling, so Discord, games and calls can use it; pick "CABLE Output" in an app, or turn on "Make it the default mic while the phone talks" (your mic comes back after). Over Wi-Fi, about a tenth of a second late. The mic needs VB-CABLE, VB-Audio's free virtual cable, because Windows only lists a microphone that a driver makes: Deck turns on one that is installed but off, or downloads VB-Audio's own setup for you (its licence doesn't allow building it into Deck's setup).
- **Tweaks** (Maintenance → Tweaks): 132 Windows settings in 13 categories (privacy, Start and search, taskbar, File Explorer, right-click menu, appearance, multitasking, gaming, AI and Copilot, updates, network, system, advanced), from Win11Debloat and Chris Titus Tech's WinUtil, each checked, plus Deck's own. Every switch shows what Windows is set to right now ("Partly" when another tool set part of it), what it changes, its risk and whether it needs Explorer restarted, a sign-out or a restart. **Every change can be undone to exactly what it was before** (one by one or all at once), also months later; Deck notices when a Windows update changes a tweak back and offers to apply it again. Presets (Privacy, Clean Start & taskbar, Gaming, Quiet Windows) and "Recommended" open as checklists, never as one click that does everything. A restore point is offered before Advanced tweaks. Options that don't exist on this Windows version or this PC are hidden. Tweaks also turn up in Deck's search, and a PC to PC setup carries them to your other PC. Deck never removes Edge or WebView2, turns Windows Update or Defender off, or runs scripts from the internet.
- **Built-in apps:** remove Clipchamp, News, the Xbox apps and the rest (Win11Debloat's list with its safe / optional / needed rating), and reinstall any of them later.
- **Store apps without the Microsoft Store** (Tweaks → Get Store apps), like store.rg-adguard.net: search the Store, then Install, Download (to Downloads\Store apps), send to FluxDM, or copy the links. The files come straight from Microsoft's own servers, only the ones this PC is missing (usually just the app), checked against Microsoft's checksums, with a progress bar, speed and time left. Free apps only; desktop apps from the Store install with winget.
- **The phone remote also answers on https** (same address, `https://`). Phones allow the mic only on secure pages; Deck makes its own certificate, so the phone warns once ("not private") the first time.

### Changed
- **Store apps download about six times faster:** each file comes in 8 parts at once (Microsoft's servers give one connection only so much; WhatsApp's 311 MB took about 27 minutes on one). A cancelled or failed download has **Carry on** / **Try again** and continues where it stopped.

### Fixed
- PC to PC's "restart Explorer" after applying a setup started Explorer with Deck's admin rights; Windows now restarts it as you.
- Settings → Updates said "GitHub's answer wasn't understood" on every check after the first while no new version was out (GitHub's "nothing new" answer was read as a broken one). Updating itself wasn't affected.
- Turning the phone remote off and on moved it to the next port (the old one stayed open), so a phone's saved link stopped working.
- Undoing *Variable refresh rate* also undid *Windowed game optimizations* when both were changed (they share one DirectX setting); each now puts back only its own part.
- Deck's own updates (and the RustDesk setup) gave up after 60 seconds (5 minutes for RustDesk) of downloading, so on a slow line a release bigger than about 10 MB could never install by itself. Now only a connection that stalls for a minute ends them.
- Game boost could end an unrelated program that had just started and been given the ID of an app boost was closing (Windows reuses process IDs); it now checks the program first.
- RustDesk's, Tailscale's and winget's command lines that hang (a stuck service) no longer freeze the Remote desktop page or PC to PC: every program Deck runs has a time limit.
- Timers and Tweaks that shut down, restart or sign out said "done" even when Windows refused (another shutdown already scheduled); they now say why.
- The phone mic stayed "on" but silent when VB-CABLE went away mid-call; the phone now reconnects and says why. When Windows doesn't restart Explorer by itself (some debloat scripts turn that off), Deck starts it without its admin rights. Installing Store apps and VB-CABLE's setup no longer fail for a Windows user name with an apostrophe.

### Security
- **Tweaks' undo list can't be used to change Windows behind your back.** Undo writes the saved values back with Deck's admin rights, and the list lives in your own folder, where any program could edit it. Deck now keeps its fingerprint where only administrators can write; a list changed by something else is set aside (Tweaks says so) and never used, and undo only ever touches what that tweak itself changes.
- **"Unpin everything from Start" and Store downloads work with your rights only** in your folders (a folder swapped for a link can't make Deck read or write elsewhere).

## 2.7.0 — 2026-10-20

### Added
- **A new in-game death counter.** Pick how it looks: a skull with a big number (the default), a ring that fills toward the deaths your last boss took, or one huge number. It can count this boss, the whole game, or both side by side, and shows the game's total between fights (or nothing).
- **The card after a death.** When you die, the counter opens into a card for a few seconds: the boss, your next try, its deaths, how long that try lasted, your time on the boss, deaths this session, bars for your last 10 tries, and a highlight like "Your longest try yet" or "100th death in this game". Every line can be switched off, and so can the card.
- **Red edges on a death** (off by default): the screen's edges glow red for a moment.
- **A live preview** of the counter and the card next to their settings, drawn by the same code as in the game.
- **Play sessions.** Deck notes when you play each game; the History tab is now one card per session (how long, deaths, bosses beaten, deaths over time) with the events inside, instead of a long list. Older history gets sessions worked out from when your deaths were counted.
- **Boss cards** instead of the table: deaths, time, longest try, which try beat it, and a line of how long each try lasted, so you can see yourself learning a fight. Each boss can have a note (a strategy, a reminder), and the card after a death can show it.
- **Records** on the Now tab (longest try, quickest win, deadliest boss, most deaths in a session) and this session's numbers.
- **All games together** on the Games tab: total deaths, time played, bosses beaten, deaths per week, the deadliest games and bosses.
- **Share and export.** "Share" copies (or saves) a picture of a game's or a boss's numbers; "Export" saves a game's history, or everything, as a spreadsheet file.

## 2.6.1 — 2026-10-20

### Fixed
- **Death counter: dark death screens are read.** Windows' text recognition read nothing from a dim red banner on a dark screen ("KHAZAN HAS FALLEN"); Deck now makes the middle of the picture high-contrast before reading it, and a long phrase may have a letter or two misread. The First Berserker: Khazan is recognised outside Steam too.
- **Teaching a death screen works in dark games and when you count late.** Deck keeps the last 20 seconds (it was 10). When the whole screen fades at death, Deck learns the words or symbol that stand out on it instead of refusing it as "one flat colour", and ignores the character and scene behind them, which differ at every death.
- **Death screens keep their colour.** Pictures were turned grey by brightness, which made red words dull; Deck now uses each spot's brightest colour, and the teaching pictures are shown in colour.

### Changed
- **Games are known by their program only.** The death counter no longer uses Steam or Epic numbers or library lists: a game is its exe, the same in every store, named from the program's description, its install folder or its window title. Deck's list of games with their own death screens or save readers is now the 17 it knows by exe (an Easy Anti-Cheat launcher no longer counts as Elden Ring). Death screens taught under an older Steam key need teaching again.
## 2.6.0 — 2026-10-20

### Fixed
- **No more "Set up" after an install or an update.** The setup is the one place that asks for admin rights: it makes Deck's admin tasks itself and starts Deck hidden through them. Before, the setup started Deck as a normal user and every install showed the Set up banner again. A Deck started without admin rights (the setup's "Run Deck" box, a shortcut) while the tasks exist now hands over to the admin task by itself.
- **Deck comes back after a crash or a graphics driver update.** If something ends Deck, the watchdog gives the fans back to the BIOS and then starts Deck again, hidden. It waits for a running driver installer to finish first. After three such ends in ten minutes it stops and Deck starts with the fans on the BIOS and no overclock until you turn hardware control on (a toast says why). The log now says how Deck ended (crash kind and the DLL, or "ended by another program").
- **A driver install no longer hits Deck's GPU calls.** While NVIDIA's (or AMD's, Intel's) driver setup runs, Deck makes no GPU calls, and restarts itself once afterwards so the new driver is used and the profile is applied again.
- **The controller's real name in the "Connected" message** (a GameSir dongle said "XInput Controller #1").
- **The overlay's CPU clocks now really match MSI Afterburner.** 2.5.10 measured the average clock each core ran at, which comes out a few % below Afterburner's on a boosting CPU (5.1 GHz against 5.29), and the thread lines still used Windows' estimate. Afterburner shows each core's current speed step times the bus clock; the overlay now reads the same (Intel), so the CPU clock, every thread line and the core table show the same figures as Afterburner. The CPU page keeps the measured average.
- **Claude Sync no longer calls the same version "older".** It compares build times, so another build of the same version (a test build) showed "runs an older Deck (2.5.10; this PC has 2.5.10)". It now says the other PC runs a different build of that version.
- **A core's load in the overlay's core table is its busiest thread's.** The average of a P-core's two threads showed a game's main thread at 100 % as 50 %, hiding a CPU-bound game.

### Changed
- **"Like MSI Afterburner" looks like MSI Afterburner:** its layout (clock, CPU, a line per thread, RAM, FPS, GPU, MEM, then the frametime graph), its default colours, a white framerate, small thread numbers (CPU₁) and a small "Frametime" above the graph with the frametime after it. The framerate figures (min, average, lows) are left off, as Afterburner shows them only while benchmarking; add them back in Items.
- New look options: **Small thread numbers** (Layout), **Afterburner layout** for the graph (Graph), and a colour of its own for the framerate number.

### Added
- **Death counter: the same game in every store.** A game is known by its program, so a Steam, GOG, Game Pass or EA copy is the same game, with the same history and death screens. Fullscreen browsers and video players are never counted as games (a video of someone dying doesn't count), one death seen by the screen and pressed on your key counts once, and "WASTED" no longer matches "WANTED".
- **Updates from GitHub.** Deck looks once a day for a newer release and installs it by itself when no game or fullscreen program is in front: no prompt, no window, and it is back in the tray a moment later. The download is checked against the release's SHA-256 first. Settings → About shows the state, "Check now", "Install" and a switch to turn it off. A Deck without admin tasks only tells you and installs on your click (one admin prompt). The first install of this version is manual; updates come on their own after that.
- **Controller overlay** (Monitor → Controller). Controller Overlay, the separate app, is now part of Deck: your controller's buttons, sticks and triggers on screen over your games, in the same DualShock 4 look, with every theme, style, layout, size, corner and monitor setting it had, idle fade, Move / resize by dragging, demo input and keyboard & mouse mode. The tray menu has it under **Controller overlay**. Your Controller Overlay settings are brought over the first time Deck starts; uninstall the old app whenever you like.
- **Controller battery for any controller.** One tray icon per controller that reports its battery, phone style, and the same level on the overlay's battery pill. Reads GameSir dongles directly, PlayStation controllers from what they already send (nothing is written to them), and Xbox and Bluetooth controllers through Windows. Like a phone, the level never jumps up after switching the controller off and on; a warning comes once per charge at 15%. The Battery tab lists every controller and where its level comes from.
- **Test tab:** the controller the overlay reads, live (buttons, sticks, triggers), with or without the overlay on.
- The overlay stays out of screenshots and recordings unless you turn that off.
- **Death counter** (Monitor → Deaths). Count your deaths in any game, per boss. Start a boss fight, and every death counts toward it until you mark it defeated or abandon it, including deaths on the way back. Stats per boss: deaths, attempts, wins, deaths before the first kill and time. Count from the tray menu (Death counter), two keyboard shortcuts you choose, a controller combo (hold Select + D-pad Down for a second; Select + Up undoes), or the page; every count can be undone, and the history can be edited. A small counter shows over the game ("Malenia · 14"), click-through and hidden from recordings unless you want it in them. Any game works; Deck recognises Steam and Epic games by name and knows 320 hard games. **Counts by itself:** Deck watches the game's window for death screens ("YOU DIED", "GAME OVER", "WASTED"… plus a game's own, for a first set of games) and runs Windows' built-in text recognition only when the picture settles; Celeste and Dark Souls: Prepare to Die Edition are counted from their save files. Nothing it sees is recorded or saved, and both can be turned off. **Teach it a death screen:** for a game whose death screen has no words (Sekiro's), count the death yourself, then click the clearest of the last 10 seconds' pictures on the Deaths page; Deck counts that screen by itself from then on (up to 3 per game, shareable with friends as a code). **Shared library:** submit what you taught to everyone (a button that copies the code and opens a GitHub form; it is added after review), and Deck picks up new death screens from Deck's public GitHub page at most once a day (a plain download, nothing about you is sent; turn it off in Deaths → Settings).
- **GPU memory controller load** ("FB usage" in Afterburner) as an overlay item (NVIDIA).

## 2.5.10 — 2026-10-19

### Fixed
- **CPU clocks now match MSI Afterburner and HWiNFO.** Deck showed Windows' estimate of each thread's clock, which runs a few % low and jumps around (4.8-5.2 GHz on P-cores and 3.2-3.9 GHz on E-cores where Afterburner showed a steady 5.29 and 3.99). Deck now reads each core's own cycle counters, as Afterburner does, on Intel and AMD; Windows' figure is only used without the driver.

## 2.5.9 — 2026-10-18

### Fixed
- **CPU clocks read about 20 % low under some power plans.** Deck measured against Windows' "current" CPU clock, which a power plan lowers, instead of the CPU's fixed base clock. In a game, cores at 2.69 GHz (HWiNFO) showed 2.15 GHz on the overlay, the CPU page and Sensors. Now checked against HWiNFO core by core.
- **The overlay's framerate could come from a different program than its lows and average**, for example a launcher drawing faster than the game. FPS, frametime, game RAM and the framerate figures now all follow the same game.
- **The framerate no longer stays frozen** on a game that stopped drawing (alt-tabbed, paused or closed).
- **A new game no longer starts with the previous game's frames** in its average and lows.
- **The preview's API and resolution are the game's own.** They used to say "D3D12" and the desktop's size for every game. With no game, the preview's graph is empty instead of a made-up line.
- **Long overlays are no longer cut off in the middle.** RivaTuner 7.3.5 and newer get the 32 KB text field; on older versions, whole lines are left off the end instead of breaking the colours of everything after the cut.
- **Hiding RivaTuner's tray icon no longer starts a process every 5 seconds**, also while gaming.
- **RivaTuner installed outside its default folder is found.**

### Changed
- **The frametime graph is MSI Afterburner's:** RivaTuner's own graph of every frame, which it redraws with each frame, so it moves as smoothly as the game. Deck used to send it about 12 points a second, which looked choppy. It uses your style, height, width and top.
- **The graph sits on a line of its own**, labelled FT and lined up with the other lines, with the live frametime in front unless the overlay already shows it.
- **The graph's top on Auto is four average frames** (33 ms at 120 FPS): a normal frame sits a quarter of the way up and stutter stands out. RivaTuner's own autoscale followed the slowest frame on screen, so one hitch flattened the rest. A fixed top shows the framerate it stands for ("16 ms · 63 FPS").
- **"Shows the last" and "Smooth the line" are gone:** RivaTuner keeps its own frame history.

## 2.5.8 — 2026-10-18

### Changed
- **The CPU page is reworked.**
  - **A live column stays in view** while you scroll or edit: clock with its last minute, temperature, load, power, the power limit in force and who set it (your motherboard or the active profile), and every core's clock and load.
  - **"Held at the power limit"** appears when the CPU draws all the watts it may under load, so a low motherboard limit is no longer invisible.
  - **Profiles are edited on the page**, not in a popup: an edit button on each card opens the settings under the profiles, with an "Unsaved" mark and Save / Discard.
  - **Plain settings first:** clock caps, Turbo boost on/off, energy preference, power limits and extras. Windows' processor states, parked cores and the five turbo modes are folded under Advanced.
  - **A slider's end means off:** all the way right is "No cap", all the way left is "Off" for the clock floor (was "Keep the clock at least") and the overclock.
  - **"Plan's own" energy preference shows the plan's real value** ("Plan's own · 33"), with a note when it leans to saving.
  - **"Stock" power limits are now "Motherboard"** and show the board's own watts. Custom PL1/PL2 go above 253 W when the board's own limits do.
  - **Warnings** for settings that cancel each other (a cap below the overclock, a clock floor above the cap). "Hold the cap in games" only shows when the profile caps.

### Fixed
- **A clock cap at the CPU's top turbo no longer caps.** A profile saved with its cap slider at the top (5,300 MHz on an i5-14600KF) still held the CPU at that clock and blocked any overclock. Such caps now count as no cap when saving and applying, once Deck has read the CPU's real top turbo.
- **E-core clocks read about a quarter too low** in the overlay, on Sensors and in the per-thread rows (2.97 GHz for an E-core really at 4.0 GHz on an i5-14600KF). Windows measures every core's performance against the CPU's base clock, and Deck multiplied the E-cores' by their own lower one.
### Testing
- **`install.ps1` no longer does nothing when Deck is running.** It printed a warning and stopped, so a developer install often left the old version in place. It now closes Deck itself, retries the copy until the installed Deck.exe matches the build (and says so in a window that stays open if it can't), and starts Deck again.

## 2.5.7 — 2026-10-18

> **When you update:** if you typed your own PC to PC pairing code or Claude Code sync key, it keeps working. A new one you type must now pass the "too easy to guess" check.

### Security
- **Programs can't borrow Deck's admin rights through winget.** Deck ran `winget` (PC to PC → Apps) by name, which finds a copy in a folder any of your programs can write to. It now runs winget only from App Installer's own protected folder.
- **Remote desktop setup can't be hijacked through PowerShell.** Deck's admin PowerShell steps could load commands from your Documents folder before Windows' own. They now load commands only from Windows' folder, and take no folder from the environment.
- **RustDesk's installer is checked where it can't be swapped.** It is copied into a protected folder, kept locked while it is checked and installed, and must carry GitHub's checksum and RustDesk's own signature (not just any valid one).
- **Hardware settings can't skip the "changed outside Deck" check.** A test switch (`DECK_PROFILE`) that your programs could set made Deck read hardware settings from a fresh folder it then trusted. An admin Deck now ignores it.
- **The 32-bit RivaTuner helper** starts only from Deck's own folder when Deck runs as admin.
- **Keys on disk are sealed with Windows (DPAPI).** This PC's PC to PC key, the pairing code, the phone key and the sync key no longer sit in plain text in AppData, so a copied profile or backup doesn't carry them. Older files are sealed the first time Deck starts.
- **Typed pairing codes and sync keys that are easy to guess are turned down** (repeats, runs like 1234 or ABCD, or few different characters). PC to PC and Claude Code sync serve at most 64 connections at once, and a stranger has 10 seconds to prove the code.
- **Exploit mitigations:** Deck and its helper are built with Control Flow Guard, and Deck with CET shadow-stack support.

### Fixed
- **CPU clocks in the overlay and on Sensors show the real clock.** The main CPU clock and every P-core / E-core row read a register that stays at the top turbo step (5.30 / 4.00 GHz on a 14600KF) while a core naps, so they never moved. They now come from the same live Windows reading as the thread rows: a core shows its busiest thread's clock.

### Testing
- The UI test suites wait up to 30 seconds for headless Edge to start (a slow CI runner timed out at 10), and the notification-window test always closes its Edge, even when it fails.

## 2.5.6 — 2026-10-18

> **When you update:** update every PC that uses PC to PC or Claude Code sync, since old and new versions can't talk to each other. Then re-pair your PCs once (trusted PCs and "always allow" are asked again; "never" choices are kept). If Deck was installed per user before, click **Set up** once more after the update. The phone page reloads itself once.

### Security
- **The phone can no longer run programs on the PC.** A phone could ask Deck to "open" any file path by pretending to answer a "File from your phone" notification. The phone now answers only its own kind of notification (media, power, timers, text), and the "Open" button on a received file works only for a file that really arrived from that phone and only from the PC itself. Accepting transfers and applying a held GPU overclock are PC-only decisions now.
- **An elevated Deck ignores WebView2 flags from the environment.** When Deck runs as admin it no longer reads `WEBVIEW2_*` variables (any program running as you can set them, and a debugging port there would expose every command Deck has). The live-testing debug port now comes from Deck's own command line (`--cdp-port`).
- **Programs can't borrow Deck's admin rights through your files.** When Deck works in your folders (phone uploads, files from another PC, Claude Code sync, share links, Clean up, the Recycle Bin, its own settings), it does only what your everyday account could do. A folder swapped for a link can't redirect it into Windows' own files.
- **Deck won't share, send or serve a file your everyday account can't open**, and won't zip a folder that contains links.
- **Hardware settings changed outside Deck wait for you.** If another program edits Deck's fan, CPU or GPU settings, Deck keeps the fans on the BIOS and applies no overclock until you click **Apply them** on the PC.
- **The phone key no longer travels over the network.** The phone signs every request instead, and a recorded request can't be sent again. The phone page also refuses requests a web page sends by pointing one of its own internet names at your PC (DNS rebinding).
- **Each PC has its own key for PC to PC.** Trust and "always allow" now belong to that one PC, not to anything that knows the pairing code. Pairing codes and the Claude Code sync key are also much slower to guess.
- **Installers from another PC always ask on this PC**, even from a trusted PC, and run through Windows' normal admin prompt, never with Deck's own rights.
- **Claude Code sync holds risky changes.** If another PC's sync would change what Claude Code runs or may do without asking (hooks, plugins, status line, permissions), you see "Claude Code settings from <PC> are waiting" with **Apply** or **Keep this PC's**.
- **Share links:**
  - A one-time link can't be downloaded twice at the same time.
  - Home-only links can't be reached from the internet.
  - Funnel turns itself off at start unless an internet link is open.
- **Deck checks RivaTuner's shared memory before using it**, so a program pretending to be RivaTuner can't make Deck read or write outside it.
- **GPU and power libraries load only from Windows' own folder** (or NVIDIA's), never from a folder you or a program could write to.
- **"Open as your normal account" never falls back to admin.** If Explorer can't take a launch, Deck says so instead of starting the program with admin rights.
- **TLS library updated** (rustls 0.23.46) for four advisories published on 2026-10-14 (RUSTSEC-2026-0346 to 0349).
- **The RustDesk password no longer appears on PowerShell's command line.**

### Changed
- **Tools is one page.** Screen tools, Locked files and Windows panels are no longer separate tabs, and the page has a fresh look.
- **The setup installs for all users, in `C:\Program Files\Deck`.** It asks for admin once, and quietly removes an older per-user copy while keeping your settings.
- **Set up refuses an unsafe install.** If Deck sits in a folder your everyday account can change, Set up explains why it won't give it admin rights. Admin tasks that already point at such a copy are removed at start, with the notice "Deck's admin start was turned off".
- **PC to PC → Settings:** the switch for installing without asking from trusted PCs is gone, since installers always ask now.

### New
- **CPU profiles for plugged in and on battery** (CPU page, on PCs with a battery). Pick a profile for each; Deck switches when you plug in or unplug, and a profile you choose yourself stays until the next change. **Profiles also apply on battery** (on by default) makes a profile cap the CPU the same way on battery; turn it off to keep Windows' own battery values in each plan.
- **Fan watchdog.** If Deck is ended from Task Manager, the fans go back to the BIOS and the GPU fan back to the driver within seconds. While hardware control is on, a second small `deck.exe` in Task Manager is the watchdog.
- **Deck keeps a log** in `%LOCALAPPDATA%\Deck\logs`, and the This PC support report includes its last lines.
- **A "Shut down when…" plan survives a Deck restart.** It starts waiting again from the beginning.

### Fixed
- **Building from source** works with Rust 1.99 (its new clippy check failed the build in CI), and the tests pass when run as admin.
- **Overlay "Threads" table showed fake clocks.** Every thread read its base clock (for example 3500 MHz on P-cores and 2600 MHz on E-cores) whatever it was really doing, so a CPU cap looked like it did nothing. It now shows each thread's live clock, the way Task Manager measures it, with or without admin rights.
- **Overlay "Game RAM" measured the wrong program** when another window was in front (a screenshot tool, Discord). It now measures the game RivaTuner is drawing in, and shows nothing if the game's anti-cheat hides it.
- **The CPU clock without admin rights** read too high when an E-core was the busiest core.
- **Bigger click targets** on the Disk space tree arrows, the Home tile settings button and the overlay tick boxes; screen readers now name both "send text" boxes.
- **Settings survive a bad shutdown.** If `settings.json` is damaged (for example by a hard reset mid-save), Deck keeps the damaged file, restores the last good copy, and otherwise keeps every setting it can still read instead of silently resetting everything. Each save now keeps a backup of the previous version and is written so a crash leaves a whole file, never a half-written one.
- **The GPU/CPU crash guard fails safe.** If its record file is damaged, Deck now holds a risky overclock back at boot instead of re-applying it — the exact situation the guard is meant for.
- **Pairing codes and the phone key** are generated without the slight bias the old method had, and Deck now stops with a clear error if the system's random number generator fails rather than making a guessable token.
- **Themes:** button and chip borders on hover, switches, sliders, progress bars, scrollbars, the calendar, toasts and app placeholders kept the default theme's blue-grey in every theme. They now take each theme's own colours.
- **The overlay key could fail to switch RivaTuner** on a PC without Microsoft's Visual C++ runtime: Deck's small 32-bit RivaTuner helper needed it. The helper now carries its own copy, like Deck.
- **Clipboard page slow with a huge item.** A copied log of 200,000+ characters went onto the page in full and made the page take about 0.2 s to open. Cards now show the start of an item, and the preview the first 20,000 characters (with a note); Copy and Paste still use all of it.
- **Sidebar badges** (a running timer, Keep awake on, a plan set, a phone connected, a PC waiting) were squeezed out next to long page names. They now sit on the page's icon: a number for a count, a dot for on or set (hover it for the word).
- **More files survive a bad shutdown.** Your clipboard history, the list of items received from a phone or another PC, and the Game boost restore-state are now written the same crash-safe way as settings, so a hard reset mid-save can't truncate them.

## 2.5.5 — 2026-10-16

### Changed
- **Overlay page, redesigned.** It was one long column of seven sections (about four screens of scrolling).
  - **Top strip:** the overlay switch and RivaTuner's state, with the keys you use in game: show or hide, and the frame limit (limit, on/off and its key).
  - **Preview:** bigger, and it stays in view while you edit, with the quick looks under it.
  - **Settings:** seven short tabs: Items, Layout, Look, Colours, Graph, Warnings, Behaviour. Deck remembers the last tab you used.
  - **Denser lists:** the item list is compact, with move and remove buttons showing on hover. "Add readings" opens when you want it.

### Fixed
- **Docs:** the README describes the new Overlay page and the framerate limiter, and has a new Overlay screenshot. It also says the CPU readings need admin.
- **Home → PC tile on a PC where Deck isn't running as admin:** the CPU card showed only "20 threads", with no clock, power or temperature, and gave no reason. Those readings need admin, so the card now says *Needs admin* and sets it up when clicked. The tile's customize dialog says the same.
- **Open RivaTuner did nothing** (the mouse showed a busy cursor for a moment) when RivaTuner's own *Start minimized* option is on: it restarted straight into the tray, whose icon Deck may hide. Deck now turns that option off for this one start and puts it back once the window is open.
- **Framerate limit key only turned the limiter on:** when Deck couldn't read RivaTuner's switch it took it as "off", so every press meant "turn on". Deck now reads the switch from RivaTuner's 64-bit hooks (and remembers what it set last), so the key turns it off again.
- **Framerate limit didn't reach a running RivaTuner:** Deck wrote the limit into RivaTuner's profile file, which RivaTuner only reads when it starts (its window still showed 0). Deck now also sets it through RivaTuner's own profile interface, so RivaTuner and running games use it at once.
- **Shortcut keys on a laptop's built-in numpad:** Fn + 9 (Page Up) was saved as "Num9", which never fires because Windows gets Page Up. The recorder now saves the key the numpad key actually sends (Page Up, Home, End, arrows…). Fn itself never reaches Windows, so there's nothing to "allow": press Fn + the key and the recorder now saves the right one.
- **Phone page settings looked unchangeable:** a click on a Screen view option (picture size, smoothness, bitrate…) was saved, but the page kept showing the old choice until something else redrew it. The page now redraws right away.
- **Fold-out sections closed by themselves** whenever a page redrew (for example the Phone page when a phone connected). Open sections now stay open.
- A setting that **failed to save** no longer shows as if it had been changed.
- **Bitrate → Type…:** pressing Cancel (or typing something that isn't a number) set the bitrate to Auto; it now keeps the bitrate. Empty still means Auto.
- **Phone limits:** two phones connecting at the same moment could both get the last place; a phone that was turned away could still send and download files. Both closed.
- **Screen view:** tap then drag on a window's title bar or a file could act as a double-click (maximize, open) on the PC; a long press during tap-then-drag right-clicked instead of dragging.
- **Shortcuts in full-screen games:** quick taps are seen more reliably, and a shortcut held while a game came to the front no longer runs again.

## 2.5.4 — 2026-10-16

### New
- **Who can connect** (Phone page): how many phones may connect at home and how many away (no limit, 1, 2, 3 or 5 each), and two switches: a phone at home shuts out phones away, or a phone away shuts out phones at home. A phone that is turned away sees why and tries again every 10 seconds.

### Fixed
- **Overlay key and other Deck shortcuts didn't work in League of Legends** (and other games that switch off Windows shortcuts while they are in front). While a full-screen game is in front, Deck now also watches its shortcut keys itself and runs one Windows didn't deliver (the rest of the time it only checks once a second whether a game came to the front). Still no keyboard hooks.
- **Phones connected** counted connections, not phones (the remote, its Screen view and its sound each added one), and didn't say where they were. It now counts each phone once and shows how many are at home and how many away.
- **Screen view on the phone:** sliding a finger held the left mouse button down (dragging or selecting on the PC). Sliding now just moves the pointer, like a laptop touchpad; tap, then touch again and slide, to drag.

## 2.5.3 — 2026-10-15

### Fixed
- **Lighting controls did nothing** (every effect, on or off, and the lights test too) while Deck said "Motherboard RGB connected". The board's lighting controller had lost the configuration Deck writes when it connects, and then ignores every colour sent to it without any error. Deck now checks every 5 seconds that the board still holds its configuration and writes it again when it doesn't.
- A **lights test** that never finished (the controller stopped answering) kept all lighting frozen and refused a new test until Deck restarted. The hold is now always released: the test gives up after 40 seconds, and a hold older than a minute is cleared by the lighting loop.

## 2.5.2 — 2026-10-15

### Fixed
- **Setup and uninstaller still said "Failed to kill Deck"** when Deck had no `\Deck\Quit` task yet (2.5.1 only adds it once it has started with admin rights). The setup / uninstaller now first uses that task and, if it isn't there, closes Deck by running `deck.exe --quit` as admin (one Windows prompt). Note: an uninstaller belongs to the version that is installed, so a Deck older than 2.5.1 still needs to be closed from the tray once; installing 2.5.2 over it replaces that uninstaller.

## 2.5.1 — 2026-10-15

### Fixed
- **Setup and uninstaller could not close Deck** ("Failed to kill Deck. Please close it first"): Deck runs with admin rights, the setup does not, so Windows refused to end it. They now close Deck through a new admin task (`\Deck\Quit`), which also hands the fans back to the BIOS. Deck adds the task itself the next time it starts with admin rights.

## 2.5.0 — 2026-10-15

### New
- **PC to PC** (bottom of the sidebar, above Phone; on by default): send files, folders, installers, apps and your Windows setup between your PCs, with Deck on both and the same pairing code. They find each other on the home network by themselves (or by address), and everything is encrypted with the pairing code.
  - **Send**: files and installers (optionally **installed on arrival**: silently when the installer allows it; the other PC asks first unless it trusts this one), whole folders (shows what goes first; skips build output such as `target` or `node_modules`; can send only new or changed files, and delete on the other PC what's gone here, after its user agrees), or a piece of text.
  - **Browse** the other PC's shared folders and copy from them; nothing is shared until you add a folder, and each PC is asked, always allowed or never allowed.
  - **Apps**: pick apps installed here; the other PC installs them itself with winget, skipping the ones it has (retries network errors; "Retry failed").
  - **Setup**: sends this PC's look (dark mode, accent, taskbar and Explorer options), wallpaper and Windhawk mods; the other PC picks what to apply, backs up first and can undo.
  - **Received**: install, install silently, extract, apply a setup, show or delete the files. Offers and requests waiting for an answer show as notifications with Accept / Decline.
  - Transfers resume after a dropped connection; progress, speed and time left show live.
  - **Everything asks first** (Accept / Decline, also as a notification), unless you trust the sending PC: **for a week, a month, 6 months or always**, from the prompt or Settings → Trusted PCs. Deleting files on your PC is always asked.
  - **Away from home**: your other PCs on Tailscale (the same private network the phone remote uses) are found by themselves; no cloud folder needed.
  - **Command line** for scripts and Claude Code: `deck.exe --pc-list`, `--pc-send <path> [--to PC] [--all] [--sync] [--install]`, `--pc-get <path> --from PC`; prints progress and a clear result (exit code 0 = done). **Let Claude Code use PC to PC** (Settings) installs a short Claude Code skill so Claude can send files or a whole project, dependencies included, when asked.
  - A single file arrives in a folder named without its extension.
  - **Phone transfers continue after a dropped connection**: the phone sends in 8 MB pieces the PC keeps, retries by itself and goes on from what the PC already has (picking the same file again later continues too), with speed and time left. Downloads to the phone and share-link downloads can be continued by the browser (byte ranges). The command line shows time left.
  - **Share link**: a file or folder for someone who isn't one of your PCs. They open a link in any browser (no Deck needed) and download; the link works once or until it ends (1 hour, 1 day or 7 days), on this Wi-Fi, or over the internet through Tailscale Funnel (only the shared file is published, and only while a link is open). A folder is zipped first; a download that breaks off doesn't use the link up; you get a notification when it's downloaded, and can stop a link any time.
- **Claude Code sync** (under Desktop, hidden until shown in Settings → Sidebar or switched on; off by default): for Claude Code on more than one PC. Keeps its conversations, memory and settings the same on your PCs (directly on the network, or through a cloud-synced folder), rewriting project paths so /resume works on each PC.
  - Encrypted with a sync key only your PCs know; sign-in details and per-PC files are never synced.
  - **Session lock**: a conversation open on one PC can't be continued on another by mistake (Claude Code is stopped with an explanation; **Take over** overrides it). **Tell Claude** which PC it runs on.
  - **Sessions** (search, where each one lives, delete here or on all PCs), **Projects** (each project's folder on this PC; move, stop syncing, delete everywhere), **Status** and **Log**.
  - It adds two small hooks to Claude Code's settings while on, and takes them out when switched off or when Deck is uninstalled. Settings from the standalone ClaudeSync app are taken over the first time; it won't start while that app runs.
- **Screen on your phone** (Phone page, off by default): see the PC's screen live in the phone remote, at home or away (Tailscale), and with **View and control** use it too.
  - **Control starts off** on the phone every time, so watching can't click anything by accident; the Control button turns it on.
  - Tap to click, hold for right-click, drag to drag, two fingers to scroll; pinch to zoom in on small text.
  - **Full screen**: hides the bars until you leave it, with small buttons on the edge for control, the keyboard and leaving.
  - **Sound** (off until you turn it on on the phone): the PC's sound plays on the phone, as one continuous stream (no clicks between pieces; the PC's and phone's clocks are evened out without skipping), with a small delay that adapts to the connection and to how the phone plays sound (from 120 ms; after a dropout it grows by as long as the sound was missing, up to 1 s while just watching, since the picture waits for the sound, and 0.3 s while controlling the PC; it shrinks again after half a minute without one; sound that falls behind catches up by leaving out silent moments; dropouts are counted in the status line). The PC also stops sending pictures while earlier ones are still queued on the line, so a bitrate above what the connection carries can't hold up the sound or your taps. **Best** (uncompressed, ~1.5 Mb/s), **Good** (~400 kb/s), **Medium** (24 kHz stereo, ~200 kb/s) or **Low** (16 kHz mono, ~70 kb/s); **Auto** picks one from the connection.
  - **Lip sync**: while only watching, each picture waits for the moment its sound plays on the phone. With Control on the picture stays instant instead.
  - **Bitrate**: **Auto** (measures the connection and follows it, from a slow DSL line up to full quality at home), a fixed limit from 30 Mb/s down to 0.5 Mb/s, or one typed in. When it's tight: **Smooth** keeps the chosen frame rate, even on a 1 Mb/s line (the picture gets smaller and blurrier: 30 fps at 1 Mb/s is about 320 px); **Sharp** keeps text readable: the screen's own resolution at good quality, with fewer pictures (about 5 a second at 8 Mb/s, 10 from 15 Mb/s, 2 on a slow line).
  - **H.264 video** (Video: H.264, the default; JPEG stays as a fallback): the same 30 fps picture takes a fraction of the data, so a 1 Mb/s DSL line shows 30 fps at about 640 px (60 fps at 480 px, text still readable at Smooth). Uses the graphics card's encoder (NVIDIA, AMD, Intel) and the Windows software one if there is none; if an encoder fails Deck moves to the next, then to JPEG, and tells the phone. The phone decodes with WebCodecs when its browser allows it (secure pages), and otherwise with its own decoder in the page (WebAssembly: any browser, plain home address included), drawing each picture as it arrives like JPEG, so nothing stalls, jumps or replays old pictures; a phone that decodes too slowly is sent narrower pictures. Browsers without WebAssembly use the browser's video player. Key pictures (several times a normal one) come only when needed. Smooth keeps the frame rate and shrinks the picture; Sharp keeps the picture and lowers the frame rate (not under 8).
  - **15, 24, 30 or 60 fps**. Pictures only go out when the screen changes, so 60 shows in games, scrolling and 60 fps video.
  - At home it uses the home network even when the phone opened the Tailscale code.
  - Type with the phone's keyboard, plus a bar of keys and shortcuts (Esc, Win, arrows, Copy, Paste, Alt+Tab, Task Manager…).
  - Every monitor can be picked; picture size **Full** (the screen's own resolution, the default), **Medium** or **Small**. Full keeps colour detail at high quality, so small text stays readable.
  - Pictures are captured on one thread and compressed on two others, so the frame rate follows the screen (the status line shows both: "49 fps (screen 59)").
  - Light on the PC and the connection: nothing is sent while the screen doesn't change, and a picture only goes out once the phone has shown the last one.
  - Control pauses while a game is in front (watching still works): Deck never sends input into games, because anti-cheat systems watch for that.
  - The PC shows a notice while a phone is watching, and the Phone page shows how many are. Windows hides the lock screen and admin prompts from every app, so the phone says so instead.
- **See and control this PC** (Phone page): remote desktop through RustDesk (free, open source), from your phone or another computer.
  - Deck installs RustDesk for you. The download is checked against GitHub's fingerprint and RustDesk's signature.
  - It shows the addresses to type in: **At home** (your home network) and **Away from home** (Tailscale), plus the RustDesk ID.
  - Switches for **Allow remote desktop** (off stops RustDesk completely, also after a restart), **Connect by address** (straight to this PC, not through RustDesk's servers) and **Hide tray icons** (RustDesk and Tailscale keep working; their state shows in Deck instead).
  - Set the password from Deck, with short steps for the phone.
- **The phone remote works away from home** through Tailscale, a free private network between your own devices; nothing is opened to the internet.
  - The Phone page's code has **At home** and **Away (Tailscale)** tabs.
  - Until a phone is on your Tailscale, the Away tab shows how to put it there. Its code opens a "Get Tailscale" page: the App Store on iPhones; on Android the Play Store and a direct download from Tailscale's own site, for countries where the Play Store doesn't offer it. It also shows the account to sign in with.
  - Once the phone is on it, its name shows under the code, connected or offline.
- **Hide RivaTuner's tray icon** (Overlay → Behaviour): RivaTuner keeps running with no icon in the taskbar corner, not even under the arrow, and Deck keeps it gone when RivaTuner or Explorer restarts. Turn the switch off and the icon comes back straight away. **Open RivaTuner** next to it opens RivaTuner's own settings. It restarts RivaTuner to do that, so a game's overlay blinks for a moment.

### Fixed
- **Framerate limit key** (Overlay → Behaviour): turns RivaTuner's framerate limiter on and off in games, like Afterburner's limiter key did, with the limit right next to it and a switch. Afterburner's limiter key is taken over by the Afterburner import.
- **Overlay closer to Afterburner**: the framerate and frametime (filled in by RivaTuner) line up in the same column as the other numbers; RivaTuner's own statistics line ("0:27:42 (5 cur, …)") is switched off, as Deck shows those figures itself; the "Like MSI Afterburner" look has a slim graph.
- **Overlay: numbers no longer touch their units** (°C, %, MHz): small units get a small gap of their own size, in the game and the preview.
- **Overlay preview colours now match the game**: a number's prefix and its unit are in the label colour (they took the part's colour in the preview), small units are drawn at RivaTuner's size and raised like in the game, the frametime graph takes the label colour (or the framerate colour with part colours), and a colour that isn't valid falls back to the default as it does in the game.
- Phone remote: the skip buttons next to pause jump 10 s back and forward when the player has no previous/next track (a video in a browser), and quick taps add up; the home page shows CPU and GPU power in watts, and the CPU's package temperature instead of its usage.
- Phone Screen view: the bar keeps the actions (close, full screen, control, sound, keyboard, keys); bitrate, frame rate, slow-connection choice, picture size, video and sound quality are in one Settings panel, each with a line saying what it does.
- Phone Screen view, Auto bitrate: measures the connection first (a short burst the phone answers piece by piece; under a second on a 1 Mb/s line) and uses 80 % of it, leaving 20 % free; on a slow line (under 3 Mb/s) it never climbs past that, so it no longer overshoots and lags while finding the limit. Measured again every 5 minutes; the status line shows the measured line. A set bitrate is the most H.264 uses; it still backs off when the line is busy. The phone's sound takes its share out of the picture's.
- Phone remote away from home was slow (buttons lagged, sent text didn't arrive): every update carried the playing track's artwork, ~170 KB every 1.5 s, more than a 1 Mb/s home upload. The phone now fetches the artwork once a track; updates are ~2 KB.
- Phone sound no longer counts a dropout at every pause in the PC's sound (the first 1.5 s of silence is now sent as silence), and its smallest delay is 80 ms.
- **The phone couldn't connect: scanning the code loaded forever.** Windows Firewall blocked it. When Deck starts with admin rights at logon, Windows never shows its "Allow access" question, so nothing allowed the phone in. Deck now adds its own firewall rule (home and work networks only, not public ones).
- **File pickers opened behind Deck** ("Send a file", Browse buttons) while Deck was on top. They now open in front of it.
- **Deck opened while taking a screenshot** with Win+Shift+S, Snipping Tool or tools like ShareX, Lightshot and Greenshot, when the box started or ended in the hot corner. The corner now ignores screenshot tools, and after a click or drag in the corner it waits until the pointer leaves.

## 2.0.0 — 2026-10-14

The big update. It installs over Deck 1.x and keeps all your settings, profiles and layouts.

### New
- **Make Deck yours**: on first start (and once after this update) Deck asks for your theme, accent colour, opacity, opening animation and low-spec mode. All of it can be changed later in Settings → General.
- **8 themes** (Settings → General → Colour): Midnight (the default), Graphite, OLED black, Pure black, Nord, Forest, Plum and Ember. Your accent colour stays the same.
- **Opacity**: how see-through Deck is, set separately for pinned and not pinned (30–100 %).
- **Opening animations**: Zoom (the default), Fade, Pop, Rise, Drop, Flip, Swirl, Blur in, or None, with a Preview button.
- **Low-spec mode** (Settings → General → Performance, off by default): for older or slower PCs. No animations or soft shadows, and live readings and graphs update every 3 seconds instead of every second. Everything still works.
- **The pin works in both modes.**
  - Quick panel: Deck becomes a small floating window on top of everything, with nothing dimmed around it, so you can use other apps while it stays open.
  - App window: Deck stays on top of other windows.
- **Home, arranged your way**:
  - Drag any tile anywhere, including under each other.
  - Resize tiles both wider and taller from the corner.
  - A guide line shows where a tile will snap to line up with its neighbours.
  - Tiles never overlap: the ones in the way move down.
  - When a tile is made small, its less important parts fold away neatly instead of overflowing.
- **New default Home layout** for new installs and for anyone who never arranged Home.
- **PC tile cards** (Home): CPU, Memory, GPU and VRAM cards, all in the same style: usage, then clock and power (for example "5.3 GHz · 33 W"), then temperature, and a graph. Their rows line up across cards. The new button in the tile's corner turns cards on or off, reorders them, adds a Network card, and hides the drives list.
- **Drives** (Monitor → Drives): the health of every HDD and SSD (S.M.A.R.T.).
  - Shows health, temperature, power-on hours, data written, wear and the warning signs (reallocated, pending and uncorrectable sectors, media errors).
  - It remembers past readings, so a problem that came and went still shows.
  - Optional notifications when a drive's health gets worse (off by default).
- **Disk space, much faster**:
  - On NTFS drives Deck reads the drive's file table directly (the way WizTree does), so a full drive scans in seconds.
  - The treemap is laid out like WizTree's, with **File types** and **Folders** views and a back button.
  - The drive picker switches drives instantly.
- **Overlay has its own page** (Monitor → Overlay).
  - It can install RivaTuner for you.
  - The overlay key now also flips RivaTuner's own "Show on-screen display" switch, so the overlay turns on and off reliably.
- **Sidebar categories can be reordered**: drag a group or a page to move it. Settings → General has a Reset to put the sidebar back. Every group starts folded on a new install, for a short menu.
- **Support report** (This PC) now includes:
  - drive health and past drive problems;
  - the PC's maker, model and type (laptop, desktop…);
  - a quick lights test.

### Changed
- **Power & time** is now the last sidebar group, after Maintenance.
- **Sensors** opens on All readings.
- **Game boost**:
  - "Free memory" now only works when memory is actually short (85 % or more in use). With room to spare it does nothing, since trimming would only make background apps slow to come back.
  - "Turn off by itself" also ends Full power after 3 hours if no game ever showed up.
  - Deck now also spots games it doesn't know, when the program in front keeps the graphics card busy.
  - Picking a CPU profile under "Switch profiles while it's on" turns off "Fastest power plan", because the CPU profile brings its own power plan. The page now says so, instead of the switch just going off.
- **Overlay settings fit narrow windows**: button groups, sliders and the font list move under their label instead of spilling past the card.
- The default sidebar is narrower (180 px).

### Fixed
- **Network speeds were wrong (often double).** Windows lists some adapters twice: packet-capture tools such as Npcap and Wireshark add a filter layer that repeats the same traffic. Deck now counts only real network adapters, each once, using Windows' own counters. With Ethernet and Wi-Fi both connected their traffic adds up. An adapter you plug in starts counting from its next reading, with no false spike. One you remove simply stops counting.
- **RAM lighting ignored Deck after a cold boot**, for example staying lit when lights were set to off. Right after Windows starts, the memory's RGB controllers can be too slow to answer, and Deck never looked for them again. Deck now keeps looking for 10 minutes after startup or wake, and never disturbs sticks it already found.
- **Resizing a Home tile sometimes jumped back** and had to be done twice. A settings refresh in the middle of a drag overwrote the new size.
- **A resized tile went back to full size** after you let go.
- Tiles flickered while dragging.
- Numbers overlapped labels in small tiles.
- Long app names, like "Microsoft Edge WebView2", pushed the volume number out of the Sound tile.
- **The pin did nothing**: its button crashed when clicked.
- The overlay key (Page Up) didn't toggle RivaTuner's on-screen display.
- Deck no longer forces an extra full-window repaint every time it opens, unless the window actually comes up blank.

## 1.1.2 — 2026-10-14

### Changed
- **Sidebar regrouped** so each group has one job: **Hardware** (CPU, GPU, Fans, Lighting, Cooler display), **Monitor** (Sensors, Processes, Network, This PC), **Desktop** (Windows, Display, Clipboard, Sound), **Power & time** (Keep awake, Timers & breaks, Shut down when…) and **Maintenance** (Disk space, Clean up, Startup apps, Tools). The pages themselves are unchanged. Folded groups open again once, since the group names changed.

## 1.1.1 — 2026-10-13

### Fixed
- **RAM and motherboard lighting stopped following Deck after sleep.** RAM RGB sticks lose power in sleep and go back to their own built-in effect, and Deck never took them over again. Deck now re-detects the RAM and reconnects the board lighting a few seconds after the PC wakes from sleep or hibernate.

## 1.1.0 — 2026-10-13

### New
- **Units** (Settings → General → Units): clock speeds in MHz or GHz, network speed in Mb/s (bits) or MB/s (bytes), temperatures in °C or °F. They apply to every page, the sensor table, the phone and the in-game overlay. Numbers you type in yourself (GPU offsets, curve editors, fan curves, temperature limits) stay in MHz and °C.
- **Comet colours** (Lighting → Comet): your own colour, **Cycle** (the comet runs through the colours) or **Rainbow** (a rainbow tail that turns as it flies).

### Faster
- **Hidden windows no longer draw frames.** The page heartbeat used a frame loop that kept the hidden window rendering at the monitor's refresh rate (up to 300 times a second) the whole time Deck sat in the tray. It now checks one frame every 4 seconds. Idle CPU use drops from about 15–20 % of one core to a few percent.
- **Screen and Game lighting** read the screen with DXGI desktop duplication: about 0.3 ms per sample instead of about 23 ms with GDI (20 samples a second while a game runs), and nothing at all while the screen doesn't change. GDI stays as the fallback.

### Fixed
- A long profile name next to CPU or GPU in the sidebar squeezed the page name to "G…" and wrapped onto two lines. The name now shrinks with "…" (hover shows it in full).
- The in-game overlay showed network speed in MB/s while the app showed Mb/s; both now follow the Units setting.

## 1.0.0 — 2026-10-13

The first public release.

### New
- **Power graph** on Sensors → Graphs: CPU package and GPU board power over the last 5 minutes.
- **Frametimes panel**: the last 600 frames, with Now, Average, 1% low, 0.1% low, Lowest and Highest.
- **Customize** on Home and Sensors → Graphs: drag panels to move them, drag the corner to resize, hide panels and bring them back, or put everything back. Drag the sidebar's edge to change its width.
- **Overlay item picking and grouping**: tick several items (Shift-click picks a range), move them together, put them on one line under your own label, or remove them at once.
- **In-game frametime graph** drawn by Deck: 120 points over 5 s to 1 minute (default 10 s), smoothed or showing every hitch, and as wide as the overlay text (or a width you set).
- **Reset key** for the framerate figures, plus Reset buttons on the Frametimes panel and the overlay settings. Handy at the start of a match or a benchmark run.
- **"?" tips** on Fans, Lighting, Cooler display, Sensors, the overlay settings, Game boost and Settings (about 90 in total).

### Fixed
- Average FPS, 1% / 0.1% lows, lowest and highest never worked. They are now read straight from RivaTuner's per-game frametime history and follow the game you are playing.
- A pause (minimising, a loading screen) no longer drags the figures down.
- The overlay now shows within a few milliseconds of switching it on, instead of 1–3 seconds.
- Missing values showed as "?" in the overlay; they now show "-".
- Game RAM sits on the RAM line in the overlay.

## 0.2.0 — 2026-10-12

### New
- **Hardware control**, replacing MSI Afterburner and the motherboard fan tool:
  - CPU profiles (power plans plus clock caps, power limits, a minimum-clock lock with heat guard, turbo-ratio overclock).
  - NVIDIA GPU profiles (power and temperature limits, clock offsets or a voltage/frequency curve, voltage, fan), with Afterburner import and a crash guard.
  - Fans (curves, fixed speeds, presets, always released to the BIOS on quit), Mystic Light and Kingston Fury RGB, USB LCD coolers, sensors with graphs, alerts and CSV logging.
  - Switching from profile cards, the tray, hotkeys, desktop shortcuts, the phone and Game boost.
- **In-game overlay** through RivaTuner: 47 readings, layouts, colours, quick looks including "Like MSI Afterburner", and a live preview.
- **Keep awake** and **Shut down when…** redesigned, with live readings and a 60-second cancel warning. Plans survive a restart.
- **Network** page on one screen: live rates, speed test, ping with Start / Stop, game-server ping.
- **Windows** and **Tools** pages with tabs (open windows, snap zones, workspaces; screen tools, locked files, Windows panels).
- "?" tips on every CPU and GPU setting; a real font list for the overlay.

### Fixed
- Clicks lost when a page refreshed under the mouse; keyboard focus kept across refreshes; accessible names and focus rings everywhere.
- Search: Enter ran the previous result; typo tolerance; kill / close now ask first.
- Calculator: `200 + 10%` = 220.
- Clean up never pre-ticks the Recycle Bin; Disk space locks Windows' own folders.
- Processes that Windows marks critical can never be ended.
- Only a playback device can be made default, never a microphone.

### Removed
- The Apps, Games and Notes pages (apps and games are still in search and on Home). Saved notes are kept in the settings file.

## 0.1.1 — 2026-10-07

### Fixed
- Protection against blank white or black windows from WebView2: browser flags on every window, a repaint nudge after showing, and a watchdog that recovers a window that stops painting.

## 0.1.0 — 2026-09-28

- First version: tray app with hot corner, launcher and search, Home dashboard, clipboard history, sound mixer, timers, keep awake, shut down when…, windows and snap zones, display, processes, startup apps, network, disk space, clean up, screen tools, phone remote, and **Game boost**.

