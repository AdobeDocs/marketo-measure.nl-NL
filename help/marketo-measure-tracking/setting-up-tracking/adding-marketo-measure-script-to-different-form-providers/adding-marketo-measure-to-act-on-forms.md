---
unique-page-id: 18874753
description: Toevoegen [!DNL Marketo Measure] op Forms - [!DNL Marketo Measure] - Productdocumentatie
title: Toevoegen [!DNL Marketo Measure] aan Act-on Forms
exl-id: 3d246e6a-ad3b-4683-b2b7-ab3f0f4c5ab2
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 0%

---

# Toevoegen [!DNL Marketo Measure] aan Act-on Forms {#adding-marketo-measure-to-act-on-forms}

## Richtingen {#directions}

1. Selecteer in het formulier dat u bewerkt de optie **[!UICONTROL Settings]** in de rechterhoek.
1. Zoeken naar een gebied met het label [!UICONTROL "External Web Analytics."] Dit is waar u de [!DNL Marketo Measure] codefragment bijhouden.

## [!DNL Marketo Measure] JavaScript {#marketo-measure-javascript}

`script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

>[!NOTE]
>
>Er zijn mogelijk al andere codefragmenten in dit gebied, zoals een [!DNL Google Analytics] code. Zorg ervoor dat u ze scheidt met een puntkomma `;` en één enkele ruimte, zoals:
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>**; **<script async="true" type="someothercode" src="someotherfile.js" ></script>`
