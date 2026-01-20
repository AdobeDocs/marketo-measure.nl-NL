---
unique-page-id: 18874771
description: Het gebruiken van de Lader van Gegevens om {het Gebied van het Bedrag van 0} bij te werken -  [!DNL Marketo Measure]  [!DNL Marketo Measure]
title: Veld voor aangepaste hoeveelheid in Marketo Measure bijwerken met gegevenslader
exl-id: 55e91ac4-a835-48e0-a6ce-1d85b32aeac0
feature: Custom Revenue Amount
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 0%

---

# Veld voor aangepaste hoeveelheid [!DNL Marketo Measure] bijwerken met gegevenslader {#using-data-loader-to-update-marketo-measure-custom-amount-field}

[!DNL Marketo Measure] raadt u aan Data Loader te gebruiken als handige optie om opportuniteitswaarden bij te werken wanneer u een aangepast inkomstenveld gebruikt (het veld Bedrag wordt uit het vak weergegeven) in [!DNL Marketo Measure] . Data Loader heeft de voorkeur boven het gebruik van het updatescript van [!DNL Marketo Measure] omdat het script vereist dat gebruikers alle Salesforce-validatieregels uitschakelen terwijl het script van [!DNL Marketo Measure] wordt uitgevoerd.

## Veld voor aangepaste hoeveelheid [!DNL Marketo Measure] bijwerken met gegevenslader{#using-data-loader-to-update-marketo-measure-custom-amount-field-1}

1. Een Excel-werkblad maken met de volgende opties:

   * Opportunity-id
   * Veld Aangepast opportuniteitsbedrag (uw voorkeursveld voor inkomsten)
   * [!DNL Marketo Measure] Veld Opportunity Amount

1. Kopieer en plak de waarden van het veld met voorkeursopbrengsten naar het veld [!UICONTROL [!DNL Marketo Measure] Opportunity Amount] . Werk deze Opps vervolgens bij met behulp van het CSV-bestand.

**_Alternatief, kunt u in Salesforce gaan en een mening van de douanelijst gebruiken om alle kansen... te masseren uitgeven_**

1. Maak een aangepaste lijstweergave voor alle mogelijkheden.
1. Voeg een filter voor aangewezen opbrengstgebied toe is niet leeg _en_ [!UICONTROL Marketo] het gebied van het Bedrag van de Kans van de Maatregel is leeg.
1. Klik op **[!UICONTROL Mass Edit]** , maar wijzig niets.
1. Klik op **[!UICONTROL Save]**. Hierdoor wordt de workflow geactiveerd om de velden [!DNL Marketo Measure] Opportunity Amount te vullen met het veld Software Revenue.
