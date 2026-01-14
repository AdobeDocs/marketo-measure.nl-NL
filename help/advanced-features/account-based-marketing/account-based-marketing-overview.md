---
description: Meer informatie over Account-Based Marketing (ABM) en hoe Adobe Marketo Measure marketing- en verkoopteams succesvolle ABM-strategieën kan uitvoeren.
title: Overzicht van accountgebaseerde marketing
exl-id: 2ead69c0-66da-439d-a0ba-25c73c4b308c
feature: Account-based Marketing
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 0%

---

# Overzicht van accountgebaseerde marketing {#account-based-marketing-overview}

In de volgende secties vindt u een kort overzicht van ABM, de componenten van de functie [!DNL Marketo Measure] ABM en hoe u deze kunt toevoegen aan de pagina-indeling van [!DNL Salesforce] . Om meer over ABM te lezen, herzie Adobe [ ABM blog ](https://business.adobe.com/blog/basics/account-based-marketing){target="_blank"}.

Voor gedetailleerde instructies voor vestiging ABM binnen uw [!DNL Salesforce] instantie, ga [ Vestiging ABM paginalay-out in Salesforce ](/help/advanced-features/account-based-marketing/account-based-marketing-overview.md#setting-up-abm-page-layout-in-salesforce){target="_blank"}.

## Wat is ABM {#what-is-abm}

Op account gebaseerde marketing, ABM, is een marketingstrategie waarbij je je richt op en verkoopt aan bedrijven en rekeningen als geheel, niet alleen als individuen. Met [!DNL Marketo Measure] kunnen marketing- en verkoopteams succesvolle ABM-strategieën uitvoeren met de functionaliteit voor het toewijzen van leads aan accounts en de voorspellende betrokkenheidsscore.

Als u wilt dat ons marketingmodel op basis van account uw CRM invult, moet u in [!DNL Marketo Measure] aan de volgende criteria voldoen:

* Uw CRM heeft minstens 25 Rekeningen nodig die minstens één Gesloten Kans van de Won op hen hebben, om de gemeenschappelijkheid van een &quot;succesvolle&quot;Rekening/Kans aan uw zaken beter te meten.
* Aan de andere kant van de munt heeft uw CRM minstens 25 Accounts nodig zonder gesloten won Opportunity (alle opps moeten ofwel in de categorie &quot;Open&quot; staan, ofwel in de categorie &quot;Closed Lost&quot;) - dit helpt ons om te bepalen wat een lagere account in uw organisatie maakt.

>[!NOTE]
>
>Bovenstaande &quot;slechte&quot; rekeningen moeten ten minste twaalf maanden geopend zijn zonder dat er een &quot;closed-on&quot;-opp is geaccumuleerd; dat is de basisrichtsnoer voor de vraag of een opp voor de doeleinden van het model al dan niet stallend is.

## Toewijzing van regel naar account {#lead-to-account-mapping}

Het in kaart brengen van leads naar accounts is een cruciaal onderdeel van een effectieve ABM-benadering. Bij het in kaart brengen van lood-aan-rekening, worden de vooruitzichten, of de lood, gegroepeerd in de zelfde bedrijfsrekening aangezien zij met uw merk in dienst nemen. Dit staat u toe om aan individuen van het zelfde bedrijf op een verenigbare manier te richten en te verkopen. Er is geen aanvullende [!DNL Salesforce] -configuratie nodig om te profiteren van deze functie. De verschillende methoden voor het toewijzen van leads aan accounts in [!DNL Marketo Measure] :

* Website naar account leiden
* E-maildomein naar website-domein van account leiden
* Bedrijfsnaam leiden naar accountnaam
* Bedrijf leiden naar accountwebsitedomein
* Website leiden naar het e-maildomein van contactpersonen voor account
* E-maildomein voor contactpersoon van account leiden
* Website leiden naar e-maildomein van verantwoordelijke account
* E-maildomein voor hoofd-e-maildomein van account leiden

De leads/contactpersonen van de accounts worden gevalideerd door hun e-mail-/websitedomeinen en overeenkomen met het domein of subdomein van de hoofd-e-mail/website. De account met de meeste overeenkomsten wordt gebruikt.

>[!NOTE]
>
>Elke lead probeert overeen te komen met een account in de bovenstaande voorkeursvolgorde van methoden. Zodra een gelijke wordt gemaakt, wordt AccountId onmiddellijk geplaatst op Lood en zal niet aangepast worden gebruikend een andere methode.

## Predictieve betrokkenheidsscore {#predictive-engagement-score}

De [!DNL Marketo Measure] Predictive Engagement Score, of PES, is een dynamische waarde die toont hoe betrokken een bepaalde rekening met uw marketing inspanningen is. Deze score is handig voor het segmenteren van accounts die als doel moeten dienen. Het is een waardevol instrument voor het identificeren van rekeningen om zich effectiever en efficiënter te richten.

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

_de rang van A van &quot;N.v.t.&quot;betekent eenvoudig dat er niet voldoende gegevens over die rekening voor het model zijn om een ware kwaliteit te produceren - met meer gegevens, wordt een graad uiteindelijk gegeven._
_de rang van A &quot;-&quot; (het dash symbool) betekent dat deze rekening nog door het proces ABM, wegens tijdbeperkingen, af en toe gemiste processen, etc. moet worden verwerkt. Als u van mening bent dat een account een score moet hebben, op basis van vergelijkbare accounts of tijdframes, kunt u het beste contact opnemen met [!DNL Marketo Measure] ._

## ABM-paginalayout instellen in [!DNL Salesforce] {#setting-up-abm-page-layout-in-salesforce}

Als u de ODA&#39;s wilt gaan gebruiken, moet u het veld ODA&#39;s en de lijst Verwante items toevoegen aan de juiste paginalay-outs in [!DNL Salesforce] .

1. Navigeer naar **[!UICONTROL Setup]** > **[!UICONTROL Customize]** > **[!UICONTROL Accounts]** > **[!UICONTROL Page Layout]** . Selecteer vervolgens de pagina-indeling die u wilt bewerken.
1. Ga naar [!UICONTROL Fields] en verplaats het veld &quot;Predictive Engagement Score&quot; in de sectie Accountinformatie.

   ![](assets/account-marketing-3.png)

1. Ga ten slotte naar [!UICONTROL Related Lists] en verplaats de lijst met verwante leads naar uw paginalay-out.

   ![](assets/account-marketing-4.jpg)

1. Navigeer vervolgens naar **[!UICONTROL Setup]** > **[!UICONTROL Customize]** > **[!UICONTROL Leads]** > **[!UICONTROL Page Layout]** en selecteer de gewenste paginalay-outs die u wilt bewerken.
1. Klik op **[!UICONTROL Fields]** en voeg het veld [!UICONTROL Account] toe waar u de pagina ziet passen.

   ![](assets/account-marketing-5.png)

U bent klaar!

