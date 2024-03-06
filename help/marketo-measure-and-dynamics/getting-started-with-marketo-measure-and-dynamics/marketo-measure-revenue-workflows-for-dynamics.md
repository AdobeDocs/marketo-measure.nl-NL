---
unique-page-id: 37356132
description: "[!DNL Marketo Measure] Workflows voor inkomsten voor dynamiek - [!DNL Marketo Measure]"
title: "[!DNL Marketo Measure] Workflows voor inkomsten voor dynamiek"
exl-id: 0e64201a-bc65-4a6d-9192-09c14c810c4a
feature: Microsoft Dynamics
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 0%

---

# [!DNL Marketo Measure] Workflows voor inkomsten voor dynamiek {#marketo-measure-revenue-workflows-for-dynamics}

## Deel 1: Geraamde inkomsten versus werkelijke inkomsten {#part-estimated-revenue-vs-actual-revenue}

[!DNL Marketo Measure] verwijst naar één standaard inkomstenveld uit het vak (Ware inkomsten), maar Dynamics heeft twee standaard inkomstenvelden: Ware inkomsten en geschatte inkomsten. Om pijpleidingsinkomsten beschikbaar te hebben op het Discover Dashboard, zijn een douanegebied en een werkschema nodig om het correcte bedrag van of de Geschatte Inkomsten of het Ware gebied van Inkomsten te vangen afhankelijk van of de Kans Open of Gesloten (Won) is.

Stap 1: Een veld voor een aangepaste opportuniteitshoeveelheid maken in Dynamics

>[!NOTE]
>
>Alle velden voor inkomsten uit dynamiek hebben een basisveld en een regulier veld. Negeer het basisveld.

Stap 2: Creeer een werkschema dat zowel het gebied van de douaneopportuniteit bijwerkt dat in stap 1 wordt gecreeerd als [!DNL Marketo Measure] Opportunity Amount, veld.

>[!NOTE]
>
>We kunnen niet verwijzen naar de [!DNL Marketo Measure] Opportunity Amount (bizible2_bizible_opportunity_amount), veld in Discover met Dynamics accounts. De klanten van de dynamiek moeten een gebied van de douaneopportuniteitshoeveelheid voor creëren [!DNL Marketo Measure] naar in Discover te wijzen. Zodra dit is voltooid, moet de klant een workflow maken die wordt bijgewerkt **beide** de [!DNL Marketo Measure] Opportuniteitsbedrag (bizible2_bizible_opportunity_amount) **en** het veld Aangepaste opportuniteitshoeveelheid. De [!DNL Marketo Measure] Het veld Opportunity Amount wordt geleverd bij het pakket, maar er moet een aangepast veld worden gemaakt.

Workflowinstructies voor het bedrag:

**WORKFLOW #1**: Opportunity - Bijwerken [!DNL Marketo Measure] Veld en aangepast veld opportuniteitsbedrag = geschatte omzet

Deze workflow wordt elke keer dat de geschatte inkomsten veranderen en de [!DNL Marketo Measure] Het veld Opportunity Amount en uw aangepaste veld zijn gelijk aan het veld Geschatte inkomsten. De workflow moet zo worden ingesteld dat &quot;Real Time&quot; wordt uitgevoerd, maar kan ook &quot;op verzoek&quot; worden uitgevoerd om open Opportunity bij te werken.

Geef uw [!DNL Marketo Measure] contactpunt met de naam van het veld voor aangepaste opportuniteiten. Ze werken de [!DNL Marketo Measure] Instellingen voor toepassingsopportuniteit om de naam van het veld voor het aangepaste opportuniteitsbedrag op te nemen. Hiermee wordt ontdekt welk veld moet worden gebruikt in de rapportage.

**WORKFLOW #2**: Opportunity - Bijwerken [!DNL Marketo Measure] Veld en aangepast veld opportuniteitsbedrag = werkelijke inkomsten

Deze workflow wordt gestart wanneer een gebruiker een opportunity sluit en de [!DNL Marketo Measure] Het gebied van het Bedrag van de kans en uw douanegebied met de Ware Ontvangsten die aan de Sluiten vorm van de Kans worden toegevoegd alvorens de Kans als gesloten sluit.

