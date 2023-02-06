---
unique-page-id: 18874590
description: "[!DNL Marketo Measure] Cookies - [!DNL Marketo Measure] - Productdocumentatie"
title: "[!DNL Marketo Measure] Cookies"
exl-id: de6e35ae-af92-43ba-8416-3e07d3dd470c
source-git-commit: 3a13ab3e497652d1975e69280a3d224ac95504aa
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 0%

---

# Marketo Measure Cookies {#marketo-measure-cookies}

Meer informatie over de verschillende [!DNL Marketo Measure] Cookies die op uw site worden geladen wanneer u de [!DNL Marketo Measure] JavaScript naar uw bestemmingspagina&#39;s. Deze informatie kan tijdens de implementatie nuttig zijn voor het webontwikkelingsteam.

| **Naam cookie** | **Type cookie** | **Doel** |
|---|---|---|
| _BUID | Derden, opgeslagen op .bizible.com-domein | Universal user id to identity the same user across multiple clients&#39; domain. |
| _biz_uid | Eerste partij | Gebruikers-id op het huidige domein. |
| _biz_sid | Eerste partij | Sessie-id van de gebruiker. |
| _biz_flagsA | Eerste partij | Eén cookie die meerdere gegevens opslaat, bijvoorbeeld of de gebruiker een formulier heeft verzonden, een migratie naar een ander domein heeft uitgevoerd, een weergavepixel heeft verzonden, heeft opgegeven dat de gegevens niet moeten worden bijgehouden, enzovoort. |
| _biz_nA | Eerste partij | Volgnummer dat [!DNL Marketo Measure] omvat voor alle verzoeken, voor intern diagnostisch doel |
| _biz_dfsA | Eerste partij | Hiermee worden gegevens uit een eerder verzonden formulier tijdelijk opgeslagen [!DNL bizible.js] ontvangt een configuratie-JS om te bepalen of het traceren van formulieren op HTTPS is ingeschakeld. |
| _biz_pendingA | Eerste partij | Hiermee slaat u tijdelijk analysegegevens op waarnaar niet is verzonden [!DNL Marketo Measure] nog niet. |

Als een WAF-waarschuwing (Web Application Firewall) wordt geactiveerd tijdens de JavaScript-installatie, kunnen gebruikers die WAF-regel uitschakelen of de cookies toestaan en vermelden, zoals in het volgende voorbeeld:

![](assets/marketo-measure-cookies-1.png)
