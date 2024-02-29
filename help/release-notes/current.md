---
description: Opmerkingen bij de huidige release - [!DNL Marketo Measure]
title: Opmerkingen bij de huidige release
exl-id: e93ff03e-ea21-41f4-abb8-32313ee74c0c
feature: Release Notes
source-git-commit: 289c40a07c60ccc0262e2aaf95f21fca0c945b11
workflow-type: tm+mt
source-wordcount: '1041'
ht-degree: 0%

---

# Opmerkingen bij de release: 2023 {#release-notes-2023}

Hieronder vindt u alle nieuwe en bijgewerkte functies voor onze 2023-releases.

## Versie Q4 {#q4-release}

<p>

**Webverkeersdashboard**

Het nieuwe ontwerp [Webverkeersdashboard](/help/marketo-measure-discover-ui/dashboards/web-traffic-dashboard.md){target="_blank"} is nu toegankelijk voor alle klanten. Dit dashboard biedt een volledig overzicht van de interactie van de bezoeker van uw website. U kunt metingen analyseren, zoals het aantal unieke bezoekers per URL, algemene bezoeken, paginaweergaven en formulierverzendingen van specifieke formulier-URL&#39;s of landingspagina&#39;s. U kunt ook de maandelijkse verkeerstendensen volgen en high-performance betaalde media identificeren, die u zullen helpen uw strategieën voor optimale opbrengstgeneratie verfijnen.

De nieuwe set van vooraf gebouwde dashboards zal naar verwachting in golven worden geïntroduceerd, die voor het eind van het jaar zullen aflopen.

>[!NOTE]
>
>Terwijl de huidige dashboards tegen Maart 2024 zullen worden verouderd, kunt u beide versies tot dan gebruiken, die een vlotte overgang verzekeren.

**IP-adresgegevens verwijderen**

Wij verwijderen IP adresgegevens uit onze opslag op lange termijn om naleving van de gegevensprivacy te verzekeren. Momenteel, bevatten de volgende lijsten en de meningen van de Snowflake IP adressen, en wij zijn van plan om deze gegevens te verwijderen en nieuwe geolocatieinformatie toe te voegen:

<table style="width:400px">
<thead>
  <tr>
    <th style="width:50%">Tabellen</th>
    <th>Weergaven</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>CUSTOMER_AB_TESTS</td>
    <td>BIZ_CUSTOMER_AB_TESTS</td>
  </tr>
  <tr>
    <td>CUSTOMER_EVENTS</td>
    <td>BIZ_CUSTOMER_EVENTS</td>
  </tr>
  <tr>
    <td>FORM_SUBMITS</td>
    <td>BIZ_FORM_SUBMITS</td>
  </tr>
  <tr>
    <td>IMPRESSIES</td>
    <td>BIZ_IMPRESSIONS</td>
  </tr>
  <tr>
    <td>PAGE_VIEWS</td>
    <td>BIZ_PAGE_VIEWS</td>
  </tr>
  <tr>
    <td>SESSIES</td>
    <td>BIZ_SESSIONS</td>
  </tr>
  <tr>
    <td>WEB_HOST_MAPPINGS</td>
    <td>BIZ_WEB_HOST_MAPPINGS</td>
  </tr>
</tbody>
</table>

* Vanaf nu downloaden we landcode, plaatsnaam en regiocode in plaats van de landnaam, plaatsnaam en gebiedsnaam.
* Tijdens de verwerking van alle historische webactiviteiten kunnen zich inconsistenties in locatiegegevens tussen records voordoen. Deze inconsistenties kunnen de aanwezigheid van IP-adressen zonder geolocatiegegevens, bijgewerkte geolocatiegegevens zonder IP-adressen of een combinatie van land- of regionamen en codes omvatten.
* _**Deze periode van gemengde gegevens zal naar verwachting plaatsvinden van 01/04/2023 tot en met 02/29/2023.**_

**Gegevens paginatitel in URL-tabel**

De URL-tabel in het dialoogvenster [data-entrepot](/help/marketo-measure-data-warehouse/data-warehouse-schema.md){target="_blank"} bevat nu naast webgegevenstabellen ook een veld voor de paginatitel.

