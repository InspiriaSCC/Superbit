### @activities true

# Superbit del 14: Servoer del 3
## Bruk servoer til å lage radiostyrt bevegelse - mottager
### Introduksjon @unplugged

I denne gjennomgangen lærer du å programmere en radiomottager som styrer en servo.


### Tilkoblinger @unplugged

Rett foran hjulet på Bitbotens ventre side finner du to kontakter med 3 pinner.
Dette er servokontaktene til Bitboten.
Det fremste paret med pinner er merket P1 og P2.
P1 og P2 er signalutgangene fra Micro:Biten som brukes til å kontrollere servoer.
De to neste parene er merket 5V og GND.
5V gir 5 volts positiv spenning mot GND, som er jordkontaktene.

### Steg 1

Monter en hvit, enkel plastarm til en **180-graderservo** som vist på bildet.
Koble **180-graderservoen** til P0 rekken av kontakter som forklart og vist.
Servoene som følger med Superbit har tre ledninger ut, en brun, en rød og en oransje.
Brun er jordledningen, den skal kobles til GND.
Rød er "+"-ledningen som skal kobles til 5V.
Oransje er signalledningen som skal kobles til P1 eller P2.
Plasser kontakten til servoen på pinnene ved P1 slik at oransje ledning treffer P1, rød ledning treffer 5V og brun ledning treffer GND.

![]()

### Steg 2

Bommen du skal åpne og lukke med radiostyring må monteres på den hvite plastarmen.
Bruk tape eller heftemasse til å feste et stripe bølgepapp eller en ispinne til armen, eller finn noe annet i et lett materiale som kan være bom.
Fest selve servoen til et fast underlag, en pappskive eller liknende ved hjelp av tape eller heftemasse.
Normalt skal du kunne feste servoen liggende flatt med klistremerket opp dersom du vil at bommen skal åpnes vertikalt.
Ønsker du at bommen skal åpnes horisontalt, fester du den slik at den står på høykant med bommen oppå servoen.

### Steg 3

Siden radiostyring krever at Micro:biten bruker radiosignaler, må du begynne med å aktivere radioen og velge en kanal.
Det gør du med blokken ``||radio.radio sett gruppe||`` som du finner i ``||radio.Radio||``-menyen.
Hent en ``||radio.radio sett gruppe||`` og plasser den i ``||basic.ved start||``-blokken.
Sett radioen til ``||radio.gruppe 1||`` dersom du brukete det samme tallene som i eksempelet vårt da du programmerte senderen.

```blocks
radio.setGroup(1)
```

### Steg 4





```package
bitbot=github:4tronix/BitBot
```

<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
