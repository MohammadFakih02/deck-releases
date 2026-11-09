# Drives and disk space

This page covers everything about your storage:

- **Drives** (Watch > Drives): the health of every hard drive and SSD, how much you have written to it, its temperature, optional warnings, a drive speed test, and a way to copy your important folders off a drive that is failing.
- **Disk space** (Clean > Disk space): a map of what fills a drive, with tools to find duplicates, see what grew, and plan how to free a given amount of space.

Drive health needs Deck to run as administrator. Disk space works without it, but scans a whole NTFS drive much faster with it.

---

# Part 1: Drives (drive health)

Find it under **Watch > Drives**. The page title line says "Deck checks drive health every 10 minutes", or "N drive(s) need attention" if any drive is in trouble. Buttons at the top: **Check drives** (reads every drive again now), **Disk space** (jumps to the disk map) and the **?** help.

Deck reads each drive's own health data (S.M.A.R.T.) the way tools such as CrystalDiskInfo do: the NVMe health log for NVMe SSDs, and the attribute and threshold tables for SATA drives. It uses standard commands that Windows passes through to the drive, with no vendor driver.

## Drive health warnings

The switch is **Drive health** in **Settings › Notifications**. While it is off, the Drives page says so at the top, with a button to that setting.

- **Default: off.**
- When on, Deck compares each drive with its last check. If something got **worse** (a new bad sector, new read errors, falling life, a worse verdict), it shows one notification with a sound that stays until you dismiss it, and a **Show** button that opens this page. Each worsening is reported once.
- It also tells you once about a drive that is already in trouble the first time Deck sees it, and once about an old warning that is "healthy now" (a drive that went past a limit in the past but is fine today).
- The checks themselves always run and are saved, so turning the switch on later does not bring up old news.

**Recommended:** turn it on. A drive often shows trouble weeks before it fails, and a one-off notification costs nothing.

## The drive cards

Each drive gets a card, sorted worst first (Bad, Caution, Good, then drives without data). A drive that needs attention has a highlighted card.

| Part of the card | Meaning |
|---|---|
| Name | The drive's model. |
| Verdict chip | **Good**, **Caution**, **Bad** or **No health data**. For SSDs it adds "NN% life remaining" when the drive reports it. |
| Second line | The bus (NVMe, SATA, USB...), SSD or Hard drive, and the Windows disk number. |
| **Capacity**, **Temperature**, **Power on** | Size, current temperature, and total hours switched on. |
| Reasons | A bulleted list of why the verdict is not Good, in plain words. |
| **Earlier warning (fine now)** | A limit the drive went past once, but which it is within today. History, not a warning. |

### How the verdict is decided

**Bad** means something serious:

- The drive's own health check failed, or an attribute is past its failure limit right now (SATA).
- NVMe: the drive reports degraded reliability, has switched itself to read-only, or its spare blocks have fallen below the drive's own limit.

**Caution** means act soon, with no emergency:

- Reallocated sectors (worn spots the drive replaced), sectors waiting to be reallocated, or sectors that could not be read (SATA).
- Data errors the drive could not correct (NVMe media errors).
- 90% or more of an SSD's rated life used, or 10% or less left.
- NVMe power-loss protection failed, or the drive reports it is too hot.

**Good** means none of the above. **No health data** means the drive's controller does not pass its health data to Windows. USB enclosures usually hide it.

When a card shows a Caution or Bad reason, back up your important files and check the drive with its maker's diagnostic tool.

### Drives that are asleep

To avoid waking a sleeping hard drive, Deck asks Windows for the drive's power state first. A sleeping drive (or one whose state Windows will not report) is skipped, and the card says "Drive asleep" or "Power state unavailable" with how long ago the last reading was. Check again while the drive is in use.

### Drives behind a USB adapter

Health data passed through a USB bridge can be wrong. For these drives Deck says so on the card, and waits for a **second** unhealthy reading before it alerts you. Confirm any warning with the maker's tool.

## Health details

