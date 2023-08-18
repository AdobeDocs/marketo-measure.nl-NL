---
description: ROI-dashboard - [!DNL Marketo Measure] - Product
title: ROI Dashboard
feature: Reporting
source-git-commit: 436e30c2a4138d780232d6ba9e64456d6277ac9b
workflow-type: tm+mt
source-wordcount: '663'
ht-degree: 0%

---

# ROI Dashboard {#roi-dashboard}

Het Dashboard van ROI voorziet marketers van een korrelige mening van rendementen op investering over kanalen, subkanalen, en campagnes. Het schort zorgvuldig kosten en opbrengstpatronen, terwijl ook het belichten van metriek zoals kosten-per-lood, overeenkomst, en kans, die een uitvoerig inzicht van marketing attributie verzekeren.

De antwoorden van de raad vragen:

* Wat waren de ROI waarden voor elk kanaal, subchannel, en campagne?
* Hoe verdeelden de kosten en de opbrengsten over elk kanaal, subchannel, en campagne?
* Wat waren de kosten per lead, de kosten per deal en de kosten per kans?

<table style="table-layout:auto"> 
<tbody>
 <tr> 
   <th>Component</th> 
   <th>Beschrijving</th>
   <th>Datumtype</th>
   <th>Velden doorlopen</th>
   <th>Filters</th>
  </tr>
  <tr>
    <td>Kostenverdeling</td>
    <td>Totale gemaakte kosten</td>
    <td>Kostendatum</td>
    <td><li>Campagne-id</li>
<li>Campagnenaam</li>
<li>Kanaal</li>
<li>Subkanaal</li>
<li>Datum</li>
<li>Draaien</li></td>
    <td rowspan="15"><li>Datum</li>
<li>Attributiemodel (instelling)</li>
<li>Kanaal</li>
<li>Subkanaal</li>
<li>Campagne</li></td>
  </tr>
  <tr>
    <td>Toegewezen inkomstentegel</td>
    <td>Totaal toegerekende inkomsten</td>
    <td>Gesloten datum</td>
    <td><li>Opportunity-id</li>
<li>Naam opportunity</li>
<li>Aanmaakdatum van opportunity</li>
<li>Datum van sluiting opportunity</li>
<li>Is gesloten (J/N)</li>
<li>Is gewonnen (Y/N)</li>
<li>Attributiemodel</li>
<li>Toegewezen inkomsten</li>
<li>Geregistreerde inkomsten</li></td>
  </tr>
  <tr>
    <td>Eenvoudige ROI-tegel</td>
    <td>Oudere ROI: inkomsten gedeeld door kosten in een bepaald tijdsbestek. 
    <li>Kosten: kosten in gefilterde datumperiode.</li>
    <li>Ontvangsten: inkomsten uit "Closed Won"-kansen in die periode.</li></td>
    <td>Gesloten datum</td>
    <td>NVT</td>
  </tr>
  <tr>
    <td>Realized ROI Tile</td>
    <td>Realized ROI: Vertegenwoordigt de tastbare resultaten van touchpoints die door campagnes binnen een gespecificeerd tijdkader worden geproduceerd.
    <li>Kosten: kosten in gefilterde datumperiode.</li>
    <li>Ontvangsten: gerealiseerde inkomsten uit alle "Closed Won"-transacties, met name die welke binnen de vastgestelde termijn door aanraakpunten worden beïnvloed.</li>
    <br/><img src="assets/roi-dashboard-1.png" width="600"></td>
    <td>Kostendatum</td>
    <td>NVT</td>
  </tr>
  <tr>
    <td>Totaal aantal nieuwe leadblokken</td>
    <td>Het totale aantal nieuwe leads (hele telling) dat binnen een opgegeven periode wordt gegenereerd, inclusief zowel aangeraakt als onaangeroerde leads.</td>
    <td>Aanmaakdatum</td>
    <td rowspan="2">
    <li>ID lead</li>
    <li>E-mailadres voor lead</li>
    <li>LC-datum</li></td>
  </tr>
  <tr>
    <td>Kosten per nieuwe leadtegel</td>
    <td>Totaal aantal nieuwe leads (totaal aantal) gedeeld door de kosten.</td>
    <td>Aanmaakdatum</td>
  </tr>
  <tr>
    <td>Totaal aantal nieuwe kansen</td>
    <td>Het totale aantal nieuwe kansen (hele telling) die binnen een gespecificeerde periode, met inbegrip van zowel aangeraakt als onaangeroerde lood worden geproduceerd.</td>
    <td>Aanmaakdatum</td>
    <td rowspan="2">
    <li>Opportunity-id</li>
    <li>Naam opportunity</li>
    <li>Aanmaakdatum van opportunity</li>
    <li>Datum van sluiting opportunity</li>
    <li>Is gesloten (J/N)</li>
    <li>Is gewonnen (Y/N)</li>
    <li>Huidig werkgebied</li></td>
  </tr>
  <tr>
    <td>Kosten per nieuwe opportunitytegel</td>
    <td>Totaal aantal nieuwe kansen (totaal aantal) gedeeld door kosten.</td>
    <td>Aanmaakdatum</td>
  </tr>
  <tr>
    <td>Totaal aantal overeenkomsten</td>
    <td>Het totale aantal transacties dat binnen een bepaalde periode wordt afgesloten, inclusief transacties zonder bijbehorende aanraakpunten.</td>
    <td>Gesloten datum</td>
    <td><li>Opportunity-id</li>
