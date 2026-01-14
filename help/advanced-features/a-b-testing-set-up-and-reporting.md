---
description: A/B Testen Opstelling en rapportagerichtlijnen voor Marketo Measure-gebruikers
title: A/B Testen en rapporteren
exl-id: 9a3f0731-5909-4fbf-a35a-9608ff561061
feature: A/B Testing
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 0%

---


# A/B Testen en rapporteren {#a-b-testing-set-up-and-reporting}

De [!DNL Marketo Measure] integratie van de Test A/B staat u toe om het opbrengsteffect van uw [&#x200B; Optimizely &#x200B;](https://www.optimizely.com/){target="_blank"} en de plaatsexperimenten van VWO te volgen. In dit artikel vindt u instructies voor het toevoegen van [!DNL Marketo Measure] A/B-testsecties aan de paginalay-outs Lead, [!UICONTROL Contact] , Case en [!UICONTROL Opportunity] . Hier worden ook algemene rapportpraktijken en aanbevelingen voor het uitvoeren van [!DNL Marketo Measure] A/B-rapporttypen besproken.

## Instellen {#set-up}

Voeg de sectie [!DNL Marketo Measure] A/B-test toe op Lood, Contact, Hoofd-kleine letter en Opportunity. [!DNL Marketo Measure] A/B de integratie van de Test staat u toe om het opbrengsteffect van uw [&#x200B; Optimizely &#x200B;](https://www.optimizely.com/){target="_blank"} en [&#x200B; VWO &#x200B;](https://vwo.com/){target="_blank"} plaatsexperimenten te volgen.

1. Controleer of u pakket [!DNL Marketo Measure] v3.9 of hoger gebruikt. U kunt dit doen door naar [!UICONTROL Salesforce] > [!UICONTROL Set Up] > [!UICONTROL Installed packages] te gaan.
1. Bewerk de paginalay-out Lead en voeg de **[!DNL Marketo Measure]Verwante lijst van A/B-tests** toe aan de pagina.

   ![](assets/advanced-features-10.png)

1. Klik op [!UICONTROL Wrench] . Verwijder het veld &quot;Id&quot; uit de lijst met geselecteerde velden. Voeg velden **[!UICONTROL Experiment]** , **[!UICONTROL Variation]** en **[!UICONTROL DateReported]** toe. Wijzig &quot;[!UICONTROL Sort by]&quot; in **[!UICONTROL Date Reported]** en selecteer **[!UICONTROL Descending]** in de vervolgkeuzelijst.

   ![](assets/advanced-features-2.png)

1. Schakel [!UICONTROL Buttons] uit onder **[!UICONTROL New]** .

   ![](assets/advanced-features-3.png)

1. Contacteer uw [!DNL Marketo Measure] rep of [&#x200B; Steun van Marketo &#x200B;](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} om de eigenschap toe te laten.

## Rapportage {#reporting}

Klanten hebben toegang tot een aantal [!DNL Marketo Measure] A/B-rapporttypen waarmee u kunt rapporteren over A/B-test met betrekking tot leads, contactpersonen en opportuniteiten:

* [!DNL Marketo Measure] A/BTests
* [!DNL Marketo Measure] A/BTests met Contact
* [!DNL Marketo Measure] A/BTests met lead
* [!DNL Marketo Measure] A/BTests met opportunity

![](assets/advanced-features-7.png)

De A/B rapporttypes worden gebruikt om te rapporteren over welke Lood of Contact of Kans aan een A/B test is blootgesteld. Deze rapporten tonen u ook de hoeveelheid opbrengst verbonden aan een Kans die aan een A/B test werd blootgesteld.

Het is belangrijk om op te merken dat Optimizely/VWO een platform van de inhoudvariatie en niet een marketing kanaal is. Deze [!DNL Marketo Measure] A/B-rapporttypen worden daarom anders gebruikt dan Buyer Touchpoint-rapporten. De types van de aanraakpuntrapporten van de koper worden gebruikt om te begrijpen welke marketing kanaal (betaalde reclame, Web direct, sociaal) een Lood of Contact naar een specifieke pagina leidde. [!DNL Marketo Measure] A/B-rapporttypen kunnen echter niet worden gebruikt om te rapporteren hoe een variatie een lead of opportunity heeft beïnvloed. Aangezien een A/B-testvariatie geen kanaal is, worden op het aanraakpunt voor kopers geen details over de variatie weergegeven.

Hier volgen enkele aanbevolen velden voor rapportage over een A/B-test om de duidelijkheid te vergroten en insight:

* Lood omgezet
* Experimenteer
* Id van experiment
* Variatie
* Variatie-id
* Datum van melding

## [!DNL Salesforce] Voorbeeldrapporten {#salesforce-example-reports}

**[!DNL Marketo Measure]A/B-test met lead**

![](assets/advanced-features-8.png)

**[!DNL Marketo Measure]A/B Test with Opportunity**

![](assets/advanced-features-9.png)
