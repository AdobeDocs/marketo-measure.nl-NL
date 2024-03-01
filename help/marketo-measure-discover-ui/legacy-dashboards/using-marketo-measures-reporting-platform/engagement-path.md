---
unique-page-id: 35586105
description: Pad voor betrokkenheid - [!DNL Marketo Measure]
title: Pad voor betrokkenheid
exl-id: 104d803f-9f40-4ab6-872d-6432f8c087e9
feature: Reporting
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '873'
ht-degree: 0%

---

# Pad voor betrokkenheid {#engagement-path}

Met het Betrokkenheidspad kunt u vanaf het eerste aanraken tot het sluiten een volledig beeld zien van de services voor lood, contact, account en opportuniteit.

![](assets/one-2.png)

## Tegelbeschrijving {#tile-description}

**Type gebeurtenis:** Het type aanraakpunt (Sessie, CRM-campagne, CRM-gebeurtenis, CRM-taak, depressie)

**Positie aanraakpunt koper:** Positie aanraakpunt van de lood/contactpersoon

**Aanraakpunt voor koperkenmerk:** Aanraakpunt positie van koperkenmerk van opportunity

**Aanraakpuntdatum:** Voor onlinebronnen: datum en tijd waarop de betrokkenheid plaatsvond. Voor offlinegebeurtenissen: datum en tijd ingesteld in de Salesforce-campagne. Voor activiteiten-aanraakpunt: wordt verwezen naar het aanraakpuntdatumveld in de activiteitenconfiguratie

**E-mail:** De e-mail die aan de service is gekoppeld

**Type marketingaanraking:** Type betrokkenheid (webbezoek, webformulier, webchat, CRM, typen activiteiten)

**Kanaal:** Marketingkanaal dat de basis vormde voor de overeenkomst

**Normaal:** Gemiddelde betrokkenheid

* Als de service afkomstig is van een aangesloten API-platform (Adwords/BingAds), wordt het CPC-medium
* Als de landingspagina van de service utm_medium bevat, parseren we
* Als de service afkomstig is van de CRM-campagne, komt het medium uit het veld Type van de CRM-campagne

**Webbron:** In deze kolom wordt de bron van de service weergegeven

* Als de service afkomstig is van een met API verbonden platform, geeft de webbron de naam van het advertentieplatform weer
* Als het aanraakpunt afkomstig is van een organische zoekopdracht, wordt in dit veld de naam van de zoekfunctie weergegeven
* Als #1 of #2 niet aanwezig is en de utm_source-waarde aanwezig is op de bestemmingspagina-URL voor het aanraakpunt, wordt die waarde hier weergegeven
* Als #1 of #2 niet en er geen utm_source-waarde aanwezig is, wordt het hoofddomein van de verwijzende URL hier weergegeven.
* Als geen van bovenstaande opties wordt weergegeven, wordt Web Direct of Web

**Eerste interactie met de persoon:** Deze kolom zal ja of Neen tonen als dat aanraakpunt de individuen eerste interactie was

**Toegewezen inkomsten:** In deze kolom worden de aan dat aanraakpunt toegewezen inkomsten weergegeven op basis van het geselecteerde toewijzingsmodel

