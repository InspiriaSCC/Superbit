### @activities true

# Superbit del 6: Neopixel
## Introduksjon
### Introduksjon @unplugged

NeoPixel er RGB-LED-pærer som kan programmeres til å lyse i alle regnbuens farger.
Om man kobler flere av dem sammen kan man lage et uendelig antall morsomme mønstre.
NeoPixel har egne blokker og krever en egen utvidelse for MakeCode.
Vi har allerede lagt til utvidelsespakken du trenger, for man kan ikke legge til utvidelser mens man gjennomfører en læringsøkt som dette.
Vi vil likevel vise hvordan du finner og legger til en slik utvidelse, selv om du ikke kan gjøre det akkurat nå.

### Legge til utvidelse @unplugged

Utvidelser legges til fra blokkmenyen i midten av skjermen.
Aller nederst i **"Avansert"**-menyen vil du kunne se en egen, lysegrå underkategori som heter **"Utvidelser"**.
Om du klikker på den, kommer du til siden der du finner utvidelsene som finnes til MakeCode.
Du kan enten bla deg gjennom utvidelsene på siden, søke etter utvidelsen i et søkefelt, eller laste inn en utvidelse du har lagret på maskinen din.
Når du har funnet utvidelsen klikker du på den, og så er den lagt til for programmet du er i ferd med å lage.
Om du oppretter en ny MakeCode-økt, må du legge til utvidelser på nytt.
De krever litt plass og minne, så derfor lastes de kun inn ved behov.
Verre er det egentlig ikke å laste inn en utvidelse.

### Steg 1 Bruke neopixel med krokodilleklemmer

Neopixler trenger å kobles til 3 steder på Miro:Biten:
Plusspolen (som regel rød ledning) kobles til 3V, minuspolen (som regel svart ledning) kobles til GND og den siste ledningen (ofte den midterste, ofte grønn eller gul) kobles til en av utdatakontaktene på Micro:Biten, altså 0, 1 eller 2 om du bruker krokodilleklemmer.

