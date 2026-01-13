---
description: Salesforce Sandbox to Production Migration - [!DNL Marketo Measure]
title: Salesforce-sandbox naar productie-migratie
exl-id: b2b71c4a-f192-43ce-a27e-cbd0ec3cf008
feature: Salesforce
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 0%

---


# Salesforce-sandbox naar productie-migratie {#salesforce-sandbox-to-production-migration}

Als u ervoor kiest om [!DNL Marketo Measure] te testen in een [!DNL Salesforce] Sandbox-omgeving, volgt u deze instructies om naar Production te migreren zodra u klaar bent. In de volgende instructies wordt ervan uitgegaan dat u het [!DNL Marketo Measure] -pakket al hebt gedownload naar uw Sandbox-org, de vereiste tests hebt uitgevoerd en klaar bent om [!DNL Marketo Measure] naar Production te drukken.

## Stap 1: Installeer het [!DNL Marketo Measure] pakket in uw productie [!DNL Salesforce] -instantie

* Installeer het [!DNL Marketo Measure] -pakket in Production met de instelling &quot;[!UICONTROL All Users]&quot;

   * [ Pakket van de Basis ](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N3000000B3KLuEAN){target="_blank"}

* Voor meer informatie over de [!DNL Marketo Measure] verhouding met [!DNL Salesforce], bekijk [ dit artikel ](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md)
* Een beetje van [!DNL Salesforce] configuratie is noodzakelijk. De specifieke actiepunten worden hieronder geschetst in [ Stap 4 hieronder ](#salesforce-configuration)

## Stap 2: Verwijder de huidige sandbox CRM-verbinding in de app [!DNL Marketo Measure] {#delete-the-current-sandbox-crm-connection-in-marketo-measure-app}

* Meld u aan bij de toepassing [!DNL Marketo Measure] op experience.adobe.com/marketo-measure
* Ga naar Mijn account > [!UICONTROL Settings] > [!UICONTROL Connections]
* Klik op het prullenbakpictogram naast de SFDC-verbinding om deze te verwijderen
* U wordt gevraagd uw verwijdering te bevestigen. Zorg ervoor dat u de vraag zorgvuldig leest en begrijp de gevolgen van het verwijderen

  ![ de verbindingspagina die van Marketo Measure schrapping van een zandbak van Salesforce bevestigen ](assets/salesforce-sandbox-to-production-migration-1.png)

   * Typ de naam van het bedrijf zoals gevraagd in het bevestigingsmodel en klik op &quot;Ik begrijp de gevolgen, verwijder deze verbinding&quot;
* Dit leidt tot het schrappingsproces en zal wat tijd vergen om te beëindigen

## Stap 3: Verbind de Instantie van CRM van de Productie in [!DNL Marketo Measure] App {#connect-the-production-crm-instance-in-marketo-measure-app}

* Meld u aan bij de toepassing [!DNL Marketo Measure] op experience.adobe.com/marketo-measure
* Ga naar [!UICONTROL My Account] > [!UICONTROL Settings] > [!UICONTROL Connections]
* Als het verwijderen van de Sandbox-verbinding is voltooid, verdwijnt de verbinding van de pagina. Als dit niet het geval is, blijft de verbinding aanwezig met de status &quot;Deletion in progress&quot;
* Klik op &quot;[!UICONTROL Set up New CRM connection]&quot;
* Klik in het modale dialoogvenster &quot;[!UICONTROL Select CRM Connection]&quot; op de handeling &quot;[!UICONTROL Connect]&quot; naast het [!DNL Salesforce] -platform en selecteer de optie &quot;[!UICONTROL Production]&quot;
* U wordt gevraagd uw referenties in te voeren. Geef de aanmeldingsgegevens voor de productie op

## Stap 4: Salesforce-configuratie {#salesforce-configuration}

[Pagina-indelingen](/help/configuration-and-setup/marketo-measure-and-salesforce/page-layout-instructions.md)

[Machtigingssets](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md)

[ het Delen rapporten ](https://help.salesforce.com/s/articleView?language=en_US&id=analytics_share_folder.htm&type=0){target="_blank"}

[Overbodige rapporttypen verbergen](/help/configuration-and-setup/marketo-measure-and-salesforce/hiding-unnecessary-report-types.md)

[Aangepaste workflow indien van toepassing](/help/advanced-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)
