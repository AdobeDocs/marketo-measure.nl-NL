---
description: '[!DNL Marketo Measure] Veelgestelde vragen over weergave door kenmerk -  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] Veelgestelde vragen over weergave door kenmerk'
exl-id: d20e88f3-3ff8-4381-a4b8-6862798caa74
feature: Attribution
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 1%

---


# [!DNL Marketo Measure] Veelgestelde vragen over weergave door kenmerk {#marketo-measure-view-through-attribution-faq}

## Wat is Weergeven door kenmerk? {#what-is-view-through-attribution}

Met de functie [!DNL Marketo Measure] [!UICONTROL View Through Attribution] kunt u ook indrukken en toevoegen in het attributiemodel opnemen.

>[!IMPORTANT]
>Vanwege privacyproblemen zijn cookies van derden op weg. Google Chrome kondigde aan dat de cookies van derden in het derde kwartaal van 2024 zijn vervangen. Dit betekent dat deze vorm van bijhouden is geëindigd. Als gevolg hiervan is Adobe bezig Marketo Measure-functies af te schaffen die afhankelijk zijn van cookies van derden, met name Cross-Domain Tracking and View-through Attribution, die gebruikmaken van het Google/DoubleClick-imitatiecookie. Geen enkele andere functie van Marketo Measure wordt beïnvloed. Het cookie-gebruik van de eerste partij wordt ook niet beïnvloed. In het licht van het Google-schema is de verwachte vervaldatum voor de twee bovenstaande functies 16-01-2024. Gerelateerde gegevens die vóór deze datum zijn verzameld, blijven beschikbaar voor Adobe-klanten.

## Waarom is [!UICONTROL View Through Attribution] belangrijk? {#why-is-view-through-attribution-important}

In het verleden was het voor de marktpartijen moeilijk om reclame te heroriënteren of de indruk te wekken bij de analyse van de toeschouwers. Potentiële klanten kunnen na verloop van tijd worden blootgesteld aan opnieuw plaatsen van advertenties, maar het is onwaarschijnlijk dat ze op een van deze advertenties klikken en een formulier binnen dezelfde sessie invullen. Onze oplossing Weergeven door kenmerk heeft nu de mogelijkheid om te traceren of iemand al dan niet werd blootgesteld aan een impressie. Dit aanraakpunt zal aan het individuele verslag worden toegevoegd en zal door tot het vooruitzicht een cliënt worden. Met deze informatie krijgt de marktleider nu betere insight over de prestaties van zijn heroriënterende reclame.

## Wat is de rol van de Commissie bij het opzetten van dit project? {#what-is-involved-in-setting-this-up}

[!DNL Marketo Measure] kan alleen beginnen met het meten van de advertentie als er een impressie-tag is die moet worden geplaatst in Dubbelklik op Campagnebeheer. Als de tag eenmaal is geïmplementeerd, worden de afbeeldingen opgeslagen in onze logboeken en zorgen we voor de rest. Ga naar Succesbeheer als u geïnteresseerd bent in het meten van weergave via attributie.

## Welke advertentieplatforms worden ondersteund? {#which-ad-platforms-are-supported}

Momenteel ondersteunen we [!DNL Doubleclick] Campagnebeheer.

## Hoe wordt de attributie berekend? {#how-is-the-attribution-calculated}

We hebben een zorgvuldige analyse uitgevoerd van de gegevens van de indruk en de invloed ervan op conversies in alle stadia en in alle afzetkanalen. De verdeling varieert afhankelijk van het model zoals u in de onderstaande tabel kunt zien:

<table>
 <colgroup>
  <col>
  <col>
  <col>
  <col>
  <col>
  <col>
  <col>
 </colgroup>
 <tbody>
  <tr>
   <th><br></th>
   <th>Eerste aanraking</th>
   <th>Aanmaken van lead</th>
   <th>U-vorm</th>
   <th>W-vorm</th>
   <th>Volledig pad</th>
   <th>Aangepast model</th>
  </tr>
  <tr>
   <td><strong>Impressies</strong></td>
   <td>0%</td>
   <td>0%</td>
   <td>10%</td>
   <td>10%</td>
   <td>10%</td>
   <td>Aangepast</td>
  </tr>
  <tr>
   <td><strong>FT</strong></td>
   <td>100%</td>
   <td>0%</td>
   <td>35%</td>
   <td>26,6%</td>
   <td>20%</td>
   <td>Aangepast</td>
  </tr>
  <tr>
   <td><strong>LC</strong></td>
   <td>0%</td>
   <td>100%</td>
   <td>35%</td>
   <td>26,6%</td>
   <td>20%</td>
   <td>Aangepast</td>
  </tr>
  <tr>
   <td><strong>OC</strong></td>
   <td>0%</td>
   <td>0%</td>
   <td>0%</td>
   <td>26,6%</td>
   <td>20%</td>
   <td>Aangepast</td>
  </tr>
  <tr>
   <td><strong>Gesloten</strong></td>
   <td>0%</td>
   <td>0%</td>
   <td>0%</td>
   <td>0%</td>
   <td>20%</td>
   <td>Aangepast</td>
  </tr>
  <tr>
   <td><strong>Midden</strong></td>
   <td>0%</td>
   <td>0%</td>
   <td>20%</td>
   <td>10%</td>
   <td>10%</td>
   <td>Aangepast</td>
  </tr>
 </tbody>
</table>

## Hoe ziet dit eruit in [!DNL Salesforce?] {#what-will-this-look-like-in-salesforce}

[!DNL Marketo Measure] maakt één aanraakpunt voor de indruk op elke lead die aan de advertentie is blootgesteld. We kunnen de gebruiker in kaart brengen, zelfs nadat deze voor het eerst naar uw website (FT) is gekomen en een formulier (LC) invullen. Het aanraakpunt bevat advertentiegegevens zoals Naam/id van advertentiecampagne, Advertentie-id, Advertentie-inhoud, Sitenaam/ID, Plaatsingsnaam/id, Marketingkanaal, Geo, Refereringspagina en meer.

Het attributiemodel view-through is afhankelijk van de client en de bijbehorende gegevens.
