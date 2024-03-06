---
unique-page-id: 18874716
description: Methodologie voor toewijzing van kenmerken - [!DNL Marketo Measure]
title: Methodologie voor toewijzing van kenmerken
exl-id: 4d54dd20-9a82-4b87-8908-ced2bd9c0f2f
feature: Attribution
source-git-commit: cd5597a681f388a5b5c743dadd38bf3127811bff
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 0%

---

# Methodologie voor toewijzing van kenmerken {#attribution-mapping-methodology}

De Methodologie van de Toewijzing van de attributen is het proces om bepaalde voorwerpen in uw CRM (Contacten, Kansen, Rekeningen) op te zoeken om attributie te creëren aanraakpunten in de bijbehorende kans. Met andere woorden, het is de [!DNL Marketo Measure] een manier om te begrijpen welke aanraakpunten in het attributiemodel moeten worden opgenomen op basis van de processen van uw huidige CRM.

## Toewijzing account-id {#account-id-mapping}

Uit de doos, [!DNL Marketo Measure] biedt toewijzing van account-id. Dit betekent dat [!DNL Marketo Measure] bekijkt de de marketing van de Rekening en zijn Contacten informatie om de Aanraakpunten van de Attributie tot stand te brengen verbonden aan de kans. Hieronder volgt een eenvoudige weergave van dat proces.

![](assets/1-1.png)

Houd er rekening mee dat **niet alles** De touchpoints van uw contacten worden geduwd in de Kans als Aanraakpunten van de Attributie. De tijdlijn van de Kans (zijn eerste aanrakingsdatum - gesloten datum) bepaalt of een aanraakpunt als beïnvloeding op de Kans telt. Daarom als een aanraakpunt op Contact A voorkwam nadat de Kans Gewonnen/Verloren wordt gesloten, [!DNL Marketo Measure] zal dat aanraakpunt niet naar de Opportunity duwen. Deze tijdlijnprocedure wordt gevolgd voor alle andere toewijzingen van toewijzingsobjecten.

Pros: Deze methode van toerekening is zeer effectief voor de meeste ondernemingen. Het marketing team te hoeven niet op het verkoopteam vertrouwen om alle contacten aan een bepaalde kans (die vaak een kwestie is) te associëren. Verder, zelfs als een verkoopteam contactrollen associeert, kunnen vele andere interactie van het contact met marketing materialen worden gemist. Tot slot biedt deze methode een ABM-strategie die erop gericht is het geheel van een rekening te beïnvloeden in plaats van specifieke invloeden.

Cons: Als er sterke Marketing &amp; Verkoop SLAs zijn die bepalen wie krediet voor wat zou moeten krijgen, dan zou deze methode problematisch kunnen zijn. Bovendien als de mensen niet de hiërarchieën van de Rekening gebruiken om specifieke bedrijfseenheden binnen een grotere rekening (zoals IBM) te bepalen, dan kunnen de marketing interactie specifiek voor één bedrijfseenheid over andere kansen van de bedrijfseenheid worden verspreid.

## Roltoewijzing opportunity-contactpersoon {#opportunity-contact-role-mapping}

Terwijl de meeste clients gebruikmaken van accountid-toewijzing, [!DNL Marketo Measure] kan tot de contactrollen (contacten verbonden aan de Kans) binnen een Kans opzoeken om het attributieproces te breken. Dit betekent dat [!DNL Marketo Measure] alleen marketinginteracties uitvoeren die zijn gekoppeld aan de contactrollen bij Opportunity als aanraakpunten voor koperkenmerken. Hieronder ziet u een voorstelling van dit proces.

![](assets/2-1.png)

Pros: Als uw team een duidelijk gedefinieerd proces van contactrollen heeft, kan dit type van attributie afbeelding ideaal voor u zijn. Het helpt verkoop en marketing een beetje meer richten aangezien iedereen volledig zou begrijpen hoe de attributie wordt verdeeld. Dit proces is ook nuttig wanneer de organisaties zich richten op veelvoudige bedrijfseenheden binnen een groot bedrijf en wanneer zij verschillende producten tezelfdertijd verkopen.

Cons: Nochtans, als er geen proces van de contactrol bestaat, verliest de marketing veel marketing gegevens en het team zal uiteindelijk veel minder krediet voor hun marketing inspanningen ontvangen die kansen beïnvloeden.

## Roltoewijzing primaire contactpersoon opportunity {#opportunity-primary-contact-role-mapping}

Naast het eenvoudig bekijken van de contactrollen op de kans, [!DNL Marketo Measure] kan zich nog meer richten om slechts de Primaire Contacten op een Kans te bekijken. Met deze instelling in gedachten, [!DNL Marketo Measure] alleen haalt het marketingaanraakpunt dat aan de primaire contactpersonen is gekoppeld, op een opportuniteit over en duwt die informatie in het attributieverhaal van die specifieke opportuniteit. Zie de onderstaande afbeelding.

![](assets/3.png)

Pros: Als uw team slechts in het begrijpen van de marketing invloed op contacten geinteresseerd is die als &quot;primair&quot;op de kans worden geplaatst, past dit type van afbeelding het team het best.

Cons: Dit is zeker het minst gebruikte kaartproces en kan marketinginvloed sterk ondermijnen die de naald over andere contacten op een kans verplaatst.
