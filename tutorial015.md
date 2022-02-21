### @activities true

# Superbit del 15: Servoer del 4
## Lag en bom som styres av en avstandssensor
### Introduksjon @unplugged

I denne gjennomgangen lærer du å programmere bom som åpnes ved hjelp av en avstandssensor.

### Tilkoblinger @unplugged

Rett foran hjulet på Bitbotens ventre side finner du to kontakter med 3 pinner.
Dette er servokontaktene til Bitboten.
Det fremste paret med pinner er merket P1 og P2.
P1 og P2 er signalutgangene fra Micro:Biten som brukes til å kontrollere servoer.
De to neste parene er merket 5V og GND.
5V gir 5 volts positiv spenning mot GND, som er jordkontaktene.

### Steg 1 @unplugged

Monter en hvit, enkel plastarm til en **180-graderservo** som vist på bildet.
Koble **180-graderservoen** til P0 rekken av kontakter som forklart og vist.
Servoene som følger med Superbit har tre ledninger ut, en brun, en rød og en oransje.
Brun er jordledningen, den skal kobles til GND.
Rød er "+"-ledningen som skal kobles til 5V.
Oransje er signalledningen som skal kobles til P1 eller P2.
Plasser kontakten til servoen på pinnene ved P1 slik at oransje ledning treffer P1, rød ledning treffer 5V og brun ledning treffer GND.

![Servokobling](https://raw.githubusercontent.com/Yngel72/Superbit/master/static/Servokobling.jpg)

### Steg 2







```package
bitbot=github:4tronix/BitBot
```

<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
