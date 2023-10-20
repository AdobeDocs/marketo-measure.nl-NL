---
unique-page-id: 18874590
description: "[!DNL Marketo Measure] Cookies - [!DNL Marketo Measure] - Productdocumentatie"
title: "[!DNL Marketo Measure] Cookies"
exl-id: de6e35ae-af92-43ba-8416-3e07d3dd470c
feature: Tracking
source-git-commit: 69304dddf3569cd92c95a50e9a2e346acdad0f43
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 1%

---

# Marketo Measure Cookies {#marketo-measure-cookies}

Meer informatie over de verschillende [!DNL Marketo Measure] Cookies die op uw site worden geladen wanneer u de [!DNL Marketo Measure] JavaScript naar uw bestemmingspagina&#39;s. Deze informatie kan tijdens de implementatie nuttig zijn voor het webontwikkelingsteam.

<table>
<thead>
  <tr>
    <th>Naam cookie</th>
    <th>Type cookie</th>
    <th>Doel</th>
    <th>Vervaldatum</th>
    <th>Heeft u een veilige vlag ingesteld?<br></th>
    <th>Heeft alleen HTTP-vlag ingesteld?</th>
    <th>Koekjesset</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>_biz_uid</td>
    <td>Eerste partij</td>
    <td>Identificeer een gebruiker op het huidige domein uniek.</td>
    <td>1 jaar</td>
    <td>Nee</td>
    <td>Nee</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_nA</td>
    <td>Eerste partij</td>
    <td>Een volgnummer dat Marketo Measure voor alle aanvragen voor interne diagnostische doeleinden invoert.</td>
    <td>1 jaar</td>
    <td>Nee</td>
    <td>Nee</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_flagsA</td>
    <td>Eerste partij</td>
    <td>Een cookie die verschillende gebruikersgegevens opslaat, zoals formulierverzending, interdomeinmigratie, doorkijkpixel, status voor het volgen van een opt-out, enzovoort.</td>
    <td>1 jaar</td>
    <td>Nee</td>
    <td>Nee</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_pendingA</td>
    <td>Eerste partij</td>
    <td>Hiermee worden analysegegevens tijdelijk opgeslagen totdat ze naar de Marketo Measure-server zijn verzonden.</td>
    <td>1 jaar</td>
    <td>Nee</td>
    <td>Nee</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_ABTestA</td>
    <td>Eerste partij</td>
    <td>Lijst van controlesommen van Optimizely en de Visuele gegevens van ABTests van de Optimizer van het Web die reeds zijn gemeld, verhinderend bizible.js verzamelde gegevens opnieuw te verzenden.</td>
    <td>1 jaar</td>
    <td>Nee</td>
    <td>Nee</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_EventA</td>
    <td>Eerste partij</td>
    <td>Lijst van controlesommen die door Bizible Events worden gemeld om bizible.js te verhinderen verzamelde gegevens opnieuw te verzenden.</td>
    <td>1 jaar</td>
    <td>Nee</td>
    <td>Nee</td>
    <td>bizible.js</td>
  </tr>
  <tr>
    <td>_biz_su</td>
    <td>Eerste partij</td>
    <td>De universele gebruiker - identiteitskaart om een gebruiker over veelvoudige domeinen te identificeren, slechts toepasselijk op huurders met integratie die ITP beperkingen omzeilen.</td>
    <td>1 jaar</td>
    <td>Ja</td>
    <td>Nee</td>
    <td>Edgecast</td>
  </tr>
  <tr>
    <td>_BUID</td>
    <td>Third party, domain=.<a href="http://bizible.com/">bizible.com</a></td>
    <td>Universele gebruiker - identiteitskaart om een gebruiker over veelvoudige domeinen te identificeren.</td>
    <td>1 jaar</td>
    <td>Ja</td>
    <td>Nee</td>
    <td>Edgecast</td>
  </tr>
  <tr>
    <td>_BUID</td>
    <td>Third party, domain=.<a href="http://bizibly.com/">bizibly.com</a></td>
    <td>Toewijzing tussen de cookie-id van Marketo Measure op het domein van de huurder en de Cookie-id van de Doubleclick.</td>
    <td>1 jaar</td>
    <td>Ja</td>
    <td>Nee</td>
    <td>Edgecast</td>
  </tr>
</tbody>
</table>

Als een WAF-waarschuwing (Web Application Firewall) wordt geactiveerd tijdens de JavaScript-installatie, kunnen gebruikers die WAF-regel uitschakelen of de cookies toestaan en vermelden, zoals in het volgende voorbeeld:

![](assets/marketo-measure-cookies-1.png)
