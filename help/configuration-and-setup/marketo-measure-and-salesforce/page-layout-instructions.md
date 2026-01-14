---
description: Richtlijnen voor pagina-indeling voor Marketo Measure-gebruikers
title: Pagina-indelingsinstructies
exl-id: 627377f0-d0cf-448c-a7b5-7eb5634b9627
feature: Salesforce
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 1%

---

# Pagina-indelingsinstructies {#page-layout-instructions}

>[!NOTE]
>
>U kunt instructies zien die &quot;[!DNL Marketo Measure]&quot;in de documentatie specificeren, maar nog zie &quot;Bizible&quot;in uw CRM. We werken eraan dat dit wordt bijgewerkt en de herbranding wordt binnenkort weerspiegeld in uw CRM.

Als u [!DNL Marketo Measure] -gegevens gemakkelijk wilt kunnen zien, is het raadzaam om de pagina-indelingen voor de objecten [!UICONTROL Account] , [!UICONTROL Contact] , [!UICONTROL Lead] , [!UICONTROL Opportunity] en [!UICONTROL Campaign]  bij te werken. De instructies worden uitgesplitst voor elke indeling van de objectpagina hieronder.

Navigeer eerst naar de instellingen voor [!DNL Salesforce] Instellingen en zoek het tabblad [!UICONTROL Customize] .

## Campagneobject {#campaign-object}

U wordt aangeraden de [!DNL Marketo Measure] -velden alleen voor uw sandbox toe te voegen aan uw SFDC-campagne. De velden kunnen worden gebruikt om het genereren van aanraakpunten te testen. In productie wordt alleen aangeraden de knop [!DNL Marketo Measure] Aanraakpunt datum bulkupdate toe te voegen. Het wordt afgeraden de [!DNL Marketo Measure] -velden aan de productie toe te voegen omdat u de regel Campagne Sync kunt maken.

1. Selecteer **[!UICONTROL Campaigns]** in de optie Build.

1. Klik op **[!UICONTROL Page Layouts]**.

   ![](assets/marketo-salesforce-7.jpg)

1. Klik op **[!UICONTROL Edit]** naast de pagina-indeling die u wilt bijwerken.

   ![](assets/marketo-salesforce-1.jpg)

1. Selecteer het veld [!UICONTROL fields] in de optie **[!UICONTROL Enable Buyer Touchpoints]** en sleep het veld naar de gewenste positie op de pagina. Voeg vervolgens de velden **[!UICONTROL Touchpoint Start Date]** en **[!UICONTROL Touchpoint End Date]** toe.

   ![](assets/bizible-full-1.png)

1. Vervolgens klikt u boven aan de pagina op de optie &quot;[!UICONTROL Buttons]&quot; in het snelmenu Zoeken.

1. Sleep de knop **[!UICONTROL Bulk Update Touchpoint Date]** naar het gedeelte met aangepaste knoppen.

   ![](assets/bizible-taxonomy-1.png)

1. Klik op **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Als u meerdere soorten campagnemerrecords gebruikt, moet u de waarden in de keuzelijst voor het veld **[!UICONTROL Enable Buyer Touchpoints]** bijwerken. Verwijs naar [ dit artikel ](/help/channel-tracking-and-setup/offline-channels/configurations-record-types.md) voor instructies.

## Leads {#leads}

1. Selecteer **[!UICONTROL Leads]** in de optie Build.

1. Klik op **[!UICONTROL Page Layouts]**.

1. Klik op **[!UICONTROL Edit]** naast de pagina-indeling die u wilt bijwerken. Houd er rekening mee dat lay-outs voor meerdere pagina&#39;s de secties Aanraakpunten voor kopers kunnen bevatten.

1. Klik de de paginaoptie VisualForce op de linkerzijde binnen uw snel zoekmenu.

1. Maak een sectie en noem deze &quot;Aanraakpunten koper&quot;.

1. Sleep de pagina **[!UICONTROL Marketo Measure Lead Related List]** VisualForce in uw sectie van de paginalay-out.

   ![](assets/connect-salesforce-1.png)

1. Klik op de moersleutel in de pagina [!DNL VisualForce] en wijzig de hoogte in 100 en schakel schuifbalken in.

1. Selecteer vervolgens de sectie [!UICONTROL Canvas Apps] in het menu en maak een sectie met de naam &quot;Marketo Measure Insights&quot; onder de sectie Touchpoints [!DNL VisualForce] die u hebt gemaakt.

1. Sleep de [!DNL Marketo Measure Insights] Canvas-app naar die nieuwe sectie. Klik **sparen**. Soms is het nodig om de paginalay-out eerst op te slaan voordat u de canvasapp neerzet, omdat Salesforce deze niet direct herkent. Sla dus na het maken van de sectie de paginalay-out op en bewerk deze opnieuw om de canvasapp in die sectie te slepen. Dit geldt voor elk object.

   >[!NOTE]
   >
   >Voor [!DNL Marketo Measure Insights] App van het Canvas behoorlijk te functioneren, [ toestemmingen moeten behoorlijk worden gevormd ](/help/configuration-and-setup/marketo-measure-insights-canvas-app/marketo-measure-insights-configuration.md).

