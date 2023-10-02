---
description: Opmerkingen bij de huidige release - [!DNL Marketo Measure] - Productdocumentatie
title: Opmerkingen bij de huidige release
exl-id: 64b8fce8-af7d-4991-b01e-3fcf375d14e7
feature: Release Notes
source-git-commit: 22f8cedf401a28444026d7b63384ce3cbabe0305
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 0%

---

# Opmerkingen bij de release: 2023 {#release-notes-2023}

Hieronder vindt u alle nieuwe en bijgewerkte functies voor onze 2023-releases.

## Versie Q4 {#q4-release}

<p>

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
>Hoewel de huidige dashboards tegen medio Januari 2024 zullen worden verouderd, kunt u beide versies tot dan gebruiken, die een vlotte overgang verzekeren.

### Afwijkingen {#deprecations}

<p>

* **Veld &quot;custom_properties&quot;**

In ons gegevenspakhuis, heeft het gebied &quot;custom_properties&quot;dienst als opslag voor extra gegevenspunten die niet door ons vaste schema worden behandeld. Opgeslagen in JSON-indeling is het gebruik van dit veld beperkt en kan de integratie ervan met SQL-query&#39;s ingewikkeld zijn, wat van invloed is op de prestaties. Gezien deze factoren hebben we besloten dit veld af te schaffen. Deze verandering zal hoofdzakelijk de gegevensverwerkingslaag binnen onze Azure lijstopslag en de gegevens beïnvloeden die naar ons gegevenspakhuis worden uitgevoerd.

* **Dynamisch pakket gerelateerd**

   * Installeer onze nieuwste pakketversie, v6.12, om verbinding te blijven maken met Dynamics. Oude versies `(<v6.12)` wordt niet meer ondersteund. Deze update optimaliseert het maken van historische records om opslaggebruik te beperken.

   * De verouderde methode van OAuth met een RefreshToken zal worden afgekeurd. Zie [deze handleiding](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/oauth-with-azure-active-directory-for-dynamics-crm.md){target="_blank"} voor het bijwerken van uw geloofsbrieven om aan Microsoft toe te passen beste praktijken van het gebruiken van ClientSecret.

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
