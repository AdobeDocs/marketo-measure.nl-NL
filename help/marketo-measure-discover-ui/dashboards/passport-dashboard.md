---
description: Paspoort-dashboard - [!DNL Marketo Measure] - Product
title: Paspoort-dashboard
feature: Reporting
exl-id: 0fbd9714-7d9c-4330-b35f-d011e17c3bfe
source-git-commit: 88dfdac366d29bed29ed39979cb76cad7aee4025
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 0%

---

# Paspoort-dashboard {#passport-dashboard}

Het Paspoort-dashboard biedt marketers een dynamische weergave van leads, contactpersonen en opportuniteiten terwijl ze verschillende fasen binnen een bepaalde periode doorlopen. Door voor een specifieke datum te filteren, kunnen de gebruikers een momentopname van verslagen voor die dag ook verkrijgen.

>[!NOTE]
>
>Dit dashboard bevindt zich momenteel in bètaversie. Tijdens deze overgangsfase zullen zowel de huidige als de nieuwe dashboards toegankelijk zijn. Het huidige dashboard wordt vervangen zodra we volledig zijn overgeschakeld en optimale functionaliteit hebben gegarandeerd.

**De antwoorden van de raad vragen:**

* Hoeveel lood, contacten, of kansen bestonden in elke niet-eindfase op om het even welke gekozen dag?
* Hoeveel verschillende leads of contactpersonen zijn er gedurende een bepaalde periode doorgegaan in elk overgangsstadium?
   * _Voorbeeld_: Indien Lood A op 1 januari 2023 in de eerste fase was en op 3 december 2023 naar fase 5 was gevorderd, zou de analyse van het paspoort Q1 2023 in de eerste fase tot en met 5 leiden tot Lood A.
* Hoeveel unieke kansen gingen door elk transient stadium tijdens een bepaald tijdkader over?

## Dashboardcomponenten {#dashboard-components}

### Kansen in werkgebied op werkgebiednaam {#opportunities-in-stage-by-stage-name}

* In elk werkgebied wordt het aantal opportuniteiten weergegeven met aanraakpunten dat binnen een bepaald tijdsbestek door de aanraakpunten is gegaan.
   * Als een kans door veelvoudige stadia binnen die spanwijdte vordert, wordt het geteld in elk stadium het overgaat.
* Eindfasen zoals &quot;Closed Won&quot; en &quot;Closed Lost&quot; zijn uitgesloten.
* Zowel begin- als einddatum zijn inclusief.

![](assets/passport-dashboard-1.png)

### Leads of contactpersonen in werkgebied op werkgebiednaam {#leads-or-contacts-in-stage-by-stage-name}

* In elk werkgebied wordt het aantal leads of contactpersonen met aanraakpunten weergegeven dat binnen een bepaald tijdsbestek door de aanraakpunten is gegaan.
   * Of &#39;&#39;Lead&#39;&#39; of &#39;&#39;Contact&#39;&#39; wordt weergegeven, wordt bepaald door de voorkeursinstelling die is ingesteld in: Instellingen > Kenmerken > Standaarddashboardobject.
   * Als een lead of contactpersoon meerdere stappen binnen die reeks doorloopt, wordt deze meegeteld in elk stadium dat deze passeert.
* Eindfasen zoals &quot;Closed Won&quot; en &quot;Closed Lost&quot; zijn uitgesloten.
* Zowel begin- als einddatum zijn inclusief.

![](assets/passport-dashboard-2.png)

## Filtervenster {#filter-pane}

Dit dashboard is uitgerust met de volgende instellingen en filters:

* Datum (gebaseerd op de overgangsdatum)
* Kanaal, subkanaal
* Campagne
* Segmenten

>[!MORELIKETHIS]
>
>* [Basisprincipes van dashboard ontdekken](/help/marketo-measure-discover-ui/dashboards/discover-dashboard-basics.md){target="_blank"}
>* [Zichtbaarheidsbeleid dashboardgegevens](/help/marketo-measure-discover-ui/dashboards/dashboard-data-visibility-policy.md){target="_blank"}
