### @activities true

# Superbit del 13: Servoer del 2
## Bruk servoer til å lage radiostyrt bevegelse
### Introduksjon @unplugged

I denne gjennomgangen skal du lage radiosenderen til en fjernstyrt bom som løftes opp og ned av en servo.

### Steg 1

Siden radiostyring krever at Micro:biten bruker radiosignaler, må du begynne med å aktivere radioen og velge en kanal.
Det gør du med blokken ``||radio.radio sett gruppe||`` som du finner i ``||radio.Radio||``-menyen.
Hent en ``||radio.radio sett gruppe||`` og plasser den i ``||basic.ved start||``-blokken.

```blocks
radio.setGroup(1)
```

### Steg 2

For å vise at Micro:Biten som skal være radiosender er på og virker, kan du sette inn et ikon i displayet som vises når senderprogrammet kjører.
Du kan tegne en liten radio, eller velge et annet ikon om du foretrekker det.
Hent en ``||basic.vis skjerm||`` eller ``||basic.vis ikon||`` blokk fra ``||basic.Basis||``-menyen og sett den inn i ``||basic.ved start||``-blokken under ``||radio.radio sett gruppe||``-blokken.

```blocks
radio.setGroup(1)
// @highlight
basic.showLeds(`
    . . . . #
    . . . . #
    # # # # #
    # . # # #
    # # # # #
    `)
```

### Steg 3

Til en bom som bare skal gå opp og ned trenger du egentlig bare to inndata: Åpne og lukke.
Da passer trykknappene fint.
Hent to ``||input.når knapp A trykkes||``-blokker fra ``||input.Inndata||``-menyen og plasser dem i arbeidsområdet.
Endre ``||input.knapp A||`` til ``||input.knapp B||`` i den ene av dem.

```blocks
input.onButtonPressed(Button.A, function () {
	
})
// @highlight
input.onButtonPressed(Button.B, function () {
	
})
```

