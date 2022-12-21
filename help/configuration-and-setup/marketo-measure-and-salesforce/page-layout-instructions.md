---
unique-page-id: 18874799
description: Pagina-indelingsinstructies - [!DNL Marketo Measure] - Productdocumentatie
title: Pagina-indelingsinstructies
exl-id: 627377f0-d0cf-448c-a7b5-7eb5634b9627
source-git-commit: b910e5aedb9e178058f7af9a6907a1039458ce7a
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 1%

---

# Pagina-indelingsinstructies {#page-layout-instructions}

>[!NOTE]
>
>Mogelijk ziet u instructies die &quot;[!DNL Marketo Measure]&quot; in onze documentatie, maar zie nog &quot;Bizible&quot;in uw CRM. We werken eraan dat dit wordt bijgewerkt en de herbranding wordt binnenkort weerspiegeld in uw CRM.

Eenvoudig te zien [!DNL Marketo Measure] gegevens, wordt aangeraden om de pagina-indelingen bij te werken voor de [!UICONTROL Account], [!UICONTROL Contact], [!UICONTROL Lead], [!UICONTROL Opportunity], en [!UICONTROL Campaign] Objecten. De instructies worden uitgesplitst voor elke indeling van de objectpagina hieronder.

Ga eerst naar uw [!DNL Salesforce] Instellingen instellen en de locatie van de [!UICONTROL Customize] tab.

## Campagneobject {#campaign-object}

We raden u aan de [!DNL Marketo Measure] velden alleen voor uw sandbox naar uw SFDC-campagne. De velden kunnen worden gebruikt om het genereren van aanraakpunten te testen. In productie adviseren wij slechts het toevoegen van [!DNL Marketo Measure] Bulk Touchpoint Date-knop bijwerken. We raden u niet aan de [!DNL Marketo Measure] velden voor productie, aangezien u regels voor het synchroniseren van campagnes kunt maken.

1. Selecteer in uw Build-optie de optie **[!UICONTROL Campaigns]**.

1. Klik op **[!UICONTROL Page Layouts]**.

   ![](assets/1-1.jpg)

1. Klikken **[!UICONTROL Edit]** naast de pagina-indeling die u wilt bijwerken.

   ![](assets/2-1.jpg)

1. Binnen de [!UICONTROL fields] selecteert u de optie **[!UICONTROL Enable Buyer Touchpoints]** en sleep het naar de gewenste positie op de pagina. Voeg vervolgens de **[!UICONTROL Touchpoint Start Date]** en **[!UICONTROL Touchpoint End Date]** velden.

   ![](assets/3-2.png)

1. Klik vervolgens boven aan de pagina op de knop &quot;[!UICONTROL Buttons]&quot; in het menu Snel zoeken.

1. Sleep de **[!UICONTROL Bulk Update Touchpoint Date]** aan uw sectie van douaneknoppen.

   ![](assets/4-1.jpg)

1. Klik op **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Als u meerdere soorten campagnemecords gebruikt, worden de keuzelijstwaarden voor de **[!UICONTROL Enable Buyer Touchpoints]** veld moet worden bijgewerkt. Gelieve te verwijzen [dit artikel](/help/channel-tracking-and-setup/offline-channels/configurations-for-multiple-campaign-record-types.md) voor instructies.

## Leads {#leads}

1. Selecteer in uw Build-optie de optie **[!UICONTROL Leads]**.

1. Klik op **[!UICONTROL Page Layouts]**.

1. Klikken **[!UICONTROL Edit]** naast de pagina-indeling die u wilt bijwerken. Houd er rekening mee dat lay-outs voor meerdere pagina&#39;s de secties Aanraakpunten voor kopers kunnen bevatten.

1. Klik op de de paginaoptie VisualForce op de linkerzijde binnen uw snel zoekmenu.

1. Maak een nieuwe sectie en noem deze &quot;Aanraakpunten koper&quot;.

   >[!NOTE]
   >
   >Selecteer de notatie Eén kolom voor elk van deze secties.

1. Sleep de **[!UICONTROL Marketo Measure Lead Related List]** De pagina VisualForce in uw sectie van de paginalay-out.

   ![](assets/5-1.png)

1. Klik op de moersleutel in het deelvenster [!DNL VisualForce] pagina, wijzigt u de hoogte in 100 en schakelt u schuifbalken in.

1. Selecteer de optie [!UICONTROL Canvas Apps] en maak een nieuwe sectie met de naam &quot;Marketo Measurement Insights&quot; onder de Touchpoints [!DNL VisualForce] -sectie die u zojuist hebt gemaakt.

   >[!NOTE]
   >
   >Selecteer de notatie Eén kolom voor elk van deze secties.

