---
unique-page-id: 18874718
description: Het creëren van een Mening van de Lijst van de Campagne voor  [!DNL Salesforce Campaigns]  -  [!DNL Marketo Measure]
title: Creërend een Mening van de Lijst van de Campagne voor  [!DNL Salesforce]  Campagnes
exl-id: 8c673ea3-ac24-4b3d-b67d-76888179c07a
feature: Channels
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---

# Een Campagnelijstweergave maken voor [!DNL Salesforce] -campagnes {#creating-a-campaign-list-view-for-salesforce-campaigns}

Leer hoe u een lijstweergave maakt voor de campagnes die u wilt synchroniseren met de aanraakpunten voor kopers.

>[!NOTE]
>
>Dit artikel behandelt een verouderd proces. Wij moedigen gebruikers aan om het [&#x200B; nieuwe, verbeterde in-app proces &#x200B;](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"} te gebruiken.

Met de lijstweergave Campagne die kan worden gemaakt, kunt u een &#39;go-to&#39;-locatie hebben om de velden Type en Aanraakpunten voor kopers inschakelen te bekijken en te beheren. Op deze manier weet u zeker dat al uw [!DNL Salesforce] -campagnes die uw offlinemarketingkanalen informeren, op de juiste wijze zijn ingesteld.

1. Naar tabblad Campagnes in [!DNL Salesforce] en maak een nieuwe lijstweergave
1. Geef de weergave de naam &quot;Campagnes voor synchronisatie met [!DNL Marketo Measure]&quot;.
1. We willen dat in deze lijst alleen de campagnes worden weergegeven die we met [!DNL Marketo Measure] willen synchroniseren, zodat we een paar filters nodig hebben:

   * **Type** [ EQUALS ] &quot;Alle Types van Campagne die wij aan uw off-line kanalen in kaart hebben gebracht&quot;. Verwijs naar uw Plan van de Implementatie of het Off-line lusje van Kanalen in [!DNL Marketo Measure] ([&#x200B; experience.adobe.com/marketo-measure &#x200B;](https://experience.adobe.com/marketo-measure){target="_blank"} -> Mijn Rekening -> Montages -> Off-line Kanalen). U kunt de gewenste typen selecteren via het vergrootglaspictogram (de typen die zijn toegewezen aan een offlinemarketingkanaal).

      * Kies max. 3 typen voor elk filter. Er geldt een limiet voor tekens die in een filterveld kunnen voorkomen. Begin met 3 types per filter en voeg extra rijen van &quot;Type&quot;filters indien nodig toe.

   * **creeerde Datum** [ GROTER OF GELIJK ] uw [!DNL Marketo Measure] begindatum. U vindt uw begindatum in het ROI-dashboard in de [!DNL Marketo Measure] -app. Selecteer gewoon &#39;Sinds aanmaakdatum&#39; in het datumbereik van het streepje en hierin wordt uw begindatum weergegeven.
   * **&#42;Type van Verslag&#42;** - om uit te geven in de Mening van de Lijst, moet u een filter voor het Type van Verslag toevoegen. Elk campagnerecord dat u moet bewerken, moet hetzelfde recordtype zijn.

1. Bewerk de geselecteerde velden om weer te geven in de lijstweergave. De volledige opstelling van de lijstmening zou als voorbeeld hieronder moeten kijken:

   In deze weergave kunt u uw campagnes bekijken en zo nodig de velden Type en Aanraakpunten voor kopers inschakelen. Wanneer u nieuwe campagnes maakt die moeten worden gesynchroniseerd met [!DNL Marketo Measure] , worden deze in deze weergave weergegeven en kunt u alle instellingen voor die campagnes rechtstreeks vanuit de lijst beheren.

   Als u inline-bewerkingen wilt uitvoeren vanuit de lijstweergave, moet u ervoor zorgen dat het volgende ook geldt binnen de instellingen van [!DNL Salesforce] :

   * **[!UICONTROL Setup]** > **[!UICONTROL User Interface]** > **[!UICONTROL Enable Inline Editing]**
   * Ook uitgebreide lijsten ingeschakeld (rechts onder het vak voor inline bewerken)
   * Zorg ervoor dat u beschikt over machtigingen voor de velden

>[!MORELIKETHIS]
>
>[&#x200B; het Oplossen van problemen gemeenschappelijke kwesties met de Mening Inline het Uitgeven van de Lijst &#x200B;](http://help.salesforce.com/articleView?id=000003911&language=en_US&type=1){target="_blank"}