Als u de [!DNL Marketo Measure] eigenschap ABM gebruikt, [ klik hier voor extra instructies van de paginalay-out ](/help/advanced-features/account-based-marketing/account-based-marketing-overview.md).

## Contactpersonen {#contacts}

1. Selecteer **[!UICONTROL Contacts]** in de optie Build.

1. Klik op **[!UICONTROL Page Layouts]**.

1. Selecteer de pagina-indeling die u wilt bewerken.

   Ga naar de optie Verwante lijsten in het snelmenu Zoeken en voeg de lijst met verwante lijsten **[!UICONTROL Buyer Touchpoints]** toe.

1. Klik op het moersleutelpictogram en voeg de volgende kolommen in deze volgorde toe:

   * Buyer Touchpoint
   * Marketingkanaal
   * Aanraakpunt Source
   * Naam advertentiecampagne
   * Positie aanraakpunt
   * Aanraakpuntdatum

1. Sorteren op: aanraakpuntdatum, oplopend.

   ![](assets/marketo-salesforce-15.jpg)

1. Vouw de optie Knoppen uit en hef de selectie van **[!UICONTROL New]** op.

   ![](assets/marketo-salesforce-12.png)

1. Ga terug naar de optie [!UICONTROL Related List] in het menu en voeg nu de lijst met verwante **[!UICONTROL Buyer Attribution Touchpoint]** toe.

1. Klik op het moersleutelpictogram en voeg de volgende kolommen in deze volgorde toe:

   * Attributie-aanraakpunt
   * Marketingkanaal
   * Kans
   * Naam advertentiecampagne
   * Type aanraakpunt
   * Positie aanraakpunt
   * Attributie % W-Vormde (_of het meest robuuste attributiemodel zoals Volledige Weg of Douane_)
   * De opbrengst W-Vormd (_of het meest robuuste attributiemodel zoals Volledige Weg of Douane_)
   * Aanraakpuntdatum

1. Sorteren op aanraakpunt [!UICONTROL Date] > [!UICONTROL Ascending] .

1. Vouw het gedeelte Knoppen uit en hef de selectie van **[!UICONTROL New]** op.

1. Klik op **[!UICONTROL Save]**.

## Kansen {#opportunities}

1. Selecteer **[!UICONTROL Opportunities]** in de optie Build.

1. Klik op **[!UICONTROL Page Layouts]**.

1. Selecteer de pagina-indeling die u wilt bewerken.

1. Voeg de **[!UICONTROL Buyer Attribution Touchpoint]** Verwante lijst toe en klik op de moersleutel om de volgende kolommen voor Kansen toe te voegen:

   * Attributie-aanraakpunt
   * Marketingkanaal
   * Contact
   * Naam advertentiecampagne
   * Type aanraakpunt
   * Positie aanraakpunt
   * Attributie % W-Vormde (_of het meest robuuste attributiemodel zoals Volledige Weg of Douane_)
   * De opbrengst W-Vormd (_of het meest robuuste attributiemodel zoals Volledige Weg of Douane_)
   * Aanraakpuntdatum

1. Sorteren op [!UICONTROL Touchpoint Date] > [!UICONTROL Ascending] .

1. Hef de selectie van **[!UICONTROL New]** op in de sectie [!UICONTROL Buttons] .

1. Klik op **[!UICONTROL Save]**.

## Accounts {#accounts}

1. Selecteer **[!UICONTROL Accounts]** in de optie Build.

1. Klik op **[!UICONTROL Page Layouts]**.

1. Selecteer de pagina-indeling die u wilt bewerken.

1. Voeg de **[!UICONTROL Buyer Attribution Touchpoint]** Verwante lijst toe en klik op de moersleutel om de volgende kolommen toe te voegen:

   * Attributie-aanraakpunt
   * Marketingkanaal
   * Kans
   * Naam advertentiecampagne
   * Type aanraakpunt
   * Positie aanraakpunt
   * Attributie % W-Vormde (_of het meest robuuste attributiemodel zoals Volledige Weg of Douane_)
   * De opbrengst W-Vormd (_of het meest robuuste attributiemodel zoals Volledige Weg of Douane_)
   * Aanraakpuntdatum

1. Sorteren op Aanraakpuntdatum > Oplopend.

1. Hef de selectie van **[!UICONTROL New]** op in de sectie [!UICONTROL Buttons] .

1. Klik op **[!UICONTROL Save]**.

Als u de [!DNL Marketo Measure] eigenschap ABM gebruikt, herzie de [ extra instructies van de paginalay-out ](/help/advanced-features/account-based-marketing/account-based-marketing-overview.md).
