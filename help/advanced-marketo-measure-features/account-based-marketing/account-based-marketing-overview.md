---
unique-page-id: 18874730
description: Overzicht van marketing op basis van account - [!DNL Marketo Measure] - Productdocumentatie
title: Overzicht van accountgebaseerde marketing
exl-id: 2ead69c0-66da-439d-a0ba-25c73c4b308c
feature: Account-based Marketing
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 0%

---

# Overzicht van accountgebaseerde marketing {#account-based-marketing-overview}

Hieronder volgt een kort overzicht van ABM, de componenten van het [!DNL Marketo Measure] ABM-functie en hoe u deze aan uw [!DNL Salesforce] pagina-indeling. Kijk uit voor meer informatie over ABM [deze pagina](https://www.marketo.com/account-based-marketing/){target="_blank"}.

Ga rechtstreeks naar de instructies voor het instellen van ABM in uw [!DNL Salesforce] instantie, alstublieft [klik hier](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md#setting-up-abm-page-layout-in-salesforce){target="_blank"}.

## Wat is ABM {#what-is-abm}

Op account gebaseerde marketing, ABM, is een marketingstrategie waarbij je je richt op en verkoopt aan bedrijven en rekeningen als geheel, niet alleen als individuen. [!DNL Marketo Measure] helpt Marketing- en verkoopteams succesvolle ABM-strategieën uitvoeren met de functionaliteit voor het toewijzen van leads aan accounts en de voorspellende betrokkenheidsscore.

Als u wilt dat ons marketingmodel op basis van account uw CRM invult, [!DNL Marketo Measure] moet aan de volgende criteria worden voldaan:

* Uw CRM heeft minstens 25 Rekeningen nodig die minstens één Gesloten Kans van de Won op hen hebben, zodat kunnen wij beter de gemeenschappelijkheden van een &quot;succesvolle&quot;Rekening/Kans aan uw zaken meten.
* Aan de andere kant van de munt heeft uw CRM minstens 25 Accounts nodig zonder gesloten Won Opportunity (alle opps moeten ofwel in onze categorie &quot;Open&quot; staan, ofwel in de categorie &quot;Closed Lost&quot;. Dit helpt ons om te bepalen wat een lagere account in uw organisatie maakt.

>[!NOTE]
>
>De bovenstaande &quot;slechte&quot; rekeningen moeten minstens 12 maanden open zijn zonder een gesloten Won-opp te accumuleren; dat is ons basisrichtsnoer voor al dan niet een Opp voor de doeleinden van het model is verkocht.

## Toewijzing van regel naar account {#lead-to-account-mapping}

Het in kaart brengen van leads naar accounts is een cruciaal onderdeel van een effectieve ABM-benadering. Bij het in kaart brengen van lood-aan-rekening, worden de vooruitzichten, of de lood, gegroepeerd in de zelfde bedrijfsrekening aangezien zij met uw merk in dienst nemen. Dit staat u toe om aan individuen van het zelfde bedrijf op een verenigbare manier te richten en te verkopen. Er zijn geen extra [!DNL Salesforce] configuratie nodig om te kunnen profiteren van deze functie. De [!DNL Marketo Measure] Toewijzing van account met vijf verschillende methoden:

* Website naar account leiden
* E-maildomein naar website-domein van account leiden
* Bedrijfsnaam leiden naar accountnaam
* Bedrijf leiden naar accountwebsitedomein
* Overeenkomend het Domein op het E-mailadres van de Leider aan de Rekening via het E-mailadres van het Contact

>[!NOTE]
>
>Elke lead probeert in de bovenstaande voorkeursvolgorde van methoden te worden gekoppeld aan een account. Zodra een gelijke wordt gemaakt, wordt AccountId onmiddellijk geplaatst op Lood en zal niet aangepast worden gebruikend een andere methode. Als de lead al een geldige account-id heeft, wordt de lead overgeslagen.

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
* Hoe waarschijnlijk het zal worden gesloten verloren/gewonnen

>[!NOTE]
>
>Het is mogelijk dat u een score van &#39;N.v.t.&#39; of &#39;-&#39; (het dash-symbool) opmerkt in de Score voor voorspellende betrokkenheid voor sommige accounts.

_Een klasse van &quot;N.v.t.&quot;betekent eenvoudig dat wij nog niet voldoende gegevens op dat rekening voor ons model hebben om ware kwaliteit te produceren - met meer gegevens, zal een graad uiteindelijk worden gegeven._
_Een klasse van &quot;-&quot; (het streepjessymbool) betekent dat dit account nog niet door ons ABM-proces is verwerkt, vanwege tijdgebrek, af en toe gemiste processen, enz. Als u van mening bent dat een account een rang moet hebben, op basis van vergelijkbare accounts of termijnen, kunt u contact opnemen met [!DNL Marketo Measure] weet._

## ABM-paginalayout instellen in [!DNL Salesforce] {#setting-up-abm-page-layout-in-salesforce}

Als u de ODA&#39;s wilt gaan gebruiken, hoeft u het veld ODA&#39;s en de bijbehorende lijst gewoon toe te voegen aan de juiste paginalay-outs in [!DNL Salesforce].

1. Ga naar **[!UICONTROL Setup]** > **[!UICONTROL Customize]** > **[!UICONTROL Accounts]** > **[!UICONTROL Page Layout]**. Selecteer vervolgens de pagina-indeling die u wilt bewerken.
1. Ga naar [!UICONTROL Fields] en verplaats het veld &quot;Predictive Engagement Score&quot; naar het gedeelte Accountinformatie.

   ![](assets/1.png)

1. Tot slot ga naar [!UICONTROL Related Lists] en verplaats de verwante lijst Leads naar de pagina-indeling.

   ![](assets/2.png)

1. Ga vervolgens naar **[!UICONTROL Setup]** > **[!UICONTROL Customize]** > **[!UICONTROL Leads]** > **[!UICONTROL Page Layout]** en selecteert u de juiste paginalay-outs die u wilt bewerken.
1. Klikken **[!UICONTROL Fields]** en voeg de [!UICONTROL Account] veld waarin de pagina past.

   ![](assets/3.png)

U bent klaar!

