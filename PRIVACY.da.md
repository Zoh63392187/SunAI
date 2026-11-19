# SunAI privatlivspolitik

Version 2026-11-19.1

Denne politik forklarer, hvilke personoplysninger SunAI behandler, hvorfor, og hvilke rettigheder du har efter EU's
databeskyttelsesforordning (GDPR) og den danske databeskyttelseslov.

Den engelske udgave (PRIVACY.md) er den gældende; denne danske udgave er en oversættelse.

## 1. Hvem er ansvarlig

Dataansvarlig: Thomas Condé Hansen, Danmark (en privatperson, der laver SunAI som et gratis hobbyprojekt).
Kontakt: privacy@condecoding.dk

## 2. På din egen PC (selvstændig tilstand)

Når SunAI kører på din PC, bliver dine data på din PC. Udvikleren modtager intet.

- Din Growatt API-nøgle gemmes krypteret med Windows (DPAPI) i `%LOCALAPPDATA%\GrowattControl` – aldrig i klartekst og
  aldrig i logfiler.
- Indstillinger, planer, historik og energimålinger gemmes i samme mappe.
- Du kan slette det hele når som helst ved at slette mappen.

SunAI kontakter disse tjenester direkte fra din PC:

- **Growatt** (openapi.growatt.com eller den region, du vælger) – med din API-nøgle for at læse og styre din inverter.
  Growatt er selv ansvarlig for sin behandling efter sin egen privatlivspolitik.
- **Energi Data Service** (Energinet) – elpriser og tariffer. Der sendes ingen personoplysninger.
- **Open-Meteo** – solprognosen. Kun koordinaterne for den by, du vælger, sendes – ikke din adresse.
- **Eloverblik** (Energinet DataHub) – kun hvis du indsætter et Eloverblik-token under Indstillinger: din elmålers aflæsninger (købte og solgte kWh, måler-id og adresse) hentes til din PC. De bliver på din PC, sendes aldrig til SunAI-serveren og slettes, når du afbryder måleren. Tokenet krypteres med Windows (DPAPI).
- **ntfy** – kun hvis du indtaster en push-adresse: de push-beskeder, du vælger, sendes til den ntfy-server.
- **GitHub** – for at søge efter og hente opdateringer (kan slås fra). GitHub ser din IP-adresse.
- **SunAI-serveren** – kun hvis du indtaster en licensnøgle (se afsnit 3).

## 3. I server-tilstand (SunAI-serveren)

Indtaster du en licensnøgle, og især hvis du lader SunAI-serveren styre dit batteri, behandles følgende på udviklerens
server, som står i Danmark:

| Data | Hvorfor | Gemmes |
|---|---|---|
| Licensnøgle, indehavers navn, PC-id og hardware-fingeraftryk (hashet), IP-adresse, app-version, sidst set | For at tjekke licensen, forhindre misbrug og holde tjenesten sikker | Så længe licensen findes |
| Din Growatt API-nøgle (krypteret) | For at læse og styre din inverter døgnet rundt | Slettes straks, når du skifter tilbage til "denne PC" |
| Inverterens serienummer, anlæg, indstillinger, planer, energihistorik, push-adresse (krypteret) | For at planlægge og styre dit batteri og sende dig push-beskeder | Slettes 30 dage efter, at du skifter tilbage |
| iPhones, du forbinder til SunAI-appen: det navn, iPhonen giver sig selv, hvornår den blev forbundet og sidst brugt, dens IP-adresse (iPhonens nøgle gemmes kun som fingeraftryk) | For kun at vise dit batteri på dine egne iPhones og holde tjenesten sikker | Indtil du afbryder iPhonen, eller licensen slettes |
| Fejlrapporter, du selv vælger at sende | For at rette fejl | 12 måneder |
| Serverlog (tid, licensindehaver, PC-id, inverterens serienummer, IP-adresse, hvad der skete) | Sikkerhed og fejlretning | 90 dage |

- Daglige backups af serveren (med API-nøglen stadig krypteret) gemmes i op til 8 uger og slettes derefter. Data, du har
  fået slettet, forsvinder derfor også fra backups inden for 8 uger.
- Alle forbindelser bruger HTTPS (TLS 1.2 eller nyere). API-nøglen og push-adressen gemmes krypteret på serveren.
- Dine data sælges aldrig, bruges aldrig til reklame og deles aldrig med andre end beskrevet her. Der er ingen sporing og
  ingen statistik-værktøjer.
- SunAI-serveren overfører ingen data uden for EU/EØS, bortset fra kald til Growatts API (som Growatt håndterer) og
  push-beskeder til den ntfy-server, du har valgt.

## 4. Retsgrundlag

- At levere SunAI og SunAI-serveren, som du har bedt om: GDPR artikel 6, stk. 1, litra b (aftale).
- Licenstjek, sikkerhed og forebyggelse af misbrug: GDPR artikel 6, stk. 1, litra f (legitim interesse i at drive en sikker
  tjeneste).

## 5. Automatiske afgørelser

Den automatiske plan bestemmer kun, hvornår dit batteri lader og aflader. Den træffer ingen afgørelser om dig, som har
retsvirkning eller på lignende måde påvirker dig betydeligt (GDPR artikel 22).

## 6. Dine rettigheder

Du har ret til indsigt, berigtigelse og sletning, til at begrænse eller gøre indsigelse mod behandlingen og til at få dine
data udleveret i et maskinlæsbart format. Skriv til privacy@condecoding.dk. Når du skifter tilbage til "denne PC" i SunAI, slettes
din API-nøgle på serveren straks og resten efter 30 dage; du kan bede om sletning med det samme.

Du kan klage til Datatilsynet, www.datatilsynet.dk.

## 7. Ændringer

Ændres politikken, viser SunAI den nye udgave og beder dig acceptere den.
