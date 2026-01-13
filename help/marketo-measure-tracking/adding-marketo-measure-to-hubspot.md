---
description: Toevoegend  [!DNL Marketo Measure]  aan  [!DNL Hubspot]  -  [!DNL Marketo Measure]
title: Toevoegend  [!DNL Marketo Measure]  aan  [!DNL Hubspot]
exl-id: 633e7ef7-7959-461e-881f-dcc543595b66
feature: Tracking
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 1%

---


# [!DNL Marketo Measure] toevoegen aan [!DNL Hubspot] {#adding-marketo-measure-to-hubspot}

Leer hoe u de [!DNL Marketo Measure] JavaScript toevoegt om uw [!DNL Hubspot] -openingspagina&#39;s en formulierverzendingen bij te houden.

Hubspot wijkt enigszins af van andere marketingautomatiseringssystemen omdat het uw landingspagina&#39;s / formulieren EN uw website kan hosten. Het is belangrijk om te weten dat de onderstaande instructies bedoeld zijn om [!DNL Marketo Measure] activiteit bij te houden op pagina&#39;s die door [!DNL Hubspot] worden gehost. Als u uw website een andere CMS dan [!DNL Hubspot] (bijvoorbeeld Wordpress) inschakelt, moet u ook de [!DNL Marketo Measure] JavaScript aan die CMS toevoegen.

>[!NOTE]
>Als u de JavaScript implementeert via een tagbeheerprovider zoals [!DNL Google Tag Manager] , hoeft u de [!DNL Marketo Measure] JavaScript niet handmatig in te schakelen op uw website.

## Aan de slag {#getting-started}

Voer de volgende stappen uit als u zich hebt aangemeld bij uw [!DNL Hubspot] -account.

1. Navigeer naar Inhoud.

1. Klik op **[!UICONTROL Content Settings]**.

1. Klik in [!UICONTROL Content Settings] op de Site Header HTML (zie onderstaande afbeelding).

1. Voeg het volgende script toe in uw `<header>` :

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

   Het moet er als volgt uitzien:

```text
<!-- Marketo Measure Javascript -->
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="">
```

>[!TIP]
>Er zijn mogelijk al andere codefragmenten voor tekstspatiëring in dit gebied, zoals een Google Analytics-code. Zorg ervoor dat u ze als volgt scheidt met een puntkomma `;` en één spatie:
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`
