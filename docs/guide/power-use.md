Where to find it: PC status › Power use

# Power use

How much power the whole PC draws now, the energy it used today and this month, what that costs, and on a laptop, which apps drain the battery.

It is one page with no tabs. Nothing on it changes your PC; the settings only change how Deck estimates and prices the energy.

## Order of the page

1. **Whole PC**: **Now**, **Today**, **This month** and **Gaming this month**
2. **Month by part** beside **Per day**
3. **Price and supply**
4. **Apps on battery** (PCs with a battery only)

## Whole PC

- **Now** is the whole PC's draw in watts, read every 5 seconds. Point at it to see the CPU and GPU (measured) and the rest of the PC and PSU loss (estimated).
- **Today**, **This month** and **Gaming this month** are in kWh, with the cost when you set a price. Point at a figure to see how long was measured. Sleep and gaps never count as measured time.
- Before anything is measured the card says "Counted while Deck runs; nothing measured yet". Energy needs both the CPU and the graphics card power.

How it is counted: the processor's package power and the graphics card's board power are measured. The rest (memory, drives, motherboard, fans, pump, the lights Deck drives, USB devices) is estimated from what Deck knows about each part. The total is divided by the power supply's efficiency at that load, and the difference is the **PSU loss**. The **Rest of PC estimated** chip and the **?** in the heading say the same.

## Month by part

A bar and up to five rows for this month: **CPU** and **GPU** (**Measured**), **Rest of PC** and **PSU loss** (**Estimated**), and **Monitors** (**Your figure**) when you count them.

## Per day

The last five measured days: date, a bar, hours measured, kWh and the cost. **Show N more** lists up to 31 days.

## Price and supply

- **Price per kWh**: your price in your own currency, from 0 to 10000. Leave it blank to hide costs.
- **Power supply**: its 80 PLUS rating and watts (Gold, 750 W until you pick yours). Deck estimates the PSU loss from it.
- **Count monitors**: off by default. On, it adds the watts you type for the whole time.

The estimates are typical figures from datasheets and reviews. Only a wall meter is exact.

## Apps on battery

On a laptop running on battery, this card estimates each app's draw in watts, because Windows shows only percentages.

- Each app gets its share of the processor and graphics use, times the measured CPU and GPU power (**From CPU and GPU power**). Where those are missing, Deck shares out the battery's draw above the lowest seen since unplugging (**From battery draw**).
- The total at the top is the battery's draw. **Screen and rest** is what no app is charged for (screen, memory, Wi-Fi, idle).
- Helpers count toward the app that started them. The list averages the last half minute and is marked **Estimate**.
- Plugged in, the card says **Plugged in** and lists nothing. Desktops don't show the card.

## Elsewhere in Deck

- [Home](home.md)'s PC status tile: **Energy** opens this page.
- **Game profiles** › a game › **Power**: **Power use** opens this page.
- **Power & time › Keep awake**: the **PC status › Power use** link at the end of the tab row.
- Each [session report](gaming.md#session-reports-in-diagnostics) has an energy estimate for that game session.

## FAQ

**Why is the figure lower than my wall meter?** Only the processor and graphics card are measured. Set your power supply and count your monitors to come closer.

**Where is it stored?** In Deck's data folder on this PC. Nothing is sent anywhere.
