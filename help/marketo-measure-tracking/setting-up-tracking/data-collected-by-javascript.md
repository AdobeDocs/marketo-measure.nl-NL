---
description: Gegevens verzameld door JavaScript - [!DNL Marketo Measure] - Productdocumentatie
title: Gegevens verzameld door JavaScript
feature: Tracking
source-git-commit: 4953d6c51a87669ced0a13e2a54810d14976585c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# Gegevens verzameld door JavaScript {#data-collected-by-javascript}

Meer informatie over de gegevens die door Marketo Measure JavaScript bij de implementatie worden verzameld.

**Voorbeeldverzoek:**

```
https://cdn.bizible.com/m/ipv?_biz_r=https%3A%2F%2Fwww.google.com%2F&_biz_h=-1801745101&_biz_u=7059e81415f34f7bbaf40fe32fdcba21&_biz_s=8cbeed&_biz_l=https%3A%2F%2Fwww.zendesk.com%2Fservice%2F&_biz_t=1676483822155&_biz_i=Customer%20service%20software%20for%20the%20best%20customer%20experiences%20%7C%20Zendesk&_biz_n=0&rnd=235938&cdn_o=a&_biz_z=1676483822155
```

<br>

Marketo Measure verzamelt de volgende algemene gegevens voor alle typen aanvragen:

<table>
<thead>
  <tr>
    <th>Oorsprong</th>
    <th>Naam</th>
    <th>Gegevenstype</th>
    <th>Doel</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Koptekst aanvragen</td>
    <td>IP-adres</td>
    <td>string</td>
    <td>De locatie van de gebruiker wordt afgeleid via GeoIP-zoekopdracht. Deze gegevens zijn tijdelijk en niet permanent opgeslagen.</td>
  </tr>
  <tr>
    <td>Koptekst aanvragen</td>
    <td>user-agent tekenreeks</td>
    <td>string</td>
    <td>Hiermee bepaalt u welk apparaat de gebruiker gebruikt.</td>
  </tr>
  <tr>
    <td>Query-parameter</td>
    <td>_biz_u</td>
    <td>string</td>
    <td>Bizible cookie ID.</td>
  </tr>
  <tr>
    <td>Query-parameter</td>
    <td>_biz_l</td>
    <td>string</td>
    <td>Huidige pagina-URL.</td>
  </tr>
  <tr>
    <td>Query-parameter</td>
    <td>_biz_t</td>
    <td>lang</td>
    <td>Tijdstempel voor activiteit.</td>
  </tr>
  <tr>
    <td>Query-parameter</td>
    <td>_biz_i</td>
    <td>string</td>
    <td>Huidige paginatitel.</td>
  </tr>
</tbody>
</table>

Naast de bovenstaande algemene gegevens voegt bizible.js ook aanvullende gegevens toe afhankelijk van de hieronder gespecificeerde aanvraagtypen:

<table>
<thead>
  <tr>
    <th>Type aanvraag</th>
    <th>Aanvraagpad</th>
    <th>Aanvullende query-parameter</th>
    <th>Gegevenstype</th>
    <th>Doel</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Voorvertoning</td>
    <td>/ipv</td>
    <td>_biz_r</td>
    <td>string</td>
    <td>URL verwijzingspagina.</td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td>_biz_h</td>
    <td>string</td>
    <td>Schermresolutie van onderbroken client.</td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td>_biz_c</td>
    <td>string</td>
    <td>Optionele parameter. Als deze parameter aanwezig is, wijst het erop dat de huurder bizible.js vormt om op de toestemming van de gebruiker te wachten alvorens te volgen, en dat bizible.js de toestemming van de gebruiker heeft ontvangen om worden gevolgd.</td>
  </tr>
  <tr>
    <td>Formulier verzenden</td>
    <td>/frm</td>
    <td>eMail</td>
    <td>string</td>
    <td>E-mailadres voor normale tekst.</td>
  </tr>
  <tr>
    <td>Toewijzing van gebruikers-id</td>
    <td>/u</td>
    <td>mapType</td>
    <td>enum</td>
    <td>Welk type gebruikersidentificatie bizible.js gedetecteerd (Marketo Munchkin id en Adobe ECID)</td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td>mapValue</td>
    <td>string</td>
    <td>De eigenlijke waarde van de cookie-id van derden voor de bovenstaande integratie.</td>
  </tr>
</tbody>
</table>

>[!NOTE]
>
>Bizible is de vroegere naam van Marketo Measure.
