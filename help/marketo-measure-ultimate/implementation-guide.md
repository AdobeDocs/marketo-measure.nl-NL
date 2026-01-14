---
description: '''[!DNL Marketo Measure] Ultimate Implementation Guide - [!DNL Marketo Measure]'''
title: '[!DNL Marketo Measure] Ultimate Implementation Guide'
feature: Integration, Tracking, Attribution
exl-id: 0c707875-5d05-49b9-b1ff-c3f7b711ebd1
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '1008'
ht-degree: 0%

---

# [!DNL Marketo Measure] Ultimate Implementation Guide {#marketo-measure-ultimate-implementation-guide}

Dit artikel fungeert als implementatiegids voor Marketo Measure Ultimate en biedt duidelijke stappen en inzichten om een succesvolle integratie en toepassing te waarborgen.

## Belangrijkste verschillen bij gebruik van Ultimate op standaardtips {#main-differences-when-using-ultimate-over-standard-tiers}

B2B-gegevens importeren via AEP: Van markeertekens wordt verwacht dat ze hun B2B-gegevens (bijvoorbeeld account, opportunity, Contact, lead, campagne, campagnerelid, activiteit) via AEP doorgeven. Maak gebruik van bijna elke gegevensbron en meerdere gegevensbronnen van hetzelfde type om al uw gegevens voor attributie in te voeren.

* Gebruik met bijna om het even welke CRM, niet alleen Salesforce en Dynamics.
* Sluit meerdere CRM-instanties en/of MAP-instanties aan op één Marketo Measure-instantie.
* Gegevens over webinaire registratie en deelname van derden beschikbaar maken.

De directe verbindingen CRM en Marketo Engage zijn niet meer beschikbaar voor Ultimate.

* Ultimate duwt geen gegevens terug naar de CRM. De klanten kunnen gegevens van het gegevenspakhuis verbruiken.
* Marketers blijven gegevens van het advertentieplatform leveren via directe verbindingen en webactiviteiten volgen via Marketo Measure javascript.

Ultimate-gebruikers beschikken over AEP. Als ze AEP al hebben, zullen we geen nieuw exemplaar opnieuw aanbieden.

* De versie van AEP provisioned omvat alle bronschakelaars, schema gegevensmodellering, datasets, de ad hoc vraagdienst, en een bestemming voor slechts Marketo Measure.

