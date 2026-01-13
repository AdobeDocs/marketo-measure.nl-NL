---
description: '[!DNL Marketo Measure] Workflows voor inkomsten voor dynamiek -  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] Workflows voor inkomsten voor dynamiek'
exl-id: 0e64201a-bc65-4a6d-9192-09c14c810c4a
feature: Microsoft Dynamics
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 0%

---


# [!DNL Marketo Measure] Workflows voor inkomsten voor dynamiek {#marketo-measure-revenue-workflows-for-dynamics}

## Deel 1: Geraamde inkomsten versus werkelijke inkomsten {#part-estimated-revenue-vs-actual-revenue}

[!DNL Marketo Measure] verwijst naar één standaard inkomstenveld uit het vak (Ware inkomsten), maar Dynamics heeft twee standaard inkomstenvelden: Ware inkomsten en geschatte inkomsten. Om pijpleidingsinkomsten beschikbaar te hebben op het Discover Dashboard, zijn een douanegebied en een werkschema nodig om het correcte bedrag van of de Geschatte Inkomsten of het Ware gebied van Inkomsten te vangen afhankelijk van of de Kans Open of Gesloten (Won) is.

Stap 1: Een veld voor een aangepaste opportuniteitshoeveelheid maken in Dynamics

>[!NOTE]
>Alle velden voor inkomsten uit dynamiek hebben een basisveld en een regulier veld. Negeer het basisveld.

Stap 2: Maak een werkstroom die het veld Aangepaste opportuniteitshoeveelheid dat in stap 1 is gemaakt en het veld [!DNL Marketo Measure] Aantal kansen bijwerkt.

>[!NOTE]
>We kunnen niet verwijzen naar het veld [!DNL Marketo Measure] Opportunity Amount (bizible2_bizible_opportunity_amount) in Discover met Dynamics-accounts. De klanten van de dynamiek moeten een gebied van de het bedrag van de douanekans tot stand brengen [!DNL Marketo Measure] om aan in Discover te richten. Zodra volledig, moet de klant een werkschema tot stand brengen dat **zowel** het [!DNL Marketo Measure] Bedrag van de Kans (bizible2_bizible_Opportunity_amount) **als** het gebied van het het bedrag van de douaneopportuniteit bijwerkt. Het veld [!DNL Marketo Measure] Opportunity Amount wordt bij het pakket geleverd, maar er moet een aangepast veld worden gemaakt.

Workflowinstructies voor het bedrag:

**WORKFLOW #1**: Opportunity - werk [!DNL Marketo Measure] het Gebied van het Bedrag van de Kans bij &amp; het Geheime Gebied van de Douane = Geschatte Inkomsten

Deze workflow wordt elke keer dat de geschatte omzet wordt gewijzigd op open kansen uitgevoerd en werkt het veld [!DNL Marketo Measure] Opportunity Amount en uw aangepaste veld bij tot hetzelfde niveau als het veld Geschatte omzet. De workflow moet zo worden ingesteld dat &quot;Real Time&quot; wordt uitgevoerd, maar kan ook &quot;op verzoek&quot; worden uitgevoerd om open Opportunity bij te werken.

Geef het contactpunt van [!DNL Marketo Measure] de naam van het veld voor de aangepaste opportuniteit. Ze werken de [!DNL Marketo Measure] App Opportunity-instellingen bij en voegen de naam van het veld Aangepaste opportuniteitshoeveelheid toe. Hiermee wordt ontdekt welk veld moet worden gebruikt in de rapportage.

**WORKFLOW #2**: Opportunity - werk [!DNL Marketo Measure] het Gebied van de Bedrag van de Kans bij &amp; het Geheime Gebied van de Douane = Werkelijke Inkomsten

Deze workflow wordt gestart wanneer een gebruiker een Opportunity sluit en het veld [!DNL Marketo Measure] Opportunity Amount en uw aangepaste veld met de werkelijke inkomsten die aan het formulier Opportunity Close zijn toegevoegd, bijwerkt voordat Opportunity wordt vergrendeld als gesloten.

## Deel 2: Geschatte sluitdatum vs. werkelijke sluitdatum {#part-estimated-close-date-vs-actual-close-date}

