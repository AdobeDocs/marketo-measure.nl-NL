---
description: Uitleg van de Plaatsen van het Aanraakpunt en Generatie over BTs en BBTs -  [!DNL Marketo Measure]
title: Uitleg van plaatsen van het Aanraakpunt en Generatie over BTs en  [!DNL BATs]
exl-id: 4903f917-a366-4767-a126-5216d2377399
feature: Touchpoints
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 0%

---

# Uitleg van aanraakpuntposities en genereren over BT&#39;s en [!DNL BATs] {#explanation-of-touchpoint-positions-and-generation-across-bts-and-bats}

**Generatie van de Plaatsen van het Aanraakpunt &amp; Stroom door de Reis van Kopers**

Kennis van de Buyer Touchpoint-posities en hoe deze worden geactiveerd is van cruciaal belang voor een geslaagde rapportage met [!DNL Marketo Measure] -gegevens. Je wilt een duidelijk inzicht hebben in wat je vooruitzichten deden toen ze door de reis van de koper gingen en op zijn beurt hoe dat eruit zal zien in de Touchpoint data. Voor meer context over dit onderwerp raden we aan het artikel [[!UICONTROL Touchpoint Generation & Mapping]](/help/configuration-and-setup/getting-started-with-marketo-measure/touchpoint-generation-and-mapping.md) te bekijken.