## Deel 2: Geschatte sluitdatum vs. werkelijke sluitdatum {#part-estimated-close-date-vs-actual-close-date}

Uit de doos, zijn de gegevens van de pijpleidingsopbrengst niet beschikbaar in het dashboard omdat, door gebrek, de Dynamiek twee gebieden van de voorraaddichte datum heeft: Geschatte Dichte Datum en Dood van de Duur. [!DNL Marketo Measure] kan slechts naar één afsluitdatumveld in het dashboard verwijzen en verwijst naar de werkelijke einddatum.

Als de open kansen geen gegevens op het Werkelijke Dichte gebied van de Datum hebben, zijn er geen gegevens in het dashboard voor open kansen. Toch is een workflow nodig op basis van de opportuniteitsfase om beide datumvelden te ondersteunen.

1. Aangepast vervaldatumveld maken op het Opportunity-object ([!DNL Marketo Measure] Aangepaste sluitdatum).
1. Een workflow maken om de [!DNL Marketo Measure] Het veld Aangepaste einddatum met de datum vanaf de geschatte einddatum of de werkelijke einddatum, afhankelijk van het feit of de opportuniteit open of gesloten is (de workflow moet worden opgeslagen zodat deze in real-time kan worden uitgevoerd, maar u moet minstens één keer op aanvraag worden uitgevoerd om alle geopende opps bij te werken).
1. Test de workflow en bevestig dat deze werkt.
1. Klant geeft de API-naam Aangepaste sluitingsdatum door aan [!DNL Marketo Measure].
1. [!DNL Marketo Measure] om de [!DNL Marketo Measure] app-instellingen om naar de [!DNL Marketo Measure] Het veld Aangepaste datum sluiten in het dashboard.

   Als u de bovenstaande stappen hebt uitgevoerd, voert u de workflows uit om zowel de aangepaste versie als de aangepaste [!DNL Marketo Measure] Het veld Hoeveelheid opp en het veld [!DNL Marketo Measure] Het veld Aangepaste datum sluiten op uw historische kansen om de juiste gegevens weer te geven. Dit zal waarschijnlijk gewijzigde op/door gebieden veranderen zodat zou u met uw team moeten controleren om te zien of die om het even welke kwesties aantoont.

De gesloten mogelijkheden bijwerken...

1. Mogelijkheden isoleren die zijn gesloten sinds uw [!DNL Marketo Measure] opstartdatum tot de workflow actief is. Dit is de groep van historische kansen die u via werkschema moet bijwerken.
1. Alle records exporteren naar Excel.
1. Open Excel-bestand, schakel inhoud in.
1. Werkelijke sluitdatumgegevens kopiëren naar [!DNL Marketo Measure] Aangepaste sluitdatum.
1. Gegevens van werkelijke inkomsten kopiëren naar [!DNL Marketo Measure] Aangepast opportuniteitsbedrag **en** [!DNL Marketo Measure] Mate van opportunity (er zijn twee gebieden.)
1. Bestand opslaan.
1. Bestand importeren. Dynamics herkent dit als een bestand met bestaande records die moeten worden bijgewerkt.
1. Controleren op fouten bij het importeren van bestanden.

>[!NOTE]
>
>De workflows die in dit document worden beschreven, zijn slechts één manier om de velden bij te werken, zodat [!DNL Marketo Measure] kan de juiste gegevens weergeven in Discover. Als u een andere manier hebt om dezelfde taak uit te voeren, kunt u ervoor kiezen. Wat we van hen nodig hebben, is een soort workflow die het volgende bereikt:
>
> * Als Opp = Open, werk het gebied van de de dichte douanedatum, het gebied van het aangepaste opp bedrag bij, en [!DNL Marketo Measure] opp-waardeveld gelijk aan respectievelijk geschatte einddatum en geschatte inkomsten.
> * Als Opp = Gesloten Won, werk het gebied van de dichte douanedatum, het gebied van het aangepaste opp bedrag bij, en [!DNL Marketo Measure] opp-waardeveld gelijk aan respectievelijk de werkelijke einddatum en de werkelijke inkomsten.
