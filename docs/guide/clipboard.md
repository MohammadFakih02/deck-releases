Where to find it: Taskbar › Clipboard

# Clipboard

A history of what you copy (text, images and files) that you can search, pin, group and paste back, plus snippets and the paste stack.

The tabs are **Text**, **Images**, **Files** and **Pinned**. Windows' own Win+V history keeps working; Deck's history is separate. The history stays on this PC, and copies a password manager marks as private are never kept (see [Privacy](#privacy)).

## The history

### The list

Each tab shows one kind of item, newest first, under **Pinned**, your groups, **Today**, **Yesterday** and **Earlier**. Each card shows the kind, a preview (text, a thumbnail or file names) and details: how long ago, the source app, a link's website, the length of text or the size of an image, and **Wiped within a minute** for likely secrets.

The list shows 120 items at a time; press **Show N more** for the rest.

### Searching

**Search history** filters by text, file names, group and source app. Select **Search all tabs** to search every kind of item.

Start with `re:` for a regular expression: `re:\d{5}` finds five digits in a row, `re:^https?://` finds links. Case doesn't matter. A broken pattern says so.

### Groups

1. Select an item and type a name under **Group** (or pick an existing one).
2. Press **Put in group**.

Groups show A to Z under **Pinned**. Up to 20 groups, names up to 40 characters. Grouped items are kept like pinned ones. **Remove from group** returns an item to its day.

### Selecting, pasting and keys

| Action | Result |
|---|---|
| Click | Selects the item and shows it on the right. |
| Double-click or Enter | Pastes into the app you were using, or only copies, as set in **On double-click or Enter**. |
| Arrow keys | Move the selection. |
| Delete | Removes the selected item. |

Keys work while you aren't typing in a box.

### The selected item

| Control | What it does |
|---|---|
| **Paste** / **Copy** | The main button follows **On double-click or Enter**. When it says Paste, a second **Copy** copies without pasting. |
| **Pin** | Pinned items are kept forever, don't count towards the limit and are never wiped. |
| **Send to phone** | Sends the text or one file to your connected [phone](phone.md). |
| **Delete** | Removes the item. |
| **Float on screen** | Images only: shows the picture in a small window that stays on top and never takes the keyboard. |
| Preview | Text in full (the first 20,000 characters show; paste uses all of it), a larger image, or file names and paths with **Show in folder**. |

### Paste as

For text, the **Paste as** chips copy a changed version (and paste it if pasting is on). The history item isn't changed.

- **Plain text**, **Upper case**, **Lower case**, **Title case**
- **Trim spaces** (trims lines and collapses runs of spaces)
- **One line** (joins the lines)

### Preview first

These show the result before anything is copied:

- **Format as JSON** (says so if the text isn't valid JSON)
- **Lines to CSV** (one value per line, joined with commas)
- **Remove link tracking** (drops campaign tags from links)
- **Hide private details** (replaces emails, card numbers, keys and long numbers with labels)

Then **Copy the changed text** (or **Paste the changed text**) or **Close preview**. The original stays in your history.

### Text from an image

**Extract text from this image** reads the text with Windows' built-in text recognition, in the languages installed in Windows. **Copy the text** copies it.

### Clear history

**Clear all** deletes unpinned items from every tab, after asking.

## Paste stack

Copy several things, then paste them in order.

1. Turn on **Paste stack** (the row under the summary).
2. Copy what you need, one after the other, from any app.
3. Press **Copy next**: the oldest waiting copy goes on the clipboard. Paste it with Ctrl+V.
4. Repeat until the waiting count is 0.

Deck never presses keys for you. Likely secrets and password-manager copies never join the stack. It holds up to 50 copies in memory only, and **Empty** clears it.

## Clipboard settings

These sit on the page, under the history.

### Clipboard history

| Setting | What it does | Default |
|---|---|---|
| **Keep clipboard history** | Off stops recording. | On |
| **Keep images** | Keeps copied pictures too. | On |
| **Wipe codes and keys after a minute** | Clears copies that look like one-time codes, card numbers or keys 60 seconds after copying. Pinned items stay. It goes by the shape of the text, so treat it as a safety net. | Off |
| **On double-click or Enter** | **Paste** or **Copy only**. | Paste |
| **History limit** | 100, 200, 400, 1,000 or 3,000 items. Pinned items don't count. | 400 |

Text over 1,000,000 bytes isn't kept, and at most 150 unpinned images are.

### Snippets

Short texts you use often.

1. Press **New snippet**.
2. Give it a name, an optional keyword (one word, for the [launcher](launcher.md)) and the text. `{date}`, `{time}`, `{datetime}` and `{clipboard}` are filled in when you use it; **What it pastes right now** shows the result.
3. Click a snippet to copy it, then paste with Ctrl+V.

Up to 200 snippets of 20,000 characters each, stored encrypted for your Windows account.

### Copy cleanup

Off until you add an app. Pick an app, select the actions, press **Add**. For text copied from that app Deck can **Remove link tracking**, **Trim spaces** and keep only plain text. The cleaned text is what the history keeps. Password-manager copies and likely secrets are never touched.

### Paste as text

A list of apps (a code editor, a terminal). When one comes to the front while the clipboard holds formatted text, Deck adds the plain version to the history and shows a notice with a button that puts it on the clipboard. Nothing is pasted for you. Up to 30 apps.

## Privacy

- The history, its images and your snippets are stored on this PC, encrypted for your Windows account; a copy of the folder is useless on another PC or account.
- Backups leave the history out unless you turn on **Include clipboard history in backups** in [Settings](settings.md), and only a backup with a password holds it.
- Copies flagged "don't keep" by Windows (password managers do this) are skipped.
- What you copy never goes into Deck's log or support report, and leaves the PC only through **Send to phone**.

## Recommended setup

- Keep the history on, turn on **Wipe codes and keys after a minute**, keep the limit at 400.
- Pin what you paste daily; add snippets with short keywords.
- Add your code editor and terminal to **Paste as text**.

## Troubleshooting

- **A copy is missing.** It may have come from a password manager, been over 1,000,000 bytes, been wiped as a likely secret, or fallen off the limit. Select **Search all tabs**.
- **Paste goes to the wrong window.** Set **On double-click or Enter** to **Copy only** and press Ctrl+V yourself.
- **Images are missing.** Check **Keep images**; only 150 unpinned images are kept.
- **The page says Clipboard history is off.** Turn on **Keep clipboard history**.
- **Extract text finds nothing.** The text must be in an installed Windows recognition language and large enough.

## FAQ

- **Does it replace Win+V?** No, both work.
- **Anti-cheat?** Deck only listens to Windows' clipboard notification. Paste sends a normal Ctrl+V; avoid it while a game with strict anti-cheat has focus.
- **Can I move my history to another PC?** Only through a password-protected backup with **Include clipboard history in backups** on.
