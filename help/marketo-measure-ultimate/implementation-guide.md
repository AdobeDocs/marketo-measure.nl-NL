---
description: '[!DNL Marketo Measure] Ultieme implementatiehandleiding - [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] Ultieme implementatiegids'
feature: Integration, Tracking, Attribution
source-git-commit: 1d954811e90165953f9d56a17747a3f12c723023
workflow-type: tm+mt
source-wordcount: '1008'
ht-degree: 0%

---

# [!DNL Marketo Measure] Ultieme implementatiegids {#marketo-measure-ultimate-implementation-guide}

Dit artikel fungeert als implementatiegids voor Marketo Measure Ultimate en biedt duidelijke stappen en inzichten om een succesvolle integratie en toepassing te waarborgen.

## Belangrijkste verschillen bij gebruik van Ultimate via standaardtiers {#main-differences-when-using-ultimate-over-standard-tiers}

B2B-gegevens importeren via AEP: Van markers wordt verwacht dat ze hun B2B-gegevens (bijvoorbeeld account, opportunity, Contact, lead, campagne, campagnerelid, activiteit) via AEP doorgeven. Maak gebruik van bijna elke gegevensbron en meerdere gegevensbronnen van hetzelfde type om al uw gegevens voor attributie in te voeren.

* Gebruik met bijna om het even welke CRM, niet alleen Salesforce en Dynamica.
* Sluit meerdere CRM-instanties en/of MAP-instanties aan op één Marketo Measure-instantie.
* Gegevens over webinaire registratie en deelname van derden beschikbaar maken.

De directe verbindingen van CRM en van het Marketo Engage zijn niet meer beschikbaar voor Ultimate.

* Ultimate duwt gegevens niet terug naar de CRM. De klanten kunnen gegevens van het gegevenspakhuis verbruiken.
* Marketers blijven gegevens van het advertentieplatform leveren via directe verbindingen en webactiviteiten volgen via Marketo Measure javascript.

Ultieme gebruikers worden geleverd met AEP. Als ze al een AEP hebben, zullen we geen nieuw geval opnieuw aanbieden.

* De versie AEP provisioned omvat alle bronschakelaars, schema gegevensmodellering, datasets, de ad hoc vraagdienst, en een bestemming voor slechts Marketo Measure.

Meer informatie over [Marketo Measure Ultimate](/help/marketo-measure-ultimate/marketo-measure-ultimate-overview.md){target="_blank"}.

## Schema&#39;s en gegevenssets {#schemas-and-datasets}

