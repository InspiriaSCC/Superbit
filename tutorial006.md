### @activities true

# Superbit del 6: Neopixel
## Introduksjon
### Introduksjon @unplugged

NeoPixels er RGB-LED-pærer som kan programmeres til å lyse i alle regnbuens farger.
Om man kobler flere av dem sammen kan man lage et uendelig antall morsomme mønstre.
Hver NeoPixel består av en RGB LED og en liten chip som leser koden som sendes gjennom NeoPixelen.
NeoPixler er såkalt adresserbare LEDs.
Det betyr i prinsippet at koden du lager forteller første NeoPixel at den er nummer en, nummer to får vite at den er nummer to osv.
Dette gjør at du kan bestemme farge, lysstyrke og om den skal være av eller på eller blinke for hver enkelt neopixel.
NeoPixel har egne blokker som krever en egen utvidelse for MakeCode.
Det første du skal lære her er å legge til utvidelsen for NeoPixel

### Steg 1 Legge til utvidelse

Utvidelser legges til fra blokkmenyen i midten av skjermen.
Aller nederst i **"Avansert"**-menyen vil du kunne se en egen, lysegrå underkategori som heter **"Utvidelser"**.
Om du klikker på den, kommer du til siden der du finner utvidelsene som finnes til MakeCode.
Bla deg gjennom utvidelsene på siden eller søk etter NeoPixel i søkefeltet om du ikke ser utvidelsen på siden.
Når du har funnet utvidelsen klikker du på den, og så er den lagt til for programmet du er i ferd med å lage.
Om du oppretter en ny MakeCode-økt, må du legge til utvidelser på nytt.
De krever litt plass og minne, så derfor lastes de kun inn ved behov.
Verre er det egentlig ikke å laste inn en utvidelse.

### Steg 2 Bruke NeoPixel med krokodilleklemmer 1

Før du går igang trenger du NeoPixelstripen.
Det er den ca 35 cm lange stripen med svart, hvit og rød ledning med krokodilleklemmer på.
NeoPixler trenger å kobles til 3 steder på Miro:Biten:
Plusspolen (rød ledning) kobles til 3V, minuspolen (svart ledning) kobles til GND og den siste ledningen (den midterste, hvit) kobles til en av utdatakontaktene på Micro:Biten, altså 0, 1 eller 2 når du bruker krokodilleklemmer.
Vi kobler den hvite klemmen til utgang 2 i eksempelkoden, fordi det er den nærmest utgangen til 3V og GND.
Når du har koblet opp neopixelstripen som forklart, går du videre.

### Steg 3 Bruke neopixel med krokodilleklemmer 2

Til dette programmet trenger du aller først en ``||basic.gjenta for altid||``-blokk.
Fra ``||neopixel.NeoPixel||``-menyen trenger du en ``||variables.sett strip til||`` ``||neopixel.NeoPixel at p0 with 24 leds as RGB (GRB format)||``.
Dra den inn i ``||basic.gjenta for altid||``-blokken og endre ``||neopixel.24||`` til ``||neopixel.20||``, eller det antall NeoPixler du har på din stripe.
Det er 20 NeoPixels på stripen som følger med Superbit.

```blocks
let strip: neopixel.Strip = null
basic.forever(function () {
    strip = neopixel.create(DigitalPin.P2, 20, NeoPixelMode.RGB)
})
```





```package
neopixel=github:microsoft/pxt-neopixel
```
