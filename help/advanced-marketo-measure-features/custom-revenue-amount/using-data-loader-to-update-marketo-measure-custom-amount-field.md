---
unique-page-id: 18874771
description: Bijwerken met gegevenslader [!DNL Marketo Measure] Veld voor aangepaste hoeveelheid - [!DNL Marketo Measure]
title: Veld voor aangepaste hoeveelheid in Marketo Measure bijwerken met gegevenslader
exl-id: 55e91ac4-a835-48e0-a6ce-1d85b32aeac0
feature: Custom Revenue Amount
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 0%

---

# Bijwerken met gegevenslader [!DNL Marketo Measure] Veld voor aangepaste hoeveelheid {#using-data-loader-to-update-marketo-measure-custom-amount-field}

[!DNL Marketo Measure] raadt u aan Data Loader te gebruiken als handige optie om opportuniteitswaarden bij te werken wanneer u een aangepast inkomstenveld gebruikt (we gebruiken het veld Bedrag uit het vak) in [!DNL Marketo Measure]. Data Loader heeft de voorkeur boven het gebruik van de [!DNL Marketo Measure] update script als het script vereist dat gebruikers alle Salesforce-validatieregels uitschakelen terwijl het script [!DNL Marketo Measure] script wordt uitgevoerd.

## Bijwerken met gegevenslader [!DNL Marketo Measure] Veld voor aangepaste hoeveelheid{#using-data-loader-to-update-marketo-measure-custom-amount-field-1}

1. Een Excel-werkblad maken met de volgende opties:

   * Opportunity-id
   * Veld Aangepast opportuniteitsbedrag (uw voorkeursveld voor inkomsten)
   * [!DNL Marketo Measure] Opportunity Amount, veld

1. Kopieer en plak de waarden van het veld van uw voorkeursinkomsten naar het [!UICONTROL [!DNL Marketo Measure] Opportunity Amount] veld. Werk deze Opps vervolgens bij met behulp van het CSV-bestand.

**_U kunt ook naar Salesforce gaan en een aangepaste lijstweergave gebruiken om alle mogelijkheden op grote schaal te bewerken..._**

1. Maak een aangepaste lijstweergave voor alle mogelijkheden.
1. Een filter toevoegen voor het veld met voorkeursinkomsten is niet leeg _en_ [!UICONTROL Marketo] Het veld Meerwaarde opportunity meten is leeg.
1. Klikken **[!UICONTROL Mass Edit]**, maar verandert niets.
1. Klik op **[!UICONTROL Save]**. Hierdoor wordt de workflow zo gevuld [!DNL Marketo Measure] De gebieden van het Bedrag van de kans met het gebied van de Inkomsten van de Software.
