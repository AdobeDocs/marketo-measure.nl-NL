---
description: Best practices voor segmentatiebegeleiding voor Marketo Measure-gebruikers
title: Beste praktijken voor Segmentatie
exl-id: 68281210-383b-4688-86e9-27fbdc1fabbb
feature: Segmentation
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 0%

---

# Beste praktijken voor Segmentatie {#best-practices-for-segmentation}

## Overzicht {#overview}

[!DNL Marketo Measure] De segmentatie staat u toe om regels te bepalen, die hoofdzakelijk filters zijn, die op uw gebieden van CRM worden gebaseerd om hen in individuele segmenten te verpakken. Deze segmenten zijn vervolgens beschikbaar voor gebruik in uw Discover-dashboards en in uw [!DNL Salesforce] -rapporten.

Segmentering is van cruciaal belang voor het gebruik van uw [!DNL Marketo Measure] -account, met name in uw Discover-borden. Omdat de [!DNL Marketo Measure] Discover boards tot een vooraf bepaalde reeks filters beperkt zijn, geeft de segmentatie u de capaciteit om uw gegevens in Ontdekking te ontleden veel als u in uw [!DNL Salesforce] rapportering zou willen.

Als u deze optie inschakelt in [!DNL Salesforce] , worden segmentwaarden geschreven naar het veld Segment en bevinden deze zich binnen elk type rapport voor aanraakpunten van koper. Dit maakt een uniforme rapportage op beide platforms mogelijk. Het segment is ook te vinden op het &quot;aanraakpuntdetail&quot; van elk aanraakpunt.

Als u deze optie inschakelt in [!UICONTROL Discover] , worden Segmenten weergegeven als een beschikbaar filter in de vervolgkeuzelijst met filters die zich op alle platen bevindt.

## Beste praktijken {#best-practice}

Of u segmentatie voor het eerst bepaalt of enkel de segmentatie herziet die eerder is gevestigd, houd de volgende beste praktijken in mening.

* Houd het eenvoudig!
* Richt uw segmentnaam aan de nomenclatuur van uw organisatie, d.w.z., de categorie = filternaam, segment = filterwaarde
* Gebruik geen formulervelden in uw regels
* Maak waar mogelijk de segmentatie op zowel de lead/contactpersoon als de opportunity, zodat u deze voor de hele funnel kunt gebruiken
   * Als u een klant van Marketo Measure Ultimate bent en uw StandaardVoorwerp Dashboard als Contact hebt geplaatst, gebruik niet de hieronder twee gebieden specifiek voor Lood ([ leert meer hier ](/help/marketo-measure-ultimate/data-integrity-requirement.md){target="_blank"}).
      * b2b.personStatus
      * b2b.isConverted
   * Niet elke categorie Segment wordt uitgelijnd op de gehele funnel
      * Een segmentcategorie van &#39;Opportunity Type&#39; heeft bijvoorbeeld geen betrekking op leads, maar een segment met betrekking tot &#39;Region&#39; is waarschijnlijk een categorie die in de hele funnel kan worden gedefinieerd
* Denk aan de manieren u momenteel uw gegevens, of het in CRM of een hulpmiddel van BI is, bouwend dit als Segment in [!DNL Marketo Measure] zodat kunt u de zelfde rapportering in Discover hebben

## Aanbevolen werkwijzen voor onderhoud {#best-practice-for-maintenance}

Als u de segmentatie ten minste twee keer per jaar controleert, is de segmentatie up-to-date. Als beste praktijken, adviseren wij het herzien van uw regels binnen het &quot;[!UICONTROL Segments]&quot;lusje van uw [!DNL Marketo Measure] Montages van de Rekening, evenals het trekken van rapporten binnen [!DNL Salesforce] om uw Segmenten in actie te herzien. Deze stappen zullen u en uw team helpen vertrouwen in uw segmentatie en daarna uw [!DNL Marketo Measure] rapportering te voelen.

Andere redenen aan dat zouden een overzicht kunnen teweegbrengen uw Segmentatie omvat..

* Omzet in uw marketingteam
* Wijzigingen in velden die worden gebruikt om de segmenten te definiëren
* Toevoegingen of wijzigingen aan de segmenten die al zijn ingesteld

>[!MORELIKETHIS]
>
>[ hoe te de Segmentatie van de Douane van de Opstelling ](/help/advanced-features/segmentation/custom-segmentation.md)
