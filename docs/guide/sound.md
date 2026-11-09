# Sound and mic

The **Sound and mic** page controls where your sound plays, how loud everything is, which apps use which speakers, and how your microphones are set up. It also holds automatic switching: output profiles, rules that react to a headset being plugged in or an app starting, and a microphone check before calls.

Find it under **Desktop > Sound and mic**. It has three tabs: **Playback**, **Microphones** and **Outputs & rules**. Deck reopens on the tab you used last.

Everything on this page uses Windows' own audio controls (the same ones the Windows volume mixer and Sound settings use). Deck does not install an audio driver, does not hook into games and does not read their memory, so it is safe with anti-cheat.

---

## Tab 1: Playback

### Playback devices

A card per speaker, headphone or other output Windows has turned on. The one in use is marked **Default playback**. Click another card to make it the default for apps, games and calls.

The panel folds down to just the device in use. **Expand** shows every device and two extra buttons:

| Control | What it does |
|---|---|
| **Rename a playback device** | Pick a device, type a new name. It is the name Windows and every app show for it. Handy when two outputs are both called "Speakers". |
| **Turn playback devices on or off** (shown as "On or off (N off)" when something is off) | Lists every playback device with a switch, like Windows' Enable and Disable. A device that is off disappears from Windows and from all apps until you turn it back on. Devices that are off stay in this list so you can bring them back, and a line under the folded panel says how many are off. |

