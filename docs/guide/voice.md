Where to find it: Audio › Mic (Soundboard is the page next to it)

# Mic and Soundboard

Clean up your microphone, add a voice effect and play sounds into Discord, games and calls through VB-CABLE.

The **Mic** page has no tabs. From top to bottom: what others hear, your microphone next to the setup check, the stages acting on your voice, and the effect. Windows' own microphone jobs (default mic, rename, turn on or off, Listen) are on [Mixer › Devices](sound.md#devices).

## Others hear

The top card says what goes out right now:

| It says | Meaning |
| --- | --- |
| **Your voice, cleaned** | Processing is on, no effect. |
| Your voice + an effect (for example "Your voice + Radio") | Processing is on with that effect. |
| **Your mic, untouched** | Processing is off, or the voice isn't running. Apps on CABLE Output hear your plain mic. |
| **Muted** | Deck's **Mute** is on. Sounds still play. |
| **Nobody is listening** | No app records CABLE Output, so the chain rests. With the page closed and no sound playing, Deck also stops listening to the mic until an app listens, a sound plays or you open the page. |
| **Nothing — VB-CABLE missing** | There is no cable to send the voice to. |

Chips show which app is listening (for example "Discord listening"), the effect and the delay. **Mute** silences your voice. Windows' own mute is the **Windows: muted** chip on the **Microphone** card.

The switch on the card is **Processing**:

- On: your voice goes through the clean-up stages and the effect. Turning it on the first time also starts the voice.
- Off: apps on CABLE Output still hear you, but as your plain mic.

The **⋯** menu has:

- **Voice outputs…**: where others hear you (**Others hear**), where you hear yourself (**You hear**) and **CABLE as default mic**.
- **Open the audio devices again**: try again after a device was unplugged.
- **Import MicDrop's settings** (when MicDrop is found).
- **Stop and free the mic**: stops the voice completely. Apps on CABLE Output then hear nothing.

## Microphone

