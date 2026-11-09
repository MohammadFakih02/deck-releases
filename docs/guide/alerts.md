# Alerts and notifications out

Deck can watch your PC's sensors and tell you, or act, when something goes wrong: a CPU that is too hot, a fan that stopped, a drive that is running out of room on the speed you set. It can also send chosen messages to your phone or a chat app, so you hear about them when you are away from the PC.

**Where to find it:** sidebar > **Watch** > **Sensors** > the **Alerts** tab. That tab holds, from top to bottom:

1. **Temperature alerts** (the simple CPU and GPU heat warning)
2. **Sensor logging** (an optional log file)
3. **Alert rules** (your own rules on any reading)
4. **Notifications out** (ntfy and Discord)

Other Deck warnings live on their own pages: drive health warnings on the Drives page, and the warning before a shutdown plan on the [Power](power.md) page. Notifications out can forward those too.

Alerts need the sensor engine, so this tab only works on a PC where the Sensors page is available. See [Sensors](sensors.md). Alert checking runs while Deck is running (in the tray is fine) but not while Deck is quit.

## Contents

- [Temperature alerts](#temperature-alerts)
- [Sensor logging](#sensor-logging)
- [Alert rules](#alert-rules)
- [Notifications out](#notifications-out)
- [Recommended setup](#recommended-setup)
- [Troubleshooting](#troubleshooting)
- [FAQ](#faq)

## Temperature alerts

The quickest way to be warned about heat.

| Setting | What it does | Default |
|---|---|---|
| **Warn me when it gets hot** | Shows a Windows notification when the CPU or graphics card goes above the temperature you set. Catches a stopped fan, a clogged filter or a runaway overclock before it crashes. | Off |
| **CPU above** | CPU temperature limit, 60 to 105 °C. Appears once alerts are on. | 90 °C |
| **GPU above** | Graphics card temperature limit, 60 to 100 °C. | 85 °C |
| **Flash the board lights red** | For a few seconds when an alert fires, then the lighting effect returns. Appears if this PC has controllable lighting. | Off |

At most **one notification every five minutes per sensor**, so a long hot game does not flood you. When **Notifications out** is set up for "Alert rules and heat alerts", the heat alert is sent there too.

Temperature alerts, sensor logging and the lighting flash are applied together with **Apply changes** in the bar that appears at the bottom when you have edited them (it lists what you changed, and has **Discard changes**). If saving fails, your draft is kept and you can **Try again**.

### Choosing the limits

- CPU: most CPUs run 60 to 85 °C under heavy load. Many modern CPUs are designed to touch 90 to 100 °C briefly. If you set 90 and it fires constantly, your cooling is the issue; a limit slightly above your normal gaming temperature is better than one far above it.
- GPU: most graphics cards sit at 65 to 85 °C in games. 85 is a reasonable "something is wrong" line for many cards; check your card's specification.
- This alert tells you; it does not slow anything down. For heat protection of overclocks see [CPU](cpu.md) and [GPU](gpu.md).

## Sensor logging

| Setting | What it does | Default |
|---|---|---|
| **Log every sensor to a CSV file** | Writes every reading from the All readings table once a second to a `monitor.csv` file that Excel opens. Use it to see what happened before a crash, or to compare two settings over a session. A new file starts every 50 MB and the latest five are kept. | Off |
| **Slow readings during games** | While a game is running, drive and idle-fan sensors are read every three seconds instead of every second (fan control itself stays fast). Keeps the sensor engine lighter while you play. | On |
| **Open folder** | Opens the folder that holds the log. | |

The log contains sensor names and numbers only. See [where Deck stores data](settings.md#where-deck-stores-data).

## Alert rules

A rule watches one or more readings and acts when **every test holds without a break for a number of seconds**. Rules go further than the simple heat alert: any sensor Deck can read can be used (temperatures, fan speeds, loads, clocks, power, voltages, drive temperatures and more).

Press **Add an alert** to create one. You can have up to **20 rules**, each with up to **4 tests**. The button is greyed out if there are no readings to choose from yet.

### What a rule contains

| Part | What it does | Default |
|---|---|---|
| **Switch** | Turns the rule on or off without deleting it. | On |
| **Alert name** | A label (up to 60 characters). It becomes the title of the notification. | "New alert" |
| **Tests** | Each test is a **Reading** (from the list of readings Deck has, shown as "group | name"), **is above** or **is below**, and a **Value** in that reading's own unit. Use **Add another test** (up to four) to require several things at once, for example "GPU temperature is above 80" and "GPU fan is below 1000 RPM". Remove a test with **Remove test**. If a reading you used disappears, it is shown as "(not found now)" and the rule cannot fire. | One test, first reading, above 80 |
| **For at least** | How many seconds all the tests must hold continuously before it fires, 0 to 600 in steps of 5. Short spikes shorter than this are ignored. | 10 s |
| **Wait before repeating** | After a rule has fired it stays quiet at least this many minutes, even if the reading dips and comes back, 1 to 120. | 5 min |
| **Show a notification** | A Windows notification with the rule name and the current values (for example "CPU Package temperature is 91.2 (limit 90) for 10 s"). | On |
| **Send it out (see Notifications out)** | Also sends it to your ntfy topic / Discord webhook, if "Alert rules and heat alerts" is ticked there. | Off |
| **Flash the board lights red** | Flashes supported lighting red for a few seconds. | Off |
| **Switch to** | Switches a CPU or GPU profile when the rule fires (choose from "CPU: *name*" and "GPU: *name*"), or **Don't switch profile**. A deleted profile shows as "Missing profile". | Don't switch |

With every action off, the rule only counts in Deck's log.

### How a rule fires

A rule fires **once per stretch** in which it holds: the tests must all be true, continuously, for the "For at least" time; then it fires, and cannot fire again until the tests have stopped holding *and* the wait-before-repeating time has passed. A reading that goes missing breaks the stretch.

### Saving

Rules are edited as a draft. **Save alerts** stores them; **Discard changes** goes back to what was saved. (This is separate from the **Apply changes** bar of the heat alerts and logging above.) If saving fails the message is shown under the rules.

### Example rules

| Goal | Tests | For at least | Actions |
|---|---|---|---|
| Warn about a failing cooler fan | CPU fan speed is below 300 RPM **and** CPU temperature is above 70 | 20 s | Notification + send out |
| Drop to a cooler GPU profile when too hot | GPU temperature is above 83 | 30 s | Notification + switch to a quieter GPU profile |
| Tell me when a render is done | CPU load is below 10 | 120 s | Notification + send out |
| Warn about a hot drive | NVMe drive temperature is above 70 | 60 s | Notification |

Reading names depend on your hardware; pick them from the list.

## Notifications out

Sends chosen messages **over the internet** to your phone or a chat so you can hear about them away from the PC. Nothing is sent anywhere until you turn a destination on **and** tick the kinds of message you want. Everything starts off.

### Destinations

| Destination | What to enter | Notes |
|---|---|---|
| **ntfy topic** | An address like `https://ntfy.sh/your-topic`. | ntfy is a free notification service; install its phone app and subscribe to the same topic. A public topic name is readable by anyone who guesses it, so make it long and random, or use your own ntfy server. Must start with `http://` or `https://` and contain a topic. |
| **Discord webhook** | A webhook address starting `https://discord.com/api/webhooks/…` (or `discordapp.com`). | Create it in your Discord server's channel settings (Integrations > Webhooks). Messages are posted without any mentions (no @everyone). |

### Messages that may be sent

| Tick | Sent when |
|---|---|
| **Alert rules and heat alerts** | One of your alert rules (with *Send it out* ticked) or a heat alert fires. |
| **Drive warnings** | Deck warns that a drive's health changed (needs **Drive health** on in Settings › Notifications). |
| **Shutdown plans** | The warning before a [shutdown plan](power.md) acts. |
| **"Deck closed unexpectedly" reports** | Deck was ended unexpectedly and started again. |

All four default to off. These four are the only things Deck can forward. Every other notification (timers, break reminders, "Downloads finished", fan warnings) stays on this PC.

### Buttons

- **Send a test message** sends "Deck test" to every destination that is switched on and has a valid address, whatever the ticks say, using what you have typed even if you have not saved yet. It tells you what happened ("Sent to ntfy and Discord." or what went wrong, such as an address that does not look right, or the service not being reachable).
- **Save** stores the destinations, ticks and addresses (the **Save** button is enabled when something changed). Rules and destinations are saved together in the same file, so saving one saves any edits to the other.

### Limits and privacy

- The same kind of message goes out at most **once every 30 seconds**, so a flapping sensor cannot spam you.
- Messages contain a title and a short line (for example the rule name and the sensor values, or "Deck ended on its own and was started again"). A message is cut to a safe length (about 1000 characters for ntfy, 1900 for Discord).
- The addresses are saved **encrypted for your Windows account**, so a copy of the file on another account or PC cannot read them. Alert rules and destinations are stored in their own file next to Deck's settings (see [where Deck stores data](settings.md#where-deck-stores-data)); they are **not** part of a Deck backup, so note down your rules and addresses if you move to another PC.
- Messages travel to the service you chose (ntfy or Discord) over the internet. Anyone who can read your topic or webhook can read the messages, so keep the addresses private. Deck sends nothing to anyone else.

## Recommended setup

- **Everyone:** turn on **Warn me when it gets hot** with the defaults (90 °C CPU, 85 °C GPU) and lower them a few degrees if your PC normally runs cool. It is cheap and may save hardware.
- **Desktops you leave running:** set up **ntfy** or a **Discord webhook**, tick **Alert rules and heat alerts** and **"Deck closed unexpectedly" reports**, and press **Send a test message**.
- **Laptops:** a rule with "CPU temperature is above 90 for 30 s" that switches to a lower-power CPU profile can protect a thin laptop in a hot room.
- **Gamers:** keep alerts to notifications; rules that switch profiles in the middle of a game can change performance unexpectedly. Heat alerts do not touch the game.
- **Quiet PCs:** use a rule on a fan RPM rather than only temperature, so a stopped fan is caught before the PC heats up.
- Keep **Wait before repeating** at 5 minutes or more, and give rules at least 10 seconds in **For at least** so one spike does not trigger them.

## Troubleshooting

**I never get a heat notification.** Turn on **Warn me when it gets hot** and press **Apply changes**. The limit must be reached by the CPU or GPU temperature Deck reads. The CPU temperature needs Deck to run as admin on many PCs. Windows "Focus assist" / "Do not disturb" can hide toasts: check your notification settings.

**The tab is empty or says it could not load.** The alert settings load when the tab opens; close the page and open it again. If Sensors itself shows nothing, the hardware engine is not running (see [Sensors](sensors.md)).

**A rule never fires.** Check its switch is on, that every test holds at once, and that "For at least" is not longer than the condition lasts. A test whose reading says "(not found now)" can never be true; choose it again. Also check it is not still in its **Wait before repeating** period.

**A rule fires too often.** Raise **Wait before repeating** and **For at least**, or move the limit.

**"Send a test message" says the address does not look right.** ntfy needs `http(s)://host/topic`; Discord needs a full `https://discord.com/api/webhooks/…` address.

**"ntfy/Discord answered with an error" or "could not be reached".** Check the address, your internet connection and that the topic / webhook still exists.

**Messages arrive only occasionally.** Each kind is limited to one per 30 seconds, and each rule has its own wait time.

**The flash-the-lights option is missing.** It only shows on a PC with lighting Deck can control; see [Lighting](lighting.md).

**The profile I chose says "Missing profile".** It was deleted. Pick another profile or "Don't switch profile".

## FAQ

**Do alerts work when Deck is closed to the tray?** Yes. They stop only if you quit Deck.

**Do alerts affect games or anti-cheat?** No. They read Deck's own sensor readings and show notifications. Deck never injects into games or reads their memory.

**Can alerts slow my PC down?** No. Rules are checked once a second against readings Deck already has.

**Is anything sent to Deck's author or any other third party?** No. Notifications out only goes to the ntfy or Discord address you typed, and only for the kinds you ticked.

**Can I send alerts by email or SMS?** Not directly. ntfy can forward to those if you set that up on the ntfy side.

**What does "Alert rules" do that "Temperature alerts" does not?** Rules can watch any reading, combine up to four conditions, run for a set time, send messages out and switch CPU / GPU profiles. Temperature alerts are a simple CPU and GPU temperature warning.

**Does a Deck backup include my alert rules?** No. The temperature alert switch and limits are part of the hardware settings and are backed up, but alert rules and the ntfy / Discord addresses are not. See [Settings](settings.md#backups).
