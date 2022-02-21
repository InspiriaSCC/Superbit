### @activities true

# Superbit del 11: Radiostyring del 2: Mottageren
## Bruk radiosignaler til å fjernstyre en Bitbot
### Introduksjon @unplugged

Forrige gjennomgang tok for seg hvordan man lager en radiosender som kan styre en Bitbot.
Nå skal du lage mottageren som skal stå i Bitboten og ta imot signaler fra senderen.
Legg radiosenderen på et trygt sted eller merk den med litt tape så den ikke blir brukt til noe annet i mellomtiden.
Til mottageren trenger du en ny Micro:Bit.
Så fort du har en klar, kan du gå videre.

### Steg 1

Siden radiostyring krever at Micro:biten bruker radiosignaler, må du begynne med å aktivere radioen og velge en kanal.
Det gør du med blokken ``||radio.radio sett gruppe||`` som du finner i ``||radio.Radio||``-menyen.
Hent en ``||radio.radio sett gruppe||`` og plasser den i ``||basic.ved start||``-blokken.

```blocks
radio.setGroup(1)
```

### Radiogrupper @unplugged
Det er viktig at mottagerens radio er satt til samme gruppe som senderens.
I gjennomgangen for senderen ble gruppe 1 brukt som eksempel, siden det er standardgruppen når du henter blokken i menyen.
Av den grunn brukes 1 som eksempel i denne gjennomgangen også.
Radiogrupper fungerer som radiokanaler.
Dersom flere roboter skal kjøres i samme rom, må alle sender/mottagerpar settes til forskjellige grupper.
Tallet i radiogruppeblokken kan være alle tall fra og med 0 til og med 255, så man kan i teorien kjøre 256 roboter i samme rom samtidig.
Det bør med andre ord være nok grupper å velge mellom til at en hel skoleklasse kan bygge hver sin fjernstyrte robot og kjøre dem i samme rom uten problemer.

### Steg 2

Siden senderen bare sender tall, må mottagerprogrammet kjøre i en ``||radio.når radio mottar receivedNumber||``-blokk fra ``||radio.Radio||``-menyen.
Legg en ``||logic.hvis sann så ellers||``-blokk fra ``||logic.Logikk||``-menyen inn i ``||radio.når radio mottar receivedNumber||``-blokken.

```blocks
radio.onReceivedString(function (receivedNumber) {
    // @highlight
    if (true) {
    	
    } else {
    	
    }
})
```

### Steg 3

Siden senderen sender et tall til mottageren, må vi bruke logisk sjekk for tall i heksagonene i ``||logic.hvis sann så ellers||``-blokken.
Hent en ``||logic.0 = 0||`` fra ``||logic.Logikk||``-menyen og dra den inn i det øverste heksagonet i ``||logic.hvis sann så ellers||``-blokken.

```blocks
radio.onReceivedString(function (receivedNumber) {
    // @highlight
    if (0 == 0) {
    	
    } else {
    	
    }
})
```

### Steg 4

Du trenger en slik sjekk for alle 4 retninger, så du kan like godt kopiere denne blokken og legge den inn i tilsammen 4 heksagoner i ``||logic.hvis sann så ellers||``-blokken.
Utvid ``||logic.hvis sann så ellers||``-blokken ved å trykke på det lille "+"-tegnet nederst til venstre i blokken 3 ganger.
Kopier ``||logic.0 = 0||``-blokken fra det øverste heksagonet i ``||logic.hvis sann så ellers||``-blokken 3 ganger og legg en kopi i hert av de andre heksagonene.
Trykk på det lille "-"-tegnet til høyre i den nest nederste armen i ``||logic.hvis sann så ellers||``-blokken for å lukke gapet du ikke trenger.

```blocks
radio.onReceivedString(function (receivedNumber) {
    // @highlight
    if (0 == 0) {
    	
    } else if (0 == 0) {
    	
    } else if (0 == 0) {
    	
    } else if (0 == 0) {
    	
    }
})
```

### Steg 5

Dra den ovale variabelen ``||variables.receivedNumber||`` fra øverst i ``||radio.når radio mottar receivedNumber||``-blokken og legg den inn i det første hvite feltet i det øverste ``||logic.0 = 0||``-heksagonet.
Gjenta for hvert av de 3 resterende heksagonene i ``||logic.hvis sann så ellers||``-blokken.

```blocks
radio.onReceivedNumber(function (receivedNumber) {
    // @highlight
    if (receivedNumber == 0) {
    	
    } else if (receivedNumber == 0) {
    	
    } else if (receivedNumber == 0) {
    	
    } else if (receivedNumber == 0) {
    	
    }
})
```

### Steg 6

Legg inn tallet "1" i det ledige hvite feltet i det øverste ``||logic.0 = 0||``-heksagonet, legg inn tallet "2" i neste heksagon, "3" i det neste og "4" i det siste.