Pick the mic Deck uses (**Windows default** follows Windows' choice), watch its **Level** (the green marks are the good range) and set its **Input volume**. **Test (5 s)** records five seconds and shows the peak, the noise floor and clipping; it works with the voice off too. **Hear myself** plays your processed voice in your headset.

## Setup check

Each row is good or needs a fix, with the button Deck can offer:

| Row | Good when | Fix |
| --- | --- | --- |
| **VB-CABLE** | Installed and on | **Get VB-CABLE** (VB-Audio's own setup: click Install Driver, then restart the PC), **Turn on**, or **Fix** when the cable became your speakers |
| **Apps hearing Deck** | An app records CABLE Output | Pick CABLE Output as that app's microphone |
| **Raw mic in use** | No other app records your real mic | **Fix** turns on **CABLE as default mic** |
| **Level** | Your recent peaks are in the good range | **Test (5 s)** |
| **Heard once** | No echo loop: Windows Listen is off, MicDrop is closed | **Turn Listen off**, **Quit MicDrop** |
| **App noise filter off** | You marked it **Done** | Deck can't read Discord's settings. Turn off its noise suppression (Krisp), echo cancellation and automatic gain, then press **Done**. |

Before the voice first runs, this card is **Set up** with three steps:

1. **Install VB-CABLE**
2. **Turn on processing**
3. **In Discord, pick CABLE Output**

Keep your headphones or speakers as Windows' playback device. The voice won't start while CABLE Input is the default output, because every app's sound would reach your friends.

## Processing now

A row of the stages acting on your voice, in order, each with its value and when it acts:

| Stage | Acts |
| --- | --- |
| **Rumble filter** | Always |
| **Noise suppression** | Always |
| **Noise gate** | Between words |
| **EQ** | Always |
| **Compressor** | Loud words |
| **Effect** | Always, or while talking |
| **Ducking** | While a sound plays |
| **Limiter** | Peaks only |

**+N off** lists the stages that are off. Click a stage to open its settings: its switch, **A/B** (hold to hear your voice without that stage), **Reset** and its sliders. The card is titled **Processing** while the voice is off.

### Natural sound

**Natural** and **Custom** at the top of the card show whether every stage is at its default. Press **Natural** to reset every stage (Hear myself is kept); **Undo** brings back what you had.

The defaults aim for a natural voice:

- **Noise suppression** on at 80 % strength, so a little of your own mic keeps the voice full.
- **Noise gate** off. Turned on, it only lowers the mic by 20 dB between words, so word ends aren't cut.
- **EQ** off and flat.
- A light **Compressor** (−20 dB, 2:1).

Values you never moved follow these defaults. Values you moved, or imported from MicDrop, stay.

## Effect

Starred effects, **None** and the one in use are buttons. **All effects** opens the full list: change an effect's controls, star it for the tray and phone, **Duplicate as my own…**, **Rename…**, **Move up** or **Move down** (the tray and phone follow this order) or **Reset its settings**.

### Autotune

**Autotune** pulls your pitch to the nearest note of a key and scale.

| Control | What it does | Default |
| --- | --- | --- |
| **Key and scale** | Click a note to make it the key. Chromatic, Major, Minor or Pentatonic. | C, Chromatic |
| **Strength** | How far each note is pulled. 100 % lands on the note. | 100 % |
| **Retune speed** | 0 ms snaps at once (the robot sound); higher glides. | 0 ms |

It adds about 12 ms of delay. Whispers, noise and very low or high pitches are left alone.

## Soundboard

The top line says what others hear, with a **Mic** button back to the Mic page.

1. Press **Add** and choose **Add sound files…** or **Add a whole folder…**. Deck measures each sound's loudness in the background.
2. Click a pad to play it. **Stop all** stops every sound.
3. Star sounds to put them in **Favorites**. Search the board, or filter by **Favorites**, **Short** or **Long**. **Show N more** opens the rest of **All sounds**.

A sound's menu edits its name, level, key and who hears it, or removes it. **Sound levels** sets what others hear and what you hear. **Options** has overlapping sounds, even loudness, the voice effect on sounds and **Keybinds in games**. Sounds play only while the voice runs.

### Keys for sounds

In a sound's **Edit…** sheet, give it a key (for example Ctrl+Alt+1). Keys work while the voice runs and are refused if another Deck shortcut uses them. **Keybinds in games** is off by default, so a game in front keeps its keys.

### Say it

**Say it** speaks what you type into the voice, so others hear it like a sound (you hear it too). Up to 500 characters. Choose a **Speaking voice** from those installed in Windows and a **Speed** (**Slow**, **Normal** or **Fast**). Nothing is downloaded or kept.

## CABLE as default mic

Off by default, in **⋯ › Voice outputs…**. On, apps set to the default mic hear Deck's processed voice while it runs. Deck restores your previous mic when the voice stops, when Deck quits, or at the next start after a crash. [What Deck changed](home.md#what-deck-changed) lists it, with **Undo**.

## Tray and phone

While the voice runs, the tray menu's **Voice** submenu (in the Desktop group) has **Voice effect**, **Mute my voice**, **Stop all sounds** and **Reset voice and sounds**. The [phone remote](phone.md) has the same parts: turn Voice on or off, **Mute**, **Stop all**, **Clean and stop**, effects, the soundboard with search, **Others hear** and **You hear**, and **Say it**. When the phone is your microphone, its audio goes through the same chain.

## Import MicDrop's settings

1. Quit MicDrop.
2. Choose **⋯ › Import MicDrop's settings** on the Mic page, or **Add › Import MicDrop's sounds and effects** on the Soundboard.

This brings over sounds, effects, the mic chain, volumes and device choices, and replaces the current setup. It doesn't turn the voice on. MicDrop's own files stay as they are.

## Safety

- Deck updates install only after the voice has been quiet for 10 minutes, so a call is not cut.
- While the voice runs, Deck holds the cable on its own where Windows allows it, so a screen share can't record your voice twice.
- Sound files over 200 MB are refused.

## If something is wrong

- **Others hear nothing:** read Others hear and the Setup check: the cable, the app on CABLE Output, Mute.
- **Sounds are cut short in chat:** turn off the chat app's noise suppression, echo cancellation and automatic gain.
- **A device was unplugged:** reconnect it, or pick another on the Microphone card, then **⋯ › Open the audio devices again**.
- **There is an echo:** follow the Heard once row and use headphones.
