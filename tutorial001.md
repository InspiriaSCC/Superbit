### @activities true

# Superbit: Bli kjent med BBC Micro:Bits grunnleggende funksjoner
## Introduksjon
### Introduksjon @unplugged

I denne gjennomgangen lærer du grunnleggende programmering av BBC Micro:Bit.
Første skritt i ethvert programmeringskurs pleier å være at man lærer seg å skrive ut en liten tekststreng i ved hjelp av kode.
Tradisjonelt skriver man "Hello world" og får programmet til å vise denne strengen på en skjerm eller i et display. 
Nå kan du selvsagt skrive akkurat hva du vil, her kommer i alle fall det du trenger for å vise tekst i displayet til Micro:Biten ved hjelp av MakeCode-blokker som første steg.

### Steg 1

I menyen midt på skjermen ser du en kolonne med fargede kategorier. Å vise tekst er en ``||Basic.Basic||`` funksjon i MakeCode. Klikk på ``||Basic.Basic||`` for å åpne ``||Basic.Basic||``-menyen og hent ut blokken ``||Basic.show string||``.
Plasser blokken i ``||Basic.forever||``-blokken på arbeidsbordet. Nå kan du endre teksten inni blokken til hva du vil.
Når du har skrevet inn teksten du vil vise, kobler du Micro:Biten til enheten du jobber på, så trykker du på "Download" og venter til lyset på baksiden av Micro:Biten har sluttet å blinke.
Nå skal teksten din vises i displayet. Siden displayet bare er 5x5 pixler, må teksten rulle forbi i displayet.

```blocks

loops.forever(function () {
    basic.showString("Hello!")
})
```

### Steg 2

Når du legger blokker til et program inne i ``||Basic.forever||``-blokken vil programmet gjentas så lenge Micro:Biten er tilkoblet strøm.
Som du sikkert la merke til ligger det en blokk til på arbeidsbordet når man starter MakeCode. ``||Basic.on start||``-blokken vil bare kjøre koden som ligger der en gang, og så stoppe.
``||Basic.forever||``-løkken er fin dersom du lager et program som skal kjøre igjen og igjen, som for eksempel en tekst som skal rulle over displayet gjentatte ganger.
Programmer som kjøres en gang, som spill eller liknende, plasserer man i ``||Basic.on start||``.
Klikk og dra tekstblokken din fra ``||Basic.forever||``-blokken og inn i ``||Basic.on start||``-blokken. Observer hva som skjer.

```blocks
basic.showString("Hello!")
```




