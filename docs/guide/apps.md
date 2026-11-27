Where to find it: Clean up › Apps

# Apps

Uninstall programs cleanly, update them, remove Windows' built-in apps, and get Store apps without the Store.

| Tab | What it is for |
|---|---|
| **Installed** | Every installed program, with **Uninstall** and **Review removal** (uninstall plus leftovers). |
| **App updates** | Newer versions of your desktop programs, through winget. |
| **Built-in apps** | Windows' preinstalled apps, with **Remove** and **Reinstall**. |
| **Store apps & updates** | Update and install Store apps without the Store. |

## Installed

The list matches Windows' Installed apps, plus your Store apps. Each row shows the icon, name, publisher, version, install date and size.

- **Filter by name or publisher** narrows this list. The chips **Desktop**, **Store** and **Needs attention** filter by kind (**Clear** shows all). Sort by **Name**, **Size** or **Newest**.
- **Refresh** reads the list again. **Open folder** opens an app's install folder.
- Up and Down move between apps; Enter shows one in **Selected app**.
- When **Uninstall app** isn't available, the reason shows beside it.

### Needs attention

Leftovers of a half-finished uninstall sit in their own panel, with a chip saying why:

| Chip | Meaning |
|---|---|
| **Uninstaller missing** | The uninstaller is gone. **Review removal** removes what's left. |
| **Not in Windows' list** | Windows Installer knows the app but Settings doesn't list it. It uninstalls normally here. |
| **Files gone** | The install folder is gone. **Uninstall** finishes the job. |

If Deck closed during an advanced uninstall, a banner offers **Scan for leftovers** or **Forget it**.

### Uninstall

1. Press **Uninstall** and confirm. The app's own uninstaller runs, the same one Windows Settings uses.
2. Deck waits for it and anything it started to finish.
3. If the app is gone, Deck looks for leftovers and shows **What <app> left behind**.
4. If the uninstaller closed without removing the app, Deck says so. Try again or use **Review removal**.

A Store app is removed for your account, with no leftovers search.

Before you remove a Windows runtime (Visual C++, .NET, DirectX), Deck says which installed apps use it. **Who uses this?** checks on demand. It is a best guess: Store apps can't be checked.

### Bulk uninstall

1. Press **Pick several** and select the apps.
2. Press **Review**. Deck lists the apps in the order it will remove them, each with what depends on it: a launcher's games, games inside the app's folder, startup entries, and Deck's own game profiles and workspaces that start it. A launcher whose game you also picked goes last.
3. Press **Uninstall N**. Apps go one at a time, with "2 of 5" progress.

Nothing is uninstalled quietly. Each app's own uninstaller opens and asks (**Opens its window**); for a Store app, Deck asks first (**Deck asks**). Each app gets its own result: **Removed**, **Canceled** or **Failed** with the reason. A canceled or failed app stops the queue; the rest show **Not started**. **Stop after this one** ends early.

- Nothing starts while a game is in front.
- Apps without an uninstaller, Deck itself, runtimes and drivers can't be selected; remove those on their own.
- Bulk uninstall doesn't search for leftovers. Use **Review removal** on one app for that.

### Deck still points at it

After an uninstall, the **Deck still points at it** card lists Deck settings that still name the app: game profiles, workspaces, pinned items, window rules and sound rules. **Remove N** takes them out (a workspace stays, without the app); **Undo** brings them back; **Keep them** leaves them.

### Review removal

For an app whose uninstaller is broken or missing, or one that keeps coming back. Not offered for Store apps.

- A working uninstaller runs first. If it fails or you cancel it, Deck asks whether to look for leftovers anyway.
- A missing uninstaller: Deck removes the list entry and goes straight to leftovers.

The leftovers window groups what Deck found:

| Group | What happens |
|---|---|
| **Folders** | The install folder and folders named after the app. Sent to the Recycle Bin. |
| **Shortcuts** | Start menu shortcuts. Sent to the Recycle Bin. |
| **Registry** | The app's settings keys. Each is backed up first, then removed. |
| **Windows services** | Services that run from the app's folder. Stopped and removed, with a backup. |

Only items Deck is sure about are selected; check the rest. Names must match the app or its folder, and nothing another installed program uses is offered. Choose **Keep all** or **Remove selected**.

## App updates

Uses Windows' App Installer (winget). Without it, the tab points you to App Installer in the Microsoft Store.

1. Press **Check for updates**. Every app with a newer version is listed and selected.
2. Clear the ones you don't want (**Select all** / **Select none**).
3. Press **Update N apps**. Apps update one at a time, each showing **Waiting**, **Updating…**, **Updated**, **Failed** or **Skipped**.
4. **Stop after this one** ends after the current app.

