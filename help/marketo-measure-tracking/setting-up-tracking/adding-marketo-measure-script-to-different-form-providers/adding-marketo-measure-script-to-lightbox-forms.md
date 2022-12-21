---
unique-page-id: 18874519
description: Toevoegen [!DNL Marketo Measure] Script naar lichtbak Forms - [!DNL Marketo Measure] - Productdocumentatie
title: Toevoegen [!DNL Marketo Measure] Script naar lichtbak Forms
exl-id: fa9ce480-fc4f-4abd-8555-dbb74849747e
source-git-commit: ae5b77744d523606ce6cfcf48d7e8d5049d5ccb7
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 0%

---

# Toevoegen [!DNL Marketo Measure] Script naar lichtbak Forms {#adding-marketo-measure-script-to-lightbox-forms}

Leer hoe u de [!DNL Marketo Measure] JavaScript naar een formulier in een lichtbak.

Met een lichtbak wordt een formulier vóór de inhoud geopend wanneer de bezoeker een bepaalde handeling uitvoert (bijvoorbeeld op een bepaald gedeelte van de pagina klikken, een bepaalde periode op de pagina doorbrengen, enz.). Doorgaans vragen we alleen om de [!DNL Marketo Measure] JavaScript geplaatst in het hoofd van de landingspagina, maar voor formulieren binnen een lichtbak is er één extra stap nodig.

Aangezien een formulier in een lichtbak in feite een formulier binnen een iFrame is, hebben we ons script nodig dat in dat iFrame is geplaatst.

Zoek eerst het iFrame op de [!UICONTROL lightbox] leven in.

![](assets/1.png)

Vervolgens plaatst u de [!DNL Marketo Measure] JavaScript in het iFrame.

![](assets/2.png)

Wanneer JavaScript is toegevoegd, wordt u ten slotte aangeraden formulierverzendingen te valideren door de volgende aanwijzingen te volgen:

1. Kopieer de URL van de bestemmingspagina die de [!UICONTROL lightbox] formulier.
1. Open een Incognito-browser en plak de URL.
1. Verzend het formulier met een uniek e-mailadres.
1. Bevestig dat de test is bijgehouden door uw CRM te controleren op het unieke e-mailadres dat wordt gebruikt. Controleer of de aanraakpuntgegevens worden ingevuld.
