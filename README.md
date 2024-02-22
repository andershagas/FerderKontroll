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
