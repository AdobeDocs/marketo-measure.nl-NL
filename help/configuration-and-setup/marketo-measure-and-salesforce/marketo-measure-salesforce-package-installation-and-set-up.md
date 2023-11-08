---
description: "[!DNL Marketo Measure] Installatie en installatie van het Salesforce-pakket - [!DNL Marketo Measure] - Productdocumentatie"
title: "[!DNL Marketo Measure] [!DNL Salesforce] Pakketinstallatie en -installatie"
exl-id: ed58bc1e-cfb0-48db-aa53-96204e12de2e
feature: Installation, Salesforce
source-git-commit: 68eb5bf83d589c9161490b1772551ed46a9ce444
workflow-type: tm+mt
source-wordcount: '502'
ht-degree: 0%

---

# [!DNL Marketo Measure] Installatie en installatie van het Salesforce-pakket {#marketo-measure-salesforce-package-installation-and-set-up}

Voordat u de [!DNL Marketo Measure] [!DNL Salesforce] basispakket, moet u bepalen of u het eerst in een [!DNL Salesforce] sandbox voordat u naar de productie-instantie Salesforce gaat.

>[!NOTE]
>
>Eenmaal uw [!DNL Marketo Measure] account is verbonden met een [!DNL Salesforce] productie-instantie, kunt u niet achterwaarts verplaatsen en verbinding maken met een sandbox. Ook een [!DNL Marketo Measure] account kan slechts met één account worden verbonden [!DNL Salesforce] productie-instantie.

De [!DNL Marketo Measure] Basispakket bevat:

* 7 Aangepast [!DNL Marketo Measure] Objecten
* Aangepast [!DNL Marketo Measure] Velden
* 25 [!DNL Stock] Rapporten

[!DNL Marketo Measure] kan de standaard lezen [!DNL Salesforce] Objecten, velden en records, echter [!DNL Marketo Measure] nooit gegevens bijwerken of verzenden. Alle gegevens die door de [!DNL Marketo Measure] JavaScript wordt weergegeven in het dialoogvenster [!DNL Marketo Measure] Aangepaste objecten en velden.

Voer de onderstaande stappen uit om de [!DNL Marketo Measure Salesforce] basispakket.

1. Ga met een incognitobrowser naar de [Salesforce Appexchange](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N3000000B3KLuEAN){target="_blank"} en aanmelden.

1. Installeren in het dialoogvenster [!DNL Marketo Measure] in sandbox of productie.

1. Aanmelden bij [!DNL Salesforce] als beheerder.

1. Selecteren **[!UICONTROL Install]voor Alle Gebruikers**.

   ![](assets/marketo-measure-salesforce-package-installation-and-set-up-1.png)

1. Nadat de installatie is voltooid, kunt u deze weergeven.

   ![](assets/marketo-measure-salesforce-package-installation-and-set-up-2.png)

Nadat u de installatie hebt voltooid, kunt u uw [[!DNL Salesforce] paginalay-outs](/help/configuration-and-setup/marketo-measure-and-salesforce/page-layout-instructions.md){target="_blank"} met de [!DNL Marketo Measure] velden, indien gewenst.

>[!NOTE]
>
>Meer informatie over de [!DNL Marketo Measure] Machtigingen ingesteld en [hoe zij zullen worden gebruikt](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md){target="_blank"}.

## Een [!DNL Marketo Measure] Profiel en gebruiker {#creating-a-marketo-measure-profile-and-user}

[!DNL Marketo Measure] verzendt en ontvangt gegevens door verbonden [!DNL Salesforce] binnen de [!DNL Marketo Measure] app.

Als u aanraakpuntgegevens naar uw [!DNL Salesforce] -instantie, moet de verbonden gebruiker toegang hebben tot [!DNL Marketo Measure] aangepaste objecten (zoals Aanraakpunt koper en Aanraakpunt koper) en standaard [!DNL Salesforce] objecten zoals regelafstand en contactpersonen.

Een [!DNL Marketo Measure] -profiel om te zorgen dat er geen validatiefouten optreden wanneer u gegevens naar Salesforce verplaatst.

Stap 1: Maak een specifieke [!DNL Marketo Measure] profiel

1. Wijs de volgende machtigingen toe:

* &quot;[!DNL Marketo Measure] Beheerdersmachtigingen&quot;
   * De beheerde rechtenset geeft een SFDC-beheerder de mogelijkheid om records te maken, lezen, schrijven, verwijderen uit [!DNL Marketo Measure] objecten.
* &quot;Omgezette machtigingsset voor leads weergeven en bewerken&quot;
   * Dit maakt [!DNL Marketo Measure] om leidingen te versieren nadat ze zijn omgezet in contacten. Als deze rechtenset niet is ingeschakeld, kunnen er belangrijke hiaten in het bijhouden van gegevens zijn.

>[!NOTE]
>
>Dit profiel kan een kloon zijn van een profiel voor systeembeheer.

Stap 2: Een speciale versie maken [!DNL Marketo Measure] gebruiker zodat u het effect van [!DNL Marketo Measure] op uw [!DNL Salesforce] instance

1. Wijs de nieuwe [!DNL Marketo Measure] Profiel naar die gebruiker.

1. Schakel &quot;Gebruiker op de markt brengen&quot; in als machtiging op gebruikersniveau.

* De [!UICONTROL Marketing User] Met het selectievakje kan de gebruiker campagnes maken en de wizard Campagne importeren gebruiken. Als deze optie niet wordt geselecteerd, kan de gebruiker campagnes en geavanceerde campagneopstelling slechts bekijken, de Geschiedenis van de Campagne voor één enkele lood of contact uitgeven, en campagnerapporten in werking stellen. [!DNL Marketo Measure] moet het campagneobject kunnen lezen en schrijven.

Stap 3: Sluit dit profiel uit van alle triggers, workflows en processen

Stap 4: Meld u aan bij uw [!DNL Marketo Measure] Account en autoriseer de [!DNL Salesforce] verbinding met de nieuwe gebruiker

1. Ga naar apps.bizible.com en login met de nieuwe gebruikersproductie [!DNL Salesforce] referenties.

1. Selecteren **[!UICONTROL Settings]** binnen de **[!UICONTROL My Account]** vervolgkeuzelijst.

1. Selecteren **[!UICONTROL Connections]** binnen de **[!UICONTROL Integrations]** groeperen.

1. Klik op het pictogram Key rechts van de huidige verbinding [!DNL Salesforce] verbinding en selecteer naar **Opnieuw autoriseren met productie**. Meld u opnieuw aan met de nieuwe gebruikersgegevens (indien gevraagd).

>[!MORELIKETHIS]
>
>[Adobe Admin Console Setup](/help/configuration-and-setup/getting-started-with-marketo-measure/adobe-admin-console-setup.md){target="_blank"}
