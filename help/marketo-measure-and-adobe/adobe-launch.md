---
description: '[!DNL Marketo Measure] Integraties met Adobe Launch -  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] Integratie met Adobe Launch'
exl-id: 316ee8a8-b2d3-42e9-9ee5-c9b1d91c2769
feature: Integration
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 0%

---


# [!DNL Marketo Measure] Integratie met Adobe Launch {#marketo-measure-integrations}

De Adobe Launch-extensie is ontworpen voor bestaande [!DNL Marketo Measure] -gebruikers die Adobe Launch al gebruiken op hun website. De extensie fungeert als een oplossing voor tagbeheer waarmee u scripts op uw pagina&#39;s kunt configureren en dynamisch laden op basis van bepaalde gebeurtenissen en voorwaarden.

Wanneer de extensie [!DNL Marketo Measure] is geïnstalleerd en geconfigureerd in Adobe Launch, wordt het script bizible.js geladen op de pagina&#39;s waarop het Adobe Launch-script aanwezig is. Dit staat marketers toe om bizible.js door de configuratie van de Lancering van Adobe toe te voegen, in tegenstelling tot uitdrukkelijk het wijzigen van de Web-pagina om bizible.js manuscriptmarkering toe te voegen.

## De Adobe-startextensie configureren {#configure-the-adobe-launch-extension}

>[!PREREQUISITES]
>Raadpleeg de volgende koppelingen voor meer informatie over Adobe Launch en de extensies ervan:
> [[!DNL Marketo Measure] Extensie &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email/bizible.html?lang=nl-NL#catalog){target="_blank"}
> [Adobe-overzicht van starten &#x200B;](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/overview.html?lang=nl-NL){target="_blank"}
> [Overzicht Adobe-extensie starten &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/tags/extension-dev/overview.html?lang=nl-NL){target="_blank"}

1. Creeer een bezit na de stappen [&#x200B; in dit artikel &#x200B;](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/configure-tags/create-a-property.html?lang=nl-NL#go-to-the-data-collection-interface){target="_blank"}.

1. Klik op de eigenschap die u hebt gemaakt.

   ![&#x200B; het scherm van de het bezitsselectie van de Lancering van Adobe het tonen van beschikbare eigenschappen &#x200B;](assets/marketo-measure-integrations-1.png)

1. Klik op **[!UICONTROL Extensions]**.

   ![&#x200B; het lusje van Uitbreidingen in het bezitsmontages van de Lancering van Adobe &#x200B;](assets/marketo-measure-integrations-2.png)

1. Klik op het tabblad **[!UICONTROL Catalog]** en zoek naar &quot;[!UICONTROL Bizible]&quot;.

   ![&#x200B; het catalogusonderzoek van de Uitbreiding tonend Bizible uitbreiding &#x200B;](assets/marketo-measure-integrations-3.png)

1. Klik in de [!UICONTROL Bizible Analytics] -tegel op **[!UICONTROL Install]** .

   ![&#x200B; Bizible Analytics uitbreidingstegel met Install knoop &#x200B;](assets/marketo-measure-integrations-4.png)

1. Typ in het veld Bizible AccountId de URL van uw website (bijvoorbeeld `adobe.com` ).

   ![&#x200B; Bizible uitbreidingsconfiguratie met gebied AccountId &#x200B;](assets/marketo-measure-integrations-5.png)

1. Klik op **[!UICONTROL Save]**.

   ![&#x200B; sparen knoop voor Bizible uitbreidingsconfiguratie &#x200B;](assets/marketo-measure-integrations-6.png)

1. Klik op **[!UICONTROL Rules]** en selecteer vervolgens **[!UICONTROL Create New Rule]** .

   ![&#x200B; Regels lusje met Create Nieuwe knoop van de Regel &#x200B;](assets/marketo-measure-integrations-7.png)

1. Klik op de knop **[!UICONTROL Add]** onder [!UICONTROL Events] .

   ![&#x200B; voegt knoop in de sectie van Gebeurtenissen van regelconfiguratie &#x200B;](assets/marketo-measure-integrations-8.png) toe

1. Selecteer **[!UICONTROL Core]** in de vervolgkeuzelijst Extensie. Selecteer vervolgens **[!UICONTROL Library Loaded (Page Top)]** in de vervolgkeuzelijst Type gebeurtenis. Als u de gebeurtenis geen naam geeft, wordt een standaardnaam toegepast. Klik op **[!UICONTROL Keep Changes]** als u klaar bent.

   ![&#x200B; de configuratiedialoog van de Gebeurtenis met de uitbreiding van de Kern en Bibliotheek Geladen gebeurtenistype &#x200B;](assets/marketo-measure-integrations-9.png)

1. Klik op de knop **[!UICONTROL Add]** onder Handelingen.

   ![&#x200B; voegt knoop in de sectie van Acties van regelconfiguratie &#x200B;](assets/marketo-measure-integrations-10.png) toe

1. Selecteer **[!UICONTROL Bizible Analytics]** in de vervolgkeuzelijst Extensie. Selecteer vervolgens **[!UICONTROL Initialize]** in de vervolgkeuzelijst Type actie. Als u de handeling geen naam geeft, wordt er een standaardnaam toegepast. Klik op **[!UICONTROL Keep Changes]** als u klaar bent.

   ![&#x200B; de configuratiedialoog van de Actie met Bizible uitbreiding Analytics en Initialiseert actietype &#x200B;](assets/marketo-measure-integrations-11.png)

1. Klik op **[!UICONTROL Save]**.

   ![&#x200B; sparen knoop voor regelconfiguratie &#x200B;](assets/marketo-measure-integrations-12.png)

