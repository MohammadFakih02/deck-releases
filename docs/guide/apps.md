# Apps

The **Apps** page is where you uninstall programs properly, update them, remove the apps Windows ships with, and install or update Microsoft Store apps even when the Store is broken or slow.

Find it under **Clean > Apps** in the sidebar. The page has four tabs:

| Tab | What it is for |
|---|---|
| **Installed** | Every installed program, with Uninstall, and an Advanced uninstall that also finds what the program left behind. |
| **App updates** | Newer versions of your desktop programs, updated one by one with your say-so. |
| **Built-in apps** | Windows' own preinstalled apps (Clipchamp, Weather, Xbox apps, OEM bloat...), with Remove and Reinstall. |
| **Store apps & updates** | Update your Store apps without the Store, and install free Store apps. |

The tab you used last is remembered.

---

## Tab 1: Installed

The list shows what Windows' own "Installed apps" shows: programs registered in Windows, plus your Microsoft Store apps. Each row has the app's icon and name, a line with publisher, version, install date and size, and buttons.

### Finding an app

- **Search your apps** matches the name and publisher.
- **All / Desktop / Store / Needs attention (N)** filters the list.
- **Name / Size / Newest** sorts it. Sizes are what the app itself reports; a few report none.
- **Refresh** reads the list again.
- A folder button on a row (and **Open folder** in the selected-app panel) opens the app's install folder. Store apps have none.
- The line above the list gives the number of apps and the total of the sizes that were reported.

### Needs attention

Some entries are leftovers of a half-finished uninstall. They sit in their own **Needs attention** panel at the top, with a chip saying why:

| Chip | Meaning |
|---|---|
| **Uninstaller missing** | The uninstall program is gone. **Advanced** removes what is left. |
| **Missing from Windows' list** | Windows Installer knows the app but Settings does not list it (a cleanup tool or a bad uninstall removed the entry). It uninstalls normally from here. |
| **Files gone** | The install folder is gone. **Uninstall** finishes the job; **Advanced** also clears leftovers. |

They clutter the list and can stop you reinstalling the app. If Deck closed in the middle of an advanced uninstall, a banner offers **Look for leftovers now** or **Forget it**.

### Uninstall

**Uninstall** runs the app's own uninstaller, the same one Windows' Settings runs.

1. Deck asks you to confirm.
2. The uninstaller runs. Deck waits until it **and anything it started** have finished (many installers copy themselves to a temporary folder first).
3. If the app is gone, Deck automatically looks for what it left behind and shows the **What <app> left behind** window (below). If it found nothing, it says so.
4. If the uninstaller closed without removing the app, Deck says "is still installed". You can try again or use Advanced.

A **Store app** is removed for your account, with no leftovers search.

**Windows runtimes** (Visual C++, .NET, DirectX): before removing one, Deck checks which installed apps use it and tells you ("3 installed apps use it: ... They may stop working without it"). It is a best-effort check: apps that keep their files out of reach, such as Store apps, cannot be checked. You can also press **Who uses this?** on a selected runtime.

### Advanced uninstall (Review removal)

For an app whose uninstaller is broken or missing, or one that keeps coming back. It is the **Advanced** button on a row, or **Review removal** in the selected-app panel.

- If the uninstaller still works, it runs first. If it fails or is cancelled, Deck asks whether to look for leftovers anyway.
- If the uninstaller is missing, Deck removes the app's list entry and goes straight to leftovers.
- Not offered for Store apps (a normal Uninstall already removes them cleanly).

### What it left behind

The leftovers window lists what Deck found, in groups:

| Group | What goes |
|---|---|
| **Folders** | The app's install folder and folders named after the app in the usual places. Sent to the **Recycle Bin**. |
| **Shortcuts** | Start menu shortcuts and folders for the app. Sent to the Recycle Bin. |
| **Registry** | The app's settings keys. Each key is **saved to a backup file first** in Deck's data folder (`backups\uninstall`), then removed. |
| **Windows services** | A service that runs a program from the app's folder. Stopped and removed, with a backup of its settings saved first. |

