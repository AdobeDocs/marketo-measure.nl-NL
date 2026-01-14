---
description: Overzicht van richtlijnen voor Marketo Measure-gebruikers
title: Overzicht
exl-id: 2076521c-b579-457c-ab1c-263b1da4dd89
feature: Multi-Currency
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 1%

---

# Overzicht {#overview}

De toepassing [!DNL Marketo Measure] ondersteunt momenteel slechts één munt (verondersteld om USD te zijn), terwijl we weten en ons ervan bewust zijn dat we klanten over de hele wereld hebben die moeten rapporteren over hun eigen zakelijke en gebruikersvaluta. Met deze functie kunnen gebruikers schakelen tussen dezelfde valuta&#39;s die in hun CRM worden gebruikt bij het bekijken van gemelde uitgaven of verkoopopbrengsten in [!DNL Marketo Measure] .

## Beschikbaarheid {#availability}

Niveau 2 en hoger.

## Vereisten {#requirements}

[!DNL Marketo Measure] haalt de valutainstelling automatisch uit de CRM-instellingen van de klant. Handmatige configuratie in [!DNL Marketo Measure] die overeenkomt met de CRM is niet langer vereist. De valutainstelling is te vinden op de pagina &quot;Algemeen&quot; onder &quot;CRM&quot;.

In [!DNL Salesforce] moet de klant de optie Meerdere valuta&#39;s activeren hebben ingeschakeld. De klant kan desgewenst ook &quot;Ja, ik wil Geavanceerd valutabeheer inschakelen.&quot;

In Dynamiek, kan de klant statische wisselkoersen in hun Montages voor veelvoudige valuta plaatsen. Er is geen concept van &quot;geavanceerd valutabeheer&quot; in Dynamics.

## Voorwaarden {#terms}

| **Term** | Beschrijving |
|---|---|
| **Geavanceerde Munt** | De klant heeft Advanced Currency Management en Multiple Currencies ingeschakeld, wat betekent dat ze verschillende conversietarieven kunnen hebben voor verschillende tijdsperiodes. |
| **Collectieve Valuta** | Dit zijn de verschillende valuta&#39;s die door een organisatie in de BCR worden vermeld en gedeclareerd, allemaal met omrekeningskoersen. [!DNL Marketo Measure] importeert deze waarden en stelt deze valuta&#39;s beschikbaar voor gebruikers in ons product. |
| **Scène van de Valuta** | De enige munt die voor een organisatie wordt gebruikt, die op de pagina van de Informatie van het Bedrijf wordt geplaatst. |
| **Lokale Valuta (of de Valuta van de Gebruiker)** | De valuta die voor één gebruiker is ingesteld in het gebruikersprofiel, zodat deze elk bedrag in de eigen lokale valuta kan bekijken. De organisatie moet de valuta aangeven en instellen voordat een gebruiker zijn lokale valuta kan selecteren. |
| **Enige Munt** | Wordt gebruikt voor klanten die geen Meerdere valuta&#39;s gebruiken in de CRM, maar die hun organisatie uitvoeren in een andere valuta, zodat ze een &quot;Valuta-landinstelling&quot; hebben. Dit is nog steeds een gemeenschappelijke munt voor de organisatie, maar zonder enige conversie. |
| **Eenvoudige Munt** | De klant heeft Meerdere valuta&#39;s ingeschakeld, maar heeft een statische omrekeningskoers per valuta. |
