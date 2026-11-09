# Processes

The **Processes** page shows every program running on your PC, grouped by app, with how much processor and memory each one uses. You can end a stuck program from here, and you can ask Deck to check whether a program file is safe: who signed it, whether antivirus engines flag it, and what Microsoft Defender says.

Find it under **Watch > Processes** in the sidebar. It is a single page with no tabs.

> It does the same job as the first tab of Windows' Task Manager, with two additions: a one-line "what is this?" for each program and the optional safety checks. The **Task Manager** button at the top opens the real Task Manager if you want it.

---

## What the page shows

### The top bar

| Control | What it does |
|---|---|
| **CPU** and **Memory** figures | The whole PC's processor load and memory in use right now. |
| **Filter apps** box | Type part of a program's name (or its window title) to narrow both lists. A note beside it says how many programs match, for example "3 of 120 programs match". |
| **Task Manager** | Opens Windows' own Task Manager. |

The page refreshes by itself while you look at it. It pauses while you are in the middle of clicking something, so a row does not jump away from under your mouse.

### Running apps and Background processes

Deck splits the list the way Task Manager does:

- **Running apps** are programs that have a window.
- **Background processes** are everything else: services, helpers, updaters, drivers' companion programs.

Both lists are grouped by program. Chrome with twenty helper processes is one row, "Chrome", with a note saying "20 processes". Each row shows:

