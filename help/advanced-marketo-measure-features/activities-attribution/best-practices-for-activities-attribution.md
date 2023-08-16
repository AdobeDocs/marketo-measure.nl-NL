---
description: Beste praktijken voor Activiteiten Attributie - [!DNL Marketo Measure] - Productdocumentatie
title: Aanbevolen procedures voor kenmerk Activiteiten
exl-id: 66fb9f47-3912-40a6-b112-3efca789f321
feature: Attribution
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# Aanbevolen procedures voor kenmerk Activiteiten {#best-practices-for-activities-attribution}

## Overzicht {#overview}

De [!DNL Marketo Measure] De eigenschap van de Attributie van activiteiten staat klanten toe om touchpoints van de verslagen van de Activiteit in uw CRM tot stand te brengen. Deze methode voor het maken van aanraakpunten is flexibel, omdat u regels kunt maken op basis van taak- of gebeurtenisvelden om [!DNL Marketo Measure] welke activiteitenverslagen zij moet produceren aanraakpunten van, en vervolgens toekenningskredieten ontvangen.

Het meest gebruikte geval voor deze functie is om regels te maken die de interactie van de Verkoop in uw touchpoint gegevens van de Koper opnemen. Met Kenmerken voor activiteiten kunt u uw verkoop- en marketinggegevens op één reis afstemmen.

Voor veel [!DNL Salesforce] instanties, kan het voorwerp van de Activiteit een verscheidenheid van verslagtypes huisvesten, zodat is het belangrijk dat uw regels van de Activiteit specifiek zijn en aan de verslagen worden aangepast u probeert om in aanraakpunten te vertalen. De volgende aanbevolen procedures helpen u ervoor te zorgen dat u zinvolle en waardevolle aanraakpunten maakt via uw activiteitentoewijzing.

## Beste praktijken {#best-practice}

Of u de regels van de Activiteit voor het eerst bepaalt of enkel het herzien van de regels van de Activiteit die eerder opstelling zijn geweest, houd de volgende beste praktijken in mening.

* Eenvoudig starten
   * Identificeer een paar zeer belangrijke types van Activiteiten u in uw wilt opnemen [!DNL Marketo Measure] gegevens, dan voeg meer types toe aangezien u met hoe deze touchpoints wordt vertrouwd vertrouwd
   * Zoals vermeld, is het primaire gebruiksgeval van deze eigenschap touchpoints te creëren die de doeltreffendheid van uw team van de Ontwikkeling van de Verkoop, specifiek de Uitgaande Vraag van de Telefoon en Uitgaande E-mail volgen

>[!NOTE]
>
>Het is **NOT** Aanbevolen om de Activiteiten van de Verkoop te volgen die nadat de Kans wordt gecreeerd aangezien het volgen van een proces van de Uitvoerders van de Verkoop niet veel inzicht zal aanbieden. Het doel is de invloed van de Verkoop naast de invloed van de Marketing te volgen, hoofdzakelijk in de ontwikkeling van een nieuwe Kans/pijpleiding productie

* Gebruik geen formulervelden om uw regels te definiëren
* Specifieke en nauwkeurige regels maken
   * U wilt dat de drempel voor het maken van een Activity-aanraakpunt gelijk is aan (of vergelijkbaar is) het lidmaatschap van een formuliervulling of campagne, dat wil zeggen (reageert op een uitgaande e-mail of voltooide telefoongesprekken)
* Nieuwe regels altijd valideren in [!DNL Salesforce] vóór opslaan en verwerken
   * Als u uw activiteitsregel(s) dupliceert in een rapporttype &quot;Taken en gebeurtenissen&quot;, krijgt u een duidelijk inzicht in het aantal aanraakpunten dat op basis van die regel wordt gemaakt.
* Werken met je verkoopteam
   * Het brengen in het team dat het dichtst met uw verslagen van de Activiteit of het hulpmiddel van de verkoopenablement werkt zal ervoor zorgen u de correcte gebieden gebruikt om uw regels te bepalen

## Aanbevolen werkwijzen voor onderhoud {#best-practice-for-maintenance}

Als u ten minste tweemaal per jaar uw regels voor activiteitskenmerken controleert, weet u zeker dat uw Activity-aanraakpunten correct en up-to-date zijn. U wilt ervoor zorgen dat deze regels geen ongewenste aanraakpunten maken die de gegevens van de koperkenmerk verwateren. Een overzicht van hoe uw regels worden bepaald zal u en uw team vertrouwen in uw Attributen van Activiteiten en zijn rol in uw voelen [!DNL Marketo Measure] gegevens.

Andere redenen die kunnen leiden tot een herziening van de activiteitenregels zijn onder meer...

* Omzet in uw marketingteam
* Wijzigingen in velden die worden gebruikt om uw activiteitenrecords te definiëren
* Wijzigingen of updates van uw hulpprogramma(s) voor verkoopmogelijkheden

>[!MORELIKETHIS]
>
>* [Activiteitenkenmerk](/help/advanced-marketo-measure-features/activities-attribution/salesforce-activities-attribution.md)
>* [Veelgestelde vragen over kenmerken van verkoopactiviteiten](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)

