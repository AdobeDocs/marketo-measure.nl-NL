---
unique-page-id: 35586069
description: Garandeerde toestemming voor GDPR in Marketo Measure Js - Marketo Measure - Productdocumentatie
title: Ervoor zorgen dat toestemming voor GDPR in Marketo Measure Js
exl-id: 9afc5e4d-cf97-4c49-b9ee-ee1cc99c1f90
feature: Tracking
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 0%

---

# Ervoor zorgen dat toestemming voor GDPR in Marketo Measure Js {#ensuring-consent-for-gdpr-in-marketo-measure-js}

De algemene verordening inzake gegevensbescherming (GDPR) is een wetgeving van de Europese Unie die op 25 mei 2018 in werking is getreden.

## Overzicht {#overview}

Het doel van de GDPR is de rechten van betrokkenen binnen de Europese Unie (EU) en de Europese Economische Ruimte (EER) te versterken met betrekking tot de wijze waarop hun persoonsgegevens worden gebruikt en beschermd. &quot;Persoonsgegevens&quot; zijn gegevens die betrekking hebben op een geïdentificeerde of identificeerbare natuurlijke persoon. De GDPR is van toepassing op elke organisatie binnen of buiten de EU die goederen of diensten verkoopt aan en/of het gedrag volgt van betrokkenen binnen de EU en de EER. Als je zaken doet met betrokkenen in Europa die de verwerking van hun persoonsgegevens impliceren, dan is deze wetgeving op jou van toepassing. De sancties wegens niet-naleving zijn aanzienlijk, met grote boetes voor degenen die de verordening overtreden; de maximumboete voor één enkele inbreuk bedraagt 20 miljoen euro of 4% van de wereldwijde jaaromzet, afhankelijk van wat het grootst is.

Standaard, [!DNL bizible.js] verzamelt analysegegevens van gebruikers tenzij het wordt gevormd om op toestemming te wachten. Wanneer [!DNL bizible.js] is geconfigureerd om te wachten op toestemming van de gebruiker, worden er pas cookies gemaakt of analytische gegevens verzonden nadat de toestemming is bereikt.

## Hoe te op Toestemming wachten {#how-to-wait-for-consent}

U kunt op twee manieren instellen [!DNL bizible.js] wachten op toestemming.

Optie 1 - De standaardinstelling vervangen [!DNL bizible.js] scripttag met:

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-consent-button-id="ConsentButtonId"></script>`

**Als u [!DNL Google Tag Manager] om script te installeren** Houd er rekening mee dat GTM gegevenskenmerken verwijdert, dus gebruik in plaats daarvan het volgende script:

`<span id="bizible-settings" data-consent-button-id="ConsentButtonId"></span>`
`<script type="text/javascript" src=https://cdn.bizible.com/scripts/bizible.js async=""></script>`

>[!NOTE]
>
>In dit geval: [!DNL bizible.js] Koppelt een gebeurtenis on-click aan het HTML-element met id &quot;ConsentButtonId&quot;.

Wanneer op dit HTML-element wordt geklikt, [!DNL bizible.js] wordt een cookie gemaakt om te onthouden dat de toestemming van de gebruiker is ontvangen en dat wordt begonnen met het verzamelen van analysegegevens zoals gewoonlijk.

**-of-**

Optie 2 - De standaardinstelling vervangen [!DNL bizible.js] scripttag met:

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-requires-user-consent="true"></script>`

Dit vertelt [!DNL bizible.js] om niet te volgen tot de toestemming wordt bereikt, wat met de volgende JS API kan worden gedaan:

*venster[&quot;Bizible&quot;] = venster[&quot;Bizible&quot;] || {_wachtrij: [], Push: function (o, p) { this._queue.push({ type: o, data: p }); };*

*Bizible. Push(&#39;Consent&#39;, true);*

**Als u [!DNL Google Tag Manager] om script te installeren** Houd er rekening mee dat GTM gegevenskenmerken verwijdert, dus gebruik in plaats daarvan het volgende script:

`<span id="bizible-settings" data-requires-user-consent="true"></span>`
`<script type="text/javascript" src=https://cdn.bizible.com/scripts/bizible.js async=""></script>`

>[!NOTE]
>
>bizible.js zal een koekje tot stand brengen om zich te herinneren dat de toestemming van de gebruiker is ontvangen en begint analysegegevens te verzamelen zoals gewoonlijk slechts nadat JS API wordt geroepen.

Klanten kunnen deze API daarentegen ook gebruiken om de toestemming van de gebruiker in te trekken:

`window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) { this._queue.push({ type: o, data: p }); } };`

`Bizible.Push('Consent', false);`

Wanneer deze code wordt uitgevoerd, worden alle cookies verwijderd die [!DNL bizible.js] die eerder zijn gemaakt en de verzameling van analysegegevens alleen hervat als de gebruiker hiermee instemt.
