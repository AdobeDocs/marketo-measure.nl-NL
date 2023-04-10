---
unique-page-id: 27656735
description: Overzicht - [!DNL Marketo Measure] - Productdocumentatie
title: Overzicht
exl-id: 2076521c-b579-457c-ab1c-263b1da4dd89
source-git-commit: bf047695c4ea82c4fbf1e9079b7443a5c9821e42
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 0%

---

# Overzicht {#overview}

De [!DNL Marketo Measure] de toepassing steunt slechts één enkele munt (verondersteld om USD te zijn), terwijl wij weten en ons ervan bewust zijn dat wij klanten over de hele wereld hebben die over hun eigen bedrijf en gebruikersvaluta moeten rapporteren. Met deze functie kunnen gebruikers schakelen tussen dezelfde valuta&#39;s die in hun CRM worden gebruikt bij het bekijken van gerapporteerde uitgaven of omzet in [!DNL Marketo Measure].

## Beschikbaarheid {#availability}

Niveau 2 en hoger.

## Vereisten {#requirements}

[!DNL Marketo Measure] zal automatisch de valuta-instelling van de CRM van de klant trekken. Handmatige configuratie in [!DNL Marketo Measure] om de CRM aan te passen is niet langer vereist. De valutainstelling is te vinden op de pagina &quot;Algemeen&quot; onder &quot;CRM&quot;.

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
