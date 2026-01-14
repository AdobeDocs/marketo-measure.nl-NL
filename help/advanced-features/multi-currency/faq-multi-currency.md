---
description: Richtlijnen voor veelgestelde vragen (meerdere valuta's) voor Marketo Measure-gebruikers
title: Veelgestelde vragen (meerdere valuta's)
exl-id: 1d0936fb-4e66-4877-98d2-32c678a7ef3e
feature: Multi-Currency
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 0%

---

# Veelgestelde vragen (meerdere valuta&#39;s) {#faq-multi-currency}

**Hoe weet ik welk eigenschapbeetje om toe te laten?**

Onthoud dat deze functie twee verschillende functiebits heeft. Beide bevinden zich op het tabblad [!UICONTROL General] van het gedeelte CRM in Instellingen: Meerdere valuta&#39;s en Geavanceerde valuta&#39;s. Meerdere valuta&#39;s moeten zijn ingeschakeld als de klant meer dan één valuta gebruikt, terwijl de extra functie Geavanceerde valuta&#39;s kan worden ingeschakeld als de klant de functie &quot;Geavanceerd valutabeheer&quot; van [!DNL Salesforce] gebruikt, waar de gebruiker een op tijd gebaseerd bereik voor conversiekoersen kan instellen.

Marketo Measure haalt automatisch de valutainstelling op van de CRM-afdeling van de klant. Handmatige configuratie in Marketo Measure die overeenkomt met de CRM is niet langer vereist. De valutainstelling is te vinden op de pagina &quot;Algemeen&quot; onder &quot;CRM&quot;.

**waarom geeft mijn advertentierekening me een waarschuwingsbericht?**

Er verschijnt een waarschuwingsbericht naast je advertentierekening met valuta&#39;s die vanuit een niet-ondersteunde valuta binnenkomen. Als dit gebeurt, bevatten uw dashboards tegels met het bericht &quot;Gemengde Valuta&#39;s&quot;. Wij adviseren dat u met uw Admin van CRM werkt om ervoor te zorgen deze onbekende munt een omzetting in uw CRM bevat.

**wat &quot;Gemengde Valuta&#39;s&quot;op mijn dashboardtegel betekent?**

Als je een tegel hebt met een bericht &#39;Gemengde valuta&#39;s&#39; onderaan, betekent dat dat we wat kosten hebben geïmporteerd die zijn toegewezen aan een valuta die we niet herkennen. Omdat al onze omzettingen van CRM met een daadwerkelijke omrekeningskoers moeten komen, betekent het dat uw CRM deze valuta mist. Wij adviseren dat u met uw Admin van CRM werkt om ervoor te zorgen deze onbekende munt een omzetting in uw CRM bevat.

**Hoe kan ik de &quot;Gemengde Valuta&#39;s&quot;fout bevestigen die door ongeldige die valuta&#39;s wordt veroorzaakt?**

Ons systeem werkt niet-herkende valuta&#39;s bij naar &quot;XXX&quot;. Als u Opportunity met ongeldige valuta&#39;s wilt uitsluiten, maakt u een onderdrukkingsregel op de pagina Instellingen aanraakpunt om aanraakpunten met de valuta &#39;XXX&#39; te voorkomen. Na verwerking rapporteren we alleen over bekende valuta&#39;s.

**hoe kan ik een nieuwe munt of een omrekeningskoers toevoegen?**

U kunt alleen een nieuwe valuta of conversiekoers declareren in [!DNL Salesforce] of [!DNL Dynamics] , zodat er slechts één bron van waarheid is voor deze waarden. Zodra een nieuwe valuta of conversiekoers wordt ontdekt, zal [!DNL Marketo Measure] dat downloaden en het ter beschikking stellen van u. We bieden geen ruimte om deze tarieven in te voeren.

**de munt toont niet in het correcte formaat. Hoe kan ik dit veranderen?**

We begrijpen dat sommige landen een andere manier hebben om bedragen op te maken (bijvoorbeeld 1.234.00, 1.234, 1.234). Maar we introduceren een ander niveau van complexiteit als we niet alleen de valuta van een gebruiker moeten bepalen, maar ook het land van herkomst, omdat verschillende landen en valuta&#39;s anders kunnen worden behandeld. De consistente indeling die we hebben gekozen, is 1.234.00. Dit kan niet worden gewijzigd.

**waarom kunt u niet het muntsymbool voor mijn geselecteerde munt tonen?**

[!DNL Salesforce] en [!DNL Dynamics] geven de bijbehorende bedragen weer met de 3-letterige conversiecode. Voor de consistentie worden de omgezette bedragen ook weergegeven met de 3-letterige conversiecode en niet met het symbool.

**wat mijn klant zal zien als zij toegelaten multi-munt niet hebben?**

Als de klant niet over de functie voor meerdere valuta&#39;s beschikt, wordt de landinstelling van de valuta van de klant standaard ingesteld op de CRM en worden alle ISO-codes gewijzigd die hun uitgaven en inkomsten in de bedrijfsvaluta weergeven. Als dit onjuist is en de klant een gemengd gebruik van valuta heeft, zou de oplossing zijn om te bevorderen om de multi-munteigenschap te krijgen.

**hoe beïnvloedt deze eigenschap op aanraakpunt-gebaseerde rapporten in CRM?**

Voor [!DNL Dynamics] - en [!DNL Salesforce] -klanten die alleen het standaard (niet-geavanceerde) valutamanagement gebruiken, moeten aanraakinkomstenbedragen correct worden geconverteerd, zodat CRM-rapporten naar behoren werken.

Er is helaas enige nuance voor de manier waarop dit werkt voor gebruikers van [!DNL Salesforce] Advanced Currency Management, vanwege een langdurige beperking van [!DNL Salesforce] . Het korte antwoord op &quot;wat doen we in dit geval&quot; is dat we inkomstenbedragen omzetten met behulp van de vaste tarieven die zijn gedefinieerd op het basistabblad (d.w.z. niet-geavanceerde) &quot;Currencies beheren&quot;. Met andere woorden, we negeren de gedateerde wisselkoersen geheel, ondanks het feit dat de klant gedateerde wisselkoersen heeft gedefinieerd.

Voor de geïnteresseerde lezer is dit de reden waarom het zo werkt. Onze aanraakpunten gebruiken formules om opbrengsten te berekenen (afgeleid van het bijbehorende opportuniteitsbedrag). [!DNL Salesforce] biedt native ondersteuning voor valutaomrekening voor deze berekeningen van formules, maar alleen voor hun basissmaak van valutaondersteuning. Het is onmogelijk voor ons om een formuleringsveld te definiëren dat verwijst naar de gedateerde wisselkoersen. [!DNL Salesforce] ondersteunt die mogelijkheid simpelweg niet, dus we hebben geen manier om naar de gedateerde tarieven te verwijzen in onze inkomstenberekeningen, ondanks het feit dat die gedateerde tarieven bestaan in [!DNL Salesforce] (het klinkt krankzinnig maar zo werkt het.)

**als mijn klant een werkschema gebruikte om een omgezet gebied te bevolken, hoe zouden zij dit gebied vooruit moeten gebruiken?**

Omdat onze aanbieding nu de omzettingen voor de klant zal behandelen, adviseren wij zij de werkschema&#39;s en het douanegebied verwijderen en ons toestaan om hun ruwe waarde van het Bedrag in te voeren.

>[!MORELIKETHIS]
>
>[ Meldingen van de Fout ](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"}
