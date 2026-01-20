---
unique-page-id: 18874753
description: Toevoegend  [!DNL Marketo Measure]  aan gedoe-op Forms -  [!DNL Marketo Measure]
title: Toevoegend  [!DNL Marketo Measure]  aan gedoe-op Forms
exl-id: 3d246e6a-ad3b-4683-b2b7-ab3f0f4c5ab2
feature: Tracking
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '72'
ht-degree: 0%

---

# [!DNL Marketo Measure] toevoegen aan Act-On Forms {#adding-marketo-measure-to-act-on-forms}

## Richtingen {#directions}

1. Selecteer in het formulier dat u bewerkt de optie **[!UICONTROL Settings]** in de rechterhoek.
1. Zoek naar een gebied met het label [!UICONTROL "External Web Analytics."] Hier zet u het codefragment [!DNL Marketo Measure] tracking neer.

## [!DNL Marketo Measure] JavaScript {#marketo-measure-javascript}

`script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

>[!NOTE]
>
>Er zijn mogelijk al andere codefragmenten voor reeksspatiëring in dit gebied, zoals een [!DNL Google Analytics] -code. Zorg ervoor dat u ze scheidt met behulp van een puntkomma `;` en één spatie, zoals:
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>**; **<script async="true" type="someothercode" src="someotherfile.js" ></script>`
