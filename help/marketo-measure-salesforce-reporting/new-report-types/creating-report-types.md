---
description: Creërend de leidraad van de Types van Rapport van de Douane  [!DNL Marketo Measure]  voor de gebruikers van Marketo Measure
title: 'Creërend de Types van Rapport van de Douane  [!DNL Marketo Measure] '
exl-id: 1d72a04f-6a2d-4607-ad09-3b025125156a
feature: Reporting
hidefromtoc: true
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 0%

---

# Aangepaste [!DNL Marketo Measure] rapporttypen maken {#creating-custom-marketo-measure-report-types}

>[!NOTE]
>
>U kunt instructies zien die &quot;[!DNL Marketo Measure]&quot;in de documentatie specificeren, maar nog zie &quot;[!DNL Bizible]&quot;in uw CRM. We werken eraan dat dit wordt bijgewerkt en de herbranding wordt binnenkort weerspiegeld in uw CRM.

Leer hoe u aangepaste rapporttypen [!DNL Marketo Measure] [!DNL Salesforce] maakt. Er zijn drie verschillende rapporttypen die we aanraden te maken: leads met kopersaanraakpunten (Aangepast), [!DNL Marketo Measure] Person with Buyer Touchpoints (Aangepast), Opportunity with Buyer Attribution Touchpoint (Aangepast).

## Leads met aanraakpunten voor kopers (aangepast) {#leads-with-buyer-touchpoints-custom}

1. Ga naar **[!UICONTROL Setup]** > **[!UICONTROL Build]** > **[!UICONTROL Report Types]** > **[!UICONTROL New Custom Report Types]** .

   ![](assets/new-types-1.png)

1. Bepaal het Type van Rapport van de Douane.

   * [!UICONTROL Report Type Focus] > [!UICONTROL [!UICONTROL Primary Object]] : Lead
   * Identificatie > [!UICONTROL Report Type Label]: Leads met aanraakpunten voor koper (aangepast)
   * [!UICONTROL Store in Category]: Overige rapporten
   * [!UICONTROL Deployment] > [!UICONTROL Deployment Status]: Geïmporteerd

   ![](assets/new-types-10.jpg)

1. Definieer de objectrelaties.

   * Het object Lead (A) koppelen aan het [!DNL Marketo Measure] object Person (B) en vervolgens aan het object Buyer Touchpoint (C)
   * Zorg ervoor dat &quot;[!UICONTROL Each A/B record must have at least one B/C]&quot;-record is geselecteerd
   * [!UICONTROL Save]

   ![](assets/new-types-11.png)

## [!DNL Marketo Measure] Persoon met aanraakpunten koper (aangepast) {#marketo-measure-person-with-buyer-touchpoints-custom}

1. Ga naar **[!UICONTROL Setup]** > **[!UICONTROL Build]** > **[!UICONTROL Report Types]** > **[!UICONTROL New Custom Report Types]** .

   ![](assets/new-types-12.png)

1. Bepaal het Type van Rapport van de Douane.

   * [!UICONTROL Report Type Focus] > [!UICONTROL Primary Object] : [!DNL Marketo Measure] Personen
   * [!UICONTROL Identification] > [!UICONTROL Report Type Label] : [!DNL Marketo Measure] Persoon met aanraakpunten koper (aangepast)
   * [!UICONTROL Store in Category]: Overige rapporten
   * [!UICONTROL Deployment] > [!UICONTROL Deployment Status]: Geïmporteerd

   ![](assets/new-types-13.jpg)

1. Definieer de objectrelaties.

   * Het [!DNL Marketo Measure] object Person (A) koppelen aan het Buyer Touchpoint-object (B)
   * Zorg ervoor dat &quot;[!UICONTROL Each A record must have at least one B]&quot;-record is geselecteerd
   * [!UICONTROL Save]

   ![](assets/new-types-9.png)

## Kansen met Buyer Attribution Touchpoint (aangepast) {#opportunities-with-buyer-attribution-touchpoint-custom}

1. Ga naar **[!UICONTROL Setup]** > **[!UICONTROL Build]** > **[!UICONTROL Report Types]** > **[!UICONTROL New Custom Report Types]** .

   ![](assets/new-types-8.png)

1. Bepaal het Type van Rapport van de Douane.

   * [!UICONTROL Report Type Focus] > [!UICONTROL Primary Object] : Opportunity
   * [!UICONTROL Identification] > [!UICONTROL Report Type Label]: Opportuniteiten met Buyer Attribution Touchpoint (aangepast)
   * [!UICONTROL Store in Category]: Overige rapporten
   * [!UICONTROL Deployment] > [!UICONTROL Deployment Status]: Geïmporteerd

   ![](assets/new-types-14.jpg)

1. Definieer de objectrelaties.

   * Het object Opportunity (A) koppelen aan het object Buyer Attribution Touchpoint (B)
   * Zorg ervoor dat &quot;[!UICONTROL Each A record must have at least one B]&quot;-record is geselecteerd
   * [!UICONTROL Save]

   ![](assets/new-types-15.png)

## Aangepaste velden toevoegen aan aangepaste rapporttypen {#adding-custom-fields-to-custom-report-types}

1. Zodra de rapporten worden gecreeerd, zult u aan een overzicht van het rapporttype worden opnieuw gericht. Klik op **[!UICONTROL Edit Layout]**.

   ![](assets/new-types-2.png)

1. Zorg ervoor dat de aangepaste velden die u aan het rapport wilt toevoegen, worden weergegeven in de sectie Eigenschappen van veldindeling. Als er andere gebieden zijn u zou willen toevoegen, gebruik &quot;[!UICONTROL Add fields related via lookup]&quot;optie.

   ![](assets/new-types-3.png)
