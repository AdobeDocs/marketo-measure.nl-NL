---
unique-page-id: 18874716
description: Methodologie voor toewijzing van kenmerken - [!DNL Marketo Measure] - Productdocumentatie
title: Methodologie voor toewijzing van kenmerken
exl-id: 4d54dd20-9a82-4b87-8908-ced2bd9c0f2f
source-git-commit: 993a326c377b3b6ff48c4e0114b59297f9ca2ca6
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 0%

---

# Methodologie voor toewijzing van kenmerken {#attribution-mapping-methodology}

De Methodologie van de Toewijzing van de attributen is het proces om bepaalde voorwerpen in uw CRM (Contacten, Kansen, Rekeningen) op te zoeken om attributie te creëren aanraakpunten in de bijbehorende kans. Met andere woorden, het is [!DNL Marketo Measure] een manier om te begrijpen welke aanraakpunten in het attributiemodel moeten worden opgenomen op basis van de processen van uw huidige CRM.

## Toewijzing account-id {#account-id-mapping}

Uit de doos, [!DNL Marketo Measure] biedt toewijzing van account-id. Dit betekent dat [!DNL Marketo Measure] bekijkt de de marketing van de Rekening en zijn Contacten informatie om de Aanraakpunten van de Attributie tot stand te brengen verbonden aan de kans. Hieronder volgt een eenvoudige weergave van dat proces.

![](assets/1-1.png)

Houd er rekening mee dat **niet alles** De aanraakpunten van uw contacten zullen in de Kans als Aanraakpunten van de Attributie worden geduwd. De tijdslijn van de Kans (het is eerste aanrakingsdatum - gesloten datum) zal bepalen of een aanraakpunt als beïnvloedende factor op de Kans zal tellen. Daarom als een aanraakpunt op Contact A voorkwam nadat de Kans Gewonnen/Verloren wordt gesloten, [!DNL Marketo Measure] zal dat aanraakpunt niet naar de Opportunity duwen. Deze tijdlijnprocedure wordt gevolgd voor alle andere toewijzingen van toewijzingsobjecten.

Pros: Deze methode van toerekening is zeer effectief voor de meeste ondernemingen. Het marketing team te hoeven niet op het verkoopteam vertrouwen om alle contacten aan een bepaalde kans (die vaak een kwestie is) te associëren. Bovendien, zelfs als een verkoopteam contactrollen associeert, kunnen veel interactie van andere contact met marketing materialen worden gemist. Tot slot biedt deze methode ABM-strategieën die de gehele rekening willen beïnvloeden in plaats van specifieke invloedrijke factoren.

Cons: Als er sterke Marketing &amp; Verkoop SLAs zijn die bepalen wie krediet voor wat zou moeten krijgen, dan zou deze methode problematisch kunnen zijn. Bovendien als de mensen de hiërarchieën van de Rekening niet gebruiken om specifieke bedrijfseenheden binnen een grotere rekening te bepalen (bijvoorbeeld: IBM), dan kunnen de marketing interacties specifiek voor één bedrijfseenheid over andere mogelijkheden van de bedrijfseenheid worden verspreid.

## Roltoewijzing opportunity-contactpersoon {#opportunity-contact-role-mapping}

Terwijl de meeste clients gebruikmaken van accountid-toewijzing, [!DNL Marketo Measure] heeft de capaciteit om omhoog aan de contactrollen (contacten verbonden aan de Kans) binnen een Kans te kijken om het attributieproces te breken. Dit betekent dat [!DNL Marketo Measure] alleen marketinginteracties uitvoeren die zijn gekoppeld aan de contactrollen bij Opportunity als aanraakpunten voor koperkenmerken. Hieronder ziet u een voorstelling van dit proces.

![](assets/2-1.png)

Pros: Als uw team een zeer duidelijk bepaald proces van contactrollen heeft, kan dit type van attributie afbeelding ideaal voor u zijn. Het zal helpen verkoop en marketing een beetje meer richten aangezien iedereen volledig zou begrijpen hoe de attributie wordt verdeeld. Dit proces is ook zeer nuttig wanneer de organisaties zich richten op veelvoudige bedrijfseenheden binnen een groot bedrijf evenals wanneer zij verschillende producten tezelfdertijd verkopen.

Cons: Nochtans, als er geen proces van de contactrol in werking is, zal marketing veel marketing gegevens verliezen en het team zal uiteindelijk veel minder krediet voor hun marketing inspanningen ontvangen die kansen beïnvloeden.

## Roltoewijzing primaire contactpersoon opportunity {#opportunity-primary-contact-role-mapping}

Naast het eenvoudig bekijken van de contactrollen op de kans, [!DNL Marketo Measure] kan zich nog meer richten om slechts de Primaire Contacten op een Kans te bekijken. Met deze instelling in gedachten, [!DNL Marketo Measure] zal slechts het marketing aanraakpunt verbonden aan de primaire contacten op een kans grijpen en zal die informatie in het attributieverhaal van die specifieke kans duwen. Zie de onderstaande afbeelding.

![](assets/3.png)

Pros: Als uw team slechts in het begrijpen van de marketing invloed op contacten geinteresseerd is die als &quot;primair&quot;op de kans worden geplaatst, zal dit type van afbeelding het team het best aanpassen.

Cons: Dit is zeker het minst gebruikte kaartproces en kan in hoge mate invloed op de marketing ondermijnen die de naald over andere contacten op een kans bewegen.
