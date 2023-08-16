---
unique-page-id: 30082018
description: Vertraagde synchronisatie van cookies - [!DNL Marketo Measure] - Productdocumentatie
title: Vertraagde synchronisatie van cookies
exl-id: 394053ed-5642-48e4-b83c-c483a58ebbd7
feature: Tracking
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# Vertraagde synchronisatie van cookies {#delayed-cookie-sync}

Deze wijziging in de standaardinstelling [!DNL Marketo Measure] Javascript biedt [!DNL bizible.js] API-ondersteuning, zodat u de JS kunt configureren om gebruikersactiviteiten van bezoekers tijdelijk op te slaan, maar de informatie niet naar de [!DNL Marketo Measure] tot de gebruiker hiermee instemt.

## Procedure {#how-to}

De standaardinstelling vervangen [!DNL bizible.js] scripttag met het volgende:

`<script id="bizible-settings" type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" data-consent-button-id="ConsentButtonId"></script>`

Het kenmerk data-permission-button-id=&quot;ConsentButtonId&quot; vertelt [!DNL bizible.js] om geen analysegegevens te verzenden tot een element van HTML met die identiteitskaart wordt geklikt.

Als alternatief kunnen klanten de [!UICONTROL data-consent-button-id] niet bestaat (bijvoorbeeld &quot;voetbalk&quot;) en gebruikt de volgende API om [!DNL bizible.js] dat de gebruiker heeft ingestemd met:

`window['Bizible'] = window['Bizible'] || { _queue: [], Push: function (o, p) {this._queue.push({ type: o, data: p }); } };`
`Bizible.Push("Consent", true });`

>[!NOTE]
>
>De toestemming van de gebruiker wordt bewaard in het koekje, betekenend dat zodra de gebruiker heeft ingestemd zodra er geen behoefte is om deze vraag op om het even welke verdere pagina&#39;s uit te voeren.

## Beperking {#limitation}

Omdat [!DNL bizible.js] tijdelijke opslag van niet-verzonden webactiviteiten in cookies van de eerste partij van de klant en de grootte van cookies van de eerste partij zijn beperkt, zodat op elk moment slechts drie niet-verzonden aanvragen kunnen worden opgeslagen.

Als er al drie verzoeken in behandeling zijn, worden alle volgende activiteiten genegeerd. Dit betekent dat de eerste pagina behouden blijft, die waardevolle informatie over de verwijzende persoon bevat.
