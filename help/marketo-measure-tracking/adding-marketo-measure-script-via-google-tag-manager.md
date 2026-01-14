---
description: Het toevoegen van  [!DNL Marketo Measure]  Manuscript via  [!DNL Google Tag Manager]  begeleiding voor de gebruikers van Marketo Measure
title: Toevoegend  [!DNL Marketo Measure]  Manuscript via  [!DNL Google Tag Manager]
exl-id: 539efb10-35cb-4146-8eea-728c3948a11e
feature: Tracking
hidefromtoc: true
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 0%

---

# [!DNL Marketo Measure] Script toevoegen via [!DNL Google Tag Manager] {#adding-marketo-measure-script-via-google-tag-manager}

Wanneer het installeren van [!DNL Marketo Measure] JavaScript, wordt het geadviseerd dat u [&#x200B; hard-code het manuscript &#x200B;](/help/marketo-measure-tracking/adding-marketo-measure-script.md){target="_blank"} direct in de plaats. Als dat niet mogelijk is, kunt u ook [!DNL Google Tag Manager] (GTM) gebruiken om de [!DNL Marketo Measure] JS te laden. [!DNL Marketo Measure] JS die via GTM wordt geladen, is gevoelig voor latentie. Latentie veroorzaakt een vertraging in de laadtijden van scripts, waardoor ongeveer 3-5% van alle ingevulde formulieren kan ontbreken.

Als u besluit om ons script toe te voegen via GTM, stelt u het script van [!DNL Marketo Measure] in op de hoogste prioriteit in de volgorde waarin het wordt gemaakt en zorgt u ervoor dat er geen synchrone scripts staan vóór de tag [!DNL Marketo Measure] om effecten van GTM-latentie te beperken.

>[!NOTE]
>
>Gebruik dit [&#x200B; steunartikel door Google &#x200B;](https://support.google.com/tagmanager/answer/2772421?hl=en){target="_blank"} om meer te leren.

## [!DNL Marketo Measure] JS toevoegen via [!DNL Google Tag Manager] {#how-to-add-marketo-measure-js-via-google-tag-manager}

1. Open GTM en voeg het script [!DNL Marketo Measure] toe op uw websitecontainer. Zorg dat u **[!UICONTROL Custom HTML tag]** selecteert.

1. Gebruik het onderstaande script van [!DNL Marketo Measure] en neem het op in uw container.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Klik **[!UICONTROL Add a Firing Rule]** zodat kunt u Google vertellen om ons fragment op *te laden Alle Pagina&#39;s*.

1. Ga naar de sectie van het Overzicht van het Concept van de Container op de linkerzijde. Klik op de knop om een versie van de container te maken en de wijzigingen te publiceren.