```blocks
radio.onReceivedNumber(function (receivedNumber) {
    // @highlight
    if (receivedNumber == 1) {
    	
    } else if (receivedNumber == 2) {
    	
    } else if (receivedNumber == 3) {
    	
    } else if (receivedNumber == 4) {
    	
    }
})```

### Tallkodene @unplugged

Før du legger inn bevegelsene Bitboten skal gjøre for hver mottatte tallkode, kan det være lurt å sjekke tallene i programmet til senderen.
Om du fulgte instruksjonene til senderen til punkt og prikke, skal tallene i denne gjennomgangen stemme.
Målet er at når man tilter senderen framover går roboten framover, tilt bakover fører til at roboten rygger, tilt til venstre får roboten til å svinge til venstre og tilt til høyre får roboten til å svinge til høyre.
Om du har brukt andre tall i koden til senderen, bør du sjekke at tallene i sender og mottager stemmer overens.
Du vil i alle fall merke om det er feil i koden når du begynner å kjøre roboten.

### Steg 7

Hent en ``||bitbot.kjør framover med fart 60 %||`` fra ``||bitbot.Bitbot/Kjøring||``-menyen og dra den inn i det øverste gapet i `||logic.hvis sann så ellers||``-blokken.

```blocks
radio.onReceivedNumber(function (receivedNumber) {
    if (receivedNumber == 1) {
        // @highlight
        bitbot.go(BBDirection.Forward, 60)
    } else if (receivedNumber == 2) {
    	
    } else if (receivedNumber == 3) {
    	
    } else if (receivedNumber == 4) {
    	
    }
})
```

### Steg 8

Kopier ``||bitbot.kjør framover med fart 60 %||``-blokken og legg den inn i det neste ledige gapet.
Endre ``||bitbot.framover||`` til ``||bitbot.framover||``.

```blocks
radio.onReceivedNumber(function (receivedNumber) {
    if (receivedNumber == 1) {
        bitbot.go(BBDirection.Forward, 60)
    } else if (receivedNumber == 2) {
        // @highlight
        bitbot.go(BBDirection.Reverse, 60)
    } else if (receivedNumber == 3) {
    	
    } else if (receivedNumber == 4) {
    	
    }
})
```

### Steg 9

Hent en ``||bitbot.snu til venstre med fart 60 %||`` fra ``||bitbot.Bitbot/Kjøring||``-menyen og dra den inn i det neste ledige gapet i `||logic.hvis sann så ellers||``-blokken.

```blocks
radio.onReceivedNumber(function (receivedNumber) {
    if (receivedNumber == 1) {
        bitbot.go(BBDirection.Forward, 60)
    } else if (receivedNumber == 2) {
        bitbot.go(BBDirection.Reverse, 60)
    } else if (receivedNumber == 3) {
        // @highlight
        bitbot.rotate(BBRobotDirection.Left, 60)
    } else if (receivedNumber == 4) {
    	
    }
})
```

### Steg 10

Kopier ``||bitbot.snu til venstre med fart 60 %||``-blokken og legg den inn i det siste ledige gapet.
Endre ``||bitbot.venstre||`` til ``||bitbot.høyre||``.

```blocks
radio.onReceivedNumber(function (receivedNumber) {
    if (receivedNumber == 1) {
        bitbot.go(BBDirection.Forward, 60)
    } else if (receivedNumber == 2) {
        bitbot.go(BBDirection.Reverse, 60)
    } else if (receivedNumber == 3) {
        bitbot.rotate(BBRobotDirection.Left, 60)
    } else if (receivedNumber == 4) {
        // @highlight
        bitbot.rotate(BBRobotDirection.Right, 60)
    }
})
```

### Steg 11

Om du vil kan du legge til et smilefjes eller et annet bilde i ``||basic.ved start||``-blokken, slik at du kan se at koden din kjører.
Erfaringen viser at dersom man bruker flere lysfunksjoner på den fjernstyrte roboten, som NeoPixler eller liknende, kan roboten bli litt treg i responsen.
Dersom du prøver å legge til retningsvisere eller liknende ved hjelp av NeoPixlene på Bitboten og den blir vanskelig å styre, vet du nå hva det kan skyldes.

```blocks
radio.setGroup(1)
// @highlight
basic.showLeds(`
    . . . . .
    . # . # .
    . . . . .
    # . . . #
    . # # # .
    `)
```

### Avslutning @unplugged

Det var alt! Nå er mottageren ferdig. Om tallkodene i sender og mottager stemmer overens skal du nå kunne styre roboten ved å tilte på senderen.
Husk å koble en batteripakke til senderen eller koble den til en PC med USB-kabel før du tester roboten.
Senderen må ha strøm for å virke.


```package
bitbot=github:4tronix/BitBot
```

<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
