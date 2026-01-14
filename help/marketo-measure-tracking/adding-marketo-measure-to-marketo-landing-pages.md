---
description: Het toevoegen van  [!DNL Marketo Measure]  aan Marketo die de richtlijnen van de Pagina's voor de gebruikers van Marketo Measure Landing
title: Toevoegend  [!DNL Marketo Measure]  aan Marketo het Landen Pagina's
exl-id: 3771d4d2-8723-452a-b23d-cea3b11ab9ee
feature: Tracking
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 0%

---

# [!DNL Marketo Measure] toevoegen aan Marketo-bestemmingspagina&#39;s {#adding-marketo-measure-to-marketo-landing-pages}

Leer hoe u reeksspatiëring toevoegt aan [!DNL Marketo Engage] bestemmingspagina&#39;s omdat deze extra verwerkingstijd vereisen. [!DNL Marketo Measure] JavaScript moet aanwezig zijn op zowel de landingspagina als het [!DNL Marketo Engage] -formulier zelf. Hiervoor moet u de [!DNL Marketo Measure] JavaScript in [!DNL Marketo Engage] laden, zoals in de volgende instructies wordt uitgelegd.

>[!NOTE]
>
>Als u de JavaScript implementeert via een tagbeheerprovider zoals [!DNL Google Tag Manager] , hoeft u [!DNL Marketo Measure] JS niet handmatig aan [!DNL Marketo Engage] toe te voegen.

## [!DNL Marketo Measure] Script toevoegen aan [!DNL Marketo Engage] bestemmingspagina&#39;s {#how-to-add-marketo-measure-script-to-marketo-engage-landing-pages}

1. Meld u aan bij uw [!DNL Marketo Engage] -account.
1. Selecteer de openingspagina en klik op **[!UICONTROL Edit Draft]** .
1. Sleep in het HTML-element.
1. Voer de [!DNL Marketo Measure] JavaScript in de [!UICONTROL head] -sectie in:

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

Voorbeeld in onderstaande schermafbeelding

1. Klik op **[!UICONTROL Save]**.

   ![](assets/adding-pages-1.png)

## Aanvullende opmerkingen {#additional-notes}

* Mogelijk hebt u al andere codefragmenten voor tekstspatiëring, zoals een [!DNL Google Analytics] -code. Er is geen probleem met dit. Zorg ervoor dat u de objecten scheidt met een puntkomma `;` en één spatie. Een voorbeeld van hoe dit eruit zou zien:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`

* Het is waarschijnlijk dat u veelvoudige het Bestaan van de Pagina malplaatjes in gebruik hebt, ben zeker om de code aan alle malplaatjes toe te voegen die vormen op hen hebben.

* Wanneer u de sjabloon voor bestemmingspagina&#39;s bewerkt, moet u soms de pagina&#39;s die de bestemmingspagina gebruikt, opnieuw goedkeuren. Dit artikel verklaart [ hoe te om massa goed te keuren ](https://experienceleague.adobe.com/docs/marketo/using/product-docs/demand-generation/landing-pages/landing-page-actions/approve-multiple-landing-pages-at-once.html){target="_blank"}.
