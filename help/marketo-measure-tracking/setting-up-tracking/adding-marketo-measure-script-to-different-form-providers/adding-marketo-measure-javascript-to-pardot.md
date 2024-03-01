---
unique-page-id: 18874757
description: Toevoegen [!DNL Marketo Measure] JavaScript naar [!DNL Pardot] - [!DNL Marketo Measure]
title: Toevoegen [!DNL Marketo Measure] JavaScript naar [!DNL Pardot]
exl-id: e49190ad-aa86-4f8f-a9ed-48de9e937a7e
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 0%

---

# Toevoegen [!DNL Marketo Measure] JavaScript naar [!DNL Pardot] {#adding-marketo-measure-javascript-to-pardot}

[!DNL Pardot] formulieren moeten binnen de formuliersjabloon verder worden verwerkt dan alleen scripts op de site plaatsen om [!DNL Marketo Measure] om formulierverzendingen te erkennen. Het proces is eenvoudig; het vereist slechts het plaatsen van [!DNL Marketo Measure] script bijhouden in de [!DNL Pardot] formuliersjabloon

## Instructies Stap voor stap {#step-by-step-instructions}

Nadat u zich hebt aangemeld bij uw [!DNL Pardot] -account, volgt u de onderstaande stappen.

1. Navigeren naar **[!UICONTROL Marketing]**.

1. Klikken op **[!UICONTROL Landing Pages]**.

1. Selecteren **[!UICONTROL Layout Template]**.

   ![](assets/1-3.png)

1. Bepaal de juiste lay-outsjabloon en klik op **[!UICONTROL Edit]** rechts.

   ![](assets/2-1.png)

1. Kopieer en plak de [!DNL Marketo Measure] JavaScript-code vlak voor de afsluitende koptag op de pagina HTML.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Voer de volgende stappen uit voor alle toepasselijke sjablonen voor paginalayout.

1. Zorg ervoor dat de [!DNL Marketo Measure] JavaScript staat ook op de algemene sitepagina.

   Binnen de [!DNL Pardot] Lay-outsjabloon, ziet de code er ongeveer als volgt uit:

```text
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>
   </head>
   <body>
```

## Aanvullende opmerkingen {#additional-notes}

Als de [!DNL Pardot] IFrame heeft de volgende HTML-tag:

`<base href="http://go.pardot.com">`

_en_ het IFrame zelf bevindt zich eigenlijk op een veilige pagina (HTTPS) in plaats van een niet-beveiligde pagina (HTTP), wanneer we ons script proberen te laden op het [!DNL Pardot] IFrame, zal browser proberen om een versie van HTTP van ons manuscript op een HTTPS pagina te laden die zal ontbreken en ons van het volgen zal verhinderen. De oplossing is om het manuscript op de [!DNL Pardot] IFrame om de veilige versie van ons script te laden:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

Er kunnen ook al andere codefragmenten in dit gebied zijn, zoals een [!DNL Google Analytics] code. Zorg ervoor dat u ze met een puntkomma scheidt `;` en één spatie, zoals in dit voorbeeld wordt getoond:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="othercode_example" src="otherfile_example.js" ></script>`
