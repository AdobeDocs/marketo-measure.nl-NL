---
unique-page-id: 18874572
description: Records dupliceren en [!DNL Marketo Measure] - [!DNL Marketo Measure] - Productdocumentatie
title: Records dupliceren en [!DNL Marketo Measure]
exl-id: e340100c-120a-4771-946d-336a1458da4e
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 0%

---

# Records dupliceren en [!DNL Marketo Measure] {#duplicate-records-and-marketo-measure}

>[!NOTE]
>
>Mogelijk ziet u instructies die &quot;[!DNL Marketo Measure]&quot; in onze documentatie, maar zie nog &quot;Bizible&quot;in uw CRM. We werken eraan dat dit wordt bijgewerkt en de herbranding wordt binnenkort weerspiegeld in uw CRM.

[!DNL Marketo Measure] Gebruikt het e-mailadres als onze unieke id wanneer gegevens worden vergeleken met een gerelateerde lead of contactpersoon in de CRM. Wanneer [!DNL Marketo Measure] Als u meerdere leads of contactpersonen met hetzelfde e-mailadres zoekt, worden dezelfde gegevens in alle records weergegeven. Dit heeft gevolgen wanneer u rapporteert over de leads of contactpersonen met [!DNL Marketo Measure] en kan ten onrechte de hoeveelheid unieke personen opblazen die aanraakpunten voor kopers hebben.

Hoe ziet dit eruit in [!DNL Marketo Measure] Rapportage?

_Voorbeeld: [!DNL Marketo Measure] Personen met aanraakpunten voor kopers._

![](assets/1-1.png)

U kunt de [!DNL Marketo Measure] Persoon-id van kelsey@adobe.com dat er zowel een lead als een contactpersoon bestaat met dat e-mailadres. Dit rapport bevat 2 First Touches, 2 Lead Creation Touches en 2 PostLC-interacties. Deze dubbele gegevens hebben dezelfde aanraakpuntdatum en dezelfde aanraakpuntinformatie, wat tot de conclusie zou kunnen leiden dat zij twee verschillende personen zijn, hoewel zij dezelfde persoon zijn.

**Aanbeveling**

* Om de terugkeer in uw rapporten te maximaliseren, adviseren wij leveraging een deduping hulpmiddel binnen uw CRM om ervoor te zorgen dat u slechts netto nieuwe, unieke verslagen creeert. Dit kan met uw hulpmiddel van de Automatisering van de Marketing of een afzonderlijke software worden gedaan die binnen uw CRM wordt ge??nstalleerd. [!DNL Marketo Measure] dedupliceert records niet automatisch en biedt deze service niet via onze software aan.
* Een andere optie is om records handmatig samen te voegen wanneer u duplicaten identificeert. Dit proces kan tijdrovend en vervelend zijn, maar de output van nauwkeurige rapportering is de tijdinvestering waard.
