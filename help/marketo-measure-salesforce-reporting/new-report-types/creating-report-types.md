---
description: 'Creërend de Types van Rapport van de Douane  [!DNL Marketo Measure] '
title: 'Creërend de Types van Rapport van de Douane  [!DNL Marketo Measure] '
exl-id: 1d72a04f-6a2d-4607-ad09-3b025125156a
feature: Reporting
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 0%

---


# Aangepaste [!DNL Marketo Measure] rapporttypen maken {#creating-custom-marketo-measure-report-types}

>[!NOTE]
>U kunt instructies zien die &quot;[!DNL Marketo Measure]&quot;in de documentatie specificeren, maar nog zie &quot;[!DNL Bizible]&quot;in uw CRM. We werken eraan dat dit wordt bijgewerkt en de herbranding wordt binnenkort weerspiegeld in uw CRM.

Leer hoe u aangepaste rapporttypen [!DNL Marketo Measure] [!DNL Salesforce] maakt. Er zijn drie verschillende rapporttypen die we aanraden te maken: leads met kopersaanraakpunten (Aangepast), [!DNL Marketo Measure] Person with Buyer Touchpoints (Aangepast), Opportunity with Buyer Attribution Touchpoint (Aangepast).

## Leads met aanraakpunten voor kopers (aangepast) {#leads-with-buyer-touchpoints-custom}

1. Ga naar **[!UICONTROL Setup]** > **[!UICONTROL Build]** > **[!UICONTROL Report Types]** > **[!UICONTROL New Custom Report Types]** .

   ![&#x200B; het menunavigatie van de Opstelling van Salesforce aan de Nieuwe Types van Rapport van de Douane &#x200B;](assets/1.png)

1. Bepaal het Type van Rapport van de Douane.

   * [!UICONTROL Report Type Focus] > [!UICONTROL [!UICONTROL Primary Object]] : Lead
   * Identificatie > [!UICONTROL Report Type Label]: Leads met aanraakpunten voor koper (aangepast)
   * [!UICONTROL Store in Category]: Overige rapporten
   * [!UICONTROL Deployment] > [!UICONTROL Deployment Status]: Geïmporteerd

   ![&#x200B; de vorm van de het rapporttype van de Douane met Lood als primair voorwerp &#x200B;](assets/2.png)

1. Definieer de objectrelaties.

   * Het object Lead (A) koppelen aan het [!DNL Marketo Measure] object Person (B) en vervolgens aan het object Buyer Touchpoint (C)
   * Zorg ervoor dat &quot;[!UICONTROL Each A/B record must have at least one B/C]&quot;-record is geselecteerd
   * [!UICONTROL Save]

   ![&#x200B; het relatiediagram van Objecten die Lood aan Persoon tonen aan de verbindingen van Touchpoint &#x200B;](assets/3.png)

## [!DNL Marketo Measure] Persoon met aanraakpunten koper (aangepast) {#marketo-measure-person-with-buyer-touchpoints-custom}

1. Ga naar **[!UICONTROL Setup]** > **[!UICONTROL Build]** > **[!UICONTROL Report Types]** > **[!UICONTROL New Custom Report Types]** .

   ![&#x200B; het menunavigatie van de Opstelling van Salesforce aan de Nieuwe Types van Rapport van de Douane &#x200B;](assets/4.png)

1. Bepaal het Type van Rapport van de Douane.

   * [!UICONTROL Report Type Focus] > [!UICONTROL Primary Object] : [!DNL Marketo Measure] Personen
   * [!UICONTROL Identification] > [!UICONTROL Report Type Label] : [!DNL Marketo Measure] Persoon met aanraakpunten koper (aangepast)
   * [!UICONTROL Store in Category]: Overige rapporten
   * [!UICONTROL Deployment] > [!UICONTROL Deployment Status]: Geïmporteerd

   ![&#x200B; de vorm van de het rapporttype van de Douane met de Persoon van Marketo Measure als primair voorwerp &#x200B;](assets/5.png)

1. Definieer de objectrelaties.

   * Het [!DNL Marketo Measure] object Person (A) koppelen aan het Buyer Touchpoint-object (B)
   * Zorg ervoor dat &quot;[!UICONTROL Each A record must have at least one B]&quot;-record is geselecteerd
   * [!UICONTROL Save]

   ![&#x200B; het relatiediagram van Objecten die Persoon aan Verbinding van het Aanraakpunt tonen &#x200B;](assets/6.png)

## Kansen met Buyer Attribution Touchpoint (aangepast) {#opportunities-with-buyer-attribution-touchpoint-custom}

1. Ga naar **[!UICONTROL Setup]** > **[!UICONTROL Build]** > **[!UICONTROL Report Types]** > **[!UICONTROL New Custom Report Types]** .

   ![&#x200B; het menunavigatie van de Opstelling van Salesforce aan de Nieuwe Types van Rapport van de Douane &#x200B;](assets/7.png)

1. Bepaal het Type van Rapport van de Douane.

   * [!UICONTROL Report Type Focus] > [!UICONTROL Primary Object] : Opportunity
   * [!UICONTROL Identification] > [!UICONTROL Report Type Label]: Opportuniteiten met Buyer Attribution Touchpoint (aangepast)
   * [!UICONTROL Store in Category]: Overige rapporten
   * [!UICONTROL Deployment] > [!UICONTROL Deployment Status]: Geïmporteerd

   ![&#x200B; de vorm van de het rapporttype van de Douane met Kansen als primair voorwerp &#x200B;](assets/8.png)

1. Definieer de objectrelaties.

   * Het object Opportunity (A) koppelen aan het object Buyer Attribution Touchpoint (B)
   * Zorg ervoor dat &quot;[!UICONTROL Each A record must have at least one B]&quot;-record is geselecteerd
   * [!UICONTROL Save]

   ![&#x200B; het relatiediagram dat van Objecten Kanaal aan de verbinding van het Aanraakpunt van de Attributie toont &#x200B;](assets/9.png)

## Aangepaste velden toevoegen aan aangepaste rapporttypen {#adding-custom-fields-to-custom-report-types}

1. Zodra de rapporten worden gecreeerd, zult u aan een overzicht van het rapporttype worden opnieuw gericht. Klik op **[!UICONTROL Edit Layout]**.

   ![&#x200B; het type van Rapport het overzichtsscherm met de Edit knoop van de Lay-out &#x200B;](assets/10.png)

1. Zorg ervoor dat de aangepaste velden die u aan het rapport wilt toevoegen, worden weergegeven in de sectie Eigenschappen van veldindeling. Als er andere gebieden zijn u zou willen toevoegen, gebruik &quot;[!UICONTROL Add fields related via lookup]&quot;optie.

   ![&#x200B; de sectie van de Eigenschappen van de Lay-out van het Gebied met beschikbare douanegebieden &#x200B;](assets/11.png)
