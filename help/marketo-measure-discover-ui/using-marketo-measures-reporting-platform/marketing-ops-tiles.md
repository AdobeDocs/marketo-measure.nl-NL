---
unique-page-id: 34406495
description: OPS-blokken voor marketing - [!DNL Marketo Measure] - Productdocumentatie
title: OPS-blokken marketing
exl-id: e7978a79-6f6e-4bfd-9962-b35b7d46a9ac
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 0%

---

# OPS-blokken marketing {#marketing-ops-tiles}

Met marketingtips kunt u valideren en diagnostiseren [!DNL Marketo Measure] gegevens met volledige zichtbaarheid in afzonderlijke aanraakpunten per lead, contactpersoon, account, campagne en opportunity.

<table> 
 <colgroup> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
  <col> 
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
   <td><br></td> 
   <td><p><strong>Account-id</strong></p></td> 
   <td><p><strong>Accountnaam</strong></p></td> 
   <td><p><strong>Opp-id</strong></p></td> 
   <td><p><strong>Opp-naam</strong></p></td> 
   <td><p><strong>Lead of contactpersoon-id</strong></p></td> 
   <td><p><strong>E-mailadres voor lead of contact</strong></p></td> 
   <td><p><strong>Campagne-id</strong></p></td> 
   <td><p><strong>Opp Won</strong></p></td> 
   <td><p><strong>Aanmaakdatum opp</strong></p></td> 
   <td><p><strong>Datum Sluiten</strong></p></td> 
   <td><p><strong>Aanraakpuntdatum</strong></p></td> 
   <td><p><strong>Attributiemodel</strong></p></td> 
  </tr> 
  <tr> 
   <td><p><strong>Accounts</strong></p></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><br></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
  </tr> 
  <tr> 
   <td><p><strong>Opportunity</strong></p></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><br></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
  </tr> 
  <tr> 
   <td><p><strong>Contactpersonen</strong></p></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
  </tr> 
  <tr> 
   <td><p><strong>Leads</strong></p></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X*</strong></td> 
   <td><strong>X*</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X*</strong></td> 
   <td><strong>X*</strong></td> 
   <td><strong>X*</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
  </tr> 
  <tr> 
   <td><p><strong>Campagnes</strong></p></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><br></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
   <td><strong>X</strong></td> 
  </tr> 
 </tbody> 
</table>

## Accounttegel {#account-tile}

![](assets/one-1.png)

Hier worden de volgende gegevens weergegeven met betrekking tot de opgegeven account(s).

**Accounts moeten aanraakpuntgegevens hebben (alleen van toepassing als ABM is ingeschakeld)**

-Account-ID: Account ID in CRM

-Accountnaam: Rekeningnaam in CRM

-Aanmaakdatum: Aanmaakdatum van de rekening in de CRM

* Drill-down: Zie Aanmaakdatum per uur, minuut, tijd

-Website: Waarde gevonden in het veld Website op de account

-Betrokkenheidsscore: Predictive Engagement Score (PES), gevuld door [!DNL Marketo Measure]^1

-Opportuniteiten: Aantal Kansen verbonden met de rekening

* Drill-down: Zie details voor de bijbehorende Opportunity(s)

-Contacten: Aantal contactpersonen op deze account

* Drill-down: Zie details voor de bijbehorende contacten

-Leads: Aantal leads dat aan dit account is toegewezen via lead in accounttoewijzing^1

* Drill-down: Zie details voor de leads die aan de account zijn toegewezen

-Attributie-aanraakpunten: Aantal aanraakpunten voor koperkenmerken voor de account

* Drill-down: Zie Aanraakpuntgegevens voor koperkenmerken (ID, e-mail, aanraakpuntdatum, accountnaam, campagne, kanaal, subkanaal, type marketingaanraking, kenmerkmodel)

-Aanraakpunten: Aantal aanraakpunten dat de contactpersonen op dit account hebben^2

* Drill-down: Zie Aanraakpunten op de aanraakpuntgegevens van de account (ID, E-mail, Aanraakpuntdatum, Accountnaam, Campagne, Kanaal, Subkanaal, Type marketingaanraking)

>[!NOTE]
>
>Als u ABM hebt, worden de aanraakpunten weergegeven die gerelateerd zijn aan de leads die zijn toegewezen via Toewijzing van lead to-account.

## Opportunity-tegel {#opportunity-tile}

![](assets/two-1.png)