Open the **Health details** fold of a card for:

- **Starts**, **Written**, **Read**, **Unsafe shutdowns**, **Media errors** and **Bad sectors**, where the drive reports them.
- The **Endurance and temperature history** fold (below).
- For SATA drives, the raw attribute table: **ID**, **Attribute**, **Value**, **Worst**, **Fail below** and **Raw**. A row is marked when the value has fallen to the failure limit. The table is for reading along with the maker's documentation.

### Endurance and temperature history

| Item | Meaning |
|---|---|
| **Written** | Total data written to the drive in its life, in terabytes. |
| **Rated endurance** | The maker's TBW rating: how much the drive is rated to write. Deck fills in a typical value for a few common SSD families (certain Samsung 970 EVO, 970 EVO Plus, 980 PRO and 870 EVO, and WD Black SN850 and SN770 sizes); otherwise type your drive's TBW from its datasheet. |
| **Time to rated endurance** | An estimate, at the rate you have been writing, of how many years until you reach the rating. It needs a rating and at least a day of recorded, rising write totals, and is dropped if the drive's counter ever resets. |

TBW is the rated write total, not a failure forecast: many drives last well beyond it.

The form under it has two fields:

- **Rated endurance (TBW)**: 1 to 100,000.
- **Temperature alert (C)**: 20 to 100. When the drive reaches this temperature, Deck shows a notification ("Improve airflow and check it on the Drives page"). It fires when the drive rises to the limit, not on every reading. Leave it blank for **off** (the default).

Press **Save drive settings** to keep them. Below the form is a **graph of the temperature** Deck has recorded, with the time range and the number of readings. Deck keeps up to about a month of readings for each drive. It shows "Temperature history appears after another reading" until there are two readings.

For drives in Caution or Bad, a **Plan a verified copy** button appears here (see below).

## Drive speed test

A panel at the bottom measures how fast a drive really is. It writes a temporary file on the chosen drive, so it is only for when you want to know.

| Control | What it does |
|---|---|
| **Volume** | Which drive letter to test, with free space and the Windows disk number. |
| **Test size** | 64 MB up to 8 GB. Default 1 GB. |
| **Runs (best kept)** | 1 to 9 passes of each workload; the best result of each is shown. Default 3. |
| **Start speed test** / **Cancel test** | Run or stop. |

A line under the controls says the most data the test will write for the current settings. Big repeated tests wear SSDs, so keep it small unless you need the detail. A test larger than 1 GB asks you to confirm first. Each pass stops at 60 seconds, and the whole test at 30 minutes.

It runs four workloads, each for reading and for writing:

| Workload | Reads as |
|---|---|
| **SEQ1M Q8T1** | Big sequential transfers (copying large files), with a queue of 8. The "headline" speed. |
| **SEQ1M Q1T1** | The same with no queue: a single large transfer. |
| **RND4K Q32T1** | Many small random reads and writes at once (a busy system). |
| **RND4K Q1T1** | Small random access one at a time: how fast the PC feels for everyday use. |

Results are in MB/s and IOPS (operations per second). The latest result is shown in a table; earlier tests are kept (up to 100) under **Earlier tests**.

Safety and limits:

- The test file lives in a **Deck** folder at the root of the tested drive and is deleted when the test finishes or you cancel.
- You need free space equal to the test size plus 1 GB.
- It **refuses to start**, and stops if running, when a game is in front, so it never competes with a game.
- It will not follow folder links to another drive.
- Close games and other heavy disk activity first for a fair result. Results on a drive that is nearly full or very hot will be lower.

## Verified copy

If a drive's verdict is Caution or Bad, **Plan a verified copy** opens the **Drive evacuation plan**. It copies your important folders to a different drive and *proves* the copies are good, so you do not trust a failing drive with the only copy.

1. The plan lists the volumes on that drive, then the **games installed** on it and **your personal folders** on it. Tick the folders to copy.
2. Choose a **Destination drive** from the volumes on a *different physical drive* (so the copy survives the first drive failing).
3. Press **Copy and verify selected folders**.

