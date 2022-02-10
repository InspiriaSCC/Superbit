### @activities true

# Superbit del 2: Variabler, inndata og 
## Introduksjon
### Introduksjon @unplugged
I denne delen lærer du hvordan du lager og bruker en variabel og hvordan du får Micro:Bit til å reagere på en handling, eller inndata, som det kalles på kodespråket.
Du lærer også hvordan du kan bruke en viktig logikkfunksjon: "Hvis ellers så", eller "if then else" som den oftest kalles.
Du kan velge om du vil laste programmene opp til en Micro:Bit, eller spare tid ved å bruke simulatoren.

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
// @highlight
basic.showNumber(minVariabel)
```

### Steg 4: Superenkel terning
Når vi kan vise en tallvariabel i displayet, kan vi bruke det til å lage en elektronisk terning.
En inndatafunksjon kan ta seg av hvert terningkast. Vi kan bruke det innebygde akselerometeret i Micro:Bit til terningkastene.
Gå til ``||input.Inndata||``-menyen og hent blokken ``||input.når ristes||``.
Plasser blokken hvor som helst i arbeidsområdet, denne blokkene er også en startblokk.
Dra den gamle startblokken ut i papirkurven til venstre.

```blocks
input.onGesture(Gesture.Shake, function () {
	
})
```

### Inndata @unplugged

Det finnes flere måter å gi inndata til Micro:Bit på. Micro:Bit har innebygde sensorer for lys og temperatur, digitalt kompass og akselerometer.
Alle disse kan brukes som inndata. Det finnes også to knapper som kan brukes hver for seg eller sammen.
I tillegg har den radio og en rekke kontakter som kan ta imot elektroniske signaler.
Vi bruker ristefunksjonen her, fordi det passer for en terning.

### Steg 5: Terning uten å lagre variabel
Fra ``||basic.Basis||``-menyen trenger du nå blokken ``||basic.vis tall||`` som du brukte tidligere.
Dra den inn i ``||input.når ristes||``-blokken.
Gå til ``||math.matematikk||``-menyen og hent en ``||math.velg tilfeldig 0 til 10||``-blokk.
Dra den inn i det hvite feltet i ``||basic.vis tall||``-blokken og endre tallene 0 og 10 til 1 og 6.
Nå skal Micro:Biten vise et tilfeldig tall fra og med 1 til og med 6 når den ristes.
Du kan trykke på **"Shake"**-knappen like over B-knappen på høyre side av simulatoren for å sjekke at koden fungerer. 
Gratulerer! Du har nå laget en terning ved hjelp av to linjer kode!

```blocks
input.onGesture(Gesture.Shake, function () {
    // @highlight
    basic.showNumber(randint(1, 6))
})
```

### Terning med variabel @unplugged
Ofte vil det være en fordel å legge data inn i en variabel i stedet for å vise dem direkte.
Nå skal du utvide terningen med å legge resultatet inn i en variabel før du viser det.
Senere skal vi bruke denne variabelen til å få terningen litt føles litt mer realistisk ut.
Bruk av variabler i MakeCode krever alltid to trinn.
Først må variabelen opprettes og gis et navn.
Det gjør at det lages en egen blokk for denne variabelen i ``||variables.Variabler||``-menyen.
Så må variabelen defineres i selve koden og gis en verdi.
Blokken ``||variables.sett <variabelnavn> til||`` brukes for å definere en variabel i koden.

### Steg 6: Terning med variabel
Først må du opprette den nye variabelen. Klikk på ``||variables.Variabler||``-menyen og velg **"Lag ny variabel..."**.
Gi variabelen et navn som sier noe om hva den er for noe.
Denne kan du kalle "terningkast".
Det er en god vane å definere variabler øverst i koden, så hent en ``||variables.sett terningkast til||``-blokk fra ``||variables.Variabler||``-menyen og plasser den øverst i ``||input.når ristes||``-blokken.

```blocks
let terningkast = 0
input.onGesture(Gesture.Shake, function () {
    // @highlight
    terningkast = 0
    basic.showNumber(randint(1, 6))
})
```

### Steg 7: Terning med variabel
Dra den lille blokken ``||math.velg tilfeldig 1 til 6||`` fra ``||basic.vis tall||``-blokken til det hvite feltet i ``||variables.sett terningkast til||``.
Nå vil variabelen ``||variables.terningkast||`` settes til et tilfeldig tall fra 1 til 6 hver gang noen rister på Micro:Biten.
For å vise resultatet må variabelen være tallet som skal vises i displayet.
Klikk på ``||variables.Variabler||``-menyen, hent den lille variabelblokken ``||variables.terningkast||`` og plasser den i det hvite feltet i ``||basic.vis tall||``
Når du rister på Micro:Biten, skjer akkurat det samme som ved den forrige terningen du lagde, men siden du nå bruker en variabel, kan vi endre på dette i neste steg.

```blocks
let terningkast = 0
input.onGesture(Gesture.Shake, function () {
    terningkast = randint(1, 6)
    // @highlight
    basic.showNumber(terningkast)
})

