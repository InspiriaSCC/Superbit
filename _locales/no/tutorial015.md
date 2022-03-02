### @activities true

# Superbit del 15: Servoer del 4
## Lag en bom som styres av en avstandssensor
### Introduksjon @unplugged

I denne gjennomgangen lærer du å programmere bom som åpnes ved hjelp av en avstandssensor.

### Tilkoblinger @unplugged

Rett foran hjulet på Bitbotens ventre side finner du to kontakter med 3 pinner.
Dette er servokontaktene til Bitboten.
Det fremste paret med pinner er merket P1 og P2.
P1 og P2 er signalutgangene fra Micro:Biten som brukes til å kontrollere servoer.
De to neste parene er merket 5V og GND.
5V gir 5 volts positiv spenning mot GND, som er jordkontaktene.

### Steg 1

Monter en hvit, enkel plastarm til en **180-graderservo** som vist på bildet.
Koble **180-graderservoen** til P0 rekken av kontakter som forklart og vist.
Servoene som følger med Superbit har tre ledninger ut, en brun, en rød og en oransje.
Brun er jordledningen, den skal kobles til GND.
Rød er "+"-ledningen som skal kobles til 5V.
Oransje er signalledningen som skal kobles til P1 eller P2.
Plasser kontakten til servoen på pinnene ved P1 slik at oransje ledning treffer P1, rød ledning treffer 5V og brun ledning treffer GND.

