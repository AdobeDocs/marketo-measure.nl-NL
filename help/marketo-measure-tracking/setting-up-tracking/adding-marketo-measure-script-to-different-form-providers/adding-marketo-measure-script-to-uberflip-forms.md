---
unique-page-id: 18874749
description: Toevoegen [!DNL Marketo Measure] Script naar [!DNL Uberflip] FORMS - [!DNL Marketo Measure]
title: Toevoegen [!DNL Marketo Measure] Script naar [!DNL Uberflip] Forms
exl-id: fb123e15-523d-4931-b4c1-705fe49be3d0
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 0%

---

# Toevoegen [!DNL Marketo Measure] Script naar [!DNL Uberflip] Forms {#adding-marketo-measure-script-to-uberflip-forms}

Als u momenteel [!DNL Uberflip] om uw inhoud te beheren, is het belangrijk dat u deze noodzakelijke stappen neemt om ervoor te zorgen dat [!DNL Marketo Measure] volgt deze formulierverzendingen. Je succesbeheer op [!DNL Uberflip] U moet u daarbij ook kunnen helpen.

1. Dit script toevoegen aan [!DNL Uberflip]s [!UICONTROL Custom Code>HTML] sectie.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Zorg ervoor dat [!DNL Marketo Measure] preambule codebrand op zowel paginading als AJAX paginaverandering. Doe dit binnen de [!UICONTROL Custom Code>JS] sectie

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   Deze preambule toevoegen aan beide [!DNL Hubs.onLoad] en de [!DNL Hubs.onPageChange] AJAX JavaScript-gebeurtenishaken hieronder. (Opmerking: in deze gebeurtenishaken kunt u ook andere code gebruiken. Zorg ervoor dat u ook de preambule opneemt.)

   `Hubs.onLoad = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

   `Hubs.onPageChange = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

1. Maak en definieer een functie die gegevens naar Bizible duwt bij het verzenden van een Form CTA. Dit gaat over de [!UICONTROL Custom Code>JavaScript] sectie. (Opmerking: deze functie vereist alleen de ctaData-parameter die Uberflip biedt, maar u kunt de andere parameters ctaId en ctaName opnemen voor het geval de gebruiker zijn code wil aanpassen om deze gegevens ook door te geven).

   `function bizibleFormCode(ctaId, ctaData, ctaName) {`
   `var email = ctaData["email"];`
   `if(email){`
   `Bizible.Push('User', {`
   `eMail: email, // required`
   `}); }`

   `}`

1. Wanneer een formulier-CTA wordt verzonden, moet u ervoor zorgen dat [!DNL Marketo Measure] functie wordt hieronder uitgevoerd. Dit wordt gedaan binnen [!UICONTROL Custom Code>JS] sectie. (Opmerking: mogelijk hebt u andere code binnen de JavaScript-gebeurtenishaak Hubs.onCtaFormSubmitSuccess, en zorg ervoor dat u deze functieaanroep ook opneemt.)

   `Hubs.onCtaFormSubmitSuccess = function (ctaId, ctaData, ctaName) {`
   `bizibleFormCode(ctaId, ctaData, ctaName);`\
   `}`
