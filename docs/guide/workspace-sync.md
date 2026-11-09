# Workspace Sync

**Workspace Sync** keeps your workspace client's sessions, memory, settings and add-on servers the same on all your PCs, so you can start a piece of work on one PC and carry on in the same place on another. It can also copy your project folders and tell you which developer programs another PC has that this one is missing.

This feature is for people who use a "workspace client" (a coding tool that keeps conversation sessions, project memory and settings in a folder in your user profile) on more than one PC. If you do not, you can ignore this page; the feature is off until you switch it on.

Find it in the sidebar under **Workspace Sync** (the footer group, between PC to PC and Phone). It is hidden unless it is on or you turn on **Show Workspace Sync** in [Settings › General › Sidebar](settings.md#sidebar).

---

## Switching it on

When it is off the page is a short pitch: "Bring your sessions, memory and project settings to your other PCs." Press **Switch on**.

What switching on does:

- Starts syncing sessions, memory and settings (project files stay off until you turn them on).
- Adds two small hooks to the workspace client's own settings file: one stops a session being used on two PCs at once (session lock) and one tells the client which PC it is running on. They run a copy of Deck's program in your user profile. Switching Workspace Sync off removes both hooks.
- Starts a small listener for your other PCs: UDP 47835 and TCP 47836.

If the older standalone sync app is running on this PC, Deck asks you to close it first (tray icon > Exit). Settings from the standalone app are imported once.

Set up on every PC: switch it on, give every PC the **same sync key** (Settings › Connections), and make sure they can reach each other (same network, Tailscale or a cloud folder).

The switch at the top of the page, **Sync between your PCs**, turns it off again.

### How it is protected

- Everything sent between PCs, or stored in the cloud folder, is encrypted and compressed with your sync key.
- Sign-in details and other per-PC files never sync.
- Anything in an incoming change that could make the client run a program (hooks, plugins, status line, helper commands, permissions, environment, add-on servers, and a project's own client settings) does not apply by itself. It waits for your **Apply** on this PC.
- Deck uses a separate key from PC to PC's pairing code.

---

## Status tab

### Last sync

A coloured chip: **Up to date**, a phase ("Syncing...") or a result with problems. Under it: when the last sync ran, **Sync now** and **Pause** / **Resume**.

Other lines may appear:

- A warning when another PC runs an older, newer or just different build of Deck (update the older one).
- **Changes need review**: incoming changes that could run a program wait with the names of the files and which PC sent them. **Apply** accepts them, **Keep this PC's** refuses. Apply only if you made the change.
- The last error in plain words.

Facts shown: how many sessions, memory files, settings files and project files this PC has; the **Connection and storage details** fold gives total size, network port, whether it works away from home, the cloud folder and what was received since Deck started.

### Your other PCs

Each PC that was found: online or not, how it is reached (home network or Tailscale), when it last changed, how many files it holds, its Deck version and processor kind (Intel/AMD or ARM). If none are found there are three steps: switch on Workspace Sync on both PCs, use the same sync key, join the same network, Tailscale or cloud folder.

### Programs

(Only if **Find programs missing on this PC** is on.) Each PC shares which developer programs it has: Rust toolchains, targets and components, cargo tools, Node and global npm packages, Python, pipx tools, Git, and Microsoft's C++ build tools that Rust needs. This card lists what another PC has and this one does not.

- **Install all** or one **Install** button opens a PowerShell window with your normal rights to install them. Nothing installs on its own.
- **Check again** re-reads this PC.
- Versions like "stable" are compared by kind, so each PC installs its own matching kind.

### Open workspace sessions

Sessions open in the workspace client on this PC ("Here") and on other PCs. If session lock is off the card says a session can run on two PCs at once.

- If the client has a session open elsewhere, it is locked here. **Take over** unlocks it here after a confirmation; it stays open on the other PC and if both add messages you get two copies. Safer: close it there, then resume it here. **Undo** puts the lock back.
- A session open here that has newer messages elsewhere says so: close it and its editor tab to get them.

---

## Sessions tab

A searchable list of every synced session (search by title, words, project or ID; 60 shown at a time, **Show more**). Each card shows the title, the project folder, which PCs have it (with online dots), prompts, size, when it was last used and its ID. The first and last prompt are in the **Prompts and technical details** fold.

- If another PC added newer messages: **Get latest** syncs now. Close the session and its tab, then resume it.
- **Delete here...** removes it from this PC only (it will not come back to this PC). **Delete on all PCs...** removes it on every PC; a PC that is off or has it open deletes it later. Deleted sessions go to the trash folder and can be recovered. A session that is open in the client cannot be deleted until closed.

---

## Projects tab

Each project (a folder the client has worked in) has a name that is the same on every PC and its own folder on each PC. For each project:

| Control | What it does |
|---|---|
| **Folder on this PC** | Where the project lives here. **Move...** to change it. Close the client before moving a project. The home folder entry cannot be moved. |
| "Guessed from <PC>" | When the folder was only guessed from another PC, files do not arrive until you press **Keep this folder** or **Move...** to the right one. A guess under another PC's user folder becomes the same place under this PC's user folder. |
| "On <PC>: path" | Where the other PCs keep it. |
| **Sync this project** | Off: its sessions, memory and files stay on this PC. |
| **Its sessions (conversations)** | Off: memory (and files, if copied) still sync, so you start a fresh session on the other PC and carry on with the project. |
| **Its files (the project folder)** | Only with Project files on (Settings › Connections). |
| Files not copied | A note explains why (for example too large). |
| **Get git history** | Files are copied without `.git`. On a PC where the folder has no git history, this offers to open a PowerShell window that connects it to the same remote and branch (files untouched). |
| **Delete everywhere...** | Deletes its sessions and memory on every PC (project files stay; recoverable from the trash folder). |

---

## Workspace Sync settings

These live in **Settings › Connections**, under the Workspace Sync switch, while sync is on.

### This PC

| Setting | What it does |
|---|---|
| **Name** | This PC's name in Workspace Sync. |
| **Sync key** | Shown hidden; use the eye to show it and the copy button. Type the same key on every PC. |
| **Use the other PC's key** | Paste a key from another PC. |
| **New key** | Makes a new key. Your other PCs stop syncing until they get the new key. |

### How your PCs reach each other

| Setting | What it does | Default |
|---|---|---|
| **Directly, on the same network** | Finds PCs on the network. | On |
| **Connect from anywhere with Tailscale** | Also reaches PCs over Tailscale, wherever they are. The line below shows whether Tailscale is not installed, not connected, or which of your other PCs are on it (with **Get Tailscale** / **Open Tailscale**). | On |
| **Other PC's address** | Only if they do not find each other: a name or `host:port`, for example `LAPTOP` or `192.168.1.20`. | empty |
| **Catch up through a cloud folder** | Syncs through a folder that OneDrive, Google Drive, Dropbox or similar keeps in sync, when PCs are never on the same network. Choose the folder (**Use OneDrive** or **Choose...**). Everything inside is encrypted and each PC writes only its own files, so the cloud service never sees a conflict. If the switch is on and no folder is chosen the page tells you. | Off |

### What to sync

| Setting | What it does | Default |
|---|---|---|
| **Sessions and conversation history** | Sync sessions. | On |
| **Project memory** | Sync project memory files. | On |
| **Settings and extensions** | Sync settings, skills and plugins, and add-on server lists. | On |
| **Project files** | Keep each project's folder the same on your PCs, without `.git` and build output. Never copies a folder over 40,000 files or 3 GB, a drive or your user folder. Deleted files go to the trash folder on the other PCs, and switching it off deletes nothing. A project stops copying when its drive has under 2 GB free. | Off |
| **Include build folders** | Also copy build output (target, node_modules, .venv...). Can be several GB; rebuilding is usually quicker. Not copied between an ARM and an Intel/AMD PC. | Off |
| **Find programs missing on this PC** | The Programs card. | On |
| **Check every** | 10 seconds, 20 seconds, a minute or 5 minutes. | 20 seconds |

What stays private: sign-ins and per-PC files never sync. Per-PC project settings kept in `settings.local.json` also stay on each PC.

### Workspace client

| Setting | What it does | Default |
|---|---|---|
| **Prevent editing the same session on two PCs** | The session-lock hook: messages in a session open on another PC are stopped. Close it there, then resume here. | On |
| **Identify this PC in each session** | Tells the client which PC it is running on, so it cannot mix up hardware or paths. | On |

The bottom of the tab shows the session folder, the ports (UDP 47835, TCP 47836) and a **Data folder** button.

---

## Log tab

Recent activity of Workspace Sync (also copied into Deck's main log at debug level).

---

## Recommended setup

1. Switch on Workspace Sync on both PCs.
2. Copy the sync key from the first PC's Settings › Connections into **Use the other PC's key** on the second.
3. If they are on the same network they appear on the Status tab within a minute. Otherwise use Tailscale or a cloud folder.
4. Leave Sessions, Memory and Settings on. Turn on **Project files** only for the projects you really move between PCs (use **Sync this project** and **Its files** per project).
5. Close a session on one PC before continuing it on the other. Keep the session lock on.
6. Check the Status tab for "Changes need review" after changing settings on another PC.

## Troubleshooting

**The other PC does not appear.** Same sync key? Workspace Sync on in both? Network or Tailscale reachable? Try **Other PC's address**. The Status tab's "Away from home" fact tells you whether Tailscale is used.

**"runs an older Deck".** Update Deck on the PC named so both use matching versions.

**Changes are waiting for review.** Press **Apply** or **Keep this PC's** on the Status tab.

**A session shows "open on <PC>".** It is open there. Close it there and resume it here, or use **Take over** knowing you may get two copies.

**A project's files do not arrive.** Check Project files is on, **Sync this project** and **Its files** are on, the folder was kept or moved (not just guessed), the project is not over the size limits, and its drive has at least 2 GB free.

**The cloud folder is not catching up.** Choose a folder that the cloud app really syncs, use the same one on every PC, and give the cloud app time to upload.

**"The standalone sync app is running here".** Close the standalone app (tray icon > Exit) before switching on.

## FAQ

**Does this send my data to a server?** No server of Deck's. Data goes directly between your PCs (network or Tailscale), or through a folder in your own cloud storage, encrypted with your key.

**Can a stranger use my key?** Anyone with the key can sync with your PCs, which is why changes that could run a program wait for your approval, and why you should use **New key** if the key leaks.

**Does it change my files?** It writes synced files into the workspace client's folder and, if enabled, project folders, and adds the two hooks described above. Deleted files go to a trash folder you can recover from; switching Project files off deletes nothing.

**Is it safe with anti-cheat?** It does not touch games.