What happens:

- Deck copies the files into a new folder on the destination called `Deck copies\verified-<code>`, one numbered subfolder per source folder.
- Every file is hashed while it is read, then the copy is read back and hashed again; the two must match, or the copy stops with a message.
- **The source is never changed or deleted.** You decide later what to do with the original.
- Progress shows at the bottom of the Drives page ("Verified folder copy: Copying and verifying", bytes and files verified), with a **Cancel copy** button. A cancelled copy leaves a partial folder for you to review or delete.

Limits and refusals (the message tells you which): you can choose 1 to 100 folders; the destination needs the folders' total size plus 1 GB free; a copy stops after one hour; the source and destination must be on different physical drives; Windows' own folders cannot be chosen; and folders containing links or **online-only** (cloud) files are refused, as are folders that contain each other or very large trees (over about 250,000 files and folders).

---

# Part 2: Disk space

Find it under **Clean > Disk space**. It answers "what is filling my drive?" with a map and a folder list, and lets you send big things to the Recycle Bin.

## Scanning

The page opens on a card per drive (with used space; **Almost full** appears above 90% used, and turns red above 95%) and a card **A folder...** to scan just one folder. Click a card to scan it. A progress card shows files found, bytes and seconds, with **Stop**.

- **NTFS drives** are read straight from the drive's file table (the Master File Table), which takes seconds even for a very large drive. This needs administrator rights.
- Other drives (exFAT, network drives), single folders, and any scan without admin rights are listed folder by folder, which is slower. A note under the breadcrumb says which method was used and, if it fell back, why.

A summary card shows the space used on the scanned root and free space.

## The explorer

After a scan you get:

- **Breadcrumbs** and the number of files and folders, plus **Scan again** and **Other drives** (back to the drive cards; your scan is kept).
- **Up** and **Root** buttons (Backspace also goes up).
- A **folder list** with **Name**, **% of parent**, **Size**, **Files** and **Folders**. Click the arrow to open a folder in place.
- A **file types** table beside it, biggest first, in the same colours as the map.
- A **treemap**: every file and folder as a rectangle sized by how much space it takes, nested like the folder tree. Hover for the name and size. One click selects the item and finds it in the list; a double-click opens a folder (or shows a file in Explorer).
- A **selection bar** under the list for whatever you selected: its path and size, **Space on disk** (for a file), **Show in Explorer**, **Open** (for a folder) and **Recycle**.
- **Biggest files on this scan**: the top 25 files, each with Show in Explorer and Recycle.

### Recycling

**Recycle** moves the item to the Recycle Bin after you confirm, and tells you how big it is. You can restore it from the Recycle Bin; space is only freed when the bin is emptied (or use [Clean up](cleanup.md), which can empty it). If something is too big for the bin, Windows asks before deleting it for good.

**Windows' own files are locked.** Deck refuses to recycle drive roots, the Windows folder, Program Files, ProgramData, the Users and profile folders themselves, and system files at the root of a drive (pagefile, hibernation file, recovery and boot data, System Volume Information). These show a padlock instead of a Recycle button. Deck also follows folder links to the real location first, so a link cannot be used to reach Windows' files, and it only removes what your own account would be allowed to delete.

## Disk tools

A panel above the map (after a scan) has three tools. None of them changes anything until you confirm each step.

### Find duplicate files

Looks for files with identical contents in the scan. It groups files by size, then compares fingerprints, then the full contents, so only truly identical files are listed. Links, protected Windows files and online-only (cloud) files are skipped. Results show "N copies, SIZE each" per group; the check is capped at 250,000 files and 500 groups, and at 10 minutes. **Cancel duplicate check** stops it.

Tick copies to act on them:

- **Measure selected space** shows the logical size, the size on disk (counting unique files only) and how much space would actually be freed if you permanently deleted them.
- **Recycle selected copies** moves them to the Recycle Bin. Deck makes you keep at least one copy of each group.
- **Link to first copy** replaces a duplicate with a hardlink to the first copy, so both names share one file and the space is saved. Edits show in both names. Deck keeps the original as a backup, tells you where, and offers to move it to the Recycle Bin once you are happy.

