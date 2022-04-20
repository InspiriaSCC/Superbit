### @activities true

# Superbit - Kodeøkt 1: Bli kjent med Micro:Bit og MakeCode
## Introduksjon
### Introduksjon @unplugged
MakeCode-miljøet består av tre deler: Til venstre på skjermen ser du en Micro:Bit-simulator som viser hva koden din gjør med Micro:Biten.
I menyen midt på skjermen ser du en kolonne med fargede kategorier. Her finner du alle blokkene du trenger for å bygge koden din.
Den store flaten til høyre på skjermen er arbeidsbordet ditt. Her plasserer du blokker fra menyen i midten for å bygge et program som kan kjøres av Micro:Biten.
Når du flytter en blokk i arbeidsområdet, følger alle blokkene som er festet under blokken også med.
***Du kan flytte en enkeltblokk ved å holde inn Ctrl-knappen mens du klikker og drar.***
La oss varme opp litt lett kode til å begynne med.

### La oss starte enkelt @unplugged

Tradisjonen tro starter vi med skrive "Hello world" og får programmet til å vise teksten på Micro:Biten. 
Nå skal vi se på hva du trenger for å bruke displayet til Micro:Biten ved hjelp av MakeCode-blokker.

### Steg 1: Startblokkene
De aller fleste av kodeblokkene i MakeCode må legges inn i en startblokk for at koden skal kunne kjøres.
Når du starter MakeCode vil du alltid se to sånne startblokker på arbeidsbordet ditt. Du trenger ikke å bruke begge.
Mange blokker vil være grå på skjermen om de legges utenfor en startblokk. Det betyr at de ikke er en del av et program, og at kommandoene i disse blokkene ikke vil utføres.


### Steg 2: Tekst i en uendelig løkke
Å vise tekst er en ``||Basic.Basis||``-funksjon i MakeCode.
Klikk på ``||Basic.Basis||`` for å åpne ``||Basic.Basis||``menyen og hent ut blokken ``||Basic.vis tekst||``.
Plasser blokken i ``||Basic.gjenta for alltid||``-blokken på arbeidsbordet. Nå kan du endre teksten inni blokken til hva du vil.
Når du har skrevet inn teksten du vil vise, kobler du Micro:Biten til enheten du jobber på, så trykker du på **"Last ned"** nederst til venstre på skjermen og venter til lyset på baksiden av Micro:Biten har sluttet å blinke.
Nå skal teksten din vises i displayet. Siden displayet bare er 5x5 pixler, må teksten rulle forbi i displayet.

```blocks

basic.forever(function () {
    basic.showString("Hello!")
})
```

### Forskjellen på "ved start" og "gjenta for alltid" @unplugged

Når du plasserer blokker inne i ``||Basic.gjenta for alltid||``-blokken vil koden gjentas så lenge Micro:Biten er tilkoblet strøm.
Som du sikkert la merke til ligger det en blokk til på arbeidsbordet når man starter MakeCode.
``||Basic.ved start||``-blokken kjører koden som ligger der en gang, og så stopper den.
Likevel er ``||basic.ved start||`` en svært viktig blokk.
Det er der du definerer variabler som skal brukes flere steder i programmet (globale variabler), og det er der man som regel setter opp startkriteriene i koden.
``||Basic.gjenta for alltid||``-løkken er fin dersom du lager litt kode som skal kjøre igjen og igjen, som for eksempel en tekst som skal rulle over displayet gjentatte ganger.
Variabler og andre kodeblokker som trengs mange steder i programmet plasseres i `||Basic.ved start||``-blokken

### Steg 3: Tekst som vises bare én gang

Klikk og dra tekstblokken din fra ``||Basic.gjenta for alltid||``-blokken og inn i ``||Basic.ved start||``-blokken.
Last ned progreammet til Micro:Biten og observer hva som skjer.

```blocks
basic.showString("Hello!")
```

### Steg 4: Vise tall

Å vise tall er like enkelt som å vise en tekststreng.
Det er likevel viktig å huske på at MakeCode behandler tall og tekststrenger forskjellig.
Før du går videre må du fjerne ``||Basic.vis tekst||`` fra ``||Basic.ved start||``.
For å vise et tall må du hente blokken ``||basic.vis tall||`` fra ``||basic.Basis||``-menyen.
Sett blokken inn i ``||basic.ved start||``, skriv inn et tall og last ned programmet til Micro:Biten.

```blocks
basic.showNumber(8)
```

### Steg 5: Vise ikoner

Du kan også vise ferdige ikoner i displayet.
Til det bruker du ``||basic.vis ikon||`` fra ``||basic.Basis||``-menyen.
Fjern ``||Basic.vis tall||`` fra ``||Basic.ved start||`` og sett inn en ``||basic.vis ikon||``.
Klikk på den lille hvite pilen til høyre for hjerteikonet for å velge ikon.

```blocks
basic.showIcon(IconNames.Heart)
```

### Steg 6: Lage egne bilder

Fjern ``||basic.vis ikon||``-blokken fra koden din før du går videre.
I tillegg til ferdige ikoner kan du også tegne dine egne bilder på 5x5 piksler.
Da bruker du ``||basic.vis skjerm||``-blokken fra ``||basic.Basis||``-menyen.
Hent den og sett den inn i ``||basic.ved start||``-blokken.
Hver av de 25 rutene på denne blokken representerer en LED på displayet.
Klikk på ruter for å slå lyset av og på.
Klarer du å tegne et smilefjes?

```blocks
basic.showLeds(`
    . . . . .
    . # . # .
    . . . . .
    # . . . #
    . # # # .
    `)
