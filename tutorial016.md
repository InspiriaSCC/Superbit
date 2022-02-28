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

### begrensninger @unplugged

Musikkredigering i MakeCode har en del begrensninger.
Blokkene du bruker representerer egentlig JavaScript-kode.
JavaScript er et scriptspråk som må kjøres i en nettleser eller et tilsvarende program.
Linjer i scriptspråk leses én og én, det er ikke mulig å kjøre flere linjer samtidig i et program (det som innen programmering kalles multi-threading).
Når man redigerer musikk betyr det at man for eksempel ikke kan kjøre toner oppå hverandre, man kan altså **ikke** lage melodier med flere stemmer eller flere loops som går oppå hverandre.
Derfor er alle melodiene i MakeCode veldig enkle.

### Steg 4

Dersom du bare vil ha en liten melodi lagt inn i et program, for eksempel i slutten av et spill, kan du bruke blokken ``||music.start melodi dadada-daa gjenta en gang||`` fra ``||music.Musikk||``-menyen.
Alt etter hvordan koden i resten av programmet er, kan det hende du må legge inn en ``||basic.pause 100 ms||``-blokk etter melodien og endre tiden slik at melodien rekker å spille ferdig før programmet går videre i koden.
Om du legger flere ``||music.start melodi dadada-daa gjenta en gang||``-blokker med forskjellige melodier rett etter hverandre i koden, vil du bare høre den siste melodien.
Om du legger inn lange nok pauser mellom melodiene, vil alle kunne høres.
Prøv å legge inn tre forskjellige melodier i en ``||ved start||``-blokk, spill av og se hva som skjer.
Forsøk så å legge inn passe lange pauser mellom blokkene så melodiene spilles av i sin helhet etter hverandre.

```blocks
music.startMelody(music.builtInMelody(Melodies.Dadadadum), MelodyOptions.Once)
basic.pause(4500)
music.startMelody(music.builtInMelody(Melodies.Entertainer), MelodyOptions.Once)
basic.pause(4000)
music.startMelody(music.builtInMelody(Melodies.Prelude), MelodyOptions.Once)
```

### Steg 5

Musikk består ofte av gjentagende temaer.
Da kan det være lurt å bruke løkker for å begrense mengden med kode.
I hintet ser du et forsøk på å gjengi et klassisk musikkstykke som kanskje nesten er gjenkjennbart.
Begrensningene i musikkredigeringsprogrammet gjør det litt vanskelig å få til god timing, og nesten umulig å få til synkope.
Klarer du å kopiere koden, og klarer du å kjenne igjen stykket?