Uit de doos, zijn de gegevens van de pijpleidingsopbrengst niet beschikbaar in het dashboard omdat, door gebrek, de Dynamiek twee gebieden van de voorraaddichte datum heeft: Geschatte Dichte Datum en Dood van de Duur. [!DNL Marketo Measure] kan slechts naar één afsluitdatumveld in het dashboard verwijzen en verwijst naar de werkelijke einddatum.

Als de open kansen geen gegevens op het Werkelijke Dichte gebied van de Datum hebben, zijn er geen gegevens in het dashboard voor open kansen. Toch is een workflow nodig op basis van de opportuniteitsfase om beide datumvelden te ondersteunen.

1. Creeer het Geheime gebied van de Dichte Datum van de Douane op het Voorwerp van de Opportunity ([!DNL Marketo Measure] Aangepaste Dichte Datum).
1. Maak een workflow om het veld [!DNL Marketo Measure] Aangepaste sluitdatum bij te werken met de datum vanaf de geschatte sluitdatum of de werkelijke einddatum, afhankelijk van het feit of de opportuniteit open of gesloten is (de workflow moet worden opgeslagen om in real-time te worden uitgevoerd, maar moet minstens één keer &quot;op aanvraag&quot; worden uitgevoerd om alle geopende opps bij te werken).
1. Test de workflow en bevestig dat deze werkt.
1. De klant moet de API-naam Aangepaste sluitdatum opgeven voor [!DNL Marketo Measure] .
1. [!DNL Marketo Measure] om de toepassingsinstellingen van [!DNL Marketo Measure] zo bij te werken dat deze verwijzen naar het veld [!DNL Marketo Measure] Aangepaste sluitdatum op het dashboard.

   Nadat u de bovenstaande stappen hebt uitgevoerd, voert u de workflows uit om zowel het veld Aangepast opp- bedrag [!DNL Marketo Measure] als het veld [!DNL Marketo Measure] Aangepaste sluitdatum op uw historische kansen bij te werken om de juiste gegevens weer te geven. Dit zal waarschijnlijk gewijzigde op/door gebieden veranderen zodat zou u met uw team moeten controleren om te zien of die om het even welke kwesties aantoont.

De gesloten mogelijkheden bijwerken...

1. Isoleer de mogelijkheden die zijn gesloten sinds de [!DNL Marketo Measure] startdatum tot de workflow actief is. Dit is de groep van historische kansen die u via werkschema moet bijwerken.
1. Alle records exporteren naar Excel.
1. Open Excel-bestand, schakel inhoud in.
1. Gegevens over werkelijke sluitdatum kopiëren naar [!DNL Marketo Measure] Aangepaste sluitdatum.
1. De gegevens van de Opbrengst van het exemplaar de Werkelijke aan [!DNL Marketo Measure] Bedrag van de Aangepaste Kans **en** [!DNL Marketo Measure] Bedrag van de Kans (er zijn twee gebieden.)
1. Bestand opslaan.
1. Bestand importeren. Dynamics herkent dit als een bestand met bestaande records die moeten worden bijgewerkt.
1. Controleren op fouten bij het importeren van bestanden.

>[!NOTE]
>De workflows die in dit document worden beschreven, zijn slechts één manier om de velden bij te werken, zodat [!DNL Marketo Measure] de juiste gegevens kan weergeven in Discover. Als u een andere manier hebt om dezelfde taak uit te voeren, kunt u ervoor kiezen. Wat we van hen nodig hebben, is een soort workflow die het volgende bereikt:
> * Als Opp = Open, werk het gebied van de douanevervaldatum, het gebied van het douaneopp bedrag, en het gebied van het [!DNL Marketo Measure] opp- bedrag aan gelijke Geschatte Dichte Datum en Geraamde Ontvangsten, respectievelijk bij.
> * Als Opp = Gesloten Won, werk het gebied van de de dichte datum van de douane, het gebied van het douaneopp bedrag, en het gebied van het [!DNL Marketo Measure] opp bedrag aan gelijke Duur van de Duur en Ware Opbrengst bij.
