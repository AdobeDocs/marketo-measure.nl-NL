---
description: Toegang tot Data Warehouse - account Reader - productdocumentatie
title: Toegang tot Data Warehouse - Account Reader
exl-id: 2aa73c41-47ab-4f11-96d8-dafb642308fc
feature: Data Warehouse
source-git-commit: e9861f8032475d3e60a3bb3ebf67dfee520bbb75
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 0%

---

# Toegang tot Data Warehouse - Account Reader {#data-warehouse-access-reader-account}

## Koppeling naar toegang Snowflake {#snowflake-access-link}

Om tot uw Snowflake gegevenspakhuis toegang te hebben, moet u aan specifieke URL voor uw rekening van de Snowflake navigeren. U vindt deze toegangskoppeling door u aan te melden bij [!DNL Marketo Measure] en de onderstaande stappen te volgen om naar de pagina met informatie over de Data Warehouse te navigeren.

1. Klik in [!DNL Marketo Measure] boven aan de pagina op **[!UICONTROL My Account]** > **[!UICONTROL Settings]** .

   ![](assets/data-warehouse-access-reader-account-1.png)

1. Klik in het linkermenu onder Beveiliging op **[!UICONTROL Data Warehouse]** .

   ![](assets/data-warehouse-access-reader-account-2.png)

1. Deze pagina heeft de verbinding aan uw het gegevenspakhuis van de Snowflake en uw gebruikersbenaming.

   ![](assets/data-warehouse-access-reader-account-3.png)

   >[!NOTE]
   >
   >Dit is een alleen-lezen account dat beschikbaar is voor uw organisatie, en niet alleen voor een individuele gebruiker. Elke gebruiker binnen uw organisatie die toegang heeft tot [!DNL Marketo Measure] kan dit account gebruiken om u aan te melden bij het account voor de Data Warehouse van de Snowflake.

1. Klik op de koppeling in de URL van de Snowflake om naar de aanmeldingspagina van de Snowflake te gaan waar u uw gebruikersnaam en wachtwoord invoert. _als u uw wachtwoord niet hebt, zie de stappen hieronder om het_ terug te stellen.

   ![](assets/data-warehouse-access-reader-account-4.png)

1. Klik op **[!UICONTROL Worksheets]** boven aan de pagina als u zich hebt aangemeld.

   ![](assets/data-warehouse-access-reader-account-5.png)

1. De BIZIBLE_ROI_V3-databaseobjecten bevinden zich aan de linkerkant van het scherm. Ga het Warehouse, het Gegevensbestand, en het Schema van de dropdown opties bij de bovenkant van het vraagvenster in. Er mag slechts één optie voor elke optie zijn. Nu bent u bereid om vragen binnen de de vraagredacteur van de Snowflake uit te voeren.

   ![](assets/data-warehouse-access-reader-account-6.png)

## Wachtwoord opnieuw instellen {#reset-your-password}

[!DNL Marketo Measure] heeft geen toegang tot uw wachtwoord voor het aanmelden van de Snowflake. Als u het wachtwoord opnieuw moet instellen, klikt u op de knop [!UICONTROL Reset Password] op de pagina met informatie over de Data Warehouse en volgt u de instructies. Een tijdelijk wachtwoord wordt onmiddellijk getoond in UI. U zal worden ertoe aangezet om uw eigen wachtwoord op uw volgende login van het gegevenspakhuis tot stand te brengen.

>[!NOTE]
>
>* Als u het wachtwoord opnieuw instelt, wordt dit opnieuw ingesteld voor alle [!DNL Marketo Measure] -gebruikers in uw organisatie, en niet alleen voor de gebruiker die momenteel is aangemeld.
>* Het tijdelijke wachtwoord wordt alleen weergegeven in de gebruikersinterface. Er wordt geen e-mail verzonden.

![](assets/data-warehouse-access-reader-account-7.png)

![](assets/data-warehouse-access-reader-account-8.png)

## Verbinding maken met Snowflake via hulpmiddelen van derden {#connecting-to-snowflake-via-third-party-tools}

U moet een paar stukken van informatie ingaan om uw Snowflake gegevenspakhuis met een derdehulpmiddel te verbinden.

>[!NOTE]
>
>Elk hulpmiddel heeft verschillende verbindingsvereisten; het wordt geadviseerd u de documentatie voor het specifieke hulpmiddel raadpleegt u probeert om te verbinden.

* **URI** (altijd vereist)
   * Dit is de domeinnaam van de account Snowflake. Het is bevat binnen een gedeelte van de Snowflake login verbinding.
* **Gebruikersnaam** (altijd vereist)
   * De gebruikersnaam wordt vermeld op de pagina met informatie over de Data Warehouse in [!DNL Marketo Measure] .
* **Wachtwoord** (altijd vereist)
   * Dit is het wachtwoord dat u instelt de eerste keer dat u zich hebt aangemeld bij uw Snowflake-account. Zie de bovenstaande stappen om uw wachtwoord opnieuw in te stellen.
* **Naam van het Gegevensbestand** (niet altijd vereist)
   * De database is wat de gegevens in Snowflake opslaat. Het is de opslagbron. De databasenaam wordt vermeld op de pagina met informatie over de Data Warehouse in [!DNL Marketo Measure] .
* **Naam van het Warehouse** (niet altijd vereist)
   * Het pakhuis is wat vragen in Snowflake uitvoert. Het is de berekende bron. De pakhuisnaam wordt vermeld op de de informatiepagina van de Data Warehouse in [!DNL Marketo Measure].

  ![](assets/data-warehouse-access-reader-account-9.png)
