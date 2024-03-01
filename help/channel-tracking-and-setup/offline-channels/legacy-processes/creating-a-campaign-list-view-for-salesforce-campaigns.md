---
unique-page-id: 18874718
description: Campagneelijstweergave maken voor [!DNL Salesforce Campaigns] - [!DNL Marketo Measure]
title: Campagneelijstweergave maken voor [!DNL Salesforce] Campagnes
exl-id: 8c673ea3-ac24-4b3d-b67d-76888179c07a
feature: Channels
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---

# Campagneelijstweergave maken voor [!DNL Salesforce] Campagnes {#creating-a-campaign-list-view-for-salesforce-campaigns}

Leer hoe u een lijstweergave maakt voor de campagnes die u wilt synchroniseren met de aanraakpunten voor kopers.

>[!NOTE]
>
>Dit artikel behandelt een verouderd proces. We raden gebruikers aan de [nieuw, verbeterd proces in de app](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"}.

In de keuzelijst Campagne die u kunt maken, kunt u een &#39;go-to&#39;-locatie instellen voor het weergeven en beheren van de velden Type en Aanraakpunten voor kopers inschakelen om ervoor te zorgen dat elk van uw [!DNL Salesforce] campagnes die uw off-line marketing kanalen informeren zijn opstelling behoorlijk.

1. Kop naar tabblad Campagnes in [!DNL Salesforce] en maak een nieuwe lijstweergave
1. Geef de weergave de naam &quot;Campagnes voor synchronisatie met [!DNL Marketo Measure].&quot;
1. We willen dat deze lijst alleen de campagnes toont waarmee we willen synchroniseren [!DNL Marketo Measure] we hebben dus een paar filters nodig :

   * **Type** [EQUALS] &quot;Alle soorten campagne die wij aan uw off-line kanalen in kaart hebben gebracht&quot;. Raadpleeg het implementatieplan of het tabblad Offlinekanalen in [!DNL Marketo Measure] ([experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} -> Mijn account -> Instellingen -> Offlinekanalen). U kunt de gewenste typen selecteren via het vergrootglaspictogram (de typen die zijn toegewezen aan een offlinemarketingkanaal).

      * Kies max. 3 typen voor elk filter. Er geldt een limiet voor tekens die in een filterveld kunnen voorkomen. Begin met 3 types per filter en voeg extra rijen van &quot;Type&quot;filters indien nodig toe.

   * **Aanmaakdatum** [GROTER OF GELIJK] uw [!DNL Marketo Measure] begindatum. U kunt uw begindatum in het ROI dashboard binnen vinden [!DNL Marketo Measure] App. Selecteer gewoon &#39;Sinds aanmaakdatum&#39; in het datumbereik van het streepje en hierin wordt uw begindatum weergegeven.
   * **&#42;Recordtype&#42;** - Als u wijzigingen wilt aanbrengen in de lijstweergave, moet u een filter toevoegen voor Recordtype. Elk campagnerecord dat u moet bewerken, moet hetzelfde recordtype zijn.

1. Bewerk de geselecteerde velden om weer te geven in de lijstweergave. De volledige opstelling van de lijstmening zou als voorbeeld hieronder moeten kijken:

   In deze weergave kunt u uw campagnes bekijken en zo nodig de velden Type en Aanraakpunten voor kopers inschakelen. Terwijl u nieuwe campagnes maakt die moeten worden gesynchroniseerd met [!DNL Marketo Measure]worden weergegeven, worden ze weergegeven en u kunt alle instellingen voor die campagnes rechtstreeks vanuit de lijst beheren.

   Als u inline-bewerkingen wilt uitvoeren vanuit de lijstweergave, moet u ervoor zorgen dat het volgende ook geldt voor uw [!DNL Salesforce] instellen:

   * **[!UICONTROL Setup]** > **[!UICONTROL User Interface]** > **[!UICONTROL Enable Inline Editing]**
   * Ook uitgebreide lijsten ingeschakeld (rechts onder het vak voor inline bewerken)
   * Zorg ervoor dat u beschikt over machtigingen voor de velden

>[!MORELIKETHIS]
>
>[Problemen met algemene problemen met Inline lijstweergave oplossen](http://help.salesforce.com/articleView?id=000003911&amp;language=en_US&amp;type=1){target="_blank"}
