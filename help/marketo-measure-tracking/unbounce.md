---
description: Het verbinden  [!DNL Marketo Measure]  aan Unbounce Manager van het Manuscript -  [!DNL Marketo Measure]
title: Verbindend  [!DNL Marketo Measure]  aan Unbounce Manager van het Manuscript
exl-id: c3212bc3-1d8f-4da5-bb2d-11ffd2fb4e98
feature: Tracking
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 2%

---


# [!DNL Marketo Measure] verbinden met Unbounce Script Manager {#connecting-marketo-measure-to-unbounce-script-manager}

[!DNL Marketo Measure] kan rechtstreeks worden geïntegreerd met Unbounce, zodat u de digitale marketingbron van de omzettingen van de bestemmingspagina rechtstreeks kunt volgen in [!DNL Salesforce] . U kunt de verbinding tot stand brengen door het script [!DNL Marketo Measure] toe te voegen aan de Unbounce Script Manager. Zo gaat het.

1. Meld u aan bij uw [!DNL Unbounce] -account.
1. Klik op **[!UICONTROL Settings]** > **[!UICONTROL Script Manager]** > **[!UICONTROL Add Script]**.
1. Selecteer [!UICONTROL Custom Script] in de pop-up en geef deze de naam &quot;[!DNL Marketo Measure Marketing Analytics]&quot;. Klik op **[!UICONTROL Add Script Details]**.
1. Selecteer plaatsing in het hoofd. Neem het script op in het dialoogvenster Hoofd-landingspagina en Formulierbevestiging. Plak het script van [!DNL Marketo Measure] hieronder in het vak.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Klik op **[!UICONTROL Save]**.

De integratie van [!DNL Marketo Measure] werkt op bestemmingspagina&#39;s Unbounce zolang deze op uw domein (bijvoorbeeld landing.mysite.com) worden gehost en niet op de pagina unbounce.com.