[!DNL Marketo Measure] heeft verschillende aanraakpunten die worden geactiveerd door verschillende stappen tijdens de reis van de koper. Bij het rapporteren van [!DNL Marketo Measure] -gegevens zijn er twee sets aanraakpuntgegevens, aanraakpunten voor kopers (BT&#39;s) en aanraakpunten voor kopers (BBT&#39;s). Het kan zijn dat deze gegevenssets enigszins verschillende posities hebben, aangezien ze betrekking hebben op verschillende objecten. Voor meer context over dit onderwerp, adviseren wij het [&#x200B; Verschil tussen de Aanraakpunten van de Koper (BTs) &amp; de Aanraakpunten van de Attributie van de Koper (BBTs) &#x200B;](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md) artikel te herzien.

**Aanraakpunten van de Koper (BTs)**: Dit zijn de aanraakpunten verbonden aan een individuele persoon en hun reis en zullen aan dat individu uniek zijn. Het volgende uit de vakrapporten wordt gebouwd van de gegevens van Buyer Touchpoint.

* [!DNL Marketo Measure] 101: Leads op id
* [!DNL Marketo Measure] 101: Regelafstand per kanaal
* [!DNL Marketo Measure] 101: ID van lead/contactpersoon
* [!DNL Marketo Measure] 101: Lead/Contact via kanaal

Hieronder wordt een overzicht gegeven van de Buyer Touchpoint-standpunten die aangeven waar een individu op reis is en welke maatregelen zij hebben genomen om die positie te verwerven.

<table> 
 <tbody>
  <tr>
   <th>Positie Buyer Touchpoint (BT)</th> 
   <th>Type aanraakpunt (handeling die aanraakpunt kan activeren)</th> 
   <th>Beschrijving van aanraakpunt</th> 
  </tr>
  <tr>
   <td>Eerste aanraking (FT)</td> 
   <td>Webbezoek</td> 
   <td>De eerste marketinginteractie die een individu heeft met uw merk</td> 
  </tr>
  <tr>
   <td>Lood maken (LC)</td> 
   <td>De Vulling van de vorm <strong> OF </strong> Campagne/de Opname van het Programma</td> 
   <td>De eerste formuliervullingen die een individu heeft (doorgaans een formulierverzending, maar ook een campagne-/programmacode)</td> 
  </tr>
  <tr>
   <td>Post LC</td> 
   <td>De Vulling van de vorm <strong> OF </strong> Campagne/de Opname van het Programma</td> 
   <td>Elk formulier dat een individu invult nadat het LC (of een volgende campagne/programma-opname) is voltooid</td> 
  </tr>
 </tbody>
</table>

**Aanraakpunten van de Attributie van de Koper (BATS)**: Dit zijn de aanraakpunten die aan een Kans en zijn reis worden geassocieerd. Deze aanraakpunten worden verbonden met inkomsten aangezien zij met de Kans en zijn Contacten worden verbonden. Het volgende uit de vakrapporten wordt gebouwd van de gegevens van Buyer Attribution Touchpoint.

* [!DNL Marketo Measure] 101: Kansen op id
* [!DNL Marketo Measure] 101: Kansen per id-kanaal

<table> 
 <tbody>
  <tr>
   <th>Positie Buyer Attribution Touchpoint (BBT)</th> 
   <th>Type aanraakpunt (handeling die aanraakpunt kan activeren)</th> 
   <th>Beschrijving van aanraakpunt</th> 
  </tr>
  <tr>
   <td>Eerste aanraking (FT)</td> 
   <td>Webbezoek</td> 
   <td>De eerste marketinginteractie die een contact met uw merk had</td> 
  </tr>
  <tr>
   <td>Lood maken (LC)</td> 
   <td>De Vulling van de vorm <strong> OF </strong> Campagne/de Opname van het Programma</td> 
   <td>Het eerste formulier dat een contactpersoon invult, heeft (meestal een formulier verzenden, maar kan ook een campagne/programma-opname zijn)</td> 
  </tr>
  <tr>
   <td>Opportunity maken</td> 
   <td>De Vulling van de vorm <strong> OF </strong> Bezoek van het Web <strong> OF </strong> Campagne/de Opname van het Programma</td> 
   <td>De marketinginteractie die het dichtst bij het moment ligt waarop de Opp wordt gemaakt</td> 
  </tr> 
  <tr>
   <td>Gesloten won/Verloren</td> 
   <td>De Vulling van de vorm <strong> OF </strong> Bezoek van het Web <strong> OF </strong> Campagne/de Opname van het Programma</td> 
   <td>De marketinginteractie die het dichtst bij staat wanneer de Opp wordt gesloten (Won of Verloren)</td> 
  </tr>
  <tr>
   <td>Midden aanraken</td> 
   <td>De Vulling van de vorm <strong> OF </strong> Campagne/de Opname van het Programma</td> 
   <td>Wanneer een contact een online vorm invult en het niet samenvalt met mijlpaal touchpoint</td> 
  </tr>
 </tbody>
</table>

[!DNL Marketo Measure] heeft deze twee reeksen gegevens van het Aanraakpunt om een duidelijk inzicht in de reis van een individu en de Kansen te creëren. Deze twee Touchpoint-gegevenssets geven u een duidelijke kaart van wat er gebeurd is van boven naar beneden in funnel.

In het volgende voorbeeld ziet u de gegevensstroom van de aanraakpunten voor kopers (BT&#39;s) naar de aanraakpunten voor koperkenmerken (BAT&#39;s). In dit voorbeeld maken Person A en Person B beide deel uit van dezelfde Opportunity die een Gemaakt Datum van 3.7.2020 en een Dichte Datum van 5.6.2020 heeft.

**Persoon A** de Reeks van Gegevens van Buyer Touchpoint

* First Touch (FT) - Paid Search.AdWords - 9/1/2019
* Loodcreatie (LC) - Organic Search.Google - 11-20-2019
* Post LC (form fill) - Webinar - 3/4/2020

**Persoon B** de Reeks van Gegevens van Buyer Touchpoint

* First Touch (FT) - Paid Social.Facebook - 26-8-2019
* Loodcreatie (LC) - Organic Search.Yahoo - 20-20-2020
* Post LC (form fill) - E-mail - 5/1/2020

**Kansen** de gegevens van Buyer Attribution Touchpoint zouden als volgt lezen...

* First Touch (FT) - Paid Social.Facebook - 26-8-2019
   * (van **Persoon B** omdat zij ware _Eerste aanraking_ voor de Rekening/Opp hebben)
* Loodcreatie (LC) - Organic Search.Google - 11-20-2019
   * (van **Persoon A** omdat zij de ware _Leiding_ voor de Rekening/Opp hebben)
* Opportunity Creation (OC) - Webinar - 3-4-2020
   * (Post LC touchpoint van **Persoon A** zou het _Aanraakpunt OC_ zijn omdat het de meest recente interactie was wij aan de Kans die op 3/7/2020 wordt gecreeerd)
* Gesloten won - E-mail - 15-2020
   * (Post LC touchpoint van **Persoon B** zou het _Gesloten Aanraakpunt van de Won_ zijn omdat het de meest recente interactie was wij aan de Kans die op 5/6/2020 wordt gesloten)
