---
unique-page-id: 18874743
description: Verbinding maken [!DNL Marketo Measure] om Scriptbeheer weer te geven - [!DNL Marketo Measure]
title: Verbinding maken [!DNL Marketo Measure] om Scriptbeheer weer te geven
exl-id: c3212bc3-1d8f-4da5-bb2d-11ffd2fb4e98
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 2%

---

# Verbinding maken [!DNL Marketo Measure] om Scriptbeheer weer te geven {#connecting-marketo-measure-to-unbounce-script-manager}

[!DNL Marketo Measure] integreert rechtstreeks met Unbounce, waardoor u de digitale marketingbron van de omzettingen van de bestemmingspagina rechtstreeks kunt volgen in [!DNL Salesforce]. Als u de verbinding wilt maken, voegt u gewoon de knop [!DNL Marketo Measure] script naar uw Unbounce Script Manager. Zo gaat het.

1. Aanmelden bij uw [!DNL Unbounce] account.
1. Klik op **[!UICONTROL Settings]** > **[!UICONTROL Script Manager]** > **[!UICONTROL Add Script]**.
1. Selecteer in het pop-upmenu [!UICONTROL Custom Script] en noem het &quot;[!DNL Marketo Measure Marketing Analytics].&quot; Klik op **[!UICONTROL Add Script Details]**.
1. Selecteer plaatsing in het hoofd. Neem het script op in het dialoogvenster Hoofd-landingspagina en Formulierbevestiging. Plak de [!DNL Marketo Measure] in het tekstvak.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Klik op **[!UICONTROL Save]**.

De [!DNL Marketo Measure] integratie werkt op bestemmingspagina&#39;s van Unbounce zolang deze op uw domein (bijvoorbeeld, landing.mysite.com) worden ontvangen niet degenen die het unbounce.com domein gebruiken.