| Column | Meaning |
|---|---|
| **Program** | The program's name and icon, with a second line: "N processes", **Not responding** (Windows says the program has hung), or **Protected by Windows**. Click the name to select the row. |
| **CPU** | The program's share of the *whole* processor (all cores together), with a small bar. 100% would mean every core fully busy. |
| **Memory** | The memory the program holds, with a bar scaled to your total memory. |
| **Network** | Download (down arrow) and upload (up arrow) speed for that program right now. It shows a dash while Deck is still measuring, or if Deck is not running as administrator (see [Requirements](#requirements)). |

Click a column heading (**Program**, **CPU**, **Memory**, **Network**) to sort by it. The default is **Memory**, biggest first.

### The selected app

Click a row and the panel on the right shows that program:

- Its window title (for apps with a window).
- A one-line **"what is this?"**. Deck has a built-in list of common Windows and driver programs. For anything else it reads the description stored inside the program file itself.
- CPU and memory.
- Its safety result (see below).
- **Scan file**: runs the safety checks on this one program (see [Check a file](#check-a-file-once)).
- **End app**: ends the program. If it has several processes the button says **End app (N processes)**. You are asked to confirm first, and told that unsaved work may be lost. Protected programs show a **Protected by Windows** chip instead of the button.
- A **File and check results** fold with the full path of the program file (or a note that none could be read) and the check chips again.

If the selected program has more than one process, a **Processes inside <name>** panel appears with a **Show N processes** button. It lists each process with its PID, CPU and memory, and an **End** button for each, so you can end one stuck helper without ending the whole program. Ending a single process of a program can leave the program half-working; Deck warns you of that in the confirmation.

---

## Ending a program

1. Select the program.
2. Click **End app** (or **End** next to one process inside it).
3. Read the question and confirm.

Deck asks Windows to end the program. This is the same as "End task" in Task Manager: the program gets no chance to save. Save your work first.

### What Deck will not end

Some programs are protected, because ending them would crash Windows or leave you without a desktop. A protected row has a lock instead of an End button. Protected means:

- A list of Windows' core programs: for example the System process, the service host (svchost), the window manager, the session and logon programs, the audio and print services, the Windows Defender engine, the Start menu and Explorer shell, and Deck itself.
- Any process that Windows has marked **critical** (ending it would cause a blue screen). Deck asks Windows directly. If Windows will not say whether a process is critical, Deck treats it as protected.

You can still end Explorer or other helper programs through Windows' own tools. Deck just does not offer it here.

---

## Check program files

Next to the lists is a panel called **Check program files**. It answers "is this program what it says it is?" with four optional checks. Each one runs on every program file in the list, one after the other, with a progress line and a **Stop** button. Nothing is ever deleted, quarantined or changed.

| Button | What it checks | What leaves your PC |
|---|---|---|
| **Signatures** | Who signed each program, according to Windows. Real software is nearly always signed by its publisher; malware rarely has a valid signature. | Nothing. |
| **AV engines** | Asks Team Cymru's Malware Hash Registry what share of antivirus engines flag the file. | Only the file's SHA-1 fingerprint, sent as a DNS lookup. No key needed. |
| **Defender** | Microsoft Defender scans each program file. Deck runs it so that it only reports; nothing is removed or changed. | Nothing. |
| **VirusTotal** | Looks the file up on VirusTotal by its fingerprint. | Only the file's SHA-256 fingerprint. Nothing is uploaded. Needs your own free VirusTotal key. |

A fold called **What each check sends** repeats this table inside the app.

### VirusTotal key

The **Add VirusTotal key** button opens a box where you paste your key (get a free one from virustotal.com: your profile, then API key). The key stays on your PC. Once saved the button reads **VirusTotal key ✓**, and you can replace or remove the key from the same box. The free key allows about four lookups a minute, so checking many programs with VirusTotal takes a while. Without a key the **VirusTotal** button is greyed out.

### Reading the results

Each result is a small chip in the row and in the selected-app panel:

| Chip | Meaning |
|---|---|
| A tick and a publisher name | Validly signed by that publisher. |
| **Unsigned** | Nobody signed the file. Common for small self-made tools and older programs; weigh it against the other checks. |
| **Bad sig** | Signed, but the signature does not hold: the file changed after signing, or the certificate is not trusted. Treat this one seriously. |
| **AV 0%** / **AV 12%** | The share of antivirus engines that flag the file. 0% means it is not known as malware. |
| **Def (tick)** / **Def: <threat name>** / **Def ?** | Defender found nothing / found something / could not scan the file. |
| **VT 0/70** | VirusTotal: how many of its engines call the file malicious. Click it to open the full report in your browser. **VT ?** means VirusTotal has never seen the file. |
| **File not scanned yet** | You have not run a check since this file last changed. |

Results are saved per file fingerprint on your PC, so a file is only checked again when it changes.

### Sort apps by safety

The **Sort apps by safety** button sorts the lists with the most worrying results first: a Defender detection counts most, then VirusTotal and antivirus-engine detections, then a bad signature, then no signature. Press it after running the checks to bring anything suspicious to the top. Click a column heading to go back to normal sorting.

### Programs that cannot be checked

A few rows show a dash and "can't be checked: no file to scan". These have no readable program file:

- Windows' kernel parts (System, Registry, Memory Compression, the idle process). Deck checks the Windows kernel file they run from instead, and marks them in the results. A file check cannot see a threat that lives only in memory.
- Programs Windows will not show Deck without administrator rights.

The line above the buttons also explains why "Check all N files" can be smaller than the number of rows: several rows can run from the same file, and each file is checked once.

### Check a file once

**Check a file...** (top right of the Check panel) and **Scan file** (in the selected-app panel) check one file privately. You pick the checks (VirusTotal only if you added a key), press **Check**, and see the result with the file's SHA-256 fingerprint and a copy button. **Nothing about the file is saved**: not its path, not its fingerprint, not the results. They live in memory while that window is open and are forgotten when you close it. This is the right tool for a download you are unsure about.

---

## Requirements

| Feature | Needs |
|---|---|
| The lists, CPU, memory, End | Nothing special. |
| **Network** column | Deck running as administrator. The speeds come from Windows' own kernel network events (the same source Task Manager uses), with no extra driver. The measuring only runs while the Processes page asks for it and stops about a minute after you leave. |
| Some file paths | Without administrator rights Windows hides the file of some system programs, so they cannot be scanned. |
| Safety checks | Internet for AV engines and VirusTotal. Signatures and Defender work offline. |

Most of Deck's pages work best with administrator rights, which Deck sets up once (see [Getting started](getting-started.md)).

---

## Recommended setup

- Leave the page on its defaults. Filter by name when you are hunting for a program.
- Run **Signatures** and **Defender** once after installing Deck or after installing a lot of new software. They cost nothing and send nothing.
- Add a VirusTotal key only if you want a second opinion on unfamiliar programs. A clean result from all four checks is good evidence, not a guarantee.
- For one suspicious download, use **Check a file...** instead of installing it first.

---

## Troubleshooting

**The Network column shows dashes.** Deck is not running as administrator, or it is still measuring (give it a few seconds). Open any hardware page and use **Set up**, or reinstall with the Deck installer, which sets up the admin start.

**A program has a lock and no End button.** It is protected (see above). If a normal program is locked, Windows has marked it critical. Close it from the program itself.

**I ended a program and it came back.** Something restarts it: a service, a startup entry, an updater. Look for it on [Startup apps](startup.md) and turn its startup entry off, or close it from its own settings.

**"Not responding" but the program is just busy.** Windows marks a program as not responding when its window stops answering. A program doing heavy work can look like this for a while, so give it a little time before you end it.

**The safety check says "Unsigned" for a program I trust.** Many small tools, older programs and games' helper files are unsigned. Look at the other three checks and where you got the program.

**VirusTotal says "VT ?".** VirusTotal has never seen that exact file. This is normal for very new, very rare or self-built programs.

**Defender says "Def ?".** Defender could not scan the file. The chip's tooltip gives the reason Defender reported.

---

## FAQ

**Does Deck read or change my games' memory?** No. The Processes page reads the same process list that Task Manager reads. It does not inject into any program and does not read any program's memory, so it is safe to use alongside anti-cheat.

**Is ending a game from here risky for my account?** Ending a process is an ordinary Windows action, the same as End task in Task Manager. Deck does not touch the game in any other way. A game that is closed in the middle of an online match may count as you leaving it, as it would with any other way of closing it.

**Is it safe to send a fingerprint to Team Cymru or VirusTotal?** A fingerprint is a short code computed from the file. It cannot be turned back into the file. Deck never uploads a file.

**Why do the numbers differ a little from Task Manager?** Deck shows each program's CPU as a share of the whole processor and adds up all of a program's processes into one row. The two tools also read at different moments, so small differences are normal.

**Do the checks slow my PC down?** Checking every file takes some disk and CPU while it runs. Press **Stop** at any time. Nothing runs in the background afterwards.

**Where are the results kept?** In a small file in Deck's data folder (`%APPDATA%\Deck`), keyed by file fingerprint. Results from **Check a file...** are never written there.
