---
unique-page-id: 18874694
description: Salesforce Sandbox naar productie-migratie - [!DNL Marketo Measure] - Productdocumentatie
title: Salesforce Sandbox naar productie-migratie
exl-id: b2b71c4a-f192-43ce-a27e-cbd0ec3cf008
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 0%

---

# Salesforce Sandbox naar productie-migratie {#salesforce-sandbox-to-production-migration}

Als u ervoor kiest om te testen [!DNL Marketo Measure] in een [!DNL Salesforce] De zandbakomgeving, volg deze instructies om naar Productie te migreren zodra u klaar bent. In de volgende instructies wordt ervan uitgegaan dat u de [!DNL Marketo Measure] in uw Sandbox-org, heeft de vereiste test uitgevoerd en is klaar om te drukken [!DNL Marketo Measure] naar Productie.

## Stap 1: Installeren [!DNL Marketo Measure] Pakketten in uw productie [!DNL Salesforce] Instance {#install-marketo-measure-packages-into-your-production-salesforce-instance}

* De twee apparaten installeren [!DNL Marketo Measure] verpakt in Production met de &quot;[!UICONTROL All Users]&quot; instellen

   * [Basispakket](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N3000000B3KLuEAN){target="_blank"}
   * [Dashboard Extension Package](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t610000001jI6){target="_blank"}

* Voor meer informatie over de [!DNL Marketo Measure] relatie met [!DNL Salesforce], bekijk [dit artikel](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md)
* Een beetje [!DNL Salesforce] configuratie is noodzakelijk. De specifieke actiepunten worden hieronder beschreven in [Stap 4 hieronder](#salesforce-configuration)

## Stap 2: Huidige CRM-verbinding met sandbox verwijderen in [!DNL Marketo Measure] App {#delete-the-current-sandbox-crm-connection-in-marketo-measure-app}

* Aanmelden bij de [!DNL Marketo Measure] toepassing op experience.adobe.com/marketo-measure
* Ga naar Mijn account >[!UICONTROL Settings] >[!UICONTROL Connections]
* Klik op het prullenbakpictogram naast de SFDC-verbinding om deze te verwijderen
* U wordt gevraagd uw verwijdering te bevestigen. Zorg ervoor dat u de vraag zorgvuldig leest en begrijp de gevolgen van het verwijderen

   ![](assets/salesforce-sandbox-to-production-migration-1.png)

   * Typ de naam van het bedrijf zoals gevraagd in het bevestigingsmodel en klik op &quot;Ik begrijp de gevolgen, verwijder deze verbinding&quot;
* Dit zal het schrappingsproces teweegbrengen en zal wat tijd vergen be??indigen

## Stap 3: Verbind de Instantie van CRM van de Productie in [!DNL Marketo Measure] App {#connect-the-production-crm-instance-in-marketo-measure-app}

* Aanmelden bij de [!DNL Marketo Measure] toepassing op experience.adobe.com/marketo-measure
* Ga naar [!UICONTROL My Account] >[!UICONTROL Settings] > [!UICONTROL Connections]
* Als het verwijderen van de Sandbox-verbinding is voltooid, verdwijnt de verbinding van de pagina. Als dit niet het geval is, blijft de verbinding aanwezig met de status &quot;Deletion in progress&quot;
* Klik op &quot;[!UICONTROL Set up New CRM connection]&quot;
* In het veld &quot;[!UICONTROL Select CRM Connection]&quot;, klikt u op de knop &quot;[!UICONTROL Connect]&quot; Actie naast de [!DNL Salesforce] Platform, selecteer &quot;[!UICONTROL Production]&quot;, optie
* U wordt gevraagd uw referenties in te voeren. Geef aanmeldingsgegevens voor de productie op

## Stap 4: Salesforce-configuratie {#salesforce-configuration}

[Pagina-indelingen](/help/configuration-and-setup/marketo-measure-and-salesforce/page-layout-instructions.md)

[Machtigingssets](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md)

[Rapporten delen](https://help.salesforce.com/articleView?id=analytics_share_folder.htm&amp;type=0){target="_blank"}

[Overbodige rapporttypen verbergen](/help/configuration-and-setup/marketo-measure-and-salesforce/hiding-unnecessary-report-types.md)

[Aangepaste workflow indien van toepassing](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)
