Where to find it: PC status › Sensors

# Alerts and notifications out

Get told, or have Deck act, when a sensor goes wrong, and send chosen alerts to your phone or a chat.

Everything here is on the **Alerts** tab of [Sensors](sensors.md), from top to bottom:

1. **Temperature alerts**: the simple CPU and GPU heat warning.
2. **Sensor logging**: an optional log file.
3. **Alert rules**: your own rules on any sensor.
4. **Quiet during games**: hold alerts while you play.
5. **Send alerts to…**: ntfy and Discord.

Alerts are checked while Deck runs, also when it is only in the tray. Changes on this tab are a draft until you press **Apply changes** in the bar at the bottom (or **Discard changes**).

## Temperature alerts

| Setting | What it does | Default |
| --- | --- | --- |
| **Temperature alerts** | A Windows notification when the CPU or GPU goes above your limit. Catches a stopped fan or a clogged filter. At most one notification every 5 minutes per part. | Off |
| **CPU above** | 60 to 105 °C. | 90 °C |
| **GPU above** | 60 to 100 °C. | 85 °C |
| **Flash lights red** | A few seconds of red on the lights per alert, on PCs with lighting Deck controls. | Off |

Choosing limits: most CPUs run 60 to 85 °C under load, and many touch 90 to 100 °C briefly by design. Most graphics cards sit at 65 to 85 °C in games. Set the limit a little above your normal gaming temperature. The alert only tells you; it slows nothing down.

## Sensor logging

**Log to file**, **Slower in games** and **Open folder** are described in [Sensors](sensors.md#the-alerts-tab).

## Alert rules

A rule watches one or more sensors and acts when all its conditions stay true for a set time. Any sensor Deck reads can be used. Deck offers starters that match your PC: **CPU too hot**, **GPU too hot** and **Fan stopped**.

1. Press **Add an alert** (up to 20).
2. Give it an **Alert name**. It becomes the notification title.
3. Under **When all of these are true:**, pick a **Sensor**, **is above** or **is below**, and a **Value**. **Add condition** adds up to four.
4. Set **For at least** (0 to 600 seconds), so short spikes are ignored.
5. Set **Wait before repeating** (1 to 120 minutes).
6. Choose the actions: **Show a notification**, **Send to phone or chat**, **Flash lights red**, and **Switch to** a CPU or GPU profile (or **Don't switch profile**).
7. Press **Apply changes**.

A rule fires once each time its conditions hold for the whole time, then waits. A sensor that disappears shows "(not found now)" and its rule can't fire. A deleted profile shows **Missing profile**.

Examples:

| Goal | Conditions | For at least | Actions |
| --- | --- | --- | --- |
| A failing CPU fan | CPU fan below 300 RPM and CPU temperature above 70 | 20 s | Notification, send out |
| Cool down a hot GPU | GPU temperature above 83 | 30 s | Notification, switch to a quieter GPU profile |
| A render is done | CPU load below 10 | 120 s | Notification, send out |

## Quiet during games

**Hold alerts while a game is in front** (on by default): **Custom and temperature alerts** and **Drive warnings** wait during a game and show once, about ten seconds after you leave it. Shutdown warnings and crash reports are never held, and messages to your phone or chat still go out.

## Send alerts to…

Sends chosen messages over the internet to your phone or a chat. Nothing is sent until you turn on a destination and choose what to send. Everything starts off.

| Destination | What to enter |
| --- | --- |
| **ntfy topic** | An address like `https://ntfy.sh/your-topic`. Install the ntfy phone app and subscribe to the same topic. Anyone who guesses a public topic can read it, so make it long and random. |
| **Discord webhook** | A `https://discord.com/api/webhooks/…` address, from the channel's Integrations settings. Messages mention nobody. |

**Messages to send:**

| Choice | Sent when |
| --- | --- |
| **Custom and temperature alerts** | A temperature alert fires, or a rule with **Send to phone or chat** on. |
| **Drive warnings** | A drive's health changes. |
| **Shutdown plans** | The warning before a [shutdown plan](power.md) acts. |
| **"Deck closed unexpectedly" reports** | Deck was ended and started again. |

Nothing else is ever forwarded. **Send a test message** sends "Deck test" to every destination that is on, using what you typed.

Privacy:

- The same kind of message goes out at most once every 30 seconds.
- The addresses are saved encrypted for your Windows account.
- Alert rules and addresses are not part of a Deck backup. Note them down before moving to another PC.
- Messages go only to the address you entered.

## Recommended setup

- **Everyone:** turn on **Temperature alerts** with the defaults.
- **PCs left running:** set up ntfy or Discord, choose **Custom and temperature alerts** and **"Deck closed unexpectedly" reports**, and press **Send a test message**.
- **Thin laptops:** a rule "CPU temperature above 90 for 30 s" that switches to a lower-power CPU profile.
- **Gamers:** keep rules to notifications; switching profiles mid-game changes performance.
- Give rules at least 10 seconds in **For at least** and 5 minutes in **Wait before repeating**.

## Troubleshooting

**No heat notification.** Turn on **Temperature alerts** and press **Apply changes**. CPU temperature needs administrator. Windows' Do not disturb can hide notifications.

**A rule never fires.** Check its switch, that all conditions hold at once, and that **For at least** isn't longer than the problem lasts. Choose again any sensor marked "(not found now)".

**A rule fires too often.** Raise **For at least** and **Wait before repeating**, or move the limit.

**The test message fails.** ntfy needs `https://host/topic`; Discord needs a full webhook address. Check the internet connection and that the topic or webhook still exists.

## FAQ

**Do alerts affect games or anti-cheat?** No. They only use sensors Deck already reads and show notifications.

**Is anything sent to anyone else?** No. Only to the ntfy or Discord address you entered, and only what you chose.

**Can I get alerts by email or SMS?** Not directly; ntfy can forward them if you set that up on its side.

**Does a Deck backup include my rules?** The temperature alert settings, yes. Alert rules and addresses, no. See [Settings](settings.md#backups).