1. Sleep de [!DNL Marketo Measure Insights] Canvas App in die nieuwe sectie. Klikken **Opslaan**. Soms is het nodig om de paginalay-out eerst op te slaan voordat u de canvasapp neerzet, omdat Salesforce deze niet direct herkent. Sla dus na het maken van de nieuwe sectie de paginalay-out op en bewerk deze opnieuw om de canvasapp in die sectie te slepen. Dit geldt voor elk object.

   >[!NOTE]
   >
   >Voor de [!DNL Marketo Measure Insights] Canvas App correct laten functioneren, [de toestemmingen moeten behoorlijk worden gevormd](/help/configuration-and-setup/marketo-measure-insights-canvas-app/marketo-measure-insights-configuration.md).

   >[!TIP]
   >
   >De meeste klanten gebruiken niet de gebieden die met (FT) of (LC) beëindigen omdat zij erfenisgebieden van vóór zijn [!DNL Marketo Measure] Het aanraakpunt bestond als een object.

Als u gebruikmaakt van de [!DNL Marketo Measure] ABM-functie, [klik hier voor aanvullende instructies voor de pagina-indeling](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md).

## Contactpersonen {#contacts}

1. Selecteer in uw Build-optie de optie **[!UICONTROL Contacts]**.

1. Klik op **[!UICONTROL Page Layouts]**.

1. Selecteer de pagina-indeling die u wilt bewerken.

   Ga naar de optie Verwante lijsten in het snelmenu Zoeken en voeg de optie **[!UICONTROL Buyer Touchpoints]** verwante lijst.

1. Klik op het moersleutelpictogram en voeg de volgende kolommen in deze volgorde toe:

   * Aanraakpunt koper
   * Marketingkanaal
   * Aanraakpuntbron
   * Naam advertentiecampagne
   * Positie aanraakpunt
   * Aanraakpuntdatum

1. Sorteren op: Aanraakpuntdatum, oplopend.

   ![](assets/6.jpg)

1. De optie Knoppen uitvouwen en de selectie opheffen **[!UICONTROL New]**.

   ![](assets/7.png)

1. Ga terug naar de [!UICONTROL Related List] in het menu en voeg nu de optie **[!UICONTROL Buyer Attribution Touchpoint]** verwante lijst.

1. Klik op het moersleutelpictogram en voeg de volgende kolommen in deze volgorde toe:

   * Aanraakpunt kenmerk
   * Marketingkanaal
   * Opportunity
   * Naam advertentiecampagne
   * Type aanraakpunt
   * Positie aanraakpunt
   * Attributie % W-Shaped (_of het meest robuuste attributiemodel, zoals Volledig pad of Aangepast_)
   * Inkomsten in W-vorm (_of het meest robuuste attributiemodel, zoals Volledig pad of Aangepast_)
   * Aanraakpuntdatum

1. Sorteren op aanraakpunt [!UICONTROL Date] > [!UICONTROL Ascending].

1. Vouw het gedeelte Knoppen uit en schakel het selectievakje uit **[!UICONTROL New]**.

1. Klik op **[!UICONTROL Save]**.

## Kansen {#opportunities}

1. Selecteer in uw Build-optie de optie **[!UICONTROL Opportunities]**.

1. Klik op **[!UICONTROL Page Layouts]**.

1. Selecteer de pagina-indeling die u wilt bewerken.

1. Voeg de **[!UICONTROL Buyer Attribution Touchpoint]** Verwante Lijst en klik op de moersleutel om de volgende kolommen voor Kansen toe te voegen:

   * Aanraakpunt kenmerk
   * Marketingkanaal
   * Contact
   * Naam advertentiecampagne
   * Type aanraakpunt
   * Positie aanraakpunt
   * Attributie % W-Shaped (_of het meest robuuste attributiemodel, zoals Volledig pad of Aangepast_)
   * Inkomsten in W-vorm (_of het meest robuuste attributiemodel, zoals Volledig pad of Aangepast_)
   * Aanraakpuntdatum

1. Sorteren op [!UICONTROL Touchpoint Date] > [!UICONTROL Ascending].

1. Deselecteren **[!UICONTROL New]** binnen de [!UICONTROL Buttons] sectie.

1. Klik op **[!UICONTROL Save]**.

## Accounts {#accounts}

1. Selecteer in uw Build-optie de optie **[!UICONTROL Accounts]**.

1. Klik op **[!UICONTROL Page Layouts]**.

1. Selecteer de pagina-indeling die u wilt bewerken.

1. Voeg de **[!UICONTROL Buyer Attribution Touchpoint]** Verwante lijst en klik op de moersleutel om de volgende kolommen toe te voegen:

   * Aanraakpunt kenmerk
   * Marketingkanaal
   * Opportunity
   * Naam advertentiecampagne
   * Type aanraakpunt
   * Positie aanraakpunt
   * Attributie % W-Shaped (_of het meest robuuste attributiemodel, zoals Volledig pad of Aangepast_)
   * Inkomsten in W-vorm (_of het meest robuuste attributiemodel, zoals Volledig pad of Aangepast_)
   * Aanraakpuntdatum

1. Sorteren op Aanraakpuntdatum > Oplopend.

1. Deselecteren **[!UICONTROL New]** binnen de [!UICONTROL Buttons] sectie.

1. Klik op **[!UICONTROL Save]**.

Als u gebruikmaakt van de [!DNL Marketo Measure] ABM-functie,  [klik hier voor aanvullende instructies voor de pagina-indeling](/help/advanced-marketo-measure-features/account-based-marketing/account-based-marketing-overview.md).
