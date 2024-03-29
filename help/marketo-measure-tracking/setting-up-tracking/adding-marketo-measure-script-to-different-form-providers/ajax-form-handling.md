---
unique-page-id: 18874745
description: Formulierverwerking AJAX - [!DNL Marketo Measure]
title: Formulierverwerking AJAX
exl-id: 042e42ff-d8d9-4380-b878-aba4934bc4a0
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 0%

---

# Formulierverwerking AJAX {#ajax-form-handling}

Om klantenomzettingen aan manueel te melden [!DNL Marketo Measure]Er is een eenvoudige API die u kunt gebruiken. Beide JavaScript-API&#39;s zijn automatisch beschikbaar op uw site als er trackingcode op staat. Het is niet nodig om iets speciaals te doen om toegang te krijgen.

## Scenario 1 - HTML formulier met AJAX verzenden {#scenario-html-form-with-an-ajax-submit}

Wanneer u formulieren gebruikt die AJAX (of een ander mechanisme) bevatten om conversiedatums van de client naar onze servers te verzenden, [!DNL Marketo Measure] misschien niet bewust van de klantenomzetting door om het even welke standaardwegen die wij controleren. In dit scenario kunnen we een eenvoudige API gebruiken (zie hieronder).

Als u uw eigen formulierverzendingen verwerkt, kunt u expliciet [!DNL Marketo Measure] in het JavaScript. [!DNL Marketo Measure] verzamelt alle relevante informatie in het formulier en plaatst deze asynchroon op onze servers.

**Hieronder ziet u een codevoorbeeld met JQuery (ervan uitgaande dat de id in het formulier &quot;formId&quot; is):**

```jquery
///////////////////////////////////////////////////////////////////////  
// Preamble for all API usage.  
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };  
  
// Give Marketo Measure the JQuery Selector for the form and we'll collect the data automatically.  
Bizible.Push('Form',$('#*formId*'));
```

**Hieronder ziet u een codevoorbeeld waarin JQuery niet wordt gebruikt (er wordt aangenomen dat de id op het formulier &quot;formId&quot; is):**

```jquery
///////////////////////////////////////////////////////////////////////  
// Preamble for all API usage.  
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };  
  
// Give Marketo Measure the Form ID and we'll collect the data automatically.
Bizible.Push('Form','MyFormID');
```

## Scenario 2 - Loodinformatie verzameld in een niet-HTML vorm {#scenario-lead-information-collected-in-a-non-html-form}

Als informatie uit een geconverteerde lead wordt verzameld met behulp van JavaScript of eenvoudige tekstvelden zonder HTML-formulier, werkt deze oplossing voor u. Hieronder wordt de API gedeeld die in dit scenario moet worden gebruikt:

```jquery
///////////////////////////////////////////////////////////////////////  
// Preamble for all API usage.  
window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };  
  
// If your site is using Ajax, or you are running a secure site, it is best to send us the data directly.  
Bizible.Push('User', {
eMail: 'user@gmail.com' // required  
});  
```

In deze code [!UICONTROL email] is vereist. [!DNL Marketo Measure] deze gegevens asynchroon op onze servers plaatsen.

## Scenario 3 - de gebruikersinformatie van het Rapport van de dank-u pagina {#scenario-report-user-information-from-the-thank-you-page}

Soms is het handiger om de hoofdinformatie te melden aan [!DNL Marketo Measure] op de pagina &quot;Bedankt&quot;, nadat het formulier is verzonden. De eenvoudigste manier om deze informatie te rapporteren is door een verborgen element toe te voegen aan de pagina die informatie bevat van de formulierverzending, en [!DNL Bizible.js] Deze gegevens worden gelezen wanneer de pagina &quot;Bedankt&quot; is geladen.

**Bijvoorbeeld:**

```html
<div id="bizible.reportUser" style="display:none"  
data-email="user@gmail.com">  
```

Het maakt niet uit of het verborgen element een div-, script- of ander labeltype is. [!DNL Marketo Measure] zoekt id=&quot;bizible.reportUser&quot;om de informatie te lezen.