Each item shows its path, why Deck thinks it belongs to the app, and its size. **Only items Deck is sure about are ticked**; check the rest, because a folder can be shared with another program. Deck's matching is deliberately narrow: a name has to match the app's own name or its install folder's name, and nothing that another installed program still uses is offered.

Choose **Keep all** to leave everything, or **Remove selected**. Nothing is removed unless you tick it.

**Recommended:** for ordinary apps use **Uninstall**. Use **Advanced** when something is broken.

---

## Tab 2: App updates

Shows which of your installed **desktop** apps have newer versions. It uses Windows' App Installer tool (winget). If winget is not installed, the tab says so and points you to **App Installer** in the Microsoft Store.

1. Press **Check for updates**. Deck asks winget and lists every app with an update, each with `current version -> new version`. It is ticked.
2. Untick any app you do not want updated (**Tick all** / **Untick all** help).
3. Press **Update N apps**. Apps update **one at a time**, each with its own result: **Waiting**, **Updating...**, **Updated**, **Failed** or **Skipped**. A single app gets up to 15 minutes.
4. **Stop after this one** ends the run after the current app. If a game comes to the front, the rest wait and are marked Skipped.
5. A summary says how many updated and how many failed.

Nothing updates until you press **Update**. Apps that winget will not update by itself (pinned or needing manual installation) are not listed. For Microsoft Store apps use the **Store apps & updates** tab.

---

## Tab 3: Built-in apps

Windows comes with apps many people never use. This tab lists the well-known ones and lets you **Remove** each for your account, or **Reinstall** one you removed.

- Apps are grouped by how safe it is to remove them:

| Group | Meaning |
|---|---|
| **Safe to remove** | Nothing depends on them (sponsored games and apps, Bing apps, Clipchamp, Feedback Hub, old Skype, Teams and more). |
| **Optional: you may use these** | Things you may use: Photos, Calculator, Notepad, Snipping Tool, Paint, Xbox apps, Phone Link, OneDrive, Outlook and the OEM apps from HP, Dell and Lenovo. |
| **Windows or other apps need these** | Hidden by default (Get Help, Microsoft Store, Windows Terminal and the Xbox support pieces). Turn on **Show apps Windows needs** to see them. Removing one can stop Windows or other apps from working. |

- **Search your built-in apps** filters the list; **Refresh** reads it again. Only apps installed on your PC can be removed; ones you already removed show **Reinstall**.
- **Remove**: Deck first offers to make a **restore point** (once per session; Windows allows one a day), then asks you to confirm. An "unsafe" app gets an extra warning that something may stop working. The app is removed for your account.
- **Reinstall** downloads the app from Microsoft's servers (the progress appears on the Store tab).

Removing is not a risk to your files, but a removed app's own data goes with it. The list is from the Win11Debloat project (MIT). **Microsoft Edge is never offered**, because Deck and other apps rely on its engine.

---

## Tab 4: Store apps & updates

### Updates

Press **Check for updates** to ask Microsoft's servers about every Store app you have. Deck lists those with a newer version (installed `->` latest, and the size). It works without the Store app.