Geeft de volgende gegevens weer met betrekking tot de opgegeven opportunity(en).

-Opportunity-id: Opportunity-id in CRM

-Naam opportunity: Naam van opportunity in CRM

-Accountnaam: Accountnaam gekoppeld aan de opportuniteit

-Aanmaakdatum: Aanmaakdatum van de opportuniteit in de CRM

Drill-down: Zie Aanmaakdatum per uur, minuut, tijd

-Close Date: Gesloten datum van de opportuniteit in de CRM

Drill-down: Zie Datum sluiten op Uur, Minuut, Tijd

-Hoeveelheid: Het totale bedrag van de opportuniteit

-Contacten: Aantal Contacten verbonden aan de Kans

Drill-down: Zie details voor de bijbehorende contacten

-Attributie-aanraakpunten: Aantal verwante aanraakpunten voor koperkenmerken

Drill-down: Zie Aanraakpuntgegevens voor koperkenmerken (ID, e-mail, aanraakpuntdatum, accountnaam, campagne, kanaal, subkanaal, type marketingaanraking, kenmerkmodel)

## Contactegel {#contacts-tile}

![](assets/three-1.png)

Hier worden de volgende gegevens weergegeven met betrekking tot de opgegeven contactpersoon of contactpersonen.

-Contactpersoon-id: Contactpersoon-id in CRM

-E-mail: E-mailadres contactpersoon

-Aanmaakdatum: Aanmaakdatum van de contactpersoon bij de CRM

* Drill-down: Zie Aanmaakdatum per uur, minuut, tijd

-Accountnaam: Accountnaam gekoppeld aan de contactpersoon

-Attributie-aanraakpunten: Aantal aanraakpunten koper voor de contactpersoon

* Drill-down: Zie Aanraakpuntgegevens voor koperkenmerken (ID, e-mail, aanraakpuntdatum, accountnaam, campagne, kanaal, subkanaal, type marketingaanraking, kenmerkmodel)

-Aanraakpunten: Aantal aanraakpunten koper voor de contactpersoon

* Drill-down: Zie Contacten op de gegevens van het aanraakpunt van de account (ID, E-mail, Aanraakpunt Datum, Accountnaam, Campagne, Kanaal, Subkanaal, Type marketingaanraking)

## Leadblok {#leads-tile}

![](assets/four-1.png)

Hiermee geeft u de volgende gegevens weer met betrekking tot de opgegeven lead(s).

-ID lead: ID lead in CRM

-E-mail: E-mailadres voor lead-record

-Aanmaakdatum: Toen de lead werd gecreëerd in de CRM

* Drill-down: Zie Aanmaakdatum per uur, minuut, tijd

-Bedrijf (uit Lead): Het bedrijf dat op het verslag in CRM vermeld is bevolkt door klant

-Accountnaam: De accountnaam [!DNL Marketo Measure] wordt gevuld op basis van onze toewijzing van leads voor account

-Aanraakpunten: Het aantal aanraakpunten dat is gekoppeld aan de lead(s)

* Drill-down: Zie Contacten op de gegevens van het aanraakpunt van de account (ID, E-mail, Aanraakpunt Datum, Accountnaam, Campagne, Kanaal, Subkanaal, Type marketingaanraking)

## Campagne Tile {#campaigns-tile}

![](assets/five-1.png)

Hiermee geeft u de volgende gegevens weer met betrekking tot de opgegeven campagne(s).

-Campagne-id: Campagne-id in CRM

-Campagnenaam: Campagnenaam in CRM

-Campagne-uitgaven: De uitgaven [!DNL Marketo Measure] heeft opgenomen met betrekking tot de campagne

-Attributiemodel: Hiermee wordt de juiste toewijzing weergegeven op basis van het geselecteerde model

-Attributie-aanraakpunten: Het aantal aanraakpunten voor koperkenmerken dat aan de campagne (en) is gekoppeld

* Drill-down: Zie Aanraakpuntgegevens voor koperkenmerken (ID, e-mail, aanraakpuntdatum, accountnaam, campagne, kanaal, subkanaal, type marketingaanraking, kenmerkmodel)

-Aanraakpunten: Het aantal aanraakpunten dat is gekoppeld aan de campagne(s)

* Drill-down: Zie Contacten op de gegevens van het aanraakpunt van de account (ID, E-mail, Aanraakpunt Datum, Accountnaam, Campagne, Kanaal, Subkanaal, Type marketingaanraking)
