---
unique-page-id: 18874747
description: Toevoegend  [!DNL Marketo Measure]  Manuscript aan de Pagina's van de Sitecore -  [!DNL Marketo Measure]
title: Toevoegend  [!DNL Marketo Measure]  Manuscript aan de Pagina's van de Sitecore
exl-id: 87ce1857-7532-45a7-8c39-255c6118b50a
feature: Tracking
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 0%

---

# [!DNL Marketo Measure] Script toevoegen aan Sitecore Pages {#adding-marketo-measure-script-to-sitecore-pages}

Voor systemen voor contentbeheer zijn mogelijk aanvullende stappen nodig, naast de standaardimplementatie, om formulierverzendingen te herkennen in [!DNL Marketo Measure] . In het onderstaande proces wordt beschreven hoe u [!DNL Marketo Measure] javascript aan uw [!DNL Sitecore] -pagina&#39;s kunt toevoegen.

Voor sites met Sitecore-pagina&#39;s:

1. Meld u aan bij Sitecore en navigeer naar uw website. Zoek de map [!UICONTROL Configuration] die zich op hetzelfde niveau bevindt als de map [!UICONTROL Home] item en [!UICONTROL Metadata] .
1. Klik op **[!UICONTROL +]** naast de map [!UICONTROL Configuration] .
1. Klik op **[!UICONTROL +]** naast de map [!UICONTROL Tools] .
1. Selecteer het item [!UICONTROL Javascript] .
1. Klik op het tabblad [!UICONTROL Content] op de koppeling **[!UICONTROL Lock and Edit]** om het item te ontgrendelen voor bewerking.
1. De sectie [!UICONTROL 'JavaScript'] zoeken. Klik op **[!UICONTROL +]** als dit nog niet is gebeurd.
1. Voer ons script in: `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js"async=""></script>`
1. Klik op **[!UICONTROL Save]** in de linkerbovenhoek.
