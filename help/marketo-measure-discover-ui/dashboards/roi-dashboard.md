---
description: ROI-dashboard - [!DNL Marketo Measure] - Product
title: ROI Dashboard
feature: Reporting
exl-id: 878db6e0-3ac7-4f4c-b993-bd7a1cfa0638
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 0%

---

# ROI Dashboard {#roi-dashboard}

Het Dashboard van ROI voorziet marketers van een korrelige mening van rendementen op investering over kanalen, subkanalen, en campagnes. Het schort zorgvuldig kosten en opbrengstpatronen, terwijl ook het belichten van metriek zoals kosten-per-lood, overeenkomst, en kans, die een uitvoerig inzicht van marketing attributie verzekeren.

>[!NOTE]
>
>Dit dashboard bevindt zich momenteel in bètaversie. Tijdens deze overgangsfase zullen zowel de huidige als de nieuwe dashboards toegankelijk zijn. Het huidige dashboard wordt vervangen zodra we volledig zijn overgeschakeld en optimale functionaliteit hebben gegarandeerd.

**Vragen over de antwoorden van de commissie**

* Wat waren de ROI waarden voor elk kanaal, subchannel, en campagne?
* Hoe verdeelden de kosten en de opbrengsten over elk kanaal, subchannel, en campagne?
* Wat waren de kosten per lead, de kosten per deal en de kosten per kans?

## Dashboardcomponenten {#dashboard-components}

### KPI-tegels {#kpi-tiles}

* **Kosten**: Totale kosten van verbonden gegevensbronnen en handmatig geüploade kosten.
* **Toegewezen inkomsten**: De totale inkomstenbijdrage, gebaseerd op het gekozen toewijzingsmodel, van Opportunity met aanraakpunten die binnen de gefilterde datumperiode zijn gesloten.
* **Geregistreerde toegerekende inkomsten**: De totale inkomstenbijdrage, gebaseerd op het gekozen toewijzingsmodel, van Opportunity with touchpoints binnen de gefilterde datumperiode, ongeacht wanneer ze werden gesloten.
* **Totaal aantal nieuwe leads**: Het totale aantal nieuwe leads dat wordt gegenereerd, inclusief zowel aangeraakt als onaangeroerde leads.
* **Kosten per nieuwe lead**: De gemiddelde kosten per nieuwe lood, afgeleid van de totale kosten gedeeld door het totale aantal nieuwe lood.
* **Totaal aantal nieuwe kansen**: Het totale aantal nieuwe kansen dat wordt gegenereerd, met inbegrip van zowel aangeroerde als onaangeroerde Kansen.
* **Kosten per Nieuwe Kans**: De gemiddelde kosten per nieuwe Kans, die van de totale kosten worden afgeleid gedeeld door het totale aantal nieuwe Kansen.
* **Totaal aantal transacties**: Het aantal &#39;Closed Won&#39;-kansen, inclusief Opportunity zonder aanraakpunten.
* **Eenvoudig rendement**: Toegewezen ontvangsten gedeeld door kosten in de gefilterde datumperiode.
* **Realized ROI**: Geregistreerde toegerekende opbrengsten gedeeld door kosten in de gefilterde datumperiode.

![](assets/roi-dashboard-1.png)

### Kosten en opbrengsten per kanaalgrafiek {#cost-and-revenue-by-channel-graph}

Staafdiagram dat de kosten en opbrengsten weergeeft en dat is ontworpen om een vergelijkend perspectief te bieden op hun grootte ten opzichte van verschillende kanalen, subkanalen en campagnes.

* de functies voor uitvouwen en Omhoog gebruiken om de gegevens te categoriseren op Subkanaal en Campagne.
* Houd de muisaanwijzer boven elke balk om de eenvoudige en gerealiseerde ROI&#39;s weer te geven.

**Vragen over de antwoorden in het diagram**

* Wat waren de ROI waarden voor elk kanaal, subchannel, en campagne?
* Zijn er uitbijters of subkanalen met ongewoon hoge of lage kosten in verhouding tot hun inkomsten?

![](assets/roi-dashboard-2.png)

### Gegraaliseerd versus eenvoudig rendement in de loop der tijd {#realized-vs-simple-roi-over-time}

