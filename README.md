# FerderKontroll

![project-6](https://github.com/andershagas/FerderKontroll/assets/42244235/9894501f-8899-4b5d-8188-419ad7bac181)


Hva er FerderKontroll?
=============

FerderKontroll er et avansert system utviklet for å løse logistikkutfordringer ved hjelp av Vehicle Routing Problem (VRP)-teknologi.
Dette systemet gir brukerne muligheten til å opprette optimale ruter for transport av varer og tjenester ved å ta i bruk avanserte
algoritmer og verktøy. Her er en kort oversikt over hovedtrinnene i FerderKontroll.

## Trinn 1: Konfigurasjon av Transport
Før FerderKontroll starter ruteplanleggingen sin, gir systemet muligheten til å konfigurere transportparametre. Brukere kan
velge å ignorere forhåndsdefinerte kjøretøy (Allerede lagt til i TDS.) og la systemet selv bestemme transporten.
Dette ekskluderer kjøretøy som ikke er registrert i kjøretøyregisteret i FerderKontroll. (For eksempel busser som har ruter på seg,
disse vil vi ikke endre.)

## Trinn 2: Datainnsamling og Behandling
FerderKontroll tar imot logistikkdata i form av Excel-ark direkte fra TDS.
Systemet filtrerer og behandler disse dataene for å forstå innholdet, inkludert parsing av ko-ordinater,
adresser, egenskaper som ledsager, rullestoler og andre relevante opplysninger.

Dette trinnet sikrer at systemet har en klar forståelse av logistikkdataene som skal bearbeides.
I tillegg leser systemet om studenttransport er avbestillt og søker igjennom tur dataene for å identifisere
hvilke studenter som er berørty, men det er kun hvis behandleren på sentralen har gjort det riktig. (Som sjelden skjer.)

FerderKontroll gir også brukerne mulighet til å tilpasse hente- og leveringstidspunkt for transport. Dette kan inkludere
å ankomme tidligere eller senere med et gitt tidsintervall eller legge til ekstra tid på en reise hvis det greves for å
hente flere studenter underveis, så lenge den totale reisetiden forblir innenfor det opprinnelige tidsintervallet.

For eksempel: Det tar 10 minutter og hente student X, reglene tilsier at turer kan maks ta 5 minutter ekstra hvis det omhandler å samkjøre
en annen elev på samme tur.
Hvis det da tar 3 minutter ekstra for å hente student Y, vil den da legges på for å bli samkjørt på samme tur.

## Trinn 3: Adressebehandling

En utfordring jeg fikk i utviklingen av FerderKontroll er uvanlige adresser som inneholder flere lokasjer.
For eksempel, kan området mellom Nykirke og Skoppum, adresser som har "Holmestrand, Re" og "Undrumsdal, Re" i adressen være
forvirrende.

FerderKontroll inneholder en intelligent adressebehandling som identifiserer og håndterer slike komplekse adresser, og sikrer nøyaktig
ruteplanlegging.

## Trinn 4: Kjøretøyvalg

FerderKontroll sjekker hvilke kjøretøy som er tilgjengelige i systemet, og identifiserer hvilke kjøretøy som er tildelt de planlagte turene.
Systemet unngår å inkludere minibusser og tunge kjøretøy som ikke er en del av logistikksystemet. (Selvfølgelig støtter den det også,
men vanligvis har minibusser og store busser helt fast rute som aldri endres.

Systemet har også lagret hvor kjøretøy har startposisjon, og har også mange muligheter for konfigurasjon per bil, som for eksempel
driftstid for kjøretøy eller driftslengde. Alt annet er også justerbart, antall seter, rullestol kapasitet osv.

## Trinn 5: Ruteplanlegging og Resultater

FerderKontroll går deretter gjennom hver planlagt tur og tilordner et bestemt kjøretøy. Dette skjer i samsvar med tidligere konfigurerte
kjøretøy fra TDS systemet, for eksempel så er en student tilordnet kjøretøyet VT325. Da vil systemet sette den turen på den bilen automatisk, så bygge opp ruta til bilen
basert på dette.

Til slutt genererer FerderKontroll en oversikt over resultatene som viser hvilke kjøretøy som kjører hvem i hvilke rekkefølge. Systemet viser også
eventuelle turer den ikke er enig i, samt turer som ikke kunne løses automatisk og må håndteres manuelt av en kvalifisert smarting.


*Med disse trinnene sikrer FerderKontroll en optimal ruteplanlegging for effektiv transport av studenter, samtidig som den tar hensyn til brukerpreferanser
og systemparametere. Dette gjør FerderKontroll til en verdifull ressurs innen logistikk, som kan bidra til voldsomme kostnadsbesparelser og effektiv ressursbruks, samtidig
som den gir fleksibilitet for tilpasninger basert på brukerens og sentralens behov og unike situasjoner.*

**Bonus:** Systemet er like i stand for å sette opp pasientkjøring som den er skolekjøring. :)


Utenom FerderKontroll så vurderte jeg å lage ett dashboard for alt dette, men dette var kun ett "fritidsprosjekt" som ikke gikk noen vei,
så ville ikke det. Jeg lagde også ett kart system som viser alle turer til visse tidspunkt. Det gjør det enklere for en person og visualisere alle turer som skjer en at de er på en liste.


*Spoiler:* Dette systemet ble aldri tatt i bruk på ordentlig. Det funker perfekt, men jeg vet ikke hvorfor det var veldig lite interesse. Fikk blandt annet en kommentar
om at "systemet gjør jobben dems".
