---
unique-page-id: 18874779
description: Aangepast kenmerkmodel en aangepaste instellingen - [!DNL Marketo Measure]
title: Aangepast kenmerkmodel en aangepaste instellingen
exl-id: 7b156db2-9ac6-4d32-ac67-06c0aa15d651
feature: Attribution, Custom Models
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '822'
ht-degree: 0%

---

# Aangepast kenmerkmodel en aangepaste instellingen {#custom-attribution-model-and-setup}

Zie hieronder voor een overzicht van de [!DNL Marketo Measure] aangepast toewijzingsmodel en hoe u dit instelt.

## Aangepast kenmerkingsmodel {#custom-attribution-model}

De [!DNL Marketo Measure] Met het aangepaste kenmerkingsmodel kunnen gebruikers kiezen welke aanraakpunten of aangepaste stadia in het model worden opgenomen. De gebruikers kunnen het percentage van opbrengstkredieten controleren die aan deze touchpoints en stadia worden toegeschreven, of, kunnen de percentagewaarden gebruiken die door de [!DNL Marketo Measure] Machine Learning Model.

## Uw aangepaste kenmerkingsmodel instellen {#how-to-set-up-your-custom-attribution-model}

1. Bepaal welke stadia u in uw douanemodel wilt omvatten.

   Om uw model van de douaneattributie te beginnen bouwen, zult u moeten selecteren welke stadia voor uw team van de Marketing belangrijk zijn. Naast de [!DNL Marketo Measure] De mijlpaalfasen (FT, LC, OC, Gesloten) u kunt tot zes extra lood/de Statussen van het Contact of stadia van de Kans in uw douanemodel toevoegen. Het is bijvoorbeeld gebruikelijk dat het MQL-werkgebied wordt opgenomen in het aangepaste model. Marketing teams willen vaak weten welke inspanningen of kanalen de overgang naar het MQL-stadium stimuleren.

   Aanmelden bij [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}. Ga naar [!UICONTROL My Account] > [!UICONTROL Settings] > en onder de afdeling CRM selecteert u **[!UICONTROL Stage Mapping]**.

   Kies vervolgens welke stappen voor leads/contactpersonen en opportunity u wilt opnemen door het selectievakje **[!UICONTROL Include in Model]** doos.

   >[!NOTE]
   >
   >U kunt maximaal zes aangepaste stappen uitvoeren (exclusief de standaardinstellingen: FT, LC, OC, Closed).

   ![](assets/1-1.png)

   >[!NOTE]
   >
   >_Alles_ Hier worden de fasen Leads/Contacten en Opportunity weergegeven, zelfs als het werkgebied inactief is of niet meer wordt gebruikt in [!DNL Salesforce]. Als u deze fasen wilt verwijderen, moet u ze op de juiste wijze verwijderen in [!DNL Salesforce].

   Wanneer u de stadia hebt geselecteerd, moet u op de knop **[!UICONTROL Save & Process]** onder aan de pagina. De fases worden nu weergegeven in **[!UICONTROL Attribution Settings]** en kunt u toewijzingspercentages toewijzen aan elk werkgebied. Aangepaste fasen worden ook in de Marketing Performance Suite weergegeven als een &#39;lead&#39;- of &#39;opportunity&#39;-fase in de Demand Waterfall.

   Als er andere stadia zijn die u in het model wilt opnemen, maar deze niet in het [!UICONTROL Lead/Contact Status] of [!UICONTROL Opportunity Stage] lijst, kunt u uw eigen douanestadium bepalen dat van gebieden in uw CRM wordt gebaseerd.

   In het onderstaande voorbeeld wordt een aangepast &#39;MQL&#39;-werkgebied gedefinieerd met behulp van een datumveld. De regel bepaalt eenvoudig dat als het veld MQL-datum niet leeg is, dit als een MQL moet worden beschouwd en in het aangepaste model moet worden opgenomen. Het is ook belangrijk om de douaneframes te sorteren zodra zij zijn gecreeerd zodat het de vooruitgang van uw verkoopcyclus volgt.

   ![](assets/2-1.png)

   >[!CAUTION]
   >
   >Vergeet niet het bijhouden van historie in te schakelen voor aangepaste velden.

