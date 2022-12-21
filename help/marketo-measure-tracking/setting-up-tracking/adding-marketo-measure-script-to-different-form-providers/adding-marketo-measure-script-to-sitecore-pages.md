---
unique-page-id: 18874747
description: Toevoegen [!DNL Marketo Measure] Script naar Sitecore-pagina's - [!DNL Marketo Measure] - Productdocumentatie
title: Toevoegen [!DNL Marketo Measure] Script naar Sitecore-pagina's
exl-id: 87ce1857-7532-45a7-8c39-255c6118b50a
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 0%

---

# Toevoegen [!DNL Marketo Measure] Script naar Sitecore-pagina&#39;s {#adding-marketo-measure-script-to-sitecore-pages}

Voor contentbeheersystemen zijn naast de standaardimplementatie aanvullende stappen vereist voor [!DNL Marketo Measure] om formulierverzendingen te erkennen. In het onderstaande proces wordt beschreven hoe u het [!DNL Marketo Measure] javascript naar uw [!DNL Sitecore] pagina&#39;s.

Voor sites met Sitecore-pagina&#39;s:

1. Meld u aan bij Sitecore en navigeer naar uw website. Zoek de [!UICONTROL Configuration] map die zich op hetzelfde niveau bevindt als uw [!UICONTROL Home] item en [!UICONTROL Metadata] map.
1. Klik op de knop **[!UICONTROL +]** naast de [!UICONTROL Configuration] map.
1. Klik op de knop **[!UICONTROL +]** naast de [!UICONTROL Tools] map.
1. Selecteer [!UICONTROL Javascript] item.
1. In de [!UICONTROL Content] klikt u op de knop **[!UICONTROL Lock and Edit]** koppeling om het item te ontgrendelen voor bewerking.
1. Zoek de [!UICONTROL 'JavaScript'] sectie. Als het nog niet is uitgevouwen, klikt u op de knop **[!UICONTROL +]**.
1. Voer ons script in: `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js"async=""></script>`
1. Klikken **[!UICONTROL Save]** in de linkerbovenhoek.
