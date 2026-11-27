Where to find it: PC status › Drive health

# Drive health and disk space

The health of every drive, a speed test and a verified copy on **Drive health**; what fills a drive and how to free space on **Disk space**.

Drive health needs administrator. Disk space works without it, but scans a whole NTFS drive much faster with it.

## Drive health

Where to find it: PC status › Drive health

Deck reads each drive's own health data (S.M.A.R.T.), as CrystalDiskInfo does, every 10 minutes. **Check drives** reads again now. Links at the top open **Clean up › Disk space** and the warning thresholds in Settings.

This is an early warning, not a clean bill of health: a drive can fail without one. Keep a backup even when it says Good.

### The drive cards

Cards are sorted worst first; a drive that needs attention is highlighted.

| Part | Meaning |
|---|---|
| Verdict | **Good**, **Caution**, **Bad** or **Unknown**, with life remaining for SSDs that report it. |
| Second line | The bus (NVMe, SATA, USB), **SSD** or **Hard drive**, and the Windows disk number. |
| **Used for** | Total hours switched on. "Not counted" means the drive reports zero hours despite clear use. |
| Reasons | Why the verdict isn't Good, in plain words. |
| **Earlier warning (fine now)** | A limit the drive passed once but is within today. History, not a warning. |

**Bad** means the drive's own check failed, an attribute is past its failure limit, or an NVMe drive reports degraded reliability, read-only mode or spare blocks below its limit.

**Caution** means act soon: reallocated, pending or unreadable sectors, uncorrectable errors, NVMe media errors, 90 % or more of rated life used, or the drive reports it is too hot.

**Unknown** means the controller doesn't pass health data to Windows. USB enclosures usually hide it.

With Caution or Bad, back up your files and check the drive with its maker's tool.

- Sleeping drives aren't woken. The card says "Drive asleep" or "Power state unavailable" with the last recorded data.
- Behind a USB adapter, data can be wrong; Deck waits for a second unhealthy check before alerting.
- **smartctl:** if Windows gets no data and you installed smartmontools yourself, Deck reads the drive with its `smartctl` (read only) and the card shows **from smartctl**. Deck never installs or bundles it.

### Drive details

