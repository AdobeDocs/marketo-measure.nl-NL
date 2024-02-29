---
description: Beste praktijken voor Segmentatie - [!DNL Marketo Measure] - Productdocumentatie
title: Beste praktijken voor Segmentatie
exl-id: 68281210-383b-4688-86e9-27fbdc1fabbb
feature: Segmentation
source-git-commit: cc786cb3af08fa36af91ef22f4dba3072c9617eb
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---

# Beste praktijken voor Segmentatie {#best-practices-for-segmentation}

## Overzicht {#overview}

[!DNL Marketo Measure] De segmentatie staat u toe om regels te bepalen, die hoofdzakelijk filters zijn, die op uw gebieden van CRM worden gebaseerd om hen in individuele segmenten te emmeren. Deze segmenten zijn dan beschikbaar voor gebruik in uw Discover-dashboards en uw [!DNL Salesforce] rapportage.

Segmentering is van cruciaal belang voor het gebruik van uw [!DNL Marketo Measure] -account, met name in uw Discover boards. Omdat de [!DNL Marketo Measure] Borden ontdekken zijn beperkt tot een vooraf bepaalde reeks filters, segmentatie geeft u de mogelijkheid om uw gegevens in Discover te ontleden, net als in uw [!DNL Salesforce] rapportage.

Wanneer geduwd op [!DNL Salesforce], worden de waarden van het Segment geschreven aan het gebied van het &quot;Segment&quot;en zijn binnen om het even welk type van het de aanraakpuntrapport van de Koper. Dit maakt een uniforme rapportage op beide platforms mogelijk. Het segment is ook te vinden op het &quot;aanraakpuntdetail&quot; van elk aanraakpunt.

Wanneer geduwd op [!UICONTROL Discover]Segmenten worden weergegeven als een beschikbaar filter in de keuzelijst met filters die zich op alle gebieden bevindt.

## Beste praktijken {#best-practice}

Of u segmentatie voor het eerst bepaalt of enkel de segmentatie herziet die eerder is gevestigd, houd de volgende beste praktijken in mening.

* Houd het eenvoudig!
* Richt uw segmentnaam aan de nomenclatuur van uw organisatie, d.w.z., de categorie = filternaam, segment = filterwaarde
* Gebruik geen formulervelden in uw regels
* Maak waar mogelijk de segmentatie op zowel de lead/contactpersoon als de opportunity, zodat u deze over de gehele trechter kunt gebruiken
   * Als u een Marketo Measure Ultimate-klant bent en uw standaarddashboard-object als contactpersoon hebt ingesteld, gebruikt u de onderstaande twee velden niet die specifiek zijn voor Lead ([meer informatie hier](/help/marketo-measure-ultimate/data-integrity-requirement.md){target="_blank"}).
      * b2b.personStatus
      * b2b.isConverted
   * Niet zal elke categorie van het Segment zich door het volledige trechter richten
      * Een segmentcategorie van &#39;Opportunity Type&#39; heeft bijvoorbeeld geen betrekking op Leads, maar een segment met betrekking tot &#39;Regio&#39; is waarschijnlijk een categorie die in de gehele trechter kan worden gedefinieerd
* Denk aan de manieren u momenteel uw gegevens wilt segmenteren, of het in CRM of een hulpmiddel van BI is, denk na bouwend dit als Segment in [!DNL Marketo Measure] zodat u dezelfde rapportage kunt uitvoeren in Discover

## Aanbevolen werkwijzen voor onderhoud {#best-practice-for-maintenance}

Als u de segmentatie ten minste twee keer per jaar controleert, is de segmentatie up-to-date. We raden u aan om uw regels te herzien in het &quot;[!UICONTROL Segments]&#39; tabblad van uw [!DNL Marketo Measure] Accountinstellingen en rapporten ophalen binnen [!DNL Salesforce] om uw segmenten in actie te bekijken. Deze stappen helpen u en uw team vertrouwen in uw segmentatie en daarna uw [!DNL Marketo Measure] rapportage.

Andere redenen aan dat zouden een overzicht kunnen teweegbrengen uw Segmentatie omvat..

* Omzet in uw marketingteam
* Wijzigingen in velden die worden gebruikt om de segmenten te definiëren
* Toevoegingen of wijzigingen aan de segmenten die al zijn ingesteld

>[!MORELIKETHIS]
>
>[Aangepaste segmentatie instellen](/help/advanced-marketo-measure-features/segmentation/custom-segmentation.md)
