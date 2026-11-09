# PC to PC

**PC to PC** sends files, folders, installers, apps and your Windows "look" between your own PCs. Both PCs run Deck. They find each other on your network, prove they share a pairing code, and talk over an encrypted channel. Nothing goes through a cloud service.

Find it at the bottom of the sidebar: **PC to PC**. The tabs are **Send**, **Activity**, **Share link**, **Apps**, **Copy my look** and **Settings**. A switch beside the page title turns the whole feature on or off. It is **on by default**.

Typical uses: moving a project folder to your laptop, sending an installer and having the other PC install it, copying the same list of apps to a new PC, handing a friend a download link, and waking a PC that is asleep so you can send to it.

---

## Getting two PCs to find each other

1. Install Deck on both PCs and leave **PC to PC** on.
2. On the first PC open **Settings › Connections › Pairing** (or just look at the empty Send tab) and copy **Pairing code** (twenty letters and digits, shown as `XXXX-XXXX-XXXX-XXXX-XXXX`).
3. On the other PC paste it under **Use the other PC's code** (also shown on the Send tab as "Code from the other PC" while no PC is found).
4. The PCs find each other. Each appears under **Recipient** with its name, address and "home network" or "Tailscale".

How they find each other: every PC broadcasts a small UDP beacon on the local network containing its name and a fingerprint of the pairing code. Only PCs with the same code recognise each other. Ports used: UDP 47833 and TCP 47834 (shown at the bottom of Settings). Windows Firewall must allow Deck on your private network.

If they do not find each other:

