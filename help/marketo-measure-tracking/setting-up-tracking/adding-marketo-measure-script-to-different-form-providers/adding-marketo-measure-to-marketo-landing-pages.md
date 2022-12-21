---
unique-page-id: 18874755
description: Toevoegen [!DNL Marketo Measure] tot [!DNL Marketo] Aanlandingspagina's - [!DNL Marketo Measure] - Productdocumentatie
title: Toevoegen [!DNL Marketo Measure] naar Marketo-bestemmingspagina's
exl-id: 3771d4d2-8723-452a-b23d-cea3b11ab9ee
source-git-commit: 82cc8269bfdb26b6acf039d0ce0e06564f5e2612
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 0%

---

# Toevoegen [!DNL Marketo Measure] naar Marketo-bestemmingspagina&#39;s {#adding-marketo-measure-to-marketo-landing-pages}

Leer hoe u tekstspatiëring toevoegt aan [!DNL Marketo Engage] De Pagina&#39;s van de landing aangezien zij extra behandeling vereisen. [!DNL Marketo Measure] JavaScript moet aanwezig zijn op zowel de bestemmingspagina als de [!DNL Marketo Engage] zelf te vormen. Hiervoor moet u de opdracht [!DNL Marketo Measure] JavaScript in [!DNL Marketo Engage] zoals uitgelegd in de volgende aanwijzingen.

>[!NOTE]
>
>Als u JavaScript implementeert via een tagbeheerprovider, zoals [!DNL Google Tag Manager]hoeft u niet handmatig toe te voegen [!DNL Marketo Measure] JS naar [!DNL Marketo Engage].

## Toevoegen [!DNL Marketo Measure] Script naar [!DNL Marketo Engage] Openingspagina&#39;s {#how-to-add-marketo-measure-script-to-marketo-engage-landing-pages}

1. Meld u aan bij uw [!DNL Marketo Engage] account.
1. Selecteer de openingspagina en klik op **[!UICONTROL Edit Draft]**.
1. Sleep in het element HTML.
1. Voer de [!DNL Marketo Measure] JavaScript in de [!UICONTROL head] sectie:

   `<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

Voorbeeld in onderstaande schermafbeelding

1. Klik op **[!UICONTROL Save]**.

   ![](assets/adding-bizible-to-marketo-landing-pages-1.png)

## Aanvullende opmerkingen {#additional-notes}

* Mogelijk hebt u al andere codefragmenten voor tekstspatiëring, zoals een [!DNL Google Analytics] code. Er is geen probleem met dit, zorg ervoor dat u ze met een puntkomma van elkaar scheidt `;` en één spatie. Een voorbeeld van hoe dit eruit zou zien:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>; <script async="true" type="someothercode" src="someotherfile.js" ></script>`

* Het is waarschijnlijk dat u veelvoudige het Bestaan van de Pagina malplaatjes in gebruik hebt, ben zeker om de code aan alle malplaatjes toe te voegen die vormen op hen hebben.

* Soms moet u bij het bewerken van de sjabloon voor bestemmingspagina&#39;s de pagina&#39;s waarop de bestemmingspagina wordt gebruikt opnieuw goedkeuren. In dit artikel wordt uitgelegd [massagoedkeuring](https://experienceleague.adobe.com/docs/marketo/using/product-docs/demand-generation/landing-pages/landing-page-actions/approve-multiple-landing-pages-at-once.html){target=&quot;_blank&quot;}.
