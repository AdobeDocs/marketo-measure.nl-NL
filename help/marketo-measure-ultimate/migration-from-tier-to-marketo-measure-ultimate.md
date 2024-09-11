---
description: Leer over het migratieproces wanneer het bewegen van het  [!DNL Marketo Measure]  Gelaagde abonnement aan  [!DNL Marketo Measure]  Ultimate.
hide: true
hidefromtoc: true
title: Migratie van Rij aan  [!DNL Marketo Measure]  Ultieme
feature: Integration, Tracking, Attribution
source-git-commit: 0c94276bec390bb67dafe5dd679c1a0378a05c85
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 1%

---

# Migratie van niveau 1-2 naar [!DNL Marketo Measure] Ultimate {#migration-from-tier-to-marketo-measure-ultimate}

Dit artikel beschrijft het migratieproces voor gebruikers die van het Tier 1- of 2-abonnement naar Marketo Measure Ultimate overstappen.

>[!IMPORTANT]
>
>Vergeet niet uw bestaande Tier-instantie te behouden totdat de migratie is voltooid.

## Gegevensverzameling {#data-collection}

### Webverkeersgegevens {#web-traffic-data}

* Er zijn geen wijzigingen vereist voor JavaScript-implementatie.

* Schakel domeinen in de nieuwe Ultimate-instantie in.

* Indien nodig, verzend een kaartje om historische Webgegevens te migreren en opnieuw te verwerken.

* De integratie van toevoegingen blijft ongewijzigd, maar vergeet niet om deze opnieuw aan te sluiten in Ultimate. Voordat u dit doet, moet u ervoor zorgen dat de Advertentierekeningen in de huurder van de Rij worden losgemaakt.

>[!NOTE]
>
>Historische gegevens en kostengegevens worden niet geïmporteerd. We importeren en maken alleen kostengegevens beschikbaar die verder gaan nadat de advertentierekeningen opnieuw zijn aangesloten.

### Bedrijfsgegevensverbinding {#enterprise-data-connection}

Implementeer alle brongegevensverbindingen in AEP opnieuw, inclusief CRM- en Marketo Engage-verbindingen.

## Gegevenstransformatie {#data-transformation}

* Account-Based Marketing-functies, zoals &#39;lead-to-account&#39;-overeenkomsten en voorspellende betrokkenheidsscores, zijn niet beschikbaar in Ultimate.

   * U kunt echter wel de resultaten van overeenkomsten tussen leads en accounts importeren via AEP en deze binnen het platform gebruiken.

* In Ultimate worden CRM-overgangen in het historisch stadium afgeleid in plaats van rechtstreeks gelezen, aangezien er geen directe CRM-verbinding is.

   * We lezen opportuniteitsrecords en tijdstempels en zien het huidige stadium, en trekken vervolgens de historische fases af.

## Rapportage {#reporting}

* Ultimate duwt gegevens niet terug naar CRM&#39;s.

   * Als het duwen van gegevens terug naar CRM wordt gewenst, wordt een douanepijpleiding ETL vereist om gegevens van de Snowflake van Marketo Measure aan CRM te halen. U moet opstelling een model van douanegegevens in uw CRM.

* Alle Discover-dashboards blijven hetzelfde als in de gelaagde oplossing, met toevoeging van Attribution AI-dashboards.
