### @activities true

# Superbit - Kodeøkt 3: Kjør en Bitbot
## Introduksjon til hvordan du kjører Bitboten
### Introduksjon @unplugged

Lær hvordan du får BitBoten til å kjøre

### Steg 1

Aller først må du fortelle programmet hvilken versjon av BitBot du har.
Hent en ``||Bitbot.velg BitBot modell||``-blokk fra ``||Bitbot.BitBot/BitBot modell||`` menyen og dra den inn i gapet på ``||Basic.on start||``-blokka.
Sjekk hvilken BitBot du har og velg riktig modell ved å klikke der det står ``||Bitbot.Classic||``.

```blocks
bitbot.select_model(BBModel.XL)
```

### Steg 2

Nå skal du få bilen til å kjøre fremover.
Hent en ``||Bitbot.kjør framover med fart 60 % i 400 ms||``-blokk fra ``||Bitbot.Bitbot/Kjøring||`` og plasser den under ``||Bitbot.velg BitBot modell||``-blokken.

```blocks
bitbot.select_model(BBModel.XL)
// @highlight
bitbot.goms(BBDirection.Forward, 60, 400)
```

### Steg 3

Test programmet på BitBoten og følg med på hvor langt og fort den kjører.
Du kan endre på farten ved å endre tallet der det står ``||Bitbot.fart||`` 60 ``||Bitbot.%||`` og hvor lenge den kjører ved å endre tallet der det står ``||Bitbot.i||`` 400 ``||Bitbot.ms||``.
Test litt forskjellige tider og hastigheter for å få en følelse av hvordan innstillingene påvirker Bitboten.
(Blokkene i hintene i denne gjennomgangen gir ingen fasit på hvordan man treffer på 1 meter)

```blocks
bitbot.select_model(BBModel.XL)
// @highlight
bitbot.goms(BBDirection.Forward, 100, 1000)
```

### Steg 4

Mål opp 1 meter på gulvet og prøv å få BitBoten til å kjøre akkurat 1 meter før den stopper.
Endre tallene i kodeblokkene for å kontrollere kjørelengden.
Tips: Du får større kontroll ved lavere fart.
Endre kun på ett av tallene av gangen.
Da blir det mye enklere å vurdere hvordan endringen du gjorde påvirket kjørelengden.

```blocks
bitbot.select_model(BBModel.XL)
// @highlight
bitbot.goms(BBDirection.Forward, 60, 800)
```

### Steg 5

Nå skal du få Bitboten til å kjøre fram, snu seg rundt og kjøre tilbake til start.
For å snu roboten trenger du blokken ``||bitbot.snu til venstre med fart 60 % i 400 ms||`` fra ``||bitbot.Bitbot||``-menyen.
Legg den under ``||Bitbot.kjør framover med fart ?? % i ?? ms||``-blokken i koden din.
Du kan velge om du vil snu roboten mot venstre eller høyre ved å klikke på den lille pilen til høyre for ``||bitbot.venstre||`` og velge retning.
Rekkefølgen på koden er viktig her. Programmet kjører instruksjonene i samme rekkefølge som blokkene ligger i ``||basic.ved start||``.

```blocks
bitbot.select_model(BBModel.XL)
bitbot.goms(BBDirection.Forward, 60, 400)
// @highlight
bitbot.rotatems(BBRobotDirection.Left, 60, 400)
```

### Steg 6

Du har allerede forhåpentligvis koden du trenger for å kjøre 1 meter.
Kopier blokken ``||Bitbot.kjør framover med fart ?? % i ?? ms||``.
La instillingene i denne blokken være som de er, dersom du har klart å få roboten til å kjøre riktig lengde.
Her må det prøving og feiling til, så her må du bare laste ned programmet og teste det med Bitboten til du treffer.
Tips: For å spare tid kan du legge blokkene som kjører Bitboten 1 meter rett fram utenfor ``||basic.ved start||``-blokken og kun teste for 180 graders sving helt til du treffer.

### Avrunding @unplugged

Nå vet du hvordan du får Bitboten til å kjøre.
Da er du klar for å lære deg hvordan du bruker sensorene på Bitboten.

```blocks
bitbot.select_model(BBModel.XL)
bitbot.goms(BBDirection.Forward, 60, 400)
bitbot.rotatems(BBRobotDirection.Left, 60, 400)
// @highlight
bitbot.goms(BBDirection.Forward, 60, 400)
```


```package
bitbot=github:4tronix/BitBot
```

<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>



