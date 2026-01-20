---
unique-page-id: 18874749
description: Toevoegend  [!DNL Marketo Measure]  Manuscript aan  [!DNL Uberflip]  Forms -  [!DNL Marketo Measure]
title: Toevoegend  [!DNL Marketo Measure]  Manuscript aan  [!DNL Uberflip]  Forms
exl-id: fb123e15-523d-4931-b4c1-705fe49be3d0
feature: Tracking
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 0%

---

# [!DNL Marketo Measure] Script toevoegen aan [!DNL Uberflip] Forms {#adding-marketo-measure-script-to-uberflip-forms}

Als u momenteel [!DNL Uberflip] gebruikt om uw inhoud te beheren, is het belangrijk dat u de volgende stappen uitvoert om ervoor te zorgen dat [!DNL Marketo Measure] deze verzonden formulieren bijhoudt. Uw Succesbeheer op [!DNL Uberflip] moet u hierbij ook kunnen helpen.

1. Voeg dit script toe aan de [!DNL Uberflip] [!UICONTROL Custom Code>HTML] -sectie.

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

1. Zorg ervoor dat deze [!DNL Marketo Measure] preamble-code wordt geactiveerd bij het laden van de pagina en bij het wijzigen van de AJAX-pagina. Doe dit binnen de [!UICONTROL Custom Code>JS] sectie

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   Voeg deze preambule toe aan de [!DNL Hubs.onLoad] en de [!DNL Hubs.onPageChange] AJAX JavaScript-gebeurtenishaken hieronder. (Opmerking: in deze gebeurtenishaken kunt u ook andere code gebruiken. Zorg ervoor dat u ook de preambule opneemt.)

   `Hubs.onLoad = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

   `Hubs.onPageChange = function () {`

   `window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`

   `}`

1. Maak en definieer een functie die gegevens naar Bizible duwt bij het verzenden van een Form CTA. Hier komt de sectie [!UICONTROL Custom Code>JavaScript] . (Opmerking: deze functie vereist alleen de ctaData-parameter die Uberflip biedt, maar u kunt de andere parameters ctaId en ctaName opnemen voor het geval de gebruiker zijn code wil aanpassen om deze gegevens ook door te geven).

   `function bizibleFormCode(ctaId, ctaData, ctaName) {`
   `var email = ctaData["email"];`
   `if(email){`
   `Bizible.Push('User', {`
   `eMail: email, // required`
   `}); }`

   `}`

1. Wanneer een formulier-CTA wordt verzonden, moet de functie [!DNL Marketo Measure] hieronder worden uitgevoerd. Dit gebeurt binnen de sectie [!UICONTROL Custom Code>JS] . (Nota: U zou andere code binnen de de gebeurtenishaak van de gebeurtenis Hubs.onCtaFormSubmitSuccess JavaScript kunnen hebben, zorg ervoor u deze functievraag eveneens omvat).

   `Hubs.onCtaFormSubmitSuccess = function (ctaId, ctaData, ctaName) {`
   `bizibleFormCode(ctaId, ctaData, ctaName);`\
   `}`
