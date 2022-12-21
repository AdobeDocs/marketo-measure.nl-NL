---
unique-page-id: 27656735
description: Overzicht - [!DNL Marketo Measure] - Productdocumentatie
title: Overzicht
exl-id: 2076521c-b579-457c-ab1c-263b1da4dd89
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 0%

---

# Overzicht {#overview}

De [!DNL Marketo Measure] de toepassing steunt slechts één enkele munt (verondersteld om USD te zijn), terwijl wij weten en ons ervan bewust zijn dat wij klanten over de hele wereld hebben die over hun eigen bedrijf en gebruikersvaluta moeten rapporteren. Deze eigenschap bouwt in de capaciteit voor gebruikers om tussen verschillende valuta te schakelen wanneer zij of gemelde uitgaven of verkoopopbrengst bekijken.

## Beschikbaarheid {#availability}

Niveau 2 en hoger.

## Vereisten {#requirements}

In [!DNL Salesforce], moet de klant Meerdere valuta&#39;s activeren hebben ingeschakeld. De klant kan desgewenst ook &quot;Ja, ik wil Geavanceerd valutabeheer inschakelen.&quot;

In Dynamiek, kan de klant statische wisselkoersen in hun Montages voor veelvoudige valuta plaatsen. Er is geen concept van &quot;geavanceerd valutabeheer&quot; in Dynamics.

## Voorwaarden {#terms}

| **Term** | Beschrijving |
|---|---|
| **Geavanceerde valuta** | De klant heeft Advanced Currency Management en Multiple Currencies ingeschakeld, wat betekent dat ze verschillende conversietarieven kunnen hebben voor verschillende tijdsperiodes. |
| **Zakelijke valuta** | Dit zijn de verschillende valuta&#39;s die door een organisatie in de BCR worden vermeld en gedeclareerd, allemaal met omrekeningskoersen. [!DNL Marketo Measure] Deze waarden importeren en deze valuta&#39;s beschikbaar stellen voor gebruikers in ons product. |
| **Landinstelling valuta** | De enige munt die voor een organisatie wordt gebruikt, die op de pagina van de Informatie van het Bedrijf wordt geplaatst. |
| **Lokale valuta (of Gebruikersprijs)** | De valuta die voor één gebruiker is ingesteld in het gebruikersprofiel, zodat deze elk bedrag in de eigen lokale valuta kan bekijken. De organisatie moet de valuta aangeven en instellen voordat een gebruiker zijn lokale valuta kan selecteren. |
| **Enkele valuta** | Wordt gebruikt voor klanten die geen Meerdere valuta&#39;s gebruiken in de CRM, maar die hun organisatie uitvoeren in een andere valuta, zodat ze een &quot;Valuta-landinstelling&quot; hebben. Dit is nog steeds een gemeenschappelijke munt voor de organisatie, maar zonder enige conversie. |
| **Eenvoudige valuta** | De klant heeft Meerdere valuta&#39;s ingeschakeld, maar heeft een statische omrekeningskoers per valuta. |
