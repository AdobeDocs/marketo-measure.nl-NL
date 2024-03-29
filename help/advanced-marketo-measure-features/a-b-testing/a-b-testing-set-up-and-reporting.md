---
unique-page-id: 18874773
description: Testopstelling en rapportage van A/B - [!DNL Marketo Measure]
title: A/B Testen en rapporteren
exl-id: 9a3f0731-5909-4fbf-a35a-9608ff561061
feature: A/B Testing
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 0%

---

# A/B Testen en rapporteren {#a-b-testing-set-up-and-reporting}

De [!DNL Marketo Measure] A/B de integratie van de Test staat u toe om het opbrengsteffect van uw te volgen [Optimizely](https://www.optimizely.com/){target="_blank"} experimenten met de werkomgeving VWO. Dit artikel bevat instructies voor het toevoegen van [!DNL Marketo Measure] A/B-testsecties naar de lood; [!UICONTROL Contact], en [!UICONTROL Opportunity] paginalay-outs. Ook worden algemene rapportagepraktijken en aanbevelingen voor het uitvoeren van [!DNL Marketo Measure] A/B rapporttypen.

## Instellen {#set-up}

Voeg de [!DNL Marketo Measure] A/B de secties van de Test op Lood, Contact, Geval, en Kans. [!DNL Marketo Measure] A/B de integratie van de Test staat u toe om het opbrengsteffect van uw te volgen [Optimizely](https://www.optimizely.com/){target="_blank"} and [VWO](https://vwo.com/){target="_blank"} experimenten op locaties.

1. Controleren of u pakket gebruikt [!DNL Marketo Measure] v3.9 of hoger. Je kunt dit doen door naar [!UICONTROL Salesforce] >[!UICONTROL Set Up] > [!UICONTROL Installed packages].
1. De pagina-indeling Lead bewerken en de **[!DNL Marketo Measure]A/B-tests** Verwante lijst voor de pagina.

   ![](assets/1.png)

1. Klik op de knop [!UICONTROL Wrench] knop. Verwijder het veld &quot;Id&quot; uit de lijst met geselecteerde velden. Toevoegen **[!UICONTROL Experiment]**, **[!UICONTROL Variation]**, en **[!UICONTROL DateReported]** velden. Wijzigen &quot;[!UICONTROL Sort by]&quot; naar **[!UICONTROL Date Reported]** en selecteert u **[!UICONTROL Descending]** in de vervolgkeuzelijst.

   ![](assets/2.png)

1. Onder [!UICONTROL Buttons], uitschakelen **[!UICONTROL New]**.

   ![](assets/3.png)

1. Neem contact op met uw [!DNL Marketo Measure] rep of [Marketo-ondersteuning](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} om de functie in te schakelen.

## Rapportage {#reporting}

Klanten hebben toegang tot een aantal [!DNL Marketo Measure] A/B rapporttypes die u toestaan om over A/B Test met betrekking tot Leidingen, Contacten, en Kansen te rapporteren:

* [!DNL Marketo Measure] A/BTests
* [!DNL Marketo Measure] A/BTests met Contact
* [!DNL Marketo Measure] A/BTests met lead
* [!DNL Marketo Measure] A/BTests met opportunity

![](assets/4.png)

De A/B rapporttypes worden gebruikt om te rapporteren over welke Lood of Contact of Kans aan een A/B test is blootgesteld. Deze rapporten tonen u ook de hoeveelheid opbrengst verbonden aan een Kans die aan een A/B test werd blootgesteld.

Het is belangrijk om op te merken dat Optimizely/VWO een platform van de inhoudvariatie en niet een marketing kanaal is. Deze [!DNL Marketo Measure] De rapporttypen A/B worden anders gebruikt dan de rapporten van het Aanraakpunt van de Koper. De types van de aanraakpuntrapporten van de koper worden gebruikt om te begrijpen welke marketing kanaal (betaalde reclame, Web direct, sociaal) een Lood of Contact naar een specifieke pagina leidde. Maar [!DNL Marketo Measure] A/B-rapporttypen kunnen niet worden gebruikt om te rapporteren hoe een variatie een lead of opportunity heeft beïnvloed. Aangezien een A/B-testvariatie geen kanaal is, worden op het aanraakpunt voor kopers geen details over de variatie weergegeven.

Hier volgen enkele aanbevolen velden voor rapportage over een A/B-test om de duidelijkheid en het inzicht te vergroten:

* Lood omgezet
* Experimenteer
* Id van experiment
* Variatie
* Variatie-id
* Datum van melding

## [!DNL Salesforce] Voorbeeldrapporten {#salesforce-example-reports}

**[!DNL Marketo Measure]A/B-test met lood**

![](assets/5.png)

**[!DNL Marketo Measure]A/B-test met mogelijkheid**

![](assets/6.png)
