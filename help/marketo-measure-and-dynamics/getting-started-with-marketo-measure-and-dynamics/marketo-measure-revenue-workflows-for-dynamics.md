---
unique-page-id: 37356132
description: "[!DNL Marketo Measure] Workflows voor inkomsten voor dynamiek - [!DNL Marketo Measure] - Productdocumentatie"
title: "[!DNL Marketo Measure] Workflows voor inkomsten voor dynamiek"
exl-id: 0e64201a-bc65-4a6d-9192-09c14c810c4a
source-git-commit: 54337a0a65b79d80ebeae6531f5e92f4f48721a7
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 0%

---

# [!DNL Marketo Measure] Workflows voor inkomsten voor dynamiek {#marketo-measure-revenue-workflows-for-dynamics}

## Deel 1: Geraamde inkomsten versus werkelijke inkomsten {#part-estimated-revenue-vs-actual-revenue}

[!DNL Marketo Measure] wijst naar één standaard inkomstenveld uit de doos (Ware Inkomsten) maar Dynamics heeft twee standaard inkomstenvelden: Werkelijke ontvangsten en geraamde ontvangsten. Om pijpleidingsinkomsten beschikbaar te hebben op het Discover Dashboard, zijn een douanegebied en een werkschema nodig om het correcte bedrag van of de Geschatte Inkomsten of het Ware gebied van Inkomsten te vangen afhankelijk van of de Kans Open of Gesloten (Won) is.

Stap 1: Veld voor aangepaste opportuniteitshoeveelheden maken in Dynamiek

>[!NOTE]
>
>Alle velden voor inkomsten uit dynamiek hebben een basisveld en een regulier veld. Negeer het basisveld.

Stap 2: Maak een workflow die zowel het veld voor de aangepaste opportuniteit dat in stap 1 is gemaakt als het veld voor de aangepaste opportuniteit bijwerkt [!DNL Marketo Measure] Opportunity Amount, veld.

>[!NOTE]
>
>We kunnen niet verwijzen naar de [!DNL Marketo Measure] Opportunity Amount (bizible2_bizible_Opportunity_amount), veld in Discover met Dynamics-accounts. De klanten van de dynamiek moeten een gebied van de douaneopportuniteitshoeveelheid voor creëren [!DNL Marketo Measure] naar Discover te wijzen. Na voltooiing moet de klant een workflow maken die updates biedt **beide** de [!DNL Marketo Measure] Opportuniteitsbedrag (bizible2_bizible_opportunity_amount) **en** het veld Aangepaste opportuniteitshoeveelheid. De [!DNL Marketo Measure] Het veld Opportunity Amount wordt geleverd bij het pakket, maar er moet een aangepast veld worden gemaakt.

Workflowinstructies voor het bedrag:

**WORKFLOW #1**: Opportunity - Bijwerken [!DNL Marketo Measure] Veld en aangepast veld opportuniteitsbedrag = geschatte omzet

Deze workflow wordt elke keer dat de geschatte inkomsten veranderen, op open kansen uitgevoerd en werkt de [!DNL Marketo Measure] Het veld Opportunity Amount en uw aangepaste veld zijn gelijk aan het veld Geschatte inkomsten. De workflow moet zo worden ingesteld dat &quot;Real Time&quot; wordt uitgevoerd, maar kan ook &quot;op verzoek&quot; worden uitgevoerd om open Opportunity bij te werken.

Geef uw [!DNL Marketo Measure] contactpunt met de naam van het veld voor aangepaste opportuniteiten. Ze werken de [!DNL Marketo Measure] Instellingen voor toepassingsopportuniteit om de naam van het veld voor aangepaste opportuniteiten op te nemen. Hiermee wordt ontdekt welk veld moet worden gebruikt voor rapportage.

**WORKFLOW #2**: Opportunity - Bijwerken [!DNL Marketo Measure] Veld en aangepast veld opportuniteitsbedrag = werkelijke inkomsten

Deze workflow wordt in real-time uitgevoerd. De gebeurtenis wordt gestart wanneer een gebruiker een opportunity sluit en de gebeurtenis [!DNL Marketo Measure] Het gebied van het Bedrag van de kans en uw douanegebied met de Ware Ontvangsten die aan de Sluiten vorm van de Kans worden toegevoegd alvorens de Kans als gesloten sluit.

