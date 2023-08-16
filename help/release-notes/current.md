---
description: Opmerkingen bij de huidige release - [!DNL Marketo Measure] - Productdocumentatie
title: Opmerkingen bij de huidige release
exl-id: 64b8fce8-af7d-4991-b01e-3fcf375d14e7
feature: Release Notes
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# Opmerkingen bij de release: 2023 {#release-notes-2023}

Hieronder vindt u alle nieuwe en bijgewerkte functies voor onze 2023-releases.

## V2-release {#q2-release}

<p>

**Salesforce-pakketconsolidatie**

* We voegen alle Salesforce-pakketten samen tot één uitgebreid pakket voor een verbeterde gebruikerservaring en vereenvoudigd gebruik. De pakketten V1, V2_EXT, en van de Rapportering zullen volgend kwartaal worden gepensioneerd. Het nieuwe pakket combineert alle vorige functies, waardoor klanten efficiënter kunnen volgen en meer inzicht krijgen in de situatie.
* Klanten die het V2-pakket al hebben geïnstalleerd, moeten dit bijwerken naar de nieuwe geconsolideerde versie.
* We hebben twee nieuwe velden toegevoegd om uw rapportagemogelijkheden te verbeteren:
   * form_name: Nu beschikbaar in BT/BAT-objecten, kunnen gebruikers in dit veld rapporten maken op basis van formuliernamen.
   * user_touchpoint_id: Met dit veld kunnen gebruikers rapporten maken met unieke aantallen gebruikers-aanraakpunten.
* [Dit artikel](/help/configuration-and-setup/marketo-measure-and-salesforce/salesforce-package-consolidation.md){target="_blank"} omvat gidsen op het ontspannen van rapporten en dashboards van de erfenisRapporterende pakketten.

**Versie-updates van de Salesforce-API**

* Alle versies van de Salesforce-API van Apex-klassen, inclusief de klasse UserActivityContext, worden bijgewerkt naar ondersteunde versies. (31,0 tot en met 57,0)

**Nieuwe pakketinstallatie**

* De nieuwe geconsolideerde link van de pakketinstallatie [hier te vinden](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t1P000000VY6Z){target="_blank"}

### Wat komt er? {#whats-coming}

<p>

**Wijzigingen in IP-adresopslag**

* IP-adressen worden niet meer in ons systeem opgeslagen op basis van privacyoverwegingen. We zullen de geolocatie van het IP-adres blijven identificeren en opslaan, maar de notatie wordt gewijzigd (bijvoorbeeld &quot;Verenigde Staten&quot; in &quot;VS&quot;).
