---
description: '[!DNL Marketo Measure] Cookies -  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] Cookies'
exl-id: de6e35ae-af92-43ba-8416-3e07d3dd470c
feature: Tracking
hidefromtoc: true
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 4%

---

# Marketo Measure Cookies {#marketo-measure-cookies}

Meer informatie over de verschillende [!DNL Marketo Measure] cookies die op uw site worden geladen wanneer u de [!DNL Marketo Measure] JavaScript toepast op uw bestemmingspagina&#39;s. Deze informatie kan tijdens de implementatie nuttig zijn voor het webontwikkelingsteam.

>[!IMPORTANT]
>
>Vanwege privacyproblemen zijn cookies van derden op weg. Google Chrome kondigde aan dat de cookies van derden in het derde kwartaal van 2024 zijn vervangen. Dit betekent dat deze vorm van bijhouden is geëindigd. Als gevolg hiervan is Adobe bezig Marketo Measure-functies af te schaffen die afhankelijk zijn van cookies van derden, met name Cross-Domain Tracking and View-through Attribution, die gebruikmaken van het Google/DoubleClick-imitatiecookie. Geen enkele andere functie van Marketo Measure wordt beïnvloed. Het cookie-gebruik van de eerste partij wordt ook niet beïnvloed. In het licht van het Google-schema is de verwachte vervaldatum voor de twee bovenstaande functies 16-01-2024. Gerelateerde gegevens die vóór deze datum zijn verzameld, blijven beschikbaar voor Adobe-klanten.

| Naam cookie | Type cookie | Doel | Vervaldatum | Heeft u een veilige vlag ingesteld? | Heeft alleen HTTP-vlag ingesteld? | Koekjesset |
| --- | --- | --- | --- | --- | --- | --- |
| `_biz_uid` | Eerste partij | Identificeer een gebruiker op het huidige domein uniek. | 1 jaar | Nee | Nee | `bizible.js` |
| `_biz_nA` | Eerste partij | Een volgnummer dat Marketo Measure voor alle aanvragen voor interne diagnostische doeleinden invoert. | 1 jaar | Nee | Nee | `bizible.js` |
| `_biz_flagsA` | Eerste partij | Een cookie die verschillende gebruikersgegevens opslaat, zoals formulierverzending, interdomeinmigratie, doorkijkpixel, status voor het volgen van een opt-out, enzovoort. | 1 jaar | Nee | Nee | `bizible.js` |
| `_biz_pendingA` | Eerste partij | Hiermee worden analysegegevens tijdelijk opgeslagen totdat ze naar de Marketo Measure-server zijn verzonden. | 1 jaar | Nee | Nee | `bizible.js` |
| `_biz_ABTestA` | Eerste partij | Lijst met controlesommen uit de gegevens van Optimizely en Visual Web Optimizer ABTests die reeds zijn gemeld, verhinderend `bizible.js` verzamelde gegevens opnieuw te verzenden. | 1 jaar | Nee | Nee | `bizible.js` |
| `_biz_EventA` | Eerste partij | Lijst met controlesommen die door Bizible Events worden gerapporteerd om te voorkomen dat `bizible.js` verzamelde gegevens opnieuw verzendt. | 1 jaar | Nee | Nee | `bizible.js` |
| `_biz_su` | Eerste partij | De universele gebruiker - identiteitskaart om een gebruiker over veelvoudige domeinen te identificeren, slechts toepasselijk op huurders met integratie die ITP beperkingen omzeilen. | 1 jaar | Ja | Nee | Edgecast |
| `_BUID` | Derden, domein=.bizible.com | Universele gebruiker - identiteitskaart om een gebruiker over veelvoudige domeinen te identificeren. | 1 jaar | Ja | Nee | Edgecast |
| `_BUID` | Derden, domein=.bizibly.com | Toewijzing tussen de cookie-id van Marketo Measure op het domein van de huurder en de Cookie-id van de Doubleclick. | 1 jaar | Ja | Nee | Edgecast |

Als een waarschuwing van de Firewall van de Toepassing van het Web (WAF) tijdens de opstelling van JavaScript wordt teweeggebracht, kunnen de gebruikers of die regel van WAF onbruikbaar maken of de koekjes, zoals het volgende voorbeeld lijsten van gewenste personen:

![ als een waarschuwing van de Firewall van de Toepassing van het Web (WAF) tijdens JavaScript ](assets/adding-script-1.png) wordt teweeggebracht
