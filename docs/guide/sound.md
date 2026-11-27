Where to find it: Audio › Mixer

# Mixer

Choose where sound plays, set every volume, send apps to different outputs and switch outputs automatically.

**Mixer** has two tabs: **Playback** and **Devices**. Your voice itself (the mic Deck uses, its test, clean-up and effects) is on [Mic](voice.md). Links under the title open **Taskbar › Music & volume pop-ups** and **Devices › Device batteries** (headset sidetone and auto power-off, see [Device batteries](devices.md#headset-controls)).

Everything here uses Windows' own audio controls, the same ones as the Windows volume mixer and Sound settings. Deck installs no audio driver and doesn't touch games, so it is safe with anti-cheat.

## Playback

### Output

One button per output Windows has turned on, up to four; the rest are under **More outputs (N)**. The default one is marked **Default output**. Click another to make it the default for apps, games and calls. A virtual cable is marked **Into voice chat**, and Deck asks first before making it your speakers.

- **Spatial sound** opens Windows' Sound settings, where each output has its own spatial sound choice. Deck changes nothing there.
- **⋯ › Rename device** changes the name Windows and every app show, handy when two outputs are both called "Speakers".
- **⋯ › Turn devices on or off** lists every output with a switch, like Windows' Enable and Disable. An output that is off disappears from all apps until you turn it back on.

To switch the output from the tray, right-click the Deck icon and open **Sound output** in the Hardware group. It never changes the microphone.

### Device volume

The master volume of the default output, with mute and a live level bar, the same as the Windows volume icon. When Windows doesn't report the volume (a device just unplugged, a driver not answering), the card says **Not available** and the slider is locked until it answers.

### App volume

One row per app making sound now, with its own slider, mute and level bar, the same as the Windows volume mixer. Above 12 apps the silent ones fold behind **Show quiet apps (N)**. Each row also shows which output the app plays on; click it to change it.

### Chat mix

One dial between voice chat and the game, like the ChatMix wheel on some headsets. Off until you turn on the card's switch.

- Turn the dial toward **Chat** to lower the game, toward **Game** to lower chat. In the middle (**Even**) both play at their own level. Double-click for the middle.
- **Chat** lists the voice-chat apps (Discord to start with). **Add** picks from the apps playing sound now.
- **Game** counts **Game in front** (on by default); **Add** adds other programs.

Deck only scales each app's own volume. Turning the mix off, removing an app, or the game leaving the front restores each level; after a crash, the next start does.

### Output equalizer

Drives [Equalizer APO](https://sourceforge.net/projects/equalizerapo/), a free program you install yourself. Without it the card shows **Needs Equalizer APO**.

1. Turn on the card's switch. The state reads **Off**, **On: <curve>**, **Bypassed** or **On, not linked yet**.
2. Add the line `Include: deck-eq.txt` to Equalizer APO's `config.txt` (**Copy the line** helps). Until then the equalizer has no effect. Deck never edits `config.txt`.
3. Shape the ten bands (31 Hz to 16 kHz, ±12 dB): drag a handle, use the arrow keys, or double-click it for 0 dB. Or pick **Flat**, **Bass**, **Footsteps** or **Voice**. The preamp is set for you so boosted bands can't clip.

- **Headphones…** holds AutoEq corrections for 16 popular models, included with Deck (nothing is downloaded). **Earlier curve** brings back what you had.
- **Other headphones: paste a profile**: paste your model's `ParametricEq.txt` from AutoEq and press **Use this profile**.
- **Bypass (A/B)** keeps the file but writes no filters, to compare.
- **Remove and restore** turns the equalizer off and restores the file that was there before Deck's first write.

Writing into Equalizer APO's folder needs administrator. The equalizer works on a whole output, not per app. Apps that use exclusive mode bypass it.

### Now playing

When an app reports a song or video to Windows, this card shows it with **Previous**, **Play** / **Pause** and **Next**. A grayed-out button means the app doesn't offer it. The pop-up music card is a separate feature: see [Music & volume pop-ups](flyouts.md).

## Devices

### Microphones

One row per microphone, with chips for its jobs: **Apps** (the default for apps), **Calls**, **Muted** and **Listen on**. A row's ⋯ menu has:

- **Use for apps and games** and **Use for calls**
- **Mute** / **Unmute**
- **Listen to this device…**: plays the mic on your speakers. It asks first, needs administrator and can howl without headphones.
- **Mic boost…**: extra gain in the driver, only when the driver has it. Raise the input volume on Mic first; boost adds hiss.
- **Rename…**

**Turn microphones on or off** works like Windows' Enable and Disable.

**Test mic on calls** (off by default) checks your call microphone when Zoom, Teams, Discord, Skype, Webex, Slack or WhatsApp starts. It warns when the mic is missing, muted, nearly silent or playing on your speakers, or when calls use a different mic from apps. It only reads settings and never records.

### Auto switching

The top card turns automatic switching on or off. It starts off. **Remember app volumes** (off by default) keeps each app's last volume for each output, so speakers and headphones can have different app levels.

### App outputs

Send each app to its own output, for example a game on your headset and music on the speakers. One row per app playing sound, one column per output; **Default** follows Windows. Apps appear only while they play: start something and press **Refresh**. System sounds always follow the default output.

### Output rules

**Add rule** picks when it fires:

| When | What it does |
| --- | --- |
| **A headset or output connects** | When an output whose name contains your text appears, makes it the default (**Use the connected output**) or applies an output profile. |
| **An app starts (output goes back when it closes)** | Applies an output profile while the program runs. Your earlier outputs and volumes come back when it closes, even after a restart or crash. |
| **A game is in front (output goes back when it is not)** | The same, while that game is in front. A quick Alt+Tab doesn't flip it. |

App rules need a saved output profile and **Auto switching** on. While a game is in front, only that game's rules switch anything. A rule that is working says **In force now**. If Deck can't restore the earlier output (it was unplugged), the rule shows **Retrying reset · 2 min**; after that, choose the output yourself on Playback. Rules only react to devices and apps that appear after Deck has started.

### Reset changes

**Reset all** restores the outputs and volumes Deck changed on this page and turns off **Auto switching** and **Remember app volumes**.

### Output profiles

**Save current output profile** stores the **Output**, an optional **Calls output** and, with **Include current app outputs and app volumes**, each playing app's output and volume. **Apply profile** applies one; a device that isn't connected is skipped and named. Profiles never change the microphone.

## Recommended setup

- **Headset and speakers:** save a profile for each, add an **A headset or output connects** rule, and turn on **Auto switching**.
- **Gaming with chat:** put the game on your headset and music on the speakers in **App outputs**, and save it as a profile that includes app outputs.
- **Calls:** choose **Use for calls** on your headset mic, turn on **Test mic on calls**, and run **Test (5 s)** on [Mic](voice.md) once.

## Troubleshooting

**An app is missing from App volume or App outputs.** Apps only appear while they make sound. Play something, then press **Refresh**.

**The device I want isn't listed.** It may be turned off. Use **⋯ › Turn devices on or off** on Output, or **Turn microphones on or off** on Microphones.

**A rule didn't fire.** Check that **Auto switching** is on, the rule's text is part of the output's name, and an app rule has a profile and a program name with `.exe`.

**I hear an echo or howl.** **Listen on** is set on a mic while you use speakers. Choose **Turn Listen off** in its menu.

**Mic boost is missing.** The microphone's driver doesn't offer it.

## FAQ

**Is this safe with anti-cheat?** Yes. Deck changes volumes and devices through Windows and doesn't touch games.

**What does Deck change?** Default devices, volumes, app outputs, mic mute, boost and Listen, device names and on/off, only when you ask or when a rule fires. **Reset all** restores what Deck changed.

**Does anything record my voice?** No. The mic test measures levels in memory and keeps nothing.

**Are changes kept after a restart?** Windows keeps default devices and volumes. Deck keeps profiles, rules and the switches.
