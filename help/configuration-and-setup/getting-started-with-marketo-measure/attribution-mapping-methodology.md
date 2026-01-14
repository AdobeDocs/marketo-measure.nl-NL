---
description: Richtlijnen voor toewijzingsmethode voor Marketo Measure-gebruikers
title: Methodologie voor toewijzing van kenmerken
exl-id: 4d54dd20-9a82-4b87-8908-ced2bd9c0f2f
feature: Attribution
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 0%

---

# Methodologie voor toewijzing van kenmerken {#attribution-mapping-methodology}

De Methodologie van de Toewijzing van de attributen is het proces om bepaalde voorwerpen in uw CRM (Contacten, Kansen, Rekeningen) op te zoeken om attributie te creëren aanraakpunten in de bijbehorende kans. Met andere woorden, het is de [!DNL Marketo Measure] manier om te begrijpen welke aanraakpunten in het attributiemodel moeten worden opgenomen op basis van de processen van uw huidige CRM.

## Toewijzing account-id {#account-id-mapping}

Uit het vak, geeft [!DNL Marketo Measure] de toewijzing van de account-id weer. Dit betekent dat [!DNL Marketo Measure] naar de marketing-informatie van de Rekening en zijn Contacten kijkt om Attribution Touchpoints tot stand te brengen verbonden aan de kans. Hieronder volgt een eenvoudige weergave van dat proces.

![](assets/adobe-setup-1.png)

Houd in mening dat **niet alle** aanraakpunten van uw contacten in de Kans als Aanraakpunten van de Attributie worden geduwd. De tijdlijn van de Kans (zijn eerste aanrakingsdatum - gesloten datum) bepaalt of een aanraakpunt als beïnvloeding op de Kans telt. Daarom als een aanraakpunt op Contact A voorkwam nadat de Kans Won/Verloren wordt gesloten, zal [!DNL Marketo Measure] niet dat aanraakpunt aan de Kans duwen. Deze tijdlijnprocedure wordt gevolgd voor alle andere toewijzingen van toewijzingsobjecten.

Pros: Deze methode van toerekening is zeer effectief voor de meeste ondernemingen. Het marketing team te hoeven niet op het verkoopteam vertrouwen om alle contacten aan een bepaalde kans (die vaak een kwestie is) te associëren. Verder, zelfs als een verkoopteam contactrollen associeert, kunnen vele andere interactie van het contact met marketing materialen worden gemist. Tot slot biedt deze methode een ABM-strategie die erop gericht is het geheel van een rekening te beïnvloeden in plaats van specifieke invloeden.

Cons: Als er sterke Marketing &amp; Verkoop SLAs zijn die bepalen wie krediet voor wat zou moeten krijgen, dan zou deze methode problematisch kunnen zijn. Bovendien als de mensen niet de hiërarchieën van de Rekening gebruiken om specifieke bedrijfseenheden binnen een grotere rekening (zoals IBM) te bepalen, dan kunnen de marketing interactie specifiek voor één bedrijfseenheid over andere kansen van de bedrijfseenheid worden verspreid.

## Roltoewijzing opportunity-contactpersoon {#opportunity-contact-role-mapping}

Terwijl de meeste cliënten de afbeelding van identiteitskaart van de Rekening gebruiken, [!DNL Marketo Measure] kan tot de contactrollen (contacten verbonden aan de Kans) binnen een Kans opzoeken om het attributieproces te verdelen. Dit betekent dat [!DNL Marketo Measure] alleen marketinginteracties zal uitvoeren die zijn gekoppeld aan de contactrollen bij Opportunity als aanraakpunten voor koperkenmerken. Hieronder ziet u een voorstelling van dit proces.

![](assets/adobe-setup-2.png)

Pros: Als uw team een duidelijk gedefinieerd proces van contactrollen heeft, kan dit type van attributie afbeelding ideaal voor u zijn. Het helpt verkoop en marketing een beetje meer richten aangezien iedereen volledig zou begrijpen hoe de attributie wordt verdeeld. Dit proces is ook nuttig wanneer de organisaties zich richten op veelvoudige bedrijfseenheden binnen een groot bedrijf en wanneer zij verschillende producten tezelfdertijd verkopen.

Cons: Nochtans, als er geen proces van de contactrol bestaat, verliest de marketing veel marketing gegevens en het team zal uiteindelijk veel minder krediet voor hun marketing inspanningen ontvangen die kansen beïnvloeden.

## Roltoewijzing primaire contactpersoon opportunity {#opportunity-primary-contact-role-mapping}

Naast het eenvoudig bekijken van de contactrollen op de kans, kan [!DNL Marketo Measure] zich nog meer concentreren om slechts de Primaire Contacten op een Kans te bekijken. Met deze opstelling in mening, [!DNL Marketo Measure] krijgt slechts het marketing aanraakpunt verbonden aan de primaire contacten op een kans en duwt die informatie in het attributieverhaal van die specifieke kans. Zie de onderstaande afbeelding.

![](assets/adobe-setup-3.png)

Pros: Als uw team slechts in het begrijpen van de marketing invloed op contacten geinteresseerd is die als &quot;primair&quot;op de kans worden geplaatst, past dit type van afbeelding het team het best.

Cons: Dit is zeker het minst gebruikte kaartproces en kan marketinginvloed sterk ondermijnen die de naald over andere contacten op een kans verplaatst.
