---
unique-page-id: 18874519
description: Toevoegen [!DNL Marketo Measure] Script naar lichtbak Forms - [!DNL Marketo Measure]
title: Toevoegen [!DNL Marketo Measure] Script naar lichtbak Forms
exl-id: fa9ce480-fc4f-4abd-8555-dbb74849747e
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---

# Toevoegen [!DNL Marketo Measure] Script naar lichtbak Forms {#adding-marketo-measure-script-to-lightbox-forms}

Leer hoe u de [!DNL Marketo Measure] JavaScript naar een formulier in een lichtbak.

Met een lichtbak wordt een formulier vóór de inhoud geopend wanneer de bezoeker een bepaalde actie uitvoert (door op een bepaald gedeelte van de pagina te klikken, een bepaalde tijd op de pagina door te brengen, enzovoort). We vragen meestal om de opdracht [!DNL Marketo Measure] JavaScript geplaatst in het hoofd van de landingspagina, maar voor formulieren binnen een lichtbak is er één extra stap nodig.

Aangezien een formulier in een lichtbak in feite een formulier binnen een iFrame is, wordt het script in dat iFrame geplaatst.

Zoek eerst het iFrame op de [!UICONTROL lightbox] leven in.

![](assets/1.png)

Vervolgens plaatst u de [!DNL Marketo Measure] JavaScript in het iFrame.

![](assets/2.png)

Wanneer JavaScript wordt toegevoegd, worden formulierverzendingen ten slotte in de volgende richtingen bijgehouden:

1. Kopieer de URL van de bestemmingspagina die de [!UICONTROL lightbox] formulier.
1. Open een Incognito-browser en plak de URL.
1. Verzend het formulier met een uniek e-mailadres.
1. Bevestig dat de test is gevolgd door uw CRM te controleren op het unieke e-mailadres dat wordt gebruikt. Controleer of de aanraakpuntgegevens worden gevuld.
