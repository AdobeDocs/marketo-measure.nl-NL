---
description: Betrokkenheidsdashboard -  [!DNL Marketo Measure]  - Product
title: Betrokkenheidsdashboard
feature: Reporting
exl-id: dc8bcbe4-d470-4cd3-a2d9-804fdebe7121
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 0%

---


# Betrokkenheidsdashboard {#engagement-dashboard}

Het betrokkenheidsdashboard volgt nauwgezet de gegevens van de gebruikersbetrokkenheid. Het toont aanraakpunten, het aantal betrokken personen en de gemiddelde aanraakpunten per persoon. Gebruik het staafdiagram van de tijdreeks voor een maandelijkse, driemaandelijkse, of jaarlijkse mening, en het staafdiagram voor gedetailleerde Inzichten van het Kanaal, Subchannel, en van de Campagne. Dit hulpmiddel is essentieel voor het begrijpen van betrokkenheidspatronen en het verfijnen van uw servicestrategieën.

We volgen elke interactie van klanten als UT&#39;s (User Touchpoints), de &#39;onbewerkte&#39; verzamelde gegevenspunten, die de basis vormen voor betrokkenheidsmetriek op ons dashboard. Niet alle UT&#39;s evolueren naar de aanraakpunten voor kopers (BT&#39;s) of de aanraakpunten voor koperskenmerken (BBT&#39;s), aangezien dit geselecteerde resultaten zijn voor het toewijzen van specifieke klantinteracties aan inkomstengerelateerde activiteiten. Het is belangrijk om op te merken dat de suppressieregels UTs of het betrokkenheidsdashboard niet beïnvloeden.

* **Aanraakpunten van de Gebruiker**: Aanraakpunten die van alle overeenkomsten worden gecreeerd.
* **Aanraakpunten van de Koper**: Aanraakpunten geselecteerd voor kenmerk Lead en Contactpersoon. BT&#39;s zijn niet gekoppeld aan opportuniteiten en hebben geen bijbehorende inkomsten.
* **Aanraakpunten van de Attributie van de Koper**: Aanraakpunten die voor de attributie van de Kans worden geselecteerd. BBT&#39;s hebben gevolgen voor de inkomsten, aangezien zij verband houden met opportuniteiten.

Het gebruik van alleen BT&#39;s of BBT&#39;s om de betrokkenheid te meten, zou de ware omvang van de interactie tussen klanten onderschatten, aangezien de betrokkenheid breder is dan alleen toewijzing.

Hiermee worden vragen gesteld aan het dashboard:

* Hoeveel mensen waren betrokken? Wat is het gemiddelde aantal tochten per betrokken persoon?
* Hoe vergelijk het aantal aanraakpunten met de personen die binnen een specifiek kanaal/subkanaal/campagne worden aangeraakt?
* Hoeveel aanraakpunten waren er met een bepaald kanaal of subkanaal? Hoe veranderde het in de loop der tijd?

>[!NOTE]
>De metriek van de rekening en van de Overeenkomst van de Kans zijn gepland voor versie in de eerste helft van 2024.

## Dashboardcomponenten {#dashboard-components}

### KPI-tegels {#kpi-tiles}

* Aanraakpunten: het totale aantal ruwe aanraakpunten dat wordt gegenereerd.
   * Aanraakpunten voor kopers en Aanraakpunten voor koperkenmerken zijn toewijzingsresultaten die worden gemaakt door specifieke aanraakpunten te selecteren voor creditering. Niet alle aanraakpunten worden als BT&#39;s en BBT&#39;s geselecteerd.
* Mensen die werden geraakt: het totale aantal mensen met aanraakpunten.
* Aanraakpunten per persoon: gemiddeld aantal aanraakpunten per persoon dat is aangeraakt.

### Aanraakpunten en personen die in de loop der tijd aanraken {#touchpoints-and-people-touched-over-time}

In het staafdiagram van de tijdreeks wordt het aantal aanraakpunten, Personen met aanraakpunten en aanraakpunten per persoon voor elke maand, elk kwartaal en elk jaar weergegeven.

* de functies voor uitvouwen en Omhoog gebruiken om de gegevens te categoriseren op maand, kwartaal of jaar.
* Houd de muis boven een balk of lijn om gedetailleerde informatie weer te geven.

Vragen in de grafiek:

* Hoe is het aantal aanraakpunten en mensen met een aanraking in de loop der tijd geëvolueerd?
* Hoe vergelijken de aanraakpunten per persoon van een kwartaal/maand met volgende?

![&#x200B; de tijdreeks van het dashboard van de Betrokkenheid van touchpoints en mensen aanraakten &#x200B;](assets/engagement-dashboard-1.png)

### Aanraakpunten/Personen met Kanaal {#touchpoints-people-touched-by-channel}

Staafdiagram waarin aanraakpunten of Personen met aanraakpunten worden weergegeven die zijn gesegmenteerd door Kanaal/Subkanaal/Campagne.

* de functies voor uitvouwen en Omhoog gebruiken om de gegevens te categoriseren op Subkanaal en Campagne.
* Houd de muisaanwijzer boven elke balk om de aanraakpunten of de personen die u aanraakt, weer te geven.

Vragen in de grafiek:

* Welk kanaal/Subkanaal/Campagne leidde de meeste betrokkenheid?
* Hoe vergelijk het aantal aanraakpunten met de personen die binnen een specifiek kanaal/subkanaal/campagne worden aangeraakt?

![&#x200B; dashboardgrafiek van het Betrokkenheid van touchpoints en mensen door kanaal &#x200B;](assets/engagement-dashboard-2.png)

## Filtervenster {#filter-pane}

Dit dashboard is uitgerust met de volgende instellingen en filters:

* Datum (gebaseerd op aanraakpuntdatum)
* Kanaal, subkanaal
* Campaign
