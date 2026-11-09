# Clipboard

The **Clipboard** page keeps a history of what you copy (text, images and files), lets you search it, pin the things you want to keep, paste an old item back, change text before you paste it, and store snippets you type often.

Find it under **Desktop > Clipboard**. The tabs are **Text**, **Images**, **Files**, **Pinned** and **Settings**. Windows' own Win+V history keeps working; Deck's history is separate.

Deck does not send your clipboard anywhere. The history is stored on this PC only. Items that a password manager marks as private are never stored (see [Privacy](#privacy)).

---

## The history

### The list

Each tab shows one kind of item, newest first, grouped under **Pinned**, **Today**, **Yesterday** and **Earlier**. Each card shows:

- an icon for the kind (text, link, image, files),
- a preview (the first 600 characters of text, a thumbnail of an image, or the file names),
- small details: **Pinned**, "Wiped within a minute" (see below), how long ago it was copied, the app it was copied from, a link's website, the number of characters of text or the size of an image.

The list shows 120 items at a time; scroll to the end, or press **Show N more**, for the rest. The header counts every item kept.

### Searching

The **Search clipboard history** box filters by text, file names and the app the item came from. **Search scope** chooses **This tab** (default) or **All history**.

### Selecting, pasting and keyboard

| Action | Result |
|---|---|
| One click | Selects the item and shows it on the right. |
| Double-click or Enter | Pastes the item into the app you were using, or just copies it, depending on the **On double-click or Enter** setting. |
| Arrow keys | Move the selection. |
| Delete | Removes the selected item. |

The keys work as long as you are not typing in a box.

### The selected item (right side)

| Control | What it does |
|---|---|
| **Paste** / **Copy** | The main button follows the **On double-click or Enter** setting. When it says Paste, a second **Copy** button copies without pasting. |
| Pin (pin icon) | Pinned items are kept, are not counted towards the history limit, and are never wiped. |
| Send to phone | Sends the text (or a single copied file) to your connected phone. See [Phone](phone.md). |
| Delete (bin) | Removes the item. |
| Preview | Text shows in full up to the first 20,000 characters; copy and paste still use all of it. Images show larger with their size. Files list their names and open in Explorer when clicked. |
| Counts | Characters, words and lines for text. |

### Paste as

For text items, the **Paste as** chips put a changed version on the clipboard (and paste it if pasting is on). The item in your history is not changed.

| Chip | Result |
|---|---|
| **Plain text** | The text with formatting removed. |
| **Upper case**, **Lower case**, **Title case** | Changes the letter case. |
| **Trim spaces** | Trims each line, collapses runs of spaces, trims the whole. |
| **One line** | Joins lines into a single line. |

### Change it (preview first)

A second set of chips for text shows a preview before anything is copied:

| Chip | Result |
|---|---|
| **Format as JSON** | Pretty-prints JSON (it says so if the text is not valid JSON). |
| **Lines to CSV** | One value per non-empty line, joined with commas, quoted where a spreadsheet needs it. |
| **Remove link tracking** | Removes tracking parameters (such as campaign tags) from every link in the text. |
| **Hide private details** | Replaces emails, card numbers, keys and long numbers with labels. |

Then **Copy the changed text** (or **Paste the changed text**), or **Close preview**. If nothing would change, the page says "Nothing to change in this text." The original stays in your history.

### Images

For an image item, **Copy text from this image** reads the text in the picture using Windows' built-in text recognition and shows it, with **Copy the text**. The image is untouched. It uses the recognition languages installed in Windows.

### Clear history

**Clear history** (bottom right) deletes everything except pinned items, after asking.

---

## Clipboard settings

These live in **Settings › Desktop**.

### Clipboard history

| Setting | What it does | Default | Recommended |
|---|---|---|---|
| **Keep clipboard history** | Master switch. Off stops recording. | On | On, unless you never want a history. |
| **Keep images** | Also keep copied pictures (stored as PNG files on disk). | On | Off if you copy many screenshots and want to save disk space. |
| **Wipe codes and keys after a minute** | Removes copies that look like secrets from the history 60 seconds after they were copied. Pinned items stay. | Off | On if you copy passwords, one-time codes or keys. |
| **On double-click or Enter** | **Paste into the app you were using**, or **Copy only**. | Paste | Paste for speed; Copy only if pasting into the wrong window worries you. |
| **History limit** | How many items are kept: 100, 200, 400, 1,000 or 3,000. Pinned items do not count. | 400 | 400 for most; more only if you search old items. |

Other limits: text over 1,000,000 bytes is not kept, and at most 150 unpinned images are kept.

"Wipe codes and keys" works on the **pattern** of the text: short, single-line copies that look like a one-time code, a payment card number (it passes the standard card check) or a key/token/password by its shape. It can miss a secret, or wipe ordinary text that looks like one, so treat it as a safety net. Wiped items show "Wiped within a minute" until they go.

### Snippets

Short texts you type often (an email sign-off, an address).

1. Press **New snippet**.
2. Give it a **Name**, an optional **Keyword you type in the launcher** (one word), and the **Text**.
3. In the text, `{date}`, `{time}`, `{datetime}` and `{clipboard}` are filled in when you use the snippet. A live line shows "What it pastes right now".
4. Click a snippet to edit it; the bin deletes it. Up to 200 snippets of up to 20,000 characters each.

Type the keyword in the launcher (see [Launcher](launcher.md)) to paste the snippet.

### Paste as plain text

A list of apps (for example a code editor, a terminal, a notes app). When one of these apps comes to the front while the clipboard holds formatted text (from a web page or a rich-text document), Deck adds the plain-text version to the top of the history and shows a notice with a button that puts only the plain text on the clipboard. Nothing is pasted for you, and the clipboard itself is not changed until you press the button. Pick an open app and press **Add**; **Remove** takes one off. Empty means off. Up to 30 apps.

---

## Privacy

- The history is stored on this PC (in `clipboard\history.json` in Deck's data folder, with images as files next to it).
- Copies that carry the standard Windows "do not keep this" flags are skipped. Password managers set these flags, so their copies never reach the history.
- Deck does not read the clipboard of other users and does not upload it. It only leaves the PC if you press **Send to phone** (to your own connected phone).
- Use **Clear history**, pins, **Wipe codes and keys after a minute** and **Keep images** to control what stays.

## Recommended setup

- Leave **Keep clipboard history** on, turn on **Wipe codes and keys after a minute**, keep the limit at 400.
- Pin the handful of things you paste daily.
- Add snippets for repeated text and give each a short keyword.
- Add your code editor and terminal to **Paste as plain text**.

## Troubleshooting

**Something I copied is missing.** It may have come from a password manager (never kept), exceeded 1,000,000 bytes, been wiped as a likely secret, or fallen off the end of the history limit. Check the **All history** scope.

**Double-click pastes into the wrong window.** Pasting goes to the window that was in front before Deck opened. If that is unreliable, set **On double-click or Enter** to **Copy only** and press Ctrl+V yourself.

**Images are missing.** Check **Keep images** is on. Only 150 unpinned images are kept.

**Clipboard history is empty and the page says it is off.** Turn on **Keep clipboard history** in Settings › Desktop.

**Copy text from this image finds nothing.** The image must contain text in an installed Windows recognition language, large enough to read.

## FAQ

**Does it replace Win+V?** No. Both work side by side.

**Is it safe with anti-cheat?** Deck only listens for clipboard changes through the normal Windows notification; it does not touch games. The Paste action sends a normal Ctrl+V to the app you were using; avoid using it while a game with strict anti-cheat has focus.

**Can I move my history to another PC?** The history is part of the files Deck's backup can include; see [Settings](settings.md).

**Why are there two "Copy" buttons?** When pasting is on, the main button pastes and the second copies. With Copy only, the main button copies, so there is just one.