```blocks
for (let index = 0; index < 2; index++) {
    music.playTone(196, music.beat(BeatFraction.Whole))
    music.playTone(294, music.beat(BeatFraction.Half))
    music.playTone(494, music.beat(BeatFraction.Half))
    music.playTone(440, music.beat(BeatFraction.Half))
    music.playTone(494, music.beat(BeatFraction.Half))
    music.playTone(440, music.beat(BeatFraction.Half))
    music.playTone(494, music.beat(BeatFraction.Half))
    music.playTone(294, music.beat(BeatFraction.Half))
}
for (let index = 0; index < 2; index++) {
    music.playTone(220, music.beat(BeatFraction.Whole))
    music.playTone(330, music.beat(BeatFraction.Half))
    music.playTone(523, music.beat(BeatFraction.Half))
    music.playTone(494, music.beat(BeatFraction.Half))
    music.playTone(523, music.beat(BeatFraction.Half))
    music.playTone(494, music.beat(BeatFraction.Half))
    music.playTone(523, music.beat(BeatFraction.Half))
    music.playTone(330, music.beat(BeatFraction.Half))
}
for (let index = 0; index < 2; index++) {
    music.playTone(294, music.beat(BeatFraction.Whole))
    music.playTone(440, music.beat(BeatFraction.Half))
    music.playTone(523, music.beat(BeatFraction.Half))
    music.playTone(494, music.beat(BeatFraction.Half))
    music.playTone(523, music.beat(BeatFraction.Half))
    music.playTone(494, music.beat(BeatFraction.Half))
    music.playTone(523, music.beat(BeatFraction.Half))
    music.playTone(440, music.beat(BeatFraction.Half))
}
for (let index = 0; index < 2; index++) {
    music.playTone(196, music.beat(BeatFraction.Whole))
    music.playTone(294, music.beat(BeatFraction.Half))
    music.playTone(494, music.beat(BeatFraction.Half))
    music.playTone(440, music.beat(BeatFraction.Half))
    music.playTone(494, music.beat(BeatFraction.Half))
    music.playTone(440, music.beat(BeatFraction.Half))
    music.playTone(494, music.beat(BeatFraction.Half))
    music.playTone(294, music.beat(BeatFraction.Half))
}
for (let index = 0; index < 2; index++) {
    for (let index = 0; index < 2; index++) {
        music.playTone(330, music.beat(BeatFraction.Whole))
        music.playTone(494, music.beat(BeatFraction.Half))
        music.playTone(659, music.beat(BeatFraction.Half))
        music.playTone(622, music.beat(BeatFraction.Half))
        music.playTone(659, music.beat(BeatFraction.Half))
        music.playTone(622, music.beat(BeatFraction.Half))
        music.playTone(659, music.beat(BeatFraction.Half))
        music.playTone(494, music.beat(BeatFraction.Half))
    }
    for (let index = 0; index < 2; index++) {
        music.playTone(220, music.beat(BeatFraction.Whole))
        music.playTone(330, music.beat(BeatFraction.Half))
        music.playTone(554, music.beat(BeatFraction.Half))
        music.playTone(494, music.beat(BeatFraction.Half))
        music.playTone(554, music.beat(BeatFraction.Half))
        music.playTone(494, music.beat(BeatFraction.Half))
        music.playTone(554, music.beat(BeatFraction.Half))
        music.playTone(440, music.beat(BeatFraction.Half))
    }
    for (let index = 0; index < 2; index++) {
        music.playTone(294, music.beat(BeatFraction.Whole))
        music.playTone(440, music.beat(BeatFraction.Half))
        music.playTone(587, music.beat(BeatFraction.Half))
        music.playTone(554, music.beat(BeatFraction.Half))
        music.playTone(587, music.beat(BeatFraction.Half))
        music.playTone(554, music.beat(BeatFraction.Half))
        music.playTone(587, music.beat(BeatFraction.Half))
        music.playTone(440, music.beat(BeatFraction.Half))
    }
    for (let index = 0; index < 2; index++) {
        music.playTone(196, music.beat(BeatFraction.Whole))
        music.playTone(294, music.beat(BeatFraction.Half))
        music.playTone(494, music.beat(BeatFraction.Half))
        music.playTone(440, music.beat(BeatFraction.Half))
        music.playTone(494, music.beat(BeatFraction.Half))
        music.playTone(440, music.beat(BeatFraction.Half))
        music.playTone(494, music.beat(BeatFraction.Half))
        music.playTone(294, music.beat(BeatFraction.Half))
    }
}

```


### Avslutning @unplugged

Nå har du lært det grunnleggende om hvordan du lager musikk med MakeCode og Micro:Bit.
Det finnes blokker for volumjustering og tempoendring underveis også, og det finnes blokker som er laget for å utløse lyd underveis i en melodi.
Alle disse blokkene krever en del eksperimentering og prøving og feiling for å få til å fungere med de begrensningene som finnes når det gjelder lyd på Micro:Bit.
Det finnes også blokker som kun kan brukes av Micro:Bit V2.
Med Micro:Bit V2 er det mulig å spille av noen lyder som overlapper med melodiblokker.
Grunnprinsippet for musikk på Micro:Bit er likevel at du kun kan spille en tone av gangen.
Lykke til med musikkproduksjonen!


<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