De paginatitel in de URL-tabel komt mogelijk niet altijd overeen met de paginatitel in andere webtabellen. De URL-tabel krijgt de titel van de meest recente pagina. Als de titel voor de URL is gewijzigd nadat de webactiviteit heeft plaatsgevonden, komt deze niet overeen met de titel in de URL-tabel.

**Opnieuw ontwerpen van dashboard detecteren**

Alle Marketo Measure-gebruikers zullen onze opnieuw ontworpen dashboards in de app ervaren die verbeterde bruikbaarheid combineren met toegevoegde waarde. We introduceren ook nieuwe maatstaven, zoals &#39;Realized ROI&#39;, die rekening houden met de typische vertraging tussen marketinginvesteringen en aankopen in B2B-modellen.

De nieuwe set van vooraf gebouwde dashboards zal naar verwachting in golven worden geïntroduceerd, vanaf de eerste week van oktober tot het einde van het jaar. Deze nieuwe dashboards zullen automatisch in uw instanties, samen met in-productinformatie en verbindingen aan documentatie verschijnen.

* [Nieuwe Discover-dashboardgids](/help/marketo-measure-discover-ui/dashboards/new-discover-dashboard-guide.md){target="_blank"}
* [Basisprincipes van dashboard ontdekken](/help/marketo-measure-discover-ui/dashboards/discover-dashboard-basics.md){target="_blank"}
* [Dashboard overzicht van inkomsten](/help/marketo-measure-discover-ui/dashboards/revenue-overview-dashboard.md){target="_blank"}
* [Toegewezen belastingdashboard](/help/marketo-measure-discover-ui/dashboards/attributed-revenue-dashboard.md){target="_blank"}
* [ROI Dashboard](/help/marketo-measure-discover-ui/dashboards/roi-dashboard.md){target="_blank"}
* [Paspoort-dashboard](/help/marketo-measure-discover-ui/dashboards/passport-dashboard.md){target="_blank"}

>[!NOTE]
>
>Terwijl de huidige dashboards tegen Maart 2024 zullen worden verouderd, kunt u beide versies tot dan gebruiken, die een vlotte overgang verzekeren.

### Afwijkingen {#deprecations}

<p>

#### Salesforce-veldvervorming

We zullen onze exporttaken geleidelijk afschaffen naar objecten Lead/Contact om onze integratie te vereenvoudigen en de noodzaak om te exporteren naar standaardobjecten van Salesforce te elimineren. De hieronder vermelde gedenormaliseerde velden worden ook afgekeurd, omdat klanten dezelfde gegevens kunnen verkrijgen van hun Touchpoint-objecten. _**De tijdslijn van afschrijving is juni 2024.**_

<table style="width:350px">
<tbody>
  <tr>
    <td>bizible2_Ad_Campaign_Name_FT__c</td>
  </tr>
  <tr>
    <td>bizible2_ad_Campaign_Name_LC_c</td>
  </tr>
  <tr>
    <td>bizible2_Landing_Page_FT__c</td>
  </tr>
  <tr>
    <td>bizible2_Landing_Page_LC__c</td>
  </tr>
  <tr>
    <td>bizible2__Touchpoint_Date_FT__c</td>
  </tr>
  <tr>
    <td>bizible2_Touchpoint_Date_LC__c</td>
  </tr>
  <tr>
    <td>bizible2__Touchpoint_Source_FT__c</td>
  </tr>
  <tr>
    <td>bizible2__Touchpoint_Source_LC__c</td>
  </tr>
  <tr>
    <td>bizible2_Marketing_Channel_FT__c</td>
  </tr>
  <tr>
    <td>bizible2_Marketing_Channel_LC__c</td>
  </tr>
</tbody>
</table>

De velden die dezelfde informatie bevatten over de Touchpoint- en Attribution Touchpoint-objecten zijn:

* bizible2_ad_Campaign_Name__c
* bizible2_Landing_Page__c
* bizible2_Marketing_Channel__c
* bizible2_Touchpoint_Date__c
* bizible2__Touchpoint_Source__c

**Vereiste handelingen**

* Maak nieuwe rapporttypen voor leads en contactpersonen met of zonder aanraakpunten.

![](assets/release-notes-2023-1.png)

* Creeer rapporten die de functionaliteit van om het even welk bestaand rapport vangen dat de verwijderde gebieden gebruikt. Als onderdeel van dit proces wilt u de velden in het rapport wijzigen, zoals hieronder is aangegeven:

