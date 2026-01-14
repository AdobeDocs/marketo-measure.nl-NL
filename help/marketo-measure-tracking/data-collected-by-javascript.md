---
description: Gegevens verzameld door JavaScript-richtlijnen voor Marketo Measure-gebruikers
title: Gegevens verzameld door JavaScript
feature: Tracking
exl-id: 83814168-9d3e-45ac-b514-df58f0b2e90b
hidefromtoc: true
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%

---

# Gegevens verzameld door JavaScript {#data-collected-by-javascript}

Meer informatie over de gegevens die Marketo Measure JavaScript bij de implementatie heeft verzameld.

**verzoek van de Steekproef:**

```text
https://cdn.bizible.com/m/ipv?_biz_r=https%3A%2F%2Fwww.google.com%2F&_biz_h=-1801745101&_biz_u=7059e81415f34f7bbaf40fe32fdcba21&_biz_s=8cbeed&_biz_l=https%3A%2F%2Fwww.zendesk.com%2Fservice%2F&_biz_t=1676483822155&_biz_i=Customer%20service%20software%20for%20the%20best%20customer%20experiences%20%7C%20Zendesk&_biz_n=0&rnd=235938&cdn_o=a&_biz_z=1676483822155
```

<br>

Marketo Measure verzamelt de volgende algemene gegevens voor alle typen aanvragen:

| Oorsprong | Naam | Gegevenstype | Doel |
| --- | --- | --- | --- |
| Koptekst aanvragen | IP-adres | string | De locatie van de gebruiker wordt afgeleid via GeoIP-zoekopdracht. Deze gegevens zijn tijdelijk en niet permanent opgeslagen. |
| Koptekst aanvragen | user-agent tekenreeks | string | Hiermee bepaalt u welk apparaat de gebruiker gebruikt. |
| Query-parameter | `_biz_u` | string | Bizible cookie ID. |
| Query-parameter | `_biz_l` | string | Huidige pagina-URL. |
| Query-parameter | `_biz_t` | lang | Tijdstempel voor activiteit. |
| Query-parameter | `_biz_i` | string | Huidige paginatitel. |

Naast de bovenstaande algemene gegevens voegt bizible.js ook aanvullende gegevens toe afhankelijk van de hieronder gespecificeerde aanvraagtypen:

| Type aanvraag | Aanvraagpad | Aanvullende query-parameter | Gegevenstype | Doel |
| --- | --- | --- | --- | --- |
| Voorvertoning | `/ipv` | `_biz_r` | string | URL verwijzingspagina. |
|  |  | `_biz_h` | string | Schermresolutie van onderbroken client. |
|  |  | `_biz_c` | string | Optionele parameter. Als deze parameter aanwezig is, wijst het erop dat de huurder `bizible.js` vormt om op de toestemming van de gebruiker te wachten alvorens te volgen, en dat `bizible.js` de toestemming van de gebruiker heeft ontvangen om worden gevolgd. |
| Formulier verzenden | `/frm` | `eMail` | string | E-mailadres voor normale tekst. |
| Toewijzing van gebruikers-id | `/u` | `mapType` | enum | Welk type gebruikersidentificatie `bizible.js` gedetecteerd (Marketo Munchkin-id en Adobe ECID) |
|  |  | `mapValue` | string | De eigenlijke waarde van de cookie-id van derden voor de bovenstaande integratie. |

>[!NOTE]
>
>Bizible is de vroegere naam van Marketo Measure.
