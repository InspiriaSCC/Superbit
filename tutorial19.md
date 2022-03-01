### @activities true

# Superbit del 19: Bitbotens NeoPixler
## Bruk de innebygde lysene på Bitboten
### Introduksjon @unplugged

Bitboten har to "horn" på sidene.
På hvert av disse sidene sitter det 6 NeoPixler som kan styres ved hjelp av kode.
I denne økten lærer du hvordan du kontrollerer NeoPixlene på Bitboten ved hjelp av et program.

### Steg 1

Alle blokkene du trenger for å styre NeoPixlene på Bitboten finner du i menyen ``||bitbot.Bitbot/Lys||``.
En fin blokk å starte med er blokken ``||bitbot.sett LED til regnbue||``.
Dra den inn i ``||basic.ved start||``-blokken.
Last ned programmet til Micro:Biten, slå på Bitboten og se hva som skjer.

```blocks
bitbot.ledRainbow()
```

### Steg 2

Du kan animere den fine regnbuen på en veldig enkel måte.
Hent blokken ``||bitbot.roter LED||`` og sett den inn i ``||basic.gjenta for alltid||``-blokken (**ikke** i ``||basic.ved start||``-blokken).
Last ned programmet til Micro:Biten, slå på Bitboten og se på forskjellen.

```blocks
bitbot.ledRainbow()
basic.forever(function () {
    bitbot.ledRotate()
})
```

### Steg 3

Som du sikkert la merke til går animasjonen litt i raskeste laget.
For en litt langsommere animasjon kan du sette inn en ``||basic.pause 100 ms||``-blokk i ``||basic.gjenta for alltid||``-blokken under ``||bitbot.roter LED||``.
Last ned programmet og se hvordan animasjonen endres. Du kan endre tidsverdien i ``||basic.pause||``-blokken om du vil ha enda langsommere animasjon.

```blocks
basic.forever(function () {
    bitbot.ledRotate()
    basic.pause(100)
})
```

### Steg 4

Du kan justere lysstyrken på NeoPixlene med blokken ``||bitbot.sett LED lysstyrke til 40||``.
Klikk på **"40"** og juster lysstyrken med slideren.
Høyeste lysstyrkeverdi er **255**.
Er verdien **0** vil NeoPixlene være slukket.
Hent blokken ``||bitbot.sett LED lysstyrke til 40||`` fra ``||bitbot.Bitbot/Lys||`` og sett den inn i ``||basic.ved start||``-blokken, under ``||bitbot.sett LED til regnbue||``.
Test ut programmet ved å endre litt på lysstyrken et par-tre ganger, og last programmet ned til Micro:Biten etter hver endring.
Velg en lysstyrke du synes er passe før du går videre.
(PS: Høyere lysstyrke tapper batteriene til Bitboten raskere. NeoPixler krever en del strøm.)

```blocks
bitbot.ledRainbow()
bitbot.ledBrightness(132)
```





```package
bitbot=github:4tronix/BitBot
```

<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
