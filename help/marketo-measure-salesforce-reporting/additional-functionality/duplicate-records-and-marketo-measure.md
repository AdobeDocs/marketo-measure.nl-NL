---
unique-page-id: 18874572
description: Records dupliceren [!DNL Marketo Measure] - [!DNL Marketo Measure]
title: Records dupliceren [!DNL Marketo Measure]
exl-id: e340100c-120a-4771-946d-336a1458da4e
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 0%

---

# Records dupliceren [!DNL Marketo Measure] {#duplicate-records-and-marketo-measure}

>[!NOTE]
>
>Mogelijk ziet u instructies die &quot;[!DNL Marketo Measure]&quot; in de documentatie, maar zie nog steeds &quot;Bizible&quot; in uw CRM. We werken eraan dat dit wordt bijgewerkt en de herbranding wordt binnenkort weerspiegeld in uw CRM.

[!DNL Marketo Measure] gebruikt het e-mailadres als een unieke identificatie bij het koppelen van gegevens aan een gerelateerde lead of contactpersoon in de CRM. Wanneer [!DNL Marketo Measure] Vindt veelvoudige Leidingen of Contacten met het zelfde e-mailadres, wij oppervlakte de zelfde gegevens over alle verslagen. Dit heeft gevolgen wanneer u rapporteert over de leads of de contactpersonen met [!DNL Marketo Measure] en kan het aantal unieke personen met aanraakpunten voor kopers onjuist opblazen.

Hoe ziet dit eruit in [!DNL Marketo Measure] Rapportage?

_Voorbeeld van rapport: [!DNL Marketo Measure] Personen met aanraakpunten voor kopers._

![](assets/1-1.png)

U kunt de [!DNL Marketo Measure] Persoon-id van kelsey@adobe.com dat er zowel een lead als een contactpersoon bestaat met dat e-mailadres. In dit rapport worden 2 First Touches gerapporteerd, twee Lead Creation Touches en twee PostLC-interacties. Deze dubbele gegevens delen de datum van het aanraakpunt en de informatie van het aanraakpunt, wat tot de conclusie zou kunnen leiden dat zij twee verschillende personen zijn, hoewel zij dezelfde persoon zijn.

**Aanbeveling**

* Om de terugkeer in uw rapporten te maximaliseren, adviseren wij gebruikend een deduping hulpmiddel binnen uw CRM om ervoor te zorgen dat u slechts netto nieuwe, unieke verslagen creeert. Dit kan met uw hulpmiddel van de Automatisering van de Marketing of een afzonderlijke software worden gedaan die binnen uw CRM wordt geïnstalleerd. [!DNL Marketo Measure] dedupliceert records niet automatisch en biedt deze service niet via onze software aan.
* Een andere optie is om records handmatig samen te voegen wanneer u duplicaten identificeert. Dit proces kan tijdrovend en vervelend zijn, maar de output van nauwkeurige rapportering is de tijdinvestering waard.