* Verwijder de velden Lood/Contact FT/LC:

![](assets/release-notes-2023-2.png)

* Velden voor aanraakpunten toevoegen:

![](assets/release-notes-2023-3.png)

* Het aanraakpuntpositiefilter en alle filters die gebruikmaken van de FT/LC-velden, inclusief het datumveld, moeten als volgt worden bijgewerkt:

![](assets/release-notes-2023-4.png)

![](assets/release-notes-2023-5.png)

* Verwijder eventuele bestaande rapporten waarin de verwijderde velden uit het object Lead/Contact zijn gebruikt om niet langer naar deze velden te verwijzen.

<p>

#### Dynamisch pakket gerelateerd

* Installeer onze nieuwste pakketversie, v6.12, om verbinding te blijven maken met Dynamics. Oude versies `(<v6.12)` wordt niet meer ondersteund. Deze update optimaliseert het maken van historische records om opslaggebruik te beperken.

* De verouderde methode van OAuth met een RefreshToken zal worden afgekeurd. Zie [deze handleiding](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/oauth-with-azure-active-directory-for-dynamics-crm.md){target="_blank"} voor het bijwerken van uw geloofsbrieven om aan Microsoft toe te passen beste praktijken van het gebruiken van ClientSecret.

#### Veld &quot;custom_properties&quot;

In ons gegevenspakhuis, heeft het gebied &quot;custom_properties&quot;dienst als opslag voor extra gegevenspunten die niet door ons vaste schema worden behandeld. Opgeslagen in JSON-indeling is het gebruik van dit veld beperkt en kan de integratie ervan met SQL-query&#39;s ingewikkeld zijn, wat van invloed is op de prestaties. Gezien deze factoren hebben we besloten dit veld af te schaffen. Deze verandering zal hoofdzakelijk de gegevensverwerkingslaag binnen onze Azure lijstopslag en de gegevens beïnvloeden die naar ons gegevenspakhuis worden uitgevoerd.

### Wat komt er? {#q4-whats-coming}

<p>

**Aangepaste rapportage in de app**

Marketo Measure-klanten kunnen voor het eerst hun eigen rapporten rechtstreeks in de app maken en opslaan. Dit zal volgen op de release van de vooraf gebouwde dashboards begin 2024.

<br>

## V2-release {#q2-release}

<p>

* **Salesforce-pakketconsolidatie**

We voegen alle Salesforce-pakketten samen tot één uitgebreid pakket voor een verbeterde gebruikerservaring en vereenvoudigd gebruik. De pakketten V1, V2_EXT, en van de Rapportering zullen volgend kwartaal worden gepensioneerd. Het nieuwe pakket combineert alle vorige functies, waardoor klanten efficiënter kunnen volgen en meer inzicht krijgen in de situatie.

Klanten die het V2-pakket al hebben geïnstalleerd, moeten dit bijwerken naar de nieuwe geconsolideerde versie.

We hebben twee nieuwe velden toegevoegd om uw rapportagemogelijkheden te verbeteren:

* form_name: Nu beschikbaar in BT/BAT-objecten, kunnen gebruikers in dit veld rapporten maken op basis van formuliernamen.
* user_touchpoint_id: Met dit veld kunnen gebruikers rapporten maken met unieke aantallen gebruikers-aanraakpunten.

[Dit artikel](/help/configuration-and-setup/marketo-measure-and-salesforce/salesforce-package-consolidation.md){target="_blank"} omvat gidsen op het ontspannen van rapporten en dashboards van de erfenisRapporterende pakketten.

* **Versie-updates van de Salesforce-API**

Alle versies van de Salesforce-API van Apex-klassen, inclusief de klasse UserActivityContext, worden bijgewerkt naar ondersteunde versies. (31,0 tot en met 57,0)

* **Nieuwe pakketinstallatie**

De nieuwe geconsolideerde link van de pakketinstallatie [hier te vinden](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t1P000000VY6Z){target="_blank"}

### Wat komt er? {#q2-whats-coming}

<p>

**Wijzigingen in IP-adresopslag**

IP-adressen worden niet meer in ons systeem opgeslagen op basis van privacyoverwegingen. We zullen de geolocatie van het IP-adres blijven identificeren en opslaan, maar de notatie wordt gewijzigd (bijvoorbeeld &quot;Verenigde Staten&quot; in &quot;VS&quot;).
