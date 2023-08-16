---
unique-page-id: 18874759
description: Toevoegen [!DNL Marketo Measure] tot [!DNL Hubspot] - [!DNL Marketo Measure] - Productdocumentatie
title: Toevoegen [!DNL Marketo Measure] tot [!DNL Hubspot]
exl-id: 633e7ef7-7959-461e-881f-dcc543595b66
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 0%

---

# Toevoegen [!DNL Marketo Measure] tot [!DNL Hubspot] {#adding-marketo-measure-to-hubspot}

Leer hoe u de [!DNL Marketo Measure] JavaScript om uw [!DNL Hubspot] het aanlanden van pagina&#39;s en het indienen van formulieren.

Hubspot wijkt enigszins af van andere marketingautomatiseringssystemen omdat het uw landingspagina&#39;s / formulieren EN uw website kan hosten. Het is belangrijk om op te merken dat de onderstaande instructies zijn voor het hebben van [!DNL Marketo Measure] trackactiviteit op [!DNL Hubspot]-hosted pages. Als u uw website een andere CMS dan [!DNL Hubspot] (bijvoorbeeld Wordpress), moet u de opdracht [!DNL Marketo Measure] JavaScript ook naar dat CMS.

>[!NOTE]
>
>Als u JavaScript implementeert via een tagbeheerprovider, zoals [!DNL Google Tag Manager]hoeft u de code niet handmatig op te slaan [!DNL Marketo Measure] JavaScript in uw website.

## Aan de slag {#getting-started}

Nadat u zich hebt aangemeld bij uw [!DNL Hubspot] -account, voert u deze stappen uit.

1. Navigeer naar Inhoud.

1. Klik op **[!UICONTROL Content Settings]**.

1. Within [!UICONTROL Content Settings]klikt u op de HTML van de sitekoptekst (zie de onderstaande afbeelding).

1. Voeg het volgende script toe in uw `<header>`:

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

   Het moet er als volgt uitzien:

```text
<!-- Marketo Measure Javascript -->
<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="">
```

>[!TIP]
>
>Er zijn mogelijk al andere codefragmenten voor tekstspatiëring in dit gebied, zoals een Google Analytics-code. Zorg ervoor dat u ze met een puntkomma scheidt `;` en één enkele ruimte, zoals:
>
>`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`
