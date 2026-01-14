---
description: Meer informatie over vereisten en stappen om directe toegang tot het Marketo Measure-gegevenspakhuis in Snowflake mogelijk te maken
title: Data Warehouse Access - Direct delen
exl-id: 940c3316-5f94-4aa2-a656-aec5eb7b7450
feature: Data Warehouse
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%

---

# Data Warehouse Access - Direct delen {#data-warehouse-access-direct-share}

## Vereisten {#requirements}

Als u [!DNL Marketo Measure] wilt toestaan een rechtstreekse koppeling naar het gegevenspakhuis in te stellen, moet u aan de volgende vereisten voldoen.

* Je hebt je eigen Snowflake-exemplaar.
* Uw Snowflake-instantie bevindt zich in de Azure East US 2 Snowflake-regio.
* U geeft [!DNL Marketo Measure] op met de id van uw Snowflake-account.

## Beperkingen {#limitations}

[!DNL Marketo Measure] kan alleen Snowflake Direct-aandelen instellen met accounts in Azure East US 2 vanwege de huidige beperkingen van Snowflake Direct Share. Als u uw gegevens om in andere gebieden van Snowflake moet worden ter beschikking gesteld, adviseren wij het maken van een exemplaar van de gegevens in een rekening van Snowflake die in Azure East US 2 wordt gevestigd en het gebruiken van de [&#x200B; eigenschap van de Replicatie van het Gegevensbestand 0&rbrace; Snowflake om uw gegevens in het gebied van Snowflake/de rekening van uw keus te kopiëren.](https://docs.snowflake.com/en/user-guide/database-replication-intro.html){target="_blank"}

## Snowflake-account-id invoeren {#enter-snowflake-account-id}

Open de **sectie van Montages** in Marketo Measure app en navigeer aan de **Data Warehouse** pagina. In de **Directe sectie van het Aandeel**, ga uw [&#x200B; Snowflake rekeningsidentiteitskaart &#x200B;](https://docs.snowflake.com/en/user-guide/admin-account-identifier.html){target="_blank"} in de verstrekte doos in en klik **verbinden**.

![](assets/data-share-1.png)

## Toegang tot het delen {#accessing-the-share}

Nadat het aandeel voor verstrekte rekeningidentiteitskaart wordt gecreeerd, moet u de [&#x200B; opstellingsstappen &#x200B;](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target="_blank"} binnen uw instantie van Snowflake voltooien om tot de gegevens toegang te hebben.

>[!NOTE]
>
>U kunt elke gewenste databasenaam kiezen. U kunt de rechten toewijzen aan elke rol die u kiest, zolang deze bestaat in uw Snowflake-instantie.

* De rol Account Admin gebruiken

```sql
USE ROLE ACCOUNTADMIN
```

* Beschikbare aandelen weergeven (dit geeft de naam van het toegekende aandeel aan)

```sql
SHOW SHARES
```

* Een database maken voor delen

```sql
CREATE DATABASE <database_name> FROM SHARE <provider_account>.<share_name>
```

* Rechten verlenen voor de gedeelde database

```sql
GRANT IMPORTED PRIVILEGES ON DATABASE <database_name> TO ROLE <role_name>
GRANT IMPORTED PRIVILEGES ON ALL SCHEMAS IN DATABASE <database_name> TO ROLE <role_name>
```

Voor meer gedetailleerde instructies en stappen om deze stappen van Snowflake UI te verwezenlijken, verwijzing {de documentatie van 0} Snowflake direct [.](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target="_blank"}
