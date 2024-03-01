---
description: Uitleg van aanraakpuntposities en het genereren van BT's en BBT's - [!DNL Marketo Measure]
title: Uitleg van aanraakpuntposities en genereren over BT's en [!DNL BATs]
exl-id: 4903f917-a366-4767-a126-5216d2377399
feature: Touchpoints
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 0%

---

# Uitleg van aanraakpuntposities en genereren over BT&#39;s en [!DNL BATs] {#explanation-of-touchpoint-positions-and-generation-across-bts-and-bats}

**Opwekken van aanraakpunten en doorlopen via de kopersreis**

Een goed begrip van de posities van het aanraakpunt voor kopers en de manier waarop deze worden geactiveerd is van cruciaal belang voor een geslaagde rapportage met [!DNL Marketo Measure] gegevens. Je wilt een duidelijk inzicht hebben in wat je perspectieven deden toen ze door de reis van de koper gingen en op zijn beurt hoe dat eruit zal zien in de Touchpoint-gegevens. Voor meer context over dit onderwerp adviseren wij het herzien van [[!UICONTROL Touchpoint Generation & Mapping]](/help/configuration-and-setup/getting-started-with-marketo-measure/touchpoint-generation-and-mapping.md) artikel.

[!DNL Marketo Measure] heeft verschillende aanraakpunten die worden geactiveerd door verschillende stappen in de reis van de koper. Bij rapportage over [!DNL Marketo Measure] Er zijn twee sets aanraakpuntgegevens, aanraakpunten voor kopers (BT&#39;s) en aanraakpunten voor kopers (BBT&#39;s). Het kan zijn dat deze gegevenssets enigszins verschillende posities hebben, aangezien ze betrekking hebben op verschillende objecten. Voor meer context over dit onderwerp adviseren wij het herzien van [Verschil tussen aanraakpunten voor kopers (BT&#39;s) en aanraakpunten voor kopers (BAT&#39;s)](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md) artikel.

**Aanraakpunten koper (BT&#39;s)**: Dit zijn de aanraakpunten met een individuele persoon en zijn reis en zullen uniek zijn voor dat individu. De volgende rapporten in het vak zijn samengesteld uit gegevens van het aanraakpunt voor kopers.

* [!DNL Marketo Measure] 101: Leads op ID
* [!DNL Marketo Measure] 101: Regelafstand per kanaal
* [!DNL Marketo Measure] 101: lood/contact op ID
* [!DNL Marketo Measure] 101: lood/contact via kanaal

Hieronder wordt een overzicht gegeven van de posities van het aanraakpunt voor kopers, waarin wordt beschreven waar een individu zich bevindt en welke acties zij hebben ondernomen om die positie te veroveren.

<table> 
 <tbody>
  <tr>
   <th>Positie aanraakpunt koper</th> 
   <th>Type aanraakpunt (handeling die aanraakpunt kan activeren)</th> 
   <th>Beschrijving van aanraakpunt</th> 
  </tr>
  <tr>
   <td>Eerste aanraking (FT)</td> 
   <td>Webbezoek</td> 
   <td>De allereerste marketinginteractie die een individu heeft met uw merk</td> 
  </tr>
  <tr>
   <td>Lood maken (LC)</td> 
   <td>Formuliervulling <strong>OF</strong> Campagne/opname van programma</td> 
   <td>Het allereerste formulier dat een individu invult, heeft (meestal een formulier verzenden, maar kan ook een campagne/programma-opname zijn)</td> 
  </tr>
  <tr>
   <td>Post LC</td> 
   <td>Formuliervulling <strong>OF</strong> Campagne/opname van programma</td> 
   <td>Elk formulier dat een individu invult nadat het LC (of een volgende campagne/programma-opname) is voltooid</td> 
  </tr>
 </tbody>
</table>

**Aanraakpunten voor koperkenmerken (BATS)**: Dit zijn de aanraakpunten die verbonden zijn aan een Opportunity en zijn reis. Deze aanraakpunten zullen met opbrengst worden verbonden aangezien zij met de Kans en zijn Contacten worden verbonden. De volgende rapporten in het vak zijn samengesteld uit gegevens van het aanraakpunt voor koperkenmerken.

* [!DNL Marketo Measure] 101: Kansen per id
* [!DNL Marketo Measure] 101: Kansen per id-kanaal

<table> 
 <tbody>
  <tr>
   <th>Positie van het aanraakpunt voor koperkenmerken (BBT)</th> 
   <th>Type aanraakpunt (handeling die aanraakpunt kan activeren)</th> 
   <th>Beschrijving van aanraakpunt</th> 
  </tr>
  <tr>
   <td>Eerste aanraking (FT)</td> 
   <td>Webbezoek</td> 
   <td>De allereerste marketinginteractie die een contact had met uw merk</td> 
  </tr>
  <tr>
   <td>Lood maken (LC)</td> 
   <td>Formuliervulling <strong>OF</strong> Campagne/opname van programma</td> 
   <td>Het allereerste formulier dat een contactpersoon invult, heeft (meestal een formulier verzenden, maar kan ook een campagne/programma-opname zijn)</td> 
  </tr>
  <tr>
   <td>Opportunity maken</td> 
   <td>Formuliervulling <strong>OF</strong> Webbezoek <strong>OF</strong> Campagne/opname van programma</td> 
   <td>De marketinginteractie die het dichtst bij het moment ligt waarop de Opp wordt gemaakt</td> 
  </tr> 
  <tr>
   <td>Gesloten won/Verloren</td> 
   <td>Formuliervulling <strong>OF</strong> Webbezoek <strong>OF</strong> Campagne/opname van programma</td> 
   <td>De marketinginteractie die het dichtst bij staat wanneer de Opp wordt gesloten (Won of Verloren)</td> 
  </tr>
  <tr>
   <td>Midden aanraken</td> 
   <td>Formuliervulling <strong>OF</strong> Campagne/opname van programma</td> 
   <td>Wanneer een contact een online vorm invult en het niet samenvalt met mijlpaal touchpoint</td> 
  </tr>
 </tbody>
</table>

[!DNL Marketo Measure] heeft deze twee sets aanraakpuntgegevens om een duidelijk inzicht te krijgen in de reis van een persoon en in de mogelijkheden. Deze twee Touchpoint-gegevenssets geven u een duidelijke kaart van wat er gebeurde van boven naar onder in de trechter.

In het volgende voorbeeld ziet u de gegevensstroom van de aanraakpunten voor kopers (BT&#39;s) naar de aanraakpunten voor koperkenmerken (BAT&#39;s). In dit voorbeeld maken Person A en Person B beide deel uit van dezelfde Opportunity die een Gemaakt Datum van 3.7.2020 en een Dichte Datum van 5.6.2020 heeft.

**Persoon A** Gegevensset aanraakpunt koper

* First Touch (FT) - Paid Search.AdWords - 9/1/2019
* Loodcreatie (LC) - Organic Search.Google - 11-20-2019
* Post LC (form fill) - Webinar - 3/4/2020

**Persoon B** Gegevensset aanraakpunt koper

* First Touch (FT) - Paid Social.Facebook - 26-8-2019
* Loodcreatie (LC) - Organic Search.Yahoo - 20-20-2020
* Post LC (form fill) - E-mail - 5/1/2020

**Kansen** Aanraakpuntgegevens voor koperkenmerk worden als volgt gelezen...

* First Touch (FT) - Paid Social.Facebook - 26-8-2019
   * (van **Persoon B** omdat ze de waarheid hebben _Eerste aanraking_ voor de account/Opp)
* Loodcreatie (LC) - Organic Search.Google - 11-20-2019
   * (van **Persoon A** omdat ze de waarheid hebben _Aanmaken van lead_ voor de account/Opp)
* Opportunity Creation (OC) - Webinar - 3-4-2020
   * (het aanraakpunt Post LC vanaf **Persoon A** zou _OC-aanraakpunt_ omdat het de meest recente interactie was die we hebben met de Opportunity die op 3-7-2020 werd gecreëerd)
* Gesloten won - E-mail - 15-2020
   * (het aanraakpunt Post LC vanaf **Persoon B** zou _Gesloten Won-aanraakpunt_ omdat het de meest recente interactie was die we op 6 juni 2020 moesten sluiten)