### What grew since last scan

Compares this scan with the last saved scan of the same drive or folder and lists the folders that grew or shrank (with the change and the size now). Folder totals include subfolders, so do not add rows together. The first scan has nothing to compare with; scan again later. If some folders could not be read, Deck says the changes may be off and keeps the last complete scan as the baseline.

### Space plan

Type **Space to make (GB)** and press **Build a space plan**. Deck builds a suggested list that adds up to your goal, starting with the least disruptive:

1. The safe [Clean up](cleanup.md) categories (caches and reports Windows and apps rebuild by themselves).
2. The Clean up categories that cost you time to rebuild (shader caches, game crash dumps, old installers, developer caches).
3. Apps you could remove (from [Apps](apps.md)), with their reported sizes.
4. Large files (100 MB and over) in the scan that are not part of an app or a cache.

Within each step the biggest items come first. Each line has a **Review** button that opens the right place: the Clean up page, the app's uninstall, or a window for the file with **Keep file**, **Show in Explorer** and **Move file to Recycle Bin**. Nothing is removed by the plan itself. If the suggestions do not reach your goal, scan more folders or measure Clean up again.

---

## Recommended setup

- Turn on **Drive health** in Settings › Notifications and leave Deck running with administrator rights.
- Enter the TBW from your SSD's datasheet if Deck did not know it, and set a **Temperature alert** around 70 C for an SSD you want to watch.
- Scan your system drive with **Disk space** every few months. Use **Find duplicate files** and the **Space plan** before buying more storage.
- Use the **Drive speed test** after installing a new drive or when a drive feels slow. A small size (256 MB to 1 GB) is enough.
- **Laptops** with one NVMe drive: the Drives page is the only warning you will get before data loss. Keep a backup anyway.

---

## Troubleshooting

**"No drives could be read".** Drive health needs administrator rights. Set Deck up as described in [Getting started](getting-started.md).

**A drive shows "No health data".** The drive is behind a USB enclosure or a RAID controller that does not pass S.M.A.R.T. through, or the drive is an unusual model. This is not a fault of the drive.

**The health figures did not change.** Deck re-reads every 10 minutes, and a sleeping hard drive is left alone. Press **Check drives**.

**My drive says Caution but works fine.** Caution means the drive reported something (for example a handful of reallocated sectors). Many such drives run for years, but treat the data as at risk: back it up and watch whether the number grows.

**The speed test will not start.** A game is in front, there is not enough free space (test size plus 1 GB), or the volume cannot do aligned 4 KB tests. The message says which.

**The scan of an NTFS drive is slow.** Without administrator rights Deck cannot read the file table and falls back to the slow method.

**Disk space and Windows' own numbers differ.** Deck shows file sizes as the drive lists them. **Space on disk** and **Measure selected space** show the size on disk, which also counts the slack space each file wastes.

---

## FAQ

**Does Deck write to my drive during the health checks?** No. Health reading is read-only. Only the speed test (a temporary file you start) and the verified copy (to a folder you choose) write.

**Does the speed test wear out my SSD?** Any write wears an SSD slightly. The default test (1 GB, 3 runs) can write up to about 13 GB, which is a small fraction of a modern SSD's rated endurance. Avoid running 8 GB tests with many runs again and again.

**Is anything uploaded?** No. Drive health, the speed test results, the temperature history and the scan comparisons stay in Deck's data folder on your PC.

**Does Deck delete anything for me in Disk space?** Only what you click Recycle on, and only to the Recycle Bin. The duplicate **Link to first copy** keeps a backup of the original.

**Will the verified copy delete my original?** Never. It only reads the source.

**Where are the records kept?** Drive health checks in `drive-health.json` and speed tests, ratings and temperature history in `drive-history.json`, both under `%APPDATA%\Deck`.