- Check both have **PC to PC** on and the same code.
- The PCs need to be on the same subnet. Guest Wi-Fi networks and some routers block device-to-device traffic.
- Use **Other PC's address** in Settings › Connections › Pairing: type the other PC's name or IP address (for example `LAPTOP` or `192.168.1.20`).
- Away from home, use [Tailscale](https://tailscale.com) (free) on both PCs with the same account. They then find each other over it. The Settings page and the "Looking for your other PC" card show Tailscale's state with **Get Tailscale** / **Open Tailscale**.

Each PC also has its own key, so PCs that share a pairing code are still told apart. Another device with the same code cannot pass for one of your PCs.

**Make a new code** replaces the code on this PC. The other PC stops finding it until you give it the new one.

---

## Tab: Send

The **Recipient** card lists the PCs found (select one). Each recipient has **Browse files**, which lists that PC's shared folders (see Settings) and lets you copy from them.

### Send to

| Control | What it does |
|---|---|
| **Choose files** | Pick files or installers to send. |
| **Choose a folder** | Pick a folder. Deck counts its files first and shows a card (see below). |
| **Install on arrival** | Tick it before sending an installer. The other PC will install it once its user accepts. Installers always wait for an Accept, even from a trusted PC. |
| Text box and **Send text** | Sends text or a link to the other PC. |

The other PC sees a notification and a card: "<PC> wants to send you <what>", with the number of files and size, and (if you open **What's in it**) the biggest files and the file types. If any file can start a program or script (exe, msi, bat, cmd, ps1, vbs, js, lnk, reg, dll and similar) a warning counts them. The receiver chooses **Accept**, **Decline**, or **Accept and trust <PC>...** for a week, a month, six months or always. Deck also checks the receiving drive has room, always leaving 100 MB free.

### Sending a folder

After you choose a folder a card shows what will go.

| Option | Meaning |
|---|---|
| **Skip build output** | Leaves out build and dependency folders listed in Settings (target, node_modules, .git and so on). Shows how many files and how much space were left out. On by default. |
| **Only send what's new or changed** | Skips files that are already identical on the other PC, so a second copy takes seconds. |
| **Delete files on the other PC that no longer exist here** | Makes the other PC's folder match this one. Needs you to tick **Yes, delete them**, and the other PC's user is asked first, with the number of files that would be deleted. |

Then press **Send**. If the destination folder already exists, Settings > **Folder conflicts** decides what happens.

### Transfers

Each transfer shows its direction, a progress bar, speed, time left and a final line ("Done: 2.1 GB in 40 s"). **Cancel** stops one. What already arrived stays on the other PC and **Carry on** sends only the rest. **Clear finished** tidies the list.

### Wake a PC

If a PC you have seen before is switched off or asleep and no longer answers, a **Wake a PC** panel appears under the Recipient card (on the Send, Apps and Copy my look tabs). Press **Wake** next to it and Deck sends a Wake-on-LAN "magic packet" to its network card. It can take a minute to start; press the bin to forget a PC.

Requirements:

- The PC must have **Wake-on-LAN** enabled in its BIOS/UEFI and in its network adapter's properties in Windows, and be connected by cable (Wi-Fi rarely supports it).
- It must be on your home network. Deck learned its hardware address from the network's address table when it was last seen, so the PC must have been seen on the home network at least once. PCs known only over Tailscale cannot be woken.
- Deck sends nothing until you press Wake. Up to 24 PCs are remembered.

---

## Tab: Activity

### Received

What arrived, newest first, with the sender, time, number of files and size. Depending on what it is:

| Button | When it shows |
|---|---|
| **Install** / **Install silently** | An installer. Silent works for Inno Setup, NSIS, Burn and MSI installers. |
| **Extract** | A zip file. |
| **Install these apps** (or **Retry failed**) | An apps list sent from the Apps tab. |
| **Apply setup...** and **Undo** | A "look" sent from Copy my look. |
| **Show files** | Opens the folder. |
| Bin | Deletes the files from this PC (asks first). |
| x | Removes the entry from the list only. |

**Open folder** opens the receive folder. Waiting offers and requests also appear as notifications and as cards on top of the page, with a counter "N waiting for you". A request from another PC ("wants to ...") declines by itself after a countdown.

### Activity log

The recent log of what PC to PC did.

---

## Tab: Share link

For someone who is not one of your PCs. You get a link they open in any browser; nobody needs Deck.

| Option | Choices | Default |
|---|---|---|
| **Link works for** | 1 hour, 1 day, 7 days | 1 day |
| **Downloads** | **Once** or **Until it ends** | Once |
| **Over the internet (Tailscale Funnel)** | Off: this Wi-Fi only. On: reachable over the internet through Tailscale. | Off |

Press **Share a file** or **Share a folder** (a folder is zipped first). The result appears under **Open links** with a copy button for the link and its size, remaining downloads and time left. **Stop** ends a link early.

Details:

- A small web server runs only while a link is open (port 47837) and serves only that file.
- A download that breaks off does not count against "Once".
- Links survive a restart of Deck.
- Internet links need Tailscale on this PC with Funnel allowed; if Tailscale asks for permission the page shows an **Allow Funnel** button. Funnel publishes only the share path and only while an internet link is open.
- Anyone who has the link can download the file, so send it only to the person it is for.

---

## Tab: Apps

Sends a list of the apps installed on this PC so another PC can install them. Deck reads the installed apps through winget (it takes a few seconds the first time; **Rescan** reads again). Only the list of package IDs is sent. The other PC installs each one itself with winget, skipping what it already has.

- Search the list, tick apps (**Select all shown**, **Select none**), and press **Send N apps to <PC>**.
- Apps are grouped: Everyday apps, Creative tools, System tools, Development, Runtimes and system parts, More installed apps. **Show runtimes and system parts** reveals the runtimes.
- On the other PC they appear in Activity as an apps list with **Install these apps**.
- Apps winget does not know can still be sent as installer files from the Send tab.

Requires winget (App Installer) on both PCs.

---

## Tab: Copy my look

Sends this PC's appearance to another PC. Choose what to copy:

| Item | What it covers |
|---|---|
| **Windows look and feel** | Theme, accent colour, taskbar, Explorer settings and Maintenance tweaks (see [Tweaks](tweaks.md)). No drivers. |
| **Wallpaper** | The desktop picture. |
| **Windhawk mods** | The Windhawk mods and their settings. Both PCs need the same Windhawk version; mods are only added or updated. Greyed out if Windhawk is not installed here. |

Press **Send look to <PC>**. On the other PC, **Apply setup...** (in Activity) shows what is inside and lets the user choose what to apply, including **Restart Explorer afterwards so the taskbar updates** (closes open folder windows). Windhawk is off unless ticked, because mods run inside other programs: only apply your own. **Undo** puts the previous settings back.

---

## PC to PC settings

These live in **Settings › Connections**, under the PC to PC switch, while PC to PC is on.

### This PC

| Setting | What it does |
|---|---|
| **Name the other PC sees** | The name shown to your other PCs. |
| **Save received files in** | The folder for received files. **Change...** picks another. |

### Receiving and trust

| Setting | What it does | Default |
|---|---|---|
| **Ask me before anything comes in** | Files wait for your Accept unless the sending PC is trusted. | On |

Installers always wait for your Accept, even from a trusted PC.

**Trusted PCs.** Each known PC has a drop-down: **Ask first**, or **Trust** for a week, a month, 6 months or always. Files from a trusted PC arrive without asking. Installs and deletions always ask. Trust is per PC and is tied to that PC's own key.

### Explorer

| Setting | What it does | Default |
|---|---|---|
| **"Send to PC" in the right-click menu** | Adds "Send to PC (Deck)" to Explorer's right-click menu, for this Windows account only. The entry lists your other PCs once Deck has seen one. | Off |

### Pairing

Pairing code, **Use the other PC's code**, **Other PC's address**, Tailscale state and **Make a new code** (see above).

### Shared folders

Folders your other PCs may browse and copy from (Send > Browse files). Nothing is shared until you **Add a folder**; the **x** stops sharing one. Under **Who may copy from this PC**, each known PC can be set to **Ask me each time**, **Always (trusted)** or **Never**.

### Excluded files

| Setting | What it does |
|---|---|
| **Skip build output when sending or copying a folder** | The default for the Send option of the same name. |
| **Skipped names** | A comma-separated list (default: target, node_modules, .git, __pycache__, *.pdb, *.obj, dist, build). A name matches any folder or file called that; `*.pdb` style patterns work. |

### Folder conflicts

**A received folder already exists:** **Merge (newer file wins)** (default), **Replace same-named files** or **Keep both (new folder)**.

### Workspace client

| Setting | What it does | Default |
|---|---|---|
| **Let the workspace client use PC to PC** | Installs a small instruction file so your workspace client can send things to your other PCs on request. The other PC still asks before anything comes in, unless it trusts this PC. Turning it off removes the file. | Off |

---

## Recommended setup

- Keep **Ask me before anything comes in** on. Use **Trust ... for a week** for a PC you are about to send a lot to, not "always".
- Turn on the Explorer right-click entry if you send often.
- Use Tailscale for PCs that are not on the same network.
- For a new PC: send **Apps** first, then **Copy my look**.
- Keep **Skip build output** on for project folders.

## Troubleshooting

**"Looking for your other PC" never ends.** Same pairing code on both? **PC to PC** on in both? Same network? Firewall? Try **Other PC's address**.

**The receiver never gets the offer.** The offer shows as a notification and a card on the receiving PC. If the receiver has not answered, the sender sees "Waiting for <PC> to accept...". A request declines by itself after a countdown.

**A transfer failed or was cancelled.** If part arrived, press **Carry on**. Only the rest is sent.

**Wake does nothing.** Check Wake-on-LAN in the BIOS and adapter settings, use a cable connection, and note the PC must have been seen on the home network.

**Installer did nothing on the other PC.** Accept it, then press **Install** (or **Install silently** for supported installers) in Activity. An installer that needs a restart says so.

**A share link says it is gone.** It expired, reached its download count, or you stopped it. Make a new one.

## FAQ

**Is it encrypted?** Yes. Every connection proves knowledge of the pairing code and is then encrypted with ChaCha20-Poly1305 using keys derived per connection. The code never travels.

**Does it send anything to the internet?** No, except share links you choose to publish through Tailscale Funnel.

**Can a PC on the same Wi-Fi without the code receive my files?** No. It cannot find or talk to your PCs without the code.

**What changes on my PC?** Received files go in the receive folder you chose. Installing, applying a setup or deleting files always needs you to confirm on the receiving PC. The Explorer entry and the workspace-client instruction file are added only if you switch them on, and removed when you switch them off.

**Is it safe with anti-cheat?** It does not touch games. Avoid large transfers during online matches only because they use bandwidth.
