---
description: '''[!DNL Marketo Measure] Ultieme implementatiehandleiding - [!DNL Marketo Measure] - Productdocumentatie"'
title: '[!DNL Marketo Measure] Ultieme implementatiegids'
hide: true
hidefromtoc: true
feature: Integration, Tracking, Attribution
source-git-commit: fad900c97f25e7d19692fb2b4403b439e479caa1
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 0%

---

# [!DNL Marketo Measure] Ultieme implementatiegids {#marketo-measure-ultimate-implementation-guide}

INTRO SENTENCE

Belangrijkste verschillen bij gebruik van Ultimate via standaardtiers {#main-differences-when-using-ultimate-over-standard-tiers}

B2B-gegevens importeren via AEP: Van markers wordt verwacht dat ze hun B2B-gegevens (bijvoorbeeld account, opportunity, Contact, lead, campagne, campagnerelid, activiteit) via AEP doorgeven. Maak gebruik van vrijwel elke gegevensbron en van meerdere gegevensbronnen van hetzelfde type om al uw gegevens voor attributie in te voeren.

* Gebruik met bijna om het even welke CRM, niet alleen Salesforce en Dynamica.
* Sluit meerdere CRM-instanties en/of MAP-instanties aan op één Marketo Measure-instantie.
* Gegevens over webinaire registratie en deelname van derden beschikbaar maken.

De directe verbindingen van CRM en van het Marketo Engage zijn niet meer beschikbaar voor Ultimate.

* Ultimate duwt gegevens niet terug naar de CRM. De klanten kunnen gegevens van het gegevenspakhuis verbruiken.
* Marketers blijven gegevens van het advertentieplatform leveren via directe verbindingen en webactiviteiten volgen via Marketo Measure javascript.

Ultieme gebruikers worden ingericht voor AEP. Als ze al een AEP hebben, zullen we geen nieuw exemplaar aanbieden.

* De geleverde versie AEP zal alle bronschakelaars, schema gegevensmodellering, datasets, ad hoc vraagdienst, en een bestemming voor slechts Marketo Measure omvatten.

Meer informatie over [Marketo Measure Ultimate](/help/marketo-measure-ultimate/marketo-measure-ultimate-overview.md).

## Schema&#39;s en gegevenssets {#schemas-and-datasets}

>[!TIP]
>
>Uitchecken [Bouwstenen van een schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=en#building-blocks-of-a-schema) voor een overzicht van schema&#39;s, klassen, en gebiedsgroepen.

XDM Schema = Class + Schema Field Group*

* De vereiste velden kunnen niet worden gewijzigd. Klanten kunnen aangepaste velden maken en toevoegen.
* Voorbeeld van een veldnaam op basis van hiërarchie: accountOrganisation.annualRevenue.amount

&#42; _Een schema bestaat uit een klasse en nul of meer groepen schemavelden. Dit betekent u een datasetschema kon samenstellen zonder gebiedsgroepen te gebruiken._

![](assets/marketo-measure-ultimate-implementation-guide-.png)

ExL: Overzicht van gegevenssets: Alle gegevens die succesvol in AEP zijn opgenomen, blijven in het Data Lake bestaan als gegevenssets. Een dataset is een opslag en beheersconstructie voor een inzameling van gegevens, typisch een lijst, die een schema (kolommen) en gebieden (rijen) bevat.

## Een schema maken {#creating-a-schema}

Wij adviseren klanten een auto-generatienut gebruiken om 10 standaardB2B- schema&#39;s tot stand te brengen.

De stappen om het nut te downloaden en te plaatsen kunnen in de &quot;van de Opstelling B2B namespaces en schema auto-generatie nut&quot;sectie in ExL worden gevonden: B2B namespaces en schema&#39;s

Voor klanten met een CDP bevoegdheid: Creeer schema&#39;s door naar de Bronpagina te gaan

Selecteer Gegevens toevoegen > Sjablonen gebruiken in een bron

![](assets/marketo-measure-ultimate-implementation-guide-.png)

Selecteer een account en alle B2B-sjablonen om 10 standaard B2B-schema&#39;s te maken.

![](assets/marketo-measure-ultimate-implementation-guide-.png)

## Gegevensstromen {#dataflows}

Voorbeeld: Overzicht van gegevensstromen

Stappen om een gegevensstroom te maken:

1. Selecteer een bron.
1. Selecteer een bestaand account of maak een account.
1. Selecteer een gegevenstype in de lijst met beschikbare typen die u uit de bron wilt importeren.
1. Selecteer een bestaande dataset of creeer een nieuwe dataset.
1. Wijs de gebieden van de Bron aan het schema toe.

   >[!NOTE]
   >
   >* Als u één schematype aan een andere identieke kaart toewijst, zal het automatisch worden gedaan.
   >* U kunt ook toewijzingen importeren uit een andere flow in het systeem.
   >* U kunt één Bronveld toewijzen aan meerdere doelvelden, maar u kunt niet het tegenovergestelde doen.
   >* U kunt berekende velden maken (bijvoorbeeld Data Prep-toewijzingsfuncties).

   >[!CAUTION]
   >
   >* U kunt een gegevensstroom bewerken, maar er wordt geen back-up van de gegevens gemaakt wanneer een toewijzing wordt gewijzigd.
   >* Als een vereist veld NULL is, wordt de volledige flow geweigerd.

ExL: Marketo Measure Ultimate Data Integrity-vereiste

1. Stel een cadence voor gegevensbelasting in.
1. Controleren en voltooien.
1. Controleer de pagina &quot;Accountstatus&quot; in de instellingen voor maatgebruikersinterface voor de status van de gegevensstroom.

Controle: Bronnen → Dataflows pagina om de status van gegevensstromen te controleren om de activiteitendetails van een dataset te bekijken, eenvoudig op de dataset klikken om dataflow fouten te bekijken, een dataflow te selecteren, een dataflow looppas te kiezen, en &quot;de voorproef van de diagnostiek van de Fout te klikken&quot;

## Gegevenscontrole {#data-inspection}

ExL: Marketo Measure Ultimate Data Integrity-vereiste Dit document bevat vereiste velden voor elke XDM en inspectievragen. Het zal in ExL worden gepubliceerd.

Optie 1: Om vragen van UI direct in werking te stellen, heb toegang tot het lusje van Vragen onder het Beheer van Gegevens.

![](assets/marketo-measure-ultimate-implementation-guide-.png)

Optie 2: PSQL (sneller en betrouwbaarder) downloaden en gebruiken: PSQL aansluiten op Query Service

## Dataset activeren voor Marketo Measure {#activate-dataset-for-marketo-measure}

Voordat u begint, gaat u naar het gedeelte &quot;Experience Platform > Sandbox-toewijzing&quot; in de instellingen voor de gebruikersinterface van meten en wijst u een sandbox toe.

>[!CAUTION]
>
>Dit kan niet worden gewijzigd als de optie eenmaal is geselecteerd.

1. Ga in AEP naar &quot;Doelen > Marketo Measure-pagina&quot; om gegevenssets te exporteren.

1. Vorm bestemming.

1. Gegevensset activeren.

1. Controleer de pagina &quot;Accountstatus&quot; in de instellingen voor maatgebruikersinterface voor de status van de gegevensstroom.

Opmerkingen: gegevens voor een bepaalde entiteit (bijvoorbeeld Account) van een bepaalde bron kunnen slechts in één gegevensset worden opgenomen. Elke dataset kan slechts in één gegevensstroom worden omvat. Overtredingen zullen de gegevensstroom tijdens runtime stoppen.
Verwijder de volledige bestemming in AEP om gegevens in Meetlat te verwijderen. Als u deze optie uitschakelt, worden alleen nieuwe gegevens geëxporteerd en blijven de oude gegevens behouden.
De configuratie Meetlat ziet er meestal hetzelfde uit, maar sommige onderdelen, zoals Werkgebiedtoewijzing, zien er anders uit.
Het vergt een paar uren voor een nieuwe dataflow om een stroomlooppas te produceren, en dan komen zij met regelmatige uurintervallen voor.

Bij Maatregel moet de standaardvaluta worden ingesteld in de sectie &quot;Valuta&quot;. Als klanten meerdere valuta&#39;s gebruiken, moet het schema voor de omrekeningskoers van de valuta in AEP worden ingevuld om te kunnen lezen en gebruiken voor omrekeningen.

Werkgebiedtoewijzing We importeren geen fasen automatisch uit klantgegevens, zodat alle fasen handmatig moeten worden toegewezen.

Gebruikers kunnen fasen toewijzen uit verschillende bronnen.

![](assets/marketo-measure-ultimate-implementation-guide-.png)

Als de fases niet in kaart worden gebracht, zal het systeem niet functioneren omdat er nergens gegevens zullen zijn om te gaan.
De Regels van het Lid van de campagne moeten een dataset selecteren en regels voor elk plaatsen.

De Regels van de Gebeurtenissen van de ervaring moeten een dataset selecteren en activiteitentypes selecteren.
Aangepaste activiteiten worden nog niet ondersteund.
Als de klant activiteiten heeft die niet op de beschikbare opties passen, stellen wij voor deze te categoriseren als &quot;Interessmoment&quot; en aangepaste velden te gebruiken om ze te onderscheiden.

Offline Kanalen wij doen dataset-specifieke regels van de kanaalafbeelding niet, zodat zou dit globaal zijn.
We moeten uiteindelijk zowel het Campagnertype van CRM als het Kanaal aanpassen, maar voor nu, kunnen wij de kanaalnaam aan beide gebieden als tussenoplossing in kaart brengen.
Kanaalregels: de gegevens in de back-up hebben geen gegevens over de werkgebiedovergang.

De instellingen voor aanraakpunten en segmenten blijven ongewijzigd.
