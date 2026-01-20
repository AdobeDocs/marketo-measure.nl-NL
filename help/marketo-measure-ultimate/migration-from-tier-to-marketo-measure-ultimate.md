---
description: Leer over het migratieproces wanneer het bewegen van het  [!DNL Marketo Measure]  Gelaagde abonnement aan  [!DNL Marketo Measure]  Ultimate.
title: Migratie van Rij aan  [!DNL Marketo Measure]  Ultimate
feature: Integration, Tracking, Attribution
exl-id: 828c9bba-3835-484a-bd80-84b5a6b67e22
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 1%

---

# Migratie van niveau 1-2 naar [!DNL Marketo Measure] Ultimate {#migration-from-tier-to-marketo-measure-ultimate}

In dit artikel wordt het migratieproces beschreven voor gebruikers die van het Tier 1- of 2-abonnement naar [!DNL Marketo Measure] Ultimate gaan.

>[!IMPORTANT]
>
>Vergeet niet uw bestaande Tier-instantie te behouden totdat de migratie is voltooid.

## Gegevensverzameling {#data-collection}

### Webverkeersgegevens {#web-traffic-data}

* Er zijn geen wijzigingen vereist voor JavaScript-implementatie.

* Schakel domeinen in de nieuwe Ultimate-instantie in.

* Indien nodig, verzend een kaartje om historische Webgegevens te migreren en opnieuw te verwerken.

* Integraties van advertenties blijven ongewijzigd, maar vergeet niet om ze opnieuw te verbinden in Ultimate. Voordat u dit doet, moet u ervoor zorgen dat de Advertentierekeningen in de huurder van de Rij worden losgemaakt.

>[!NOTE]
>
>Historische gegevens en kostengegevens worden niet geïmporteerd. We importeren en maken alleen kostengegevens beschikbaar die verder gaan nadat de advertentierekeningen opnieuw zijn aangesloten.

### Bedrijfsgegevensverbinding {#enterprise-data-connection}

Implementeer alle brongegevensverbindingen in AEP opnieuw, inclusief CRM- en Marketo Engage-verbindingen.

## Gegevenstransformatie {#data-transformation}

* Account-Based Marketing-functies, zoals &#39;lead-to-account&#39;-overeenkomsten en voorspellende betrokkenheidsscores, zijn niet beschikbaar in Ultimate.

   * U kunt echter wel de resultaten van de overeenkomst tussen leads en accounts importeren via AEP en deze binnen het platform gebruiken.

* In Ultimate worden CRM-overgangen in het historisch stadium afgeleid in plaats van rechtstreeks gelezen, aangezien er geen directe CRM-verbinding is.

   * We lezen opportuniteitsrecords en tijdstempels en zien het huidige stadium, en trekken vervolgens de historische fases af.

## Rapportage {#reporting}

* Ultimate stuurt gegevens niet terug naar CRM&#39;s.

   * Als u gegevens wilt terugsturen naar de CRM, is een aangepaste ETL-pijpleiding vereist om gegevens van Marketo Measure Snowflake naar de CRM te extraheren. U moet opstelling een model van douanegegevens in uw CRM.

* Alle Discover-dashboards blijven hetzelfde als in de Tiered-oplossing, met toevoeging van Attribution AI-dashboards.
