### @activities true

# Superbit del 4: Lag et spill - Funksjoner og spillblokker
## Introduksjon
### Introduksjon @unplugged

Ved hjelp av displayet og inndata kan man lage forskjellige spill til Micro:Bit.
Alle funksjoner som har med spill å gjøre finner du under **"Avansert"** i blokkemenyen.
Denne gjennomgangen er ganske lang, så sett av litt god tid.
Du skal nå lære å programmere spillet som ligger på alle nye Micro:Bits når de startes første gang.
Spillet kalles *"Chase the dot"* på engelsk. Fang prikken eller fang pixelen kan man kanskje kalle det på norsk?
Spillet går ut på å styre en lysende prikk som skal fange en annen prikk som blinker.
Du må vende på hele Micro:Biten for å få prikken du styrer til å falle ned mot byttet den jakter på.

### Steg 1 Lag variablene

Det første du må gjøre er å lage en variabel for hver prikk.
Gå til ``||variables.Variabler||``-menyen og velg **"Lag en variabel..."**.
Lag to variabler, en som du kaller ``||variables.jeger||`` og en som du kaller ``||variables.bytte||``.
Hent to ``||variables.sett bytte til||``-blokker fra ``||variables.Variabler||``-menyen og dra dem inn i ``||basic.ved start||``-blokken.
Endre den ene slik at det står ``||variables.sett bytte til||`` i en blokk og ``||variables.sett jeger til||`` i den andre.

```blocks
let bytte = 0
let jeger = 0
```

### Steg 2 Spillmenyen

Nå trenger du to blokker fra menyen med spillblokker.
Klikk på **"Avansert"** nederst i blokkmenyen så menyen utvides.
Klikk på ``||game.Spill||``-menyen som dukker opp og velg blokken ``||game.lag brikke på x: 0 y: 0||``.
Plasser en slik blokk i det hvite feltet i ``||variables.sett bytte til||``-blokken og en i ``||variables.sett jeger til||``-blokken.
Endre X og Y verdiene i "bytteblokken" så det står ``||variables.sett bytte til||`` ``||game.lag brikke på x: 2 y: 2||`` og ``||variables.sett jeger til||`` ``||game.lag brikke på x: 0 y: 0||``

```blocks
// @highlight
let bytte = game.createSprite(2, 2)
let jeger = game.createSprite(0, 0)
```

### Micro:Bit-displayet og koordinater @unplugged

Displayet til Micro:bit behandles som et koordinatsystem av programmet.
Koordinatene går fra 0 til 4, ikke fra 1 til 5, selv om det displayet har 5 x 5 pixler.
I programmering er det vanlig å starte rekker og lister med 0.
Koordinaten 0,0 er i det ene hjørnet av displayet.
Koordinatene 2,2 er midt på displayet.

### Steg 3 Lysstyrke og blinking

For at spilleren skal se forskjell på jeger og bytte, må du hente to ``||game.sprite angir x til||``-blokker fra ``||game.Spill||``-menyen.
klikk på den lille pilen til høyre for ``||variables.sprite||`` på den første blokken og velg ``||variables.bytte||``.
Gjør det samme på den andre blokken, men velg ``||variables.jeger||``
Klikk på den lille pilen til høyre for ``||game.x||`` i ``||game.bytte||``-blokken og velg ``||game.blinke||``.
Sett tallet bak ``||game.blinke||`` til 3.
Klikk på den lille pilen til høyre for ``||game.x||`` i ``||game.jeger||``-blokken og velg ``||game.lysstyrke||``.
Sett tallet bak ``||game.lysstyrke||`` til 5.

```blocks
let bytte = game.createSprite(2, 2)
let jeger = game.createSprite(0, 0)
bytte.set(LedSpriteProperty.Blink, 3)
jeger.set(LedSpriteProperty.Brightness, 5)
```

### Funksjoner @unplugged

I neste trinn skal du lage en funksjon.
En funksjon er kode som kan hentes av programmet når programmet trenger den.
Funksjoner bruker vi når vi trenger å kjøre den samme koden flere forskjellige steder i et program, så vi slipper å skrive den samme koden mange ganger.
Det kan minne om løkker, men mens løkker kjører koden flere ganger rett etter hverandre, kan en funksjon kjøre koden en gang og la programmet gå videre.
Neste gang programmet trenger funksjoene, kan du hente inn funksjonen igjen.
Det kalles vanligvis å *kalle* på en funksjon.
Ofte gir man funksjoner navn med stor førstebokstav, for lettere å skille dem fra variabler som gjerne har liten førstebokstav.

### Steg 4 Lag en funksjon

Å lage en funksjon minner om å lage en variabel.
Funksjonsmenyen ligger under **"Avansert"**.
Klikk på ``||functions.Funksjoner||``-menyen og velg **"Lag en funksjon..."**
Gi funksjonen navnet NyRunde ved å skrive inn det nye navnet der det står GjørNoe i blokken som dukker opp på skjermen.
Funksjonen legger seg automatisk i arbeidsområdet etter at du har laget den.

```blocks
function NyRunde () {
	
}
```

### Steg 5 Sett inn kode i funksjonen

Når spilleren klarer å fange byttet starter en ny runde.
Da skal et nytt bytte dukke opp et tilfeldig sted på skjermen.
Hent to nye ``||game.sprite angir x til||``-blokker fra ``||game.Spill||``-menyen og bytt ut ``||variables.sprite||`` med ``||variables.bytte||`` i begge.
Endre ``||game.x||`` til ``||game.y||`` i den **ene** av blokkene.
Hent en ``||math.velg tilfeldig 0 til 10||``-blokk fra ``||math.Matematikk||``-menyen og plasser den i det hvite feltet etter ``||game.x||`` i den ene blokken.
Endre 10-tallet til et 4-tall i ``||math.velg tilfeldig 0 til 10||``-blokken.