- **Update** installs the new version for one app. **Update all (N)** / **Update N selected** updates the ticked ones **one at a time** (a slow line split ten ways helps nobody). Others wait in a queue shown on the row, and **Don't update** takes one out.
- **Install Store updates when downloaded** (a switch in **Settings › Desktop**, **on by default**): the update installs as soon as it has downloaded. With it off, or for apps with **Wait for Install** ticked, the update downloads and then waits for you to press **Install**, so an open app never closes in front of you. The app is closed if it is open when installing.
- **Stop** pauses an update; what was downloaded is kept, and **Carry on** continues. **Stop all** and **Carry on all** do it for everything. An update interrupted by closing Deck can be carried on later too.
- A message names any app that **could not be checked** (with the reason, often that Microsoft's server was busy; Deck retries each, and **Try those again** repeats it), paid or protected apps that only the Store can check, and apps that are not in the Store's catalogue because they were installed elsewhere.
- An app whose version numbers use a different style is marked **Different version numbering: not ticked**, because Deck cannot tell whether it is newer.
- **Update all with the Microsoft Store** hands the whole job to Windows' own Store update. It cannot skip unticked apps, so Deck warns you first. If the **Store apps update by themselves** tweak is set to Off (see [Tweaks](tweaks.md)), Windows does not let the Store update apps on its own, so this button cannot work, and Deck explains your options.
- **Store's Downloads page** opens the Store.
- The per-app **...** menu gives the download links, or updates that app in the Store.

### Downloads

A **Downloads** list shows every job with progress, speed and time left. **Pause all**, **Resume all**, **Install all downloaded** and **Clear finished** manage them. A job that was paused, failed or interrupted keeps its partial download, so **Resume** or **Try again** carries on from there.

### Get a Store app

For when the Store is broken, removed or slow. Search the Store ("Spotify, WhatsApp, Netflix...") and pick a result:

- **Install**: downloads the app's package from Microsoft's update servers (as the Store does), checks it and installs it for your account.
- The **...** menu: **Download only (to Downloads\Store apps)**, **Send to FluxDM** (if you use that download manager), or **Show the download links** (copy one link, copy all the links this PC needs, or open one). Links mark the dependencies you already have.
- **Paid** apps show **Open in Store**: only the Store can supply them. The same goes for protected apps. This feature is for **free** apps.
- An app you already have shows **Installed**, its version, **Check for update**, **Update** and **Uninstall**.
- If the result is a desktop app rather than a Store package, Deck offers **Install with winget**.

---

## Requirements

| Feature | Needs |
|---|---|
| Uninstall, Advanced uninstall | Nothing special. Without administrator rights, all-users apps may ask Windows for permission. |
| App updates | winget (App Installer, included in current Windows). |
| Built-in app Remove and Reinstall | A normal signed-in account. |
| Store updates and Get a Store app | Internet. Downloads come from Microsoft's own update servers. |

---

## Recommended setup

- Uninstall with **Uninstall** first. Use **Advanced** only when it fails.
- Check **App updates** every few weeks for desktop apps, and leave **Install Store updates when downloaded** on for Store apps, unless you often keep apps open for days, in which case tick **Wait for Install** on those.
- **Built-in apps:** start with the **Safe to remove** group. Skip anything you might use. On a laptop from HP, Dell or Lenovo the maker's own apps are listed under Optional.
- Make the restore point when asked.

---

## Troubleshooting

**An app is still in the list after Advanced.** Press **Refresh**. If it stays, it may be a Store package; remove it from the Store entry.

**"Is still installed" after Uninstall.** The uninstaller was cancelled or failed. Try again, or use **Advanced**.

**Update says "Failed".** The row gives the reason. Close the app and try again; for desktop apps, a program that needs a reboot or is open often blocks winget.

**Store update says the Store can't update by itself.** The **Store apps update by themselves** tweak is set to Off. Update here, use the Store's **Get updates**, or set the tweak back to On.

**Remove is greyed or missing for a built-in app.** It is not installed for you, or it is in the "Windows needs these" group and hidden. Use **Show apps Windows needs**.

**Can't find a Store app.** Paid and protected apps cannot be installed here. Try a more specific name.

---

## FAQ

**Is Advanced uninstall safe?** It only offers what it finds and only removes what you tick. Files go to the Recycle Bin, and registry keys and services are backed up first. Deck never removes anything it is not sure about without your tick.

**Will removing Windows' built-in apps break Windows?** Not the ones in the safe and optional groups. The "needs" group is where you can cause trouble, which is why it is hidden by default.

**Can I get a removed built-in app back?** Yes, with **Reinstall**.

**Why are some sizes empty?** The app does not report one.

**Does this send my app list anywhere?** No. Store updates and installs contact Microsoft's servers for the apps you ask about, the same as the Store. App updates go through winget.
