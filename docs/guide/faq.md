Where to find it: Settings › About

# Frequently asked questions

Short answers to the most common questions, each with a link to the page that has the detail. For problems, see [Troubleshooting](troubleshooting.md).

## Safety and anti-cheat

**Will Deck get me banned?**
Deck never injects code into a game, never reads game memory and installs no hooks. It uses ordinary Windows calls (power plans, window positions, volume), and the in-game overlay is drawn by RivaTuner, which anti-cheat systems already accept. Pages with their own answer: [Game profiles](gaming.md#faq), [Performance overlay](overlay.md#faq), [Deck bar](game-bar.md#faq), [Controller](controller.md#faq), [Death counter](death-counter.md#faq).

**Is there any exception?**
One: the FACEIT anti-cheat refuses to run while Deck's hardware driver (PawnIO) is loaded. While FACEIT runs, Deck hands the fans to the BIOS, stops using the driver and tells you why. Fan control, CPU temperature and board lighting pause until FACEIT closes. See [Fans](fans.md#what-happens-with-anti-cheat).

**Is it safe to leave Deck running all the time?**
Yes. If Deck is ended from outside, a small helper hands the fans and graphics card back to the BIOS and driver ([Settings](settings.md#restart-after-a-crash)).

**Can hardware tuning damage my PC?**
Deck stays inside what your hardware and driver allow, and adds guards: fans go to 100 % when the CPU reaches 85 °C, and after an unexpected restart an overclock is held back. Overclocking, undervolting and fan changes can still make a PC unstable or hot, as with any tool. Read [CPU](cpu.md#faq), [GPU](gpu.md#faq) and [Fans](fans.md#faq) first.

**Can Windows tweaks break Windows?**
Most tweaks are easy to undo. Advanced ones can lower protection or stability, so they ask for a restore point and a review. Undo restores settings, not deleted data. See [Windows tweaks](tweaks.md#faq).

**Is the phone remote safe?**
The connection is encrypted and each request is signed with a key that never leaves your devices. Treat the pairing code like a password and press **Make a new code** after sharing it. See [Phone](phone.md#faq).

## What Deck changes and how to undo it

Deck only changes what you ask for, and keeps the old values. Press **Activity** at the top of any page to see what Deck is holding now and **Undo** it ([Home](home.md#what-deck-changed)).

| Area | How to undo |
|---|---|
| Fans | Set fans to **Motherboard decides** and press **Apply hardware changes**, or quit Deck. Deck never changes BIOS settings ([Fans](fans.md#faq)). |
| GPU | **Reset GPU**, or restart the PC ([GPU](gpu.md#faq)). |
| CPU | Switch profile. The clock floor ends when Deck quits; a turbo overclock stays until the PC restarts ([CPU](cpu.md#faq)). |
| Windows tweaks | Undo one or all, even months later ([Windows tweaks](tweaks.md)). |
| Sound | **Reset changes** on Mixer › Devices ([Mixer](sound.md#faq)). |
| Display | **Reset changes**; brightness and color also return when Deck quits ([Display](display.md)). |
| Deck game mode | Deck undoes it when the game closes, or at the next start after a crash ([Game profiles](gaming.md#faq)). |
| Uninstalled apps | Files go to the Recycle Bin; registry keys and services are backed up first ([Apps](apps.md#faq)). |
| RivaTuner | **Restore RivaTuner's own look** ([Performance overlay](overlay.md#faq)). |

Deck does not turn off Windows Defender or Windows Update. What Deck stores and where: [Settings](settings.md#where-deck-stores-data).

## Administrator

**Does Deck need administrator?**
For fans, CPU and GPU tuning, CPU temperature, drive health, lighting, most Windows tweaks and silent updates, yes. The rest works without it. Programs Deck opens start as your normal account. See [Getting started](getting-started.md#why-deck-needs-administrator).

**A page says "Needs administrator". What do I do?**
Press **Restart as administrator** and accept the one Windows prompt. Deck creates its own scheduled task, so it starts with those rights from then on. See [This PC](this-pc.md#administrator-access).

**Can another program borrow Deck's rights?**
Deck refuses to set up admin start for a copy in a folder a normal program could change. It also refuses hardware settings files edited behind its back until you press **Apply them** ([CPU](cpu.md#faq)).

## What leaves your PC

**Does Deck collect data about me?**
No. There is no account, and nothing is uploaded on its own. The features that use the internet (updates, game artwork, currency rates, speed tests, alerts to ntfy or Discord) are listed in [Privacy: what leaves your PC](settings.md#privacy-what-leaves-your-pc). Phone, PC to PC and Project sync talk only to your own devices and are off until you turn them on.

**Do the support report and logs hold personal data?**
File paths are shortened, serial numbers are left out, and secrets, your user name and PC name are hidden. Crash files are added only if you choose to ([Settings](settings.md#support-report)).

**Can I use Deck offline?**
Yes. Only updates, artwork, currency rates and speed tests need the internet.

## Hardware

**Does Deck work on AMD processors?**
Yes. CPU profiles on Windows power plans work on any CPU. Power limits and the clock lock are Intel only, and turbo ratios need an unlocked Intel CPU ([CPU](cpu.md)).

**Does Deck work with AMD or Intel graphics?**
Yes for sensors, the overlay, game profiles and session reports. GPU tuning and Target FPS need an NVIDIA card ([GPU](gpu.md)).

**Does it work on laptops?**
Yes, with limits. Laptops usually control their own fans; Deck can drive HP laptop fans. See [Recommended setups](recommended.md#laptop-on-battery) and [This PC](this-pc.md), which shows what Deck can and can't control.

**Safe Mode or ARM PCs?**
Deck starts, but changes no fans, lights or graphics settings, and the hardware pages say why.

**Why is a page missing from the sidebar?**
Hardware pages hide themselves when your PC has nothing Deck can use for them. Check [This PC](this-pc.md#what-deck-controls).

**Which fan chips are supported?**
Nuvoton NCT668x / NCT679x and ITE chips (most MSI, ASUS, Gigabyte and ASRock boards) and HP laptops. See [Fans](fans.md).

**Can I use MSI Afterburner or my board's fan software too?**
Not for the same job at the same time: two programs writing the same settings fight. Deck can import Afterburner profiles ([GPU](gpu.md#faq)). For the overlay, RivaTuner alone is enough.

## Performance

**Does Deck slow down my games?**
Very little. Sensors update once a second (slower for heavy ones during games), and updates, tweaks and hardware changes wait until no game is in front.

**Can I make Deck lighter?**
Turn on **Low-spec mode** ([Settings](settings.md#performance--units)) and turn off features you don't use. More in [Troubleshooting](troubleshooting.md#high-cpu-use-or-deck-feels-heavy).

## Crashes, backups and updates

**What if Deck crashes?**
The fans and GPU fan go back to the BIOS and driver, then Deck starts again hidden (**Restart after a crash**). After three crashes in ten minutes it stops and starts safe ([Settings](settings.md#restart-after-a-crash)).

**What if the PC crashes during a game?**
At the next start Deck undoes the game mode changes and holds back overclocked profiles until you apply them again ([GPU](gpu.md#crash-guard-and-applying-again)).

**How do I back up Deck?**
Settings › Data & recovery: **Export my setup**, or turn on **Weekly backup** ([Settings](settings.md#backups)).

**How do I move to a new PC?**
Install Deck, then restore your backup. Use **Include secrets** with a password if you want the phone key too. After a restore, connections and automatic features stay off until you turn them on. Windows tweaks can go with [PC to PC](pc-to-pc.md).

**How does Deck update?**
It checks daily and installs when no game is in front, only if the setup carries Deck's signature and matching checksum. Turn off **Update automatically** to check by hand ([Settings](settings.md#updates)).

**How do I uninstall Deck?**
Windows Settings › Apps › Installed apps › Deck. See [Getting started](getting-started.md#uninstalling).

## Features

**Can Deck remap keys or mouse buttons?**
No, on purpose. Remapping needs a hook on every key press, and Deck installs none. Use your keyboard's or mouse's own software.

**Does the death counter work in every game?**
Yes, once you count a death there. Known games count automatically ([Death counter](death-counter.md#faq)).

**Does Clipboard replace Win+V?**
No, both work side by side ([Clipboard](clipboard.md#faq)).

**Can I get alerts on my phone?**
Yes, through ntfy or a Discord webhook ([Alerts](alerts.md#faq)).

**Can the phone work away from home?**
Yes, through Tailscale. Deck never opens your router ([Phone](phone.md#faq)).