- **Starts**, **Written**, **Read**, **Unsafe shutdowns**, **Media errors** and **Bad sectors**, where reported. Values the drive doesn't report are grouped in one chip.
- **Trend · 90 days**: changes in rated life used, spare, media errors, bad-sector counts and temperature between recorded days. It needs two days of data and never guesses a failure date.
- **SMART attributes** (SATA): **Attribute**, **Value**, **Worst**, **Fail below** and **Raw**. A row is marked when it reaches the failure limit.
- **Endurance**: **Written** total, **Rated endurance** (the maker's TBW; Deck knows it for a few common SSDs, otherwise type it from the datasheet) and **Time to rated endurance** at your write rate. TBW is a rating, not a failure forecast.
- **Rated endurance (TBW)** and **Temperature alert** fields, then **Save**. The alert fires once when the drive rises to the limit; blank means off.
- **Drive temperature chart** of up to about a month, with an alert chip when set.
- **Plan a verified copy** for drives in Caution or Bad.

### Drive health warnings

The switch is **Drive health** in Settings › Notifications. Off by default; the page says so with a button to it.

When on, Deck compares each drive with its last check and warns about any rise in reallocated, pending or uncorrectable sectors, rising NVMe media errors, low spare blocks, or a worse verdict. It also warns once about a drive already in trouble when first seen. Unchanged values don't repeat.

- **NVMe rated life used**: **No extra warning**, **80% (suggestion)** or **90% (suggestion)**.
- **NVMe available spare (%)**: warns below your value; blank uses the drive's limit.
- To get warnings on your phone, turn on **Drive warnings** in Sensors › Alerts (see [Alerts](alerts.md)).

### Drive speed test

Writes a temporary file on the chosen drive to measure its real speed.

| Control | What it does |
|---|---|
| Volume | The drive letter to test. |
| **Test size** | 64 MB to 8 GB. Default 1 GB. |
| **Runs** | 1 to 9 passes; the best is kept. Default 3. |
| **Start speed test** / **Cancel test** | Run or stop. |

A chip shows the most data the test writes. Tests over 1 GB ask first. The test refuses to start, and stops, while a game is in front. It needs free space of the test size plus 1 GB, and deletes its file when done.

| Workload | Reads as |
|---|---|
| SEQ1M Q8T1 | Large file copies, the headline speed. |
| SEQ1M Q1T1 | One large transfer. |
| RND4K Q32T1 | Many small reads and writes at once. |
| RND4K Q1T1 | Everyday responsiveness. |

Results show in MB/s and IOPS; up to 100 earlier tests are kept under **Earlier tests**.

### Verified copy

For a drive in Caution or Bad: **Plan a verified copy** opens the **Drive evacuation plan**, which copies your important folders to another drive and proves the copies match.

1. Select the folders: games installed on the drive and your personal folders.
2. Choose a **Destination drive** on a different physical drive.
3. Press **Copy and verify selected folders**.

Every file is hashed on read and checked again on the copy. The source is never changed. Copies go to `Deck copies\verified-<code>` on the destination; **Cancel copy** stops and leaves a partial folder. Up to 100 folders, one hour at most; Windows folders, cloud-only files and very large trees (over about 250,000 items) are refused.

## Disk space

Where to find it: Clean up › Disk space

### Scanning

Pick a drive card (**Almost full** shows above 90 % used) or **Scan a folder**. **Stop scan** ends it.

- NTFS drives are read from the drive's file table in seconds. This needs administrator.
- Other drives, single folders and scans without administrator go folder by folder, which is slower.

The summary shows the space used and **Free now**, read live from the drive. **Saved scans** lists kept scans, each with **Scan again**; **What grew** compares with them.

### The explorer

- Breadcrumbs, **Scan again**, **Up** and **Root** (Backspace goes up).
- A folder list with **Name**, size, files and folders.
- **File types**, biggest first, in the map's colors.
- A treemap: every file and folder sized by space, colored by type. **Small files** are lumped together. Click to select; double-click a folder to open it.
- For the selected item: **Space on disk**, **Show in Explorer**, **Open** and **Recycle**.
- **Biggest files on this scan**: the top 25.

**Recycle** moves an item to the Recycle Bin after you confirm. Space is freed when the bin is emptied (see [Clean up](cleanup.md)). Windows' own files show **Protected** and can't be recycled: drive roots, Windows, Program Files, ProgramData, user profile folders and system files.

### Disk tools

Below the explorer. They read files only when you ask, and stop while a game is in front. Nothing changes until you confirm.

**Find duplicate files** lists files with identical contents (size, then start and end, then the full contents). Hardlinks, protected files and cloud-only files are left out. Capped at 250,000 files and 500 groups. A group marked "Not fully compared" isn't confirmed; run again. **Cancel duplicate check** stops it. For the copies you select:

- **Measure selected space** shows what deleting them would really free.
- **Recycle selected copies** keeps at least one copy of each group.
- **Link to first copy** replaces a duplicate with a hardlink to the first copy and keeps the original as a backup you can recycle later.

**Find empty folders** lists folders with nothing in them. Folders in Windows, Program Files, ProgramData or AppData are never offered. **Review and move to Recycle Bin** lets you clear what to keep; each folder is checked again just before it moves.

**Find broken shortcuts** lists shortcuts whose target no longer exists. Shortcuts to apps, network places and unplugged drives are never listed.

**What grew since last scan** lists folders that grew or shrank since the last saved scan of the same place. Rows overlap, so don't add them up.

### Make room

Say how much free space you need ("I need 80 GB on D:") and press **Build a plan**. Deck shows **Free now**, **Still needed** and **Really freed**, and lists steps, least disruptive first:

1. Safe [Clean up](cleanup.md) categories.
2. Clean up categories that cost a rebuild (shader caches, old installers).
3. Apps you could remove (from [Apps](apps.md)).
4. Large files (100 MB and over) from the last scan of that drive.

Each line has **Review**, which opens the right place. The plan itself removes nothing. Sizes are what removal really frees: caches that refill count as 0 (**Frees nothing lasting**), as do hardlinks and cloud-only files; compressed files count their size on disk.

## Recommended setup

- Turn on **Drive health** in Settings › Notifications and keep Deck running as administrator.
- Enter your SSD's TBW if Deck didn't know it; set a **Temperature alert** around 70 °C if you want one.
- Scan your system drive every few months; use **Find duplicate files** and **Make room** before buying storage.
- Run the speed test on a new or slow drive, at 256 MB to 1 GB.

## Troubleshooting

- **No drives could be read.** Drive health needs administrator. See [Getting started](getting-started.md#why-deck-needs-administrator).
- **Unknown verdict.** The drive is behind a USB enclosure or RAID controller that hides its health. That alone says nothing about the drive.
- **The figures didn't change.** Deck reads every 10 minutes and doesn't wake sleeping drives. Press **Check drives**.
- **Caution, but it works fine.** The drive reported something, such as a few reallocated sectors. Back it up and watch whether the number grows.
- **The speed test won't start.** A game is in front, or there isn't enough free space.
- **An NTFS scan is slow.** Without administrator, Deck can't read the file table.
- **Sizes differ from Windows.** **Space on disk** and **Measure selected space** show the size on disk.

## FAQ

- **Do health checks write to my drive?** No. Only the speed test and the verified copy write.
- **Does the speed test wear my SSD?** Slightly. The default test writes up to about 13 GB, a tiny share of a modern SSD's rating.
- **Is anything uploaded?** No, unless you turn on drive warnings to your phone.
- **Does Disk space delete anything for me?** Only what you recycle, and only to the Recycle Bin.
- **Where is the data kept?** In `drive-health.json` and `drive-history.json` under `%APPDATA%\Deck`.