![Servokobling](https://raw.githubusercontent.com/Yngel72/Superbit/master/static/Servokobling.jpg)

### Ulttralydsensoren @unplugged

Til denne øvelsen trenger du avstandssensoren, eller ultralydsensoren, som den også kalles.
Den ser nesten ut som to øyne.
"Øynene" består i dette tilfellet av en høyttaler og en mikrofon og fungerer som ekkolokasjonen til en flaggermus.
Høyttaleren sender ut en ultralydpuls som reflekteres tilbake til mikrofonen fra omgivelsene i form av ekko.
Sensoren måler avstanden til objekter foran seg ved å måle tiden fra pulsen forlater høyttaleren til ekkoet når mikrofonen.
Avstanden regnes ut ved hjelp av lydhastigheten i luft.

### Steg 2
Ultralydsensoren plasseres i kontakten foran på Bitboten som vist på bildet.
"Øynene" skal peke forover, bort fra Micro:Biten.

![Avstandssensor](https://raw.githubusercontent.com/Yngel72/Superbit/master/static/Avstandssensor.jpg)

### Steg 3

Start med å sette en grunntilstand for servoen.
Siden dette er en bom, og bommen er lukket når servoen er på 0 grader, er det greit å starte med å si at servoen skal være i posisjonen 0 grader nåe programmet starter.
Hent en ``||bitbot.sett servo P1 til 90 grader||``-blokk fra ``||bitbot.Bitbot/Sensorer og styring||``-menyen og plasser den i ``||basic.ved start||``-blokken.
Endre ``||bitbot.90 grader||`` til ``||bitbot.0 grader||``.

```blocks
// @highlight
bitbot.bbSetServo(BBServos.P1, 0)
```

### Steg 4

Hent en ``||basic.vis ikon||``-blokk fra ``||basic.Basis||``-menyen og sett den inn under ``||bitbot.sett servo P1 til 0 grader||``-blokken.
Ikonet gjør det lettere å se at programmet kjører.
Velg et ikon du synes passer.

```blocks
bitbot.bbSetServo(BBServos.P1, 0)
// @highlight
basic.showIcon(IconNames.Heart)
```

### Steg 5

Siden ultralydsensorene må oppdateres hele tiden, må dette programmet kjøres i en ``||basic.gjenta for alltid||``-blokk.
Når bommen skal åpnes bestemmes av en logisk løkke som hele tiden sjekker avstanden.
Hent en ``||logic.hvis sant så ellers||``-blokk fra ``||logic.Logikk||``-menyen og plasser den i ``||basic.gjenta for alltid||``-blokken.

```blocks
basic.forever(function () {
    // @highlight
    if (true) {
    	
    } else {
    	
    }
})
```

### Steg 4

Hent et ``||logic.0 < 0||``-heksagon og plasser det i heksagonet øverst i ``||logic.hvis sant så ellers||``-blokken.

```blocks
basic.forever(function () {
    // @highlight
    if (0 < 0) {
    	
    } else {
    	
    }
})
```

### Steg 5

Hent en oval ``||bitbot.les ultralydsensor som cm||``-blokk fra ``||bitbot.Bitbot/Sensorer og styring||``-menyen.
Dra den inn i det første hvite feltet i ``||logic.0 < 0||``-heksagonet.
Endre "0" i det andre hvite feltet til 10.
Om du ønsker en annen avstand enn 10 cm, kan du velge et annet tall her.

```blocks
basic.forever(function () {
    // @highlight
    if (bitbot.sonar(BBPingUnit.Centimeters) < 0) {
    	
    } else {
    	
    }
})
```

### Steg 6

Sett en ``||bitbot.sett servo P1 90 grader||``-blokk fra ``||bitbot.Bitbot/Sensorer og styring||``-menyen inn i det øverste gapet i ``||logic.hvis sant så ellers||``-blokken.

```blocks
basic.forever(function () {
    if (bitbot.sonar(BBPingUnit.Centimeters) < 10) {
        // @highlight
        bitbot.bbSetServo(BBServos.P1, 90)
    } else {
    	
    }
})
```

### Steg 7

Sett inn en ``||basic.pause 100 ms||``-blokk fra ``||basic.Basis||``-menyen under ``||bitbot.sett servo P1 90 grader||``-blokken.
Endre ``||basic.100 ms||`` til ``||basic.200 ms||``.

```blocks
basic.forever(function () {
    if (bitbot.sonar(BBPingUnit.Centimeters) < 10) {
        bitbot.bbSetServo(BBServos.P1, 90)
        // @highlight
        basic.pause(200)
    } else {
    	
    }
})
```

### Servoer og pauser @unplugged

Servoen trenger litt tid når den vandrer fra 0 grader til 90.
Pausen på 200 ms gjør at den rekker å gjøre ferdig oppgaven før det kommer en ny instruksjon.
Om instruksjonene kommer for tett kan det føre til at servoen bare blir stående å hakke.
Dette sliter på servoen og gjør at programmet ikke fungerer som det skal.
En viktig del av feilsøkingen når et program ikke virker som det skal, er å vurdere om man har koblet til noe som ikke rekker å gjennomføre en oppgave før programmet går videre.

### Steg 8

Trykk på det lille ***"+"***-tegnet nederst til venstre i ``||logic.hvis sant så ellers||``-blokken for å lage et nytt heksagon.
Kopier den heksagonformede ``||logic.0 < 0||``-blokken fra øverst i ``||logic.hvis sant så ellers||`` og plasser den i det nye heksagonet.
Endre ***"<"*** til tegnet for ***"større eller lik"***, altså en ***">"*** med strek under.
Klikk på det lille ***"-"***-tegnet nederst til høyre på nest siste arm i ``||logic.hvis sant så ellers||``-blokken for å bli kvitt det siste gapet.

```blocks
basic.forever(function () {
    // @highlight
    if (bitbot.sonar(BBPingUnit.Centimeters) < 10) {
        bitbot.bbSetServo(BBServos.P1, 90)
        basic.pause(200)
    } else if (bitbot.sonar(BBPingUnit.Centimeters) >= 10) {
    	
    }
})
```

### Steg 9

Kopier ``||bitbot.sett servo P1 90 grader||``-blokken og dra kopien inn i det andre gapet på ``||logic.hvis sant så ellers||``-blokken.
Endre ``||bitbot.90 grader||`` til `||bitbot.0 grader||``
Kopier ``||basic.pause 200 ms||``-blokken og plasser kopien rett under ``||bitbot.sett servo P1 0 grader||``-blokken.

```blocks
basic.forever(function () {
    if (bitbot.sonar(BBPingUnit.Centimeters) < 10) {
        bitbot.bbSetServo(BBServos.P1, 90)
        basic.pause(200)
    } else if (bitbot.sonar(BBPingUnit.Centimeters) >= 10) {
        // @highlight
        bitbot.bbSetServo(BBServos.P1, 0)
        basic.pause(200)
    }
})
```

### Avslutning @unplugged

Nå kan du laste ned programmet og teste om det fungerer etter planen. Når du holder en hånd eller en ting nærmere enn 10 cm fra framsiden av ultralydsensoren, skal bommen gå opp.
Når du fjerner gjenstanden skal bommen gå ned igjen.


```package
bitbot=github:4tronix/BitBot
```

<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
