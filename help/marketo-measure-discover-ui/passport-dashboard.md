---
description: Beschrijft het dashboard van het Paspoort dat volgt hoe de contacten en de kansen door stadia in tijd bewegen
title: Paspoort-dashboard
feature: Reporting
exl-id: 0fbd9714-7d9c-4330-b35f-d011e17c3bfe
hidefromtoc: true
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 0%

---

# Paspoort-dashboard {#passport-dashboard}

Het Paspoort-dashboard biedt marketers een dynamische weergave van leads, contactpersonen en opportuniteiten terwijl ze verschillende fasen binnen een bepaalde periode doorlopen. Door voor een specifieke datum te filteren, kunnen de gebruikers een momentopname van verslagen voor die dag ook verkrijgen.

**Vragen de raad antwoorden:**

* Hoeveel lood, contacten, of kansen bestonden in elke niet-eindfase op om het even welke gekozen dag?
* Hoeveel verschillende leads of contactpersonen zijn er gedurende een bepaalde periode doorgegaan in elk overgangsstadium?
   * _Voorbeeld_: Als Lood A in stadium 1 op 1/1/2023 was en aan stadium 5 door 3/31/2023 werd gepresteerd, zou de Q1 2023 analyse van het Paspoort Lood A in stadia 1 door 5 tellen.
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
* Campaign
* Segmenten

>[!MORELIKETHIS]
>
>* [ ontdekt de Grondbeginselen van het Dashboard ](/help/marketo-measure-discover-ui/discover-dashboard-basics.md){target="_blank"}
>* [ Beleid van de Zichtbaarheid van Gegevens van het Dashboard ](/help/marketo-measure-discover-ui/dashboard-data-visibility-policy.md){target="_blank"}
