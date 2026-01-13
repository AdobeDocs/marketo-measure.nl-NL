---
description: Toevoegend  [!DNL Marketo Measure]  Manuscript aan Lichtbak Forms -  [!DNL Marketo Measure]
title: Toevoegend  [!DNL Marketo Measure]  Manuscript aan Lichtbak Forms
exl-id: fa9ce480-fc4f-4abd-8555-dbb74849747e
feature: Tracking
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 0%

---


# [!DNL Marketo Measure] Script toevoegen aan Lightroom Forms {#adding-marketo-measure-script-to-lightbox-forms}

Leer hoe u de [!DNL Marketo Measure] JavaScript correct aan een formulier in een lichtbak toevoegt.

Met een lichtbak wordt een formulier vóór de inhoud geopend wanneer de bezoeker een bepaalde actie uitvoert (door op een bepaald gedeelte van de pagina te klikken, een bepaalde tijd op de pagina door te brengen, enzovoort). Meestal vragen we om de JavaScript van [!DNL Marketo Measure] in de kop van de landingspagina te plaatsen, maar voor formulieren in een lichtbak is er één extra stap nodig.

Aangezien een formulier in een lichtbak in feite een formulier binnen een iFrame is, wordt het script in dat iFrame geplaatst.

Zoek eerst het iFrame waarin het formulier [!UICONTROL lightbox] zich bevindt.

![ die van de lichtbakvorm iFrame in de paginabron vinden ](assets/1.png)

Plaats vervolgens de JavaScript van [!DNL Marketo Measure] in het iFrame.

![ Marketo Measure die manuscript binnen lightbox iFrame wordt geplaatst ](assets/2.png)

Wanneer de JavaScript wordt toegevoegd, worden formulierverzendingen ten slotte in de volgende richtingen bijgehouden:

1. Kopieer de URL van de landingspagina met het [!UICONTROL lightbox] -formulier.
1. Open een Incognito-browser en plak de URL.
1. Verzend het formulier met een uniek e-mailadres.
1. Bevestig dat de test is gevolgd door uw CRM te controleren op het unieke e-mailadres dat wordt gebruikt. Controleer of de aanraakpuntgegevens worden gevuld.
