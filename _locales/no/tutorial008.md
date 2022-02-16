### @activities true

# Superbit del 8: Hvordan bruke avstandssensoren til Bitbot
## Avstandssensoren til Bitbot
### Introduksjon @unplugged

Avstandssensoren som følger med i Superbitsettet skal festes i den svart kontakten framme på snuten til Bitboten.
Den kan oppdage gjenstander foran Bitboten, slik at man kan bruke den til å unngå kollisjoner.
I denne gjennomgangen lærer du å bruke avstandssensoren til å få Bitboten til å unngå hindre.
**NB: Avstandssensoren krever omtrent 5 volt og fungerer derfor dårlig med oppladbare AA-batterier i Bitboten.
Vanlige, alkaliske, ikke-oppladbare AA-batterier gir høyere spenning enn oppladbare, derfor anbefales de på det sterkeste her.**

### Steg 1

Til dette programmet bruker vi en ``||basic.gjenta for alltid||``-løkke som utgangspunkt.
I ``||basic.gjenta for alltid||``-blokken må vi ha en logisk sjekk som hele tiden måler avstanden til objekter foran roboten, og bestemmer hva som skal skje om avstanden er for liten.
Hent en ``||logic.hvis sann så ellers||``-blokk fra ``||logic.Logikk||``-menyen og plasser den inni ``||basic.gjenta for alltid||``-blokken.

```blocks
basic.forever(function () {
    if (true) {
    	
    } else {
    	
    }
})
```

### Steg 2

I heksagonet øverst i ``||logic.hvis sann så ellers||``-blokken trenger vi en **"mindre enn"** sjekk.
Hent det lille heksagonet ``||logic.0 < 0||`` fra ``||logic.Logikk||``-menyen og plasser det i heksagonet på ``||logic.hvis sann så ellers||``-blokken.

```blocks
basic.forever(function () {
    if (0 < 0) {
    	
    } else {
    	
    }
})
```

### Steg 3

Fra ``||bitbot.Bitbot/Sensorer og styring||`` henter du en oval ``||bitbot.les ultralydsensor som cm||``-blokk og setter den inn i det første hvite feltet i ``||logic.0 < 0||``-blokken.

```blocks
basic.forever(function () {
    // @highlight
    if (bitbot.sonar(BBPingUnit.Centimeters) < 0) {
    	
    } else {
    	
    }
})
```

### Steg 4

Nå må du bestemme hvilken avstand du vil at Bitboten skal reagere på. 10-15 cm pleier å være et godt utgangspunkt.
Endre "0" i det andre hvite feltet i ``||logic.0 < 0||``-blokken til den avstanden du vil teste.

```blocks
basic.forever(function () {
    // @highlight
    if (bitbot.sonar(BBPingUnit.Centimeters) < 10) {
    	
    } else {
    	
    }
})
```

### Steg 5

Nå skal du instruere roboten om hva den skal gjøre når den støter på et hinder.
Hent en ``||bitbot.snu til venstre med fart 60 %||``-blokk fra ``||bitbot.Bitbot/Kjøring/||``-menyen og sett den inn i det øverste gapet i ``||logic.hvis sann så ellers||``-blokken.

```blocks
basic.forever(function () {
    if (bitbot.sonar(BBPingUnit.Centimeters) < 10) {
        // @highlight
        bitbot.rotate(BBRobotDirection.Left, 60)
    } else {
    	
    }
})
```

### Steg 6

Når det ikke er noe hinder foran Bitboten, skal den kjøre rett fram.
Hent en ``||bitbot.kjør framover med fart 60 %||``-blokk fra ``||bitbot.Bitbot/Kjøring/||``-menyen og plasser den i det andre gapet på ``||logic.hvis sann så ellers||``-blokken.
Nå gjenstår det bare å teste om avstanden på sensoren, farten på Bitboten og utslaget på svingingen fungerer greit for å unngå hindre.
Last ned programmet til Micro:Biten og test en liten hinderløype.
Bruk det du måtte ha av esker, kopper o.l. som hindre.
Det kan hende du må prøve og feile litt før koden fungerer bra.

```blocks
basic.forever(function () {
    if (bitbot.sonar(BBPingUnit.Centimeters) < 10) {
        bitbot.rotate(BBRobotDirection.Left, 60)
    } else {
        // @highlight
        bitbot.go(BBDirection.Forward, 60)
    }
})
```

### Steg 7

Dersom du opplever at Bitboten ikke helt klarer å unngå hindre slik koden er nå, kan et tips være å få den til å rygge litt når den støter på et hinder.
Du kan bruke blokken ``||bitbot.kjør framover med fart 60 % i 400 ms||`` for å få bitboten til å rygge.
Hent blokken ``||bitbot.kjør framover med fart 60 % i 400 ms||`` fra ``||bitbot.Bitbot/Kjøring||`` og sett den inn **over** ``||bitbot.snu til venstre med fart 60 %||``-blokken i det øverste gapet i ``||logic.hvis sann så ellers||``-blokken.
Endre ``||bitbot.framover||`` til ``||bitbot.bakover||`` og endre ``||bitbot.400 ms||`` til et tall du tror passer.
Test den nye koden og se om roboten nå er blitt flinkere til å unngå hindre.

```blocks
basic.forever(function () {
    if (bitbot.sonar(BBPingUnit.Centimeters) < 10) {
        bitbot.rotate(BBRobotDirection.Left, 60)
        bitbot.goms(BBDirection.Reverse, 60, 400)
    } else {
        bitbot.go(BBDirection.Forward, 60)
    }
})
```

### Avslutning @unplugged

Verre var det ikke.
Det er ikke så mange linjer kode som skal til for å bruke avstandssensoren, men prøving og feiling for å få koden til å virke optimalt tar gjerne litt tid.
**Husk at oppladbare batterier ikke fungerer særlig godt med avstandssensoren.
Bruk heller valige, ikke-oppladbare AA-batterier når du holder på med akkurat denne sensoren.**

```package
bitbot=github:4tronix/BitBot
```

<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