```

### Animasjoner @unplugged

Om du vil lage animasjoner på displayet, kan du bruke det du har lært til nå.
Det eneste du trenger i tillegg er blokken ``||pause (ms)||`` fra ``||basic.Basis||``-menyen.
Denne blokken brukes for at man skal rekke å oppfatte et bilde i displayet før programmet går videre.

### Steg 7: Animasjoner

Fjern koden din fra arbeidsområdet.
Hent en ny ``||Basic.gjenta for alltid||``-blokk fra ``||basic.Basis||``-menyen.
Hent en ny ``||basic.vis skjerm||``-blokk fra ``||basic.Basis||``-menyen og tegn det første bildet i animasjonen din.
I eksemplet lager vi et bankende hjerte.

```blocks
basic.forever(function () {
    basic.showLeds(`
        . # . # .
        # # # # #
        # # # # #
        . # # # .
        . . # . .
        `)
})
```

### Steg 8: Animasjoner

Før vi setter inn neste bilde i animasjonen trenger vi å pause programmet lenge nok til at den som ser på animasjonen rekker å oppfatte bildet.
Hent en ``||pause (ms)||``-blokk fra ``||basic.Basis||``-menyen og sett den inn under ``||basic.vis skjerm||``-blokken.

```blocks
basic.forever(function () {
    basic.showLeds(`
        . # . # .
        # # # # #
        # # # # #
        . # # # .
        . . # . .
        `)
    basic.pause(100)
})
```

### Steg 9: Fullfør animasjonen

Du kan lage animasjonen din så lang du vil, men i eksemplet bruker vi bare noen få bilder.
Husk å sette en pauseblokk mellom hvert bilde og etter det siste bildet i ``||Basic.gjenta for alltid||``-blokken.
Du kan kopiere en blokk ved å høyreklikke på den og velge **"Lag kopi"** fra rullegardinmenyen som dukker opp.
Dette gjør det ofte enklere når du skal foreta små endringer mellom bildene i en animasjon.
Juster tiden mellom blokkene slik at animasjonen vises slik du foretrekker.

```blocks
basic.forever(function () {
    basic.showLeds(`
        . # . # .
        # # # # #
        # # # # #
        . # # # .
        . . # . .
        `)
    basic.pause(100)
    basic.showLeds(`
        . . . . .
        . # . # .
        . # # # .
        . . # . .
        . . . . .
        `)
    basic.pause(100)
    basic.showLeds(`
        . . . . .
        . . . . .
        . . # . .
        . . . . .
        . . . . .
        `)
    basic.pause(100)
    basic.showLeds(`
        . . . . .
        . # . # .
        . # # # .
        . . # . .
        . . . . .
        `)
    basic.pause(100)
})
```


### Det var det!
Godt jobba! Nå har du lært de mest grunnleggende blokkene som brukes til å vise tall, tekst og bilder på displayet.
I neste runde skal vi se nærmere på hvordan vi kan bruke det du har lært til å lage en elektronisk terning.

* for PXT/microbit
<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
