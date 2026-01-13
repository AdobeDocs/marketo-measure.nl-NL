---
description: '[!DNL Marketo Measure] Cookies -  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] Cookies'
exl-id: de6e35ae-af92-43ba-8416-3e07d3dd470c
feature: Tracking
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 4%

---


# Marketo Measure Cookies {#marketo-measure-cookies}

Meer informatie over de verschillende [!DNL Marketo Measure] cookies die op uw site worden geladen wanneer u de [!DNL Marketo Measure] JavaScript toepast op uw bestemmingspagina&#39;s. Deze informatie kan tijdens de implementatie nuttig zijn voor het webontwikkelingsteam.

>[!IMPORTANT]
>Vanwege privacyproblemen zijn cookies van derden op weg. Google Chrome kondigde aan dat de cookies van derden in het derde kwartaal van 2024 zijn vervangen. Dit betekent dat deze vorm van bijhouden is geëindigd. Als gevolg hiervan is Adobe bezig Marketo Measure-functies af te schaffen die afhankelijk zijn van cookies van derden, met name Cross-Domain Tracking and View-through Attribution, die gebruikmaken van het Google/DoubleClick-imitatiecookie. Geen enkele andere functie van Marketo Measure wordt beïnvloed. Het cookie-gebruik van de eerste partij wordt ook niet beïnvloed. In het licht van het Google-schema is de verwachte vervaldatum voor de twee bovenstaande functies 16-01-2024. Gerelateerde gegevens die vóór deze datum zijn verzameld, blijven beschikbaar voor Adobe-klanten.

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
    <td>Third party, domain=.<a href="https://business.adobe.com/nl/products/marketo/bizible.html"> bizible.com </a></td>
    <td>Universele gebruiker - identiteitskaart om een gebruiker over veelvoudige domeinen te identificeren.</td>
    <td>1 jaar</td>
    <td>Ja</td>
    <td>Nee</td>
    <td>Edgecast</td>
  </tr>
  <tr>
    <td>_BUID</td>
    <td>Third party, domain=.<a href="https://bizibly.com/"> bizible.com </a></td>
    <td>Toewijzing tussen de cookie-id van Marketo Measure op het domein van de huurder en de Cookie-id van de Doubleclick.</td>
    <td>1 jaar</td>
    <td>Ja</td>
    <td>Nee</td>
    <td>Edgecast</td>
  </tr>
</tbody>
</table>

Als een waarschuwing van de Firewall van de Toepassing van het Web (WAF) tijdens de opstelling van JavaScript wordt teweeggebracht, kunnen de gebruikers of die regel van WAF onbruikbaar maken of de koekjes, zoals het volgende voorbeeld lijsten van gewenste personen:

![&#x200B; de waarschuwing van WAF van het Voorbeeld vragend om de koekjes van Marketo Measure van de lijst van gewenste personen te voeren &#x200B;](assets/marketo-measure-cookies-1.png)
