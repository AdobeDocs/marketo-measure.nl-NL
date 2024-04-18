---
unique-page-id: 18874652
description: "[!DNL Marketo Measure] Veelgestelde vragen over weergave door kenmerk - [!DNL Marketo Measure]"
title: "[!DNL Marketo Measure] Veelgestelde vragen over kenmerk bekijken"
exl-id: d20e88f3-3ff8-4381-a4b8-6862798caa74
feature: Attribution
source-git-commit: 48962b999fdd16fe96d18708ec301e64a39bc76e
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 0%

---

# [!DNL Marketo Measure] Veelgestelde vragen over weergave door kenmerk {#marketo-measure-view-through-attribution-faq}

## Wat is Weergeven door kenmerk? {#what-is-view-through-attribution}

De [!DNL Marketo Measure] [!UICONTROL View Through Attribution] Deze functie omvat de mogelijkheid om advertenties op te nemen in het toewijzingsmodel.

>[!IMPORTANT]
>
>Vanwege privacyproblemen zijn cookies van derden op weg. Google Chrome kondigde in het derde kwartaal van 2024 de afleiding van cookies van derden aan, en markeert in feite het einde van deze vorm van bijhouden. Als gevolg hiervan worden Marketo Measure-functies die afhankelijk zijn van cookies van derden afgekeurd door de Adobe, met name Cross-Domain Tracking en View-through Attribution, die gebruikmaken van het Google/DoubleClick-imitatiecookie. Geen enkele andere functie van Marketo Measure wordt beïnvloed. Het cookie-gebruik van de eerste partij wordt ook niet beïnvloed. In het licht van het Google-schema is de verwachte vervaldatum voor de twee bovenstaande functies 16-01-2024. Verwante gegevens die vóór deze datum zijn verzameld, blijven beschikbaar voor klanten van de Adobe.

## Waarom is [!UICONTROL View Through Attribution] Belangrijk? {#why-is-view-through-attribution-important}

In het verleden was het voor de marktpartijen moeilijk om reclame te heroriënteren of de indruk te wekken bij de analyse van de toeschouwers. Potentiële klanten kunnen na verloop van tijd worden blootgesteld aan opnieuw plaatsen van advertenties, maar het is onwaarschijnlijk dat ze op een van deze advertenties klikken en een formulier binnen dezelfde sessie invullen. Onze oplossing Weergeven door kenmerk heeft nu de mogelijkheid om te traceren of iemand al dan niet werd blootgesteld aan een impressie. Dit aanraakpunt zal aan het individuele verslag worden toegevoegd en zal door tot het vooruitzicht een cliënt worden. Met deze informatie krijgt de markt nu meer inzicht in de prestaties van hun heroriënterende reclame.

## Wat is de rol van de Commissie bij het opzetten van dit project? {#what-is-involved-in-setting-this-up}

Om [!DNL Marketo Measure] Als u de advertentietekens wilt gaan meten, moet u een impressietag plaatsen in Dubbelklik op Campagnebeheer. Als de tag eenmaal is geïmplementeerd, worden de afbeeldingen opgeslagen in onze logboeken en zorgen we voor de rest. Ga naar Succesbeheer als u geïnteresseerd bent in het meten van weergave via attributie.

## Welke advertentieplatforms worden ondersteund? {#which-ad-platforms-are-supported}

Wij steunen momenteel [!DNL Doubleclick] Campagnebeheer.

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

[!DNL Marketo Measure] wordt één aanraakpunt voor de indruk gemaakt op elke lead die aan de advertentie is blootgesteld. We kunnen de gebruiker in kaart brengen, zelfs nadat deze voor het eerst naar uw website (FT) is gekomen en een formulier (LC) invullen. Het aanraakpunt bevat advertentiegegevens zoals Naam/id van advertentiecampagne, Advertentie-id, Advertentie-inhoud, Sitenaam/ID, Plaatsingsnaam/id, Marketingkanaal, Geo, Refereringspagina en meer.

Het attributiemodel view-through is afhankelijk van de client en de bijbehorende gegevens.
