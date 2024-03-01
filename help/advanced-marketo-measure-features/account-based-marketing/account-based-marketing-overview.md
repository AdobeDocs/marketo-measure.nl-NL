---
unique-page-id: 18874730
description: Meer informatie over Account-Based Marketing (ABM) en hoe Adobe Marketo Measure marketingteams en verkoopteams helpt succesvolle ABM-strategieën uit te voeren.
title: Overzicht van accountgebaseerde marketing
exl-id: 2ead69c0-66da-439d-a0ba-25c73c4b308c
feature: Account-based Marketing
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 0%

---

# Overzicht van accountgebaseerde marketing {#account-based-marketing-overview}

De volgende secties geven een kort overzicht van ABM, de componenten van de [!DNL Marketo Measure] ABM-functie en hoe u deze aan uw [!DNL Salesforce] pagina-indeling. Raadpleeg de Adobe voor meer informatie over ABM [ABM-blog](https://business.adobe.com/blog/basics/account-based-marketing){target="_blank"}.

Voor gedetailleerde instructies voor het instellen van ABM in uw [!DNL Salesforce] -instantie, ga naar [ABM-paginalay-out instellen in Salesforce](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md#setting-up-abm-page-layout-in-salesforce){target="_blank"}.

## Wat is ABM {#what-is-abm}

Op account gebaseerde marketing, ABM, is een marketingstrategie waarbij je je richt op en verkoopt aan bedrijven en rekeningen als geheel, niet alleen als individuen. [!DNL Marketo Measure] helpt Marketing- en verkoopteams succesvolle ABM-strategieën uitvoeren met de functionaliteit voor het toewijzen van leads aan accounts en de voorspellende betrokkenheidsscore.

Als u wilt dat ons marketingmodel op basis van account uw CRM invult, [!DNL Marketo Measure] moet aan de volgende criteria worden voldaan:

* Uw CRM heeft minstens 25 Rekeningen nodig die minstens één Gesloten Kans van de Won op hen hebben, om de gemeenschappelijkheid van een &quot;succesvolle&quot;Rekening/Kans aan uw zaken beter te meten.
* Aan de andere kant van de munt heeft uw CRM minstens 25 Accounts nodig zonder gesloten won Opportunity (alle opps moeten ofwel in de categorie &quot;Open&quot; staan, ofwel in de categorie &quot;Closed Lost&quot;) - dit helpt ons om te bepalen wat een lagere account in uw organisatie maakt.

>[!NOTE]
>
>Bovenstaande &quot;slechte&quot; rekeningen moeten ten minste twaalf maanden geopend zijn zonder dat er een &quot;closed-on&quot;-opp is geaccumuleerd; dat is de basisrichtsnoer voor de vraag of een opp voor de doeleinden van het model al dan niet stallend is.

## Toewijzing van regel naar account {#lead-to-account-mapping}

Het in kaart brengen van leads naar accounts is een cruciaal onderdeel van een effectieve ABM-benadering. Bij het in kaart brengen van lood-aan-rekening, worden de vooruitzichten, of de lood, gegroepeerd in de zelfde bedrijfsrekening aangezien zij met uw merk in dienst nemen. Dit staat u toe om aan individuen van het zelfde bedrijf op een verenigbare manier te richten en te verkopen. Er zijn geen extra [!DNL Salesforce] configuratie nodig om te kunnen profiteren van deze functie. De [!DNL Marketo Measure] Toewijzing van account met vijf verschillende methoden:

* Website naar account leiden
* E-maildomein naar website-domein van account leiden
* Bedrijfsnaam leiden naar accountnaam
* Bedrijf leiden naar accountwebsitedomein
* Overeenkomend het Domein op het E-mailadres van de Leider aan de Rekening via het E-mailadres van het Contact

>[!NOTE]
>
>Elke lead probeert overeen te komen met een account in de bovenstaande voorkeursvolgorde van methoden. Zodra een gelijke wordt gemaakt, wordt AccountId onmiddellijk geplaatst op Lood en zal niet aangepast worden gebruikend een andere methode. Als de lead al een geldige account-id heeft, wordt de lead overgeslagen.

## Predictieve betrokkenheidsscore {#predictive-engagement-score}

De [!DNL Marketo Measure] De voorspellende Score van de Betrokkenheid, of PES, is een dynamische waarde die illustreert hoe geëngageerd een bepaalde rekening met uw marketing inspanningen is. Deze score is handig voor het segmenteren van accounts die als doel moeten dienen. Het is een waardevol instrument voor het identificeren van rekeningen om zich effectiever en efficiënter te richten.

Er zijn vele componenten die in het algoritme gaan dat de ODA berekent. Recentie en leeftijd hebben een grote invloed op het veranderen van de score, samen met laatste aanraakpuntactiviteit of paginaweergaven. Het toevoegen van nieuwe contacten aan een rekening beïnvloedt ODA ook. Hieronder vindt u een lijst met een aantal ODA-inputs:

* Totaal aantal paginaweergaven van de account
* Gemiddeld aantal paginaweergaven
* Gemiddeld aantal personen op de rekening
* Leeftijd van de laatste paginaweergave
* Gemiddelde pagina van paginaweergaven
* Aantal personen op de rekening
* Specifieke belangrijke pagina&#39;s en of er in de afgelopen 30/60/90 dagen een bezoek heeft plaatsgevonden
* Als de rekening een gesloten verloren/gewonnen overeenkomst heeft
* Hoe waarschijnlijk het gesloten verloren/gewonnen is

>[!NOTE]
>
>Het is mogelijk dat u een score van &#39;N.v.t.&#39; of &#39;-&#39; (het dash-symbool) opmerkt in de Score voor voorspellende betrokkenheid voor sommige accounts.

_Een klasse van &quot;N.v.t.&quot;betekent eenvoudig dat er geen voldoende gegevens over die rekening voor het model zijn om ware kwaliteit te produceren - met meer gegevens, wordt een graad uiteindelijk gegeven._
_Een klasse van &quot;-&quot; (het streepjessymbool) betekent dat deze rekening nog door het ABM-proces moet worden verwerkt, vanwege tijdbeperkingen, af en toe gemiste processen, enzovoort. Als u van mening bent dat een account een rang moet hebben, op basis van vergelijkbare accounts of termijnen, kunt u contact opnemen met [!DNL Marketo Measure] weet._

## ABM-paginalayout instellen in [!DNL Salesforce] {#setting-up-abm-page-layout-in-salesforce}

Als u de ODA&#39;s wilt gaan gebruiken, moet u het veld ODA&#39;s en de bijbehorende lijst toevoegen aan de juiste paginalay-outs in [!DNL Salesforce].

1. Navigeren naar **[!UICONTROL Setup]** > **[!UICONTROL Customize]** > **[!UICONTROL Accounts]** > **[!UICONTROL Page Layout]**. Selecteer vervolgens de pagina-indeling die u wilt bewerken.
1. Ga naar [!UICONTROL Fields] en verplaats het veld &quot;Predictive Engagement Score&quot; naar het gedeelte Accountinformatie.

   ![](assets/1.png)

1. Tot slot ga naar [!UICONTROL Related Lists] en verplaats de verwante lijst Leads naar de pagina-indeling.

   ![](assets/2.png)

1. Ga vervolgens naar **[!UICONTROL Setup]** > **[!UICONTROL Customize]** > **[!UICONTROL Leads]** > **[!UICONTROL Page Layout]** en selecteert u de juiste paginalay-outs die u wilt bewerken.
1. Klikken **[!UICONTROL Fields]** en voeg de [!UICONTROL Account] veld waarin de pagina past.

   ![](assets/3.png)

U bent klaar!

