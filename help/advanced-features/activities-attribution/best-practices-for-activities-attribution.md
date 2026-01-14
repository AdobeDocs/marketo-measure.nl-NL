---
description: Beste praktijken voor Activiteiten - Richtlijnen voor de Attributie voor de gebruikers van Marketo Measure
title: Aanbevolen procedures voor kenmerk Activiteiten
exl-id: 66fb9f47-3912-40a6-b112-3efca789f321
feature: Attribution
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 0%

---

# Aanbevolen procedures voor kenmerk Activiteiten {#best-practices-for-activities-attribution}

## Overzicht {#overview}

Met de functie [!DNL Marketo Measure] Activiteitenkenmerk kunnen klanten aanraakpunten maken op basis van activiteitenrecords in uw CRM. Deze methode voor het maken van aanraakpunten is flexibel. Hiermee kunt u regels maken op basis van de velden &#39;Taak&#39; of &#39;Gebeurtenis&#39; om [!DNL Marketo Measure] te laten weten welke activiteitenrecords het aanraakpunten moet maken en daarom een creditering van de toewijzing ontvangen.

Het meest gebruikte geval voor deze functie is om regels te maken die de interactie van de Verkoop in uw touchpoint gegevens van de Koper opnemen. Met Kenmerken voor activiteiten kunt u uw verkoop- en marketinggegevens op één reis afstemmen.

Voor veel [!DNL Salesforce] -instanties kan het Activity-object verschillende recordtypen bevatten. Het is daarom belangrijk dat uw Activiteitsregels specifiek zijn en zijn afgestemd op de records die u in aanraakpunten wilt vertalen. De volgende aanbevolen procedures helpen u ervoor te zorgen dat u zinvolle en waardevolle aanraakpunten maakt via uw activiteitentoewijzing.

## Beste praktijken {#best-practice}

Of u de regels van de Activiteit voor het eerst bepaalt of enkel het herzien van de regels van de Activiteit die eerder opstelling zijn geweest, houd de volgende beste praktijken in mening.

* Eenvoudig starten
   * Identificeer een paar zeer belangrijke types van Activiteiten die u in uw [!DNL Marketo Measure] gegevens wilt opnemen, dan voeg meer types toe aangezien u comfortabel met wordt hoe deze touchpoints worden toegewezen
   * Zoals vermeld, is het primaire gebruiksgeval van deze eigenschap touchpoints te creëren die de doeltreffendheid van uw team van de Ontwikkeling van de Verkoop, specifiek de Uitgaande Vraag van de Telefoon en Uitgaande E-mail volgen

>[!NOTE]
>
>Het wordt **NIET** geadviseerd om de Activiteiten van de Verkoop te volgen die nadat de Kans wordt gecreeerd gebeuren, aangezien het volgen van een proces van de Uitvoering van de Verkoop niet veel insight aanbiedt. Het doel is de invloed van de Verkoop naast de invloed van de Marketing te volgen, hoofdzakelijk in de ontwikkeling van een nieuwe Kans/pijpleiding productie

* Gebruik geen formulervelden om uw regels te definiëren
* Specifieke en nauwkeurige regels maken
   * De drempel voor het creëren van een aanraakpunt van de Activiteit zou het zelfde (of gelijkaardig) aan een vorm moeten zijn vult of campagne lidmaatschap: Reacties aan een Uitgaande E-mail of Voltooide Gesprek van de Telefoon
* Altijd nieuwe regels valideren in [!DNL Salesforce] voordat deze worden opgeslagen en verwerkt
   * Het repliceren van de regels van de Activiteit in een &quot;Taken &amp; Gebeurtenissen&quot;rapporttype geeft u een duidelijk inzicht van precies hoeveel aanraakpunten van de regel zijn
* Werken met je verkoopteam
   * Het brengen in het team dat het dichtst met uw verslagen van de Activiteit of het hulpmiddel van de verkoopenablement werkt zal ervoor zorgen u de correcte gebieden gebruikt om uw regels te bepalen

## Aanbevolen werkwijzen voor onderhoud {#best-practice-for-maintenance}

Als u de regels voor Activiteitenkenmerken ten minste twee keer per jaar controleert, weet u zeker dat de aanraakpunten voor activiteit correct en up-to-date zijn. U wilt ervoor zorgen dat deze regels geen ongewenste aanraakpunten maken die de gegevens van de koperkenmerk verwateren. Een overzicht van hoe uw regels worden bepaald zal u en uw team vertrouwen in uw Attributie van Activiteiten en zijn rol in uw [!DNL Marketo Measure] gegevens helpen voelen.

Andere redenen die kunnen leiden tot een herziening van de activiteitenregels zijn onder meer...

* Omzet in uw marketingteam
* Wijzigingen in velden die worden gebruikt om uw activiteitenrecords te definiëren
* Wijzigingen of updates van de tools voor verkoopactivering

>[!MORELIKETHIS]
>
>* [ Attributie van Activiteiten ](/help/advanced-features/activities-attribution/salesforce-activities-attribution.md)
>* [ Veelgestelde vragen van de Attributie van de Activiteiten van de Verkoop ](/help/advanced-features/activities-attribution/activities-attribution-faq.md)
