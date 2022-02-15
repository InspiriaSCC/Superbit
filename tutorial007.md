### @activities true

# Superbit del 7: Bitbot
## Introduksjon
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

```blocks
bitbot.select_model(BBModel.XL)
// @highlight
bitbot.goms(BBDirection.Forward, 100, 800)
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
bitbot.goms(BBDirection.Forward, 50, 800)
```


```package
bitbot=github:4tronix/BitBot
```

<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>



