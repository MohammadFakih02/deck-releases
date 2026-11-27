Where to find it: Connections › Project sync

# Project sync

Project sync keeps a workspace client's sessions, memory and settings the same on all your PCs, so you can continue the same work on another PC.

A workspace client is a coding tool that keeps conversation sessions, project memory and settings in your user folder. If you don't use one on several PCs, you can ignore this page. Project sync is off, and hidden from the sidebar, until you turn it on or show it in [Settings › Features](settings.md#features).

The tabs are **Status**, **Sessions**, **Projects** and **Log**.

## Turning it on

1. Press **Turn on Project sync** on every PC.
2. Give every PC the same **Sync key** (in **Sync settings** on the Status tab).
3. Make sure the PCs can reach each other: same network, Tailscale or a cloud folder.

Turning it on:

- Starts syncing sessions, memory and settings. Project files stay off until you turn them on.
- Adds two small hooks to the client's settings file: one stops a session being used on two PCs at once (the session lock), one tells the client which PC it runs on. Turning sync off removes them.
- Listens for your other PCs on UDP 47835 and TCP 47836.

If the older standalone sync app is running, close it first (tray icon › Exit). Its settings are imported once.

The **Sync between your PCs** switch in the tab row turns it off again.

### How it is protected

- Everything sent between PCs, or stored in the cloud folder, is encrypted with your sync key.
- Sign-ins and other per-PC files never sync.
- Incoming changes that could make the client run a program (hooks, plugins, permissions, add-on servers and similar) wait for your answer on this PC.
- The sync key is separate from PC to PC's pairing code.

## Status

### Last sync

A chip shows **Up to date**, **Syncing** or a problem, with when it last ran, **Sync now** and **Pause syncing** or **Resume syncing**. The **Connection and storage** card shows the total size, the port, whether it works away from home, the cloud folder and what arrived since Deck started.

### To review

Anything that needs you appears in **To review**:

- **Held changes**: an incoming change that could run a program shows **Waiting for your OK:** with the files and the sending PC. **Use their version** applies it, **Use this PC's version** refuses it. Apply it only if you made it.
- **Conflicts**: a file both PCs changed. **Use this PC's version** or **Use their version** picks one; the other stays in the sync data.
- **Large changes**: if a batch would delete more than half of an item's files, or every file looks changed, Deck holds the whole batch (Activity shows **N failed / waiting for you**). **Apply anyway** allows that exact batch; **Cancel** leaves it. This protection is always on.
- A session that is open on another PC (**Take over**), or a project whose folder is missing on this PC (left alone).

### Preview and last changes

- **Preview changes** lists what the next sync would copy, replace or delete (**Next sync preview**). It changes nothing.
- **Last sync changes** lists what the last sync copied, replaced, deleted or restored, and from which PC.

### Protection: older copies

**Protection** shows, for **Sessions**, **Project memory**, **Settings and extensions** and **Project files**, whether versions are kept, how much space they use, and **Open versions**.

To restore one file:

1. In **Protection**, press **Restore** on the item (shown once it has saved copies).
2. Open the file's fold: its kept versions, newest first, with time and size.
3. Press **Restore** on a version. Deck first keeps the file as it is now as a new version, then puts the older one back. The next sync sends it to your other PCs, and **Last sync changes** lists it as **Restored**.

Deck refuses a restore while the session is open in the client, or when the file already matches. Kept versions are a history, not a full backup.

### Your other PCs

Each PC found: online or not, how it is reached, when it last changed, its file count, Deck version and processor kind. A warning shows when its Deck version differs (update the older one) or its clock is more than 2 minutes off (set both clocks to automatic, because newest wins). **Open sync settings** opens the settings.

### Programs

With **Find programs missing on this PC** on, this lists developer programs another PC has and this one lacks: Rust toolchains and tools, Node and npm packages, Python and pipx tools, Git, and the C++ build tools Rust needs. **Install all** or **Install** opens a PowerShell window with your normal rights; nothing installs on its own. **Refresh** reads this PC again.

### Open workspace sessions

Sessions open in the client here and on other PCs.

- A session open elsewhere is locked here. **Take over** unlocks it after you confirm; it stays open on the other PC, and if both add messages you get two copies. Safer: close it there, then resume it here. **Undo takeover** puts the lock back.
- A session here with newer messages elsewhere says so: close it and its editor tab to get them.

## Sessions

Every synced session, searchable by title, words, project or id, with the chips **Open elsewhere**, **Waiting** and **Only on this PC**; **Show more** loads the next 60. Each shows the project, which PCs have it, prompts, size, last use and id.

- **Get latest** syncs newer messages from another PC. Close the session and its tab, then resume it.
- **Delete here…** removes it from this PC only. **Delete on all PCs…** removes it everywhere; a PC that is off or has it open deletes it later. Deleted sessions go to the trash folder. An open session can't be deleted.

## Projects

