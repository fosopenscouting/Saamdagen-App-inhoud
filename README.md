# Inhoud Saamdagen app - Hoe te gebruiken

## Algemeen

-   Benamingen van bestanden maken niet uit. Geef bestanden een duidelijke naam.
-   Alle bestanden in Homepage en Programma worden opgehaald door de app. Plaats hierin geen sjablonen, testbestanden,..
-   Zorg dat de info tussen `---` steeds goed ingevuld is. Kopieer een reeds bestaand item om zeker te zijn dat alles juist is.

## Aanpassingen maken

Hoe zorg je er nu voor dat de aanpassingen correct worden opgeslagen?
[Lees hier de handleiding](./git.md)

## Overzicht mappen

| Mapnaam      | Doel                                                                       |
| :----------- | :------------------------------------------------------------------------- |
| `Staging`    | Testen van de nieuwe content. Enkel zichtbaar in de test-versie van de app |
| `Production` | Deze bestanden zijn zichtbaar voor iedereen die de app gebruikt            |
| `sjablonen`  | Enkele voorbeeldsjablonen om te kopiëren                                   |

### Submappen

Daarnaast hebben `Staging` en `Production` nog enkele submappen voor de content die getoont wordt in de app.

| Mapnaam         | Doel                                     | Link                            |
| :-------------- | :--------------------------------------- | :------------------------------ |
| `Programma`     | Alles van het programma                  | [Programma](#programma)         |
| `Homepage`      | Content op het startschermp van de app   | [Homepage](#homepage)           |
| `Faq`           | Faq-items                                | [FAQ](#faq)                     |
| `Volunteer`     | Content enkel zichtbaar voor medewerkers | [Volunteer](#volunteer)         |
| `Notifications` | Voorgeprogrammeerde notificaties         | [Notifications](#notifications) |

## Opbouw content metadata

Hieronder kan je terugvinden hoe de metadata van de bestanden zijn opgebouwd.

### Programma

-   titel (**verplicht**): vrije tekst. Wordt letterlijk overgenomen door de app
-   dag (**verplicht**): keuze tussen `Vrijdag`, `Zaterdag` of `Zondag`. Andere waarden zullen genegeerd worden door de app.
-   uren (**verplicht**): vrije tekst. Wordt letterlijk overgenomen door de app ( ⚠️ **VEROUDERD**, zie [Tijden](#tijden) )
-   tijd (**verplicht**):
    -   start (**verplicht**): Tekst in formaat `'uu:mm'`. Zorg dat de `'` er staan!
    -   eind (**optioneel**): Tekst in formaat `'uu:mm'`. Zorg dat de `'` er staan! OF `...` als de einddtijd niet geweten is
-   volgorde (**verplicht**): een cijfer. Wordt gebruikt om items te ordenen in de app.
-   locatie (**verplicht**): is gelinkt aan het grondplan. Keuze uit:
    -   Podium
    -   Kampvuur
    -   Infopunt
    -   Fuiftent
    -   Eettent
    -   Camping
    -   Markt

Alle inhoud onder deze metadata wordt integraal getoond door de app.

### Homepage

-   titel (**verplicht**): vrije tekst. Wordt letterlijk overgenomen door de app
-   volgorde (**verplicht**): een cijfer. Wordt gebruikt om items te ordenen in de app.
-   link (**optioneel**): een link, zie [Links](#links)

### FAQ

-   titel (**verplicht**): vrije tekst. Wordt letterlijk overgenomen door de app
-   volgorde (**verplicht**): een cijfer. Wordt gebruikt om items te ordenen in de app.
-   icoon (**optioneel**): de naam van een icoon. Kies deze vanaf https://pictogrammers.com/library/mdi/

### Volunteer

> Zelfde als [FAQ](#faq)

### Notifications

-   titel (**verplicht**): vrije tekst. Maak dit niet te lang
-   subtitle (**optioneel**): vrije tekst. Maak dit niet te lang. Gebruik dit liever ook niet.
-   time (**verplicht**): (Vergeet de aanhalingstekens niet!)
    -   date (**verplicht**): datum in formaat `'dd/mm/yyyy'`
    -   hour (**verplicht**): uur in formaat `'hh:mm'` ( ⚠️ De app zal proberen om de melding op dit tijdstip te sturen, maar reken zeker een marge van 15min )

## Extra informatie

## Tijden

Er is recent een wijziging doorgevoerd in hoe tijden worden doorgegeven aan de app.
Vroeger gebeurde dit via `uren`, nu liever met het nieuwe `tijd`. Hieronder kan je nog eens de verschillen tussen beide terugvinden.

### uren

Hier moest je gewoon een stuk tekst opgeven met de uren, bv: `uren: '10:00 t.e.m. 12:00'`.
Als je deze toch nog wilt gebruiken, moet je zorgen dat je aan onderstaande voorwaarden voldoet:

-   Altijd één stuk tekst omgeven door aanhalingstekens (`'`)
-   Uren altijd in formaat `uu:mm`, vooral de `:` is belangrijk
-   Als er een einduur is altijd `t.e.m.` gebruiken, zorg dat dit ook juist geschreven is
-   Einduur mag ook `...` zijn

### tijd

Deze optie bestaat uit 2 onderopties, `start` en `eind`.
`start` moet altijd zijn opgegeven, en moet ook in het formaat `'uu:mm'` zijn. Vergeet dus niet de aanhalingstekens!
`eind` is optioneel. Als je het toch opgeeft, moet het uur in hetzelfde formaat als hierboven zijn, of als er geen specifiek einduur is mag het ook `...` zijn

#### Voorbeelden

<details>
<summary>Compleet</summary>

```markdown
tijd:
start: '10:00'
eind: '12:00'
```

</details>

<details>
<summary>Geen einduur</summary>

```markdown
tijd:
start: '10:00'
```

</details>

<details>
<summary>Onbekend einduur</summary>

```markdown
tijd:
start: '10:00'
eind: '...'
```

</details>

### Links

Op sommige plaatsen kunnen links gebruikt worden.
Als dit in de metadata is, dan zijn er 2 opties: volledige links en lokale links.

-   Volledige links: naar websites (`https://`), emailadressen (`mailto:`), ...
-   Lokale links: links in de app zelf, hieronder een lijst met beschikbare links

Een volledige link heeft het formaat `[tekst die getoond word](url)`, of gewoon de url op zich.

### Beschikbare lokale links

| Link                 |                         |
| :------------------- | :---------------------- |
| `/`                  | Homepagina              |
| `/map`               | Het grondplan           |
| `/faq`               | Faq                     |
| `/schedule/friday`   | Programma vrijdag       |
| `/schedule/saturday` | Programma zaterdag      |
| `/schedule/sunday`   | Programma zondag        |
| `/more`              | Meer-scherm             |
| `/more/about`        | Info over app           |
| `/more/licenses`     | Licenties van de app    |
| `/more/profile`      | `Mijn Saamdagen`-scherm |
| `/more/settings`     | Instellingen van de app |
| `/more/volunteer`    | Info voor vrijwilligers |

### Foto's

> [!WARNING]
> Gebruik dit enkel indien nodig! Dit verhoogt de laadtijd van de app en kan ervoor zorgen dat deze minder goed werkt!

Er is ook de mogelijkheid om foto's te tonen in de app. Dit kan op 2 manieren:

-   Online afbeeldingen: De app zal deze proberen downloaden de eerste keer dat de content laad, zodat de foto ook offline zichtbaar is
-   Lokale afbeeldingen: Afbeeldingen die al standaard in de app zitten

#### Hoe gebruik ik dit?

Een afbeelding in markdown is altijd in het formaat `![alt tekst](url)`. Zorg dat de afbeelding niet op de eerste lijn van de content staat, anders werkt deze niet.

Voor online afbeeldingen moet je de url van de afbeelding gebruiken.

Voor lokale afbeeldingen begint de url altijd met `@` en dan gevolgd door een naam. Momenteel is er maar 1 beschikbaar, `@saamregels`.

## Markdown schrijven

Markdown heeft verschillende mogelijkheden om tekst op te maken, hieronder enkele.

```markdown
**vet**

_schuin_

**_vet en schuin_**

[link](link)

![afbeelding](https://afbeelding.com/afbeelding.png)

| kol1 | kol2 |
| ---- | ---- |
| item | item |

- lijst1
- lijst2

1. nummer 1
2. nummer 2

# titel

## ondertitel

### subtitel 2

#### subtitel 3

##### subtitel 4

###### subtitel 5
```

## Voorbeelden

<details>
<summary>Online afbeelding</summary>

```markdown
---
... metadata
---

Hier is een afbeelding
![dit is een beschrijvende tekst](https://li.nk/vande/afbeelding.png)
```

</details>
<details>
<summary>Lokale afbeelding</summary>

```markdown
---
... metadata
---

Hier is een afbeelding van de saamregels
![de saamregels](@saamregels)
```

</details>

<details>
<summary>Homepage-item</summary>

```markdown
---
titel: Deze app
link: https://saamdagen.be
volgorde: 1
---

Dit is een tekst!
```

</details>
