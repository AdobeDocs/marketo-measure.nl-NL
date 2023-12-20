---
description: Overzicht van integratierechten - [!DNL Marketo Measure] - Productdocumentatie
title: Overzicht van integratierechten
hide: true
hidefromtoc: true
feature: APIs, Integration
source-git-commit: 9196877384140d60a22012b43ea960017528f4d5
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 0%

---

# Overzicht van integratierechten {#integration-permissions-overview}

In deze handleiding worden de benodigde machtigingen beschreven voor naadloze integratie met Marketo Measure, zodat elke integratie effectief en probleemloos werkt.

<table>
<thead>
  <tr>
    <th style="width:10%">Integratie</th>
    <th style="width:20%">Gegevenstype
    <li>Interactiegegevens web</li>
    <li>B2B-systeemgegevens</li>
    <li>Platformgegevens toevoegen</li></th>
    <th style="width:30%">Wat we bijhouden</th>
    <th style="width:40%">Machtigingsvereisten</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Salesforce</td>
    <td>B2B-systeemgegevens    
</td>
    <td>Marketo Measure volgt:
    <br>
    <li>Account</li>
<li>Campagne</li>
<li>CampaignMember</li>
<li>Contact</li>
<li>CurrencyConversionRange</li>
<li>CurrencyStatus</li>
<li>Gebeurtenissen</li>
<li>FieldHistory (lead, contact en opportunity)</li>
<li>Lood</li>
<li>Opportunity</li>
<li>OpportunityContactRole</li>
<li>OpportunityHistory</li>
<li>Taken</li>
<br>
Aanraakpunten en andere gegevens worden in aangepaste, bizible velden geschreven op account, campagne, CampaignMember, case, contact, lead en opportunity.</td>
    <td><b>Machtigingen voor met Salesforce verbonden gebruikers (vereist)</b>
    <br>
    <b>Marketo Measure Administrator Permission Set voor specifieke gebruiker:</b> SFDC-beheerder toestaan om CRUD-bewerkingen uit te voeren op marketing om objecten te meten.
    <br>
    <b>Reeks met geconverteerde leads weergeven en bewerken:</b> Op deze manier kan Marketo Measure leads versieren nadat ze zijn omgezet in contactpersonen.
    <br>
    <b>Selectievakje voor Salesforce-marketinggebruiker:</b> Met het selectievakje Gebruiker voor marketing kunnen gebruikers campagnes maken en de wizard Campagne importeren gebruiken.
    <br>
    <b>Marketo Measure Standard-gebruiker:</b> Hiermee kan een gebruiker records lezen van Marketo Measure-objecten.
    <p>
    <b>Salesforce Standard-veldmachtigingen</b>
    <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Standaardobjecten Salesforce en toegang</a>
    <p>
    <b>Aangepaste bevoegdheden Salesforce-veld</b>
    <br>
    Wij verstrekken eigenschapmontages om de gebieden van de douaneverkoop te houden die de klanten kunnen gebruiken. Als deze eigenschapmontages dan worden bepaald hebben wij LEZEN toegang tot elk van de verkoopkrachtgebieden nodig die in het eigenschapplaatsen worden bewaard (b.v., als de het plaatsen waarde van CustomLeadSourceField aan "LeadSource__c"gelijk is dan vereisen wij LEZEN toegang tot dit gebied).
    </td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
</tbody>
</table>
