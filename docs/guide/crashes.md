Where to find it: Diagnostics › Crashes

# Crashes

Windows' crash records of the last 30 days, the profiles that were on during crashes, and Deck's own health.

The page has three tabs: **Timeline**, **Profiles** and **Deck health**. Deck reopens the tab you used last.

When a new unexpected shutdown, bugcheck, crash dump or hardware error is recorded, **Diagnostics** in the sidebar shows **N new** and Crashes gets a dot. Opening the page clears both. App crashes and display resets don't set them.

## Timeline

The **Last 30 days** list shows Windows' records grouped by day, newest first, including times when no game ran. The menu above it filters by kind (**Hardware errors**, **Unexpected shutdowns**, **Bugchecks**, **App crashes**, **Display resets**, **Crash dumps**), each with its count. A row that fell inside a [session report](gaming.md#session-reports-in-diagnostics) says **During** and the game.

Select a row to see everything Windows saved about it: **When**, **Source**, **Status**, **Stop code** and its usual meaning, **Parameters**, **Exception code** and **Top module**.

- These records do not prove a cause. An unexpected shutdown is logged at the next start, so its time can be later than the shutdown. One without a dump looks like a power loss or hard reset.
- **Community meaning** labels some hardware error IDs (17: corrected PCIe error; 47: corrected error, often memory). They do not name a broken part.
- **Top module** in a dump is a hint, not proof. Missing fields say **Not available**; a dump Deck can't read stays in the list with its status.
- The **Sources** card lists each log and folder Deck read and when. A source that needs administrator says so. An empty list from readable sources does not mean the PC is clear.

Deck reads when you open the page and at most once a day in the background. It pauses while a game runs; press **Refresh** after playing.

- **Copy report** copies times, event IDs, codes and source states. It masks addresses and your PC name and leaves out file, module and device names. Nothing is uploaded.
- **Reliability history** opens Windows' own crash timeline.

## Profiles

- **Record Windows crash reports** (off by default) notes which CPU and GPU profiles were on when Windows logs a crash or driver reset. Hard resets with a profile on are counted even when it is off.
- **By profile** counts each profile's crashes in the last 7 days (amber from two). The profile also shows a chip such as "Crashed twice this week" on the [CPU](cpu.md) and [GPU](gpu.md) pages.
- **Crash history** lists each crash with its kind, time, game (or **Desktop**) and profiles. **Show N more** lists the rest.

A profile named in a crash is a clue, not proof.

## Deck health

One row each for unexpected closes of Deck in the last 7 days, background tasks that restarted or stopped, log errors and the update state. **Last errors** lists the newest log errors. Nothing here is sent anywhere. To share details, use **Copy report** on [This PC](this-pc.md).
