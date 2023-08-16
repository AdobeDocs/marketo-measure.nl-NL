---
unique-page-id: 18874539
description: Aangepast maken [!DNL Marketo Measure] Rapporttypen - [!DNL Marketo Measure] - Productdocumentatie
title: Aangepast maken [!DNL Marketo Measure] Rapporttypen
exl-id: 1d72a04f-6a2d-4607-ad09-3b025125156a
feature: Reporting
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 0%

---

# Aangepast maken [!DNL Marketo Measure] Rapporttypen {#creating-custom-marketo-measure-report-types}

>[!NOTE]
>
>Mogelijk ziet u instructies die &quot;[!DNL Marketo Measure]&quot; in onze documentatie , maar nog steeds &quot;[!DNL Bizible]&quot; in uw CRM. We werken eraan dat dit wordt bijgewerkt en de herbranding wordt binnenkort weerspiegeld in uw CRM.

Leer hoe u aangepaste [!DNL Marketo Measure] [!DNL Salesforce] rapporttypen. We raden u aan drie verschillende rapporttypen te maken: leads met kopertouch-punten (Aangepast), [!DNL Marketo Measure] Persoon met aanraakpunten koper (Aangepast), Opportunity met aanraakpunt koperkenmerk (Aangepast).

## Leads met aanraakpunten voor kopers (aangepast) {#leads-with-buyer-touchpoints-custom}

1. Ga naar **[!UICONTROL Setup]** > **[!UICONTROL Build]** > **[!UICONTROL Report Types]** > **[!UICONTROL New Custom Report Types]**.

   ![](assets/1.png)

1. Bepaal het Type van Rapport van de Douane.

   * [!UICONTROL Report Type Focus] > [!UICONTROL [!UICONTROL Primary Object]]: lead
   * Identificatie > [!UICONTROL Report Type Label]: Leads met aanraakpunten voor kopers (aangepast)
   * [!UICONTROL Store in Category]: Overige rapporten
   * [!UICONTROL Deployment] > [!UICONTROL Deployment Status]: Gedistribueerd

   ![](assets/2.png)

1. Definieer de objectrelaties.

   * Het Lead-object (A) koppelen aan de [!DNL Marketo Measure] Persoonsobject (B) en vervolgens naar het object Aanraakpunt koper (C)
   * Zorg ervoor dat &quot;[!UICONTROL Each A/B record must have at least one B/C]&quot; record is geselecteerd
   * [!UICONTROL Save]

   ![](assets/3.png)

## [!DNL Marketo Measure] Persoon met aanraakpunten koper (aangepast) {#marketo-measure-person-with-buyer-touchpoints-custom}

1. Ga naar **[!UICONTROL Setup]** > **[!UICONTROL Build]** > **[!UICONTROL Report Types]** > **[!UICONTROL New Custom Report Types]**.

   ![](assets/4.png)

1. Bepaal het Type van Rapport van de Douane.

   * [!UICONTROL Report Type Focus] > [!UICONTROL Primary Object]: [!DNL Marketo Measure] Personen
   * [!UICONTROL Identification] > [!UICONTROL Report Type Label]: [!DNL Marketo Measure] Persoon met aanraakpunten koper (aangepast)
   * [!UICONTROL Store in Category]: Overige rapporten
   * [!UICONTROL Deployment] > [!UICONTROL Deployment Status]: Gedistribueerd

   ![](assets/5.png)

1. Definieer de objectrelaties.

   * Maak een verbinding met [!DNL Marketo Measure] Persoonsobject (A) naar het object Aanraakpunt koper (B)
   * Zorg ervoor dat &quot;[!UICONTROL Each A record must have at least one B]&quot; record is geselecteerd
   * [!UICONTROL Save]

   ![](assets/6.png)

## Opportuniteiten met aanraakpunt voor koperkenmerk (aangepast) {#opportunities-with-buyer-attribution-touchpoint-custom}

1. Ga naar **[!UICONTROL Setup]** > **[!UICONTROL Build]** > **[!UICONTROL Report Types]** > **[!UICONTROL New Custom Report Types]**.

   ![](assets/7.png)

1. Bepaal het Type van Rapport van de Douane.

   * [!UICONTROL Report Type Focus] > [!UICONTROL Primary Object]: Kansen
   * [!UICONTROL Identification] > [!UICONTROL Report Type Label]: Opportuniteiten met aanraakpunt voor koperkenmerk (aangepast)
   * [!UICONTROL Store in Category]: Overige rapporten
   * [!UICONTROL Deployment] > [!UICONTROL Deployment Status]: Gedistribueerd

   ![](assets/8.png)

1. Definieer de objectrelaties.

   * Het Opportunity-object (A) koppelen aan het Aanraakpunt voor koperkenmerk (B)
   * Zorg ervoor dat &quot;[!UICONTROL Each A record must have at least one B]&quot; record is geselecteerd
   * [!UICONTROL Save]

   ![](assets/9.png)

## Aangepaste velden toevoegen aan aangepaste rapporttypen {#adding-custom-fields-to-custom-report-types}

1. Zodra de rapporten worden gecreeerd, zult u aan een overzicht van het rapporttype worden opnieuw gericht. Klik op **[!UICONTROL Edit Layout]**.

   ![](assets/10.png)

1. Zorg ervoor dat de aangepaste velden die u aan het rapport wilt toevoegen, worden weergegeven in de sectie Eigenschappen van veldindeling. Als er andere velden zijn die u wilt toevoegen, gebruikt u &quot;[!UICONTROL Add fields related via lookup]&quot;.

   ![](assets/11.png)
