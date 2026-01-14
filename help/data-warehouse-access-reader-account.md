---
description: Beschrijft hoe te opstelling en een lezerrekening te gebruiken om tot het gegevenspakje van Marketo Measure toegang te hebben
title: Data Warehouse Access - Reader-account
exl-id: 2aa73c41-47ab-4f11-96d8-dafb642308fc
feature: Data Warehouse
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 1%

---

# Data Warehouse Access - Reader-account {#data-warehouse-access-reader-account}

## Snowflake Access-koppeling {#snowflake-access-link}

Als u toegang wilt tot uw Snowflake-gegevenspaket, moet u naar de specifieke URL voor uw Snowflake-account navigeren. U vindt deze toegangskoppeling door u aan te melden bij [!DNL Marketo Measure] en de onderstaande stappen te volgen om naar de Data Warehouse-informatiepagina te navigeren.

1. Klik in [!DNL Marketo Measure] boven aan de pagina op **[!UICONTROL My Account]** > **[!UICONTROL Settings]** .

   ![1. In Marketo Measure, bij de bovenkant van de pagina, klik ](assets/data-account-7.png)

1. Klik in het linkermenu onder Beveiliging op **[!UICONTROL Data Warehouse]** .

   ![1. Op de linkerkant menu, onder Veiligheid, klik Data Warehouse.](assets/data-account-8.png)

1. Deze pagina heeft de verbinding aan uw Snowflake gegevenspakhuis en uw gebruikersbenaming.

   ![1. Deze pagina heeft de verbinding aan uw het gegevenspakhuis van Snowflake en ](assets/data-account-9.png)

   >[!NOTE]
   >
   >Dit is een alleen-lezen account dat beschikbaar is voor uw organisatie, en niet alleen voor een individuele gebruiker. Elke gebruiker binnen uw organisatie die toegang heeft tot [!DNL Marketo Measure] , kan dit account gebruiken om u aan te melden bij het Snowflake Data Warehouse-lezeraccount.

1. Klik op de koppeling in de URL van Snowflake. Hiermee gaat u naar de aanmeldingspagina van Snowflake waar u uw gebruikersnaam en wachtwoord invoert. _als u uw wachtwoord niet hebt, zie de stappen hieronder om het_ terug te stellen.

   ![1. Klik op de koppeling in de URL van Snowflake, zodat u deze koppeling kunt gebruiken ](assets/data-account-5.png)

1. Klik op **[!UICONTROL Worksheets]** boven aan de pagina als u zich hebt aangemeld.

   ![1. Zodra het programma geopend, klik Werkbladen bij de bovenkant van ](assets/data-account-6.png)

1. De BIZIBLE_ROI_V3-databaseobjecten bevinden zich aan de linkerkant van het scherm. Ga het Warehouse, het Gegevensbestand, en het Schema van de dropdown opties bij de bovenkant van het vraagvenster in. Er mag slechts één optie voor elke optie zijn. Nu kunt u query&#39;s uitvoeren in de Snowflake-query-editor.

   ![1. De BIZIBLEROIV3 gegevensbestandvoorwerpen zijn op de linkerkant van ](assets/data-account-4.png)

## Wachtwoord opnieuw instellen {#reset-your-password}

[!DNL Marketo Measure] heeft geen toegang tot uw Snowflake-wachtwoord. Als u het wachtwoord opnieuw moet instellen, klikt u op de knop [!UICONTROL Reset Password] op de pagina Data Warehouse-informatie en volgt u de instructies. Een tijdelijk wachtwoord wordt onmiddellijk getoond in UI. U zal worden ertoe aangezet om uw eigen wachtwoord op uw volgende login van het gegevenspakhuis tot stand te brengen.

>[!NOTE]
>
>* Als u het wachtwoord opnieuw instelt, wordt dit opnieuw ingesteld voor alle [!DNL Marketo Measure] -gebruikers in uw organisatie, en niet alleen voor de gebruiker die momenteel is aangemeld.
>* Het tijdelijke wachtwoord wordt alleen weergegeven in de gebruikersinterface. Er wordt geen e-mail verzonden.

![ wij tonen slechts het tijdelijke wachtwoord in UI. Een e-mail zal ](assets/data-account-3.png)

![ wij tonen slechts het tijdelijke wachtwoord in UI. Een e-mail zal ](assets/data-account-1.png)

## Verbinding maken met Snowflake via tools van derden {#connecting-to-snowflake-via-third-party-tools}

U moet een paar stukken informatie ingaan om uw Snowflake gegevenspakhuis met een derdehulpmiddel te verbinden.

>[!NOTE]
>
>Elk hulpmiddel heeft verschillende verbindingsvereisten; het wordt geadviseerd u de documentatie voor het specifieke hulpmiddel raadplegen u probeert om te verbinden.

* **URI** (altijd vereist)
   * Dit is de domeinnaam van de Snowflake-account. Het bevindt zich in een gedeelte van de Snowflake-aanmeldkoppeling.
* **Gebruikersnaam** (altijd vereist)
   * De gebruikersnaam wordt weergegeven op de Data Warehouse-informatiepagina in [!DNL Marketo Measure] .
* **Wachtwoord** (altijd vereist)
   * Dit is het wachtwoord dat u instelt wanneer u zich voor het eerst bij uw Snowflake-account hebt aangemeld. Zie de bovenstaande stappen om uw wachtwoord opnieuw in te stellen.
* **Naam van het Gegevensbestand** (niet altijd vereist)
   * De database is de database waarin de gegevens worden opgeslagen in Snowflake. Het is de opslagbron. De databasenaam wordt weergegeven op de Data Warehouse-informatiepagina in [!DNL Marketo Measure] .
* **Naam van het Warehouse** (niet altijd vereist)
   * Het pakhuis is wat vragen in Snowflake uitvoert. Het is de berekende bron. De pakhuisnaam wordt vermeld op de Data Warehouse informatiepagina in [!DNL Marketo Measure].

  ![ het pakhuis is wat vragen in Snowflake uitvoert. Het is gegevens verwerkt ](assets/data-account-2.png)
