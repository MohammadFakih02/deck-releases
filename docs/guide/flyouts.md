# Flyouts

Flyouts are small cards that pop up on the edge of your screen when something changes: the song, the volume, your microphone, Caps Lock, and so on. Deck can also hide Windows' own volume pop-up so you do not see two.

Find them under **Desktop > Flyouts**. The tabs are **Music**, **System**, **Music apps** and **Placement**. Every flyout is **off by default**; you turn on the ones you want.

Key facts:

- Flyouts never take focus. They do not steal keystrokes from a game or app.
- They follow what Windows reports (its media controls, its volume and device notifications). Deck does not hook your keyboard, so a change from any key, app, phone or controller counts the same.
- Several flyouts stack instead of overlapping.
- Over a game or a fullscreen window, a flyout lets mouse clicks pass through to the game. It is drawn without the web engine there so it does not cost frames. Flyouts are separate windows; Deck never injects into a game or reads its memory, so they are safe with anti-cheat. The one caveat is exclusive fullscreen, where no window can be drawn over the game (see [Placement](#placement-tab)).
- Flyouts stay out of the way during presentations and when Windows is in Do not disturb mode.
- If another program also shows song pop-ups, a warning banner at the top of the page names it, because you would see both. Close it or turn off its pop-ups.

---

## Music tab

### Song changes

The main switch for the music card. When on, a card shows the song title, artist and cover whenever the song changes, with previous, play/pause and next buttons. The card is coloured from the cover. When you turn it on, a sample appears so you can see it.

When the song changes, the card says the song is changing and never shows the old song as the new one; the name appears as soon as the player publishes it (some players take up to about a second and a half).

| Setting | What it does | Default | Recommended |
|---|---|---|---|
| **When you skip** | Show the card when you skip (from a media key, the player, a browser, the phone or a controller). | On | On. |
| **When the next song starts** | Show the card when a song ends and the next one starts by itself. | On | Turn off if you only want to see manual skips. |
| **Show volume with music** | **Separate**, **Above**, **Below** or **One card**. Above and Below open both cards when either changes. One card puts a thin volume bar under the song (drag it, scroll on the card, or click the speaker to mute), and volume appears alone when nothing is playing. | Separate | One card for a tidy screen. |
| **Player's own volume** | Adds a slider for just the music app, which is that app's level in the Windows volume mixer. The slider inside the app does not move. It is hidden if Windows cannot identify the player safely. | Off | Off unless you use it. |
| **Media keys always reach the player** | Sends play, next, previous and stop keys directly to the music player, so a window in front (even a frozen one) cannot keep them. Other programs that use these keys no longer receive them while this is on. | Off | Off unless media keys are being caught by something else. |
| **New song stays for** | How long the card stays (1 to 30 seconds). | 5 s | 4 to 6 s. |
| **Also for pausing and resuming** | Shows a card when playback pauses or resumes. | On | Your preference. |
| **Pause or resume stays for** | How long that card stays (0.5 to 15 s). Shown when the previous switch is on. | 2.5 s | |
| **Song end tolerance** (under **Advanced**) | How close to the end of a song a skip still counts as the song finishing (1 to 12 s). Raise it if your player crossfades. | 4 s | Leave as is unless a crossfade confuses it. |
| **Show the current card** | Previews the current song, or a labelled sample if nothing is playing. | | |

If both "When you skip" and "When the next song starts" are off, new songs do not show, but pausing and resuming still can. How Deck tells a skip from a song ending: by how close the song was to its end when it changed (it estimates from the player's position).

Skips you make from inside Deck always count as skips.

---

## System tab

Each system flyout has a switch, and once on, a **Stays for** time (0.5 to 15 seconds, default 2 s) and a **Show** button to preview it.

| Flyout | Shows | Notes |
|---|---|---|
| **Volume** | Volume and mute changes. Drag, scroll or click it to adjust or mute. | Has the extra switch **Hide Windows' own volume pop-up**: Deck draws its card and hides Windows' popup once its own is drawn. Support depends on your Windows version; if Deck cannot show its replacement, Windows' popup stays. Off by default. |
| **Microphone** | When the default microphone is muted or unmuted ("Muted" or "Unmuted"). | |
| **Sound device** | When sound moves to another device. | |
| **Lock keys** | Caps Lock, Num Lock and Scroll Lock. | |
| **Brightness** | Changes to the built-in screen's brightness. | Greyed out with "Brightness changes aren't reported by this screen." if Windows does not report them. |
| **Airplane mode** | When airplane mode turns on or off. | Greyed out if Windows does not report airplane mode on your PC. |
| **Charger** | When the charger is plugged in or out. | Greyed out when Windows is not reporting a battery (most desktops). |

When "Show volume with music" is not Separate, the volume flyout also appears with the music card.

---

## Music apps tab

Choose which apps count as music. Open a music player and it appears here with a note such as "Counts as music now: <song>", "Ignored now" or "Not open". Each app has:

| Choice | Meaning |
|---|---|
| **Auto** | Use Deck's rules. Known music apps always count. Other apps need an artist and a duration of 45 seconds or more. Launchers, chat and social apps are skipped. Browsers are a fallback. |
| **Always** | Always count this app. |
| **Never** | Never count it (for an app that shows videos, say). |

Some apps share one Windows identity (several apps reporting as the same player). They show a small info icon: the choice applies to every app sharing that identity.

A media entry that only gives a program's own name (a game launcher, for example) is ignored, so it cannot be mistaken for a song.

---

## Placement tab

| Setting | What it does | Default |
|---|---|---|
| **Position** | Six spots: top left, top middle, top right, bottom left, bottom middle, bottom right. Flyouts appear on the monitor containing the window you are using. Changing it moves flyouts that are already open, and shows a sample. | Top right |
| **Over games and fullscreen** | **Card**: shows cards that let clicks pass through to the game. **Overlay text**: shows the song as text in Deck's in-game overlay instead of a window (needs the Overlay turned on under Play; see [Overlay](overlay.md)). **Nothing**: hides flyouts while a game or fullscreen window is in front. | Card |
| **After the pointer leaves** | How long a flyout lingers after your pointer moves away from it (0.5 to 10 s). | 1.5 s |

Details for games:

- In true exclusive fullscreen, no window can be drawn over the game, so cards may be hidden. If the Overlay is on, the song is also shown there.
- Overlay text is drawn by RivaTuner, which cannot draw most non-Latin text (Japanese, for example). Use Card for those songs.
- Flyouts stay out of the way while the player or Deck itself is in front.

---

## Recommended setup

- Casual PC: turn on **Song changes** and **Volume**, set **Show volume with music** to **One card**, and enable **Hide Windows' own volume pop-up**.
- Gamers: leave **Over games and fullscreen** at **Card** for borderless-windowed games, or **Overlay text** with the Overlay on for exclusive fullscreen; **Nothing** if you never want interruptions.
- Laptops: turn on **Charger** and **Brightness**.
- Voice chat users: turn on **Microphone** so you notice a mute change.

## Troubleshooting

**Nothing appears.** Check the flyout's switch is on, press its **Show** button, and look for a banner naming another program that is showing song pop-ups. For music, check the player is listed on the **Music apps** tab and is not set to **Never**.

**I see two volume pop-ups.** Turn on **Hide Windows' own volume pop-up** on the System tab.

**The card shows no cover or the old title for a moment.** Some players are slow to publish the new song. Deck waits for the new name and shows "changing" until it arrives.

**A flyout is greyed out.** Windows does not report that thing on your PC (see the System tab table).

**Media keys do nothing, or something else answers.** Turn on **Media keys always reach the player**. Be aware other programs that use these keys then stop receiving them.

**Song card appears for videos.** Set that app (often a browser) to **Never** on the Music apps tab.

**Nothing shows in my game.** Exclusive fullscreen hides windows. Use borderless windowed, or set **Over games and fullscreen** to **Overlay text** with the Overlay on.

## FAQ

**Is it safe with anti-cheat?** Yes. Flyouts are ordinary windows that never take focus, drawn over the game by Windows. Deck does not inject into games or read their memory, and it does not hook the keyboard.

**Do they cost frames?** Over a game they are drawn without the web engine and with very little work; you can also choose Nothing.

**Does Deck read what I listen to?** Only what Windows' media controls report to the card, on this PC. Nothing is sent anywhere.

**What does Deck change on my PC?** Nothing permanent. The only system-wide effects are the optional hiding of Windows' own volume pop-up and, if you choose it, sending media keys directly to the player. Both revert when you turn the setting off.
