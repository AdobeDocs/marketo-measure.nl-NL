---
description: Aangepast kenmerkmodel en instellingsrichtlijnen voor Marketo Measure-gebruikers
title: Aangepast kenmerkmodel en aangepaste instellingen
exl-id: 7b156db2-9ac6-4d32-ac67-06c0aa15d651
feature: Attribution, Custom Models
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '886'
ht-degree: 0%

---

# Aangepast kenmerkmodel en aangepaste instellingen {#custom-attribution-model-and-setup}

Zie hieronder voor een overzicht van het aangepaste attributiemodel van [!DNL Marketo Measure] en hoe u dit instelt.

## Aangepast kenmerkingsmodel {#custom-attribution-model}

Met het [!DNL Marketo Measure] Aangepaste kenmerkingsmodel kunnen gebruikers kiezen welke aanraakpunten of aangepaste fasen in het model worden opgenomen. Gebruikers kunnen het percentage aan deze aanraakpunten en fasen toegewezen inkomstenkrediet beheren of kunnen de waarden voor het toewijzingspercentage gebruiken die worden voorgesteld door het [!DNL Marketo Measure] Machine Learning Model.

## Uw aangepaste kenmerkingsmodel instellen {#how-to-set-up-your-custom-attribution-model}

1. Bepaal welke stadia u in uw douanemodel wilt omvatten.

   Om uw model van de douaneattributie te beginnen bouwen, zult u moeten selecteren welke stadia voor uw team van de Marketing belangrijk zijn. Naast de [!DNL Marketo Measure] mijlpaalfasen (FT, LC, OC, Gesloten) kunt u maximaal zes extra statussen van de Lood/van het Contact of stadia van de Kans in uw douanemodel toevoegen. Het is bijvoorbeeld gebruikelijk dat het MQL-werkgebied wordt opgenomen in het aangepaste model. Marketing teams willen vaak weten welke inspanningen of kanalen de overgang naar het MQL-stadium stimuleren.

   Teken binnen aan [&#x200B; experience.adobe.com/marketo-measure &#x200B;](https://experience.adobe.com/marketo-measure){target="_blank"}. Ga naar [!UICONTROL My Account] > [!UICONTROL Settings] > en selecteer **[!UICONTROL Stage Mapping]** onder de sectie CRM.

   Selecteer vervolgens het vak **[!UICONTROL Include in Model]** om aan te geven welke stappen u wilt opnemen voor leads/contactpersonen en opportunity.

   >[!NOTE]
   >
   >U kunt maximaal zes aangepaste stappen uitvoeren (exclusief de standaardinstellingen: FT, LC, OC, Closed).

   ![&#x200B; u wordt toegestaan tot zes douanestadia (zonder de gebreken:](assets/custom-models-1.png)

   >[!NOTE]
   >
   >_Alle_ leiden/Contacten en stadia van de Kans zullen hier verschijnen, zelfs als het stadium inactief of niet meer gebruikt in [!DNL Salesforce] is. Als u deze fasen wilt verwijderen, moet u ze verwijderen in [!DNL Salesforce] .

   Wanneer u de stadia hebt geselecteerd, moet u op de knop **[!UICONTROL Save & Process]** onder aan de pagina klikken. De fasen worden nu weergegeven op het tabblad **[!UICONTROL Attribution Settings]** en u kunt toewijzingspercentages toewijzen aan elk werkgebied. Aangepaste fasen worden ook in de Marketing Performance Suite weergegeven als een &#39;lead&#39;- of &#39;opportunity&#39;-fase in de Demand Waterfall.

   Als er andere stadia zijn die u in het model wilt opnemen, maar niet in de lijst [!UICONTROL Lead/Contact Status] of [!UICONTROL Opportunity Stage] staan, kunt u uw eigen aangepaste werkgebied definiëren op basis van velden in uw CRM.

   In het onderstaande voorbeeld wordt een aangepast &#39;MQL&#39;-werkgebied gedefinieerd met behulp van een datumveld. De regel bepaalt eenvoudig dat als het veld MQL-datum niet leeg is, dit als een MQL moet worden beschouwd en in het aangepaste model moet worden opgenomen. Het is ook belangrijk om de douaneframes te sorteren zodra zij zijn gecreeerd zodat het de vooruitgang van uw verkoopcyclus volgt.

   ![&#x200B; In het voorbeeld hieronder, wordt een douane &quot;MQL&quot;stadium bepaald gebruikend a &#x200B;](assets/custom-models-10.png)

   >[!CAUTION]
   >
   >Vergeet niet het bijhouden van historie in te schakelen voor aangepaste velden.

Als een aangepast veld wordt gebruikt in uw aangepaste model, MOET het bijhouden van veldgeschiedenis zijn ingeschakeld in CRM. Voor instructies om het volgen van de gebiedsgeschiedenis toe te laten, verwijs naar [&#x200B; de ModelOpstelling van de Douane: laat het Volgen van de Geschiedenis van het Gebied &#x200B;](/help/channel-tracking-and-setup/custom-model-setup-enable-field-history-tracking.md) toe.

1. Bepaal de toewijzingspercentages voor het aangepaste model.

   Ga naar **[!UICONTROL Attribution Settings]** in [!DNL Marketo Measure] Apps; de douaneframes zullen hier in de attributietabel verschijnen. In de toewijzingstabel worden alle [!DNL Marketo Measure] toewijzingsmodellen weergegeven en de toewijzingsweging van elk model. De toewijzingspercentages van de eerste vijf modellen zijn vast en kunnen niet worden gewijzigd.

   In de uiterst juiste kolom geëtiketteerd &quot;**[!UICONTROL Custom]**,&quot;kunt u het percentageweging voor elk stadium in uw model van de douaneattributie plaatsen. Voer de waarden voor elk werkgebied in onder de kolom Aangepast en klik op **[!UICONTROL Save and Reprocess]** wanneer dit is voltooid.

   Links van de _kolom van de Douane_ is het **[!DNL Marketo Measure]het Leren van de Machine model**. Het leren van de machine model berekent attributieweging die op het relatieve belang wordt gebaseerd om een overeenkomst te winnen afhankelijk van wat in elk douanestadium gebeurde. Voor meer informatie over de machine die model leren, verwijs naar [&#x200B; het Leren van de Machine ModelVeelgestelde Veelgestelde vragen &#x200B;](/help/channel-tracking-and-setup/machine-learning-model-faq.md).

   ![&#x200B; links van de kolom van de Douane is Marketo Measure &#x200B;](assets/custom-models-2.png)

## Aanraakpuntposities {#touchpoint-positions}

Nadat de toewijzingspercentages zijn opgeslagen en verwerkt, worden de aanraakpunten bijgewerkt en worden de nieuwe fasen en posities weergegeven. Het aanraakpunt dat het laatst, vóór een overgangsfase, heeft plaatsgevonden, krijgt krediet voor die fase (zoals hieronder wordt weergegeven). De aangepaste weging en de inkomsten worden ook herverdeeld.

![&#x200B; nadat de attributiepercentages zijn bewaard en verwerkt, zullen de aanraakpunten &#x200B;](assets/custom-models-3.png) zijn

## Het verschil tussen Funnel-fasen en aangepaste modelfasen {#the-difference-between-funnel-stages-and-custom-model-stages}

Je kunt nu aangepaste fasen zien in je marketing Funnel, zelfs als je Aangepast model niet hebt ingeschakeld. Dit gebeurt via de Funnel Stage-functionaliteit. Met funnel Stages kunt u nu fases toevoegen aan de funnel, maar u ziet geen toewijzing voor deze fases.

Funnel-werkruimten worden nog steeds bijgehouden als aanraakpunten en verschijnen nog steeds als aanraakpuntposities in uw CRM-systeem. Zonder Aangepast model krijgen deze aanraakpunten mogelijk nog steeds een middenaanraakkenmerk als er een formuliervulling is (10% voor Midden-aanraakvlakken), maar geen attributie als het slechts een webbezoek is.

Zoals je hieronder kunt zien, hebben we de &#39;Diligence&#39;-fase opgenomen als een scheiding tussen onze Funnel-fasen. Dit betekent dat we aanraakpunten hebben waar de positie Diligence bevat, maar die aanraakpunten krijgen alleen een Midden-Touch-attributiekrediet als Aangepast model niet is ingeschakeld (maximaal 10%).

![&#x200B; Zoals u hieronder kunt zien, hebben wij het stadium van de Opkomst als apart &#x200B;](assets/custom-models-7.png) opgenomen

>[!NOTE]
>
>Het gedrag voor aangepaste BAT-modellen is dat het aangepaste model een middenaanraakpercentage gelijkmatig over andere stadia wordt verdeeld, mits er geen tussenliggende aanraakpunten zijn.
