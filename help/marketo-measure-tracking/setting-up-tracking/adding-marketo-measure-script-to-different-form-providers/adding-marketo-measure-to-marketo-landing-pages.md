---
unique-page-id: 18874755
description: Toevoegen [!DNL Marketo Measure] tot [!DNL Marketo] Aanlandingspagina's - [!DNL Marketo Measure]
title: Toevoegen [!DNL Marketo Measure] naar Marketo-bestemmingspagina's
exl-id: 3771d4d2-8723-452a-b23d-cea3b11ab9ee
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# Toevoegen [!DNL Marketo Measure] naar Marketo-bestemmingspagina&#39;s {#adding-marketo-measure-to-marketo-landing-pages}

Leer hoe u tekstspatiëring toevoegt aan [!DNL Marketo Engage] De Pagina&#39;s van de landing aangezien zij extra behandeling vereisen. [!DNL Marketo Measure] JavaScript moet aanwezig zijn op zowel de bestemmingspagina als de [!DNL Marketo Engage] zelf vorm te geven. Hiervoor moet u de opdracht [!DNL Marketo Measure] JavaScript in [!DNL Marketo Engage] zoals uitgelegd in de volgende aanwijzingen.

>[!NOTE]
>
>Als u JavaScript implementeert via een tagbeheerprovider, zoals [!DNL Google Tag Manager]hoeft u niet handmatig toe te voegen [!DNL Marketo Measure] JS naar [!DNL Marketo Engage].

## Toevoegen [!DNL Marketo Measure] Script naar [!DNL Marketo Engage] Openingspagina&#39;s {#how-to-add-marketo-measure-script-to-marketo-engage-landing-pages}

1. Aanmelden bij uw [!DNL Marketo Engage] account.
1. Selecteer de openingspagina en klik op **[!UICONTROL Edit Draft]**.
1. Sleep in het element HTML.
1. Voer de [!DNL Marketo Measure] JavaScript in de [!UICONTROL head] sectie:

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

Voorbeeld in onderstaande schermafbeelding

1. Klik op **[!UICONTROL Save]**.

   ![](assets/adding-bizible-to-marketo-landing-pages-1.png)

## Aanvullende opmerkingen {#additional-notes}

* Mogelijk hebt u al andere codefragmenten voor tekstspatiëring, zoals een [!DNL Google Analytics] code. Er is geen probleem met dit, zorg ervoor dat u ze scheidt met een puntkomma `;` en één spatie. Een voorbeeld van hoe dit eruit zou zien:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`

* Het is waarschijnlijk dat u veelvoudige het Bestaan van de Pagina malplaatjes in gebruik hebt, ben zeker om de code aan alle malplaatjes toe te voegen die vormen op hen hebben.

* Wanneer u de sjabloon voor bestemmingspagina&#39;s bewerkt, moet u soms de pagina&#39;s die de bestemmingspagina gebruikt, opnieuw goedkeuren. In dit artikel wordt uitgelegd [massagoedkeuring](https://experienceleague.adobe.com/docs/marketo/using/product-docs/demand-generation/landing-pages/landing-page-actions/approve-multiple-landing-pages-at-once.html?lang=nl-NL){target="_blank"}.
