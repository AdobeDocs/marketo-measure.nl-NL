---
unique-page-id: 18874797
description: Toevoegen [!DNL Marketo Measure] Script via [!DNL Google Tag Manager] - [!DNL Marketo Measure] - Productdocumentatie
title: Toevoegen [!DNL Marketo Measure] Script via [!DNL Google Tag Manager]
exl-id: 539efb10-35cb-4146-8eea-728c3948a11e
source-git-commit: 82cc8269bfdb26b6acf039d0ce0e06564f5e2612
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 0%

---

# Toevoegen [!DNL Marketo Measure] Script via [!DNL Google Tag Manager] {#adding-marketo-measure-script-via-google-tag-manager}

Wanneer u de [!DNL Marketo Measure] javascript, adviseren wij sterk [hard-coding het manuscript](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md){target=&quot;_blank&quot;} rechtstreeks in uw site. Nochtans, als dat niet mogelijk is, kunt u ook gebruiken [!DNL Google Tag Manager] (GTM) om de [!DNL Marketo Measure] JS. Houd er rekening mee dat [!DNL Marketo Measure] JS die door GTM wordt geladen is vatbaar voor latentie. Latentie veroorzaakt een vertraging in de laadtijden van scripts, waardoor ongeveer 3-5% van alle ingevulde formulieren kan ontbreken.

Als u besluit ons script toe te voegen via GTM, stelt u de [!DNL Marketo Measure] script naar de hoogste prioriteit in uw vuurorde en zorg ervoor dat er geen synchrone manuscripten vóór zijn [!DNL Marketo Measure] -tags gebruiken om eventuele effecten van GTM-latentie te beperken.

>[!NOTE]
>
>Gebruik deze [ondersteuningsartikel van Google](https://support.google.com/tagmanager/answer/2772421?hl=en){target=&quot;_blank&quot;} voor meer informatie.

## Toevoegen [!DNL Marketo Measure] JS via [!DNL Google Tag Manager] {#how-to-add-marketo-measure-js-via-google-tag-manager}

1. Open GTM en voeg de [!DNL Marketo Measure] script op uw websitecontainer. Zorg ervoor dat u **[!UICONTROL Custom HTML tag]**.

1. Gebruik de [!DNL Marketo Measure] hieronder en neem het in uw container op.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Klikken **[!UICONTROL Add a Firing Rule]** zodat je Google kunt vertellen ons fragment te laden op *Alle pagina&#39;s*.

1. Ga naar de sectie van het Overzicht van het Concept van de Container op de linkerzijde. Klik op de knop om een nieuwe versie van de container te maken en de wijzigingen te publiceren.
