Where to find it: Clean up › Clean up

# Clean up

Removes safe junk that Windows and your apps rebuild: temporary files, caches, crash dumps, shader caches and old installers.

You see each category's size first, select what you want, review it, and only then does Deck delete. Deck never touches your documents, pictures, saved games, or browser passwords, bookmarks, history or logins. Once measured, the **Clean up** entry in the sidebar shows how much could be cleaned.

## How it works

1. Deck measures every category when you open the page. A ring counts them ("3/9 measured"). **Stop measuring** ends early; **Scan again** measures again.
2. Select categories. **Selected to clean** adds up what you selected. Select a tile to see **Largest items** on the right: up to 50 of the files and folders it would delete, largest first, with size and age (hover a name for its full path). Listing deletes nothing.
3. Press **Review clean up**. The window lists each selected category with its size, says what happens (caches are deleted, old installers go to the Recycle Bin, an emptied Recycle Bin is gone for good) and names what will be kept.
4. Press **Remove files**, or **Back** to change your mind. **Stop** halts a clean in progress; the rest stays untouched.
5. A notification says what was freed, and the page shows **Last clean freed**. The part that went to the Recycle Bin is counted separately until the bin is emptied.

Files in use are skipped. A tile shows a chip such as "Chrome open" when its app is open; close it for a full clean. Teams, Epic Games Launcher and Battle.net are skipped entirely until closed.

Selected at first: **Temporary files**, **Crash dumps and error reports**, the browser caches, **Discord cache** and **Explorer thumbnails**.

## The categories

Categories are grouped, biggest first, and appear only when their folder exists on your PC. A group with several empty categories folds them behind a button; **Hide empty** folds them again. **Select all** / **Select none** works per group.

### Temporary files

Rebuilt by the apps, at almost no cost.

| Category | What it clears |
|---|---|
| **Temporary files** | Files apps left in Temp. The last day's files are kept. |
| **Crash dumps and error reports** | Dumps and reports from crashed apps. A known game's dumps show under that game instead. |
| **Chrome cache**, **Edge cache**, **Brave cache**, **Opera GX cache**, **Firefox cache** | Cached pages and images for every profile. Sites load a bit slower once. |
| **Discord cache** | Images, GIFs and videos from chats. |
| **Spotify cache** | The streaming cache, not your offline downloads. |
| **Explorer thumbnails** | Picture and video previews. Rebuilt as you browse. |
| **Microsoft Teams cache**, **Epic Games Launcher cache**, **Battle.net cache** | Web caches of the launchers. The app must be closed. |
| **Deck's game artwork** | Game pictures Deck downloaded; fetched again when needed. |

### Game shader caches and crash reports

| Category | The cost |
|---|---|
| **NVIDIA shader caches**, **AMD shader caches**, **DirectX shader cache** | Games rebuild them; the first launch after cleaning can stutter. |
| **<Game>: shader cache** | Steam's shader cache for one game. Close the game first. |
| **<Game>: crash dumps** | Keep them if you are looking into a crash. |

### Developer caches

**npm cache**, **pip cache**, **Gradle caches**, **NuGet packages** and **Rust build cache** (shown only with a shared Cargo build folder, `CARGO_TARGET_DIR`). They download or build again when needed; the next build is slower.

### Old downloads

**Old installers in Downloads**: setup files (.exe, .msi, .msix, .appx) directly in Downloads that are over 2 weeks old. They go to the Recycle Bin, so you can get one back.

### Recycle Bin

One row with the items it holds. Emptying it removes everything in it on all drives, for good; the review window warns you. Old installers and anything [Disk space](drives.md) sent to the bin free their space only once it is emptied.

### Windows (needs administrator)

**Delivery Optimization cache**, **Windows Update download cache** and **Windows error reports (all users)**. Hidden unless Deck runs as administrator. A pending update may download again.

## Recommended setup

- Everyone: keep the default selection and clean every month or two.
- Gamers: leave shader caches alone unless a driver update left you with stutter or space is short.
- Small SSDs: also select **Old installers in Downloads** and the developer caches.
- Close browsers before cleaning them.
- For bigger gains, use [Disk space](drives.md).

## Troubleshooting

- **A category shows 0 B.** It is empty, or the app is open and holds its cache. Close the app and press **Scan again**.
- **It freed less than shown.** Files in use were skipped, and old installers count as freed only once the bin is emptied.
- **A category is missing.** Its folder doesn't exist on this PC.
- **It says some sizes are missing.** Measuring stopped early. Press **Scan again**.
- **A game stuttered after cleaning shader caches.** Expected once while it rebuilds them.
- **Where is Clear RAM?** It is **Free up memory** on the [CPU](cpu.md) page's Memory card.

## FAQ

- **Can this break anything?** No. Everything here is cache or temporary data. Only an emptied Recycle Bin and deleted crash dumps can't come back, and Deck says so first.
- **Does it delete saved games or screenshots?** No. Game rows are shader caches and crash dumps only.
- **Is anything sent anywhere?** No.
