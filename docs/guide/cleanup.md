# Clean up

The **Clean up** page removes safe junk that Windows and your apps rebuild by themselves: temporary files, browser caches, crash dumps, shader caches and old installers. You see the size of each category before anything happens, tick what you want, review it, and only then does Deck delete.

Find it under **Clean > Clean up** in the sidebar. Once the sizes are measured, the **Clean** group in the sidebar shows the total amount that could be cleaned.

> Nothing here needs administrator rights, and nothing is deleted until you confirm in a review window. Deck never touches your documents, pictures, saved games, browser passwords, bookmarks, history or logins: it clears only cache folders and the other locations listed below.

---

## How the page works

1. When you open the page, Deck **measures** every category in the background. Sizes fill in one at a time ("Measuring..." until done). Press **Measure again** any time to re-measure.
2. Tick the categories you want. The big number at the top of the page, **Selected to clean**, adds up what you ticked.
3. Press **Review clean up**. A window lists each selected category with its size. It says what will happen: caches are deleted, old installers go to the Recycle Bin, and, if you ticked the Recycle Bin, it is emptied and its items are gone for good. It also lists the categories you did **not** tick, "will be kept".
4. Press **Clean selected files** to go, or **Back** to change your mind.
5. While it works, a **Stop** button appears. Stopping leaves the rest untouched.
6. A notification tells you what was freed ("Freed 2.3 GB: N files processed. Files in use were skipped."), and the page shows **Last clean freed ...** afterwards, with the part that went to the Recycle Bin counted separately because it is not freed until the bin is emptied.

**Files in use are skipped.** If an app is open while its cache is cleaned, the row shows "Chrome is open: some files will be skipped". Close the app first for a complete clean.

### What is ticked at first

By default Deck ticks only the most routine, no-cost categories: **Temporary files**, **Crash dumps and error reports**, the browser caches (Chrome, Edge, Brave, Opera GX, Firefox), the **Discord cache** and **Explorer thumbnails**. Everything else is unticked until you choose it.

---

## The categories

Categories are in three groups, each sorted biggest first. A category only appears if its folder exists on your PC (without Firefox installed there is no Firefox row).

### Caches and old reports

Deck rebuilds these on its own, and they cost you almost nothing.

| Category | What it clears | Notes |
|---|---|---|
| **Temporary files** | Leftovers apps put in your Temp folder. | Files from the **last day are kept**, so something that is running right now is not pulled from under it. |
| **Crash dumps and error reports** | Memory dumps and Windows Error Reporting files from crashed apps. | Dumps that belong to a game Deck recognises are shown under that game instead (see below), so nothing is counted twice. |
| **Chrome cache** | Cached web pages and images, code cache, GPU cache and service-worker cache for every Chrome profile. | Sites load a bit slower the first time afterwards. Passwords, bookmarks and history are not touched. |
| **Edge cache** | The same for Microsoft Edge. | Edge's engine is also used by some apps. |
| **Brave cache** | The same for Brave. | |
| **Opera GX cache** | The same for Opera GX. | |
| **Firefox cache** | Cached web pages and images for every Firefox profile. | |
| **Discord cache** | Cached images, GIFs and videos from chats. | |
| **Spotify cache** | Songs Spotify cached for streaming. | **Not** your offline downloads. |
| **Explorer thumbnails** | The picture and video previews File Explorer keeps. | Only the thumbnail cache files are removed. Explorer rebuilds them as you browse. |

### Caches and downloads to rebuild

These are safe too, but they cost you time later (a rebuild, a re-download or a stutter), so they are unticked.

| Category | What it clears | The cost |
|---|---|---|
| **NVIDIA shader caches**, **AMD shader caches**, **DirectX shader cache** | Compiled graphics shaders stored by your graphics driver and DirectX. | Games rebuild them. The first launch after cleaning can stutter while shaders compile again. |
| **<Game>: shader cache** | Steam's shader cache for one installed game, found in your Steam libraries. | Close the game first. Its next launch may stutter. |
| **<Game>: crash dumps** | Windows crash dumps from a recognised game's executable. | Keep them if you are investigating a crash. |
| **Old installers in Downloads** | Setup files (.exe, .msi, .msix, .msixbundle, .appx) in your Downloads folder that are **more than 2 weeks old**. | They go to the **Recycle Bin**, not straight to deletion, so you can get one back. Only files directly in Downloads are touched, not subfolders. |
| **npm cache**, **pip cache** | Downloaded JavaScript and Python packages. | Downloaded again when needed. |
| **Gradle caches**, **NuGet packages** | Android/Java build downloads and .NET packages. | The next build is slower. |
| **Rust build cache** | Cargo build output. | Only shown if you use a shared Cargo build folder (the `CARGO_TARGET_DIR` setting). Builds take minutes to compile again. Deck only touches folders that really are build output and never a project. |

### Recycle Bin

A single row: **Recycle Bin**, with how many items it holds and their size. Emptying it removes everything in it for good, on all drives. The review window warns you ("It's emptied too: N items gone for good").

Old installers and anything you sent to the bin from [Disk space](drives.md) only free their space when the bin is emptied, which is why this row exists.

---

## Requirements

None. Everything here is in your own user folders. Deck deletes through a held handle to each folder it measured and only removes what your account is allowed to delete, so a link swapped in after the scan cannot lead the deletion somewhere else.

---

## Recommended setup

- **Everyone:** leave the default selection, review, and clean every month or two.
- **Gamers:** leave the shader caches unticked unless a driver update left you with stuttering or the drive is short on space. Clean them only when you can afford one stuttery first launch of each game.
- **Laptops and small SSDs:** also tick **Old installers in Downloads** and, if you develop software, the developer caches.
- **Before cleaning a browser:** close it, so nothing is skipped.
- Use [Disk space](drives.md) when you need a bigger gain: it shows exactly what is large, and its **Space plan** uses these categories as its first step.

---

## Troubleshooting

**A category shows 0 B.** Nothing is in it right now, or the app is open and has its cache locked. Close the app and press **Measure again**.

**It freed less than the number shown.** Files in use were skipped. The recycled part (old installers) is not counted as freed until you empty the Recycle Bin.

**A category I expect is missing.** Rows only appear for folders that exist: install the app and use it once, or the app is not installed.

**It says "Stopped early".** You pressed Stop (or measuring was interrupted), so some sizes may be missing. Press **Measure again**.

**The first launch of a game stuttered after cleaning shader caches.** Expected: the game is rebuilding its shaders. It will be smooth again afterwards.

**Where is Clear RAM?** It is not on this page. Deck's **Clear RAM now** button lives on the CPU page, under **Settings > Memory** (see [CPU](cpu.md)).

---

## FAQ

**Can this break anything?** Everything on the page is a cache or temporary data that the apps recreate. Deleting the Recycle Bin and clearing crash dumps are the only things you cannot get back, and Deck says so before it does them.

**Does it delete my browser logins, bookmarks or history?** No. It only clears the browsers' cache folders.

**Does this delete my saved games or screenshots?** No. Game rows are shader caches and crash dumps only.

**Will it clean while a game is running?** Files a running program has open are skipped, so it is safe, but clean when the game is closed for the best result.

**Is anything sent anywhere?** No. Clean up works entirely on your PC.

**Why not an "everything" button?** Because the categories cost different things (a re-download, a stutter, a lost dump). You choose, and the review window shows the sizes first.
