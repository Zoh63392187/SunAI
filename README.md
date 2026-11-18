# SunAI

[![Latest version](https://img.shields.io/github/v/release/Zoh63392187/SunAI?label=latest%20version)](https://github.com/Zoh63392187/SunAI/releases/latest)
[![Released](https://img.shields.io/github/release-date/Zoh63392187/SunAI?label=released)](https://github.com/Zoh63392187/SunAI/releases/latest)
![Windows](https://img.shields.io/badge/Windows-10%20%7C%2011%20(64--bit)-0078D4)
![Vendor](https://img.shields.io/badge/inverter-Growatt-2E7D32)

**Smart, simple control of a Growatt hybrid inverter with battery – for Windows 11.**

SunAI replaces the many menus of the inverter's own app with big, clear buttons, a visual 24-hour schedule and an
automatic planner that charges and uses your battery when electricity is cheap or expensive.

> SunAI is an independent program. It is not developed by, approved by or affiliated with Growatt.
> SunAI changes settings on a real inverter. Every change is shown before it is sent, read back afterwards and logged,
> and you can always roll back or choose a safe default.

**[⬇ Download the newest version](https://github.com/Zoh63392187/SunAI/releases/latest)** – the file is `SunAI.exe`.

---

## At a glance

| | |
|---|---|
| **Inverter vendor** | Growatt only (through Growatt's official Open API) |
| **Fully supported** | Growatt **SPH / MIX** hybrid inverters with battery – read and control |
| **Schedules supported** | Growatt **MIN / TLX** – read and time-period schedules |
| **Read only** | Other Growatt types (Inverter, Storage, MAX, SPA, PCS, HPS, PBD) – live values, no control |
| **Inverters per PC** | Up to **10**, all controlled at the same time or one at a time (your choice) |
| **Inverters per server licence** | **1** as standard; licences for more (up to 50) on request |
| **PCs per licence** | 2 as standard |
| **Growatt servers** | Europe (default), USA, China, Australia |
| **Electricity prices** | Nord Pool day-ahead (Denmark DK1/DK2) and Danish grid tariffs |
| **Languages** | English (default) and Danish |
| **Runs on** | Windows 10 or 11, 64-bit – one file, nothing else to install |
| **Latest version** | See the badge above or [Releases](https://github.com/Zoh63392187/SunAI/releases/latest) |

## Version history

| Version | Date | What's new |
|---|---|---|
| [0.19.0](https://github.com/Zoh63392187/SunAI/releases/tag/v0.19.0) | 2026-11-18 | Several inverters: add more inverters in Settings, switch at the top left, and let the server control several per licence |
| [0.18.1](https://github.com/Zoh63392187/SunAI/releases/tag/v0.18.1) | 2026-11-18 | Built-in server keys and one-click server install, separate signing key for updates |
| [0.18.0](https://github.com/Zoh63392187/SunAI/releases/tag/v0.18.0) | 2026-11-18 | Server mode with licence (the SunAI server controls the battery 24/7), signed updates from GitHub, new Server and updates page |

All versions: [Releases](https://github.com/Zoh63392187/SunAI/releases).

---

## What it does

- **Overview** – solar power, house consumption, grid import/export, battery level and today's totals.
- **Schedule** – drag time periods on a 24-hour timeline: *Use battery*, *Save the battery*, *Charge from the grid*
  (with target level and power) and *Export to the grid*. A default plan and temporary plans that switch back by themselves.
- **AI automation** – measures your battery's real efficiency and losses, uses electricity prices (Nord Pool, Danish grid
  tariffs), a solar forecast tuned to your panels and your own consumption pattern, and suggests – or sends – the cheapest
  plan for the next 24 hours. Shows what you saved in kWh and kroner.
- **Watch** – checks every few minutes that the inverter still has what was sent, and sends it again if needed.
- **History and backup** – every change is logged; the inverter's original configuration is saved the first time.
- **Push messages** to your phone (ntfy), English or Danish user interface.

## Two ways to use it

| | On this PC (free) | With the SunAI server (licence) |
|---|---|---|
| Price | Free | Needs a licence key |
| Who controls the battery | This PC | The SunAI server, around the clock |
| PC must be on | Yes, for plans that change during the day and for automatic control | No |
| Your Growatt API key | Encrypted on this PC | Encrypted on the server (deleted again if you switch back) |

You choose at the first start, and can change it at any time under **Server and updates**.

## Install

1. Download `SunAI.exe` from **[Releases](https://github.com/Zoh63392187/SunAI/releases/latest)** and put it in a folder of your choice
   (for example `Documents\SunAI`). No installation is needed.
2. Start it. Windows may show "Windows protected your PC" because the file is new: click **More info → Run anyway**.
3. Get your API key in the Growatt app or on server.growatt.com: **Settings → Account Management → API Key**.
4. In SunAI: **Settings** → paste the key → **Save key** → choose your plant and inverter.
5. Optional: with a licence key, open **Server and updates**, enter the key and click **Let the SunAI server control it**.

## Updates

SunAI looks for new versions here on GitHub (at start and every 6 hours; can be turned off). When one is ready, a blue bar
appears at the top: click **Update**. The app downloads the new version, **checks that it is signed by SunAI**, replaces
itself and restarts. A file that does not match the signature is deleted and never run.

Every release contains `SunAI.exe`, `manifest.json` (version, SHA-256 and size) and the signatures `manifest.release.sig`
and `manifest.sig`.

## Security

- All connections use HTTPS (TLS 1.2 or newer). The SunAI server is verified against SunAI's own certificate authority.
- Your Growatt API key is never shown again after you save it (only the last 4 characters), never written to logs and never
  sent anywhere except to Growatt – and, only if you choose server mode, once to the SunAI server, where it is stored encrypted.
- Settings and history are stored on your PC in `%LOCALAPPDATA%\GrowattControl`.

## Requirements

- Windows 10 or 11, 64-bit. Nothing else to install (.NET is included in the file).
- A Growatt inverter with Open API access (SPH/MIX hybrid inverters are fully supported; MIN/TLX schedules are supported;
  other types are read-only).

## Terms

SunAI is provided as is, without warranty. You use it at your own risk; check that the settings suit your installation.
The source code is not public.

---

## Dansk

**SunAI** styrer en Growatt-hybridinverter med batteri på en enkel måde: store knapper, en tidsplan, du trækker på en
tidslinje, og en automatisk planlægger, der lader og bruger batteriet efter elprisen.

- **Gratis på denne PC**, eller **med SunAI-serveren** (licens), der styrer batteriet døgnet rundt, også når PC'en er slukket.
- **Hent:** [nyeste version](https://github.com/Zoh63392187/SunAI/releases/latest) → `SunAI.exe`. Viser Windows "Windows har
  beskyttet din PC", så klik **Flere oplysninger → Kør alligevel**.
- **Opdateringer:** en blå bjælke øverst i appen → **Opdatér**. Appen tjekker, at filen er signeret af SunAI, før den skifter.
- **Understøtter:** kun Growatt. SPH/MIX styres fuldt, MIN/TLX får tidsplaner, andre typer kan kun læses.
- **Antal invertere:** op til 10 pr. PC; med server-licens 1 som standard (flere efter aftale, op til 50).
- **Version:** se mærket øverst eller [Releases](https://github.com/Zoh63392187/SunAI/releases).
- Vælg dansk under **Settings → Language → Dansk**.

SunAI er et uafhængigt program og er hverken udviklet af, godkendt af eller tilknyttet Growatt.
