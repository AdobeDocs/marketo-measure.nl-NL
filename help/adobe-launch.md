---
description: '''[!DNL Marketo Measure] Integraties met Adobe Launch - [!DNL Marketo Measure]'''
title: '[!DNL Marketo Measure] Integratie met Adobe Launch'
exl-id: 316ee8a8-b2d3-42e9-9ee5-c9b1d91c2769
feature: Integration
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 4%

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

   ![1. Klik het bezit dat u creeerde.](assets/marketo-launch-12.png)

1. Klik op **[!UICONTROL Extensions]**.

   ![1. Klik op Extensies.](assets/marketo-launch-11.png)

1. Klik op het tabblad **[!UICONTROL Catalog]** en zoek naar &quot;[!UICONTROL Bizible]&quot;.

   ![1. Klik het lusje van de Catalogus en onderzoek naar &quot;Bizible.&quot;](assets/marketo-launch-10.png)

1. Klik in de [!UICONTROL Bizible Analytics] -tegel op **[!UICONTROL Install]** .

   ![1. Klik in de tegel Bizible Analytics op Install.](assets/marketo-launch-7.png)

1. Typ in het veld Bizible AccountId de URL van uw website (bijvoorbeeld `adobe.com` ).

   ![1. Typ in het veld Bizible AccountId de URL van uw ](assets/marketo-launch-6.png)

1. Klik op **[!UICONTROL Save]**.

   ![1. Klik op Opslaan.](assets/marketo-launch-8.png)

1. Klik op **[!UICONTROL Rules]** en selecteer vervolgens **[!UICONTROL Create New Rule]** .

   ![1. Klik op Regels en selecteer vervolgens Nieuwe regel maken.](assets/marketo-launch-9.png)

1. Klik op de knop **[!UICONTROL Add]** onder [!UICONTROL Events] .

   ![1. Klik op de knop Toevoegen onder Gebeurtenissen.](assets/marketo-launch-2.png)

1. Selecteer **[!UICONTROL Core]** in de vervolgkeuzelijst Extensie. Selecteer vervolgens **[!UICONTROL Library Loaded (Page Top)]** in de vervolgkeuzelijst Type gebeurtenis. Als u de gebeurtenis geen naam geeft, wordt een standaardnaam toegepast. Klik op **[!UICONTROL Keep Changes]** als u klaar bent.

   ![1. Selecteer Core in de vervolgkeuzelijst Extensie. Dan in de Gebeurtenis ](assets/marketo-launch-1.png)

1. Klik op de knop **[!UICONTROL Add]** onder Handelingen.

   ![1. Klik op de knop Toevoegen onder Handelingen.](assets/marketo-launch-3.png)

1. Selecteer **[!UICONTROL Bizible Analytics]** in de vervolgkeuzelijst Extensie. Selecteer vervolgens **[!UICONTROL Initialize]** in de vervolgkeuzelijst Type actie. Als u de handeling geen naam geeft, wordt er een standaardnaam toegepast. Klik op **[!UICONTROL Keep Changes]** als u klaar bent.

   ![1. Selecteer Bizible Analytics in de vervolgkeuzelijst Extensie. Dan in de Actie ](assets/marketo-launch-4.png)

1. Klik op **[!UICONTROL Save]**.

   ![1. Klik op Opslaan.](assets/marketo-launch-5.png)

