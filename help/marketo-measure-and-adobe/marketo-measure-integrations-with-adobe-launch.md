---
description: '[!DNL Marketo Measure] Integraties met Adobe Launch -  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] Integratie met Adobe Launch'
exl-id: 316ee8a8-b2d3-42e9-9ee5-c9b1d91c2769
feature: Integration
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 1%

---

# [!DNL Marketo Measure] Integratie met Adobe Launch {#marketo-measure-integrations-with-adobe-launch}

De Adobe Launch-extensie is ontworpen voor bestaande [!DNL Marketo Measure] -gebruikers die Adobe Launch al gebruiken op hun website. De extensie fungeert als een oplossing voor tagbeheer waarmee u scripts op uw pagina&#39;s kunt configureren en dynamisch laden op basis van bepaalde gebeurtenissen en voorwaarden.

Wanneer de extensie [!DNL Marketo Measure] is geïnstalleerd en geconfigureerd in Adobe Launch, wordt het script bizible.js geladen op de pagina&#39;s waarop het Adobe Launch-script aanwezig is. Dit staat marketers toe om bizible.js door de configuratie van de Lancering van Adobe toe te voegen, in tegenstelling tot uitdrukkelijk het wijzigen van de Web-pagina om bizible.js manuscriptmarkering toe te voegen.

## De Adobe-startextensie configureren {#configure-the-adobe-launch-extension}

>[!PREREQUISITES]
>
>Raadpleeg de volgende koppelingen voor meer informatie over Adobe Launch en de extensies ervan:
>
>* [[!DNL Marketo Measure]  Uitbreiding ](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email/bizible.html#catalog){target="_blank"}
>* [ het Overzicht van de Lancering van Adobe ](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/overview.html){target="_blank"}
>* [ het Overzicht van de Uitbreiding van de Lancering van Adobe ](https://experienceleague.adobe.com/docs/experience-platform/tags/extension-dev/overview.html){target="_blank"}

1. Creeer een bezit na de stappen [ in dit artikel ](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/configure-tags/create-a-property.html#go-to-the-data-collection-interface){target="_blank"}.

1. Klik op de eigenschap die u hebt gemaakt.

   ![](assets/marketo-measure-integrations-with-adobe-launch-1.png)

1. Klik op **[!UICONTROL Extensions]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-2.png)

1. Klik op het tabblad **[!UICONTROL Catalog]** en zoek naar &quot;[!UICONTROL Bizible]&quot;.

   ![](assets/marketo-measure-integrations-with-adobe-launch-3.png)

1. Klik in de [!UICONTROL Bizible Analytics] -tegel op **[!UICONTROL Install]** .

   ![](assets/marketo-measure-integrations-with-adobe-launch-4.png)

1. Typ in het veld Bizible AccountId de URL van uw website (bijvoorbeeld `adobe.com` ).

   ![](assets/marketo-measure-integrations-with-adobe-launch-5.png)

1. Klik op **[!UICONTROL Save]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-6.png)

1. Klik op **[!UICONTROL Rules]** en selecteer vervolgens **[!UICONTROL Create New Rule]** .

   ![](assets/marketo-measure-integrations-with-adobe-launch-7.png)

1. Klik op de knop **[!UICONTROL Add]** onder [!UICONTROL Events] .

   ![](assets/marketo-measure-integrations-with-adobe-launch-8.png)

1. Selecteer **[!UICONTROL Core]** in de vervolgkeuzelijst Extensie. Selecteer vervolgens **[!UICONTROL Library Loaded (Page Top)]** in de vervolgkeuzelijst Type gebeurtenis. Als u de gebeurtenis geen naam geeft, wordt een standaardnaam toegepast. Klik op **[!UICONTROL Keep Changes]** als u klaar bent.

   ![](assets/marketo-measure-integrations-with-adobe-launch-9.png)

1. Klik op de knop **[!UICONTROL Add]** onder Handelingen.

   ![](assets/marketo-measure-integrations-with-adobe-launch-10.png)

1. Selecteer **[!UICONTROL Bizible Analytics]** in de vervolgkeuzelijst Extensie. Selecteer vervolgens **[!UICONTROL Initialize]** in de vervolgkeuzelijst Type actie. Als u de handeling geen naam geeft, wordt er een standaardnaam toegepast. Klik op **[!UICONTROL Keep Changes]** als u klaar bent.

   ![](assets/marketo-measure-integrations-with-adobe-launch-11.png)

1. Klik op **[!UICONTROL Save]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-12.png)

