# Changelog

All notable changes to Deck. Setups for each version are on the [Releases](https://github.com/MohammadFakih02/deck-releases/releases) page.

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
