Where to find it: Connections › PC to PC

# PC to PC

PC to PC sends files, folders, installers, apps and your Windows look between your own PCs, encrypted, with no cloud service in between.

Both PCs run Deck. The tabs are **Send**, **Transfers**, **Share link**, **Apps** and **Copy my settings**. Press **Turn on PC to PC** to start; the **PC to PC** switch in the tab row turns it off. On a new install it starts off; an update keeps your choice.

## Pair your PCs

1. Turn on PC to PC on both PCs.
2. On one PC, under **Copy this PC's code**, copy the code (twenty letters and digits, `XXXX-XXXX-XXXX-XXXX-XXXX`).
3. On the other PC, paste it under **Type the other PC's code**. One PC's code is enough; you don't swap both.
4. The PCs find each other and show under **Your PCs** with their name, address and "Tailscale" when found that way.

Once a PC is paired, **Pair another PC** folds away under **Pairing and network**.

If they don't find each other:

- Check both have PC to PC on and the same code.
- Both must be on the same network. Guest Wi-Fi and some routers block traffic between devices.
- Type the other PC's name or IP address in **Other PC's address** ([PC to PC settings](#pc-to-pc-settings) › **Pairing**).
- Away from home, install [Tailscale](https://tailscale.com) (free) on both PCs with the same account. The card shows **Get Tailscale**, **Open Tailscale** or **Signed in**.
- Windows Firewall must allow Deck on your private network. Ports: UDP 47833 and TCP 47834 (under **PC to PC details**).
- **Why isn't my PC listed?** runs read-only checks (PC to PC on, the firewall rule, the network profile, Tailscale). Each shows **OK**, **Needs fixing**, **Worth checking**, **Unknown** or **Note**, with a **Fix:** line where it helps.

**Refresh** announces this PC again and looks for the others. Each PC also has its own key, so another device with the same code can't pass for one of your PCs.

### Find on this network

**Look around** lists nearby phones, TVs, printers and other Deck PCs, even with PC to PC off. The type is only a hint. **Stop** or **Scan again** as needed. It pauses during games and stays off on a Public network (**This network blocks discovery (Public network)**). Nothing is saved.

A Deck PC in the list has **Pair**, which adds its address to your PCs. Nothing is trusted by it; the pairing code is still needed.

## Send

Pick the PC under **Your PCs**. **Browse files** lists that PC's shared folders so you can copy from them (**Copy to this PC**).

In the **Send to** card:

| Control | What it does |
|---|---|
| **Send files** | Pick files or installers. |
| **Send a folder** | Pick a folder. Deck counts its files first and shows the options below. |
| **Send clipboard** | Sends the clipboard text. The other PC shows it with a Copy button and never pastes it. |
| **Install on arrival** | Turn it on before sending an installer; the other PC installs it after its user accepts. |
| **Send text** | Sends the text or link you typed. |

Until a PC is paired the card says **Pair a PC above to send files, a folder or text.**

### Sending a folder

| Option | Meaning |
|---|---|
| **Skip build output** | Leaves out build and dependency folders (target, node_modules, .git and so on). On by default. |
| **Only send what's new or changed** | Skips files that are already the same on the other PC. |
| **Delete files on the other PC that no longer exist here** | Makes the other folder match. You also select **Yes, delete them**, and the other PC's user is asked first. |

Press **Send**. If the folder already exists there, **Folder conflicts** in settings decides what happens.

### What the other PC sees

A notification and a card: who sends what, how many files and how big, and a warning if any file can start a program or script. The receiver chooses **Accept**, **Decline**, or one of the **Trust** choices (accept and let your PC send without asking for a week, a month, six months or always). Installers always ask. Deck keeps 100 MB free on the receiving drive.

### Transfers

The **Transfers** card shows each transfer with its progress, speed and time left, then "Done: … in …". **Cancel** stops one; what arrived stays, and **Resume** sends only the rest. **Try again** sends a declined or failed transfer again. **Clear finished** tidies the list. An offer waits up to three minutes for an answer.

### Wake a PC

A PC you have seen before that no longer answers appears under **Offline PCs · Wake a PC**. **Wake** sends a Wake-on-LAN signal; it can take a minute to start, and Deck can't confirm it woke. The bin forgets the PC.

The PC needs Wake-on-LAN turned on in its BIOS and network adapter, usually a cable connection, and must have been seen on your home network once. PCs known only over Tailscale can't be woken.

**Wake on LAN** (under **Pairing and network**) holds **Wake readiness**: it checks this PC without changing anything.

- **Fast Startup**: when on, it can block wake after Shut down.
- **Windows wake details**: armed devices, the last wake source, wake timers and **Sender addresses** (each adapter's MAC and broadcast address).

## Transfers

- **Received**: what arrived, newest first. By kind: **Install** and **Install silently** (installers), **Extract** (zip files), **Install these apps** or **Install failed apps again** (an apps list), **Apply setup…** and **Undo** (a look from Copy my settings). **Open folder** opens it; the bin deletes the files (after asking); the cross removes the entry only.
- **Activity log**: what PC to PC did recently; **Show all** for more.

Offers waiting for you also show as notifications, a "waiting for you" chip, and cards on Send. A request from another PC declines automatically after a countdown.

## Share link

For someone who isn't one of your PCs: they download from a link in any browser.

| Option | Choices | Default |
|---|---|---|
| **Who** | **This Wi-Fi** (**Same Wi-Fi only**) or **Internet** (**Anyone with the link**, through Tailscale Funnel) | This Wi-Fi |
| **Works for** | 1 hour, 1 day, 7 days | 1 day |
| **Downloads** | **Once** or **Until expiry** | Once |

Press **Share a file** or **Share a folder** (folders are zipped). **Your shared links** lists each link with a copy button, downloads left and time left; **Stop sharing** ends one early.

- A small web server runs only while a link is open (port 47837) and serves only that file.
- A broken-off download doesn't count against "Once". Links survive a Deck restart.
- Internet links need Tailscale with Funnel allowed (**Allow Funnel** if Tailscale asks).
- Anyone with the link can download, so send it only to the person it is for.

## Apps

Sends the list of apps installed here so another PC can install them with winget. Only package IDs are sent; the other PC skips what it already has.

1. Pick the PC in **Send to**.
2. Search the list or turn on **Runtimes and system parts** to see those too. Apps are grouped (Everyday apps, Creative tools, System tools, Development, More installed apps).
3. Select apps (**Select all shown**, **Select none**) and press **Send N apps to** the PC.
4. On the other PC, press **Install these apps** in Transfers.

**Scan again** reads the installed apps again. Needs winget (App Installer) on both PCs. Apps winget doesn't know can go as installer files from Send.

## Copy my settings

Sends this PC's look. Pick the PC in **Send to**, then choose:

| Item | What it covers |
|---|---|
| **Windows look** | Theme, accent color, taskbar, Explorer settings and Windows tweaks ([Windows tweaks](tweaks.md)). No drivers. |
| **Wallpaper** | The desktop picture. |
| **Windhawk mods** | Windhawk mods and their settings. Both PCs need the same Windhawk version; mods are only added or updated. |

**Included mods (N)** lists each mod. Press **Send my look**. On the other PC, **Apply setup…** in Transfers lets the user choose what to apply, and **Restart Explorer afterwards so the taskbar updates (closes open folder windows)**. Windhawk is off unless selected, because mods run inside other programs: only apply your own. **Undo** restores the previous settings.

## PC to PC settings

They sit on the **Send** tab, in the **PC to PC settings** fold. **Manage trusted PCs** on a waiting offer opens it at **Trusted PCs**.

| Card | Settings |
|---|---|
| **This PC** | **Name the other PC sees**; **Save received files in** with **Change…**. |
| **Receiving** | **Ask me before anything comes in** (default on). Installers always ask. |
| **Trusted PCs** | Per PC: **Ask first** or **Trust** for a week, a month, 6 months or always. **Trusted size limit** (MB, default 1024, **No cap** possible): bigger transfers ask anyway. A program, installer, install or deletion always asks. A PC found over Tailscale has **Trust this PC** (6 months) in one click. |
| **LocalSend** | **Work with LocalSend** (see below). |
| **Explorer** | **"Send to PC" in the right-click menu**, for your Windows account only (default off). |
| **Pairing** | **Pairing code**, **Use the other PC's code**, **Other PC's address**, Tailscale, **Make a new code** (the other PC stops finding this one until it has the new code). |
| **Shared folders** | Folders your other PCs may browse. Nothing is shared until you **Add a folder**. **Who may copy from this PC**: **Ask me each time**, **Always (trusted)** or **Never** per PC. |
| **Excluded files** | **Skip program build folders** and **File and folder names to skip** (comma separated; `*.pdb` works). |
| **Folder conflicts** | **If a received folder already exists**: **Merge (newer file wins)** (default), **Replace same-named files** or **Keep both (new folder)**. |
| **From coding apps** | **Let the workspace client use PC to PC**: adds an instruction file so your coding tool can send to your other PCs; the other PC still asks first. Off removes the file. |

### Work with LocalSend

Off by default. When on, phones with the free LocalSend app (iPhones too) can send files and folders here. Deck asks before accepting (no answer in a minute means no), and files go to the From phone folder. The state reads **Off**, **On, listening on port 53317**, or **On, but not listening** when another program holds the port: close it, then turn the switch off and on. LocalSend traffic isn't encrypted (**Not encrypted: home only**), so leave it off on shared networks.

## Actions from the command line and links

`deck.exe --do <action>` runs one action from a fixed list in the running Deck, for shortcuts and Stream Deck buttons: `open:<page>`, `profile:cpu:<id>`, `profile:gpu:<id>`, `mic:toggle`, `volume:toggle`, `output:<id>`, `gamebar`, `awake:on`, `awake:off`, `lock`, `sleep`, `screen_off`. Anything else is refused.

`deck://do/<action>` links work the same once you turn on **Allow deck:// links**, but links never lock, sleep or turn off the screen.

The whole list is in **Settings › Connections › Outside actions**. Each row has **Copy command** and **Copy link**; actions links never run are marked **Not from links**. Pages and profiles are folded: press **Show** beside **CPU and GPU profiles** or **Open a page**.

`Deck.exe --pc-send <file> --to <PC name>` sends a file from a command window, which stays open until the transfer ends (closing it stops the transfer); `--pc-get` copies the other way. Add `--json` for machine-readable replies.

## Recommended setup

- Keep **Ask me before anything comes in** on. Trust a PC for a week when you are about to send a lot, not always.
- Turn on the Explorer right-click entry if you send often.
- Use Tailscale for PCs on different networks.
- For a new PC: send **Apps** first, then **Copy my settings**.

## Troubleshooting

**"Looking for your other PC…" never ends.** Same code on both? PC to PC on in both? Same network? Firewall? Try **Other PC's address** and **Why isn't my PC listed?**.

**The receiver never sees the offer.** It shows as a notification and a card there. The sender sees "Waiting for … to accept…".

**Accept was pressed, but the sender still waits.** After three minutes the sender stops. Allow Deck on the private network on both PCs and send again. The **Activity log** shows each step.

**The other PC runs an older Deck.** Update both. Too-old versions fail with an update message.

**A transfer stopped.** If part arrived, press **Resume**; otherwise **Try again**.

**Wake does nothing.** Check Wake-on-LAN in the BIOS and adapter settings, use a cable, and make sure the PC was seen on the home network.

**An installer did nothing.** Accept it, then press **Install** (or **Install silently**) in Transfers.

**A share link is gone.** It expired, used up its downloads, or was stopped. Make a new one.

## FAQ

**Is it encrypted?** Yes. Each connection proves it knows the pairing code, which never travels, and is then encrypted (ChaCha20-Poly1305).

**Does it send anything to the internet?** No, except internet share links through Tailscale Funnel.

**Can a PC on my Wi-Fi without the code get my files?** No.

**What changes on my PC?** Received files go to your receive folder. Installing, applying a setup or deleting files always needs a yes on the receiving PC. The Explorer entry and the coding-tool file are added only when you turn them on.

**Is it safe with anti-cheat?** It doesn't touch games. Avoid large transfers during online matches because they use bandwidth.
