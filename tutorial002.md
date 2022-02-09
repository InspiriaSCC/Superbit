### @activities true

# Superbit del 2: Variabler, inndata og 
## Introduksjon
### Introduksjon @unplugged
I denne delen lærer du hvordan du lager og bruker en variabel og hvordan du får Micro:Bit til å reagere på en handling, eller inndata, som det kalles på kodespråket.
Du lærer også hvordan du kan bruke en viktig logikkfunksjon: Hvis så

### Steg 1: Variabler
Første gangen du klikker på ``||variables.variabler||``-menyen vil den være nesten tom.
Klikk på ``||variables.variabler||`` og velg "Lag en variabel". Gi variabelen navnet "minVariabel".
Det er en god vane å bruke liten førstebokstav på variabelnavn for å skille variabler fra f.eks. funksjoner, som gjerne får stor førstebokstav.

### Steg 2: Definer en variabel
Før du kan bruke variabelen du nettopp lagde, må den defineres i programmet ditt.
Klikk på ``||variables.variabler||`` og legg merke til at du nå har fått flere valg.
Hent blokken ``||variables.sett minVariabel til||`` og legg den inn i ``||basic.ved start||``-blokken.
Nå har du definert variabelen og satt den til null.
Sett variabelen din til et annet tall ved å skrive inn et tall i det hvite feltet.

```blocks
let minVariabel = 7
```

### Steg 3: Vis verdien av variabelen
For å vise verdien av variabelen din, må du sende variabelen til displayet.
Til det trenger du blokken ``||basic.vis tall||``.
Hent den fra ``||basic.Basis||``-menyen og legg den inn i startblokken **under** ``||variables.sett minVariabel til||``-blokken. Det er viktig at den plasseres under den forrige blokken.
Variabler må alltid defineres før du kan bruke dem, derfor er det en god vane å plassere alle ``||variables.sett [variabelnavn] til||``-blokker øverst i koden din.
Klikk på ``||variables.variabler||``-menyen, hent den lille variabelblokken ``||variables.minVariabel||`` og sett den inn der det står 0 i blokken ``||basic.vis tall||``.
``||variables.minVariabel||`` er, som du sikkert har skjønt, variabelen du lagde tidligere.

```blocks
let tall = minVariabel
basic.showNumber(minVariabel)
```
