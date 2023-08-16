---
description: '''[!DNL Marketo Measure] Integratie met Adobe starten - [!DNL Marketo Measure] - Productdocumentatie"'
title: '[!DNL Marketo Measure] Integratie met Adobe Launch'
exl-id: 316ee8a8-b2d3-42e9-9ee5-c9b1d91c2769
feature: Integration
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 0%

---

# [!DNL Marketo Measure] Integratie met Adobe Launch {#marketo-measure-integrations-with-adobe-launch}

De extensie Adobe starten is ontworpen voor bestaande [!DNL Marketo Measure] gebruikers die al gebruikmaken van Adobe Launch op hun website. De extensie fungeert als een oplossing voor tagbeheer waarmee u scripts op uw pagina&#39;s kunt configureren en dynamisch laden op basis van bepaalde gebeurtenissen en voorwaarden.

Wanneer geïnstalleerd en gevormd in de Lancering van Adobe, [!DNL Marketo Measure] De extensie laadt het script bizible.js op de pagina&#39;s waar het script Adobe Launch aanwezig is. Dit staat marketers toe om bizible.js door de configuratie van de Lancering van de Adobe toe te voegen, in tegenstelling tot uitdrukkelijk het wijzigen van de Web-pagina om bizible.js manuscriptmarkering toe te voegen.

## De extensie Adobe starten configureren {#configure-the-adobe-launch-extension}

>[!PREREQUISITES]
>
>Raadpleeg de volgende koppelingen voor meer informatie over het starten van de Adobe en de extensies van de:
>
>* [[!DNL Marketo Measure] Extensie](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email/bizible.html?lang=en#catalog){target="_blank"}
>* [Overzicht van Adobe starten](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/index.html?lang=en#prerequisites){target="_blank"}
>* [Adobe - Overzicht van extensie starten](https://experienceleague.adobe.com/docs/launch/using/extension-dev/overview.html?lang=en#extension-configuration){target="_blank"}

1. Een eigenschap maken na de stappen [in dit artikel](https://experienceleague.adobe.com/docs/platform-learn/implement-in-websites/configure-tags/create-a-property.html?lang=en#go-to-the-data-collection-interface){target="_blank"}.

1. Klik op de eigenschap die u zojuist hebt gemaakt.

   ![](assets/marketo-measure-integrations-with-adobe-launch-1.png)

1. Klik op **[!UICONTROL Extensions]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-2.png)

1. Klik op de knop **[!UICONTROL Catalog]** tab en zoek naar &quot;[!UICONTROL Bizible].&quot;

   ![](assets/marketo-measure-integrations-with-adobe-launch-3.png)

1. In de [!UICONTROL Bizible Analytics] tegel, klikken **[!UICONTROL Install]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-4.png)

1. Typ in het veld Bizible AccountId de URL van uw website.

   ![](assets/marketo-measure-integrations-with-adobe-launch-5.png)

   >[!NOTE]
   >
   >Dit veld is niet de &quot;Account ID&quot; in de tabel Business_Prod.Business. Alle webactiviteiten vanaf de opgegeven URL worden toegewezen aan de [!DNL Marketo Measure] huurder.

1. Klik op **[!UICONTROL Save]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-6.png)

1. Klikken **[!UICONTROL Rules]** selecteert u vervolgens **[!UICONTROL Create New Rule]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-7.png)

1. Klik op de knop **[!UICONTROL Add]** knop onder [!UICONTROL Events].

   ![](assets/marketo-measure-integrations-with-adobe-launch-8.png)

1. Selecteer in het vervolgkeuzemenu Extensie de optie **[!UICONTROL Core]**. Selecteer vervolgens in de vervolgkeuzelijst Type gebeurtenis de optie **[!UICONTROL Library Loaded (Page Top)]**. Als u de gebeurtenis geen naam geeft, wordt er een standaardnaam toegepast. Klikken **[!UICONTROL Keep Changes]** wanneer gereed.

   ![](assets/marketo-measure-integrations-with-adobe-launch-9.png)

1. Klik op de knop **[!UICONTROL Add]** onder Handelingen.

   ![](assets/marketo-measure-integrations-with-adobe-launch-10.png)

1. Selecteer in de vervolgkeuzelijst Extensie de optie **[!UICONTROL Bizible Analytics]**. Selecteer vervolgens in de vervolgkeuzelijst Type handeling de optie **[!UICONTROL Initialize]**. Als u de handeling geen naam geeft, wordt er een standaardnaam toegepast. Klikken **[!UICONTROL Keep Changes]** wanneer gereed.

   ![](assets/marketo-measure-integrations-with-adobe-launch-11.png)

1. Klik op **[!UICONTROL Save]**.

   ![](assets/marketo-measure-integrations-with-adobe-launch-12.png)