Recommended: turn off outputs you never use (a monitor's speakers, a virtual cable) to keep the list short. Keep at least one on.

### Device volume

A large slider for the volume of the current default output, with a mute button and a live level bar. This is the same master volume as the Windows volume icon.

### App volumes

One row per app that is making sound right now, with its own slider, mute button and level bar. This is the same per-app volume as the Windows volume mixer. Apps appear while they play; if nothing is playing the panel says "No app is making sound right now."

### Playing

When an app reports a song or video through Windows' media controls, a card shows the title, artist, app and state with **Previous**, **Play / Pause** and **Next** buttons. The buttons are greyed out when the app does not support that action. The pop-up music card is a separate feature; see [Flyouts](flyouts.md).

---

## Tab 2: Microphones

A card per microphone Windows has turned on. The panel folds down to the default microphone; **Expand** shows all of them and a **Turn microphones on or off** button that works like the one for speakers.

### On each microphone card

| Control | What it does |
|---|---|
| Name and chips | The short name and the full Windows name. The chip **Apps and games** marks the default recording device; **Calls** marks the one Windows uses for calls. |
| Rename (pencil) | Changes the name Windows and apps show for the microphone. |
| Mute (microphone icon) | Mutes or unmutes it in Windows. |
| **Level** | How loud this microphone records, the same slider as in Windows Sound settings. Aim for your voice to reach about two thirds of the test bar and rarely touch the end. |
| **Boost** | Extra gain in the sound driver (often +10, +20 or +30 dB) applied before the level slider. Shown only when the driver offers it; otherwise the card says "Boost: not supported by this microphone." Raise the level first and use boost only if that is not enough, because it adds hiss. |
| **Use for apps and games** | Makes this the default recording device. Hidden on the mic that already is. |
| **Use for calls** | Makes this the microphone Windows uses for calls. Hidden on the mic that already is. |
| **Check mic for 5 seconds** | Starts a five-second test: a bar shows your level as you speak. Nothing is kept or sent anywhere. |
| **Hear it on the speakers** | Windows' "Listen to this device": plays the microphone on your default speakers. Useful to check how you sound or to hear a line-in device such as a console. It needs administrator rights, and with speakers instead of headphones it can howl. Shown only for microphones that support it. |

### Check the mic when a call app starts

| Setting | What it does | Default | Recommended |
|---|---|---|---|
| **Check the mic when a call app starts** | When one of these programs starts, Deck looks at the microphone Windows uses for calls: Zoom, Teams, Discord, Skype, Webex, Cisco Collaboration Host, Slack or WhatsApp. If something is wrong a notification says "Check your microphone before the call". | Off | On, if you take calls. |

What it warns about:

- no microphone set up for calls
- the call microphone is muted, or turned almost all the way down
- "Listen to this device" is on for it, so you may hear yourself
- calls use a different microphone from the one apps use (it names both)

It only reads settings. It does not record. Only a call app that starts while Deck runs is noticed; one already open when Deck starts is not.

### Five-second microphone check

After a **Check mic for 5 seconds** test, a panel shows the measurements:

- **Peak** in dBFS (how close the loudest moment came to the limit; 0 is the limit)
- **Noise floor** (the background level; "not measured" if you never paused)
- **Clipping**, the share of the recording that hit the limit

Plain advice follows. Examples: your voice reaches the limit and distorts (lower the level or boost); nothing loud was heard (speak up, check mute, raise the level); very quiet (raise the level or boost); level is good; a lot of background noise (move the microphone closer and lower the boost). Pause briefly during the test so the background noise can be measured. Nothing is saved.

---

## Tab 3: Outputs & rules

### App outputs

Choose a different output for each app that is playing sound, for example a game on your headset while music stays on the speakers. Each row has a drop-down: **Follow Windows default** or one of your outputs.

- An app appears here while it is making sound. If the list is empty, start playing something in the app and press **Refresh app outputs**.
- Deck sets the choice for all three of Windows' audio roles for that app, the same way Windows' App volume and device preferences page does.
- If your Windows version does not allow this, the panel shows the reason instead of the list.
- If the app closes before you choose, Deck says "That app isn't playing sound any more." Start it again and retry.

**Undo sound changes** restores the previous values of everything Deck changed on this tab (default outputs, app outputs, output volume, app volumes) and turns off both **Automatic output switching** and **Remember each app's volume**. If an output is unplugged or an app is closed, Undo may report that some changes could not be restored; reconnect or reopen it and press Undo again.

### Output profiles and automatic switching

Open the fold **Output profiles and automatic switching**.

**Save current output profile** stores a named setup:

| Field | What it does |
|---|---|
| **Profile name** | Required. |
| **Playback output** | The device to make the default for apps, games and calls. |
| **Calls output** | Optional; "Same as playback" or another device just for calls. |
| **Include current app outputs and app volumes** | Also saves the output and volume of each app that is playing sound when you save. |

A profile is applied with its **Apply** button, and removed with **Delete** (after asking). Applying a profile switches the output, then sets the saved app outputs and volumes for apps that are running. If a device in the profile is not connected, Deck says which; the rest is still applied. You can keep 24 profiles.

Profiles never change the recording (microphone) defaults. Choose microphones on the Microphones tab or in Windows Sound settings.

**Add an output rule** has two kinds:

| Rule | When it fires | What it does |
|---|---|---|
| **A headset or output connects** | An output whose name contains the text you typed ("Part of the output name", not case-sensitive) appears. | Makes that output the default, or applies a profile you pick. Choose "Use the connected output" for the first. |
| **An app starts** | A program you named ("Program file name, including .exe") starts. | Applies the output profile you pick. A profile is required for this kind. |

You can keep 24 rules, which are listed as "When an output containing ... connects" or "When ... starts". Delete one with **Delete rule**.

Two switches control the automation:

| Setting | What it does | Default | Recommended |
|---|---|---|---|
| **Automatic output switching** | Applies enabled rules when an app starts or an output connects. | Off | On if you have rules. Everything here stays off until you turn it on. |
| **Remember each app's volume** | Keeps each app's last volume separately for each output, and restores it when the app starts playing. Lets speakers and headphones have different app levels. | Off | On if you swap outputs often. |

Notes:

- Rules look at devices that appear after Deck has started watching. An output that was already plugged in when Deck started does not trigger a rule.
- Deck checks every couple of seconds, so a switch can lag a moment behind plugging in.
- "Remember each app's volume" saves the last level you set for an app on an output, and sets it again the next time the app starts playing there. Changes you make later are remembered. It holds a limited number of entries.

---

## Recommended setup

- **Headset and speakers:** save an output profile for each, add a "headset connects" rule that applies the headset profile, and turn on **Automatic output switching**.
- **Gaming with chat:** set the game to your headset and the chat/music app to your speakers under **App outputs**, and save it as a profile that includes app outputs.
- **Calls:** set **Use for calls** on your headset microphone, turn on **Check the mic when a call app starts**, and run **Check mic for 5 seconds** once to set a good level.
- **Laptops:** if you dock often, a "dock connects" rule saves you opening Windows Sound settings.
- If you ever feel lost, **Undo sound changes** returns the page to how Deck found things.

---

## Troubleshooting

**An app is missing from App volumes or App outputs.** Apps only appear while they are making sound. Play something, then press **Refresh app outputs**.

**The device I want isn't listed.** It may be turned off. Expand the panel and use **Turn playback devices on or off** (or the microphone equivalent). Disabled devices are listed there with their switch.

**"Not connected now" when applying a profile.** A device in the profile is unplugged. Plug it in and apply again; the connected parts were still applied.

**A rule didn't fire.** Check that **Automatic output switching** is on, the rule's text really appears in the output's name (look at the full name on the Playback tab), and for app rules that the program name includes `.exe` and an output profile is chosen. Rules react to things that start or connect after Deck is running.

**The mic test shows no movement.** Check that the microphone is not muted in Windows or physically, and that the right microphone is selected. The bar only moves for the five seconds of the test.

**"Hear it on the speakers" is missing or fails.** Not every microphone supports it, and changing it needs administrator rights.

**I hear an echo or howl.** "Hear it on the speakers" is on while using speakers. Turn it off.

**Boost isn't available.** The microphone's driver does not offer it. Use the level slider.

## FAQ

**Is this safe with anti-cheat?** Yes. Deck changes volumes and default devices through Windows. It does not touch games.

**What does Deck change on my PC?** Default playback and recording devices, volumes, per-app outputs, microphone mute/level/boost, the "Listen to this device" flag, device names and enabled state, only when you ask (or when you enable automatic switching). Before a change, Deck records the old value so **Undo sound changes** can put it back.

**Does anything record my voice?** No. The five-second check measures levels in memory and keeps nothing. Only the measurements of the last test are shown.

**Do I need a driver or other software?** No. (Phone as microphone is a different feature and does need a virtual cable; see [Phone](phone.md).)

**Are the changes kept after a restart?** Windows keeps default devices and volumes. Deck keeps profiles, rules and the two switches.