## Deel 2: Geschatte sluitdatum versus werkelijke sluitdatum {#part-estimated-close-date-vs-actual-close-date}

Uit de doos, zullen de gegevens van de pijpleidingsopbrengst niet in het dashboard beschikbaar zijn omdat, door gebrek, de Dynamiek twee gebieden van de voorraaddichte datum heeft: Geschatte sluitdatum en werkelijke sluitdatum. [!DNL Marketo Measure] kan slechts naar één afsluitdatumveld in het dashboard verwijzen en we wijzen momenteel naar de werkelijke einddatum.

Als de open kansen geen gegevens op het Werkelijke Dichte gebied van de Datum hebben, zien wij geen gegevens in het dashboard voor open kansen. Toch is een workflow nodig op basis van de opportuniteitsfase om beide datumvelden te ondersteunen.

1. Het veld Aangepaste sluitdatum maken op het opportuntobject (dat wil zeggen: [!DNL Marketo Measure] Aangepaste sluitdatum).
1. Een workflow maken om de [!DNL Marketo Measure] Het veld Aangepaste einddatum met de datum vanaf de geschatte einddatum of de werkelijke einddatum, afhankelijk van het feit of de opportuniteit open of gesloten is (de workflow moet worden opgeslagen om in real-time te worden uitgevoerd, maar deze moet minstens één keer &quot;op aanvraag&quot; worden uitgevoerd om alle huidige open opps bij te werken).
1. Test de workflow en bevestig dat deze werkt.
1. Klant geeft de API-naam Aangepaste sluitingsdatum door aan [!DNL Marketo Measure].
1. [!DNL Marketo Measure] om de [!DNL Marketo Measure] app-instellingen om naar de [!DNL Marketo Measure] Het veld Aangepaste datum sluiten in het dashboard.

   Nadat de bovenstaande stappen zijn voltooid, moeten we workflows uitvoeren om beide aangepaste [!DNL Marketo Measure] Het veld Hoeveelheid opp en het veld [!DNL Marketo Measure] Het veld Aangepaste datum sluiten op uw historische kansen om de juiste gegevens weer te geven. Dit zal waarschijnlijk gewijzigde op/door gebieden veranderen zodat zult u met uw team willen controleren om te zien of behandelt dat om het even welke kwesties.

De gesloten mogelijkheden bijwerken...

1. Mogelijkheden isoleren die zijn gesloten sinds uw [!DNL Marketo Measure] opstartdatum tot de workflow actief is. Dit is de groep van historische kansen die u via werkschema zult moeten bijwerken.
1. Alle records exporteren naar Excel.
1. Open Excel-bestand, schakel inhoud in.
1. Werkelijke sluitdatumgegevens kopiëren naar [!DNL Marketo Measure] Aangepaste sluitdatum.
1. Gegevens van werkelijke inkomsten kopiëren naar [!DNL Marketo Measure] Aangepast opportuniteitsbedrag **en** [!DNL Marketo Measure] Mate van opportunity (er zijn twee gebieden.)
1. Bestand opslaan.
1. Bestand importeren. Dynamics herkent dit als een bestand met bestaande records die moeten worden bijgewerkt.
1. Controleren op fouten bij het importeren van bestanden.

>[!NOTE]
>
>De workflows die in dit document worden beschreven, zijn slechts één manier om de velden bij te werken, zodat [!DNL Marketo Measure] kan de juiste gegevens weergeven in Discover. Als u een andere manier hebt om dezelfde taak uit te voeren, kunt u ervoor kiezen. Wat we van hen nodig hebben, is een of meer workflows die het volgende bereiken:
>
> * Als Opp = Open, werk het gebied van de de dichte douanedatum, het gebied van het aangepaste opp bedrag bij, en [!DNL Marketo Measure] opp-waardeveld gelijk aan respectievelijk geschatte einddatum en geschatte inkomsten.
> * Als Opp = Gesloten Won, werk het gebied van de dichte douanedatum, het gebied van het aangepaste opp bedrag bij, en [!DNL Marketo Measure] opp-waardeveld gelijk aan respectievelijk de werkelijke einddatum en de werkelijke inkomsten.

