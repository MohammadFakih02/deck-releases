Where to find it: Taskbar › Music & volume pop-ups

# Music & volume pop-ups

Small cards that appear at the edge of the screen when the song, volume, microphone, a lock key or the charger changes.

The page has four tabs: **Music**, **System**, **Music apps** and **Placement**. Every pop-up is off until you turn it on. If Deck couldn't read the music players or what this PC supports, the tab says so and offers **Try again**.

Good to know:

- Pop-ups never take focus, so they don't steal keys from a game.
- They follow what Windows reports, so a change from any key, app, phone or controller counts. Deck doesn't hook your keyboard.
- Several pop-ups stack instead of overlapping.
- Over a game, clicks pass through and the card is drawn without the web engine, so it costs no frames. In exclusive fullscreen no window can be drawn over the game (see [Placement](#placement-tab)).
- They stay away during presentations and in Do not disturb.
- If another program also shows song pop-ups, a banner names it.

## Music tab

### Song changes

The main switch for song cards: title, artist and cover when the song changes, with previous, play/pause and next. The card takes its color from the cover. While a song is changing, the card never shows the old song as the new one.

| Setting | What it does | Default |
|---|---|---|
| **When you skip** | Show the card when you skip, from any key, player, phone or controller. | On |
| **When the next song starts** | Show the card when a song ends and the next starts. | On |
| **Show volume with music** | **Separate**, **Above**, **Below** or **One card**. One card puts a thin volume bar under the song (drag, scroll or click the speaker to mute). | Separate |
| **Player's own volume** | A slider for the player app's level in the Windows volume mixer. Hidden if Windows can't identify the player safely. | Off |
| **Media keys always reach the player** | Sends play, next, previous and stop straight to the player, so a window in front can't catch them. Other programs stop receiving these keys. | Off |
| **New song stays for** | 1 to 30 seconds. | 5 s |
| **Also for pausing and resuming** | Shows a card when playback pauses or resumes. | On |
| **Pause or resume stays for** | 0.5 to 15 seconds. | 2.5 s |
| **Song end tolerance** (in **Timing details**) | How close to the end a skip still counts as a finished song (1 to 12 s). Raise it if your player crossfades. | 4 s |

**Preview card** shows the current song, or a sample if nothing plays. If both "When you skip" and "When the next song starts" are off, new songs don't show.

## System tab

Each system card has a switch, a **Stays for** time (0.5 to 15 s, default 2 s) and **Preview card**.

| Card | Shows | Notes |
|---|---|---|
| **Volume** | Volume and mute changes. Drag, scroll or click to adjust. | **Hide Windows' own volume pop-up** (off by default): Deck's card replaces Windows' pop-up. If Deck can't show its card, Windows' pop-up stays. |
| **Microphone** | The default mic muted or unmuted. | |
| **Sound device** | Sound moves to another device. | |
| **Lock keys** | Caps Lock, Num Lock, Scroll Lock. | |
| **Brightness** | Built-in screen brightness changes. | Grayed out if the screen doesn't report them. |
| **Airplane mode** | Airplane mode on or off. | Grayed out if Windows doesn't report it. |
| **Charger** | Charger plugged in or out. | Grayed out without a battery (most desktops). |

## Music apps tab

Choose which players can show song cards. An open player appears here with what it does now. Each has **Auto**, **Always** or **Never**.

- **Auto:** known music apps count; other apps need an artist and a song of 45 seconds or more. Launchers, chat and social apps are skipped; browsers are a fallback.
- **Never** suits an app that plays videos.
- Apps that share one Windows identity show an info icon: the choice applies to all of them.

## Placement tab

| Setting | What it does | Default |
|---|---|---|
| Position | Pick a spot on the screen picture: top or bottom, left, middle or right. Pop-ups appear on the monitor with the window you're using. | Top right |
| **Over games and fullscreen** | **Card** (clicks pass to the game), **Overlay text** (the song as text in the [Performance overlay](overlay.md), which must be on) or **Nothing**. | Card |
| **Hide after the pointer leaves** | 0.5 to 10 seconds. | 1.5 s |

- In exclusive fullscreen, cards may be hidden; with the Performance overlay on, the song also shows there.
- Overlay text can't draw most non-Latin text (Japanese, for example). Use Card for those songs.

## Recommended setup

- Everyday PC: turn on **Song changes** and **Volume**, set **Show volume with music** to **One card**, and turn on **Hide Windows' own volume pop-up**.
- Gamers: **Card** for borderless games, **Overlay text** for exclusive fullscreen, or **Nothing**.
- Laptops: turn on **Charger** and **Brightness**.
- Voice chat: turn on **Microphone**.

## Troubleshooting

- **Nothing appears.** Check the switch, press **Preview card**, and look for a banner naming another program. For music, check the player on **Music apps** isn't set to **Never**.
- **Two volume pop-ups.** Turn on **Hide Windows' own volume pop-up**.
- **A card is grayed out.** Windows doesn't report that on your PC.
- **Media keys reach the wrong app.** Turn on **Media keys always reach the player**.
- **Song cards for videos.** Set that app (often a browser) to **Never**.
- **Nothing in my game.** Use borderless windowed, or **Overlay text** with the Performance overlay on.

## FAQ

- **Safe with anti-cheat?** Yes. They are ordinary windows; Deck doesn't inject into games or hook the keyboard. See the [FAQ](faq.md).
- **Does Deck read what I listen to?** Only what Windows' media controls report, on this PC. Nothing is sent anywhere.
- **What does it change?** Nothing permanent. Hiding Windows' pop-up and the media key option revert when you turn them off.
