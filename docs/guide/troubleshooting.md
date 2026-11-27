Where to find it: Settings › About

# Troubleshooting

Problems by symptom, with the first steps and a link to the page that has more. Each feature page also ends with its own Troubleshooting section.

If nothing here helps, see [Getting the log and a support report](#getting-the-log-and-a-support-report).

## Deck is still starting

Deck shows this while its background part is slow to answer. It keeps trying and opens on its own when ready. **Try again** skips the wait.

## A setting is grayed out or says "Needs administrator"

[This PC](this-pc.md#what-deck-controls) tells you whether Deck or your hardware is the limit. There are three causes:

1. **Deck isn't running as administrator.** The page shows **Needs administrator**, or Home's CPU card shows **Admin**. Press **Restart as administrator** and accept the prompt. If it keeps coming back, reinstall with the setup ([Getting started](getting-started.md#why-deck-needs-administrator)).
2. **Your hardware doesn't offer it.** For example GPU tuning needs a supported NVIDIA card, and power limits are Intel only. This is not a fault.
3. **Something is in the way.** A game in front blocks Windows changes, updates and calibration until you leave it. Another program (Afterburner, a maker's fan or RGB tool) may be fighting Deck. After **Hardware settings were changed outside Deck**, press **Apply them** only if you made the change.

## A page is missing from the sidebar

- Hardware pages hide themselves when your PC has nothing for them. Open [This PC](this-pc.md) to see what Deck found.
- Pages you hid: **Show everything** in [Settings › Features](settings.md#features) brings them back. Project sync is shown from there too.
- Order changed: **Reset order** in [Settings › General](settings.md#sidebar).
- The GPU page needs an NVIDIA card. AMD and Intel graphics appear in [Sensors](sensors.md).

## Something doesn't show over a game

Exclusive fullscreen hides every window drawn over a game. Switch the game to borderless or windowed first.

- **Performance overlay:** RivaTuner must be running; open it with **Open RivaTuner**. Some protected games can't be drawn on. See [Performance overlay](overlay.md#troubleshooting).
- **Controller overlay:** check **Hide without a controller** and press a button on the pad ([Controller](controller.md#troubleshooting)).
- **Deck bar:** try **Open now** with the game in front ([Deck bar](game-bar.md#troubleshooting)).
- **Death counter on screen:** check **Show in games** ([Death counter](death-counter.md#troubleshooting)).
- **Music & volume pop-ups:** see [Music & volume pop-ups](flyouts.md#troubleshooting).

## Fans are not controlled

1. No Fans page: your PC has no fans Deck can control (laptops usually run their own), or Deck needs administrator.
2. The page is read only: the banner says why, such as an unverified board (**Unverified fan control**) or an anti-cheat client like FACEIT.
3. Nothing changed: edits wait until you press **Apply hardware changes**.
4. A fan runs faster than its curve: a safety rule is active, for example the CPU at 85 °C.
5. Fans went back to the BIOS: that is the safe fallback after a crash, a quit or a change made outside Deck.
6. Graphics card fans are set in the GPU profile, not on the Fans page.

More in [Fans](fans.md#troubleshooting).

## GPU options are grayed out or missing

- The GPU page needs an NVIDIA card and its driver, and Deck running as administrator.
- Missing controls: the card or driver doesn't offer them.
- "GPU asleep": the card is powered down, common on laptops. It wakes when a program uses it.
- Settings gone after a restart: choose a **GPU profile when Deck starts**. After an unexpected restart an overclock is held back (**Overclock held back**) until you apply it again.
- Afterburner also tuning: close it or stop its startup profile.

More in [GPU](gpu.md#troubleshooting).

## The phone can't connect

1. Update the phone app after updating Deck.
2. Set the Windows network to Private. Deck's firewall rule doesn't cover Public networks.
3. Both devices on the same network, **Phone connection** on, Deck running as administrator.
4. Away from home: Tailscale on and signed in on both devices with the same account.

More in [Phone](phone.md#troubleshooting).

## The death counter isn't counting

1. Check **Counting on** and **Watch for death screens**, and play in borderless or windowed mode.
2. Count the first death by hand in a game Deck doesn't know yet.
3. Read the status line on the counter's page for what Deck sees.

More in [Death counter](death-counter.md#troubleshooting).

## Others can't hear my mic

Open Audio › Mic and read **Others hear** and the **Setup check**: each row says what to fix. See [Mic](voice.md#setup-check).

## Lag or stutter in games

- Network lag: Diagnostics › Network › **Lag spikes** shows when the delay rose and where on the path ([Network](network.md#lag-spikes)).
- Stutter: open the game's session report in Diagnostics › Session reports ([Game profiles](gaming.md#session-reports)).
- PC crashes or freezes: Diagnostics › Crashes lists what Windows recorded ([Crashes](crashes.md)).

## High CPU use or Deck feels heavy

1. Turn on **Low-spec mode** ([Settings](settings.md#performance--units)).
2. Turn off what you don't use: **Watch for death screens**, the controller overlay, phone screen streaming.
3. In [Sensors](sensors.md), turn on **Slower in games** and turn off **Log to file**.
4. In [Network](network.md), connection history and data per app run only if you turned them on.
5. Fewer folders in Local file search ([Settings](settings.md#local-file-search)).

## Deck won't start or open

1. It may already be running: look for the tray icon under the up arrow. The **X** only hides Deck.
2. Start it from the Start menu.
3. After three crashes in ten minutes Deck stops restarting itself. Start it by hand; it comes up safe ([Settings](settings.md#restart-after-a-crash)).
4. "Couldn't save settings": Deck can't write its settings folder (read only, full or locked). It keeps trying; keep Deck open until the message clears.
5. SmartScreen blocks the setup: click **More info**, then **Run anyway** ([Getting started](getting-started.md#installing)).

## After a crash or an unexpected restart

Deck does this on its own:

- Fans and the GPU fan go back to the BIOS and driver within seconds ([Fans](fans.md#what-happens-if-deck-crashes-or-quits)).
- Deck starts again hidden (**Restart after a crash**).
- Overclocked profiles are held back until you apply them again.
- Deck game mode, sound and phone changes are undone at the next start.
- Windows tweaks keep their old values, so Undo still works.

To see what happened, open [Crashes](crashes.md).

## Getting the log and a support report

### The support report

1. Open Settings › About › **Support report** ([Settings](settings.md#support-report)).
2. **Copy report** puts it on the clipboard; **Save report** writes a file and shows it in Explorer.
3. Turn on **Include crash files (may contain private data)** only if asked or after a crash.

The report leaves out file paths, serial numbers and secrets. Read it before posting if you're unsure.

### The log file

The log is `%LOCALAPPDATA%\Deck\logs\deck.log`. Paste that path into File Explorer's address bar. Secrets, your user name and PC name are hidden.

To log more about one problem, set that area to **Debug** in **Log detail by area**, repeat the problem, then take the report and set it back to **Normal** ([Settings](settings.md#diagnostics)).

### Where to ask

Report bugs on the project's public releases repository on GitHub (`deck-releases`), with the support report attached. Report security problems privately, as `SECURITY.md` in the repository describes.
