### @activities true

# Superbit: Bli kjent med BBC Micro:Bits grunnleggende funksjoner
## Introduksjon
### Introduksjon @unplugged

I denne gjennomgangen lærer du grunnleggende programmering av BBC Micro:Bit.
Første skritt i ethvert programmeringskurs pleier å være at man lærer seg å skrive ut en liten tekststreng i ved hjelp av kode.
Tradisjonelt skriver man "Hello world" og får programmet til å vise denne strengen på en skjerm eller i et display. 
Nå kan du selvsagt skrive akkurat hva du vil, her kommer i alle fall det du trenger for å vise tekst i displayet til Micro:Biten ved hjelp av MakeCode-blokker som første steg.

### La oss starte enkelt @unplugged
MakeCode-miljøet består av tre deler: Til venstre på skjermen ser du en Micro:Bit-simulator som viser hva koden din gjør med Micro:Biten.
I menyen midt på skjermen ser du en kolonne med fargede kategorier. Her finner du alle blokkene du trenger for å bygge koden din.
Den store flaten til høyre på skjermen er arbeidsbordet ditt. Her plasserer du blokker fra menyen i midten for å bygge kode.
La oss lage litt enkel kode til å begynne med.

### Steg 1
Å vise tekst er en ``||Basic.Basis||``funksjon i MakeCode. Klikk på ``||Basic.Basis||`` for å åpne ``||Basic.Basis||``menyen og hent ut blokken ``||Basic.vis tekst||``.
Plasser blokken i ``||Basic.gjenta for alltid||``-blokken på arbeidsbordet. Nå kan du endre teksten inni blokken til hva du vil.
Når du har skrevet inn teksten du vil vise, kobler du Micro:Biten til enheten du jobber på, så trykker du på "Download" og venter til lyset på baksiden av Micro:Biten har sluttet å blinke.
Nå skal teksten din vises i displayet. Siden displayet bare er 5x5 pixler, må teksten rulle forbi i displayet.

```blocks

basic.forever(function () {
    basic.showString("Hello!")
})
```

### Steg 2
Når du legger blokker til et program inne i ``||Basic.gjenta for alltid||``-blokken vil programmet gjentas så lenge Micro:Biten er tilkoblet strøm.
Som du sikkert la merke til ligger det en blokk til på arbeidsbordet når man starter MakeCode. ``||Basic.ved start||``-blokken vil bare kjøre koden som ligger der en gang, og så stoppe.
``||Basic.gjenta for alltid||``-løkken er fin dersom du lager litt kode som skal kjøre igjen og igjen, som for eksempel en tekst som skal rulle over displayet gjentatte ganger.
Programmer som kjøres en gang, som spill eller liknende, plasserer man i ``||Basic.ved start||``.
Klikk og dra tekstblokken din fra ``||Basic.gjenta for alltid||``-blokken og inn i ``||Basic.ved start||``-blokken. Observer hva som skjer.

```blocks
basic.showString("Hello!")
```

### Steg 3
Å vise tall er like enkelt som å vise en tekststreng. Det er likevel viktig å huske på at MakeCode behandler tall og tekststrenger forskjellig.
For å vise et tall må du hente blokken ``||basic.vis tall||`` fra ``||basic.Basis||``-menyen. Sett blokken inn i ``||basic.ved start||``, skriv inn et tall og last programmet opp til Micro:Biten.

```blocks
basic.showNumber(8)
```

### Steg 4
Du kan også vise ferdige ikoner i displayet. Til det bruker du ``||basic.vis ikon||`` fra ``||basic.Basis||``-menyen.

```blocks
basic.showIcon(IconNames.Heart)
```

### Steg 5
I tillegg til ferdige ikoner kan du også tegne dine egne bilder på 5x5 piksler. Da bruker du ``||basic.vis skjerm||``-blokken fra ``||basic.Basis||``-menyen. Hent den og sett den inn i ``||basic.ved start||``-blokken.
Hver av de 25 rutene på denne blokken representerer en LED på displayet. Klikk på ruter for å slå lyset av og på. Klarer du å tegne et smilefjes?

```blocks
basic.showLeds(`
    . . . . .
    . # . # .
    . . . . .
    # . . . #
    . # # # .
    `)
    ```

###  Steg 6
``||basic.pause||`` og ``||basic.tøm skjerm||`` gjør akkurat det navnene sier.
Noen ganger kjører koden for fort til at man rekker å se noe som dukker opp på skjermen eller utføre en fysisk handling med Micro:Biten før det er for sent.
Da kan man legge inn en ``||basic.pause||`` i koden slik at man rekker å se eller gjøre det som trengs.
Noen ganger vil man at skjermen skal være blank. Da kan du bruke ``||basic.tøm skjerm||`` til å fjerne alt som står der.
  

