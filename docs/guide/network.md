Where to find it: Diagnostics › Network

# Network

Find out why your connection lagged, test its speed and lag under load, ping game servers and see the data each app uses.

Five tabs: **Lag spikes** (opens first), **Connection**, **Game servers**, **Tests** and **Data per app**.

Deck only sends ordinary pings and test transfers. It never touches a game or reads its memory. About a game's traffic it reads only how many packets Windows saw, from the same events Task Manager uses. Speeds are in Mb/s by default; **Settings › Appearance › Performance & units** switches to MB/s.

## Lag spikes

The top card is the **Last lag spike**:

- When, how long and in which game, for example "Today 21:14 · 4 s · ELDEN RING". A spike found when no game was in front is marked **Found by the one-minute recorder**.
- What was measured: the delay before and at its worst ("Delay 14 ms → 180 ms"), lost pings, and "Game got no data for 0.8 s" when the game's own traffic stopped.
- **Path**: **This PC**, **Router**, **Provider**, **Internet**, each **Fine**, **Bad** or **No data**. A chip names where trouble starts: **Starts on this PC**, **Starts at your router**, **Starts at your provider**, **Starts past your provider**, or **Game server or its route** when every ping was fine but the game got no data.
- **At the same time**: other apps' network use around the spike (uploads first, with Windows Update and OneDrive named) and Wi-Fi events: a scan, a move to another access point, a drop, the lowest signal.
- **Suspected**: one likely cause, such as an upload filling the line. **Not enough data** when nothing points anywhere. A suspicion is not proof.
- **Trace now** traces the path now, not at the spike (see [Trace the path](#trace-the-path)).

**Spikes · 24 h** lists every spike of the last day; pick one to show it above. **Copy report** copies the last day's moments as text, with addresses, the PC name and user folders removed.

### Recording

**Record lag** turns on Connection quality and Data per app together. When it is off, the tab shows **Start recording**.

**Fast pings** catch the short spikes a once-a-minute check misses. They run only while recording is on and a game is in front:

| Fast pings | While a game is in front | Network use |
| --- | --- | --- |
| **Normal** (default) | Router, your provider's first router and 1.1.1.1, 4 pings a second each | About 14 kb/s |
| **Low** | The same, 1 ping a second each | About 4 kb/s |
| **Off** | Only the one-minute recorder | None |

A spike is a delay more than double the usual and 30 ms higher for over half a second, or two or more lost pings close together. Deck keeps each spike with 30 seconds around it (the last 200, up to a week). With Data per app on, Deck also sees when the game stopped getting data while it kept sending. Your provider's first router is found once after each network change, never during a game.

Spikes also show in [session reports](gaming.md#session-reports) unless you turn off **Add connection quality to reports** there.

## Connection

The verdict shows how many lag spikes there were today; click it to open Lag spikes.

### Traffic now

- **Download** and **Upload**: the whole PC's speed now, with a one-minute graph.
- **Local IP**: your PC's address on your network. Click to copy.
- **Public IP**: hidden until you press **Reveal public IP**, so a screenshot doesn't leak it. Revealing makes one request to a lookup service (ipify).
- **PC name**: your computer's network name.

### Connection quality

Off by default; turn on **Record history**. While Deck runs, it sends a few pings a minute to:

- **Router**: problems here are inside your home (Wi-Fi, cable, router).
- **Internet**: 1.1.1.1. Problems here with a fine router are on your provider's side.

Choose **24 hours**, **7 days** or **30 days**. Each line shows average delay, jitter and **Probe loss** (pings without a reply). Each bar of the graph runs from the lowest to the highest delay. Deck keeps 10-minute averages for 30 days and one-minute samples for 24 hours, on your PC only.

Probe loss is not game packet loss: routers and servers may ignore pings on purpose.

**Watched targets · recorded**: up to three addresses of your own (a game server, a work VPN), pinged 3 times a minute. **Add target** adds one. **Clear history** deletes the record; turning the switch off keeps it.

Turn it on when you have drops you can't reproduce. After a few days, look at when it goes wrong.

### Trace the path

Press **Trace now** on a spike, or **Trace** in **Trace the path** on Tests. It checks the path now, not at the time of a spike. IPv4 only.

1. Deck sends up to three pings to each hop, for up to 30 hops (about 90 seconds).
2. Each row shows the hop's address, **Probe loss** and min, average and max delay. **Stop** keeps the partial result.
3. Read the note under it. "This hop may ignore pings (often normal)" is common; no result proves game packet loss.

During a game a trace waits. The last five traces are kept under **Saved path trace**.

## Game servers

The delay from your PC to the regions a game's servers run in.

- Valve games (Counter-Strike 2, Dota 2, Deadlock, Team Fortress 2): Valve's relay servers in each city.
- Games on Amazon servers (Fortnite, Rocket League, Dead by Daylight and others): Amazon's game-ping regions.
- **Any game on…** a network, for a game that isn't listed.

These are stand-in servers per region, not your match's server, so a real match can differ a little.

1. Pick a game. Installed games come first; use **Find a game** or **Show all games**.
2. The first look tests it (about 3 seconds). **Test again** repeats it.
3. Read each region's delay and loss. **Lowest delay** is at the top. Under 60 ms is good, under 110 ms is fair.

Pin a game to keep it at the front. **Add a game…** adds one that isn't listed: name it and choose **Amazon servers (AWS)** or **Valve's network**. Only add one if you know its network. **Remove** deletes a game you added.

## Tests

### Speed test

**Run speed test** measures **Download**, **Upload**, ping and **Jitter** against Cloudflare. It takes up to 18 seconds and moves as much data as your line can (several hundred MB on a fast line). **Cancel** keeps the last result.

For the best result, pause other downloads and use a cable. Avoid running it often on a limited data plan.

### Lag while busy

Does a download make your games or calls lag? Too much queuing in the router is called bufferbloat.

1. Press **Run the check**. It takes about 20 seconds and uses up to 185 MB down and 100 MB up.
2. Deck measures the delay with the line quiet, then while 4 downloads fill it, then while 4 uploads fill it.
3. Read the grade, the worse of the two directions.

| Grade | Delay rise | Meaning |
| --- | --- | --- |
| A+ | Under 5 ms | No extra lag. |
| A | Under 30 ms | No real extra lag. |
| B | 30 ms or more | A little extra lag. |
| C | 60 ms or more | Noticeable in fast games. |
| D | 200 ms or more | Big transfers are felt in games and calls. |
| F | 400 ms or more, or over 10 % of replies lost | Very laggy while busy. |

**Line not filled** means the check moved less than half of your last speed test, so the grade may look too good. **Test details** has the numbers. From grade C, Deck suggests **Try Smart Queue on the router** (SQM), the usual cure. Deck changes no router settings.

Each finished check is saved (the last 20). Type a label (for example "new router") and select two to compare. **Delete** asks **Delete for good?** first.

### Before a test starts

Deck never starts a test or trace on its own. If a game is in front, or Deck's phone mic or voice holds the microphone, it says what the test would disturb and waits for **Run anyway** or **Cancel**. Deck can't see calls in other apps, so pause those yourself.

### Live ping

Pings only while you watch. The list starts with 1.1.1.1, 8.8.8.8 and discord.com.

- **Start pinging** and **Stop pinging**. Leaving the page stops it.
- Each address shows its last 60 rounds, the latest delay, the average and the loss. **No reply** means a ping timed out.
- Type an address or name in **Add an address** and press **Add**. The cross removes one.

## Data per app

How much each program downloaded and uploaded, to find what uses your data or bandwidth. Off by default; turn it on with the card's switch. It needs administrator and installs no driver.

- Counts only while Deck runs, per program per day, kept 30 days on your PC.
- Choose **Today**, **7 days** or **30 days**. Apps are listed biggest first.
- The selected app shows **Last seen** and **Data per day**.
- **Clear totals** deletes the counts.

**New app notice** (off by default, set in **Settings › Notifications**): after 7 days of counting, one notice when a program with no earlier traffic moves more than the size you chose in a day.

## Recommended setup

- **Gamers:** run **Lag while busy** once. At C or worse, turn on SQM on your router or pause big downloads while you play. Use **Game servers** before picking a region. Keep **Record lag** on to see why a match lagged.
- **Laptops on Wi-Fi:** the **Router** line of Connection quality separates Wi-Fi trouble from provider trouble.
- **Limited data plans:** turn on **Data per app** and don't run the speed test often.

## Troubleshooting

**The speed test is lower than my plan.** Wi-Fi, a busy network or a VPN lowers results. Test by cable with other downloads paused.

**The speed test fails.** Usually no internet, or a firewall or VPN blocking Cloudflare.

**Data per app shows an error.** It needs administrator. See [Getting started](getting-started.md#why-deck-needs-administrator). Right after you turn it on it says it is counting until some traffic is seen.

**Some game regions say No reply.** Some networks block pings. The other regions still compare.

## FAQ

**Does this send my data anywhere?** The speed test and lag check use Cloudflare's test servers. Pings go to the addresses you see. Revealing the public IP asks a lookup service. History and totals stay on your PC.

**Does anything run in the background?** Only Connection quality, fast pings during games and Data per app, if you turned them on, and only while Deck runs.

**Can I run tests during a game?** Run them outside matches: they use bandwidth and add delay. A trace waits until the game leaves the front.

**How do I delete what Deck recorded?** **Clear history** (Connection quality) and **Clear totals** (Data per app).
