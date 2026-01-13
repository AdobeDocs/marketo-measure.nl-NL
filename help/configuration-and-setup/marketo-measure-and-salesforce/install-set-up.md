---
description: '[!DNL Marketo Measure] Installatie en installatie van Salesforce-pakketten -  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] [!DNL Salesforce]  de Installatie van het Pakket en Opstelling'
exl-id: ed58bc1e-cfb0-48db-aa53-96204e12de2e
feature: Installation, Salesforce
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 0%

---


# [!DNL Marketo Measure] Salesforce-pakket installeren en instellen {#marketo-measure-salesforce-package-installation-and-set-up}

Voordat u het basispakket [!DNL Marketo Measure] [!DNL Salesforce] installeert, moet u bepalen of u het eerst in een [!DNL Salesforce] -sandbox installeert voordat u naar de Salesforce-productieinstantie gaat.

>[!NOTE]
>Wanneer uw [!DNL Marketo Measure] -account is verbonden met een [!DNL Salesforce] -productie-instantie, kunt u niet achterwaarts gaan en verbinding maken met een sandbox. Een [!DNL Marketo Measure] -account kan bovendien alleen worden verbonden met één [!DNL Salesforce] -productie-instantie.

Het [!DNL Marketo Measure] basispakket bevat:

* 7 aangepaste [!DNL Marketo Measure] objecten
* Aangepaste [!DNL Marketo Measure] velden
* 25 [!DNL Stock] Rapporten

[!DNL Marketo Measure] kan standaard [!DNL Salesforce] Objecten, velden en records lezen, maar [!DNL Marketo Measure] werkt of duwt er nooit gegevens naar bij. Alle gegevens die door de [!DNL Marketo Measure] JavaScript zijn verzameld, worden weergegeven in de [!DNL Marketo Measure] Aangepaste objecten en velden.

Voer de onderstaande stappen uit om het basispakket [!DNL Marketo Measure Salesforce] te installeren.

1. Gebruikend incognito browser, ga naar [&#x200B; Salesforce AppExchange &#x200B;](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N3000000B3KLuEAN){target="_blank"} en login.

1. Installeer in het [!DNL Marketo Measure] -pakket in een sandbox of productie.

1. Meld u aan bij [!DNL Salesforce] als beheerder.

1. Selecteer **[!UICONTROL Install]voor Alle Gebruikers**.

   ![&#x200B; AppExchange van Salesforce installeert dialoog voor het pakket van Marketo Measure &#x200B;](assets/marketo-measure-salesforce-package-installation-and-set-up-1.png)

1. Nadat de installatie is voltooid, kunt u deze weergeven.

   ![&#x200B; Geïnstalleerde het pakketdetailpagina van Marketo Measure in Salesforce &#x200B;](assets/marketo-measure-salesforce-package-installation-and-set-up-2.png)

Nadat u de installatie hebt voltooid, kunt u uw [[!DNL Salesforce]  paginalay-outs &#x200B;](/help/configuration-and-setup/marketo-measure-and-salesforce/page-layout-instructions.md){target="_blank"} met de [!DNL Marketo Measure] gebieden indien gewenst bijwerken.

>[!NOTE]
>Lees over de [!DNL Marketo Measure] gecreeerde Reeksen van Toestemmingen en [&#x200B; hoe zij &#x200B;](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md){target="_blank"} worden gebruikt.

## Een [!DNL Marketo Measure] profiel en gebruiker maken {#creating-a-marketo-measure-profile-and-user}

[!DNL Marketo Measure] verzendt en ontvangt gegevens via een verbonden [!DNL Salesforce] -gebruiker in de [!DNL Marketo Measure] -app.

Als u aanraakpuntgegevens naar uw [!DNL Salesforce] -instantie wilt verzenden, moet de verbonden gebruiker toegang hebben tot [!DNL Marketo Measure] aangepaste objecten (bijvoorbeeld Buyer Touchpoint en Buyer Attribution Touchpoint) en tot standaard [!DNL Salesforce] -objecten zoals Leads en Contacten.

Maak een [!DNL Marketo Measure] -profiel om te zorgen dat er geen validatiefouten optreden wanneer u gegevens naar Salesforce verplaatst.

Stap 1: Een specifiek [!DNL Marketo Measure] -profiel maken

1. Wijs de volgende machtigingen toe:

* &quot;[!DNL Marketo Measure] Beheerdermachtigingen instellen&quot;
   * Met de beheerde rechtenset kan een SFDC-beheerder records maken, lezen, schrijven, verwijderen uit [!DNL Marketo Measure] -objecten.
* &quot;Omgezette machtigingsset voor leads weergeven en bewerken&quot;
   * Hierdoor kan [!DNL Marketo Measure] leads decoreren nadat deze zijn omgezet in contactpersonen. Als deze rechtenset niet is ingeschakeld, kunnen er belangrijke hiaten in het bijhouden van gegevens zijn.

>[!NOTE]
>Dit profiel kan een kloon zijn van een profiel voor systeembeheer.

Stap 2: Maak een toegewijde [!DNL Marketo Measure] -gebruiker zodat u de impact van [!DNL Marketo Measure] op de [!DNL Salesforce] -instantie kunt volgen

1. Wijs het nieuwe [!DNL Marketo Measure] profiel toe aan die gebruiker.

1. Schakel &quot;Gebruiker op de markt brengen&quot; in als machtiging op gebruikersniveau.

* Met het selectievakje [!UICONTROL Marketing User] kan de gebruiker campagnes maken en de wizard Campagne importeren gebruiken. Als deze optie niet is geselecteerd, kan de gebruiker alleen campagnes en geavanceerde campagneopstelling weergeven, de Campagnegeschiedenis voor één enkele lead of contactpersoon bewerken en campagnerapporten uitvoeren. [!DNL Marketo Measure] moet het campagneobject kunnen lezen en schrijven.

Stap 3: Sluit dit profiel uit van alle triggers, workflows en processen

Stap 4: Meld u aan bij uw [!DNL Marketo Measure] -account en autoriseer de [!DNL Salesforce] -verbinding met de nieuwe gebruiker opnieuw

1. Ga naar apps.bizible.com en meld u aan met de gebruikersgegevens voor de nieuwe gebruikersproductie [!DNL Salesforce] .

1. Selecteer **[!UICONTROL Settings]** in de vervolgkeuzelijst **[!UICONTROL My Account]** .

1. Selecteer **[!UICONTROL Connections]** in de **[!UICONTROL Integrations]** -groep.

1. Klik het Zeer belangrijke Pictogram rechts van de huidige verbonden [!DNL Salesforce] verbinding en selecteer **opnieuw machtigen met Productie**. Meld u opnieuw aan met de nieuwe gebruikersgegevens (indien gevraagd).

>[!MORELIKETHIS]
> [&#x200B; Overzicht van de Toestemmingen van de Integratie &#x200B;](/help/api-connections/integration-permissions-overview.md){target="_blank"}
> [Adobe Admin Console Setup &#x200B;](/help/configuration-and-setup/getting-started-with-marketo-measure/adobe-admin-console-setup.md){target="_blank"}