>[!NOTE]
>
>Uitchecken [Bouwstenen van een schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=nl-NL#building-blocks-of-a-schema){target="_blank"} voor een overzicht van schema&#39;s, klassen, en gebiedsgroepen.

**XDM Schema = Class + Schema veldgroep&#42;**

* De vereiste velden kunnen niet worden gewijzigd. Klanten kunnen aangepaste velden maken en toevoegen.
* Voorbeeld van een veldnaam op basis van hiërarchie: accountOrganisation.annualRevenue.amount

&#42; _Een schema bestaat uit een klasse en nul of meer groepen schemavelden. Dit betekent u een datasetschema kon samenstellen zonder gebiedsgroepen te gebruiken._

![](assets/marketo-measure-ultimate-implementation-guide-1.png)

[Overzicht van gegevenssets](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=nl-NL){target="_blank"}: Alle gegevens die met succes in AEP worden opgenomen, blijven in het Data Lake als gegevenssets bestaan. Een dataset is een opslag en beheersconstructie voor een inzameling van gegevens, typisch een lijst, die een schema (kolommen) en gebieden (rijen) bevat.

## Een schema maken {#creating-a-schema}

Wij adviseren gebruikend een auto-generatienut om tien standaardB2B- schema&#39;s tot stand te brengen.

* Stappen om het hulpprogramma te downloaden en in te stellen [hier te vinden](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo-namespaces.html?lang=nl-NL#set-up-b2b-namespaces-and-schema-auto-generation-utility){target="_blank"}.

Voor degenen met een _&#x200B;**CDP-machtiging**&#x200B;_: Maak schema&#39;s door naar de pagina Bronnen te gaan.

* Selecteer Gegevens toevoegen > Sjablonen gebruiken in een bron

![](assets/marketo-measure-ultimate-implementation-guide-2.png)

* Selecteer een account en alle B2B-sjablonen om tien standaard B2B-schema&#39;s te maken.

![](assets/marketo-measure-ultimate-implementation-guide-3.png)

## Gegevensstromen {#dataflows}

>[!IMPORTANT]
>
>Wanneer het toevoegen van een nieuwe dataset, adviseren wij het creëren van een stroom in plaats van het gebruiken van bestaande.

[Overzicht van gegevensstromen](https://experienceleague.adobe.com/docs/experience-platform/dataflows/home.html?lang=nl-NL){target="_blank"}

**Stappen om een gegevensstroom te maken:**

1. Selecteer een bron.
1. Selecteer een bestaand account of maak een account.
1. Selecteer een gegevenstype in de lijst met beschikbare typen die u uit de bron wilt importeren.
1. Selecteer een bestaande dataset of creeer een dataset.
1. Wijs de gebieden van de Bron aan het schema toe.

   >[!NOTE]
   >
   >* Als u een schematype aan een andere identieke kaart toewijst, wordt het automatisch gedaan.
   >* U kunt ook toewijzingen importeren uit een andere flow in het systeem.
   >* U kunt één Bronveld toewijzen aan meerdere doelvelden, maar u kunt niet het tegenovergestelde doen.
   >* U kunt berekende velden maken ([Toewijzingsfuncties van Data Prep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/functions.html?lang=nl-NL){target="_blank"}).

   >[!CAUTION]
   >
   >* U kunt een gegevensstroom bewerken, maar er wordt geen back-up van de gegevens gemaakt wanneer een toewijzing wordt gewijzigd.
   >* Als een vereist veld NULL is, wordt de volledige flow geweigerd.

   >[!NOTE]
   >
   >[Marketo Measure vereist voor ultieme gegevensintegriteit](/help/marketo-measure-ultimate/data-integrity-requirement.md){target="_blank"}

1. Stel een cadence voor gegevensbelasting in.
1. Controleren en voltooien.
1. Controleer de pagina &quot;Accountstatus&quot; in de maatinstellingen voor de gebruikersinterface voor gegevensstroomstatus.

**Controle:**

Bronnen > Gegevensstroom pagina om de status van gegevensstromen te controleren

* Om de activiteitendetails van een dataset te bekijken, klik eenvoudig de dataset.
* Als u gegevensstroomfouten wilt weergeven, selecteert u een gegevensstroom, kiest u een gegevensstroomuitvoering en klikt u op Voorvertoning van foutdiagnose.

## Gegevenscontrole {#data-inspection}

Optie 1: Om vragen van UI direct in werking te stellen, heb toegang tot het lusje van Vragen onder het Beheer van Gegevens.

![](assets/marketo-measure-ultimate-implementation-guide-4.png)

Optie 2: [PSQL downloaden en gebruiken](https://experienceleague.adobe.com/docs/experience-platform/query/clients/psql.html?lang=nl-NL){target="_blank"} (sneller en betrouwbaarder).

## Dataset activeren voor Marketo Measure {#activate-dataset-for-marketo-measure}

Voordat u begint, gaat u naar het gedeelte &quot;Experience Platform > Sandbox-toewijzing&quot; in de instellingen voor de gebruikersinterface van meten en wijst u een sandbox toe.

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

* Als u meerdere valuta&#39;s gebruikt, moet het schema voor de omrekeningskoers van de valuta in AEP worden ingevuld om voor conversies te kunnen lezen en gebruiken.

**Werkgebiedtoewijzing:**

We importeren stadia niet automatisch uit gebruikersgegevens, zodat alle fasen handmatig moeten worden toegewezen.

* Gebruikers kunnen fasen toewijzen uit verschillende bronnen.

![](assets/marketo-measure-ultimate-implementation-guide-5.png)

Als de fases niet in kaart worden gebracht, zal het systeem niet functioneren omdat er nergens gegevens zullen zijn om te gaan.

Als u een Marketo Measure Ultimate-klant bent en uw standaarddashboard-object als contactpersoon hebt ingesteld, gebruikt u de onderstaande twee velden niet die specifiek zijn voor Lead ([meer informatie hier](/help/marketo-measure-ultimate/data-integrity-requirement.md){target="_blank"}).

* b2b.personStatus
* b2b.isConverted

**Regels voor campagneleden:**

Kies een dataset en stel regels voor elke gegevensset in.

**regels voor ervaringsgebeurtenissen:**

Kies een dataset en selecteer activiteitstypen.

* Aangepaste activiteiten worden nog niet ondersteund.
* Als de klant activiteiten heeft die niet op de beschikbare opties passen, stellen wij voor deze te categoriseren als &quot;Interessmoment&quot; en aangepaste velden te gebruiken om ze te onderscheiden.

**Offlinekanalen:**

* We doen geen dataset-specifieke kanaal-mapping regels, zodat zou dit globaal zijn.
* We moeten uiteindelijk zowel het Campagne Type als het Kanaal van CRM aanpassen, maar voor nu, kunnen wij de kanaalnaam aan beide gebieden als alternerende actie in kaart brengen.
* **Kanaalregels: de gegevens in de back-up hebben geen gegevens over de werkgebiedovergang.**

De instellingen voor aanraakpunten en segmenten blijven ongewijzigd.
