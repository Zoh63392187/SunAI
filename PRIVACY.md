# SunAI privacy policy

Version 2026-11-18

This policy explains what personal data SunAI handles, why, and what your rights are under the EU General Data
Protection Regulation (GDPR) and the Danish Data Protection Act.

## 1. Who is responsible

Data controller: Thomas Condé Hansen, Denmark (a private person who makes SunAI as a free hobby project).
Contact: privacy@condecoding.dk

## 2. On your own PC (standalone mode)

When SunAI runs on your PC, your data stays on your PC. The developer receives nothing.

- Your Growatt API key is stored encrypted with Windows (DPAPI) in `%LOCALAPPDATA%\GrowattControl`, never in plain text
  and never in log files.
- Settings, plans, history and energy measurements are stored in the same folder.
- You can delete everything at any time by deleting that folder.

SunAI contacts these services directly from your PC:

- **Growatt** (openapi.growatt.com or the region you choose) – with your API key, to read and control your inverter. Growatt
  is responsible for its own processing under its own privacy policy.
- **Energi Data Service** (Energinet) – electricity prices and tariffs. No personal data is sent.
- **Open-Meteo** – the solar forecast. Only the coordinates of the town you choose are sent, not your address.
- **ntfy** – only if you enter a push address: the push messages you choose are sent to that ntfy server.
- **GitHub** – to check for and download updates (can be turned off). GitHub sees your IP address.
- **The SunAI server** – only if you enter a licence key (see section 3).

## 3. In server mode (SunAI server)

If you enter a licence key, and especially if you let the SunAI server control your battery, the following is processed
on the developer's server, located in Denmark:

| Data | Why | Kept |
|---|---|---|
| Licence key, holder name, PC id and hardware fingerprint (hashed), IP address, app version, last seen | To check the licence, prevent misuse and keep the service secure | While the licence exists |
| Your Growatt API key (encrypted) | To read and control your inverter around the clock | Deleted at once when you switch back to "this PC" |
| Inverter serial number, plant, settings, plans, energy history, push address (encrypted) | To plan and control your battery and send you push messages | Deleted 30 days after you switch back |
| Error reports you choose to send | To fix errors | 12 months |
| Server log (time, licence holder, PC id, inverter serial, IP address, what happened) | Security and fixing errors | 90 days |

- Daily backups of the server (with the API key still encrypted) are kept for up to 8 weeks, then deleted. Data you have had
  deleted therefore disappears from the backups within 8 weeks.
- All connections use HTTPS (TLS 1.2 or newer). The API key and push address are stored encrypted on the server.
- Your data is never sold, never used for advertising, and never shared with anyone except as described here. There is no
  tracking and no analytics.
- No data is transferred outside the EU/EEA by the SunAI server, except calls to Growatt's API (which Growatt handles) and
  push messages to the ntfy server you chose.

## 4. Legal basis

- Providing SunAI and the SunAI server that you asked for: GDPR article 6(1)(b) (contract).
- Licence checks, security and preventing misuse: GDPR article 6(1)(f) (legitimate interest in running a safe service).

## 5. Automated decisions

The automatic plan only decides when your battery charges and discharges. It makes no decisions about you that have legal or
similarly significant effects (GDPR article 22).

## 6. Your rights

You have the right to access, correct and delete your data, to restrict or object to processing, and to receive your data
in a portable format. Write to privacy@condecoding.dk. Switching back to "this PC" in SunAI deletes your API key on the server at
once and the rest after 30 days; you can ask for immediate deletion.

You can complain to the Danish Data Protection Agency (Datatilsynet), www.datatilsynet.dk.

## 7. Changes

If this policy changes, SunAI shows the new version and asks you to accept it.
