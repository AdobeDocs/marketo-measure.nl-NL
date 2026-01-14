---
description: AJAX Form Handling Guidance for Marketo Measure users
title: AJAX-formulierverwerking
exl-id: 042e42ff-d8d9-4380-b878-aba4934bc4a0
feature: Tracking
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 0%

---

# AJAX-formulierverwerking {#ajax-form-handling}

Voor het handmatig rapporteren van klantconversies naar [!DNL Marketo Measure] is er een eenvoudige API die u kunt gebruiken. Beide JavaScript API&#39;s zijn automatisch beschikbaar op uw site als er trackingcode op staat. Het is niet nodig om iets speciaals te doen om toegang te krijgen.

## Scenario 1 - HTML-formulier met AJAX verzenden {#scenario-html-form-with-an-ajax-submit}

Wanneer u formulieren met AJAX (of een ander mechanisme) gebruikt om conversiedatums van de client naar onze servers te verzenden, is het mogelijk dat [!DNL Marketo Measure] niet op de hoogte is van de klantconversie via de standaardpaden die we controleren. In dit scenario kunnen we een eenvoudige API gebruiken (zie hieronder).

Als u uw eigen formulierverzendingen verwerkt, kunt u [!DNL Marketo Measure] expliciet aanroepen vanuit de JavaScript. [!DNL Marketo Measure] verzamelt alle relevante informatie in het formulier en plaatst deze asynchroon op onze servers.

**hieronder is een codesteekproef gebruikend JQuery (veronderstellend identiteitskaart op de vorm is &quot;formId&quot;):**

```javascript
///////////////////////////////////////////////////////////////////////  
// Preamble for all API usage.  
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };  
  
// Give Marketo Measure the JQuery Selector for the form and we'll collect the data automatically.  
Bizible.Push('Form',$('#*formId*'));
```

**hieronder is een codesteekproef die geen JQuery gebruikt (veronderstellend identiteitskaart op de vorm is &quot;formId&quot;):**

```javascript
///////////////////////////////////////////////////////////////////////  
// Preamble for all API usage.  
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };  
  
// Give Marketo Measure the Form ID and we'll collect the data automatically.
Bizible.Push('Form','MyFormID');
```

## Scenario 2 - Loodinformatie verzameld in een niet-HTML-formulier {#scenario-lead-information-collected-in-a-non-html-form}

Als informatie uit een geconverteerde lead wordt verzameld met JavaScript of eenvoudige tekstvelden zonder HTML-formulier, werkt deze oplossing voor u. Hieronder wordt de API gedeeld die in dit scenario moet worden gebruikt:

```javascript
///////////////////////////////////////////////////////////////////////  
// Preamble for all API usage.  
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };  
  
// If your site is using Ajax, or you are running a secure site, it is best to send us the data directly.  
Bizible.Push('User', {
eMail: 'user@gmail.com' // required  
});  
```

In deze code is het veld [!UICONTROL email] vereist. [!DNL Marketo Measure] plaatst deze gegevens asynchroon op onze servers.

## Scenario 3 - de gebruikersinformatie van het Rapport van de dank-u pagina {#scenario-report-user-information-from-the-thank-you-page}

Soms is het handiger om de leidende informatie naar [!DNL Marketo Measure] te melden vanaf de pagina voor bedankt, nadat het formulier is verzonden. De eenvoudigste manier om deze informatie te rapporteren is door een verborgen element toe te voegen aan de pagina die informatie bevat van het verzenden van het formulier. [!DNL Bizible.js] leest deze informatie als de pagina &quot;Bedankt&quot; is geladen.

**bijvoorbeeld:**

```html
<div id="bizible.reportUser" style="display:none"  
data-email="user@gmail.com">  
```

Het maakt niet uit of het verborgen element een div-, script- of ander labeltype is. [!DNL Marketo Measure] zoekt naar id=&quot;bizible.reportUser&quot; om de informatie te lezen.
