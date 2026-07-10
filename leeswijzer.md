# Bijlage – Leeswijzer UML-klassendiagrammen

## Inleiding

Een UML-klassendiagram is een visuele representatie van objecttypen, hun eigenschappen en hun onderlinge relaties. UML-klassendiagrammen worden gebruikt om de structuur van een informatiemodel inzichtelijk te maken.

Het informatiemodel in dit document is gemodelleerd als een UML-klassendiagram conform het **Metamodel voor Informatiemodellering (MIM)**. Het model beschrijft de betekenis, structuur en samenhang van informatie, zonder daarbij technische implementatiekeuzes vast te leggen.

Deze bijlage geeft een korte toelichting op de belangrijkste UML-constructies die in het model worden gebruikt.

## Objecttypen

Elk vak in een UML-klassendiagram representeert een **objecttype**.

Een objecttype beschrijft een verzameling objecten die dezelfde kenmerken en betekenis hebben. Voorbeelden zijn bijvoorbeeld *Treinbeweging*, *Gebeurtenis* of *Materieelopstelling*.

**Concreet objecttype**

Een concreet objecttype beschrijft objecten die daadwerkelijk in de praktijk voorkomen en waarvan instanties kunnen worden vastgelegd.

Voorbeelden:

- Treinbeweging

- Gebeurtenis

- Materieelopstelling

**Abstract objecttype**

Een abstract objecttype dient als algemene beschrijving voor één of meer gespecialiseerde objecttypen. Van een abstract objecttype worden geen directe instanties vastgelegd.

Abstracte objecttypen worden meestal cursief weergegeven en zijn vaak voorzien van de aanduiding *abstract*.

## Attributen

Attributen beschrijven de eigenschappen van een objecttype.

Voorbeelden van attributen zijn:

- identificatie

- naam

- datum

- type

Elk attribuut heeft een datatype dat aangeeft welke waarden zijn toegestaan.

Voorbeelden van veelgebruikte datatypen zijn:

- CharacterString (tekst)

- Integer (geheel getal)

- Boolean (waar/onwaar)

- Date (datum)

- DateTime (datum en tijd)

## Gegevensgroep

Een gegevensgroep is een logisch samenhangende verzameling attributen.

Gegevensgroepen worden gebruikt wanneer meerdere attributen inhoudelijk bij elkaar horen en gezamenlijk kunnen worden hergebruikt.

Binnen UML worden gegevensgroepen meestal aangeduid met een stereotype zoals \<\<Gegevensgroep\>\>

## Waardenlijsten

Waardenlijsten beperken de toegestane waarden van een attribuut.

### Codelijst

Een codelijst bevat waarden die buiten het informatiemodel worden beheerd.

Nieuwe waarden kunnen worden toegevoegd zonder dat het informatiemodel zelf hoeft te worden aangepast.

### Enumeratie

Een enumeratie bevat een vaste lijst van toegestane waarden die onderdeel vormt van het informatiemodel.

Wijzigingen in een enumeratie vereisen een wijziging van het model.

### Referentielijst

Een referentielijst bevat een beheerde verzameling waarden die als zelfstandig object binnen het informatiemodel worden gemodelleerd.

In tegenstelling tot een enumeratie of codelijst kunnen waarden uit een referentielijst aanvullende eigenschappen bevatten en relaties hebben met andere objecttypen. Hierdoor kan extra informatie over de waarden worden vastgelegd.

Referentielijsten worden toegepast wanneer de waarden zelf betekenisvolle objecten binnen het domein vertegenwoordigen en zelfstandig beheerd moeten kunnen worden.

Voorbeelden zijn lijsten met operationele locaties, organisaties, spoorvoertuigtypen of andere domeinobjecten die naast een code of naam ook aanvullende kenmerken bevatten.

### Verschil tussen Enumeratie, Codelijst en Referentielijst

| Type | Beheer | Uitbreidbaar | Extra attributen mogelijk |
|----|----|----|----|
| Enumeratie | In het model | Nee | Nee |
| Codelijst | Buiten het model | Ja | Beperkt |
| Referentielijst | Als object in het model | Ja | Ja |

Een referentielijst wordt in een UML-diagram veelal gemodelleerd als een zelfstandig objecttype waarop andere objecttypen kunnen refereren.

## Relaties

Relaties beschrijven de samenhang tussen objecttypen.

### Associaties

Een associatie beschrijft een relatie tussen twee objecttypen.

Associaties worden weergegeven als een lijn tussen objecttypen.

Een associatie kan worden voorzien van:

- een relatiebenaming;

- een relatierol;

- cardinaliteiten.

### Relatierol

Een relatierol beschrijft de betekenis van een relatie vanuit een bepaald objecttype.

Voorbeeld: Treinbeweging bestaatUit Gebeurtenis

Hier beschrijft *bestaatUit* de rol van de relatie.

### Generalisatie

Generalisatie beschrijft een *is-een-relatie* tussen objecttypen.

Een gespecialiseerd objecttype erft hierbij kenmerken van een meer algemeen objecttype.

Voorbeeld: Werkactiviteit is een Activiteit

Generalisaties worden weergegeven met een lijn en een holle driehoek.

## Cardinaliteit

Cardinaliteit geeft aan hoeveel voorkomens van een objecttype in een relatie zijn toegestaan of verplicht.

Veel voorkomende cardinaliteiten zijn:

| **Cardinaliteit** | **Betekenis**    |
|-------------------|------------------|
| 1                 | precies één      |
| 0..1              | nul of één       |
| 1..\*             | één of meer      |
| 0..\*             | nul of meer      |
| \*                | onbepaald aantal |

Voorbeelden:

- Een Treinbeweging heeft één of meer Gebeurtenissen.

- Een Gebeurtenis kan nul of meer Activiteiten begrenzen.

## Keuze (Choice)

Soms kan een attribuut of relatie uit meerdere alternatieven bestaan.

Dit wordt in UML aangeduid met een *keuze*.

### Keuze in attributen

Een attribuut kan waarden aannemen uit meerdere mogelijke datatypen.

### Keuze in relaties

Een objecttype kan gerelateerd zijn aan één van meerdere mogelijke doelobjecttypen.

## Stereotypen

MIM gebruikt stereotypen om de betekenis van modelelementen verder te specificeren.

Voorbeelden zijn:

\<\<Objecttype\>\>

\<\<Attribuutsoort\>\>

\<\<Relatiesoort\>\>

\<\<Gegevensgroep\>\>

\<\<Codelijst\>\>

\<\<Enumeratie\>\>

Stereotypen maken zichtbaar welke rol een modelelement binnen het informatiemodel vervult.

## Kleurgebruik

In sommige UML-diagrammen wordt kleur gebruikt om objecttypen van elkaar te onderscheiden.

Kleurgebruik dient uitsluitend ter ondersteuning van de leesbaarheid en heeft geen formele betekenis binnen UML of MIM, tenzij expliciet anders is aangegeven.

## Samenvatting

Bij het lezen van een UML-klassendiagram zijn de volgende uitgangspunten van belang:

- Een objecttype beschrijft een betekenisvol concept uit het domein.

- Attributen beschrijven eigenschappen van een objecttype.

- Relaties leggen samenhang vast tussen objecttypen.

- Generalisaties beschrijven specialisaties van objecttypen.

- Cardinaliteiten geven aan hoeveel relaties mogelijk of verplicht zijn.

- Codelijsten en enumeraties beperken toegestane waarden.

- Het model beschrijft de betekenis en structuur van informatie, niet de technische implementatie.

Voor meer informatie wordt verwezen naar het **Metamodel voor Informatiemodellering (MIM)**.
