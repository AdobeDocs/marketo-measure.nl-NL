---
description: '[!DNL Marketo Measure] Integratie met Adobe starten - [!DNL Marketo Measure]'
title: '''[!DNL Marketo Measure] Integratie met Adobe Launch"'
exl-id: 316ee8a8-b2d3-42e9-9ee5-c9b1d91c2769
feature: Integration
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 1%

---

# [!DNL Marketo Measure] Integratie met Adobe Launch {#marketo-measure-integrations-with-adobe-launch}

De extensie Adobe starten is ontworpen voor bestaande [!DNL Marketo Measure] gebruikers die al gebruikmaken van Adobe Launch op hun website. De extensie fungeert als een oplossing voor tagbeheer waarmee u scripts op uw pagina&#39;s kunt configureren en dynamisch laden op basis van bepaalde gebeurtenissen en voorwaarden.

Wanneer geïnstalleerd en gevormd in de Lancering van de Adobe, [!DNL Marketo Measure] extensie laadt bizible.js-script op de pagina&#39;s waarop het Adobe Launch-script aanwezig is. Dit staat marketers toe om bizible.js door de configuratie van de Lancering van de Adobe toe te voegen, in tegenstelling tot uitdrukkelijk het wijzigen van de Web-pagina om bizible.js manuscriptmarkering toe te voegen.

## De extensie Adobe starten configureren {#configure-the-adobe-launch-extension}

>[!PREREQUISITES]
>
>Raadpleeg de volgende koppelingen voor meer informatie over het starten van de Adobe en de extensies.
>
>* [[!DNL Marketo Measure] Extensie](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email/bizible.html#catalog){target="_blank"}
>* [Overzicht van starten van Adobe](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/overview.html){target="_blank"}
>* [Overzicht extensie starten Adobe](https://experienceleague.adobe.com/docs/experience-platform/tags/extension-dev/overview.html){target="_blank"}

1. Een eigenschap maken na de stappen [in dit artikel](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/configure-tags/create-a-property.html#go-to-the-data-collection-interface){target="_blank"}.

1. Klik op de eigenschap die u hebt gemaakt.

   ![](assets/marketo-measure-integrations-with-adobe-launch-1.png)

1. Klik op **[!UICONTROL Extensions]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-2.png)

1. Klik op de knop **[!UICONTROL Catalog]** tab en zoek naar &quot;[!UICONTROL Bizible].&quot;

   ![](assets/marketo-measure-integrations-with-adobe-launch-3.png)

1. In de [!UICONTROL Bizible Analytics] tegel, klikken **[!UICONTROL Install]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-4.png)

1. Typ in het veld Bizible AccountId de URL van uw website (bijvoorbeeld `adobe.com`).

   ![](assets/marketo-measure-integrations-with-adobe-launch-5.png)

   >[!NOTE]
   >
   >Dit veld is niet de &quot;Account ID&quot; in de tabel Business_Prod.Business. Alle webactiviteiten vanaf de opgegeven URL (bijvoorbeeld `adobe.com`) wordt toegewezen aan de [!DNL Marketo Measure] huurder.

1. Klik op **[!UICONTROL Save]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-6.png)

1. Klikken **[!UICONTROL Rules]** selecteert u vervolgens **[!UICONTROL Create New Rule]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-7.png)

1. Klik op de knop **[!UICONTROL Add]** knop onder [!UICONTROL Events].

   ![](assets/marketo-measure-integrations-with-adobe-launch-8.png)

1. Selecteer in het vervolgkeuzemenu Extensie de optie **[!UICONTROL Core]**. Selecteer vervolgens in de vervolgkeuzelijst Type gebeurtenis de optie **[!UICONTROL Library Loaded (Page Top)]**. Als u de gebeurtenis geen naam geeft, wordt een standaardnaam toegepast. Klikken **[!UICONTROL Keep Changes]** wanneer gereed.

   ![](assets/marketo-measure-integrations-with-adobe-launch-9.png)

1. Klik op de knop **[!UICONTROL Add]** onder Handelingen.

   ![](assets/marketo-measure-integrations-with-adobe-launch-10.png)

1. Selecteer in de vervolgkeuzelijst Extensie de optie **[!UICONTROL Bizible Analytics]**. Selecteer vervolgens in de vervolgkeuzelijst Type handeling de optie **[!UICONTROL Initialize]**. Als u de handeling geen naam geeft, wordt er een standaardnaam toegepast. Klikken **[!UICONTROL Keep Changes]** wanneer gereed.

   ![](assets/marketo-measure-integrations-with-adobe-launch-11.png)

1. Klik op **[!UICONTROL Save]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-12.png)