## Filterbeschrijving {#filter-description}

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th>Filternaam</th> 
   <th>Beschrijving</th> 
  </tr> 
  <tr> 
   <td><p>Accountnaam/ID</p></td> 
   <td><p>Hiermee staat u meerdere waarden toe door filters toe te voegen via het plusteken (+) aan de rechterkant. Meerdere filterwaarden hebben een relatie "of", wat betekent dat er voor beide filterwaarden resultaten worden weergegeven. Als een van de filterwaarden niet geldig is, levert het dashboard geen resultaten op voor de ongeldige waarde, maar filtert het toch naar de geldige filterwaarden. Niet hoofdlettergevoelig.</p></td> 
  </tr> 
  <tr> 
   <td><p>Naam/id van opportunity</p></td> 
   <td><p>Hiermee staat u meerdere waarden toe door filters toe te voegen via het plusteken (+) aan de rechterkant. Meerdere filterwaarden hebben een relatie "of", wat betekent dat er voor beide filterwaarden resultaten worden weergegeven. Als een van de filterwaarden niet geldig is, levert het dashboard geen resultaten op voor de ongeldige waarde, maar filtert het toch naar de geldige filterwaarden. Niet hoofdlettergevoelig.</p></td> 
  </tr> 
  <tr> 
   <td><p>ID lead/email</p></td> 
   <td><p>Hiermee staat u meerdere waarden toe door filters toe te voegen via het plusteken (+) aan de rechterkant. Meerdere filterwaarden hebben een relatie "of", wat betekent dat er voor beide filterwaarden resultaten worden weergegeven. Als een van de filterwaarden niet geldig is, levert het dashboard geen resultaten op voor de ongeldige waarde, maar filtert het toch naar de geldige filterwaarden. Niet hoofdlettergevoelig.</p></td> 
  </tr> 
  <tr> 
   <td><p>Contactpersoon-id/e-mail</p></td> 
   <td><p>Hiermee staat u meerdere waarden toe door filters toe te voegen via het plusteken (+) aan de rechterkant. Meerdere filterwaarden hebben een relatie "of", wat betekent dat er voor beide filterwaarden resultaten worden weergegeven. Als een van de filterwaarden niet geldig is, levert het dashboard geen resultaten op voor de ongeldige waarde, maar filtert het toch naar de geldige filterwaarden. Niet hoofdlettergevoelig.</p><p>Accountnaam/id, lead-id/e-mail, contact-id/e-mailfilter zijn 'of'-relatie. Dit betekent dat als zowel het hoofdfilter als het contactfilter waarde hebben, alle records voor een van de id's worden weergegeven.</p></td> 
  </tr> 
  <tr> 
   <td><p>Attributiemodel</p></td> 
   <td><p>Geef aan op welk model de toegerekende opbrengsten moeten worden berekend. Toegestane waarden: "Full Path Attribution", "First Touch Attribution", "Custom Model Attribution", "Lead Creation Attribution", "U Shaped Attribution", "W Shaped Attribution".</p></td> 
  </tr> 
  <tr> 
   <td><p>Type gebeurtenis</p></td> 
   <td><p>De reis van de filter door type van gebeurtenis de gebruiker touchpoint is gebaseerd op. Hiermee staat u meerdere waarden toe door filters toe te voegen via het plusteken (+) aan de rechterkant. Toegestane waarden: "Session", "CRM-campagne", "CRM-gebeurtenis", "CRM-taak", "Impression".</p></td> 
  </tr> 
  <tr> 
   <td><p>Loodstadia</p></td> 
   <td><p>De reis van de filter door loodstadium de gebruiker touchpoint is gebaseerd op. Hiermee staat u meerdere waarden toe door filters toe te voegen via het plusteken (+) aan de rechterkant. De standaardinstelling voor filteren op 'is gelijk aan' geeft suggesties voor het kiezen van 'contains', maar raadt u aan 'contains' te gebruiken als filtercriteria voor meerdere filters in fasen.</p></td> 
  </tr> 
  <tr> 
   <td><p>Opportuniteitsfasen</p></td> 
   <td><p>De reis van de filter door opportuniteitsstadium het gebruiker aanraakpunt is gebaseerd op. Hiermee staat u meerdere waarden toe door filters toe te voegen via het plusteken (+) aan de rechterkant. De standaardinstelling voor filteren op 'is gelijk aan' geeft suggesties voor het kiezen van 'contains', maar raadt u aan 'contains' te gebruiken als filtercriteria voor meerdere filters in fasen.</p></td> 
  </tr> 
  <tr> 
   <td><p>Aanraakpuntdatum</p></td> 
   <td><p>De reis van de filter door aanraakpuntdatum/tijd.</p></td> 
  </tr> 
  <tr> 
   <td><p>E-mail met aanraakpunt van gebruiker</p></td> 
   <td><p>De reis van de filter door e-mail op gebruikersaanraakpunt. Hiermee kunt u e-mailberichten filteren die niet aan een lead/contact/account zijn gekoppeld.</p></td> 
  </tr> 
  <tr> 
   <td><p>Type marketingaanraking</p></td> 
   <td><p>De reis van de filter door het aanraaktype op te merken.</p></td> 
  </tr> 
  <tr> 
   <td><p>Kanaal</p></td> 
   <td><p>Filterreis per kanaal.</p></td> 
  </tr> 
  <tr> 
   <td><p>Normaal</p></td> 
   <td><p>Filtreer met medium.</p></td> 
  </tr> 
  <tr> 
   <td><p>Webbron</p></td> 
   <td><p>De reis van de filter door Webbron.</p></td> 
  </tr> 
  <tr> 
   <td><p>Eerste interactie met de persoon</p></td> 
   <td><p>Filter de reis door "Is First Touch"kolom op de lijst van gebruikersaanraakpunten.</p></td> 
  </tr> 
  <tr> 
   <td><p>Toegewezen inkomsten</p></td> 
   <td><p>De reis van de filter door toegeschreven opbrengstwaarde.</p></td> 
  </tr> 
 </tbody> 
</table>
