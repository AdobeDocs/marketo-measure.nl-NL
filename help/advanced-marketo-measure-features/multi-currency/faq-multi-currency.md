---
unique-page-id: 27656745
description: Veelgestelde vragen (meerdere valuta) - [!DNL Marketo Measure] - Productdocumentatie
title: Veelgestelde vragen (meerdere valuta's)
exl-id: 1d0936fb-4e66-4877-98d2-32c678a7ef3e
feature: Multi-Currency
source-git-commit: b7aea1e0789b2f4f3fd4b250c0f66595618317bb
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 0%

---

# Veelgestelde vragen (meerdere valuta&#39;s) {#faq-multi-currency}

**Hoe weet ik welke functiebit moet worden ingeschakeld?**

Onthoud dat deze functie twee verschillende functiebits heeft. Beide bevinden zich op het tabblad Algemeen van het gedeelte CRM in Instellingen: Meerdere valuta&#39;s en Geavanceerde valuta&#39;s. Meerdere valuta&#39;s moeten zijn ingeschakeld als de klant meer dan één valuta gebruikt, terwijl de extra functie Geavanceerde valuta&#39;s kan inschakelen als de klant deze gebruikt [!DNL Salesforce]&#39;s &#39;Advanced Currency Management&#39; functie waar de gebruiker een op tijd gebaseerd bereik voor conversiekoersen kan instellen.

Helaas weten we niet wanneer een klant schakelt tussen Eenvoudig of Geavanceerd als Geavanceerd al is ingeschakeld. Daarom moet de klant de instelling Geavanceerde valuta&#39;s handmatig op hun CRM-instelling uitlijnen. Dit zou aan de klant moeten duidelijk zijn als de omzettingen onjuist zijn, wat betekent wij niet wisten welk niveau van omzetting van toepassing was.

**Waarom geeft mijn advertentieaccount me een waarschuwingsbericht?**

Er verschijnt een waarschuwingsbericht naast je advertentierekening met valuta&#39;s die vanuit een niet-ondersteunde valuta binnenkomen. Als dit gebeurt, bevatten uw dashboards tegels met het bericht &quot;Gemengde Valuta&#39;s&quot;. Wij adviseren dat u met uw Admin van CRM werkt om ervoor te zorgen deze onbekende munt een omzetting in uw CRM bevat.

**Wat betekent &quot;Gemengde Valuta&#39;s&quot; op mijn dashboardblok?**

Als je een tegel hebt met een bericht &#39;Gemengde valuta&#39;s&#39; onderaan, betekent dat dat we wat kosten hebben geïmporteerd die zijn toegewezen aan een valuta die we niet herkennen. Omdat al onze omzettingen van CRM met een daadwerkelijke omrekeningskoers moeten komen, betekent het dat uw CRM deze valuta mist. Wij adviseren dat u met uw Admin van CRM werkt om ervoor te zorgen deze onbekende munt een omzetting in uw CRM bevat.

**Hoe kan ik een nieuwe valuta of omrekeningskoers toevoegen?**

Een nieuwe munteenheid of een nieuwe omrekeningskoers kan alleen worden aangegeven in [!DNL Salesforce] of [!DNL Dynamics] zodat er slechts één bron van waarheid voor deze waarden is. Zodra een nieuwe valuta of omrekeningskoers wordt ontdekt, [!DNL Marketo Measure] zal dat downloaden en beschikbaar stellen aan u. We bieden geen ruimte om deze tarieven in te voeren.

**De valuta wordt niet in de juiste notatie weergegeven. Hoe kan ik dit veranderen?**

We begrijpen dat sommige landen een andere manier hebben om bedragen op te maken (bijvoorbeeld 1.234.00, 1.234, 1.234). Maar we introduceren een ander niveau van complexiteit als we niet alleen de valuta van een gebruiker moeten bepalen, maar ook het land van herkomst, omdat verschillende landen en valuta&#39;s anders kunnen worden behandeld. De consistente indeling die we hebben gekozen, is 1.234.00. Dit kan niet worden gewijzigd.

**Waarom kunt u het valutasymbool voor mijn geselecteerde valuta niet weergeven?**

[!DNL Salesforce] en [!DNL Dynamics] hun bedragen weergeven met de 3-letterige omzettingscode. Voor de consistentie worden de omgezette bedragen ook weergegeven met de 3-letterige conversiecode en niet met het symbool.

**Wat zal mijn klant zien als zij geen toegelaten multi-munt hebben?**

Als de klant niet over de functie voor meerdere valuta&#39;s beschikt, wordt de landinstelling van de valuta van de klant standaard ingesteld op de CRM en worden alle ISO-codes gewijzigd die hun uitgaven en inkomsten in de bedrijfsvaluta weergeven. Als dit onjuist is en de klant een gemengd gebruik van valuta heeft, zou de oplossing zijn om te bevorderen om de multi-munteigenschap te krijgen.

**Hoe beïnvloedt deze eigenschap touchpoint-based rapporten in CRM?**

Voor [!DNL Dynamics] en [!DNL Salesforce] klanten die alleen het elementaire (niet-geavanceerde) valutamanagement gebruiken, moeten de bedragen van de inkomsten uit aanraakpunten correct worden geconverteerd, zodat CRM-rapporten naar verwachting werken.

Er is helaas enige nuance over hoe dit werkt voor gebruikers van [!DNL Salesforce] Geavanceerd beheer van valuta&#39;s vanwege een reeds lang bestaande beperking van [!DNL Salesforce]. Het korte antwoord op &quot;wat doen we in dit geval&quot; is dat we inkomstenbedragen omzetten met behulp van de vaste tarieven die zijn gedefinieerd op het basistabblad (d.w.z. niet-geavanceerde) &quot;Currencies beheren&quot;. Met andere woorden, we negeren de gedateerde wisselkoersen geheel, ondanks het feit dat de klant gedateerde wisselkoersen heeft gedefinieerd.

Voor de geïnteresseerde lezer is dit de reden waarom het zo werkt. Onze aanraakpunten gebruiken formules om opbrengsten te berekenen (afgeleid van het bijbehorende opportuniteitsbedrag). [!DNL Salesforce] native ondersteunt valutaomrekening voor deze formule-berekeningen, maar alleen voor hun basiskenmerk van valutaondersteuning. Het is onmogelijk voor ons om een formuleringsveld te definiëren dat verwijst naar de gedateerde wisselkoersen. [!DNL Salesforce] Dat vermogen wordt eenvoudigweg niet ondersteund, dus we hebben geen mogelijkheid om de gedateerde percentages in onze inkomstenberekeningen te gebruiken, ondanks het feit dat deze gedateerde tarieven bestaan in [!DNL Salesforce] (Het klinkt gek, maar zo werkt het.)

**Als mijn klant een workflow heeft gebruikt om een geconverteerd veld te vullen, hoe moeten ze dit veld dan verder gebruiken?**

Omdat onze aanbieding nu de omzettingen voor de klant zal behandelen, adviseren wij zij de werkschema&#39;s en het douanegebied verwijderen en ons toestaan om hun ruwe waarde van het Bedrag in te voeren.

>[!MORELIKETHIS]
>
>[Foutmeldingen](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"}
