### @activities true

# super:bit - Kodeøkt 2: Terning 
## Introduksjon
### Introduksjon @unplugged
I denne delen lærer du hvordan du får Micro:Bit til å reagere på en handling, eller inndata, som det kalles på kodespråket.
Du kan velge om du vil laste ned programmet til en Micro:Bit, eller spare tid ved å bruke simulatoren.



### Steg 4: Superenkel terning
Når du har lært å vise en tallvariabel i displayet, kan du bruke det til å lage en elektronisk terning.
En inndatafunksjon skal ta seg av hvert terningkast.
Du kan bruke det innebygde akselerometeret i Micro:Bit til terningkastene.
Gå til ``||input.Inndata||``-menyen og hent blokken ``||input.når ristes||``.
Denne blokkene er også en slags startblokk.
Dra den gamle startblokken ut i papirkurven til venstre.

```blocks
input.onGesture(Gesture.Shake, function () {
	
})
```

### Inndata @unplugged

Det finnes flere måter å gi inndata til Micro:Bit på.
Micro:Bit har innebygde sensorer for lys og temperatur, digitalt kompass og akselerometer.
Alle disse kan brukes som inndata.
De to knappene kan brukes hver for seg eller sammen.
I tillegg har Micro:Bit radio og en kontaktstriper som kan ta imot elektroniske signaler.
Vi bruker ristefunksjonen her fordi det passer for en terning.

### Steg 5: Terning uten å lagre variabel
Fra ``||basic.Basis||``-menyen trenger du nå blokken ``||basic.vis tall||`` som du brukte tidligere.
Dra den inn i ``||input.når ristes||``-blokken.
Gå til ``||math.matematikk||``-menyen og hent en ``||math.velg tilfeldig 0 til 10||``-blokk.
Dra den inn i det hvite feltet i ``||basic.vis tall||``-blokken og endre tallene 0 og 10 til 1 og 6.
Nå vil Micro:Biten vise et tilfeldig tall fra og med 1 til og med 6 når den ristes.
Du kan trykke på **"Shake"**-knappen like over B-knappen i simulatoren for å sjekke at koden fungerer. 
Gratulerer! Du har nå laget en terning ved hjelp av to linjer kode!
Om du vil kan du starte terningkastet ved hjelp av andre typer inndata når du går ut av denne veilederen.
Kanskje du får til å kaste terning med et knappetrykk?

```blocks
input.onGesture(Gesture.Shake, function () {
    // @highlight
    basic.showNumber(randint(1, 6))
})
```



* for PXT/microbit
<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
