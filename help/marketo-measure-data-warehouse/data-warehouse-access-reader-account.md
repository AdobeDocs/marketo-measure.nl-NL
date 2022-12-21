---
description: Toegang tot Data Warehouse - account Reader - productdocumentatie
title: Toegang tot Data Warehouse - Account Reader
exl-id: 2aa73c41-47ab-4f11-96d8-dafb642308fc
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 0%

---

# Toegang tot Data Warehouse - Account Reader {#data-warehouse-access-reader-account}

## Snowflake Access-koppeling {#snowflake-access-link}

Als u toegang wilt krijgen tot uw Snowflake-gegevensopslagruimte, moet u naar de specifieke URL voor uw Snowflake-account navigeren. U kunt deze toegangsverbinding vinden door te registreren in [!DNL Marketo Measure] en volgt u de onderstaande stappen om naar de pagina met informatie over de Data Warehouse te navigeren.

1. In [!DNL Marketo Measure], boven aan de pagina, klikt u op **[!UICONTROL My Account]** > **[!UICONTROL Settings]**.

   ![](assets/data-warehouse-access-reader-account-1.png)

1. Klik in het linkermenu onder Beveiliging op **[!UICONTROL Data Warehouse]**.

   ![](assets/data-warehouse-access-reader-account-2.png)

1. Op deze pagina, zult u de verbinding aan uw Snowflake gegevenspakhuis en uw gebruikersbenaming vinden.

   ![](assets/data-warehouse-access-reader-account-3.png)

   >[!NOTE]
   >
   >Dit is een alleen-lezen account dat beschikbaar is voor uw organisatie, en niet alleen voor een individuele gebruiker. Elke gebruiker binnen uw organisatie die toegang heeft tot [!DNL Marketo Measure] U kunt dit account gebruiken om u aan te melden bij het account van de Snowflake Data Warehouse reader.

1. Klik op de koppeling in de URL van de Snowflake. Hiermee gaat u naar de aanmeldingspagina van de Snowflake waar u uw gebruikersnaam en wachtwoord opgeeft. _Als u uw wachtwoord niet hebt, raadpleegt u de onderstaande stappen om het opnieuw in te stellen_.

   ![](assets/data-warehouse-access-reader-account-4.png)

1. Nadat u zich hebt aangemeld, klikt u op **[!UICONTROL Worksheets]** boven aan de pagina.

   ![](assets/data-warehouse-access-reader-account-5.png)

1. De BIZIBLE_ROI_V3-databaseobjecten bevinden zich aan de linkerkant van het scherm. Ga het Warehouse, het Gegevensbestand, en het Schema van de dropdown opties bij de bovenkant van het vraagvenster in. Er mag slechts één optie voor elke optie zijn. Nu bent u bereid om vragen binnen de Snowflake vraagredacteur uit te voeren.

   ![](assets/data-warehouse-access-reader-account-6.png)

## Wachtwoord opnieuw instellen {#reset-your-password}

[!DNL Marketo Measure] heeft geen toegang tot uw wachtwoord voor aanmelding bij Snowflake. Als u het wachtwoord opnieuw moet instellen, klikt u op de knop [!UICONTROL Reset Password] op de pagina met informatie over de Data Warehouse en volg de instructies. Er wordt direct een tijdelijk wachtwoord weergegeven in de gebruikersinterface. U zal worden ertoe aangezet om uw eigen wachtwoord op uw volgende login van het gegevenspakhuis tot stand te brengen.

>[!NOTE]
>
>* Het wachtwoord opnieuw instellen herstelt het voor allen [!DNL Marketo Measure] gebruikers in uw organisatie, niet alleen de gebruiker die momenteel is aangemeld.
>* Het tijdelijke wachtwoord wordt alleen weergegeven in de gebruikersinterface. Er wordt geen e-mail verzonden.


![](assets/data-warehouse-access-reader-account-7.png)

![](assets/data-warehouse-access-reader-account-8.png)

## Verbinding maken met Snowflake via hulpmiddelen van derden {#connecting-to-snowflake-via-third-party-tools}

U zult een paar stukken van informatie moeten ingaan om uw Snowflake gegevenspakhuis met een derdehulpmiddel te verbinden.

>[!NOTE]
>
>Elk hulpmiddel heeft verschillende verbindingsvereisten; raadt u aan de documentatie te raadplegen voor het specifieke gereedschap dat u probeert te verbinden.

* **URI** (altijd vereist)
   * Dit is de domeinnaam van de Snowflake-account.  Het is bevat binnen een gedeelte van de Snowflake login verbinding.
* **Gebruikersnaam** (altijd vereist)
   * De gebruikersnaam wordt vermeld op de pagina met informatie over de Data Warehouse in [!DNL Marketo Measure].
* **Wachtwoord** (altijd vereist)
   * Dit is het wachtwoord dat u instelt als u zich voor het eerst hebt aangemeld bij uw Snowflake-account.  Zie de bovenstaande stappen om uw wachtwoord opnieuw in te stellen.
* **Databasenaam** (niet altijd vereist)
   * De gegevens worden opgeslagen in Snowflake in de database. Het is de opslagbron. De databasenaam wordt vermeld op de pagina met informatie over de Data Warehouse in [!DNL Marketo Measure].
* **Warehouse-naam** (niet altijd vereist)
   * Het pakhuis is wat vragen in Snowflake uitvoert. Het is de computerbron.  De pakhuisnaam wordt vermeld op de de informatiepagina van de Data Warehouse in [!DNL Marketo Measure].
   ![](assets/data-warehouse-access-reader-account-9.png)
