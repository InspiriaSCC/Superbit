### @activities true

# Superbit del 10: Radiostyring del 1: Senderen
## Bruk radiosignaler til å fjernstyre en Bitbot
### Introduksjon @unplugged

Gjennomgangen om radiostyring må gjøres i to deler.
Det er fordi det må programmeres to Micro:Biter for å lage en fjernstyrt robot: Sender og mottager.
Senderen tar imot inndata fra den som skal styre roboten via knapper eller bevegelse og videresender dem til mottageren som formidler inndataene til roboten.
Du begynner med å programmere senderen i denne gjennomgangen, så tar vi for oss mottageren i neste runde.

### Steg 1

Siden radiostyring krever at Micro:biten bruker radiosignaler, må du begynne med å aktivere radioen og velge en kanal.
Det gør du med blokken ``||radio.radio sett gruppe||`` som du finner i ``||radio.Radio||``-menyen.
Hent en ``||radio.radio sett gruppe||`` og plasser den i ``||basic.ved start||``-blokken.

```blocks
radio.setGroup(1)
```

### Steg 2

For å vise at Micro:Biten som skal være radiosender er på og virker, kan du sette inn et ikon i displayet som vises når senderprogrammet kjører.
Du kan tegne en liten radio, eller velge et annet ikon om du foretrekker det.
Hent en ``||basic.vis skjerm||`` eller ``||basic.vis ikon||`` blokk fra ``||basic.Basis||``-menyen og sett den inn i ``||basic.ved start||``-blokken under ``||radio.radio sett gruppe||``-blokken.

```blocks
radio.setGroup(1)
// @highlight
basic.showLeds(`
    . . . . #
    . . . . #
    # # # # #
    # . # # #
    # # # # #
    `)
```

### Steg 3

Resten av koden skal kjøre i en ``||basic.gjenta for alltid||``-blokk.
Hent en i ``||basic.Basis||``-menyen om det ikke allerede ligger en i arbeidsområdet.
Du trenger også en ``||logic.hvis sann så ellers||``-blokk fra ``||logic.Logikk||``-menyen.
Plasser ``||logic.hvis sann så ellers||``-blokken i ``||basic.gjenta for alltid||``-blokken.

```blocks
basic.forever(function () {
    // @highlight
    if (true) {
    	
    } else {
    	
    }
})
```

### Inndata @unplugged

Nå trenger du en måte å hente inndata på.
Siden Micro:Biten bare har to knapper, er det vanskelig å få til framover, bakover og sving til høyre og venstre med knappene.
Da er akselerometeret en bedre måte å styre roboten på.
Akselerometeret gir inndata når Micro:Biten vippes i fire retninger, og det er egentlig alt vi trenger for å styre en robot.

### Steg 4

Hent en heksagonformet ``||input.er ristes bevegelse||``-blokk fra ``||input.Inndata||``-menyen og plasser den i heksagonet øverst i ``||logic.hvis sann så ellers||``-blokken.
Endre ``||input.ristes||`` til ``||input.logo ned||``.

```blocks
basic.forever(function () {
    // @highlight
    if (input.isGesture(Gesture.LogoDown)) {
    	
    } else {
    	
    }
})
```

### Kommunikasjonen mellom sender og mottager @unplugged

Når Micro:Bit-senderen vippes forover, altså med logoen ned, skal den sende en kode til mottageren via radioen.
Siden du bare trenger 4 retninger; Framover, bakover, høyre og venstre, kan du bruke tallen 1-4 som radiokoder.

### Steg 5

Hent en ``||radio.radio send tall``|| blokk fra ``||radio.Radio||``-menyen og sett den inn i det øverste gapet i ``||logic.hvis sann så ellers||``-blokken.
Endre "0" til "1".

```blocks
basic.forever(function () {
    if (input.isGesture(Gesture.LogoDown)) {
        // @highlight
        radio.sendNumber(1)
    } else {
    	
    }
})
```


