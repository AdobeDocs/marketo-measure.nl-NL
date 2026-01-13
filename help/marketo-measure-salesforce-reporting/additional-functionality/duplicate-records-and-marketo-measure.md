---
description: Records dupliceren en  [!DNL Marketo Measure] - [!DNL Marketo Measure]
title: Records dupliceren en  [!DNL Marketo Measure]
exl-id: e340100c-120a-4771-946d-336a1458da4e
feature: Tracking
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 0%

---


# Records dupliceren en [!DNL Marketo Measure] {#duplicate-records-and-marketo-measure}

>[!NOTE]
>U kunt instructies zien die &quot;[!DNL Marketo Measure]&quot;in de documentatie specificeren, maar nog zie &quot;Bizible&quot;in uw CRM. We werken eraan dat dit wordt bijgewerkt en de herbranding wordt binnenkort weerspiegeld in uw CRM.

[!DNL Marketo Measure] gebruikt het e-mailadres als een unieke identificatie bij het koppelen van gegevens aan een gerelateerde lead of contactpersoon in de CRM. Als [!DNL Marketo Measure] meerdere leads of contactpersonen met hetzelfde e-mailadres vindt, worden dezelfde gegevens over alle records weergegeven. Dit heeft gevolgen wanneer u rapporteert over de leads of contactpersonen met [!DNL Marketo Measure] en het aantal unieke personen met aanraakpunten voor kopers onjuist opbladert.

Hoe ziet dit eruit in [!DNL Marketo Measure] Reporting?

_Rapport van het Voorbeeld: [!DNL Marketo Measure] Personen met de Aanraakpunten van de Koper._

![ 1 ](assets/1-1.png)

Voor de [!DNL Marketo Measure] persoon-id van kelsey@adobe.com ziet u dat er zowel een lead als een contactpersoon bestaat met dat e-mailadres. In dit rapport worden 2 First Touches gerapporteerd, twee Lead Creation Touches en twee PostLC-interacties. Deze dubbele gegevens delen de datum van het aanraakpunt en de informatie van het aanraakpunt, wat tot de conclusie zou kunnen leiden dat zij twee verschillende personen zijn, hoewel zij dezelfde persoon zijn.

**Aanbeveling**

* Om de terugkeer in uw rapporten te maximaliseren, adviseren wij gebruikend een deduping hulpmiddel binnen uw CRM om ervoor te zorgen dat u slechts netto nieuwe, unieke verslagen creeert. Dit kan met uw hulpmiddel van de Automatisering van de Marketing of een afzonderlijke software worden gedaan die binnen uw CRM wordt geïnstalleerd. [!DNL Marketo Measure] dedupliceert records niet automatisch en biedt deze service niet via de software aan.
* Een andere optie is om records handmatig samen te voegen wanneer u duplicaten identificeert. Dit proces kan tijdrovend en vervelend zijn, maar de output van nauwkeurige rapportering is de tijdinvestering waard.
