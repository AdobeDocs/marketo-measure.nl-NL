---
unique-page-id: 18874560
description: Waarom u geen aanraakpunten wilt verwijderen - [!DNL Marketo Measure] - Productdocumentatie
title: Waarom u geen aanraakpunten wilt verwijderen
exl-id: e74c14ff-0399-4ee9-b732-6686823ff5c7
feature: Touchpoints
source-git-commit: cc786cb3af08fa36af91ef22f4dba3072c9617eb
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 0%

---

# Waarom u geen aanraakpunten wilt verwijderen {#why-you-should-never-delete-touchpoints}

Als u vindt dat er een aanraakpunt is op een opportunity waaraan onjuist toewijzingskrediet wordt toegewezen, neemt u contact op met uw accountmanager om de volgende stappen te bepalen. In deze situaties raden we u aan de functie voor het onderdrukken van aanraakpunten van de koper te gebruiken om het aanraakpunt van SFDC en het ROI-dashboard te verwijderen. Uw accountmanager kan u helpen deze regels te maken. Verwijder deze aanraakpunten niet handmatig.

De [!DNL Marketo Measure] het verwerkingssysteem niet registreert dat een aanraakpunt handmatig uit SFDC is verwijderd. Vanaf vandaag is er geen trigger die ons systeem signalen geeft om gegevens aan te passen. [!DNL Marketo Measure] niet automatisch op een ander aanraakpunt duwen om het punt te vervangen dat is verwijderd, noch wordt de positie of het kenmerk van het aanraakpunt opnieuw toegewezen aan het volgende aanraakpunt.

Wanneer een aanraakpunt wordt verwijderd, ontstaat een gat in de toewijzingsgegevens. Typisch, zal dit in attributie aanraakpunten op een Kans duidelijk worden. In de onderstaande afbeelding is het aanraakpunt dat de Opportunity Creation-aanraking zou hebben gekregen, verwijderd. Als gevolg hiervan ontbreekt deze kans aan het aanraakpunt van de OC en zal het toewijzingspercentage voor deze Opp niet oplopen tot 100%.

![](assets/1.png)

Als aanraakpunten uit uw SFDC zijn verwijderd, kunt u contact opnemen met [[!DNL Marketo Support]](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} om opnieuw te importeren van uw gegevens aan te vragen.