Leer meer over [&#x200B; Marketo Measure Ultimate &#x200B;](/help/marketo-measure-ultimate/overview.md){target="_blank"}.

## Schema&#39;s en gegevenssets {#schemas-and-datasets}

>[!NOTE]
>
>Controle uit [&#x200B; Bouwstenen van een Schema &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=nl-NL#building-blocks-of-a-schema){target="_blank"} voor een overzicht van schema&#39;s, klassen, en gebiedsgroepen.

**XDM Schema = Klasse + de Groep van het Gebied van het Schema&#42;**

* De vereiste velden kunnen niet worden gewijzigd. Klanten kunnen aangepaste velden maken en toevoegen.
* Voorbeeld van een veldnaam op basis van hiërarchie: accountOrganisation.annualRevenue.amount

&#42; _het schema van A bestaat uit een klasse en nul of meer groepen van het schemagebied. Dit betekent u een datasetschema kon samenstellen zonder gebiedsgroepen te gebruiken._

![](assets/marketo-guide-1.png)

[&#x200B; Overzicht van Datasets &#x200B;](https://experienceleague.adobe.com/nl/docs/experience-platform/catalog/datasets/overview#){target="_blank"}: Alle gegevens die met succes in AEP worden opgenomen worden voortgeduurd binnen het meer van Gegevens als datasets. Een dataset is een opslag en beheersconstructie voor een inzameling van gegevens, typisch een lijst, die een schema (kolommen) en gebieden (rijen) bevat.

## Een schema maken {#creating-a-schema}

Wij adviseren gebruikend een auto-generatienut om tien standaardB2B- schema&#39;s tot stand te brengen.

* De stappen aan download en opstelling het nut [&#x200B; kunnen hier &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo-namespaces.html?lang=nl-NL#set-up-b2b-namespaces-and-schema-auto-generation-utility){target="_blank"} worden gevonden.

Voor die met a _&#x200B;**CDP beding**&#x200B;_: Creeer schema&#39;s door naar de Bronpagina te gaan.

* Selecteer Gegevens toevoegen > Sjablonen gebruiken in een bron

![](assets/marketo-guide-2.png)

* Selecteer een account en alle B2B-sjablonen om tien standaard B2B-schema&#39;s te maken.

![](assets/marketo-guide-3.png)

## Gegevensstromen {#dataflows}

>[!IMPORTANT]
>
>Wanneer het toevoegen van een nieuwe dataset, adviseren wij het creëren van een stroom in plaats van het gebruiken van bestaande.

[&#x200B; Dataflows Overzicht &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/dataflows/home.html?lang=nl-NL){target="_blank"}

**Stappen om een dataflow tot stand te brengen:**

1. Selecteer een Source.
1. Selecteer een bestaand account of maak een account.
1. Selecteer een gegevenstype in de lijst met beschikbare typen die u wilt importeren uit de Source.
1. Selecteer een bestaande dataset of creeer een dataset.
1. Wijs de gebieden van Source aan het schema toe.

   >[!NOTE]
   >
   >* Als u een schematype aan een andere identieke kaart toewijst, wordt het automatisch gedaan.
   >* U kunt ook toewijzingen importeren uit een andere flow in het systeem.
   >* U kunt één Source-veld toewijzen aan meerdere doelvelden, maar u kunt niet het tegenovergestelde doen.
   >* U kunt berekende gebieden tot stand brengen ([&#x200B; Gegevens Prep toewijzingsfuncties &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/data-prep/functions.html?lang=nl-NL){target="_blank"}).

   >[!CAUTION]
   >
   >* U kunt een gegevensstroom bewerken, maar er wordt geen back-up van de gegevens gemaakt wanneer een toewijzing wordt gewijzigd.
   >* Als een vereist veld NULL is, wordt de volledige flow geweigerd.

   >[!NOTE]
   >
   >[&#x200B; Marketo Measure Ultimate Vereiste van de Integriteit van Gegevens &#x200B;](/help/marketo-measure-ultimate/data-integrity-requirement.md){target="_blank"}

1. Stel een cadence voor gegevensbelasting in.
1. Controleren en voltooien.
1. Controleer de pagina &quot;Accountstatus&quot; in de maatinstellingen voor de gebruikersinterface voor gegevensstroomstatus.

**Controle:**

Bronnen > Gegevensstroom pagina om de status van gegevensstromen te controleren

* Om de activiteitendetails van een dataset te bekijken, klik eenvoudig de dataset.
* Als u gegevensstroomfouten wilt weergeven, selecteert u een gegevensstroom, kiest u een gegevensstroomuitvoering en klikt u op Voorvertoning van foutdiagnose.

## Gegevenscontrole {#data-inspection}

Optie 1: Om vragen van UI direct in werking te stellen, heb toegang tot het lusje van Vragen onder het Beheer van Gegevens.

![](assets/marketo-guide-4.png)

Optie 2: [&#x200B; Download en gebruik PSQL &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/query/clients/psql.html?lang=nl-NL){target="_blank"} (sneller en betrouwbaarder).

## Dataset activeren voor Marketo Measure {#activate-dataset-for-marketo-measure}

Voordat u begint, gaat u naar de sectie &quot;Experience Platform > Sandbox-toewijzing&quot; in de instellingen voor de gebruikersinterface van meten en wijst u een sandbox toe.

>[!CAUTION]
>
>Dit kan niet worden gewijzigd als de optie eenmaal is geselecteerd.

1. Ga in AEP naar &quot;Doelen > Marketo Measure-pagina&quot; om gegevenssets te exporteren.
1. Vorm bestemming.
1. Gegevensset activeren.
1. Controleer de pagina &quot;Accountstatus&quot; in de instellingen voor maatgebruikersinterface voor de status van de gegevensstroom.

>[!NOTE]
>
>* Aanbevolen wordt slechts één dataset per gegevensstroom op te nemen.
>* De gegevens voor een bepaalde entiteit (bijvoorbeeld, Rekening) van een bepaalde bron kunnen slechts in één dataset gaan. Elke dataset kan slechts in één gegevensstroom worden omvat. Overtredingen stoppen de gegevensstroom bij uitvoering.
>* Verwijder de volledige bestemming in AEP om gegevens in Meetlat te verwijderen. Als u deze optie uitschakelt, worden nieuwe gegevens niet meer geëxporteerd en blijven de oude gegevens behouden.
>* De configuratie Meetlat ziet er meestal hetzelfde uit, maar sommige onderdelen, zoals Werkgebiedtoewijzing, zien er anders uit.
>* Het vergt een paar uren voor een nieuwe dataflow om een stroomlooppas te produceren, en dan komen zij met regelmatige uurintervallen voor.

Bij Maatregel moet de standaardvaluta worden ingesteld in de sectie &quot;Valuta&quot;.

* Als u meerdere valuta&#39;s gebruikt, moet het schema van de wisselkoersen in AEP worden ingevuld om te kunnen lezen en gebruiken voor conversies.

**Toewijzing van het Stadium:**

We importeren stadia niet automatisch uit gebruikersgegevens, zodat alle fasen handmatig moeten worden toegewezen.

* Gebruikers kunnen fasen toewijzen uit verschillende bronnen.

![](assets/marketo-guide-5.png)

Als de fases niet in kaart worden gebracht, zal het systeem niet functioneren omdat er nergens gegevens zullen zijn om te gaan.

Als u een klant van Marketo Measure Ultimate bent en uw StandaardVoorwerp Dashboard als Contact hebt geplaatst, gebruik niet de hieronder twee gebieden specifiek voor Lood ([&#x200B; leert meer hier &#x200B;](/help/marketo-measure-ultimate/data-integrity-requirement.md){target="_blank"}).

* b2b.personStatus
* b2b.isConverted

**Regels van het Lid van de Campagne:**

Kies een dataset en stel regels voor elke gegevensset in.

**de Regels van de Gebeurtenissen van de Ervaring:**

Kies een dataset en selecteer activiteitstypen.

* Aangepaste activiteiten worden nog niet ondersteund.
* Als de klant activiteiten heeft die niet op de beschikbare opties passen, stellen wij voor deze te categoriseren als &quot;Interessmoment&quot; en aangepaste velden te gebruiken om ze te onderscheiden.

**Off-line Kanalen:**

* We doen geen dataset-specifieke kanaal-mapping regels, zodat zou dit globaal zijn.
* We moeten uiteindelijk zowel het Campagne Type als het Kanaal van CRM aanpassen, maar voor nu, kunnen wij de kanaalnaam aan beide gebieden als alternerende actie in kaart brengen.
* **de regels van het Kanaal: De achtergevulde gegevens zullen geen gegevens van de werkgebiedovergang hebben.**

De instellingen voor aanraakpunten en segmenten blijven ongewijzigd.