Each project (a folder the client worked in) has one name on every PC and its own folder on each.

| Control | What it does |
|---|---|
| **Folder on this PC** | Where it lives here. **Move…** changes it; close the client first. |
| **Guessed from** another PC | Files don't arrive until you press **Keep this folder** or **Move…** to the right place. |
| **Sync this project** | Off: its sessions, memory and files stay on this PC. |
| **Its sessions (conversations)** | Off: memory (and files) still sync, so you start a fresh session on the other PC. |
| **Its files (the project folder)** | Needs **Project files** on in Sync settings. |
| **Leave out of the sync** | Names, `*.ext` patterns or folder paths to skip, separated by commas. |
| **Verify now** | Compares the files with the other PC without copying: **Identical to** that PC, or a list of **Differences** (**Differs**, **Only here**, **Only on** the other PC). |
| **Get git history** | Files are copied without `.git`. This opens a PowerShell window that connects the folder to the same remote and branch; your files stay. |
| **Delete everywhere…** | Deletes its sessions and memory on every PC. Project files stay; the rest is recoverable from the trash folder. |

## Project sync settings

They sit at the bottom of the **Status** tab, in the **Sync settings** fold.

### This PC

| Setting | What it does |
|---|---|
| **Name** | This PC's name in Project sync. |
| **Sync key** | Hidden; show and copy it with its buttons. Use the same key on every PC. |
| **Use the other PC's key** | Paste a key from another PC. |
| **New key** | Makes a new key. Your other PCs stop syncing until they get it too. |

### How PCs connect

| Setting | What it does | Default |
|---|---|---|
| **Directly, on the same network** | Finds PCs on your network. | On |
| **Connect from anywhere with Tailscale** | Also reaches PCs over Tailscale (**Get Tailscale**, **Open Tailscale**). | On |
| **Other PC's address** | Only if they don't find each other: a name or address. | Empty |
| **Catch up through a cloud folder** | Syncs through a folder OneDrive, Google Drive or Dropbox keeps in sync, for PCs that are never on the same network. **Use OneDrive** or **Choose…**. Use the same folder on every PC. | Off |

### What to sync

| Setting | What it does | Default |
|---|---|---|
| **Sessions and conversation history** | Sessions. | On |
| **Project memory** | Project memory files. | On |
| **Settings and extensions** | Settings, skills, plugins and add-on server lists. | On |
| **Project files** | Each project's folder, without `.git` and build output. Never a folder over 40,000 files or 3 GB, a drive or your user folder. Stops when the drive has under 2 GB free. Turning it off deletes nothing. | Off |
| **Include build folders** | Also copies build output. Can be several GB; rebuilding is often quicker. | Off |
| **Find programs missing on this PC** | The Programs card. | On |
| **Check every** | 10 seconds to 5 minutes. | 20 seconds |

### Sync versions

**Keep versions** for each item (all off by default) keeps older copies before a sync replaces or deletes a file, with **Max age (days)** (default 365) and **Size limit (MB)** (default 512). Copies thin out over time (hourly within a day, daily within a month, then weekly). Versions stay on this PC, are never sent elsewhere, and can hold private contents. Restore one from [Protection](#protection-older-copies).

### Workspace client

| Setting | What it does | Default |
|---|---|---|
| **Prevent editing the same session on two PCs** | The session lock. | On |
| **Identify this PC in each session** | Tells the client which PC it runs on. | On |

**Project sync details** shows the ports, with **Open data folder**.

## Log

**Recent activity** of Project sync.

## Recommended setup

1. Turn on Project sync on both PCs and use the same key.
2. Leave Sessions, Memory and Settings on. Turn on **Project files** only for projects you really move between PCs.
3. Close a session on one PC before you continue on the other. Keep the session lock on.
4. Turn on **Keep versions** for items you can't afford to lose.

## Troubleshooting

**The other PC doesn't appear.** Same sync key? On in both? Same network or Tailscale? Try **Other PC's address**.

**A PC runs an older Deck.** Update it.

**Changes are waiting.** Answer them under **To review** on the Status tab.

**A session is open on another PC.** Close it there and resume it here, or use **Take over** knowing you may get two copies.

**A project's files don't arrive.** Check **Project files**, **Sync this project** and **Its files** are on, the folder was kept or moved (not only guessed), it is under the size limits, and its drive has 2 GB free.

**The cloud folder doesn't catch up.** Use a folder the cloud app really syncs, the same one on every PC, and give it time to upload.

## FAQ

**Does this send my data to a server?** No server of Deck's. Data goes between your PCs, or through your own cloud folder, encrypted with your key.

**What if someone gets my key?** They could sync with your PCs. Changes that could run a program still wait for you. Use **New key** if the key leaks.

**Does it change my files?** It writes synced files into the client's folder and, if turned on, project folders, and adds the two hooks. Deleted files go to a trash folder.

**Is it safe with anti-cheat?** It doesn't touch games.
