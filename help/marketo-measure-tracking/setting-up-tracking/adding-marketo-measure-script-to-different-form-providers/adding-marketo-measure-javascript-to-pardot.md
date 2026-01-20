---
unique-page-id: 18874757
description: Het toevoegen van  [!DNL Marketo Measure]  JavaScript aan  [!DNL Pardot]  -  [!DNL Marketo Measure]
title: Het toevoegen van  [!DNL Marketo Measure]  JavaScript aan  [!DNL Pardot]
exl-id: e49190ad-aa86-4f8f-a9ed-48de9e937a7e
feature: Tracking
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 1%

---

# [!DNL Marketo Measure] JavaScript toevoegen aan [!DNL Pardot] {#adding-marketo-measure-javascript-to-pardot}

[!DNL Pardot] -formulieren moeten binnen de formuliersjabloon verder worden verwerkt dan alleen scripts op de site plaatsen, zodat [!DNL Marketo Measure] de verzonden formulieren kan herkennen. Het proces is eenvoudig; hiervoor hoeft u alleen het [!DNL Marketo Measure] tracking-script in de [!DNL Pardot] -formuliersjabloon te plaatsen.

## Instructies voor stap {#step-by-step-instructions}

Nadat u zich hebt aangemeld bij uw [!DNL Pardot] -account, voert u de onderstaande stappen uit.

1. Ga naar **[!UICONTROL Marketing]**.

1. Klik op **[!UICONTROL Landing Pages]**.

1. Selecteer **[!UICONTROL Layout Template]**.

   ![](assets/1-3.png)

1. Bepaal de juiste lay-outsjabloon en klik rechts op **[!UICONTROL Edit]** .

   ![](assets/2-1.png)

1. Kopieer en plak de [!DNL Marketo Measure] JavaScript-code net voor de eindkoptag op de HTML-pagina.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Voer de volgende stappen uit voor alle toepasselijke sjablonen voor paginalayout.

1. Zorg ervoor dat de JavaScript van [!DNL Marketo Measure] ook op de algemene sitepagina staat.

   Binnen het [!DNL Pardot] Malplaatje van de Lay-out, kijkt de code ongeveer als volgt:

```text
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>
   </head>
   <body>
```

## Aanvullende opmerkingen {#additional-notes}

Als het [!DNL Pardot] IFrame de volgende HTML-tag heeft:

`<base href="http://go.pardot.com">`

_en_ IFrame zelf is eigenlijk een veilige pagina (HTTPS) eerder dan onveilig (HTTP), wanneer het laden van het manuscript in [!DNL Pardot] IFrame, probeert browser om een versie van HTTP van het manuscript op een HTTPS pagina te laden die zal ontbreken, die het volgen breekt. U kunt het script bijwerken naar het [!DNL Pardot] IFrame om de beveiligde versie van het script te laden:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

Er zijn mogelijk al andere codefragmenten voor reeksspatiëring in dit gebied, zoals een [!DNL Google Analytics] -code. Zorg ervoor dat u ze scheidt met een puntkomma `;` en één spatie, zoals in dit voorbeeld wordt getoond:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="othercode_example" src="otherfile_example.js" ></script>`
