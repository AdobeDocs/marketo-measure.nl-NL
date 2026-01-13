---
description: Data Warehouse Access - Direct delen
title: Data Warehouse Access - Direct delen
exl-id: 940c3316-5f94-4aa2-a656-aec5eb7b7450
feature: Data Warehouse
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
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

[!DNL Marketo Measure] kan alleen Snowflake Direct-aandelen instellen met accounts in Azure East US 2 (dit is een beperking in Marketo Measure, niet in Snowflake). Als u uw gegevens om in andere gebieden van Snowflake moet worden ter beschikking gesteld, adviseren wij het maken van een exemplaar van de gegevens in een rekening van Snowflake die in Azure East US 2 wordt gevestigd en het gebruiken van de [&#x200B; eigenschap van de Replicatie van het Gegevensbestand 0&rbrace; Snowflake om uw gegevens in het gebied van Snowflake/de rekening van uw keus te kopiëren.](https://docs.snowflake.com/en/user-guide/database-replication-intro.html){target="_blank"}

## Snowflake-account-id invoeren {#enter-snowflake-account-id}

Open de **sectie van Montages** in Marketo Measure app en navigeer aan de **Data Warehouse** pagina. In de **Directe sectie van het Aandeel**, ga uw [&#x200B; Snowflake rekeningsidentiteitskaart &#x200B;](https://docs.snowflake.com/en/user-guide/admin-account-identifier.html){target="_blank"} in de verstrekte doos in en klik **verbinden**.

![&#x200B; de montages van Marketo Measure Data Warehouse die de vorm van het Aandeel van Snowflake Direct tonen &#x200B;](assets/data-warehouse-access-direct-share-1.png)

## Toegang tot het delen {#accessing-the-share}

Nadat het aandeel voor verstrekte rekeningidentiteitskaart wordt gecreeerd, moet u de [&#x200B; opstellingsstappen &#x200B;](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target="_blank"} binnen uw instantie van Snowflake voltooien om tot de gegevens toegang te hebben.

>[!NOTE]
>U kunt elke gewenste databasenaam kiezen. U kunt de rechten toewijzen aan elke rol die u kiest, zolang deze bestaat in uw Snowflake-instantie.

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

Voor meer gedetailleerde instructies en stappen om deze stappen van Snowflake UI te verwezenlijken, verwijzing {de documentatie van 0} Snowflake direct [.](https://docs.snowflake.com/en/user-guide/data-share-consumers.html){target="_blank"}
