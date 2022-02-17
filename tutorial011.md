### @activities true

# Superbit del 11: Radiostyring del 2: Mottageren
## Bruk radiosignaler til å fjernstyre en Bitbot
### Introduksjon @unplugged

Forrige gjennomgang tok for seg hvordan man lager en radiosender som kan styre en Bitbot.
Nå skal du lage mottageren som skal stå i Bitboten og ta imot signaler fra senderen.
Legg radiosenderen på et trygt sted eller merk den med litt tape så den ikke blir brukt til noe annet i mellomtiden.
Til mottageren trenger du en ny Micro:Bit.
Så fort du har en klar kan du gå videre.

### Steg 1

Siden radiostyring krever at Micro:biten bruker radiosignaler, må du begynne med å aktivere radioen og velge en kanal.
Det gør du med blokken ``||radio.radio sett gruppe||`` som du finner i ``||radio.Radio||``-menyen.
Hent en ``||radio.radio sett gruppe||`` og plasser den i ``||basic.ved start||``-blokken.

```blocks
radio.setGroup(1)
```

### Radiogrupper @unplugged
Det er viktig at mottagerens radio er satt til samme gruppe som senderens.
I gjennomgangen for senderen ble gruppe 1 brukt som eksempel, siden det er standardgruppen når du henter blokken i menyen.
Av den grunn brukes 1 som eksempel i denne gjennomgangen også.
Radiogrupper fungerer som radiokanaler.
Dersom flere roboter skal kjøres i samme rom, må alle sender/mottakerpar settes til forskjellige grupper.
Tallet i radiogruppeblokken kan være alle tall fra og med 0 til og med 255, så man kan i teorien kjøre 256 roboter i samme rom samtidig.
Det bør med andre ord være nok grupper å velge mellom til at en hel skoleklasse kan bygge hver sin fjernstyrte robot og kjøre dem i samme rom uten problemer.

### Steg 2

Mottagerprogrammet må kjøre i en ``||basic.gjenta for alltid||``-blokk.
Om du ikke har en i arbeidsområdet allerede må du hente en fra ``||basic.Basis||``-menyen.
Legg en ``||logic.hvis sann så ellers||``-blokk fra ``||logic.Logikk||``-menyen inn i ``||basic.gjenta for alltid||``-blokken.

```blocks
basic.forever(function () {
    // @highlight
    if (true) {
    	
    } else {
    	
    }
})
```

### Steg 3

