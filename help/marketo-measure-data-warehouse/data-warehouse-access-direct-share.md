---
description: Toegang tot Data Warehouse - Direct delen - Productdocumentatie
title: Toegang tot Data Warehouse - Direct delen
exl-id: 940c3316-5f94-4aa2-a656-aec5eb7b7450
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 0%

---

# Toegang tot Data Warehouse - Direct delen {#data-warehouse-access-direct-share}

**Vereisten**

Om [!DNL Marketo Measure] aan opstelling moet een direct aandeel aan het gegevenspakhuis u aan de volgende vereisten voldoen.

* Je hebt je eigen Snowflake-exemplaar.
* Uw Snowflake-instantie bevindt zich in de regio Azure East US 2 Snowflake.
* U verstrekt [!DNL Marketo Measure] met uw Snowflake account-id.

**Beperkingen**

[!DNL Marketo Measure] alleen Snowflake Direct-aandelen kunnen instellen met accounts in Azure East US 2 vanwege de huidige beperkingen van het directe Snowflake Direct-aandeel. Als u wilt dat uw gegevens beschikbaar worden gesteld in andere regio&#39;s van de Snowflake, raden we u aan een kopie van de gegevens te maken in een Snowflake-account in Azure East US 2 en de [Snowflake Database-replicatie](https://docs.snowflake.com/en/user-guide/database-replication-intro.html){target=&quot;_blank&quot;} om uw gegevens te kopiëren in het gebied/account van de Snowflake.

**Toegang tot het delen**

Nadat het aandeel voor de opgegeven account-id is gemaakt, moet u het [stappen instellen](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target=&quot;_blank&quot;} in uw Snowflake-instantie om toegang te krijgen tot de gegevens.

>[!NOTE]
>
>U kunt elke gewenste databasenaam kiezen. U kunt de voorrechten aan om het even welke regel toewijzen u kiest, zolang het in uw instantie van de Snowflake bestaat.

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

Voor meer gedetailleerde instructies en stappen om deze stappen van de interface van de Snowflake te verwezenlijken, gelieve te verwijzen [Snowflake](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target=&quot;_blank&quot;}.