<li>Naam opportunity</li>
<li>Aanmaakdatum van opportunity</li>
<li>Datum van sluiting opportunity</li>
<li>Is gesloten (J/N)</li>
<li>Is gewonnen (Y/N)</li>
<li>Huidig werkgebied</li>
<li>Valuta</li>
<li>Attributiemodel</li>
<li>Toegewezen inkomsten</li>
<li>Geregistreerde inkomsten</li></td>
  </tr>
  <tr>
    <td>Kosten en opbrengsten per kanaalgrafiek</td>
    <td>Staafdiagram dat zowel de kosten als de inkomsten illustreert en dat is ontworpen om een vergelijkend perspectief op hun grootte te bieden ten opzichte van verschillende kanalen, subkanalen en campagnes.
    <br/><img src="assets/roi-dashboard-2.png" width="600"></td>
    <td>Gesloten datum</td>
    <td>Kosten:
<br/>
<li>Campagne-id</li>
<li>Campagnenaam</li>
<li>Kanaal</li>
<li>Subkanaal</li>
<li>Kostendatum</li>
<li>Valuta</li>
<li>Draaien</li>
<p>
Ontvangsten:
<br/>
<li>Opportunity-id</li>
<li>Naam opportunity</li>
<li>Aanmaakdatum van opportunity</li>
<li>Datum van sluiting opportunity</li>
<li>Is gesloten (J/N)</li>
<li>Is gewonnen (Y/N)</li>
<li>Toegewezen inkomsten</li>
<li>Attributiemodel</li>
<li>Toegewezen inkomsten</li>
<li>Geregistreerde inkomsten</li></td>
  </tr>
  <tr>
    <td>Geïsoleerd versus eenvoudig rendement van investeringen in de loop der tijd</td>
    <td>De lijngrafiek van de tijdreeks die de vergelijking tussen Geregistreerde en Eenvoudige ROI toont, die hun vooruitgang in tijd volgen.
    <br/><img src="assets/roi-dashboard-3.png" width="600"></td>
    <td>Eenvoudig rendement: Kostendatum en einddatum
    <p>Rendement van gerealiseerde investeringen: Kostprijs op datum en aanraakpunt</td>
    <td>NVT</td>
  </tr>
  <tr>
    <td>Kosten in de loop van de tijd Grafiek</td>
    <td>Gestapelde staafgrafiek met de totale kosten op kwartaal- en maandbasis, uitgesplitst naar afzonderlijke kanalen voor een gedetailleerde uitsplitsing.
    <br/><img src="assets/roi-dashboard-4.png" width="600"></td>
    <td>Kostendatum</td>
    <td rowspan="2"><li>Campagne-id</li>
<li>Campagnenaam</li>
<li>Kanaal</li>
<li>Subkanaal</li>
<li>Kostendatum</li>
<li>Valuta</li>
<li>Draaien</li></td>
  </tr>
  <tr>
    <td>Kosten per kanaalgrafiek</td>
    <td>Staafdiagram waarin marketinguitgaven worden weergegeven, gesegmenteerd door kanalen.
    <br/><img src="assets/roi-dashboard-5.png" width="600"></td>
    <td>Kostendatum</td>
  </tr>
  <tr>
    <td>Overzichtstabel ROI</td>
    <td>Tabel met de toegerekende inkomsten, kosten en investeringsrendement, opgesplitst naar afzonderlijke kanalen voor een gedetailleerde uitsplitsing.
<p>
<b>Kolommen:</b>
<p>
<li>Kanaal/Subkanaal/Campagne</li>
<li>Kosten</li>
<li>Toegewezen inkomsten</li>
<li>Eenvoudig rendement</li>
<li>Realized ROI</li>
<li>Ongerealiseerde pijplijn</li>
<ul style="padding-left: 30px;"><li>Pijpleiding van aanraakpunten (open kansen) verbonden aan campagnes binnen een bepaald tijdsbestek</li></ul></td>
    <td>Eenvoudig rendement: Kostendatum en einddatum
    <p>Rendement van gerealiseerde investeringen: Kostprijs op datum en aanraakpunt</td>
    <td>NVT</td>
  </tr>
  <tr>
    <td>Tabel met marketinguitgaven</td>
    <td>De lijst die kosten, nieuwe lood, kansen, en overeenkomsten toont gesloten die door individuele kanalen voor een gedetailleerde uitsplitsing worden gesegmenteerd.
<p>
<b>Kolommen:</b>
<p>
<li>Kanaal/Subkanaal/Campagne</li>
<li>Kosten</li>
<li>Nieuwe leads</li>
<li>Kosten per nieuwe lead</li>
<li>Nieuwe mogelijkheden</li>
<li>Kosten per Nieuwe Kans</li>
<li>Overeenkomsten gesloten</li>
<li>Kosten per Gesloten Overeenkomst</li></td>
    <td><li>Kosten: datum kosten</li>
<li>Nieuwe leads: Aanmaakdatum</li>
<li>Nieuwe kansen: aanmaakdatum</li>
<li>Overeenkomsten gesloten: gesloten datum</li></td>
    <td>NVT</td>
  </tr>
</tbody>
</table>

>[!MORELIKETHIS]
>
>[Basisprincipes van dashboard ontdekken](/help/marketo-measure-discover-ui/dashboards/discover-dashboard-basics.md){target="_blank"}