- While a game is in front, nothing starts; the run waits (**Stop waiting** cancels).
- Apps pinned in winget are listed but held; **Unpin** releases one. **Skip this version** keeps one version out until a newer one appears; **Stop skipping** undoes it.
- **Scoop** and **Chocolatey** cards appear when those are installed. **Copy command** copies the update command for you to run in a terminal. Deck never updates through them.

For Store apps, use **Store apps & updates**.

## Built-in apps

Windows' preinstalled apps, grouped by how safe they are to remove:

| Group | Meaning |
|---|---|
| **Safe to remove** | Nothing depends on them: sponsored apps, Bing apps, Clipchamp, Feedback Hub and more. |
| **Optional** | Apps you may use: Photos, Calculator, Notepad, Xbox apps, Phone Link, OneDrive, and HP, Dell and Lenovo apps. |
| **Windows needs** | Hidden unless you turn on **Show apps Windows needs**. Removing one can break Windows features. |

- **Search your built-in apps** filters the list.
- **Remove**: Deck first offers a restore point, then asks you to confirm. The app is removed for your account, with its data.
- **Reinstall** downloads it again from Microsoft (progress shows under **Get Store apps**).
- Microsoft Edge is never offered: Deck and other apps need it.

The list comes from the Win11Debloat project (MIT license).

## Store apps & updates

### Updates

1. Press **Check for updates**. Deck asks Microsoft's servers about every Store app you have; the Store app itself isn't needed.
2. Press **Update** for one app, or **Update all (N)** / **Update N selected**. They update one at a time; **Don't update** takes one out of the line.

- **Install Store updates when downloaded** (on by default) installs each update as it finishes; an open app closes. For an app set to **Wait for me to install** (in its More menu), or with the switch off, the update waits for **Install**.
- **Stop** keeps what was downloaded; **Resume** picks up from there. **Stop all** and **Resume all** do it for everything.
- Apps Deck couldn't check are named with the reason; **Try those again** retries. Paid and protected apps can only be checked by the Store.
- **Different version numbering: not selected** means Deck can't tell whether the version is newer.
- **Update all in Store** hands the job to the Microsoft Store, which can't skip unselected apps. If the **Store apps update automatically** tweak is off in [Windows tweaks](tweaks.md), the Store isn't allowed to, and Deck explains your options.

### Downloads

Every job with progress, speed and time left. **Pause all**, **Resume all**, **Install all downloaded** and **Clear finished** manage them. A paused, failed or interrupted job keeps its partial download.

### Get Store apps

For when the Store is broken, removed or slow. Search the Store and pick a result:

- **Install** downloads the package from Microsoft's servers, checks it and installs it for your account.
- The More menu offers **Download only** (to `Downloads\Store apps`), **Send to FluxDM** or **Show the download links**.
- Paid and protected apps show **Open in Store**. This is for free apps.
- An app you already have shows **Installed**, **Check for update**, **Update** and **Uninstall**.
- A desktop app result offers **Install with winget**.

## Recommended setup

- Use **Uninstall** first; **Review removal** only when it fails.
- Check **App updates** every few weeks.
- Keep **Install Store updates when downloaded** on, and set **Wait for me to install** for apps you keep open for days.
- Start built-in removals with **Safe to remove**, and make the restore point when asked.

## Troubleshooting

- **An app is still listed after Review removal.** Press **Refresh**. If it stays, it may be a Store package; uninstall that entry.
- **It says the app is still installed.** The uninstaller was canceled or failed. Try again, or use **Review removal**.
- **An update failed.** The row gives the reason. Close the app and try again; a pending restart often blocks winget.
- **The Store isn't allowed to update automatically.** Update here, or turn the **Store apps update automatically** tweak back on.
- **Remove is missing for a built-in app.** It isn't installed, or it is in **Windows needs**; turn on **Show apps Windows needs**.
- **A Store app can't be found.** Paid and protected apps can't be installed here.

## FAQ

- **Is Review removal safe?** It removes only what you select. Files go to the Recycle Bin; registry keys and services are backed up first.
- **Will removing built-in apps break Windows?** Not those in **Safe to remove** and **Optional**. **Windows needs** is hidden for that reason.
- **Can I get a removed built-in app back?** Yes, with **Reinstall**.
- **Why are some sizes empty?** The app doesn't report one.
- **Is my app list sent anywhere?** No. Store checks ask Microsoft's servers about your apps, as the Store does; app updates go through winget.
