---
description: Toegang tot Data Warehouse - Direct delen - Productdocumentatie
title: Toegang tot Data Warehouse - Direct delen
exl-id: 940c3316-5f94-4aa2-a656-aec5eb7b7450
feature: Data Warehouse
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 0%

---

# Toegang tot Data Warehouse - Direct delen {#data-warehouse-access-direct-share}

## Vereisten {#requirements}

Om [!DNL Marketo Measure] aan opstelling moet een direct aandeel aan het gegevenspakhuis u aan de volgende vereisten voldoen.

* Je hebt je eigen Snowflake-instantie.
* Uw instantie van de Snowflake wordt gevestigd in het Azure East US 2 Snowflake gebied.
* U verstrekt [!DNL Marketo Measure] met uw account-id voor Snowflaken.

## Beperkingen {#limitations}

[!DNL Marketo Measure] alleen Snowflake Direct Shares met accounts in Azure East US 2 kunnen instellen vanwege de huidige beperkingen van Direct Share voor Snowflaken. Als u uw gegevens in andere gebieden van de Snowflake ter beschikking wilt stellen, adviseren wij een exemplaar van de gegevens in een rekening van de Snowflake in Azure East US 2 te maken en leveraging [Replicatie database Snowflake](https://docs.snowflake.com/en/user-guide/database-replication-intro.html){target="_blank"} om uw gegevens in het gebied/de rekening van uw keuze van de Snowflake te kopiëren.

## Account-ID Snowflake invoeren {#enter-snowflake-account-id}

Open de **Instellingen** in de Marketo Measure-app en navigeer naar de **Data Warehouse** pagina. In de **Direct delen** in, voert u uw [ID Snowflake-account](https://docs.snowflake.com/en/user-guide/admin-account-identifier.html){target="_blank"} in het meegeleverde vak en klik op **Verbinden**.

![](assets/data-warehouse-access-direct-share-1.png)

## Toegang tot het delen {#accessing-the-share}

Nadat het aandeel voor de opgegeven account-id is gemaakt, moet u het [installatiestappen](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target="_blank"} binnen uw instantie van de Snowflake om tot de gegevens toegang te hebben.

>[!NOTE]
>
>U kunt elke gewenste databasenaam kiezen. U kunt de voorrechten aan om het even welke rol toewijzen u kiest, zolang het in uw instantie van de Snowflake bestaat.

* De rol Account Admin gebruiken

```
USE ROLE ACCOUNTADMIN
```

* Beschikbare aandelen weergeven (dit geeft de naam van het toegekende aandeel aan)

```
SHOW SHARES
```

* Een database maken voor delen

```
CREATE DATABASE <database_name> FROM SHARE <provider_account>.<share_name>
```

* Rechten verlenen voor de gedeelde database

```
GRANT IMPORTED PRIVILEGES ON DATABASE <database_name> TO ROLE <role_name>
GRANT IMPORTED PRIVILEGES ON ALL SCHEMAS IN DATABASE <database_name> TO ROLE <role_name>
```

Voor meer gedetailleerde instructies en stappen om deze stappen van Snowflake UI te verwezenlijken, verwijzing [Rechtstreeks documentatie van Snowflaken](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target="_blank"}.
