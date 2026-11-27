Where to find it: PC status › Processes

# Processes

See every running program grouped by app, end a stuck one, and check whether a program file is safe.

It does the job of Task Manager's first tab, with a short "what is this?" for each program and optional safety checks. **Task Manager** at the top opens Windows' own.

## Right now

The **Right now** card sums up the latest processor and memory values in at most four findings. **Seen** describes a measured value; **Possible** is an indirect sign, not a cause. It changes nothing.

| Finding | When |
| --- | --- |
| A program "is using N % of the processor" | One program uses 25 % or more of the whole processor. |
| "Memory is N % full" | Memory is 90 % full or more, with its biggest user. A program using 25 % of memory is named too. |
| A program on the graphics card or the disk | 50 % or more of the graphics card, or 50 MB/s or more on disk. |
| "Several background programs are busy at once" (Possible) | Three or more programs without a window each use 5 % or more. Links to [Startup apps](startup.md). |
| "Windows may be moving memory to disk" (Possible) | Memory is full and the disk moves 100 MB/s or more. Links to Resource Monitor. |

With nothing to report it says **Nothing stands out: no program is using an unusual share of the processor or memory**. A finding about a program has **Select**, which picks it in the list. The row under the findings opens **Startup apps**, **Resource Monitor** and **Reliability history**. **Earlier (N)** shows the slow moments Deck kept while the page was open (the last 24, on this PC only); **Forget** clears them.

## The lists

**Running apps** have a window; **Background processes** are everything else (services, helpers, updaters). Programs are grouped: Chrome with twenty helpers is one row. Rows show the program's own name (such as "Steam Client WebHelper"); hover it for the file name. Helpers a running app started sit under that app.

| Column | Meaning |
| --- | --- |
| **Program** | Name and icon, the number of processes, or **Not responding**. |
| **CPU** | Share of the whole processor (all cores). |
| **Memory** | Memory the program holds. |
| **Network** | Download and upload speed now. Needs administrator. |
| **GPU** | Share of the graphics card, counted like Task Manager. |
| **Disk** | Reads and writes together, per second. |

Click a column heading to sort (default: **Memory**, biggest first). A dash means no data yet; "n/a" means Windows has no such counter on this PC. **Filter this list** narrows both lists by name or window title. The page refreshes automatically and pauses while you click.

## Selected app

Click a row to see it under **Selected app**: its window title, a one-line "what is this?", CPU and memory, its **Safety** results and its **Program file**. **Check for viruses** checks this one program (see [Check a file](#check-a-file-once)).

A program with several processes lists them under **Processes (N)**, each with **End process**, so you can end one stuck helper. That can leave the program half-working.

## Ending a program

1. Select the program.
2. Press **End task** (or **End task (N processes)**).
3. Confirm.

Like Task Manager's End task, the program gets no chance to save. Windows' core programs and any process Windows marks critical can't be ended here: they say **Part of Windows: not ended here**. Deck itself says **Deck itself: not ended here**.

## Check program files

The **Check program files** card runs up to four checks on every program file in the list. Under **Scan all N files**, press a check's tile; **Stop checks** stops it. Nothing is ever deleted, quarantined or changed. Each file is checked once, even if several rows run from it.

| Check | What it checks | What leaves your PC |
| --- | --- | --- |
| **Signatures** | Who signed each program. Malware rarely has a valid signature. | Nothing |
| **AV engines** | What share of antivirus engines flag the file (Team Cymru's registry). | Only a fingerprint |
| **Defender** | Microsoft Defender scans each file and only reports. | Nothing |
| **VirusTotal** | Looks the file up on VirusTotal. | Only a fingerprint. Needs your own free key. |

**Add VirusTotal key**: paste a free key from virustotal.com (profile, then API key). It stays on your PC. The free key allows about four lookups a minute. Without it the tile says **Needs a key**.

### Reading the results

| Chip | Meaning |
| --- | --- |
| Signed by a publisher | Validly signed. |
| **Unsigned** | Nobody signed it. Common for small tools; weigh the other checks. |
| **Bad sig** | Signed, but the file changed after signing or the certificate isn't trusted. Take it seriously. |
| AV 0 % / AV 12 % | Share of antivirus engines that flag it. 0 % means not known as malware. |
| **Def ✓** / Def: a threat name / **Def ?** | Defender found nothing / found something / couldn't scan it. |
| VT 0/70 | VirusTotal engines that call it malicious. Click for the report. **VT ?** means VirusTotal has never seen the file. |
| **Not checked for viruses yet** | No check since the file last changed. |

Results are kept per file fingerprint, so a file is checked again only when it changes. **Sort by safety** puts the most worrying results first. Windows kernel parts are checked through the kernel file they run from; a few rows have no file to scan.

### Check a file once

**Check a file…** (under **One file**) checks any file, for example a download you're unsure about:

1. Choose the file and the checks.
2. Press **Check**.
3. Read the result and the file's SHA-256 fingerprint.

Nothing about the file is saved, not even its path or result.

## Requirements

- The lists, CPU, memory, GPU, Disk and End task need nothing special. GPU and Disk are measured only while this page is open.
- The **Network** column needs administrator. It uses Windows' own network events, with no extra driver.
- Without administrator, Windows hides the file of some system programs, so they can't be checked.
- AV engines and VirusTotal need internet. Signatures and Defender work offline.

## Troubleshooting

**Network shows dashes.** Deck isn't running as administrator, or it is still measuring. See [Getting started](getting-started.md#why-deck-needs-administrator).

**A program I ended came back.** Something restarts it (a service, a startup entry, an updater). Look on [Startup apps](startup.md).

**Not responding, but it's just busy.** A program doing heavy work can look like this for a while. Give it time before you end it.

**Unsigned, but I trust the program.** Many small tools and game helpers are unsigned. Look at the other checks and where you got it.

## FAQ

**Does Deck read or change games' memory?** No. It reads the same process list as Task Manager and is safe with anti-cheat.

**Is sending a fingerprint safe?** A fingerprint is a short code computed from the file; it can't be turned back into the file. Deck never uploads a file.

**Why do numbers differ a little from Task Manager?** Deck adds all of a program's processes into one row, and the two read at different moments.

**Where are results kept?** In a small file in Deck's data folder, keyed by fingerprint. **Check a file…** results are never saved.