De lijngrafiek van de tijdreeks die de vergelijking tussen Geregistreerde en Eenvoudige ROI toont, die hun vooruitgang in tijd volgen.

* Houd de muis boven een sectie in de grafiek om de eenvoudige en gerealiseerde ROI&#39;s weer te geven.

**Vragen over de antwoorden in het diagram**

* Hoe vergelijk het gerealiseerde ROI met het Eenvoudige ROI over specifieke tijdsperiodes?
* Hoe verhoudt de trend van het RoI zich tot significante marketinggebeurtenissen in dezelfde periode?

![](assets/roi-dashboard-3.png)

### Kosten in tijdsgrafiek {#cost-over-time-graph}

Gestapelde staafgrafiek die de Totale Kosten toont, die door bijbehorende Kanalen voor elke Maand/Kwartaal/Jaar wordt gesegmenteerd.

* de functies voor uitvouwen en Omhoog gebruiken om de gegevens te categoriseren op maand, kwartaal of jaar.
* Houd de cursor boven een staafsegment of de ruimte tussen de staven om gedetailleerde informatie weer te geven.

**Vragen over de antwoorden in het diagram**

* Hoe vergelijken de gecombineerde kosten van alle kanalen van één kwartaal/maand aan volgende?
* Hoe zijn de kosten voor een specifiek kanaal in de loop der tijd geëvolueerd?

![](assets/roi-dashboard-4.png)

### Kosten per kanaalgrafiek {#cost-by-channel-graph}

Staafdiagram met marketinguitgaven die zijn gesegmenteerd door Kanaal/Subkanaal/Campagne.

* de functies voor uitvouwen en Omhoog gebruiken om de gegevens te categoriseren op Kanaal/Subkanaal/Campagne.

**Vragen over de antwoorden in het diagram**

* Welke subkanalen of campagnes binnen een primair kanaal hebben de hoogste toewijzing?
* Welke marketingmiddelen (kanaal, subkanaal of campagne) lijken ondergefinancierd in vergelijking met andere?

![](assets/roi-dashboard-5.png)

### Overzichtstabel ROI {#roi-summary-table}

Tabel met de toegerekende inkomsten, kosten en investeringsrendement, opgesplitst naar afzonderlijke kanalen voor een gedetailleerde uitsplitsing.

* Klik op het pictogram &quot;+&quot; naast elk kanaal om de uitsplitsing naar subkanaal en campagne weer te geven.

**Kolommen**

* Kanaal/Subkanaal/Campagne
* Kosten
* Toegewezen inkomsten
* Geregistreerde toegerekende inkomsten
* Eenvoudig rendement
* Realized ROI
* Ongerealiseerde Attributed Pipeline Revenue: Pipeline Revenue linked to linked to touchpoints (Open Opportunity) created within the filtered date period.

### Tabel met marketinguitgaven {#marketing-spend-table}

Tabel met kosten, nieuwe leads, Opportunity en deals die zijn afgesloten per kanaal voor een gedetailleerde uitsplitsing.

* Klik op het pictogram &quot;+&quot; naast elk kanaal om de uitsplitsing naar subkanaal en campagne weer te geven.

**Kolommen**

* Kanaal/Subkanaal/Campagne
* Kosten
* Nieuwe leads
* Kosten per nieuwe lead
* Nieuwe mogelijkheden
* Kosten per Nieuwe Kans
* Overeenkomsten
* Kosten per Overeenkomst

## Filtervenster {#filter-pane}

Dit dashboard is uitgerust met de volgende instellingen en filters:

* Datum
   * Gebaseerd op:
      * Aanmaakdatum: nieuwsleiders, nieuwe kansen
      * Kostendatum: kosten
      * Gesloten datum: bestemmingsontvangsten (eenvoudig rendement van investeringen), transacties
      * Aanraakpuntdatum: aanraakpunten van gerealiseerde toegerekende inkomsten (gerealiseerde ROI)
* Attributiemodel
* Kanaal, subkanaal
* Campagne

>[!MORELIKETHIS]
>
>* [Basisprincipes van dashboard ontdekken](/help/marketo-measure-discover-ui/dashboards/discover-dashboard-basics.md){target="_blank"}
>* [Zichtbaarheidsbeleid dashboardgegevens](/help/marketo-measure-discover-ui/dashboards/dashboard-data-visibility-policy.md){target="_blank"}

