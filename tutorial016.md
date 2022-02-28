### @activities true

# Superbit del 16: Koble elektronikk til Micro:Biten, del 3 Høyttaler
## Introduksjon
### Introduksjon @unplugged

Micro:Biten kan spille små melodier om du kobler til en høyttaler eller en modulerbar buzzer.
Høyttalere og buzzere kobles alltid mellom pin 0 og GND nå man skal bruke musikkfunksjonen i MakeCode.
I esken som fulgte med Superbit er det en pose med 5 modulerbare buzzere.
Buzzerne har polaritet, det vil si at de har en pluss- og en minuspol, og at de bare fungerer om de kobles riktig vei.
Plusspolen er det lengste beinet på buzzeren, og har et ***"+"***-tegn printet over seg på det svarte plastdekslet.
Plusspolen skal kobles til pin 0 på Micro:Biten.
Minuspolen er det korte beinet.
Minuspolen skal kobles til GND på Micro:Biten.

### Koblinger @unplugged

Du kan godt bruke en svart ledning med krokodilleklemmer for å koble det korte beinet på buzzeren til "GND".
Svarte ledninger brukes ofte for å symbolisere at ledningen går til jord.
"Jord" brukes ofte for å beskrive den negative siden av strømkilden i en likestrømskrets.
Det lange beinet på buzzeren kobler du til kobberstripen på Micro:Biten der det står "0", altså til pin 0.
Nå er Micro:Biten klar til å lage musikk.

![Buzzerkobling](https://raw.githubusercontent.com/Yngel72/Superbit/master/static/Buzzerkobling2.jpg)

### Steg 1

Om du vil spille av en melodi kun 1 gang, bruker du ``||basic.ved start||``-blokken til å legge musikken din inn i.
Gå til ``||music.Musikk||``-menyen og hent en ``||music.play melody at 120 bpm||``-blokk.
Klikk på de hvite firkantene til høyre for notesymbolet i blokken, klikk på ***"Galleri"*** og velg en melodi fra rullegardinmenyen.
Du kan endre hastigheten på melodien ved å trykke der det står ***"120"*** og endre antall bpm (beats per minute).
Dra blokken inn i ``||basic.ved start||``-blokken og last programmet ditt ned til Micro:Biten.
Hør på melodien som spilles av på Micro:Biten

```blocks
music.playMelody("C5 B A G F E D C ", 120)
```

### Steg 2

``||music.play melody at 120 bpm||``-blokken gir deg en forenklet, visuell form for musikkredigering der du ikke kan endre varigheten for enkeltnoter.
Det gir deg begrensede muligheter, sånn rent musikalsk.
Alle noter er satt til å vare et fjerdedels taktslag, og dette kan ikke endres når du bruker denne blokken.
Du kan lage egne, enkle melodier ved å bruke ***"redigeringsprogram"***-valget når du klikker på firkantene i blokken.
Redigeringsprogrammet i denne blokken lar deg kun lage melodier i C-dur med enstrøken C i bunnen.
Den øverste linjen i matrisen gir høy C i denne skalaen, den nederste linjen gir enstrøken C.
Linjene imellom gir de andre notene i skalaen.
Matrisen gjør at du kan lage en melodi på 8 fjerdedelsnoter, eller to 4/4-takter om du vil.
Du kan sette flere blokker etter hverandre for å lage lengre melodier.
Lag din egen melodi på 4 takter, last ned og lytt.

![Redigeringsprogram](https://raw.githubusercontent.com/Yngel72/Superbit/master/static/Musikkeditor1.jpg)

```blocks
music.playMelody("C G A E F D G G ", 120)
music.playMelody("C5 B A G F D G G ", 120)
```

### Steg 3

For litt mer avansert musikk kan du bruke blokken ``||music.spill tone midtre C i 1 taktslag||`` fra ``||music.Musikk||``-menyen.
Her har du mulighet til å lage musikk over tre oktaver og får tilgang til alt fra 1/16-noter til helnoter.
Du endrer tone ved å klikke der det står ***"midtre C"*** og lengden på noten ved å klikke der det står ***"1"***.
Hent blokken ``||music.spill tone midtre C i 1 taktslag||`` fra ``||music.Musikk||``-menyen og dra den inn i ``||basic.ved start||``.
Lag en liten melodi ved å kopiere blokken noen ganger og endre toner og notelengder på blokkene.
Klarer du å gjette melodien i hintet?

![Redigeringsprogram](https://raw.githubusercontent.com/Yngel72/Superbit/master/static/Musikkeditor2.jpg)

```blocks
music.playTone(262, music.beat(BeatFraction.Double))
music.playTone(392, music.beat(BeatFraction.Double))
music.playTone(349, music.beat(BeatFraction.Quarter))
music.playTone(330, music.beat(BeatFraction.Quarter))
music.playTone(294, music.beat(BeatFraction.Half))
music.playTone(523, music.beat(BeatFraction.Double))
music.playTone(392, music.beat(BeatFraction.Double))
music.playTone(349, music.beat(BeatFraction.Quarter))
music.playTone(330, music.beat(BeatFraction.Quarter))
music.playTone(294, music.beat(BeatFraction.Half))
music.playTone(523, music.beat(BeatFraction.Double))
music.playTone(392, music.beat(BeatFraction.Double))
music.playTone(349, music.beat(BeatFraction.Quarter))
music.playTone(330, music.beat(BeatFraction.Quarter))
music.playTone(349, music.beat(BeatFraction.Half))
music.playTone(294, music.beat(BeatFraction.Double))
```


