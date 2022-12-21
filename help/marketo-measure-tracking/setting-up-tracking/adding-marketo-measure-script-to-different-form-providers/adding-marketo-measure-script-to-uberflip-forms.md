---
unique-page-id: 18874749
description: Toevoegen [!DNL Marketo Measure] Script naar [!DNL Uberflip] Forms - [!DNL Marketo Measure] - Productdocumentatie
title: Toevoegen [!DNL Marketo Measure] Script naar [!DNL Uberflip] Forms
exl-id: fb123e15-523d-4931-b4c1-705fe49be3d0
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 0%

---

# Toevoegen [!DNL Marketo Measure] Script naar [!DNL Uberflip] Forms {#adding-marketo-measure-script-to-uberflip-forms}

Als u momenteel [!DNL Uberflip] om uw inhoud te beheren, is het belangrijk dat u deze noodzakelijke stappen neemt om ervoor te zorgen dat [!DNL Marketo Measure] volgt deze formulierverzendingen. Je succesbeheer op [!DNL Uberflip] U moet u daarbij ook kunnen helpen.

1. Dit script toevoegen aan [!DNL Uberflip]s [!UICONTROL Custom Code>HTML] sectie.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Zorg ervoor dat [!DNL Marketo Measure] preambule codebrand op zowel paginading als AJAX paginaverandering. Doe dit binnen de [!UICONTROL Custom Code>JS] sectie

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   U voegt deze preambule aan beide toe [!DNL Hubs.onLoad] en de [!DNL Hubs.onPageChange] AJAX JavaScript-gebeurtenishaken hieronder. (Opmerking: U kunt ook andere codes in deze gebeurtenishaken hebben. Zorg dat u ook de preambule opneemt.)

   `Hubs.onLoad = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

   `Hubs.onPageChange = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

1. Maak en definieer een functie waarmee gegevens naar Bizible worden geduwd op het verzenden van een Form CTA. Dit gaat over de [!UICONTROL Custom Code>Javascript] sectie. (Opmerking: deze functie vereist slechts de parameter ctaData Uberflip verstrekt, maar u kunt de andere parameters ctaId en ctaName omvatten voor het geval de gebruiker hun code wil aanpassen om deze gegevens eveneens over te gaan).

   `function bizibleFormCode(ctaId, ctaData, ctaName) {`
   `var email = ctaData["email"];`
   `if(email){`
   `Bizible.Push('User', {`
   `eMail: email, // required`
   `}); }`

   `}`

1. Wanneer een formulier-CTA wordt verzonden, moet u ervoor zorgen dat [!DNL Marketo Measure] functie wordt hieronder uitgevoerd. Dit wordt gedaan binnen [!UICONTROL Custom Code>JS] sectie. (Opmerking: U zou andere code binnen de de gebeurtenishaak kunnen hebben Hubs.onCtaFormSubmitSuccess javascript, zorg enkel ervoor u deze functievraag eveneens omvat).

   `Hubs.onCtaFormSubmitSuccess = function (ctaId, ctaData, ctaName) {`
   `bizibleFormCode(ctaId, ctaData, ctaName);`\
   `}`