```

### Steg 8: Terning med øyne, del 1
Denne delen er litt lengre enn de forrige.
Nå skal du bruke noen av de viktigste algoritmene i programmering til å lage et ordentlig program.
Først må du fjerne blokken ``||basic.vis tall||``fra programmet ditt. Kast den i papirkurven.
Nå trenger du en ``||logic.hvis sant så ellers||``-blokk fra ``||logic.Logikk||``-menyen.
Dra den inn i ``||input.når ristes||``-blokken og plasser den **under** ``||variables.sett terningkast til||``-blokken.

```blocks
let terningkast = 0
input.onGesture(Gesture.Shake, function () {
    terningkast = randint(1, 6)
    // @highlight
    if (true) {
    	
    } else {
    	
    }
})
```

### Logisk sjekk @unplugged
Nå skal du foreta en logisk sjekk.
Du skal først sjekke om variabelen "terningkast" har verdien 1.
Hvis den har verdien 1, skal Micro:biten vise et terningøye i displayet.
Om verdien ikke er 1, skal programmet gjøre en ny sjekk for verdien 2.
Dersom verdien er 2, skal Micro:Biten vise to terningøyne i displayet.
Om verdiene ikke er 2 heller, gjøres en ny sjekk, helt til programmet finner den sanne verdien av "terningkast".
I alt må du sjekke 5 ganger.
Etter den femte gangen finnes det bare en mulighet igjen, siden "terningkast" bare kan ha 6 mulige verdier, så da trenger du ikke sjekke.

### Steg 9: Terning med øyne, del 2
For å sammenlikne to tall eller variabler bruker du blokken ``||logic.0 = 0||`` fra ``||logic.Logikk||``-menyen.
Hent blokken ``||logic.0 = 0||`` og plasser den i det øverste heksagonet i ``||logic.hvis sant så ellers||``-blokken.
Hent den lille variabelblokken til ``||variables.terningkast||`` i ``||variables.Variabler||``-menyen og plasser den i det første hvite feltet i ``||logic.0 = 0||``-blokken.
I det andre feltet skriver du tallet 1.

```blocks
let terningkast = 0
input.onGesture(Gesture.Shake, function () {
    terningkast = randint(1, 6)
    // @highlight
    if (terningkast == 1) {
    	
    } else {
    	
    }
})
```

### Steg 10: Terning med øyne, del 3
I det øverste gapet i ``||logic.hvis sant så ellers||``-blokken må du nå plassere blokken ``||basic.vis skjerm||`` fra ``||basic.Basis||``-menyen.
Tegn et terningøye på skjermen ved å klikke på ruten midt i ``||basic.vis skjerm||``-blokken.

```blocks
let terningkast = 0
input.onGesture(Gesture.Shake, function () {
    terningkast = randint(1, 6)
    if (terningkast == 1) {
        // @highlight
        basic.showLeds(`
            . . . . .
            . . . . .
            . . # . .
            . . . . .
            . . . . .
            `)
    } else {
    	
    }
})
```

### Kopiere og endre blokker @unplugged

Nå skal du gjøre den samme logiske sjekken for alle de mulige terningkastresultatene.
Du kan kopiere en blokk ved å høyreklikke på blokken og velge **"Lag kopi"** fra rullegardinmenyen som dukker opp.
Det sparer deg litt tid når du nå skal bruke de samme blokkene flere ganger med små endringer.
Du kan også kopiere en blokk ved å klikke på den og så trykke Ctrl-C etterfulgt av Ctrl-V på tastaturet, om du foretrekker å bruke hurtigtaster.
Når du har kopiert en blokk må du ofte gjøre små endringer i blokken der du skal bruke den på nytt.
Dette er fort gjort å glemme, men nå er du advart.

### Steg 11: Terning med øyne, del 4

Når du nå skal gjøre flere logiske sjekker i den samme ``||logic.hvis sant så ellers||``-blokken, legger du sikker merke til at det bare finnes et heksagon du kan legge en sånn sjekk inn i, og det er jo allerede opptatt.
For å utvide ``||logic.hvis sant så ellers||``-blokken må du trykke på det lille "+"-tegnet nederst i venstre hjørne av blokken.
Da vil det dukke opp et nytt gap og et nytt heksagon.
Du kan trykke flere ganger og få flere gap.
Om du skulle trykke for mange ganger, kan du trykke på det lille "-"-tegnet på høyre side i den øverste armen av det siste gapet for å fjerne det.
Trykk 4 ganger på det lille "+"-tegnet så du har 5 gap under det som allerede inneholder en ``||basic.vis skjerm||``-blokk.

```blocks
let terningkast = 0
input.onGesture(Gesture.Shake, function () {
    terningkast = randint(1, 6)
    // @highlight
    if (terningkast == 1) {
        basic.showLeds(`
            . . . . .
            . . . . .
            . . # . .
            . . . . .
            . . . . .
            `)
    } else if (false) {
    	
    } else if (false) {
    	
    } else if (false) {
    	
    } else if (false) {
    	
    } else {
    	
    }
})
```

### Steg 12: Terning med øyne, del 5

Nå kan du kopiere den lille, heksagonale ``||logic.terningkast = 1||``-blokken fra  øverst i ``||logic.hvis sant så ellers||``-blokken og plassere den i det neste ledige heksagonet.
Endre tallet 1 til 2.
Kopier ``||basic.vis skjerm||``-blokken fra de øverste gapet og legg kopien i gap nummer to.
Endre fra et øye til to ved å klikke en gang på ruten som er hvit og finn to andre ruter du kan bruke for at det skal se ut som to øyne på en terning.

```blocks
let terningkast = 0
input.onGesture(Gesture.Shake, function () {
    terningkast = randint(1, 6)
    if (terningkast == 1) {
        basic.showLeds(`
            . . . . .
            . . . . .
            . . # . .
            . . . . .
            . . . . .
            `)
    } else if (terningkast == 2) {
        // @highlight
        basic.showLeds(`
            . . . . #
            . . . . .
            . . . . .
            . . . . .
            # . . . .
            `)
    } else if (false) {
    	
    } else if (false) {
    	
    } else if (false) {
    	
    } else {
    	
    }
})
```

### Steg 13: Terning med øyne, del 6

Du må gjenta prosessen i Steg 12 for resultatene 3, 4 og 5 også.
Kopier eller hent inn blokkene som trengs for å fylle de neste 3 heksagonene og gapene i ``||logic.hvis sant så ellers||``-blokken.
Husk å endre tallet det sjekkes for i ``||logic.heksagonene||`` og antall øyne på ``||basic.vis skjerm||``-blokkene.


```blocks
let terningkast = 0
input.onGesture(Gesture.Shake, function () {
    terningkast = randint(1, 6)
    if (terningkast == 1) {
        basic.showLeds(`
            . . . . .
            . . . . .
            . . # . .
            . . . . .
            . . . . .
            `)
    } else if (terningkast == 2) {
        basic.showLeds(`
            . . . . #
            . . . . .
            . . . . .
            . . . . .
            # . . . .
            `)
    } else if (terningkast == 3) {
        basic.showLeds(`
            . . . . #
            . . . . .
            . . # . .
            . . . . .
            # . . . .
            `)
    } else if (terningkast == 4) {
        basic.showLeds(`
            # . . . #
            . . . . .
            . . . . .
            . . . . .
            # . . . #
            `)
    } else if (terningkast == 5) {
        basic.showLeds(`
            # . . . #
            . . . . .
            . . # . .
            . . . . .
            # . . . #
            `)
    } else {
    	
    }
})
```

### Steg 14: Terning med øyne, del 7
Over det siste gapet trenger du ingen ``||logic.terningkast = 6||``-blokk, for 6 trenger du ikke sjekke for.
Alle resultatene er sjekket, bortsett fra 6, så da er det jo bare en mulighet igjen.
Alt du trenger å gjøre nå er å lage den siste ``||basic.vis skjerm||``-blokken i det siste gapet, og så er terningen klar.
Vi anbefaler å laste programmet opp til Micro:Biten. Det er noe eget ved å riste på en digital terning man har laget selv.
Det var det hele! Gratulerer! Du har nettopp programmert en kul elektronisk terning!

```blocks
let terningkast = 0
input.onGesture(Gesture.Shake, function () {
    terningkast = randint(1, 6)
    if (terningkast == 1) {
        basic.showLeds(`
            . . . . .
            . . . . .
            . . # . .
            . . . . .
            . . . . .
            `)
    } else if (terningkast == 2) {
        basic.showLeds(`
            . . . . #
            . . . . .
            . . . . .
            . . . . .
            # . . . .
            `)
    } else if (terningkast == 3) {
        basic.showLeds(`
            . . . . #
            . . . . .
            . . # . .
            . . . . .
            # . . . .
            `)
    } else if (terningkast == 4) {
        basic.showLeds(`
            # . . . #
            . . . . .
            . . . . .
            . . . . .
            # . . . #
            `)
    } else if (terningkast == 5) {
        basic.showLeds(`
            # . . . #
            . . . . .
            . . # . .
            . . . . .
            # . . . #
            `)
    } else {
        basic.showLeds(`
            # . . . #
            . . . . .
            # . . . #
            . . . . .
            # . . . #
            `)
    }
})
```