Als een aangepast veld wordt gebruikt in uw aangepaste model, MOET het bijhouden van veldgeschiedenis zijn ingeschakeld in CRM. Voor instructies voor het inschakelen van het bijhouden van veldgeschiedenis raadpleegt u [Aangepaste modelinstelling: Enable Field History Tracking](/help/advanced-marketo-measure-features/custom-attribution-models/custom-model-setup-enable-field-history-tracking.md).

1. Bepaal de toewijzingspercentages voor het aangepaste model.

   Ga naar de **[!UICONTROL Attribution Settings]** in [!DNL Marketo Measure] Apps; de douaneframes zullen hier in de attributietabel verschijnen. In de toewijzingstabel worden alle [!DNL Marketo Measure] toerekeningsmodellen en de toewijzingsweging van elk model. De toewijzingspercentages van de eerste vijf modellen zijn vast en kunnen niet worden gewijzigd.

   In de kolom uiterst rechts met het label &quot;**[!UICONTROL Custom]**,&quot; kunt u de wegingsfactor voor elk werkgebied in uw aangepaste toewijzingsmodel instellen. Voer de waarden voor elk werkgebied in onder de kolom Aangepast en klik op **[!UICONTROL Save and Reprocess]** wanneer voltooid.

   Links van het dialoogvenster _Aangepast_ de kolom is **[!DNL Marketo Measure]Systeem leren**. Het leren van de machine model berekent attributieweging die op het relatieve belang wordt gebaseerd om een overeenkomst te winnen afhankelijk van wat in elk douanestadium gebeurde. Raadpleeg voor meer informatie over het leermodel van de machine [Veelgestelde vragen over het leermodel voor machines](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md).

   ![](assets/3.png)

## Aanraakpuntposities {#touchpoint-positions}

Nadat de toewijzingspercentages zijn opgeslagen en verwerkt, worden de aanraakpunten bijgewerkt en worden de nieuwe fasen en posities weergegeven. Het aanraakpunt dat het laatst, vóór een overgangsfase, heeft plaatsgevonden, krijgt krediet voor die fase (zoals hieronder wordt weergegeven). De aangepaste weging en de inkomsten worden ook herverdeeld.

![](assets/4.png)

## Het verschil tussen de fasen van de treinen en de fase van het aangepaste model {#the-difference-between-funnel-stages-and-custom-model-stages}

U kunt douanestadia in uw Trechter van de Marketing nu zien, zelfs als u geen toegelaten Model van de Douane hebt. Dit zou door het gebruik van onze functionaliteit van het Stadium van de Trechter zijn. De Staven van de trechter geven u nu de capaciteit om stadia aan de trechter toe te voegen, maar zien geen attributie voor hen.

De Stages van de trechter zullen nog als Aanraakpunten worden gevolgd en zullen nog als Plaatsen van het Aanraakpunt in uw CRM verschijnen. Zonder Aangepast model krijgen deze aanraakpunten mogelijk nog steeds een middenaanraakkenmerk als er een formuliervulling is (10% voor Midden-aanraakvlakken), maar geen attributie als het slechts een webbezoek is.

Zoals je hieronder kunt zien, hebben we de &#39;Diligence&#39;-fase opgenomen als een scheiding tussen onze treinen. Dit betekent dat we aanraakpunten hebben waar de positie Diligence bevat, maar die aanraakpunten krijgen alleen een Midden-Touch-attributiekrediet als Aangepast model niet is ingeschakeld (maximaal 10%).

![](assets/5.png)

>[!NOTE]
>
>Het gedrag voor aangepaste BBT-modellen is om het aangepaste model met de middelste aanraking gelijkmatig te verdelen over andere stadia, op voorwaarde dat er geen middelste aanrakingen zijn.
