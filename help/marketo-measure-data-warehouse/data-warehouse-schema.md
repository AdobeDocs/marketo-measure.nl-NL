---
unique-page-id: 35586140
description: Data Warehouse Schema - Marketo Measure - Productdocumentatie
title: Data Warehouse Schema
exl-id: f1895eb1-a32d-4c43-93fb-0aa838527946
feature: Data Warehouse
source-git-commit: 3ad812a05671f277d3dd3f9bc58e3b2ea3606e71
workflow-type: tm+mt
source-wordcount: '21110'
ht-degree: 1%

---

# Data Warehouse Schema {#data-warehouse-schema}

Met Data Warehouse kunt u zoveel bijhouden als u wilt, gegevens rapporteren over uw toewijzingsgegevens op de gewenste locatie en deze koppelen aan andere gegevenssets.

>[!IMPORTANT]
>
>* Rijen met een waarde voor _DELETED_DATE worden 7 dagen bewaard en vervolgens uit de Snowflake verwijderd.
>* De tijdzones die in Snowflake worden gebruikt, voldoen aan de UTC (Coordinated Universal Time).

>[!NOTE]
>
>[ klik hier ](#sample-queries) om steekproefvragen bij de bodem van dit artikel te zien.

## Relatiediagrammen voor entiteiten {#entity-relationship-diagrams}

Het _Model van Gegevens van de Data Warehouse_ ERD toont hoe de gegevens in het gegevenspakhuis bedoeld zijn om te stromen en samen worden verbonden. Dit diagram omvat niet alle lijsten beschikbaar in het gegevenspakhuis omdat sommige van hen kaartlijsten, meningen van andere reeds aanwezige lijsten, of afgekeurde lijsten vertegenwoordigen wij niet meer het gebruiken adviseren. Zie de gedetailleerde beschrijvingen van lijsten en kolommen aanwezig in het gegevenspakhuis hieronder. Veel van deze lijsten bevatten gedenormaliseerde gebieden, echter, is dit diagram het geadviseerde gegevensmodel, leveraging gegevens van dimensionele lijsten in plaats daarvan.

Extra _voegt het Model van Gegevens 1} ERD van Dimensionele Gegevens van Gegevens toe {stelt een mening van voor hoe de lijsten voor advertenties specifieke dimensies het best terug naar de lijsten in het belangrijkste gegevensmodel kunnen worden verbonden._ Hoewel de afmetingen van advertenties ook in andere lijsten worden gedenormaliseerd, vertegenwoordigt dit het geadviseerde model om zich bij deze dimensies aan te sluiten.

_klik een beeld voor zijn full-size versie_

<table style="table-layout:auto">
 <tbody> 
  <tr> 
   <th>Gegevensmodel Data Warehouse</th>
   <th>Hiermee voegt u een dimensionaal gegevensmodel toe</th>
  </tr> 
  <tr> 
   <td><a href="assets/data-warehouse-data-model.pdf"><img src="assets/data-warehouse-data-model-thumb.png"></a></td>
   <td><a href="assets/ads-dimensional-data-model.pdf"><img src="assets/ads-dimensional-data-model-thumb.png"></a></td> 
  </tr> 
 </tbody> 
</table>

## Weergaven {#views}

### BIZ_ACCOUNTS {#biz-accounts}

Accounts die uit het bronsysteem zijn geïmporteerd.

<table>
  <tbody>
    <tr>
      <th><strong>Kolom</strong></th>
      <th><strong>Gegevenstype</strong></th>
      <th><strong>Beschrijving</strong></th>
      <th><strong>Voorbeeldgegevens</strong></th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>De account-id van het bronsysteem.</td>
      <td>0013100001kpAZxAAM</td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De aanmaakdatum van de account, vanaf het bronsysteem.</td>
      <td>2016-08-28 00 :32: 55.000</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De laatste gewijzigde datum van de account, van het bronsysteem.</td>
      <td>2018-08-01 17 :38: 30.000</td>
    </tr>
    <tr>
      <td>NAAM</td>
      <td>varchar</td>
      <td>De accountnaam van het bronsysteem.</td>
      <td>[!DNL Marketo Measure]</td>
    </tr>
    <tr>
      <td>WEB_SITE</td>
      <td>varchar</td>
      <td>Website voor de Rekening, zoals geregistreerd in het bronsysteem, die voor Lood aan afbeelding van de Rekening wordt gebruikt.</td>
      <td>www.adobe.com</td>
    </tr>
    <tr>
      <td>ENGAGEMENT_RATING</td>
      <td>varchar</td>
      <td>A letter grade (A, B, C, D, N/A), dat wordt gegenereerd op basis van het [!DNL Marketo Measure] Machine Learning-model. Dit is null als ABM is uitgeschakeld.</td>
      <td>B</td>
    </tr>
    <tr>
      <td>ENGAGEMENT_SCORE</td>
      <td>nummer (38,19)</td>
      <td>Een numerieke score die wordt berekend door [!DNL Marketo Measure] Machine Learning om de Predictive Engagement Score (Engagement_Rating) te genereren. Dit is null als ABM is uitgeschakeld.</td>
      <td>0,1417350147058800000</td>
    </tr>
    <tr>
      <td>DOMEIN</td>
      <td>varchar</td>
      <td>De geparseerde versie van de website, waarbij alleen het domein wordt opgeslagen.</td>
      <td>adobe</td>
    </tr>
    <tr>
      <td>IS_DELETED</td>
      <td>boolean</td>
      <td>Of de record al dan niet wordt verwijderd in het bronsysteem.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>CUSTOM_PROPERTIES</td>
      <td>varchar</td>
      <td>Aangepaste eigenschappen die [!DNL Marketo Measure] uit het bronsysteem heeft geïmporteerd, in JSON-indeling.</td>
      <td>{"Account_Type__c": "Security", "foo":"Bar"}</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td><b>*</b> INDUSTRIE</td>
      <td>varchar</td>
      <td>Primaire bedrijfsvoering van de account.</td>
      <td>Detailhandel, telecommunicatie</td>
    </tr>
    <tr>
      <td><b>*</b> LAND</td>
      <td>varchar</td>
      <td>Landgedeelte van het adres van de account.</td>
      <td>VS, Canada</td>
    </tr>
  </tbody>
</table>
<p>
<b> * </b> <i> slechts beschikbaar in Marketo Measure Ultimate </i>
<p>

### BIZ_ACCOUNT_TO_EMAILS {#biz-account-to-emails}

Toewijzingstabel tussen bekende e-mailadressen en accounts van leads/contactpersonen. Deze tabel is leeg als ABM is uitgeschakeld.

<table>
  <tbody>
    <tr>
    <th><strong>Kolom</strong></th>
      <th><strong>Gegevenstype</strong></th>
      <th><strong>Beschrijving</strong></th>
      <th><strong>Voorbeeldgegevens</strong></th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>Een unieke id voor de record.</td>
      <td>0013800001MMPPiAAP_person@adobe.com|2022-01-05 17 :22: 13.000</td>
    </tr>
    <tr>
      <td>ACCOUNT_ID</td>
      <td>varchar</td>
      <td>Source-systeemaccount-id.</td>
      <td>001310001phrBAAAY</td>
    </tr>
    <tr>
      <td>EMAIL</td>
      <td>varchar</td>
      <td>E-mailadres dat aan de account is toegewezen, via Contactpersoon of Toewijzing van account.</td>
      <td>person@adobe.com</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De laatste gewijzigde datum van de account, van het bronsysteem.</td>
      <td>2018-08-31 23 :53: 39.000</td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De aanmaakdatum van de account, vanaf het bronsysteem.</td>
      <td>2018-08-18 22 :01: 32.000</td>
    </tr>
    <tr>
      <td>IS_DELETED</td>
      <td>boolean</td>
      <td>Of de record wordt beschouwd als verwijderd.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_ACTIVITEITEN {#biz-activities}

Activiteiten die zijn geïmporteerd uit een bronsysteem of een aangesloten advertentiekader.

<table>
  <tbody>
  <tr>
    <th><strong>Kolom</strong></th>
    <th><strong>Gegevenstype</strong></th>
    <th><strong>Beschrijving</strong></th>
    <th><strong>Voorbeeldgegevens</strong></th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>De activiteit-id van het bronsysteem.</td>
      <td>1678625515</td>
    </tr>
    <tr>
      <td>LEAD_ID</td>
      <td>varchar</td>
      <td>Id voor de lead die aan de activiteit is gekoppeld.</td>
      <td>15530482</td>
    </tr>
    <tr>
      <td>CONTACT_ID</td>
      <td>varchar</td>
      <td>Id voor de contactpersoon die aan de activiteit is gekoppeld.
      </td>
      <td>13792552</td>
    </tr>
    <tr>
      <td>ACTIVITY_TYPE_ID</td>
      <td>varchar</td>
      <td>Id voor het Type van Activiteit, van het bronsysteem.</td>
      <td>104</td>
    </tr>
    <tr>
      <td>ACTIVITY_TYPE_NAME</td>
      <td>varchar</td>
      <td>De naam van de Activiteit, van het bronsysteem.</td>
      <td>
        <p>status van progressie wijzigen</p>
      </td>
    </tr>
    <tr>
      <td>START_DATE</td>
      <td>timestamp_ntz</td>
      <td>Begindatum van de activiteit, vanaf het bronsysteem.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>END_DATE</td>
      <td>timestapm_ntz</td>
      <td>Einddatum van de activiteit, vanaf het bronsysteem.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>CAMPAIGN_ID</td>
      <td>varchar</td>
      <td>Id voor de Campagne is de Activiteit een deel van, van het bronsysteem.</td>
      <td>
        <p>li.508038570,147643566</p>
      </td>
    </tr>
    <tr>
      <td>SOURCE_SYSTEM</td>
      <td>varchar</td>
      <td>Identificeert het type bronsysteem.</td>
      <td>Marketo</td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de rij is gemaakt in het bronsysteem.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum waarop de rij voor het laatst is gewijzigd in het bronsysteem.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>IS_DELETED</td>
      <td>boolean</td>
      <td>Of de record wordt beschouwd als verwijderd in het bronsysteem.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>AD_FORM_ID</td>
      <td>varchar</td>
      <td>Id voor het advertentieformulier waarvan de activiteit deel uitmaakt, van het bronsysteem.</td>
      <td>li.507063119,3757704</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_ADS {#biz-ads}

Advertenties die zijn geïmporteerd van een verbonden advertentieaccount.

<table>
  <tbody>
    <tr>
      <th><strong>Kolom</strong></th>
      <th><strong>Gegevenstype</strong></th>
      <th><strong>Beschrijving</strong></th>
      <th><strong>Voorbeeldgegevens</strong></th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>Een unieke id voor de advertentie.</td>
      <td>fb.106851586409075.605204428804.6052044290004.6053457 66804</td>
    </tr>
    <tr>
      <td>DISPLAY_ID</td>
      <td>varchar</td>
      <td>Advertentie ID van het bronsysteem.</td>
      <td>6053457066804</td>
    </tr>
    <tr>
      <td>AD_ACCOUNT_UNIQUE_ID</td>
      <td>varchar</td>
      <td>Id voor de advertentieaccount waaruit de advertentie is geïmporteerd.</td>
      <td>fb.106851586409075</td>
    </tr>
    <tr>
      <td>AD_ACCOUNT_NAME</td>
      <td>varchar</td>
      <td>Naam van de advertentierekening waaruit de advertentie is geïmporteerd.</td>
      <td>[!DNL Marketo Measure] Account</td>
    </tr>
    <tr>
      <td>ADVERTISER_UNIQUE_ID</td>
      <td>varchar</td>
      <td>Id van Advertiser voor Advertentie, specifiek voor Doubleclick.</td>
      <td>300181641</td>
    </tr>
    <tr>
      <td>ADVERTISER_NAME</td>
      <td>varchar</td>
      <td>Naam van Advertiser voor Advertentie, specifiek voor Doubleclick.</td>
      <td>Marketinganalyses</td>
    </tr>
    <tr>
      <td>AD_GROUP_UNIQUE_ID</td>
      <td>varchar</td>
      <td>Id van Advertentiegroep voor Advertentie.</td>
      <td>fb.106851586409075.605204428804.6052044290004</td>
    </tr>
    <tr>
      <td>AD_GROUP_NAME</td>
      <td>varchar</td>
      <td>Naam van de Advertentiegroep voor Advertentie.</td>
      <td>Advertentieset voor advertentie B</td>
    </tr>
    <tr>
      <td>AD_CAMPAIGN_UNIQUE_ID</td>
      <td>varchar</td>
      <td>Id van campagne voor advertentie.</td>
      <td>fb.106851586409075,6052044288804</td>
    </tr>
    <tr>
      <td>AD_CAMPAIGN_NAME</td>
      <td>varchar</td>
      <td>Naam van de campagne voor de advertentie.</td>
      <td>Campagne voor het genereren van leads</td>
    </tr>
    <tr>
      <td>IS_ACTIVE</td>
      <td>boolean</td>
      <td>Of de advertentie al dan niet nog actief is in het bronsysteem.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>IS_DELETED</td>
      <td>boolean</td>
      <td>Of de advertentie al dan niet is verwijderd in het bronsysteem.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst is gewijzigd.</td>
      <td>2018-08-02 06 :35: 59.000</td>
    </tr>
    <tr>
      <td>FIRST_IMPORTED</td>
      <td>timestamp_ntz</td>
      <td>Datum waarop de record voor het eerst uit het bronsysteem is geïmporteerd.</td>
      <td>2018-08-02 06 :35: 59.000</td>
    </tr>
    <tr>
      <td>NAAM</td>
      <td>varchar</td>
      <td>Naam van de Advertentie, van het bronsysteem.</td>
      <td>2 AD</td>
    </tr>
    <tr>
      <td>NEEDS_UPDATE</td>
      <td>boolean</td>
      <td>Of de advertentie moet worden bijgewerkt voor [!DNL Marketo Measure] tagging.
      <p>(Diagnostisch veld, wordt gebruikt door interne verwerking.)
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>GROUPING_KEY</td>
      <td>varchar</td>
      <td>Diagnostisch veld voor interne verwerking.</td>
      <td>fb.106851586409075.605204428804.6052044290004</td>
    </tr>
    <tr>
      <td>ENTITY_TYPE</td>
      <td>varchar</td>
      <td>Het hoofdobject of de entiteit voor deze tabel. In dit geval, "Ad".</td>
      <td>Advertentie</td>
    </tr>
    <tr>
      <td>PROVIDER_TYPE</td>
      <td>varchar</td>
      <td>Naam van de advertentieprovider voor de advertentie.</td>
      <td>Facebook</td>
    </tr>
    <tr>
      <td>URL_CURRENT</td>
      <td>varchar</td>
      <td>De URL voor de landingspagina.
        <p>(Diagnostisch veld, voor interne verwerking.)
      </td>
      <td></td>
    </tr>
    <tr>
      <td>URL_OLD</td>
      <td>varchar</td>
      <td>Vorige waarde voor URL_CURRENT.
      <p>(Diagnostisch veld, voor interne verwerking.)
      </td>
      <td></td>
    </tr>
    <tr>
      <td>URL_REQUESTED</td>
      <td>varchar</td>
      <td>Wat de URL zal worden versierd met [!DNL Marketo Measure] parameters.
      <p>(Diagnostisch veld, voor interne verwerking.)
      </td>
      <td></td>
    </tr>
    <tr>
      <td>URL_ALTENATIVES</td>
      <td>varchar</td>
      <td>Geïmporteerd uit het bronsysteem.
      <p>(Diagnostisch veld, voor interne verwerking.)
      </td>
      <td></td>
    </tr>
    <tr>
      <td>ROW_KEY</td>
      <td>getal (38,0)</td>
      <td>Foreign Key to the Biz_Facts view.</td>
      <td>6008900572523230000</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_ADVERTISERS {#biz-advertisers}

Adverteerders die zijn geïmporteerd uit een verbonden advertentieaccount.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>Een unieke id voor de adverteerder.</td>
      <td>dc.6114,9143143</td>
    </tr>
    <tr>
      <td>DISPLAY_ID</td>
      <td>varchar</td>
      <td>De advertentie-id van het bronsysteem.</td>
      <td>9143143</td>
    </tr>
    <tr>
      <td>AD_ACCOUNT_UNIQUE_ID</td>
      <td>varchar</td>
      <td>Id voor de advertentieaccount waaruit de advertentie is geïmporteerd.</td>
      <td>fb.106851586409075</td>
    </tr>
    <tr>
      <td>AD_ACCOUNT_NAME</td>
      <td>varchar</td>
      <td>Naam van de advertentierekening waaruit de advertentie is geïmporteerd.</td>
      <td>[!DNL Marketo Measure] Account</td>
    </tr>
    <tr>
      <td>ADVERTISER_UNIQUE_ID</td>
      <td>varchar</td>
      <td>Id van de Adverteerder, met name voor Doubleclick.</td>
      <td>300181641</td>
    </tr>
    <tr>
      <td>ADVERTISER_NAME</td>
      <td>varchar</td>
      <td>Naam van de adverteerder, met name voor Doubleclick.</td>
      <td>[!DNL Marketo Measure] Marketinganalyses</td>
    </tr>
    <tr>
      <td>AD_GROUP_UNIQUE_ID</td>
      <td>varchar</td>
      <td>Null verwacht omdat er geen Advertentiegroep is boven de Advertiser in een advertentiehiërarchie.</td>
      <td>null</td>
    </tr>
    <tr>
      <td>AD_GROUP_NAME</td>
      <td>varchar</td>
      <td>Null verwacht omdat er geen Advertentiegroep is boven de Advertiser in een advertentiehiërarchie.</td>
      <td>null</td>
    </tr>
    <tr>
      <td>AD_CAMPAIGN_UNIQUE_ID</td>
      <td>varchar</td>
      <td>Null verwacht omdat er geen advertentiecampagne boven de adverteerder in een advertentiehiërarchie is.</td>
      <td>null</td>
    </tr>
    <tr>
      <td>AD_CAMPAIGN_NAME</td>
      <td>varchar</td>
      <td>Null verwacht omdat er geen campagne boven Advertiser in een advertentiehiërarchie is.</td>
      <td>null</td>
    </tr>
    <tr>
      <td>IS_ACTIVE</td>
      <td>boolean</td>
      <td>Of de Advertiser al dan niet nog actief is in het bronsysteem.</td>
      <td>true</td>
    </tr>
    <tr>
      <td>IS_DELETED</td>
      <td>boolean</td>
      <td>Of de Advertiser al dan niet in het bronsysteem is verwijderd.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst is gewijzigd.</td>
      <td>2018-08-02 06 :35: 59.000</td>
    </tr>
    <tr>
      <td>FIRST_IMPORTED</td>
      <td>timestamp_ntz</td>
      <td>Datum waarop de record voor het eerst uit het bronsysteem is geïmporteerd.</td>
      <td>2018-08-02 06 :35: 59.000</td>
    </tr>
    <tr>
      <td>NAAM</td>
      <td>varchar</td>
      <td>Naam van de Advertiser, van het bronsysteem.</td>
      <td>[!DNL Marketo Measure] Marketinganalyses</td>
    </tr>
    <tr>
      <td>NEEDS_UPDATE</td>
      <td>boolean</td>
      <td>Of de Advertiser moet worden bijgewerkt voor [!DNL Marketo Measure] tagging.
      <p>(Diagnostisch veld, wordt gebruikt door interne verwerking.)
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>GROUPING_KEY</td>
      <td>varchar</td>
      <td>Diagnostisch veld voor interne verwerking.</td>
      <td></td>
    </tr>
    <tr>
      <td>ENTITY_TYPE</td>
      <td>varchar</td>
      <td>Het hoofdobject of de entiteit voor deze tabel. In dit geval, "Advertiser".</td>
      <td>Adverteerder</td>
    </tr>
    <tr>
      <td>PROVIDER_TYPE</td>
      <td>varchar</td>
      <td>De advertentieprovider voor de adverteerder.</td>
      <td>Doubleclick</td>
    </tr>
    <tr>
      <td>ROW_KEY</td>
      <td>getal (38,0)</td>
      <td>Foreign Key to the Biz_Facts view.</td>
      <td>6008900572523230000</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_AD_ACCOUNTS {#biz-ad-accounts}

Advertentierekeningen die van om het even welk verbonden Advertentierekening worden ingevoerd.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Een unieke id voor de advertentieaccount.</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td>De accountid toevoegen van het bronsysteem.</td>
      <td>
        <p>6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>Er wordt een null-waarde verwacht omdat dit de record is voor de advertentierekeningen in de hiërarchie van advertenties.</td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>Er wordt een null-waarde verwacht omdat dit de record is voor de advertentierekeningen in de hiërarchie van advertenties.</td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Null verwacht omdat er geen adverteerder is boven de advertentierapporten in een advertentiehiërarchie.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Null verwacht omdat er geen adverteerder is boven de advertentierapporten in een advertentiehiërarchie.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Null verwacht omdat er geen Advertentiegroep is boven Advertentierekeningen in om het even welke advertentiehiërarchie.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Null verwacht omdat er geen Advertentiegroep is boven Advertentierekeningen in om het even welke advertentiehiërarchie.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Null verwacht omdat er geen advertentiecampagne is boven de advertentierekeningen in een advertentiehiërarchie.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Null verwacht omdat er geen advertentiecampagne is boven de advertentierekeningen in een advertentiehiërarchie.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Geeft aan of de advertentieaccount nog actief is in het bronsysteem.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Hiermee wordt aangegeven of de advertentieaccount is verwijderd uit het bronsysteem.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de record voor het laatst is gewijzigd.</p>
      </td>
      <td>
        <p>2018-09-06 12 :54: 37.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum waarop de record voor het eerst uit het bronsysteem is geïmporteerd.</p>
      </td>
      <td>
        <p>2018-08-02 06 :35: 58.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAAM</p>
      </td>
      <td>varchar</td>
      <td>Naam van de advertentierekening, van het bronsysteem.</td>
      <td>
        <p>[!DNL Marketo Measure] Advertentierekening</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of de Advertiser moet worden bijgewerkt voor [!DNL Marketo Measure] tagging.</p>
        <p>(Diagnostisch veld, wordt gebruikt door interne verwerking.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>varchar</td>
      <td>Diagnostisch veld voor interne verwerking.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het hoofdobject of de entiteit voor deze tabel. In dit geval "Account".</p>
      </td>
      <td>
        <p>Account</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De naam van de advertentieprovider voor de advertentierekening.</p>
      </td>
      <td>
        <p>AdWords</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_CURRENCY_UNIT</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De valutacode die voor de Advertentierekening, van het bronsysteem wordt gebruikt.</p>
      </td>
      <td>
        <p>USD</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COMPANY_ID</p>
      </td>
      <td>varchar</td>
      <td>Wordt gebruikt voor interne verwerking.</td>
      <td>1933789</td>
    </tr>
    <tr>
      <td>
        <p>SOURCE</p>
      </td>
      <td>varchar</td>
      <td>Geparseerd van URL van utm_source.</td>
      <td>
        <p>Sociaal</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MEDIUM</p>
      </td>
      <td>varchar</td>
      <td>Geparseerd van URL van utm_medium.</td>
      <td>
        <p>lisu07261601</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAST_30_DAYS_COST</p>
      </td>
      <td>
        <p>nummer (38,19)</p>
      </td>
      <td>
        <p>De hoeveelheid uitgaven die in de laatste 30 dagen is ingevoerd, alleen van toepassing op Advertentie-woorden.</p>
      </td>
      <td>
        <p>17260,000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAST_30_DAYS_IMPRESSIONS</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Het aantal indrukkingen van de laatste 30 dagen dat alleen van toepassing is op AdvertentieWords.</p>
      </td>
      <td>
        <p>730060</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAST_30_DAYS_CLICKS</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Het aantal klikken vanaf de laatste 30 dagen, alleen van toepassing op AdvertentieWords.</p>
      </td>
      <td>
        <p>3400</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAST_30_DAYS_CONVERSIONS</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Het aantal omzettingen dat is gemeld vanaf de laatste 30 dagen, alleen van toepassing op AdWords.</p>
      </td>
      <td>
        <p>180</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE</p>
      </td>
      <td>varchar</td>
      <td>Wordt gebruikt voor interne diagnose.</td>
      <td>
        <p>http://cdn.adobe.com/redir?lp={lpurl}&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_OLD</p>
      </td>
      <td>varchar</td>
      <td>Wordt gebruikt voor interne diagnose.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_REQUESTED</p>
      </td>
      <td>varchar</td>
      <td>Wordt gebruikt voor interne diagnose.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_APPLICAED</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De sjabloon voor bijhouden die op het niveau Advertentieaccount voor AdWords of Bing is toegevoegd voor het labelen van bestemmingspagina's.</p>
      </td>
      <td>
        <p>http://cdn.adobe.com/redir?lp={lpurl}&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Foreign Key to the Biz_Facts view.</p>
      </td>
      <td>
        <p>-4609512587744160000</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_AD_CAMPAIGNS {#biz-ad-campaigns}

Campagnes die van verbonden Advertentierekeningen, bronsystemen, utm, en zelf worden ingevoerd die.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Unieke id voor de campagne.</p>
      </td>
      <td>
        <p>aw.6601259029.285114995</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td>De campagne-id van het bronsysteem.</td>
      <td>
        <p>285114995</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id voor de advertentierekening waaruit de Campagne werd ingevoerd.</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam voor de advertentierekening waaruit de Campagne werd ingevoerd.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van Advertiser voor de Campagne, specifiek voor Doubleclick.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de Advertiser voor de Campagne, specifiek voor Doubleclick.</p>
      </td>
      <td>
        <p>Marketinganalyses</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Null verwacht omdat er geen Advertentiegroep boven de Campagne in om het even welke advertentiehiërarchie is.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Null verwacht omdat er geen Advertentiegroep boven de Campagne in om het even welke advertentiehiërarchie is.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Unieke ID voor de campagne, gebruik in plaats daarvan het gebied van Id.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Gebruik in plaats daarvan de naam van de campagne in het veld Naam.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of de campagne al dan niet nog actief is in het bronsysteem.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of de Campagne al dan niet in het bronsysteem is geschrapt.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de record voor het laatst is gewijzigd.</p>
      </td>
      <td>
        <p>2018-08-02 06 :35: 58.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum waarop de record voor het eerst uit het bronsysteem is geïmporteerd.</p>
      </td>
      <td>
        <p>2018-08-02 06 :35: 58.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAAM</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de campagne.</p>
      </td>
      <td>
        <p>Opnieuw toewijzen van partners</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of de campagne moet worden bijgewerkt voor [!DNL Marketo Measure] tagging.</p>
        <p>(Diagnostisch veld, wordt gebruikt door interne verwerking.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>varchar</td>
      <td>Diagnostisch veld voor interne verwerking.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het hoofdobject of de entiteit voor deze tabel. In dit geval, "Campaign".</p>
      </td>
      <td>
        <p>Campaign</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de advertentieprovider voor de campagne.</p>
      </td>
      <td>
        <p>AdWords</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DAILY_BUDGET</p>
      </td>
      <td>
        <p>nummer (38,19)</p>
      </td>
      <td>
        <p>De dagelijkse begroting die is vastgelegd in het advertentieplatform voor de campagne.</p>
      </td>
      <td>
        <p>0,0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE</p>
      </td>
      <td>varchar</td>
      <td>Wordt gebruikt voor interne diagnose.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_OLD</p>
      </td>
      <td>varchar</td>
      <td>Wordt gebruikt voor interne diagnose.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_REQUESTED</p>
      </td>
      <td>varchar</td>
      <td>Wordt gebruikt voor interne diagnose.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_APPLICAED</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De sjabloon voor tekstspatiëring die op campagnereniveau is toegevoegd voor AdWords of Bing voor het labelen van bestemmingspagina's.</p>
      </td>
      <td>
        <p>http://cdn.adobe.com/redir?lp={lpurl}&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Foreign Key to the Biz_Facts view.</p>
      </td>
      <td>
        <p>-6008900572523230000</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_AD_FORMS {#biz-ad-forms}

Advertentie Forms geïmporteerd van een verbonden advertentierekening.

<table>
  <tr>
    <th>
      <p>Kolom</p>
    </th>
    <th>
      <p>Gegevenstype</p>
    </th>
    <th>
      <p>Beschrijving</p>
    </th>
    <th>
      <p>Voorbeeldgegevens</p>
    </th>
  </tr>
  <tbody>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Een unieke id voor het advertentieformulier.</p>
      </td>
      <td>
        <p>li.507063119,3757704</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id voor de advertentieaccount waaruit het advertentieformulier is geïmporteerd.</p>
      </td>
      <td>
        <p>li,507063119</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de advertentierekening waaruit het Advertentieformulier werd ingevoerd.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Status is verwijderd uit het bronsysteem. Instellen op verwijderen als de status Laag, Gearchiveerd of Geannuleerd is.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de record voor het laatst is gewijzigd.</p>
      </td>
      <td>
        <p>2018-08-02 06 :35: 58.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum waarop de record voor het eerst uit het bronsysteem is geïmporteerd.</p>
      </td>
      <td>
        <p>2018-08-02 06 :35: 58.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAAM</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van het advertentieformulier.</p>
      </td>
      <td>
        <p>NSPA Ebook LGF (mei 2020)</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het hoofdobject of de entiteit voor deze tabel. In dit geval, "AdForm".</p>
      </td>
      <td>
        <p>AdForm</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de advertentieprovider voor het advertentieformulier.</p>
      </td>
      <td>
        <p>LinkedIn</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BESCHRIJVING</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Beschrijving van het ADF-formulier.</p>
      </td>
      <td>
        <p>Leer hoe intelligente automatisering procesefficiency in hypotheekherfinancieringstoepassingen kan verhogen.</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>HEADLINE</p>
      </td>
      <td>varchar</td>
      <td>Titel van het advertentievorm.</td>
      <td>
        <p>Het is tijd om het herfinancieringsproces te automatiseren</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LANDING_URL</p>
      </td>
      <td>varchar</td>
      <td>De landings URL van de Advertentie Vorm.</td>
      <td>
        <p>https://adobe.com/blog/refinancing-application-process/</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>VRAGEN</p>
      </td>
      <td>varchar</td>
      <td>Lijst met vragen voor het advertentieformulier.</td>
      <td>
        <p>voornaam:achternaam:e-mailadres:Land/regio:functie, titel:Bedrijfsnaam</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>STATUS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Status van het advertentieformulier.</p>
      </td>
      <td>
        <p>ingediend</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>SOURCE_ID</td>
      <td>varchar</td>
      <td>Id voor de Source waarvan de record afkomstig is.</td>
      <td>aw.3284209</td>
    </tr>
  </tbody>
</table>

### BIZ_AD_GROUPS {#biz-ad-groups}

Groepen toevoegen die zijn geïmporteerd uit een gekoppeld advertentieaccount.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Een unieke id voor de advertentiegroep.</p>
      </td>
      <td>
        <p>aw.6601259029.317737955.23105326115</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td>De Advertentiegroep ID van het bronsysteem.</td>
      <td>
        <p>23105326115</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id voor de advertentieaccount waaruit de advertentiegroep is geïmporteerd.</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam voor de advertentierekening waaruit de Advertentiegroep werd ingevoerd.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Er wordt een null-waarde verwacht omdat de hiërarchie voor dubbelklikken geen Advertentiegroep bevat.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Er wordt een null-waarde verwacht omdat de hiërarchie voor dubbelklikken geen Advertentiegroep bevat.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Null verwacht omdat dit de record is voor de advertentiegroep in de hiërarchie.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Null verwacht omdat dit de record is voor de advertentiegroep in de hiërarchie.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de campagne voor de advertentiegroep.</p>
      </td>
      <td>
        <p>aw.6601259029.317737955</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de campagne voor de advertentiegroep.</p>
      </td>
      <td>
        <p>Belastingkenmerk</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Geeft aan of de advertentieaccount nog actief is in het bronsysteem.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Hiermee wordt aangegeven of de advertentieaccount is verwijderd uit het bronsysteem.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de record voor het laatst is gewijzigd.</p>
      </td>
      <td>
        <p>2018-08-02 06 :36: 14.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum waarop de record voor het eerst uit het bronsysteem is geïmporteerd.</p>
      </td>
      <td>
        <p>2018-08-02 06 :36: 14.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAAM</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de advertentiegroep.</p>
      </td>
      <td>
        <p>Belastingkenmerk - Op rekening gebaseerd</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of de Advertiser moet worden bijgewerkt voor [!DNL Marketo Measure] tagging.</p>
        <p>(Diagnostisch veld, wordt gebruikt door interne verwerking.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>varchar</td>
      <td>Diagnostisch veld voor interne verwerking.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het hoofdobject of de entiteit voor deze tabel. In dit geval, "AdGroup".</p>
      </td>
      <td>
        <p>AdGroup</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de advertentieprovider voor de advertentiegroep.</p>
      </td>
      <td>
        <p>AdWords</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_NETWORK_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het medium waarop de advertentiegroep wordt uitgevoerd.</p>
      </td>
      <td>
        <p>Zoeken, weergeven, YouTube_Zoeken, YouTube_controleren</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE</p>
      </td>
      <td>varchar</td>
      <td>Wordt gebruikt voor interne diagnose.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_OLD</p>
      </td>
      <td>varchar</td>
      <td>Wordt gebruikt voor interne diagnose.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_REQUESTED</p>
      </td>
      <td>varchar</td>
      <td>Wordt gebruikt voor interne diagnose.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_APPLICAED</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De sjabloon voor bijhouden die op het niveau Advertentieaccount voor AdWords of Bing is toegevoegd voor het labelen van bestemmingspagina's.</p>
      </td>
      <td>
        <p>http://cdn.adobe.com/redir?lp={lpurl}&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Foreign Key to the Biz_Facts view.</p>
      </td>
      <td>
        <p>-5594512713562690000</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_AD_PROVIDERS

<p>Aanbieders toevoegen vanaf een verbonden advertentierekening, inclusief een vermelding voor zelf gerapporteerd indien van toepassing.</p>

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Een unieke id voor de advertentieprovider.</p>
      </td>
      <td>
        <p>Bing</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAAM</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de advertentieprovider.</p>
      </td>
      <td>
        <p>Bing</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Foreign Key to the Biz_Facts view.</p>
      </td>
      <td>
        <p>4783788151269206864</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_ATTRIBUTION_TOUCHPOINTS {#biz-attribution-touchpoints}

<p>Aanraakpunten voor koperkenmerken, alle aanraakpunten die aan een opportunity zijn gekoppeld.</p>
<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Een unieke id voor de Buyer Attribution Touchpoint (BAT).</p>
      </td>
      <td>
        <p>BAT2_0060Z00000lFHtOQAW_</p>
        <p>0030Z0003K5bpKQAR_2017-06-20:01-05-20-619330.0b5c5678807c</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de record voor het laatst is gewijzigd.</p>
      </td>
      <td>
        <p>2018-09-01 04 :53: 53.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>OPPORTUNITY_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id voor de opportuniteit waaraan de BAT is toegewezen.</p>
      </td>
      <td>
        <p>0060Z00000lFHtOQAW</p>
      </td>
    </tr>
    <tr>
      <td>CONTACT_ID</td>
      <td>varchar</td>
      <td>
        <p>Id voor de contactpersoon die aan de BAT is gekoppeld.</p>
      </td>
      <td>
        <p>0030Z0003K5bpKQAR</p>
      </td>
    </tr>
    <tr>
      <td>EMAIL</td>
      <td>varchar</td>
      <td>E-mailadres dat aan de BAT is gekoppeld.</td>
      <td>person@adobe.com</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id voor de account waaraan de BAT is toegewezen.</p>
      </td>
      <td>
        <p>0013100001otbIAAAY</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>USER_TOUCHPOINT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id voor het aanraakpunt van de gebruiker dat de BAT heeft gegenereerd.</p>
      </td>
      <td>
        <p>person@adobe.com_00v1B00003ZbWzHQAV</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TOUCHPOINT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum van het aanraakpunt.</p>
      </td>
      <td>
        <p>2017-06-20 01 :05: 20.000</p>
      </td>
    </tr>
    <tr>
      <td>VISITOR_ID</td>
      <td>varchar</td>
      <td>Id voor de bezoeker die aan de BAT is gekoppeld.</td>
      <td>v_277d79d01678498fea067c9b631bf6df</td>
    </tr>
    <tr>
      <td>
        <p>MARKETING_TOUCH_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het type van activiteit, het Bezoek van het Web, de Vorm van het Web, het Praatje van het Web, de Vraag van de Telefoon, [CRM] Campagne, of [CRM] Activiteit. Wordt in de CRM aangeduid als "aanraakpunttype".</p>
      </td>
      <td>
        <p>Webformulier</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KANAAL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het kanaal waarin het aanraakpunt valt, zoals gedefinieerd in de aangepaste kanaaldefinities in de app [!DNL Marketo Measure] . Wordt in de CRM aangeduid als "Marketing Channel - Path".</p>
      </td>
      <td>
        <p>Social.LinkedIn</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE1</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De segmentwaarde voor de eerste categorie waarin het aanraakpunt valt, zoals gedefinieerd in de segmentdefinities in de [!DNL Marketo Measure] -app. In de CRM aangeduid als "Segmenten".</p>
      </td>
      <td>
        <p>ABC</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE2</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De segmentwaarde voor de tweede categorie waarin het aanraakpunt valt, zoals gedefinieerd in de segmentdefinities in de [!DNL Marketo Measure] -app. In de CRM aangeduid als "Segmenten".</p>
      </td>
      <td>
        <p>Ja</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE3</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De segmentwaarde voor de derde categorie waarin het aanraakpunt valt, zoals gedefinieerd in de segmentdefinities in de [!DNL Marketo Measure] -app. In de CRM aangeduid als "Segmenten".</p>
      </td>
      <td>
        <p>SMB</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE4</p>
      </td>
      <td>varchar</td>
      <td>De segmentwaarde voor de vierde categorie waarin het aanraakpunt valt, zoals gedefinieerd in de segmentdefinities in de [!DNL Marketo Measure] -app. In de CRM aangeduid als "Segmenten".</td>
      <td>
        <p>Nieuwe bedrijven</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE5</p>
      </td>
      <td>varchar</td>
      <td>De segmentwaarde voor de vijfde categorie waarin het aanraakpunt valt, zoals gedefinieerd in de segmentdefinities in de [!DNL Marketo Measure] -app. In de CRM aangeduid als "Segmenten".</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE6</p>
      </td>
      <td>varchar</td>
      <td>De segmentwaarde voor de zesde categorie waarin het aanraakpunt valt, zoals gedefinieerd in de segmentdefinities in de [!DNL Marketo Measure] -app. In de CRM aangeduid als "Segmenten".</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE7</p>
      </td>
      <td>varchar</td>
      <td>De segmentwaarde voor de zevende categorie waarin het aanraakpunt valt, zoals gedefinieerd in de segmentdefinities in de [!DNL Marketo Measure] -app. In de CRM aangeduid als "Segmenten".</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE8</p>
      </td>
      <td>varchar</td>
      <td>De segmentwaarde voor de achtste categorie waarin het aanraakpunt valt, zoals gedefinieerd in de segmentdefinities in de [!DNL Marketo Measure] -app. In de CRM aangeduid als "Segmenten".</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE9</p>
      </td>
      <td>varchar</td>
      <td>De segmentwaarde voor de 9de categorie waarin het aanraakpunt valt, zoals gedefinieerd in de segmentdefinities in de [!DNL Marketo Measure] -app. In de CRM aangeduid als "Segmenten".</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE10</p>
      </td>
      <td>varchar</td>
      <td>De segmentwaarde voor de tiende categorie waarin het aanraakpunt valt, zoals gedefinieerd in de segmentdefinities in de [!DNL Marketo Measure] -app. In de CRM aangeduid als "Segmenten".</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE11</p>
      </td>
      <td>varchar</td>
      <td>De segmentwaarde voor de 11e categorie waarin het aanraakpunt valt, zoals gedefinieerd in de segmentdefinities in de [!DNL Marketo Measure] -app. In de CRM aangeduid als "Segmenten".</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE12</p>
      </td>
      <td>varchar</td>
      <td>De segmentwaarde voor de 12e categorie waarin het aanraakpunt valt, zoals gedefinieerd in de segmentdefinities in de [!DNL Marketo Measure] -app. In de CRM aangeduid als "Segmenten".</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE13</p>
      </td>
      <td>varchar</td>
      <td>De segmentwaarde voor de dertiende categorie waarin het aanraakpunt valt, zoals gedefinieerd in de segmentdefinities in de [!DNL Marketo Measure] -app. In de CRM aangeduid als "Segmenten".</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE14</p>
      </td>
      <td>varchar</td>
      <td>De segmentwaarde voor de 14e categorie waarin het aanraakpunt valt, zoals gedefinieerd in de segmentdefinities in de [!DNL Marketo Measure] -app. In de CRM aangeduid als "Segmenten".</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE15</p>
      </td>
      <td>varchar</td>
      <td>De segmentwaarde voor de 15e categorie waarin het aanraakpunt valt, zoals gedefinieerd in de segmentdefinities in de [!DNL Marketo Measure] -app. In de CRM aangeduid als "Segmenten".</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>BROWSER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Van javascript en IP adres, ontdekte browser dat de gebruiker tijdens de zitting was.</p>
      </td>
      <td>
        <p>Chrome</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BROWSER_VERSION</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Van javascript en IP adres, de ontdekte versie van browser die de gebruiker tijdens de zitting was.</p>
      </td>
      <td>
        <p>58</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLATFORM_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Van javascript en IP adres, het ontdekte platform dat de gebruiker tijdens de zitting was.</p>
      </td>
      <td>
        <p>Mac</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLATFORM_VERSION</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Van javascript en IP adres, de ontdekte versie van het platform dat de gebruiker tijdens de zitting was.</p>
      </td>
      <td>
        <p>10_12</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LANDING_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De eerste openingspagina van de sessie die tot een aanraakpunt heeft geleid. Wordt in de CRM aangeduid als "Landing Page".</p>
      </td>
      <td>
        <p>http://www.adobe.com/blog/uncover- waar-achter-kosten-per-lood</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LANDING_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De eerste openingspagina van de sessie die tot een aanraakpunt heeft geleid. Een onbewerkte bestemmingspagina bevat alle queryparameters in de URL. In de CRM aangeduid als "Landing Page - Raw".</p>
      </td>
      <td>
        <p>http://www.adobe.com/blog/uncover-truth -behind-cost-per-lead?utm_content=27322869&amp;utm_ medium=social&amp;utm_source=linkedin</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Doorgaans de externe bestemmingspagina vlak voordat de gebruiker op de website komt. Wordt in de CRM aangeduid als "Referrer Page".</p>
      </td>
      <td>
        <p>https://www.linkedin.com/</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Doorgaans de externe bestemmingspagina vlak voordat de gebruiker op de website komt. Een onbewerkte verwijzingspagina kan queryparameters in de URL bevatten. Wordt in de CRM aangeduid als "Referrer Page - Raw".</p>
      </td>
      <td>
        <p>https://www.linkedin.com/</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het eerste formulier dat is opgenomen in een sessie en dat heeft geresulteerd in een aanraakpunt. Verdere formulierverzendingen worden niet weergegeven in de tabel Attribution_Touchpoints, maar in de tabel Form_Submits. Wordt in de CRM aangeduid als "formulier-URL".</p>
      </td>
      <td>
        <p>http://info.adobe.com/intro-guide-b2b-marketing-attribution</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het eerste formulier dat is opgenomen in een sessie en dat heeft geresulteerd in een aanraakpunt. Verdere formulierverzendingen worden niet weergegeven in de tabel Attribution_Touchpoints, maar in de tabel Form_Submits. Een onbewerkte formulierpagina kan queryparameters in de URL bevatten. Wordt in de CRM aangeduid als "Form URL - Raw".</p>
      </td>
      <td>
        <p>http://info.adobe.com/intro-guide-b2b-marketing-attribution</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop het formulier is verzonden.</p>
      </td>
      <td>
        <p>2017-06-20 01 :06: 41.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>STAD</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Van javascript en IP adres, de ontdekte plaats de gebruiker binnen tijdens de zitting was.</p>
      </td>
      <td>
        <p>San Francisco</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REGIO</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Van javascript en IP adres, het ontdekte gebied de gebruiker binnen tijdens de zitting was.</p>
      </td>
      <td>
        <p>California</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAND</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Van javascript en IP adres, het ontdekte land de gebruiker binnen tijdens de zitting was.</p>
      </td>
      <td>
        <p>Verenigde Staten</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MEDIUM</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Hiermee definieert u het medium dat tot het aanraakpunt heeft geleid. Dit kan worden geparseerd vanaf de URL vanaf utm_medium. Of als [!DNL Marketo Measure] een advertentie kan oplossen, kan het waarden zijn zoals "cpc" of "display".</p>
      </td>
      <td>
        <p>sociaal</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>WEB_SOURCE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Hiermee definieert u de bron die het aanraakpunt heeft veroorzaakt. Dit kan uit URL van utm_source worden ontleed, algemeen geplaatst als "Campaign van CRM"als het van CRM werd gesynchroniseerd, of als [!DNL Marketo Measure] een advertentie kan oplossen, kan het waarden zoals "Google AdWords"of "Facebook zijn." Wordt in de CRM aangeduid als "Touchpoint Source".</p>
      </td>
      <td>
        <p>gekoppeld</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SEARCH_PHRASE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De waarde die de gebruiker in de browser heeft ingevoerd om naar de website te zoeken en op de website is geëindigd. Afhankelijk van het trefwoord dat wordt gekocht, komt dit mogelijk wel of niet overeen met de trefwoorden die zijn aangeschaft op het platform Betaalde zoekopdracht.</p>
      </td>
      <td>
        <p>goochelaar [!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_PROVIDER</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Adplatform [!DNL Marketo Measure] kon oplossen van, typisch één van onze integratiepartners.</p>
      </td>
      <td>
        <p>Google</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van advertentierekening waarvan de advertentie is opgelost.</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de advertentierekening waaruit de advertentie is opgelost.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de adverteerder van de advertentierekening waarin de advertentie is opgelost. Dit geldt alleen voor Dubbelklik op Campagnebeheer.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de adverteerder van de advertentierekening waarin de advertentie is opgelost. Dit geldt alleen voor Dubbelklik op Campagnebeheer.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] Marketinganalyses</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de site van de advertentieaccount waaruit de advertentie is opgelost. Dit geldt alleen voor Dubbelklik op Campagnebeheer.</p>
      </td>
      <td>
        <p>1695651</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de site van de advertentierekening waaruit de advertentie is opgelost. Dit geldt alleen voor Dubbelklik op Campagnebeheer.</p>
      </td>
      <td>
        <p>Quora.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de Plaatsing van de Advertentierekening waarin de Advertentie van werd opgelost. Dit geldt alleen voor Dubbelklik op Campagnebeheer.</p>
      </td>
      <td>
        <p>120839827</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de Plaatsing van de Advertentierekening waarin de Advertentie van werd opgelost. Dit geldt alleen voor Dubbelklik op Campagnebeheer.</p>
      </td>
      <td>
        <p>wegblokkeren</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de campagne van de advertentierekening waar de Advertentie van werd opgelost.</p>
      </td>
      <td>
        <p>aw.6601259029.317738075</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de campagne van de advertentierekening waarin Advertentie werd opgelost van.</p>
      </td>
      <td>
        <p>Marketingkenmerk</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de Advertentiegroep van de Advertentierekening waarin de Advertentie van werd opgelost. Dit geldt alleen voor Google Adwords.</p>
      </td>
      <td>
        <p>aw.6601259029.317738075.23105327435</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de Advertentiegroep van de Advertentierekening waarin de Advertentie werd opgelost van. Dit geldt alleen voor Google AdWords.</p>
      </td>
      <td>
        <p>Marketing Attribution - General</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de advertentie van de advertentierekening waarin de advertentie is opgelost. Dit geldt voor Dubbelklik op Campagne Manager en Facebook (display).</p>
      </td>
      <td>
        <p>dc.6114.882972.25272734.492579576</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de advertentie van de advertentierekening waarin de advertentie is opgelost. Dit geldt voor Dubbelklik op Campagne Manager en Facebook (display).</p>
      </td>
      <td>
        <p>Webinar - zijbalk</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van Creative van de advertentie-account waaruit de advertentie is opgelost. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht).</p>
      </td>
      <td>
        <p>aw.6601259029.317738075.23105327435.182716179597</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De naam van de Creative vanuit het advertentieaccount waaruit de advertentie is opgelost. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht).</p>
      </td>
      <td>
        <p>B2B-marketingkenmerk</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_1</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De eerste regel van Creative van de zoekAdvertentie, getrokken uit de Advertentierekening waarin Advertentie werd opgelost van. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht).</p>
      </td>
      <td>
        <p>Download de Gids van GMOs</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_2</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De tweede regel van Creative van de zoekAdvertentie, getrokken uit de Advertentierekening waarin Advertentie werd opgelost van. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht).</p>
      </td>
      <td>
        <p>Leer hoe de toewijzing van ROI door marketing activiteiten aan opbrengst te verbinden</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESTINATION_URL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De landingspagina die door van de onderzoekAdvertentie klikt, die van de Advertentierekening wordt getrokken waarin Advertentie werd opgelost. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht).</p>
      </td>
      <td>
        <p>http://info.adobe.com/cmos-guide-to-b2b-marketing-attribution</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DISPLAY_URL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De vriendelijke URL-naam die wordt weergegeven in de zoekadvertentie en die wordt opgehaald van de advertentierekening waaruit de advertentie is opgelost. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht).</p>
      </td>
      <td>
        <p>http://info.adobe.com/CMOs-Guide</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De id van het trefwoord dat is aangeschaft bij de aankoop van de Betaalde zoekopdracht, is opgehaald van de advertentieaccount waarvan de advertentie is opgelost. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht).</p>
      </td>
      <td>
        <p>aw.6601259029.317738075.23105327435.4838421670</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van het trefwoord dat is aangeschaft bij de aankoop van de Betaalde zoekopdracht en dat is opgehaald van de advertentieaccount waarvan de advertentie is opgelost. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht)</p>
      </td>
      <td>
        <p>"marketingtoewijzing"</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_MATCH_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het type overeenkomst dat wordt gevonden tussen de zoekuitdrukking en het aangekochte trefwoord.</p>
      </td>
      <td>
        <p>Exact</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_FIRST_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of dit aanraakpunt al dan niet wordt beschouwd als de eerste aanraking van de opportuniteitsreis.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_LEAD_CREATION_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of dit aanraakpunt al dan niet wordt beschouwd als de belangrijkste aanzet tot de opportuniteitsreis.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_OPP_CREATION_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of dit aanraakpunt al dan niet wordt beschouwd als de kans om de opportuniteitsreis te creëren.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_CLOSED_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of dit aanraakpunt al dan niet wordt beschouwd als een gesloten aanraking van de opportuniteitsreis.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>STAGES_TOUCHED</p>
      </td>
      <td>varchar</td>
      <td>Dit veld is vervangen. Gebruik de tabellen Stage_Transitions voor werkgebiedinformatie.</td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>IS_FORM_SUBMISSION_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of dit aanraakpunt tijdens de sessie al dan niet een formuliervulling had.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_IMPRESSION_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of dit aanraakpunt al dan niet wordt beschouwd als de eerste indruk van de opportuniteitsreis</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_CLICK_PERCENTAGE</p>
      </td>
      <td>
        <p>nummer(22,19)</p>
      </td>
      <td>
        <p>Het berekende percentage dat aan dit aanraakpunt is toegewezen omdat het een eerste aanraking is (Zie Is_First_Touch).</p>
      </td>
      <td>
        <p>0,0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAST_ANON_CLICK_PERCENTAGE</p>
      </td>
      <td>
        <p>nummer(22,19)</p>
      </td>
      <td>
        <p>Het berekende percentage dat is toegewezen aan dit aanraakpunt, omdat het een aanraakaanraakaanraakaanraakvlak is (zie Is_Lead_Creation_Touch).</p>
      </td>
      <td>
        <p>0,0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>U_SHAPE_PERCENTAGE</p>
      </td>
      <td>
        <p>nummer(22,19)</p>
      </td>
      <td>
        <p>Het berekende percentage dat aan dit aanraakpunt is toegewezen omdat het deel uitmaakt van een u-vormige aanraking (zie Is_First_Touch en Is_Lead_Creation_Touch).</p>
      </td>
      <td>
        <p>0,0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>W_SHAPE_PERCENTAGE</p>
      </td>
      <td>
        <p>nummer(22,19)</p>
      </td>
      <td>
        <p>Het berekende percentage dat aan dit aanraakpunt is toegewezen omdat het deel uitmaakt van een w-vormige aanraking (zie Is_First_Touch, Is_Lead_Creation_Touch en Is_Opp_Creation_Touch).</p>
      </td>
      <td>
        <p>0,0153374234214425</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FULL_PATH_PERCENTAGE</p>
      </td>
      <td>
        <p>nummer(22,19)</p>
      </td>
      <td>
        <p>Het berekende percentage dat aan dit aanraakpunt wordt toegewezen omdat het deel uitmaakt van een volledig padmodel (zie Is_First_Touch, Is_Lead_Creation_Touch, Is_Opp_Creation_Touch, Is_Closed_Touch).</p>
      </td>
      <td>
        <p>0,0143061513081193</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CUSTOM_MODEL_PERCENTAGE</p>
      </td>
      <td>nummer(22,19)</td>
      <td>Het berekende percentage dat aan dit aanraakpunt wordt toegewezen omdat het deel uitmaakt van een aangepast model (zie Is_First_Touch, Is_Lead_Creation_Touch, Is_Opp_Creation_Touch, Is_Closed_Touch).</td>
      <td>0,0143061513081193</td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Hiermee wordt aangegeven of dit aanraakpunt wordt verwijderd.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Foreign Key to the Biz_Facts view.</p>
      </td>
      <td>
        <p>-2712935512233520000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MOPPORTUNITY_ROW_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>LANDING_PAGE_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>REFERRER_PAGE_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>FORM_PAGE_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ACCOUNT_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ADVERTISER_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>SITE_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_ROW_KEY</p>
      </td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CAMPAIGN_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_GROUP_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CREATIVE_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>KEYWORD_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_ATTRIBUTION_AI_TOUCHPOINTS {#biz-attribution-ai-touchpoints}

Gegevens die zijn gegenereerd door de Attribution AI-integratie. Deze velden worden alleen ingevuld voor Marketo Measure Ultimate-klanten.

<table>
<thead>
  <tr>
    <th>Kolom</th>
    <th>Gegevenstype</th>
    <th>Beschrijving</th>
    <th>Voorbeeldgegevens</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>CONVERSION_DATE</td>
    <td>Timestamp_ntz</td>
    <td>datum van omzetting</td>
    <td>2020-01-01 01 :01: 00.000</td>
  </tr>
  <tr>
    <td>CONVERSION_NAME</td>
    <td>varchar</td>
    <td>naam van de conversiegebeurtenis (zoals opgegeven door de klant in de UI-instelling)</td>
    <td> </td>
  </tr>
  <tr>
    <td>CONVERSION_ID</td>
    <td>varchar</td>
    <td>id voor de conversiegebeurtenis (dit is de oorspronkelijke unieke id-waarde die is verzonden met de record met gebeurtenisgegevens in de brondataset)</td>
    <td>001310001b44aGAAQ</td>
  </tr>
  <tr>
    <td>CONVERSION_EVENT_ID</td>
    <td>varchar</td>
    <td>original MM event id for the conversion event 
    <br> kaarten aan een gebruiker touchpoint of een werkgebiedovergang</td>
    <td>00U0Z0000pCZmyUAG</td>
  </tr>
  <tr>
    <td>CONVERSION_ACCOUNT_ID</td>
    <td>varchar</td>
    <td>original MM account id for the conversion event</td>
    <td>0013100001kpAZxAAM</td>
  </tr>
  <tr>
    <td>CONVERSION_OPPORTUNITY_ID</td>
    <td>varchar</td>
    <td>oorspronkelijke kansen-id voor de conversiegebeurtenis</td>
    <td>0060Z00000lFHtOQAW</td>
  </tr>
  <tr>
    <td>CONVERSION_LEAD_ID</td>
    <td>varchar</td>
    <td>originele identiteitskaart van de lood MM voor de omzettingsgebeurtenis <br> waarschijnlijk ongeldig zal zijn het grootste deel van de tijd</td>
    <td>00Q0Z000013dw4GUAQ</td>
  </tr>
  <tr>
    <td>CONVERSION_CONTACT_ID</td>
    <td>varchar</td>
    <td>oorspronkelijke MM-contactpersoon voor de conversiegebeurtenis
    <br> waarschijnlijk ongeldig zal zijn het grootste deel van de tijd</td>
    <td>00331000032hMxRAAU</td>
  </tr>
  <tr>
    <td>CONVERSION_EVENT_TYPE</td>
    <td>varchar</td>
    <td>type conversiegebeurtenis (b2b = lead conversie, b2c = opportuniteitsconversie)</td>
    <td>b2b</td>
  </tr>
  <tr>
    <td>SCORE_DATE</td>
    <td>Timestamp_ntz</td>
    <td>datum waarop de aanraakpunten voor het laatst zijn vermeld</td>
    <td>2020-01-01 01 :01: 00.000</td>
  </tr>
  <tr>
    <td>INFLUENCED_PERCENT</td>
    <td>nummer (38,35)</td>
    <td>het gedeelte van de conversie dat door elk aanraakpunt wordt veroorzaakt</td>
    <td>0,10</td>
  </tr>
  <tr>
    <td>INCREMENTAL_PERCENT</td>
    <td>nummer (38,35)</td>
    <td>de hoeveelheid marginale impact die rechtstreeks door een aanraakpunt wordt veroorzaakt</td>
    <td>0,25</td>
  </tr>
  <tr>
    <td>TOUCHPOINT_DATE</td>
    <td>Timestamp_ntz</td>
    <td>de datum van het aanraakpunt of de overgangsfase</td>
    <td>2020-01-01 01 :01: 00.000</td>
  </tr>
  <tr>
    <td>TOUCHPOINT_EVENT_ID</td>
    <td>varchar</td>
    <td>id voor de gebeurtenis die het aanraakpunt heeft gegenereerd</td>
    <td>00U3100000VLUnEEAX</td>
  </tr>
  <tr>
    <td>TOUCHPOINT_OPPORTUNITY_ID</td>
    <td>varchar</td>
    <td>id voor de kans die het aanraakpunt biedt</td>
    <td>0060Z00000lFHtOQAW</td>
  </tr>
  <tr>
    <td>TOUCHPOINT_ACCOUNT_ID</td>
    <td>varchar</td>
    <td>id voor de account die is gekoppeld aan het aanraakpunt</td>
    <td>0013100001kpAZxAAM</td>
  </tr>
  <tr>
    <td>TOUCHPOINT_LEAD_ID</td>
    <td>varchar</td>
    <td>id voor de lood die is gekoppeld aan het aanraakpunt</td>
    <td>00Q0Z000013dw4GUAQ</td>
  </tr>
  <tr>
    <td>TOUCHPOINT_CONTACT_ID</td>
    <td>varchar</td>
    <td>ID voor het contact verbonden met het touchpoint</td>
    <td>00331000032hMxRAAU</td>
  </tr>
  <tr>
    <td>COUNT_TO_CONVERSION</td>
    <td>getal (38,0)</td>
    <td>de rangorde of rangorde van het aanraakpunt in de keten die tot de conversiegebeurtenis leidt</td>
    <td>10000</td>
  </tr>
  <tr>
    <td>AAI_SOURCE_ID</td>
    <td>varchar</td>
    <td>vreemde sleutel voor de tabel met toewijzingsbronnen</td>
    <td> </td>
  </tr>
  <tr>
    <td>_CREATED_DATE</td>
    <td>Timestamp_ntz</td>
    <td>datum waarop de record is gemaakt in Snowflake</td>
    <td>2020-01-01 01 :01: 00.000</td>
  </tr>
  <tr>
    <td>_MODIFIED_DATE</td>
    <td>Timestamp_ntz</td>
    <td>datum waarop de record voor het laatst is gewijzigd in Snowflake</td>
    <td>2020-01-01 01 :01: 00.000</td>
  </tr>
  <tr>
    <td>_DELETED_DATE</td>
    <td>Timestamp_ntz</td>
    <td>datum waarop de record is verwijderd in Snowflake</td>
    <td>2020-01-01 01 :01: 00.000</td>
  </tr>
</tbody>
</table>

### BIZ_CAMPAIGN_MEMBERS {#biz-campaign-members}

Campagneleden die zijn geïmporteerd uit het bronsysteem. Deze tabel is leeg als Campagne Sync is uitgeschakeld.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>De id van het Lid van de Campagne van het bronsysteem.</td>
      <td>00v0Z0001VVzdLQAT</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De laatste gewijzigde datum van het campagnelid, uit het bronsysteem.</p>
      </td>
      <td>
        <p>2018-08-31 20 :49: 54.000</p>
      </td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De gecreeerde datum van het Lid van de Campagne, van het bronsysteem.</p>
      </td>
      <td>
        <p>2018-08-31 20 :49: 54.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_TOUCH_POINT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum en tijd die de klant instelt om de datum van de campagne te overschrijven en in plaats daarvan deze waarde voor de aanraakpuntdatum te gebruiken.</p>
      </td>
      <td>
        <p>2018-08-30 18 :00: 00.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id voor de leider van de Campagne is gebonden aan.</p>
      </td>
      <td>
        <p>00Q0Z000013dw4GUAQ</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De e-mail voor de leider van de Campagne is gebonden aan.</p>
      </td>
      <td>persona@adobe.com</td>
    </tr>
    <tr>
      <td>CONTACT_ID</td>
      <td>varchar</td>
      <td>
        <p>Id voor de contactpersoon waaraan het Campagne-lid is gekoppeld.</p>
      </td>
      <td>
        <p>00331000032hMxRAAU</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De e-mail voor het Contact met het Lid van de Campagne is verbonden aan.</p>
      </td>
      <td>persona@adobe.com</td>
    </tr>
    <tr>
      <td>
        <p>STATUS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Status van het Campagne Lid, gewoonlijk geplaatst aan Verzonden of Geantwoord of een andere douanewaarde. Deze status is gebonden aan Campaign_Sync_Type om te bepalen voor welke campagneleden aanraakpunten moeten worden gemaakt.</p>
      </td>
      <td>
        <p>Verzonden</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>HAS_RESPONDED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Geeft aan of het Campagne-lid is gemarkeerd als "Reageerd" in de statuskiezer.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_RESPONDED_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum waarop het Campagne Lid voor het eerst antwoordde.</p>
      </td>
      <td>
        <p>2018-08-30 07 :00: 00.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De naam van de verwante campagne waartoe het campagnelid behoort.</p>
      </td>
      <td>
        <p>Snelle interviews met CMO</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de gerelateerde campagne van het campagnelid maakt deel uit van.</p>
      </td>
      <td>
        <p>7010Z00001TcKlQAK</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het type dat is geselecteerd in de gerelateerde campagne waartoe het Campagne-lid behoort. Het Type wordt gebruikt om het Kanaal van de Marketing in kaart te brengen.</p>
      </td>
      <td>
        <p>Off line</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_SYNC_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Bepaalt voor welke campagneleden aanraakpunten worden gemaakt. De mogelijke waarden zijn: Include_All, Include_Responded, Exclude_All.</p>
      </td>
      <td>
        <p>Opnemen_Alles</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_SYNC_STATUS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>In het veld Audit wordt aangegeven of een Buyer Touchpoint is gegenereerd voor de lead. Als er geen aanraakpunt is gemaakt, wordt de reden waarom het niet in aanmerking kwam gegeven.</p>
      </td>
      <td>
        <p>Geen aanraakpunt: Datum buiten model</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_SYNC_STATUS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>In het veld Audit wordt aangegeven of een Buyer Touchpoint is gegenereerd voor de contactpersoon. Als er geen aanraakpunt is gemaakt, wordt de reden waarom het niet in aanmerking kwam gegeven.</p>
      </td>
      <td>
        <p>Aanraakpunt gemaakt</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>OPP_SYNC_STATUS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>In het veld Audit wordt aangegeven of een Buyer Attribution Touchpoint is gegenereerd voor Opportunity. Als er geen aanraakpunt is gemaakt, wordt de reden waarom het niet in aanmerking kwam gegeven.</p>
      </td>
      <td>
        <p>Aanraakpunt gemaakt</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of de record in het bronsysteem al dan niet als verwijderd wordt beschouwd.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>CUSTOM_PROPERTIES</td>
      <td>varchar</td>
      <td>Aangepaste eigenschappen die [!DNL Marketo Measure] uit het bronsysteem heeft geïmporteerd, in JSON-indeling.</td>
      <td>{"Campaign_Type__c":"Dinners","Foo":"Bar"}</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_CHANNELS {#biz-channels}

Marketingkanalen, zoals gemaakt in de [!DNL Marketo Measure] -toepassing.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Een unieke id voor het kanaal.</p>
      </td>
      <td>
        <p>Organic Search.Google</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAAM</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van het kanaal.</p>
      </td>
      <td>
        <p>Organic Search.Google</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Foreign Key to the Biz_Facts view.</p>
      </td>
      <td>
        <p>6008900572523230000</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record in Snowflake is gemaakt.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_CONTACTS {#biz-contacts}

Contactpersonen die zijn geïmporteerd uit het bronsysteem.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>De contact-id van het bronsysteem.</p>
      </td>
      <td>
        <p>0030Z00003OZOQAB</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum waarop de contactrecord voor het laatst is gewijzigd, via het bronsysteem.</p>
      </td>
      <td>
        <p>2018-09-05 05 :17: 53.000</p>
      </td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de contactpersoonrecord is gemaakt, via het bronsysteem.</p>
      </td>
      <td>
        <p>2018-09-05 05 :17: 51.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>E-mailadres van de contactpersoon, via het bronsysteem.</p>
      </td>
      <td>persona@adobe.com</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNTID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Identiteitskaart van de Rekening met betrekking tot het Contact.</p>
      </td>
      <td>
        <p>001310001b44aGAAQ</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_SOURCE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Source waarin de lead is gemaakt.</p>
      </td>
      <td>
        <p>Advertisatie</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_STAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het huidige werkgebied van de contactpersoon, herkend als een aangepast werkgebied dat in de [!DNL Marketo Measure] -toepassing kan worden gemaakt.</p>
      </td>
      <td>
        <p>demo gepland</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_STAGE_PREVIOUS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Alle vorige stadia voor de contactpersoon, herkend als aangepaste stadia die kunnen worden gemaakt in de [!DNL Marketo Measure] -toepassing.</p>
      </td>
      <td>
        <p>Openen - Contactpersoon</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ODDS_OF_CONVERSION</p>
      </td>
      <td>
        <p>nummer (38,19)</p>
      </td>
      <td>
        <p>Deze functie is vervangen. Gebruik deze kolom niet.</p>
      </td>
      <td>
        <p>NVT</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_COOKIE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De [!DNL Marketo Measure] cookie-id die wordt gebruikt om een integratiepartner te laten vullen en een offlinegebeurtenis toe te wijzen aan een websessie. Vereiste: Enable Call Tracking: True</p>
      </td>
      <td>
        <p>08c1063cb0a64349ad0d2d862f5cc700</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of de record al dan niet wordt verwijderd in het bronsysteem.</p>
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>IS_DUPLICATE</td>
      <td>boolean</td>
      <td>Wordt gebruikt om records te dedupliceren als zowel een CRM-integratie als een Marketo-integratie is ingesteld. Als er duplicaten zijn, wordt de Marketo-contactpersoon gemarkeerd als true.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>SOURCE_SYSTEM</td>
      <td>varchar</td>
      <td>Geeft aan of de record afkomstig is van een CRM- of Marketo-integratie.</td>
      <td>Crm</td>
    </tr>
    <tr>
      <td>OTHER_SYSTEM_ID</td>
      <td>varchar</td>
      <td>Zet een persoon van een integratie van Marketo met een Contact van een integratie van CRM in kaart. Als zowel een CRM als Marketo integratie bestaan, is de waarde overeenkomstige Identiteitskaart.</td>
      <td>1234 / 00Q0Z00001OohgTUAR</td>
    </tr>
    <tr>
      <td>CUSTOM_PROPERTIES</td>
      <td>varchar</td>
      <td>Aangepaste eigenschappen die [!DNL Marketo Measure] heeft geïmporteerd uit het bronsysteem, in JSON-indeling.</td>
      <td>{"Contact_Type__c":"CMO", "Foo":"Bar"}</td>
    </tr>
    <tr>
      <td>ROW_KEY</td>
      <td>getal (38,0)</td>
      <td>Foreign Key to the Biz_Facts view.</td>
      <td>3263982503087870000</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td><b>*</b> JOB_TITLE</td>
      <td>varchar</td>
      <td>Functietitel van de contactpersoon.</td>
      <td>CEO, Vice President</td>
    </tr>
  </tbody>
</table>
<p>
<b> * </b> <i> slechts beschikbaar in Marketo Measure Ultimate </i>
<p>

### BIZ_CONVERSION_RATES {#biz-conversion-rates}

Wisselkoersen die uit het bronsysteem zijn geïmporteerd.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
      <td>ID</td>
      <td>getal (38,0)</td>
      <td>Een unieke id voor de record.</td>
      <td>-5942345438803054604</td>
    </tr>
    <tr>
      <td>CURRENCY_ID</td>
      <td>getal (38,0)</td>
      <td>Id-waarde voor de valuta.</td>
      <td>7493833133899044458</td>
    </tr>
    <tr>
      <td>SOURCE_ISO_CODE</td>
      <td>varchar</td>
      <td>ISO-code valuta, van het bronsysteem.</td>
      <td>USD</td>
    </tr>
    <tr>
      <td>START_DATE</td>
      <td>timestamp_ntz</td>
      <td>Begindatum van het conversietarief.</td>
      <td>2018-11-01 00 :00: 00.000</td>
    </tr>
    <tr>
      <td>END_DATE</td>
      <td>timestamp_ntz</td>
      <td>De volgende begindatum voor het Tarief van de Omzetting. (De einddatum voor het Tarief van de Omzetting is end_date minus 1 dag.)</td>
      <td>2018-09-01 00 :00: 00.000</td>
    </tr>
    <tr>
      <td>CONVERSION_RATE</td>
      <td>getal (38,0)</td>
      <td>De koers die wordt gebruikt om de valuta om te zetten in de bedrijfsvaluta.</td>
      <td>0,76728300</td>
    </tr>
    <tr>
      <td>IS_CURRENT</td>
      <td>boolean</td>
      <td>De semantiek van dit veld is beschadigd. Niet gebruiken.</td>
      <td>true</td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in het bronsysteem.</td>
      <td>2019-03-30 0:54: 50.000</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum waarop de record voor het laatst is gewijzigd in het bronsysteem.</td>
      <td>2019-03-30 0:54: 50.000</td>
    </tr>
    <tr>
      <td>IS_DELETED</td>
      <td>boolean</td>
      <td>Of de record wordt beschouwd als verwijderd in het bronsysteem.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_KOSTEN {#biz-costs}

Kostengegevens die zijn geïmporteerd uit verbonden advertentierekeningen of uit door uzelf gerapporteerde marketinguitgaven.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>Een unieke id voor de kostenrecord.</td>
      <td>aw.6601259029.285114995.21703163075[AdWords Display]_2018-09-06</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst is gewijzigd.</td>
      <td>2018-09-06 12 :22: 45.000</td>
    </tr>
    <tr>
      <td>COST_DATE</td>
      <td>timestamp_ntz</td>
      <td>Datum waarop de kosten zijn gemaakt (of toegerekend aan).</td>
      <td>2018-09-06 00 :00: 00.000</td>
    </tr>
    <tr>
      <td>SOURCE</td>
      <td>varchar</td>
      <td>Source van de gerapporteerde kosten.</td>
      <td>[Weergave Advertenties]</td>
    </tr>
    <tr>
      <td>COST_IN_MICRO</td>
      <td>getal (38,0)</td>
      <td>Kostenbedrag in miljoenen. De gebruiker moet de waarde delen door 1000000.</td>
      <td>1410000</td>
    </tr>
    <tr>
      <td>KLIKKEN</td>
      <td>getal (38,0)</td>
      <td>Aantal kliks dat voor de groep voor de dag wordt gemeld.</td>
      <td>4</td>
    </tr>
    <tr>
      <td>IMPRESSIES</td>
      <td>getal (38,0)</td>
      <td>Aantal gerapporteerde indrukken voor de groep voor de dag.</td>
      <td>4187</td>
    </tr>
    <tr>
      <td>ESTIMATED_TOTAL_MOSIBLE_IMPRESSIONS</td>
      <td>getal (38,0)</td>
      <td>Het totale aantal indrukkingen dat op basis van DCM voor de groep voor de dag wordt geraamd.</td>
      <td>5024</td>
    </tr>
    <tr>
      <td>AD_PROVIDER</td>
      <td>varchar</td>
      <td>Leverancier voor wie de kosten werden afgetrokken.</td>
      <td>Google</td>
    </tr>
    <tr>
      <td>CHANNEL_UNIQUE_ID</td>
      <td>varchar</td>
      <td>Id voor het marketingkanaal, gemaakt door [!DNL Marketo Measure] .</td>
      <td>Display.Google</td>
    </tr>
    <tr>
      <td>CHANNEL_NAME</td>
      <td>varchar</td>
      <td>Naam voor het marketingkanaal dat door de klant in de app [!DNL Marketo Measure] is gemaakt.</td>
      <td>Display.Google</td>
    </tr>
    <tr>
      <td>CHANNEL_IS_AGGREGATABLE_COST</td>
      <td>boolean</td>
      <td>Hiermee wordt aangegeven of de rij Kosten bevat die kunnen worden samengevoegd door Kanaal. (Met andere woorden om de kosten van het Kanaal op te halen, som rijen waar deze kolom waar. evenaart)</td>
      <td>false</td>
    </tr>
    <tr>
      <td>ADVERTISER_UNIQUE_ID</td>
      <td>varchar</td>
      <td>Id van Advertiser die van de verbinding van de Advertentie, specifiek voor de verbindingen van de Doubleclick werd getrokken.</td>
      <td>300181641</td>
    </tr>
    <tr>
      <td>ADVERTISER_NAME</td>
      <td>varchar</td>
      <td>De naam van de adverteerder die uit de advertentie-verbinding is gehaald, met name voor Dubbleclick-verbindingen.</td>
      <td>[!DNL Marketo Measure] Marketinganalyses</td>
    </tr>
    <tr>
      <td>ADVERTISER_IS_AGGREGATABLE_COST</td>
      <td>boolean</td>
      <td>Geeft aan of de rij kosten bevat die kunnen worden samengevat door Advertiser. (Als u kosten voor adverteerders wilt ophalen, telt u de som van de rijen waar deze kolom gelijk is aan true.)</td>
      <td>false</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de advertentierekening uit de advertentie-verbinding.</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de advertentierekening die van de Advertentie verbinding wordt getrokken.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Hiermee wordt aangegeven of de rij Kosten bevat die kunnen worden samengevat per account. (Als u bijvoorbeeld Accountkosten wilt ophalen, som de rijen waar deze kolom gelijk is aan true.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de campagne is uit de advertentie-verbinding gehaald.</p>
      </td>
      <td>
        <p>aw.6601259029.285114995</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de campagne die uit de advertentie-verbinding is gehaald.</p>
      </td>
      <td>
        <p>Opnieuw toewijzen van partners</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Geeft aan of de rij kosten bevat die kunnen worden samengevat door campagne. (Voor Campagnekosten, som rijen waar deze kolom gelijk is aan true.)</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de advertentiegroep die is opgehaald uit de advertentie-verbinding.</p>
      </td>
      <td>
        <p>aw.6601259029.285114995.21703163075</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de Advertentiegroep die uit de Advertentie wordt getrokken.</p>
      </td>
      <td>
        <p>Attributiebeheersoftware | Woorden</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Hiermee wordt aangegeven of de rij Kosten bevat die kunnen worden samengevat door Advertentiegroep. (Als u kosten voor Advertentiegroep wilt ophalen, telt u de som van rijen waar deze kolom gelijk is aan true.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de advertentie die uit de advertentie-verbinding is gehaald.</p>
      </td>
      <td>
        <p>dc.6114.9131003.24149929.467969200</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de advertentie die is opgehaald uit de advertentie-verbinding.</p>
      </td>
      <td>
        <p>Advertentienaam: Ad3-320x50.gif; 320 x 50</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Hiermee wordt aangegeven of de rij Kosten bevat die kunnen worden samengevat met Advertentie. (Met andere woorden om advertentiekosten op te halen, som rijen waar deze kolom waar is.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de Creative Cloud uit de advertentie-verbinding.</p>
      </td>
      <td>
        <p>aw.6601259029.285114995.51749608028.266050115160</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de Creative Cloud die uit de advertentie-verbinding is gehaald.</p>
      </td>
      <td>
        <p>Gartner Magic Quadrant 2019</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Hiermee geeft u aan of de rij kosten bevat die kunnen worden samengevat door Creative. (Met andere woorden om Creative Cost te krijgen, som rijen waar deze kolom waar is.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van het trefwoord dat uit de advertentie-verbinding is gehaald.</p>
      </td>
      <td>
        <p>aw.6601259029.669328935.3941912872.99608705795</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van het trefwoord dat uit de advertentie-verbinding is gehaald.</p>
      </td>
      <td>
        <p>sfdc-marketingtoewijzing</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Hiermee wordt aangegeven of de rij Kosten bevat die kunnen worden samengevat met Trefwoord. (Als u bijvoorbeeld Trefwoordkosten wilt ophalen, som de rijen waar deze kolom gelijk is aan true.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de Plaatsing die uit de Advertentie wordt getrokken.</p>
      </td>
      <td>
        <p>120839827</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de plaatsing die uit de advertentie-verbinding is gehaald.</p>
      </td>
      <td>
        <p>wegblokkeren</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Hiermee wordt aangegeven of de rij Kosten bevat die kunnen worden samengevat door Plaatsing. (Als u bijvoorbeeld Plaatsingskosten wilt ophalen, som de rijen waar deze kolom gelijk is aan true.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de Site die is opgehaald uit de advertentie-verbinding.</p>
      </td>
      <td>
        <p>1695651</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de Site die uit de advertentie-verbinding is gehaald.</p>
      </td>
      <td>
        <p>Quora.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_IS_AGGREGATABLE_COST</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Geeft aan of de rij kosten bevat die per site kunnen worden samengevat. (Als u Sitekosten wilt ophalen, som de rijen waar deze kolom gelijk is aan true.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of de record in het bronsysteem al dan niet als verwijderd wordt beschouwd.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>ISO_CURRENCY_CODE</td>
      <td>varchar</td>
      <td>ISO-code voor de valuta, geïmporteerd uit het bronsysteem.</td>
      <td>USD</td>
    </tr>
    <tr>
      <td>SOURCE_ID</td>
      <td>varchar</td>
      <td>Id voor de Source waarvan de record afkomstig is.</td>
      <td>aw.3284209</td>
    </tr>
    <tr>
      <td>ROW_KEY</td>
      <td>getal (38,0)</td>
      <td>
        <p>Foreign Key to the Biz_Facts view.</p>
      </td>
      <td>6008900572523230000</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_ROW_KEY</p>
      </td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ADVERTISER_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>SITE_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>PLACEMENT_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CAMPAIGN_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_GROUP_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CREATIVE_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>KEYWORD_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CURRENCY_ID</td>
      <td>getal (38,0)</td>
      <td>Id-waarde van de valuta voor de record.</td>
      <td>
        <p>-3253183181619994799</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_CREATIVES {#biz-creatives}

Creatieve producten die zijn geïmporteerd van een verbonden advertentieaccount.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Een unieke id voor Creative.</p>
      </td>
      <td>
        <p>ba.3284209.132855866,4556709270,10426699711</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td>De Creative-id van het bronsysteem.</td>
      <td>
        <p>10426699711</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id voor de advertentierekening waarvan Creative werd ingevoerd.</p>
      </td>
      <td>fb.106851586409075</td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam voor de advertentierekening waarvan Creative werd ingevoerd.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van Advertiser voor Creative, met name voor Doubleclick.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de Advertiser voor Creative, met name voor Doubleclick.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] Marketinganalyses</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van Advertentiegroep voor Creative.</p>
      </td>
      <td>fb.106851586409075.605204428804.6052044290004</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van Advertentiegroep voor Creative.</p>
      </td>
      <td>Advertentieset voor advertentie B</td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de campagne voor Creatief.</p>
      </td>
      <td>
        <p>ba.3284209.132855866</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de Campagne voor Creatief.</p>
      </td>
      <td>
        <p>PipelineMarketing.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Geeft aan of Creative nog actief is in het bronsysteem.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of Creative al dan niet is verwijderd in het bronsysteem.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de record voor het laatst is gewijzigd.</p>
      </td>
      <td>
        <p>2018-08-02 06 :36: 25.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum waarop de record voor het eerst uit het bronsysteem is geïmporteerd.</p>
      </td>
      <td>
        <p>2018-08-02 06 :36: 25.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAAM</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van Creative, van het bronsysteem.</p>
      </td>
      <td>
        <p>PipelineMarketing.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of Creative Cloud moet worden bijgewerkt voor [!DNL Marketo Measure] -tags.</p>
        <p>(Diagnostisch veld, wordt gebruikt door interne verwerking.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>varchar</td>
      <td>Diagnostisch veld, voor interne verwerking.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het hoofdobject of de entiteit voor deze tabel. In dit geval 'Creative'.</p>
      </td>
      <td>
        <p>Creatief</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de advertentieprovider voor de Creative.</p>
      </td>
      <td>
        <p>BingAds</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>URL_CURRENT</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De huidige versie van de URL inclusief alle tags.</p>
        <p>(Diagnostisch veld, voor interne verwerking.)</p>
      </td>
      <td>
        <p>cdn.adobe.com/redir?lp=http%3a%2f%2fwww.pipelinemarketing.com%2f&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}&amp;utm_content={adid}&amp;utm_term={keyword}&amp;utm_campaign=PipelineMarketing.com&amp;utm_source=bing&amp;utm_medium=cpc</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>URL_DISPLAY</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De verkorte en vriendelijke URL die wordt weergegeven op Creative.</p>
      </td>
      <td>
        <p>PipelineMarketing.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>URL_OLD</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Vorige waarde voor URL_CURRENT.</p>
        <p>(Diagnostisch veld, voor interne verwerking.)</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_REQUESTED</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wat de URL zal worden versierd met [!DNL Marketo Measure] parameters.</p>
        <p>(Diagnostisch veld, voor interne verwerking.)</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_SHORTENED</p>
      </td>
      <td>varchar</td>
      <td>De verkorte en vriendelijke URL die wordt weergegeven op Creative. (Alleen gebruikt voor LinkedIn-advertenties.)</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het type Creative, bijvoorbeeld Tekst of Weergave</p>
      </td>
      <td>
        <p>Tekst</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_UPGRADED_URL</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Bepaalt of de creatieve functie Bijgewerkte URL's gebruikt.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>HEADLINE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De bovenste regel (kop) van het creatieve object</p>
      </td>
      <td>
        <p>PipelineMarketing.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DESCRIPTION_LINE_1</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De kopie van de eerste regel van het creatieve object</p>
      </td>
      <td>
        <p>Maak verbinding met en leer meer over de inkomsten van B2B-markeerapparaten. Lid worden van de Gemeenschap.</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DESCRIPTION_LINE_2</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De kopie van de tweede regel van het creatieve object</p>
      </td>
      <td>
        <p>Heb je Analytics gebruikt? Laat vandaag nog een revisie achter!</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE</p>
      </td>
      <td>varchar</td>
      <td>Diagnostiekveld, voor interne verwerking.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_OLD</p>
      </td>
      <td>varchar</td>
      <td>Diagnostiekveld, voor interne verwerking.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_REQUESTED</p>
      </td>
      <td>varchar</td>
      <td>Diagnostiekveld, voor interne verwerking.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_APPLICAED</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Diagnostiekveld, voor interne verwerking.</p>
      </td>
      <td>
        <p>http://cdn.adobe.com/redir?lp={lpurl}&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SHARE_URN</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De aandeel-id. (Alleen gebruikt voor LinkedIn-advertenties.)</p>
      </td>
      <td>
        <p>urn :li: aandeel:6376987561897848832</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>Foreign Key to the Biz_Facts view.</td>
      <td>6008900572523230000</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_CRM_EVENTS {#biz-crm-events}

Gebeurtenissen die zijn geïmporteerd uit het bronsysteem. Deze tabel is leeg als Activiteitensynchronisatie is uitgeschakeld.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>De gebeurtenis-id van het bronsysteem.</p>
      </td>
      <td>
        <p>00U3100000VLUnEEAX</p>
      </td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de gebeurtenis is gemaakt, via het bronsysteem.</p>
      </td>
      <td>
        <p>2016-12-12 19 :32: 53.000</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum waarop de gebeurtenis voor het laatst is gewijzigd, via het bronsysteem.</p>
      </td>
      <td>
        <p>2018-09-03 08 :39: 51.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id voor de lead die aan de gebeurtenis is gekoppeld.</p>
      </td>
      <td>
        <p>00Q0Z00013eVrxUAE</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>E-mail voor de lead die aan de gebeurtenis is gekoppeld.</p>
      </td>
      <td>
        <p>person@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>CONTACT_ID</td>
      <td>varchar</td>
      <td>
        <p>Id voor de contactpersoon die aan de gebeurtenis is gekoppeld.</p>
      </td>
      <td>
        <p>0030Z00003OyjbOQAR</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>E-mail voor de contactpersoon die aan de gebeurtenis is gekoppeld.</p>
      </td>
      <td>
        <p>person@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_COOKIE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De [!DNL Marketo Measure] cookie-id die wordt gebruikt om een integratiepartner te laten vullen en een offlinegebeurtenis toe te wijzen aan een websessie. Vereiste: Enable Call Tracking: True</p>
      </td>
      <td>
        <p>08c1063cb0a64349ad0d2d862f5cc700</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACTIVITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam activiteitstype, van het bronsysteem.</p>
      </td>
      <td>
        <p>E-mail</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EVENT_START_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Begindatum voor de gebeurtenis, een van de opties die wordt gebruikt om de datum van het aanraakpunt te bepalen.</p>
      </td>
      <td>
        <p>2016-12-16 19 :30:.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EVENT_END_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Einddatum voor de gebeurtenis, een van de opties die wordt gebruikt om de datum van het aanraakpunt te bepalen.</p>
      </td>
      <td>
        <p>2016-12-16 21 :30: 00.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Of de record wordt beschouwd als verwijderd in het bronsysteem.</td>
      <td>
        <p>Onwaar</p>
      </td>
    </tr>
    <tr>
      <td>CUSTOM_PROPERTIES</td>
      <td>varchar</td>
      <td>Aangepaste eigenschappen die [!DNL Marketo Measure] uit het bronsysteem heeft geïmporteerd, in JSON-indeling.</td>
      <td>{"Contact_Type__c":"CMO","Foo":"Bar"}</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_CRM_TASKS {#biz-crm-tasks}

Taken die zijn geïmporteerd uit het bronsysteem. Deze lijst zal bevolken als de Synchronisatie van Activiteiten OF het Volgen van de Vraag worden toegelaten.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>De Taak-id van het bronsysteem.</p>
      </td>
      <td>
        <p>00T0Z0004Rf62rUAB</p>
      </td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum de Taak werd gecreeerd, van het bronsysteem.</p>
      </td>
      <td>
        <p>2018-08-27 18 :30: 25.000</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum de Taak werd het laatst gewijzigd, van het bronsysteem.</p>
      </td>
      <td>
        <p>2018-08-27 18 :31: 53.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id voor de lood verbonden aan de Taak.</p>
      </td>
      <td>
        <p>00Q0Z00013eVrxUAE</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>E-mail voor de lood verbonden aan de Taak.</p>
      </td>
      <td>
        <p>person@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>CONTACT_ID</td>
      <td>varchar</td>
      <td>
        <p>Id voor het Contact verbonden aan de Taak.</p>
      </td>
      <td>
        <p>00331000038uGfhAAE</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>E-mail voor het Contact verbonden aan de Taak.</p>
      </td>
      <td>
        <p>person@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_COOKIE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De [!DNL Marketo Measure] cookie-id die wordt gebruikt om een integratiepartner te laten vullen en een offlinegebeurtenis toe te wijzen aan een websessie. Vereiste: Enable Call Tracking: True</p>
      </td>
      <td>
        <p>08c1063cb0a64349ad0d2d862f5cc700</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACTIVITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam activiteitstype, van het bronsysteem.</p>
      </td>
      <td>
        <p>Bellen</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACTIVITY_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de taak is uitgevoerd, is een van de opties die zijn gebruikt om de datum van het aanraakpunt te bepalen.</p>
      </td>
      <td>
        <p>2018-08-27 07 :00: 00.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Of de record wordt beschouwd als verwijderd in het bronsysteem.</td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>CUSTOM_PROPERTIES</td>
      <td>varchar</td>
      <td>Aangepaste eigenschappen die [!DNL Marketo Measure] uit het bronsysteem heeft geïmporteerd, in JSON-indeling.</td>
      <td>{"Contact_Type__c":"CMO", "Foo":"Bar"}</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_CURRENCIES {#biz-currencies}

Tabel van alle ISO-valuta&#39;s.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>getal (38,0)</td>
      <td>Een unieke id voor de valutarecord.</td>
      <td>139474809945095870</td>
    </tr>
    <tr>
      <td>ISO_CODE</td>
      <td>varchar</td>
      <td>ISO-code voor de valuta.</td>
      <td>USD</td>
    </tr>
    <tr>
      <td>IS_CORPORATE</td>
      <td>boolean</td>
      <td>Hiermee wordt aangegeven of de valuta de bedrijfsvaluta is.</td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>IS_ENABLED</td>
      <td>boolean</td>
      <td>Hiermee geeft u aan of de valuta is ingeschakeld in het bronsysteem.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst is gewijzigd in [!DNL Marketo Measure] .</td>
      <td>2018-08-27 18 :30: 25.000</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE_CRM</td>
      <td>timestamp_ntz</td>
      <td>Datum waarop de record voor het laatst is gewijzigd in het bronsysteem.</td>
      <td>2018-08-27 18 :30: 25.000</td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in [!DNL Marketo Measure]</td>
      <td>2018-08-27 18 :30: 25.000</td>
    </tr>
    <tr>
      <td>CREATED_DATE_CRM</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in het bronsysteem.</td>
      <td>2018-08-27 18 :30: 25.000</td>
    </tr>
    <tr>
      <td>ISO_NUMERIC</td>
      <td>getal (38,0)</td>
      <td>Numerieke code volgens ISO-norm.</td>
      <td>048</td>
    </tr>
    <tr>
      <td>EXPONENT</td>
      <td>getal (38,0)</td>
      <td>Het aantal decimalen tussen de kleinste gedefinieerde munteenheid en een gehele munteenheid.</td>
      <td>2</td>
    </tr>
    <tr>
      <td>NAAM</td>
      <td>varchar</td>
      <td>Naam van de valuta.</td>
      <td>Argentijnse peso</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_CUSTOMER_AB_TESTS {#biz-customer-ab-tests}

AB Tests geregistreerd. Deze lijst zal leeg zijn als de Tests van AB niet worden toegelaten.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De eerste cookie-id van de verwante bezoeker-id.</p>
      </td>
      <td>v_36ec805b4db344d6e92c972c86aee34a</td>
    </tr>
    <tr>
      <td>
        <p>COOKIE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De opgenomen cookie-id op het moment dat de gebeurtenis werd geregistreerd.</p>
      </td>
      <td>36ec805b4db344d6e92c972c86aee34a</td>
    </tr>
    <tr>
      <td>
        <p>EVENT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de chat is geregistreerd.</p>
      </td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>IP_ADDRESS</td>
      <td>varchar</td>
      <td>
        <p>Het opgenomen IP-adres op het moment dat het experiment werd geregistreerd.</p>
      </td>
      <td>192.0.2.1</td>
    </tr>
    <tr>
      <td>
        <p>EXPERIMENT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De id van het experiment dat uit het AB-testplatform is getrokken.</p>
      </td>
      <td>123</td>
    </tr>
    <tr>
      <td>
        <p>EXPERIMENT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De naam van het experiment dat uit het AB-testplatform is gehaald.</p>
      </td>
      <td>Experimenteer A</td>
    </tr>
    <tr>
      <td>
        <p>VARIATION_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De variatie-id van het experiment dat uit het AB-testplatform is getrokken.</p>
      </td>
      <td>456</td>
    </tr>
    <tr>
      <td>
        <p>VARIATION_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De variatienaam van het experiment dat van het AB-testplatform is genomen.</p>
      </td>
      <td>Blauwe test</td>
    </tr>
    <tr>
      <td>
        <p>ABTEST_USER_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De id van de gebruiker die het experiment heeft ondergaan, is afkomstig van het AB-testplatform.</p>
      </td>
      <td>584d64et</td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of de record al dan niet is verwijderd, wordt gebruikt voor diagnostiek en controle.</p>
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_CUSTOMER_EVENTS {#biz-customer-events}

Gebeurtenissen van het Web die gebruikend douanegebeurtenissen in Javascript zijn geregistreerd. Deze tabel is leeg als [!DNL Marketo Measure] Gebeurtenissen niet zijn ingeschakeld.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De eerste cookie-id van de verwante bezoeker-id.</p>
      </td>
      <td>v_36ec805b4db344d6e92c972c86aee34a</td>
    </tr>
    <tr>
      <td>
        <p>COOKIE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De opgenomen cookie-id op het moment dat de gebeurtenis werd geactiveerd via het aangepaste javascript.</p>
      </td>
      <td>36ec805b4db344d6e92c972c86aee34a</td>
    </tr>
    <tr>
      <td>
        <p>EVENT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de gebeurtenis is geactiveerd vanuit het aangepaste javascript.</p>
      </td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De laatste datum waarop de record is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>
        <p>IP_ADDRESS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het opgenomen IP-adres op het moment dat de gebeurtenis werd geactiveerd via het aangepaste javascript.</p>
      </td>
      <td>192.0.2.1</td>
    </tr>
    <tr>
      <td>
        <p>SLEUTEL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De naam die aan de gebeurtenis wordt gegeven die van douane javascript werd teweeggebracht.</p>
      </td>
      <td>Videoweergave</td>
    </tr>
    <tr>
      <td>
        <p>WAARDE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De waarde die aan de gebeurtenis wordt gegeven die van douane javascript werd teweeggebracht.</p>
      </td>
      <td>75% bekeken</td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of de record al dan niet is verwijderd, wordt gebruikt voor diagnostiek en controle.</p>
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_CUSTOM_LANDING_PAGES {#biz-custom-landing-pages}

Openingspagina&#39;s die zijn gedownload van een aangesloten advertentieaccount.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Een unieke id voor de record.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>Id voor de advertentierekening waaruit de landingspagina is geïmporteerd.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>Naam van de advertentierekening waaruit de landingspagina is geïmporteerd</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de Advertiser voor de landingspagina, met name voor Doubleclick.</p>
      </td>
      <td>300181641</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de Advertiser voor de landingspagina, met name voor Doubleclick.</p>
      </td>
      <td>
        <p>Marketinganalyses</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>Id van Advertentiegroep voor de landingspagina.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de Advertentiegroep voor de landingspagina.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de campagne voor de landingspagina.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de campagne voor de landingspagina.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De laatste gewijzigde datum van de rij</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>timestamp_ntz</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>NAAM</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_CURRENT</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_OLD</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_EMAIL_TO_VISITOR_IDS {#biz-email-to-visitor-ids}

Toewijzingstabel voor e-mailadressen en bezoekersidentiteiten.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>Een unieke id voor de record.</td>
      <td>
        <p>0013800001MMPPiAAP_person@adobe.com|2022-01-05 17 :22: 13.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Een bekend e-mailadres dat is gekoppeld aan een bepaalde bezoeker-id van een sessie</p>
      </td>
      <td>
        <p>person@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het eerste cookie van de verwante bezoeker-id</p>
      </td>
      <td>
        <p>v_36ec805b4db344d6e92c972c86aee34a</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De laatste gewijzigde datum van de rij</p>
      </td>
      <td>
        <p>2018-08-14 23 :55: 3.000</p>
      </td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De gemaakte datum van de rij</p>
      </td>
      <td>
        <p>2018-08-14 23 :55: 3.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of de record al dan niet als verwijderd wordt beschouwd, wordt gebruikt voor diagnostiek en controle.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>IS_IGNORE</td>
      <td>boolean</td>
      <td>Geeft aan of de e-mail- of bezoekersidentiteitskaart wordt beschouwd als ruis of spam, wordt gebruikt voor interne verwerking.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_FACTS {#biz-facts}

Unies verenigen afbeeldingen, paginaweergaven, bezoeken, verzenden van formulieren, aanraakpunten voor gebruikers, aanraakpunten (BT), aanraakpunten (BAT) en kostengegevens. Wordt intern gebruikt ter ondersteuning van [!DNL Marketo Measure] -rapportage.

>[!IMPORTANT]
>
>Marketo Measure zal deze tabel medio 2024 afschaffen. Als u wenst om het op uw kant tot stand te brengen, stel [ deze SQL vraag ](/help/marketo-measure-data-warehouse/assets/BIZ_FACTS.sql) in werking.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
      <td>COST_KEY</td>
      <td>getal (38,0)</td>
      <td>Wordt gebruikt om deel te nemen aan de tabel Kosten.</td>
      <td>2672629811884560039</td>
    </tr>
    <tr>
      <td>ATP_KEY</td>
      <td>getal (38,0)</td>
      <td>Wordt gebruikt om verbinding te maken met de tabel Attribution Touchpoints.</td>
      <td>2672629811884560039</td>
    </tr>
    <tr>
      <td>TP_KEY</td>
      <td>getal (38,0)</td>
      <td>Wordt gebruikt om verbinding te maken met de aanraakpunten of de tabellen met gebruikerstekens.</td>
      <td>5028390208679093800</td>
    </tr>
    <tr>
      <td>PAGE_VIEW_KEY</td>
      <td>getal (38,0)</td>
      <td>Wordt gebruikt om deel te nemen aan de tabel Paginaweergaven.</td>
      <td>-8044063242541720607</td>
    </tr>
    <tr>
      <td>SESSION_KEY</td>
      <td>getal (38,0)</td>
      <td>Wordt gebruikt om deel te nemen aan de tabel Sessies.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>VISITOR_ID</td>
      <td>varchar</td>
      <td>De eerste cookie-id van de verwante bezoeker-id.</td>
      <td>v_530d8334c455460df0d48f48270a4b23</td>
    </tr>
    <tr>
      <td>COOKIE_ID</td>
      <td>varchar</td>
      <td>De opgenomen cookie-id op het moment dat de gebeurtenis werd geregistreerd.</td>
      <td>530d8334c455460df0d48f48270a4b23</td>
    </tr>
    <tr>
      <td>FORM_SUBMIT_KEY</td>
      <td>getal (38,0)</td>
      <td>Wordt gebruikt om deel te nemen aan de tabel Formulier verzenden.</td>
      <td>-8659572802702769670</td>
    </tr>
    <tr>
      <td>IMPRESSION_KEY</td>
      <td>getal (38,0)</td>
      <td>Wordt gebruikt om verbinding te maken met de tabel Impressies.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CURRENT_PAGE_KEY</td>
      <td>getal (38,0)</td>
      <td>Wordt gebruikt om verbinding te maken met de tabel Urls.</td>
      <td>4079876040770132443</td>
    </tr>
    <tr>
      <td>REFERRER_PAGE_KEY</td>
      <td>getal (38,0)</td>
      <td>Wordt gebruikt om verbinding te maken met de tabel Urls.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>FORM_PAGE_KEY</td>
      <td>getal (38,0)</td>
      <td>Wordt gebruikt om verbinding te maken met de tabel Urls.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>AD_PROVIDER_KEY</td>
      <td>getal (38,0)</td>
      <td>Wordt gebruikt om deel te nemen aan de tabel Advertentieproviders.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>
        <p>CHANNEL_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Wordt gebruikt om te verbinden met de tabel Kanalen.</p>
      </td>
      <td>
        <p>-1921844114032355934</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Wordt gebruikt om deel te nemen aan de tabel Advertentiecampagnes.</p>
      </td>
      <td>
        <p>252687814634577606</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Wordt gebruikt om verbinding te maken met de tabel Trefwoorden.</p>
      </td>
      <td>
        <p>8817975702393619368</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Wordt gebruikt om zich aan te sluiten bij de tabel Advertenties.</p>
      </td>
      <td>
        <p>8817975702393619368</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Wordt gebruikt om deel te nemen aan de tabel Advertentiegroepen.</p>
      </td>
      <td>
        <p>8817975702393619368</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Wordt gebruikt om deel te nemen aan de tabel Creative.</p>
      </td>
      <td>
        <p>-2333871387956621113</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Wordt gebruikt om deel te nemen aan de tabel Sites.</p>
      </td>
      <td>
        <p>8817975702393619368</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Wordt gebruikt om deel te nemen aan de tabel Advertisers.</p>
      </td>
      <td>
        <p>8817975702393619368</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Wordt gebruikt om deel te nemen aan de tabel Advertentierekeningen.</p>
      </td>
      <td>
        <p>1825012532740770032</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Wordt gebruikt om deel te nemen aan de tabel Placements.</p>
      </td>
      <td>
        <p>8817975702393619368</p>
      </td>
    </tr>
    <tr>
      <td>CATEGORIE_01_KEY</td>
      <td>Aantal (38,0)</td>
      <td>Wordt gebruikt om zich aan te sluiten bij de tabel Segmenten.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORIE_02_KEY</td>
      <td>Aantal (38,0)</td>
      <td>Wordt gebruikt om zich aan te sluiten bij de tabel Segmenten.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORIE_03_KEY</td>
      <td>Aantal (38,0)</td>
      <td>Wordt gebruikt om zich aan te sluiten bij de tabel Segmenten.</td>
      <td>-2333871387956621113</td>
    </tr>
    <tr>
      <td>CATEGORIE_04_KEY</td>
      <td>Aantal (38,0)</td>
      <td>Wordt gebruikt om zich aan te sluiten bij de tabel Segmenten.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORIE_05_KEY</td>
      <td>Aantal (38,0)</td>
      <td>Wordt gebruikt om zich aan te sluiten bij de tabel Segmenten.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORIE_06_KEY</td>
      <td>Aantal (38,0)</td>
      <td>Wordt gebruikt om zich aan te sluiten bij de tabel Segmenten.</td>
      <td>-2333871387956621113</td>
    </tr>
    <tr>
      <td>CATEGORIE_07_KEY</td>
      <td>Aantal (38,0)</td>
      <td>Wordt gebruikt om zich aan te sluiten bij de tabel Segmenten.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORIE_08_KEY</td>
      <td>Aantal (38,0)</td>
      <td>Wordt gebruikt om zich aan te sluiten bij de tabel Segmenten.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORIE_09_KEY</td>
      <td>Aantal (38,0)</td>
      <td>Wordt gebruikt om zich aan te sluiten bij de tabel Segmenten.</td>
      <td>2333871387956621113</td>
    </tr>
    <tr>
      <td>CATEGORIE_10_KEY</td>
      <td>Aantal (38,0)</td>
      <td>Wordt gebruikt om zich aan te sluiten bij de tabel Segmenten.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORIE_11_KEY</td>
      <td>Aantal (38,0)</td>
      <td>Wordt gebruikt om zich aan te sluiten bij de tabel Segmenten.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORIE_12_KEY</td>
      <td>Aantal (38,0)</td>
      <td>Wordt gebruikt om zich aan te sluiten bij de tabel Segmenten.</td>
      <td>-2333871387956621113</td>
    </tr>
    <tr>
      <td>CATEGORIE_13_KEY</td>
      <td>Aantal (38,0)</td>
      <td>Wordt gebruikt om zich aan te sluiten bij de tabel Segmenten.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORIE_14_KEY</td>
      <td>Aantal (38,0)</td>
      <td>Wordt gebruikt om zich aan te sluiten bij de tabel Segmenten.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>CATEGORIE_15_KEY</td>
      <td>Aantal (38,0)</td>
      <td>Wordt gebruikt om zich aan te sluiten bij de tabel Segmenten.</td>
      <td>8817975702393619368</td>
    </tr>
    <tr>
      <td>TYPE</td>
      <td>getal (38,0)</td>
      <td>Geeft het gebeurtenistype van de rij aan. 1 = Buyer Attribution Touchpoint 2 = Cost 3 = Buyer Touchpoint 4 = User Touchpoint 5 = Page View 6 = Session 7 = Form Submit 8 = Impression</td>
      <td>3</td>
    </tr>
    <tr>
      <td>DATE</td>
      <td>date</td>
      <td>De datum waarop de gebeurtenis heeft plaatsgevonden.</td>
      <td>28-08-2018</td>
    </tr>
    <tr>
      <td>TIJDSTEMPEL</td>
      <td>timestamp_ntz</td>
      <td>Datum en tijd waarop de gebeurtenis heeft plaatsgevonden.</td>
      <td>2018-08-28 19 :39: 15.000</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de rij voor het laatst is gewijzigd.</p>
      </td>
      <td>
        <p>2018-08-29 00 :46: 47.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COST_IN_MICRO</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Kostenbedrag in miljoenen. De gebruiker moet de waarde delen door 1000000.</p>
      </td>
      <td>
        <p>27370000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IMPRESSIES</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Aantal gerapporteerde indrukken voor de groep voor de dag.</p>
      </td>
      <td>
        <p>340</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KLIKKEN</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Aantal kliks dat voor de groep voor de dag wordt gemeld.</p>
      </td>
      <td>4</td>
    </tr>
    <tr>
      <td>
        <p>FIRST_CLICK_PERCENTAGE</p>
      </td>
      <td>
        <p>nummer(22,19)</p>
      </td>
      <td>
        <p>Het berekende percentage dat aan dit aanraakpunt is toegewezen omdat het een eerste aanraking is.</p>
      </td>
      <td>0,0000000000000000000</td>
    </tr>
    <tr>
      <td>
        <p>LAST_ANON_CLICK_PERCENTAGE</p>
      </td>
      <td>
        <p>nummer(22,19)</p>
      </td>
      <td>
        <p>Het berekende percentage dat is toegewezen aan dit aanraakpunt omdat het een aanraakaanraakaanraakaanraakaanraakpunt is.</p>
      </td>
      <td>100,0000000000000000000</td>
    </tr>
    <tr>
      <td>
        <p>U_SHAPE_PERCENTAGE</p>
      </td>
      <td>
        <p>nummer(22,19)</p>
      </td>
      <td>
        <p>Het berekende percentage dat wordt toegewezen aan dit aanraakpunt omdat het deel uitmaakt van een u-vormige aanraking.</p>
      </td>
      <td>
        <p>100,0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>W_SHAPE_PERCENTAGE</p>
      </td>
      <td>
        <p>nummer(22,19)</p>
      </td>
      <td>
        <p>Het berekende percentage dat wordt toegewezen aan dit aanraakpunt omdat het deel uitmaakt van een w-vormige aanraking.</p>
      </td>
      <td>
        <p>0,0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FULL_PATH_PERCENTAGE</p>
      </td>
      <td>
        <p>nummer(22,19)</p>
      </td>
      <td>
        <p>Het berekende percentage dat aan dit aanraakpunt wordt toegewezen omdat het deel van een volledig wegmodel uitmaakt.</p>
      </td>
      <td>
        <p>0,0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CUSTOM_MODEL_PERCENTAGE</p>
      </td>
      <td>
        <p>nummer(22,19)</p>
      </td>
      <td>
        <p>Het berekende percentage dat aan dit aanraakpunt wordt toegewezen omdat het deel van een douanemodel uitmaakt.</p>
      </td>
      <td>
        <p>0,0000000000000000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BEDRAG</p>
      </td>
      <td>
        <p>nummer(38,8)</p>
      </td>
      <td>
        <p>Hoeveelheid van de Kans, van het bronsysteem.</p>
      </td>
      <td>
        <p>42000,00000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_WON</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Hiermee wordt aangegeven of de opportunity is verplaatst naar een werkgebied dat is geclassificeerd als won.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_OPP_CLOSED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Geeft aan of de opportunity is verplaatst naar een werkgebied dat als gesloten is geclassificeerd.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>OPPORTUNITY_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Opportunity-id van het bronsysteem.</p>
      </td>
      <td>
        <p>0060Z0000nFEfEQAW</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>OPP_CREATED_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de Opportunity is gemaakt, vanuit het bronsysteem.</p>
      </td>
      <td>
        <p>2018-08-31 15 :45: 47.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>OPP_CLOSE_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Dichte datum voor de Kans, van het bronsysteem.</p>
      </td>
      <td>
        <p>2018-12-31 07 :00: 00.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_CREATED_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de contactpersoonrecord is gemaakt, via het bronsysteem.</p>
      </td>
      <td>2017-04-28 00 :21: 52.000</td>
    </tr>
    <tr>
      <td>CONTACT_ID</td>
      <td>varchar</td>
      <td>
        <p>Contact-id van het bronsysteem.</p>
      </td>
      <td>
        <p>0030Z00003ORVJmQAP</p>
      </td>
    </tr>
    <tr>
      <td>EMAIL</td>
      <td>varchar</td>
      <td>E-mailadres voor de record.</td>
      <td>personb@adobe.com</td>
    </tr>
    <tr>
      <td>
        <p>LEAD_CREATED_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de lead-record is gemaakt, via het bronsysteem.</p>
      </td>
      <td>
        <p>2017-04-28 00 :21: 52.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van lead uit het bronsysteem.</p>
      </td>
      <td>
        <p>00Q3100001GMPIsEAP</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_AD</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Hiermee wordt aangegeven of de rij Kosten bevat die kunnen worden samengevat met Advertentie. (Met andere woorden om advertentiekosten op te halen, som rijen waar deze kolom waar is.)</p>
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_ADVERTISER</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Geeft aan of de rij kosten bevat die kunnen worden samengevat door Advertiser. (Als u kosten voor adverteerders wilt ophalen, telt u de som van de rijen waar deze kolom gelijk is aan true.)</p>
      </td>
      <td>true</td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_AD_ACCOUNT</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Hiermee wordt aangegeven of de rij Kosten bevat die kunnen worden samengevat per account. (Als u bijvoorbeeld Accountkosten wilt ophalen, som de rijen waar deze kolom gelijk is aan true.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_AD_GROUP</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Hiermee wordt aangegeven of de rij Kosten bevat die kunnen worden samengevat door Advertentiegroep. (Als u kosten voor Advertentiegroep wilt ophalen, telt u de som van rijen waar deze kolom gelijk is aan true.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_CAMPAIGN</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Geeft aan of de rij kosten bevat die kunnen worden samengevat door campagne. (Voor Campagnekosten, som rijen waar deze kolom gelijk is aan true.)</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_CHANNEL</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Hiermee wordt aangegeven of de rij Kosten bevat die kunnen worden samengevoegd door Kanaal. (Met andere woorden om de kosten van het Kanaal op te halen, som rijen waar deze kolom waar. evenaart)</p>
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_CREATIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Hiermee geeft u aan of de rij kosten bevat die kunnen worden samengevat door Creative. (Met andere woorden om Creative Cost te krijgen, som rijen waar deze kolom waar is.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_KEYWORD</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Hiermee wordt aangegeven of de rij Kosten bevat die kunnen worden samengevat met Trefwoord. (Als u bijvoorbeeld Trefwoordkosten wilt ophalen, som de rijen waar deze kolom gelijk is aan true.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_PLACEMENT</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Hiermee wordt aangegeven of de rij Kosten bevat die kunnen worden samengevat door Plaatsing. (Als u bijvoorbeeld Plaatsingskosten wilt ophalen, som de rijen waar deze kolom gelijk is aan true.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_AGGREGATABLE_COST_SITE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Geeft aan of de rij kosten bevat die per site kunnen worden samengevat. (Als u Sitekosten wilt ophalen, som de rijen waar deze kolom gelijk is aan true.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of de record is verwijderd, wordt gebruikt als audittrail.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>CURRENCY_ID</td>
      <td>getal (38,0)</td>
      <td>Id-waarde van de valuta voor de record.</td>
      <td>-3253183181619994799</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_FORM_SUBMITS {#biz-forms-submits}

Vastgelegde formulierverzendingen.

<table>
  <tbody>
    <tr>
      <th>
        Kolom
      </th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Een unieke id voor het formulier dat wordt verzonden.</p>
      </td>
      <td>
        <p>2018-08-06:01-35-21-927280.9bc63c34482f4</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COOKIE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De opgenomen cookie-id op het moment dat het formulier wordt verzonden.</p>
      </td>
      <td>
        <p>9bc63c34482f4de8c2e3b9d8d9f0df56</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De eerste cookie-id van de verwante bezoeker-id. Als de record is gemarkeerd als is_duplicated = true, is dit veld null.</p>
      </td>
      <td>
        <p>v_9bc63c34482f4de8c2e3b9d8d9f0df56</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SESSION_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De opgenomen sessie-id op het moment dat het formulier wordt verzonden. Als de record is gemarkeerd als is_duplicated = true, is dit veld null.</p>
      </td>
      <td>
        <p>2018-08-06:01-35-24-1231230.9bc63c34482f</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EVENT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop het formulier is verzonden.</p>
      </td>
      <td>
        <p>2018-08-06 01 :35: 21.000</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de record voor het laatst is gewijzigd.</p>
      </td>
      <td>
        <p>2018-08-07 23 :09: 52.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CURRENT_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>URL waar het formulier is verzonden, zonder queryparameters.</p>
      </td>
      <td>
        <p>https://info.adobe.com/webinar-marketo-measure-impact</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CURRENT_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>URL waar het formulier is verzonden, inclusief eventuele queryparameters.</p>
      </td>
      <td>
        <p>https://info.adobe.com/webinar-marketo-measure-impact?utm_source=partner&amp;mkt_tok=eyJpIjoiTnpBeE1EVml PV0UyWlRObSIsInQiOiI3MEFIek04ZVJiWm9renc1Z29RXC9kXC92YkxycFRYclE0MVhOaH Nwdml3YTZBZd PdXh4Q0RmcnBJWXhwZTF1Z0RrbXlDVmxJNzIwNkhW</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IP_ADDRESS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het opgenomen IP-adres op het moment dat het formulier werd verzonden.</p>
      </td>
      <td>
        <p>174 127 184 158</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TYPE</p>
      </td>
      <td>varchar</td>
      <td>Geeft het type gebeurtenis aan.</td>
      <td>
        <p>FormSubmit</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>USER_AGENT_STRING</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Apparaat en browser zijn opgenomen op het moment dat het formulier wordt verzonden.</p>
      </td>
      <td>
        <p>Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_6) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/11.1.2 Safari/605.1.15</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CLIENT_SEQUENCE</p>
      </td>
      <td>varchar</td>
      <td>Hiermee geeft u de volgorde aan waarin de paginaweergave is opgetreden tijdens de sessie.</td>
      <td>
        <p>4</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CLIENT_RANDOM</p>
      </td>
      <td>varchar</td>
      <td>Wordt gebruikt voor interne controle en verwerking.</td>
      <td>
        <p>20042b6b7af4512b43f6244d86faf4c</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DUPLICATED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Hiermee wordt aangegeven of de record wordt beschouwd als een duplicaat.</td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_PROCESSED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Wordt gebruikt voor interne verwerking.</td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>E-mailadres opgegeven op het formulier, zoals vastgelegd in het javascript.</p>
      </td>
      <td>
        <p>personc@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_TYPE</p>
      </td>
      <td>varchar</td>
      <td>Hiermee geeft u het type verzonden formulier aan.</td>
      <td>
        <p>Chat</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_SOURCE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Geeft de methode aan waarin het formulier is herkend, zoals onSubmit of AjaxIntercept</p>
      </td>
      <td>
        <p>onSubmit</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_IDENTIFIER</p>
      </td>
      <td>varchar</td>
      <td>Id-waarde voor het formulier.</td>
      <td>
        <p>-956012665</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Foreign Key to the Biz_Facts view.</p>
      </td>
      <td>
        <p>-6255315750913680000</p>
      </td>
    </tr>
    <tr>
      <td>CURRENT_PAGE_KEY</td>
      <td>getal (38,0)</td>
      <td>External Key to the Url table.</td>
      <td>6255315750913680000</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_IMPRESSIONS {#biz-impressions}

Afgevoerde en opgenomen indrukkingen. Voor deze tabel is een DoubleClick-verbinding vereist en Weergave inschakelen via ingesteld op Waar.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Een unieke id voor de afdruk.</p>
      </td>
      <td>
        <p>6acd7b43290490fe5c53eed31281d09a|2020-05-18:22: 20:59|000|0|286936905 2</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COOKIE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De opgenomen cookie-id op het moment van de impressie.</p>
      </td>
      <td>08c1063cb0a64349ad0d2d862f5cc700</td>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De eerste cookie-id van de verwante bezoeker-id.</p>
      </td>
      <td>v_08c1063cb0a64349ad0d2d862f5cc700</td>
    </tr>
    <tr>
      <td>
        <p>SESSION_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De opgenomen sessie-id op het moment dat de onderdrukking werd geregistreerd.</p>
      </td>
      <td>2018-08-06:01-35-24-1231230.9bc63c34482f</td>
    </tr>
    <tr>
      <td>
        <p>EVENT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de depressie is opgetreden.</p>
      </td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de record voor het laatst is gewijzigd.</p>
      </td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>
        <p>CURRENT_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>URL waar de Indrukking, zonder vraagparameters werd gediend.</p>
      </td>
      <td>https://info.adobe.com/webinar-marketo-measure-impact</td>
    </tr>
    <tr>
      <td>
        <p>CURRENT_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>URL waar de Indrukking werd gediend, met inbegrip van om het even welke vraagparameters.</p>
      </td>
      <td>https://info.adobe.com/webinar-marketo-measure-impact?utm_source=partner&amp;mkt_tok=eyJpIjoiTnpBeE1EVml PV0UyWlRObSIsInQiOiI3MEFIek04ZVJiWm9renc1Z29RXC9kXC92YkxycFRYclE0MVhOaH Nwdml3YTZBZd PdXh4Q0RmcnBJWXhwZTF1Z0RrbXlDVmxJNzIwNkhW</td>
    </tr>
    <tr>
      <td>
        <p>IP_ADDRESS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het opgenomen IP-adres op het moment van de onderdrukking.</p>
      </td>
      <td>174 127 184 158</td>
    </tr>
    <tr>
      <td>
        <p>TYPE</p>
      </td>
      <td>varchar</td>
      <td>Geeft het type gebeurtenis aan.</td>
      <td>Impressie</td>
    </tr>
    <tr>
      <td>
        <p>USER_AGENT_STRING</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Apparaat en browser zijn opgenomen op het moment dat het formulier wordt verzonden.</p>
      </td>
      <td>
        <p>Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_6) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/11.1.2 Safari/605.1.15</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CLIENT_SEQUENCE</p>
      </td>
      <td>varchar</td>
      <td>Hiermee geeft u de volgorde aan waarin de paginaweergave is opgetreden tijdens de sessie.</td>
      <td>
        <p>4</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CLIENT_RANDOM</p>
      </td>
      <td>varchar</td>
      <td>Wordt gebruikt voor interne controle en verwerking.</td>
      <td>
        <p>20042b6b7af4512b43f6244d86faf4c</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DUPLICATED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Hiermee wordt aangegeven of de record wordt beschouwd als een duplicaat.</td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_PROCESSED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Wordt gebruikt voor interne verwerking.</td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Doorgaans de externe bestemmingspagina vlak voordat de gebruiker op de website komt. Wordt in de CRM aangeduid als "Referrer Page".</p>
      </td>
      <td>https://www.linkedin.com/</td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE-RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Doorgaans de externe bestemmingspagina vlak voordat de gebruiker op de website komt. Een onbewerkte verwijzingspagina kan queryparameters in de URL bevatten. Wordt in de CRM aangeduid als "Referrer Page - Raw".</p>
      </td>
      <td>https://www.linkedin.com/</td>
    </tr>
    <tr>
      <td>
        <p>STAD</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De opgeloste stad van het IP adres.</p>
      </td>
      <td>
        <p>Seattle</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REGIO</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het opgeloste gebied van het IP adres.</p>
      </td>
      <td>
        <p>Washington</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAND</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het opgeloste land van het IP adres.</p>
      </td>
      <td>
        <p>Verenigde Staten</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ISP_NAME</p>
      </td>
      <td>varchar</td>
      <td>Null verwacht omdat het veld verouderd is.</td>
      <td>NULL</td>
    </tr>
    <tr>
      <td>
        <p>AD_PROVIDER</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Adplatform [!DNL Marketo Measure] kon oplossen van, typisch één van onze integratiepartners.</p>
      </td>
      <td>Google</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van advertentierekening waarvan de advertentie is opgelost.</p>
      </td>
      <td>aw.6601259029</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de advertentierekening waaruit de advertentie is opgelost.</p>
      </td>
      <td>[!DNL Marketo Measure]</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de adverteerder van de advertentierekening waarin de advertentie is opgelost. Dit geldt alleen voor Dubbelklik op Campagnebeheer.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de adverteerder van de advertentierekening waarin de advertentie is opgelost. Dit geldt alleen voor Dubbelklik op Campagnebeheer.</p>
      </td>
      <td>
        <p>Marktmaatmarketinganalyse</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de site van de advertentieaccount waaruit de advertentie is opgelost. Dit geldt alleen voor Dubbelklik op Campagnebeheer.</p>
      </td>
      <td>
        <p>1695651</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de site van de advertentierekening waaruit de advertentie is opgelost. Dit geldt alleen voor Dubbelklik op Campagnebeheer.</p>
      </td>
      <td>
        <p>Quora.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de Plaatsing van de Advertentierekening waarin de Advertentie van werd opgelost. Dit geldt alleen voor Dubbelklik op Campagnebeheer.</p>
      </td>
      <td>
        <p>120839827</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de Plaatsing van de Advertentierekening waarin de Advertentie van werd opgelost. Dit geldt alleen voor Dubbelklik op Campagnebeheer.</p>
      </td>
      <td>
        <p>wegblokkeren</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de campagne van de advertentierekening waar de Advertentie van werd opgelost.</p>
      </td>
      <td>aw.6601259029.317738075</td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de campagne van de advertentierekening waarin Advertentie werd opgelost van.</p>
      </td>
      <td>Marketingkenmerk</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Null verwacht omdat er geen Advertentiegroep in de Dubbelklik-hiërarchie is voor afbeeldingen</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Null verwacht omdat er geen Advertentiegroep in de Dubbelklik-hiërarchie is voor afbeeldingen</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de advertentie van de advertentierekening waarin de advertentie is opgelost. Dit geldt voor Dubbelklik op Campagne Manager en Facebook (display).</p>
      </td>
      <td>
        <p>68035923</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de advertentie van de advertentierekening waarin de advertentie is opgelost. Dit geldt voor Dubbelklik op Campagne Manager en Facebook (display).</p>
      </td>
      <td>
        <p>centurylink_banner_98121</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De waarde null wordt verwacht omdat de dubbelklikhiërarchie voor afbeeldingen geen Creatief bevat.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De waarde null wordt verwacht omdat de dubbelklikhiërarchie voor afbeeldingen geen Creatief bevat.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_1</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De waarde null wordt verwacht omdat de dubbelklikhiërarchie voor afbeeldingen geen Creatief bevat.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_2</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De waarde null wordt verwacht omdat de dubbelklikhiërarchie voor afbeeldingen geen Creatief bevat.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESTINATION_URL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De waarde null wordt verwacht omdat de dubbelklikhiërarchie voor afbeeldingen geen Creatief bevat.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DISPLAY_URL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De waarde null wordt verwacht omdat de dubbelklikhiërarchie voor afbeeldingen geen Creatief bevat.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Er wordt een null-waarde verwacht omdat de dubbelklikhiërarchie voor afbeeldingen geen trefwoord bevat.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Er wordt een null-waarde verwacht omdat de dubbelklikhiërarchie voor afbeeldingen geen trefwoord bevat.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_MATCH_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Er wordt een null-waarde verwacht omdat de dubbelklikhiërarchie voor afbeeldingen geen trefwoord bevat.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>BROWSER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Van javascript en IP adres, ontdekte browser dat de gebruiker tijdens de zitting was.</p>
      </td>
      <td>
        <p>Chrome</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BROWSER_VERSION</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Van javascript en IP adres, de ontdekte versie van browser die de gebruiker tijdens de zitting was.</p>
      </td>
      <td>
        <p>58</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLATFORM_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Van javascript en IP adres, het ontdekte platform dat de gebruiker tijdens de zitting was.</p>
      </td>
      <td>
        <p>Mac</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLATFORM_VERSION</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Van javascript en IP adres, de ontdekte versie van het platform dat de gebruiker tijdens de zitting was.</p>
      </td>
      <td>
        <p>10_12</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Foreign Key to the BIZ_FACTS view.</p>
      </td>
      <td>
        <p>-2712935512233520000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CURRENT_PAGE_KEY</p>
      </td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>REFERRER_PAGE_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ACCOUNT_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ADVERTISER_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>SITE_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>PLACEMENT_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CAMPAIGN_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_GROUP_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CREATIVE_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>KEYWORD_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_KEYWORDS {#biz-keywords}

Trefwoorden die zijn geïmporteerd uit een verbonden advertentieaccount.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Een unieke id voor het trefwoord.</p>
      </td>
      <td>
        <p>ba.3284209.132630532.3646889365.39464932147</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td>De trefwoord-id van het bronsysteem.</td>
      <td>
        <p>39464932147</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id voor de advertentierekening waarvan het Sleutelwoord werd ingevoerd.</p>
      </td>
      <td>fb.106851586409075</td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de advertentierekening waaruit het Sleutelwoord werd ingevoerd.</p>
      </td>
      <td>[!DNL Marketo Measure]</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Er wordt een null-waarde verwacht omdat de dubbelklikhiërarchie voor afbeeldingen geen trefwoord bevat.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Er wordt een null-waarde verwacht omdat de dubbelklikhiërarchie voor afbeeldingen geen trefwoord bevat.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van Advertentiegroep voor het Sleutelwoord.</p>
      </td>
      <td>
        <p>ba.3284209.132630532.364689365</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de Advertentiegroep voor het Sleutelwoord.</p>
      </td>
      <td>
        <p>Belastingkenmerk - B2B</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de campagne voor het trefwoord.</p>
      </td>
      <td>
        <p>ba.3284209.132630532</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de campagne voor het trefwoord.</p>
      </td>
      <td>
        <p>Belastingkenmerk</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of het trefwoord nog steeds actief is in het bronsysteem.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of het trefwoord al dan niet is verwijderd in het bronsysteem.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de record voor het laatst is gewijzigd.</p>
      </td>
      <td>2018-08-02 06 :37: 29.000</td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum waarop de record voor het eerst uit het bronsysteem is geïmporteerd.</p>
      </td>
      <td>
        <p>2018-08-02 06 :37: 29.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAAM</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van het Sleutelwoord, van het bronsysteem.</p>
      </td>
      <td>
        <p>[ontvangstentoerekening b2b]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of het trefwoord moet worden bijgewerkt voor [!DNL Marketo Measure] -tags.</p>
        <p>(Diagnostisch veld, gebruikt voor interne verwerking.)</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>varchar</td>
      <td>Diagnostisch veld voor interne verwerking.</td>
      <td>
        <p>ba.3284209.132630532.364689365</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het hoofdobject of de entiteit voor deze tabel. In dit geval "Trefwoord".</p>
      </td>
      <td>
        <p>Trefwoord</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de advertentieprovider voor het trefwoord.</p>
      </td>
      <td>
        <p>BingAds</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>URL_CURRENT</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De URL voor de landingspagina.</p>
        <p>(Diagnostisch veld, voor interne verwerking.)</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_OLD</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Vorige waarde voor URL_CURRENT.</p>
        <p>(Diagnostisch veld, voor interne verwerking.)</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>URL_REQUESTED</td>
      <td>varchar</td>
      <td>
        <p>De URL voor de landingspagina met [!DNL Marketo Measure] -parameters.</p>
        <p>(Diagnostisch veld, voor interne verwerking.)</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>IS_UPGRADED_URL</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Diagnostisch veld, voor interne verwerking.</td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>WOORD</p>
      </td>
      <td>varchar</td>
      <td>De zoekfase die de gebruiker heeft ingevoerd.</td>
      <td>
        <p>inkomstentoerekening b2b</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MATCH_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het type overeenkomst dat is gevonden tussen de zoekuitdrukking en het trefwoord.</p>
      </td>
      <td>
        <p>Exact</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE</p>
      </td>
      <td>varchar</td>
      <td>Wordt gebruikt voor interne diagnose.</td>
      <td>http://cdn.adobe.com/redir?lp={lpurl}&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}</td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_OLD</p>
      </td>
      <td>varchar</td>
      <td>Wordt gebruikt voor interne diagnose.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_REQUESTED</p>
      </td>
      <td>varchar</td>
      <td>Wordt gebruikt voor interne diagnose.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>TRACKING_URL_TEMPLATE_APPLICAED</p>
      </td>
      <td>varchar</td>
      <td>De URL-volgsjabloon [!DNL Marketo Measure] die aan het trefwoord is toegevoegd.</td>
      <td>
        <p>http://cdn.adobe.com/redir?lp={lpurl}&amp;_bt={creative}&amp;_bk={keyword}&amp;_bm={matchType}</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Foreign Key to the Biz_Facts view.</p>
      </td>
      <td>-2712935512233520000</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_LANDING_PAGES {#biz-landing-pages}

Pagina&#39;s die zijn geïmporteerd van een aangesloten advertentieaccount aanlanden.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Een unieke id voor de bestemmingspagina.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>Id voor de advertentierekening waaruit de landingspagina is geïmporteerd.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>Naam van de advertentierekening waaruit de landingspagina is geïmporteerd.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de Advertiser voor de landingspagina, met name voor Doubleclick.</p>
      </td>
      <td>300181641</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de Advertiser voor de landingspagina, met name voor Doubleclick.</p>
      </td>
      <td>Marketinganalyses</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>Id van Advertentiegroep voor de landingspagina.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>Naam van de Advertentiegroep voor de landingspagina.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>Id van de campagne voor de landingspagina.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>Naam van de campagne voor de landingspagina.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De laatste gewijzigde datum van de rij.</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>timestamp_ntz</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>NAAM</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_CURRENT</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_OLD</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_REQUESTED</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_LEADS {#biz-leads}

Leads die zijn geïmporteerd uit het bronsysteem.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>De lood-id van het bronsysteem.</p>
      </td>
      <td>
        <p>00Q0Z00001MZcj8UAD</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de lead-record voor het laatst is gewijzigd, via het bronsysteem.</p>
      </td>
      <td>
        <p>2018-08-27 21 :52: 10.000</p>
      </td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de lead-record is gemaakt, via het bronsysteem.</p>
      </td>
      <td>2018-08-27 21 :52: 10.000</td>
    </tr>
    <tr>
      <td>
        <p>EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>E-mailadres van de lead via het bronsysteem.</p>
      </td>
      <td>persona@adobe.com</td>
    </tr>
    <tr>
      <td>
        <p>WEB_SITE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Website ingegaan voor Lood, van het bronsysteem, die voor Lood2Account afbeelding wordt gebruikt.</p>
      </td>
      <td>
        <p>adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ONDERNEMING</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De naam van het bedrijf ingegaan voor Lood, van het bronsysteem, die voor afbeelding Lead2Account wordt gebruikt.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_SOURCE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Source waarin de lead is gemaakt.</p>
      </td>
      <td>
        <p>Advertisatie</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_CONVERTED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of de lead al dan niet is omgezet in een contactpersoon.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONVERTED_OPPORTUNITY_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de gerelateerde opportunity zodra de lead is omgezet.</p>
      </td>
      <td>
        <p>001310001b44aGAAQ</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONVERTED_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de lead is omgezet in een contactpersoon.</p>
      </td>
      <td>
        <p>2018-08-27 07 :00: 00.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONVERTED_CONTACT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Identiteitskaart van het verwante Contact zodra de Lood is omgezet.</p>
      </td>
      <td>
        <p>0030Z0003OYP25QAB</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNTID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van het toegewezen account. Vereisten: ABM inschakelen</p>
      </td>
      <td>
        <p>0010Z0000236F9GQAU</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_STAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het huidige stadium van de lead, herkend als een aangepast werkgebied dat in de [!DNL Marketo Measure] -toepassing kan worden gemaakt.</p>
      </td>
      <td>
        <p>demo gepland</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_STAGE_PREVIOUS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Alle vorige fasen voor de lead, herkend als aangepaste stadia die kunnen worden gemaakt in de [!DNL Marketo Measure] -toepassing.</p>
      </td>
      <td>
        <p>MQL</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ODDS_OF_CONVERSION</p>
      </td>
      <td>
        <p>nummer (38,19)</p>
      </td>
      <td>
        <p>Deze functie is vervangen. Gebruik deze kolom niet.</p>
      </td>
      <td>
        <p>NVT</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_SCORE_MODEL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>(afgekeurd)</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_SCORE_RESULTS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>(afgekeurd)</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_COOKIE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De [!DNL Marketo Measure] cookie-id die wordt gebruikt om een integratiepartner te laten vullen en een offlinegebeurtenis toe te wijzen aan een websessie. Vereiste: Enable Call Tracking: True</p>
      </td>
      <td>
        <p>08c1063cb0a64349ad0d2d862f5cc700</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of de record al dan niet wordt verwijderd in het bronsysteem.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Foreign Key to the Biz_Facts view.</p>
      </td>
      <td>3263982503087870000</td>
    </tr>
    <tr>
      <td>CUSTOM_PROPERTIES</td>
      <td>varchar</td>
      <td>Aangepaste eigenschappen die [!DNL Marketo Measure] heeft geïmporteerd uit het bronsysteem, in JSON-indeling.</td>
      <td>{"Lead_Type__c":"Verkoop gemaakt", "Foo":"Bar"}</td>
    </tr>
    <tr>
      <td>IS_DUPLICATE</td>
      <td>boolean</td>
      <td>Wordt gebruikt om records te dedupliceren als zowel een CRM-integratie als een Marketo-integratie is ingesteld. Als er duplicaten zijn, wordt de Marketo-lead gemarkeerd als true.</td>
      <td>true</td>
    </tr>
    <tr>
      <td>SOURCE_SYSTEM</td>
      <td>varchar</td>
      <td>Geeft aan of de record afkomstig is van een CRM- of Marketo-integratie.</td>
      <td>Crm</td>
    </tr>
    <tr>
      <td>OTHER_SYSTEM_ID</td>
      <td>varchar</td>
      <td>Zet een persoon van een integratie van Marketo met een Lood van een integratie van CRM in kaart. Als zowel een CRM als Marketo integratie bestaan, is de waarde overeenkomstige Identiteitskaart.</td>
      <td>1234</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_LEAD_STAGE_TRANSITIONS {#biz-lead-stage-transitions}

Werkgebiedovergangen voor leads of contactpersonen.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Een unieke id voor de overgang.</p>
      </td>
      <td>
        <p>ST_0030Z0003FhkRXQAZ__FT-1_TP2_Person_0030Z0003FhkRXQAZ_2018-08-27:17-05-45-94 74800.0d5c18c29d7b</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het opgegeven e-mailadres voor de betreffende lead/contactpersoon.</p>
      </td>
      <td>
        <p>persone@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id voor de lead die aan de overgang is gekoppeld.</p>
      </td>
      <td>
        <p>00Q310001Fx6AlEAJ</p>
      </td>
    </tr>
    <tr>
      <td>CONTACT_ID</td>
      <td>varchar</td>
      <td>
        <p>Id voor de contactpersoon die aan de overgang is gekoppeld.</p>
      </td>
      <td>
        <p>0033100003Aq9grAAB</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TOUCHPOINT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id voor de Buyer Touchpoint die aan de overgang is gekoppeld.</p>
      </td>
      <td>
        <p>TP2_Person_00Q310001Fx6AlEAJ_2018-08-28:14-41-06-1674260.d00ceb09fbd3</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRANSITION_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum waarop de record naar het werkgebied is overgebracht.</p>
      </td>
      <td>
        <p>2018-08-27 16 :05: 34.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>STAGE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id-waarde van het werkgebied voor de overgang.</p>
      </td>
      <td>
        <p>_bizible_FT</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>WERKGEBIED</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van het werkgebied voor de overgang.</p>
      </td>
      <td>
        <p>FT</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>RANK</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>De numerieke positie van het werkgebied, zoals geordend in de instellingen voor werkgebiedtoewijzing van [!DNL Marketo Measure] .</p>
      </td>
      <td>
        <p>5</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>INDEX</p>
      </td>
      <td>
        <p>varchar(1)</p>
      </td>
      <td>
        <p>Wordt gebruikt in interne verwerking voor het indexeren en bestellen van boemerang-fasen.</p>
      </td>
      <td>
        <p>1</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAST_INDEX</p>
      </td>
      <td>
        <p>varchar(1)</p>
      </td>
      <td>Wordt gebruikt in interne verwerking voor het indexeren en bestellen van boemerang-fasen.</td>
      <td>
        <p>1</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_PENDING</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Geeft aan of het aanraakpunt als in behandeling wordt beschouwd en nog niet is gesloten. Dit wordt alleen weergegeven voor klanten met het volledige toewijzingsmodel voor paden.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_NON_TRANSITIONAL</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Hiermee wordt aangegeven of de rij is gekoppeld aan een overgangsfase van een mijlpaal. Als er bijvoorbeeld drie fasen/ingangen (FT, LC, MQL) en vier aanraakpunten zijn, wordt het 1 aanraakpunt zonder een stadium op het punt beschouwd als "niet-tijdelijk", zodat de waarde gelijk is.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PREVIOUS_STAGE_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Overgangsdatum voor de vorige fase, volgens de positie van het werkgebied.</p>
      </td>
      <td>
        <p>2017-11-28 21 :26: 44.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NEXT_STAGE_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Overgangsdatum voor de volgende fase, volgens de positie van het werkgebied.</p>
      </td>
      <td>
        <p>2017-12-11 22 :39: 17.000</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum van laatste wijziging van de record.</p>
      </td>
      <td>
        <p>2018-08-28 15 :31: 10.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of de overgangsrecord wordt beschouwd als verwijderd.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_MOGELIJKHEDEN {#biz-opportunities}

Kansen die uit het bronsysteem worden ingevoerd.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>De opportunity-id van het bronsysteem.</p>
      </td>
      <td>
        <p>0060Z0000o89I4QAI</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De laatste gewijzigde datum van de Kans, van het bronsysteem.</p>
      </td>
      <td>2017-11-28 21 :26: 44.000</td>
    </tr>
    <tr>
      <td>CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De gecreeerde datum van de Kans, van het bronsysteem.</p>
      </td>
      <td>2017-11-28 21 :26: 44.000</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de verwante account.</p>
      </td>
      <td>
        <p>001i00000qbyeoAAA</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAAM</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De naam van de Kans, van het bronsysteem.</p>
      </td>
      <td>
        <p>Mareketo Maatregel Verlenging</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_WON</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Geeft aan of de opportunity is verplaatst naar een werkgebied waarvan wordt aangenomen dat deze is gewonnen.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_CLOSED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Geeft aan of de opportunity is verplaatst naar een werkgebied dat als gesloten wordt beschouwd.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CLOSE_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Verwacht of daadwerkelijke sluitingsdatum van de Kans, van het bronsysteem.</p>
      </td>
      <td>
        <p>2019-08-28 07 :00: 00.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_CUSTOM_MODEL_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>(afgekeurd)</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BEDRAG</p>
      </td>
      <td>
        <p>nummer(38,8)</p>
      </td>
      <td>
        <p>Het bedrag van de overeenkomst dat van de Kans, van het bronsysteem wordt verwacht of gesloten.</p>
      </td>
      <td>
        <p>8988,00000000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONVERTED_FROM_LEAD_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De id van de gerelateerde lead die is omgezet in deze opportunity.</p>
        <p>Dit veld is niet ingesteld en retourneert null in Snowflake voor alle klanten.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONVERTED_FROM_LEAD_EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De e-mail van de gerelateerde lead die is geconverteerd naar deze opportunity.</p>
        <p>Dit veld is niet ingesteld en retourneert null in Snowflake voor alle klanten.</p>
      </td>
      <td>
        <p>null</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PRIMARY_CONTACT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Als de Primaire Rol van het Contact wordt gebruikt, identiteitskaart van het verwante Contact die als primaire contactrol wordt vermeld.</p>
      </td>
      <td>
        <p>00331000038uGfhAAE</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PRIMARY_CONTACT_EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Als Primaire rol van het Contact wordt gebruikt, de e-mail van de verwante Contact die als primaire contactrol wordt vermeld.</p>
      </td>
      <td>
        <p>personb@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ODDS_OF_CONVERSION</p>
      </td>
      <td>
        <p>nummer (38,19)</p>
      </td>
      <td>
        <p>Deze functie is vervangen. Gebruik deze kolom niet.</p>
      </td>
      <td>
        <p>NVT</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_STAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Huidige fase van de Opportunity, zoals gedefinieerd in de [!DNL Marketo Measure] -toepassing.</p>
      </td>
      <td>
        <p>DM Demo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BIZIBLE_STAGE_PREVIOUS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Een tekenreeks met alle fasen die de Opportunity eerder heeft doorlopen, zoals gedefinieerd in de [!DNL Marketo Measure] -toepassing.</p>
      </td>
      <td>
        <p>Gekwalificeerde detectie, demo gepland</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of de record al dan niet wordt verwijderd in het bronsysteem.</p>
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Foreign Key to the Biz_Facts view.</p>
      </td>
      <td>
        <p>4609512587744160000</p>
      </td>
    </tr>
    <tr>
      <td>CURRENCY_ISO_CODE</td>
      <td>varchar</td>
      <td>ISO-code voor de valuta, geïmporteerd uit het bronsysteem.</td>
      <td>USD</td>
    </tr>
    <tr>
      <td>CURRENCY_ID</td>
      <td>getal (38,0)</td>
      <td>Id-waarde van de valuta voor de record.</td>
      <td>4609512587744160000</td>
    </tr>
    <tr>
      <td>CUSTOM_PROPERTIES</td>
      <td>varchar</td>
      <td>Aangepaste eigenschappen die [!DNL Marketo Measure] heeft geïmporteerd uit het bronsysteem, in JSON-indeling.</td>
      <td>{"Opportunity_Location__c":"Seattle", "Foo":"Bar"}</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td><b>*</b> MOPPORTUNITY_TYPE</td>
      <td>varchar</td>
      <td>Type van Kans, zoals Nieuwe Zaken, Verlenging, enz.</td>
      <td>Verlenging, vooruitzichten</td>
    </tr>
  </tbody>
</table>
<p>
<b> * </b> <i> slechts beschikbaar in Marketo Measure Ultimate </i>
<p>

### BIZ_OPP_STAGE_TRANSITIONS {#biz-opp-stage-transitions}

Werkgebiedovergangen voor opportunity.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Een unieke id voor de overgang.</p>
      </td>
      <td>
        <p>ST_0060Z0000nEgjlQAC_0030Z0003IjojKQAR_Demo Scheduled-1_BAT2_0060Z0000nEgjlQAC_0030Z Z00003IjojKQAR_2018-06-01:19-51-38-1685390.beec556e757</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id voor de account die aan de opportunity is gekoppeld.</p>
      </td>
      <td>
        <p>001310001b44nTAAK</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>OPPORTUNITY_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id voor de Opportunity die aan de overgang is gekoppeld.</p>
      </td>
      <td>
        <p>0060Z0000nEgjlQAC</p>
      </td>
    </tr>
    <tr>
      <td>CONTACT_ID</td>
      <td>varchar</td>
      <td>
        <p>Id voor de contactpersoon die aan de overgang is gekoppeld.</p>
      </td>
      <td>
        <p>0030Z0003IjojKQAR</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het opgegeven e-mailadres voor de betreffende contactpersoon.</p>
      </td>
      <td>
        <p>persone@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TOUCHPOINT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id voor de Buyer Attribution Touchpoint die aan de overgang is gekoppeld.</p>
      </td>
      <td>
        <p>BAT2_0060Z0000nEgjlQAC_0030Z0003IjojKQAR_2018-06-01:19-51-38-1685390.beb eg556e7757</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TRANSITION_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum waarop de record naar het werkgebied is overgebracht.</p>
      </td>
      <td>
        <p>2018-05-26 07 :29: 43.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>WERKGEBIED</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van het werkgebied voor de overgang.</p>
      </td>
      <td>
        <p>demo gepland</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>STAGE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id-waarde van het werkgebied voor de overgang.</p>
      </td>
      <td>
        <p>_bizible_FT</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>RANK</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>De numerieke positie van het werkgebied, zoals geordend in de instellingen voor werkgebiedtoewijzing van [!DNL Marketo Measure] .</p>
      </td>
      <td>
        <p>4</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>INDEX</p>
      </td>
      <td>
        <p>varchar(1)</p>
      </td>
      <td>
        <p>Wordt gebruikt in interne verwerking voor het indexeren en bestellen van boemerang-fasen.</p>
      </td>
      <td>1</td>
    </tr>
    <tr>
      <td>
        <p>LAST_INDEX</p>
      </td>
      <td>
        <p>varchar(1)</p>
      </td>
      <td>
        <p>Wordt gebruikt in interne verwerking voor het indexeren en bestellen van boemerang-fasen.</p>
      </td>
      <td>1</td>
    </tr>
    <tr>
      <td>
        <p>IS_PENDING</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Geeft aan of het aanraakpunt als in behandeling wordt beschouwd en nog niet is gesloten. Dit wordt alleen weergegeven voor klanten met het volledige toewijzingsmodel voor paden.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_NON_TRANSITIONAL</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Hiermee wordt aangegeven of de rij is gekoppeld aan een overgangsfase van een mijlpaal. Als er bijvoorbeeld drie fasen/ingangen (FT, LC, MQL) en vier aanraakpunten zijn, wordt het 1 aanraakpunt zonder een stadium op het punt beschouwd als "niet-tijdelijk", zodat de waarde gelijk is.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PREVIOUS_STAGE_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Overgangsdatum voor de vorige fase, volgens de positie van het werkgebied.</p>
      </td>
      <td>
        <p>2015-07-16 :41: 49.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NEXT_STAGE_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Overgangsdatum voor de volgende fase, volgens de positie van het werkgebied.</p>
      </td>
      <td>
        <p>2018-08-27 19 :40: 52.000</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum van laatste wijziging van de record.</p>
      </td>
      <td>
        <p>2018-08-28 03 :53: 33.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of de overgangsrecord wordt beschouwd als verwijderd.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_PAGE_VIEWS {#biz-page-views}

Paginaweergaven verzameld bij webbezoeken. Weergaven met meerdere pagina&#39;s kunnen één sessie samenstellen.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Een unieke id voor de paginaweergave.</p>
      </td>
      <td>
        <p>2018-08-19:16-49-58-24340.277d79d0167849</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COOKIE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De opgenomen cookie-id op het moment dat de paginaweergave werd geregistreerd.</p>
      </td>
      <td>
        <p>277d79d01678498fea067c9b631bf6df</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De eerste cookie van de verwante bezoeker-id.</p>
      </td>
      <td>
        <p>v_277d79d01678498fea067c9b631bf6df</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SESSION_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De sessie-id correleerde met de paginaweergave.</p>
      </td>
      <td>
        <p>2018-08-19:16-49-58-24340.277d79d0167849</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EVENT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de paginaweergave is opgetreden.</p>
      </td>
      <td>
        <p>2018-08-19 16 :49: 58.000</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de record voor het laatst is gewijzigd.</p>
      </td>
      <td>
        <p>2018-08-19 16 :55: 37.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CURRENT_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>URL van de paginaweergave, zonder queryparameters.</p>
      </td>
      <td>
        <p>https://info.adobe.com/demo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CURRENT_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>URL van de paginaweergave, inclusief queryparameters.</p>
      </td>
      <td>
        <p>https://info.adobe.com/demo?hsCtaTracking=207219e9-87b6-4105-8f4b-0a3b62ae1af8%7C48060522-3aeb-4c72-8ce5-fd4b1017f069</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IP_ADDRESS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het opgenomen IP-adres op het moment dat het formulier werd verzonden.</p>
      </td>
      <td>
        <p>174 127 184 158</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TYPE</p>
      </td>
      <td>varchar</td>
      <td>Geeft het type gebeurtenis aan.</td>
      <td>
        <p>PageView</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>USER_AGENT_STRING</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Apparaat en browser zijn opgenomen op het moment dat het formulier wordt verzonden.</p>
      </td>
      <td>
        <p>Mozilla/5.0 (X11; Linux x86_64; rv:52.0) Gecko/20100101 Firefox/52.0</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CLIENT_SEQUENCE</p>
      </td>
      <td>
        <p>varchar(1)</p>
      </td>
      <td>
        <p>Hiermee geeft u de volgorde aan waarin de paginaweergave is opgetreden tijdens de sessie.</p>
      </td>
      <td>
        <p>1</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CLIENT_RANDOM</p>
      </td>
      <td>varchar</td>
      <td>Wordt gebruikt voor interne controle en verwerking.</td>
      <td>
        <p>103532</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DUPLICATED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Hiermee wordt aangegeven of de record wordt beschouwd als een duplicaat.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>
        <p>IS_PROCESSED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Wordt gebruikt voor interne verwerking.</td>
      <td>true</td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>URL waar de Mening van de Pagina voortkwam van, zonder vraagparameters.</p>
      </td>
      <td>
        <p>http://info.adobe.com/cmos-guide-to-b2b-marketing-attribution</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>URL waarvan de paginaweergave afkomstig is, inclusief queryparameters.</p>
      </td>
      <td>
        <p>http://info.adobe.com/cmos-guide-to-b2b-marketing-attribution?utm_source=linkedin&amp;utm_medium=Social&amp;utm_campaign=SU%20-%20CMO%20JT&amp;utm_content=CMOs%20Guide&amp;utm_term=lisu05091601</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PAGINA_TITEL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Titel van de pagina.</p>
      </td>
      <td>
        <p>De Gids van de GMO aan de Download van de Attributen van de Marketing B2B</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>E-mailadres opgegeven op een formulier, zoals vastgelegd in het javascript.</p>
      </td>
      <td>personc@adobe.com</td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Foreign Key to the Biz_Facts view.</p>
      </td>
      <td>
        <p>-6255315750913680000</p>
      </td>
    </tr>
    <tr>
      <td>CURRENT_PAGE_KEY</td>
      <td>getal (38,0)</td>
      <td>External Key to the Url table.</td>
      <td>6255315750913680000</td>
    </tr>
    <tr>
      <td>REFERRER_PAGE_KEY</td>
      <td>getal (38,0)</td>
      <td>External Key to the Url table.</td>
      <td>6255315750913680000</td>
    </tr>
    <tr>
      <td>HAS_USER_CONSENT</td>
      <td>boolean</td>
      <td>Geeft aan of de gebruiker heeft ingestemd met bijhouden. Onwaar betekent dat de paginaweergave is verzameld omdat de toestemming van de gebruiker niet is vereist. True betekent dat de paginaweergave is verzameld en dat de gebruiker toestemming heeft gegeven om te worden bijgehouden.</td>
      <td>true</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_PLACEMENTS {#biz-placements}

Een tabel waarin alle locaties zijn opgeslagen die zijn gedownload van gekoppelde advertentierekeningen, een object van de Dubbelklik-integratie.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Een unieke id voor de plaatsing.</p>
      </td>
      <td>
        <p>ba.3284209.132855866,4556709270,10426699711</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td>De plaatsings-id van het bronsysteem.</td>
      <td>10426699711</td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id voor de advertentierekening waaruit de Plaatsing werd ingevoerd.</p>
      </td>
      <td>fb. 106851586409075</td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam voor de advertentierekening waaruit de Plaatsing werd ingevoerd.</p>
      </td>
      <td>[!DNL Marketo Measure]</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de Advertiser voor de Plaatsing, specifiek voor Doubleclick.</p>
      </td>
      <td>300184624</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de Adverteerder voor de Plaatsing, specifiek voor Doubleclick.</p>
      </td>
      <td>[!DNL Marketo Measure] Analytics</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Null verwacht omdat er geen Advertentiegroep boven het Plaatsen in om het even welke advertentiehiërarchie is.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Null verwacht omdat er geen Advertentiegroep boven het Plaatsen in om het even welke advertentiehiërarchie is.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de campagne voor de plaatsing.</p>
      </td>
      <td>ba.3284209.132855866</td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de campagne voor de plaatsing.</p>
      </td>
      <td>Afgifte via pijpleidingen</td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of de Plaatsing al dan niet nog in het bronsysteem actief is.</p>
      </td>
      <td>true</td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of de Plaatsing al dan niet in het bronsysteem is geschrapt.</p>
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de record voor het laatst is gewijzigd.</p>
      </td>
      <td>2018-08-02 06 :36: 25.000</td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum waarop de record voor het eerst uit het bronsysteem is geïmporteerd.</p>
      </td>
      <td>2018-08-02 06 :36: 25.000</td>
    </tr>
    <tr>
      <td>
        <p>NAAM</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de Plaatsing, van het bronsysteem.</p>
      </td>
      <td>Markt</td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of de plaatsing moet worden bijgewerkt voor [!DNL Marketo Measure] -tags.</p>
        <p>(Diagnostisch veld, wordt gebruikt door interne verwerking.)</p>
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>varchar</td>
      <td>Diagnostisch veld, voor interne verwerking.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het hoofdobject of de entiteit voor deze tabel. In dit geval, "Plaatsing".</p>
      </td>
      <td>Plaatsing</td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de advertentieprovider voor de plaatsing.</p>
      </td>
      <td>BingAds</td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Foreign Key to the Biz_Facts view.</p>
      </td>
      <td>6008900572523230000</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Door de Snowflake gemaakte datum van de record</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Gewijzigde datum van de record van de Snowflake</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake heeft de verwijderde datum van de record indien deze verwijderd is</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_SEGMENTEN {#biz-segments}

Segmentwaarden zoals gedefinieerd in de [!DNL Marketo Measure] -toepassing.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Een unieke id voor het segment.</p>
      </td>
      <td>
        <p>Nieuwe bedrijven</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAAM</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van het segment.</p>
      </td>
      <td>
        <p>Nieuwe bedrijven</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Foreign Key to the Biz_Facts view.</p>
      </td>
      <td>
        <p>1028715376434030000</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_SEGMENT_NAMES {#biz-segment-names}

Wijst de naam van het douanesegment aan het zijn categoriewaarde toe. (Hiermee worden de kolomnamen toegewezen aan de kolomkoppen Categorie1 - 15 in de aanraakpunttabellen.)

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Geeft de categorie aan waaraan de segmentnaam is toegewezen.</p>
      </td>
      <td>
        <p>CategorieOne</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de record voor het laatst is gewijzigd.</p>
      </td>
      <td>
        <p>2022-02-28 18 :12: 35.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SEGMENT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van het segment dat is toegewezen aan de categorie.</p>
      </td>
      <td>
        <p>1028715376434030000</p>
      </td>
    </tr>
    <tr>
      <td>IS_ACTIVE</td>
      <td>boolean</td>
      <td>Hiermee wordt aangegeven of de categorie in gebruik is.</td>
      <td>true</td>
    </tr>
    <tr>
      <td>IS_DELETED</td>
      <td>boolean</td>
      <td>Hiermee wordt aangegeven of de record wordt verwijderd.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_SESSIONS {#biz-sessions}

Sessies zijn verwerkt vanuit paginaweergaven. Weergaven met meerdere pagina&#39;s kunnen uit één sessie bestaan en één bezoeker-id kan aan meerdere sessies worden gekoppeld.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Een unieke id voor de sessie.</p>
      </td>
      <td>
        <p>2016-08-01:14-24-21-9079480.33163948f0a3</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De eerste cookie van de verwante bezoeker-id.</p>
      </td>
      <td>v_277d79d01678498fea067c9b631bf6df</td>
    </tr>
    <tr>
      <td>
        <p>COOKIE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De opgenomen cookie van de sessie.</p>
      </td>
      <td>277d79d01678498fea067c9b631bf6df</td>
    </tr>
    <tr>
      <td>
        <p>EVENT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum van de sessie.</p>
      </td>
      <td>
        <p>2016-08-01 14 :24: 21.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>GEWIJZIGDE DATUM</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de record voor het laatst is gewijzigd.</p>
      </td>
      <td>
        <p>2018-09-01 03 :49: 10.000</p>
      </td>
    </tr>
    <tr>
      <td>IS_FIRST_SESSION</td>
      <td>boolean</td>
      <td>Hiermee wordt aangegeven of dit de eerste sessie voor de bezoeker-id is.</td>
      <td>true</td>
    </tr>
    <tr>
      <td>
        <p>KANAAL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Kanaal dat is toegewezen aan de sessie, zoals gedefinieerd door de kanaaldefinities die zijn ingesteld in de toepassing [!DNL Marketo Measure] .</p>
      </td>
      <td>
        <p>Betaalde zoekopdracht.Advertentiewoorden</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PAGINA_TITEL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de webpagina.</p>
      </td>
      <td>
        <p>Salesforce Googles Analytics | [!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LANDING_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>URL van de eerste paginaweergave van de sessie, zonder queryparameters.</p>
      </td>
      <td>
        <p>http://www.adobe.com/salesforce-google-analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LANDING_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>URL van de eerste paginaweergave van de sessie, inclusief queryparameters.</p>
      </td>
      <td>
        <p>http://www.adobe.com/salesforce-google-analytics?_bt=83558988035&amp;_bk=google%20analytics%20salesforce&amp;_bm= p&amp;gclid=CMvd5YTLo84CFUI9gQodd-kLEQ</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>URL waar de Zitting voortkwam van, zonder vraagparameters.</p>
      </td>
      <td>
        <p>https://www.google.com/</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>URL waar de Zitting voortkwam van, met inbegrip van om het even welke vraagparameters.</p>
      </td>
      <td>
        <p>https://www.google.com/</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de verwijzingspagina.</p>
      </td>
      <td>
        <p>Google</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SEARCH_PHRASE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De waarde die de gebruiker heeft ingevoerd in de browser om te zoeken en op de website is beland.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] goochelarij</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>WEB_SOURCE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Hiermee definieert u de bron die het resultaat is van de sessie. Dit kan vanaf utm_source worden geparseerd of worden ingesteld op een advertentieprovider als [!DNL Marketo Measure] een advertentie kan oplossen.</p>
      </td>
      <td>
        <p>Google AdWords</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>HAS_FORM</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of de sessie een formuliervulling bevatte of niet;</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>HAS_CHAT</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of de Sessie al dan niet een webchat bevatte.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>HAS_EMAIL</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of de sessie een e-mailadres heeft of niet.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>HAS_CRM_ACTIVITY</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of de sessie al dan niet afkomstig is van een CRM-activiteitenrecord.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>APPARAAT</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De browser en het besturingssysteem van de gebruiker tijdens de sessie.</p>
      </td>
      <td>
        <p>Chrome (65.0), Windows (6.1)</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_PROVIDER</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het advertentieplatform [!DNL Marketo Measure] is opgelost, meestal een van onze integratiepartners.</p>
      </td>
      <td>
        <p>Google</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van advertentierekening waarvan de advertentie is opgelost.</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de advertentierekening waarvan de advertentie is opgelost.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van Advertiser de advertentie is opgelost, met name via de verbinding Doubleclick.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De naam van de adverteerder van wie de advertentie is opgelost, met name via de verbinding Doubleclick.</p>
      </td>
      <td>
        <p>Marketinganalyses</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de site waarvan de advertentie is opgelost. Dit geldt alleen voor Dubbelklik op Campagnebeheer.</p>
      </td>
      <td>
        <p>1695651</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de site waarvan de advertentie is opgelost. Dit geldt alleen voor Dubbelklik op Campagnebeheer.</p>
      </td>
      <td>
        <p>Quora.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van het Palement waarvan de advertentie is opgelost. Dit geldt alleen voor Dubbelklik op Campagnebeheer.</p>
      </td>
      <td>
        <p>120839827</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De naam van de locatie waar de advertentie is opgelost. Dit geldt alleen voor Dubbelklik op Campagnebeheer.</p>
      </td>
      <td>
        <p>wegblokkeren</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de campagne van de advertentie is opgelost.</p>
      </td>
      <td>
        <p>aw.6601259029.321586235</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De naam van de campagne waarvan de advertentie is opgelost.</p>
      </td>
      <td>
        <p>Webinar voor uw budget plannen</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de advertentiegroep waarvan de advertentie is opgelost. Dit geldt alleen voor Google Adwords.</p>
      </td>
      <td>
        <p>aw.6601259029.321586235.23182235435</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de advertentiegroep waaruit de advertentie is opgelost. Dit geldt alleen voor Google Adwords.</p>
      </td>
      <td>
        <p>SALESFORCE - GOOGLES ANALYTICS</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van advertentie is opgelost van. Dit geldt voor Dubbelklik op Campagne Manager en Facebook (display).</p>
      </td>
      <td>aw.6601259029.321586235.23182235435</td>
    </tr>
    <tr>
      <td>
        <p>AD_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De naam van de advertentie is opgelost. Dit geldt voor Dubbelklik op Campagne Manager en Facebook (display).</p>
      </td>
      <td>Winter promotie - groen</td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van Creative the Ad is opgelost vanuit. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht).</p>
      </td>
      <td>
        <p>aw.6601259029.321586235.23182235435.835898035</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De naam van de Creative the Ad is opgelost. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht).</p>
      </td>
      <td>
        <p>Integratie van GA en Salesforce</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_1</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De eerste regel van Creative van de zoekAdvertentie, getrokken uit de Advertentierekening waarin Advertentie werd opgelost van. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht).</p>
      </td>
      <td>
        <p>Salesforce en analyse integreren in</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_2</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De tweede regel van Creative van de zoekAdvertentie, getrokken uit de Advertentierekening waarin Advertentie werd opgelost van. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht).</p>
      </td>
      <td>
        <p>Optimaliseren voor inkomsten. Leer hoe.</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESTINATION_URL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De landingspagina die door van de onderzoekAdvertentie klikt, die van de Advertentierekening wordt getrokken waarin Advertentie werd opgelost. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht).</p>
      </td>
      <td>
        <p>http://www.adobe.com/salesforce-google-analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DISPLAY_URL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De vriendelijke URL-naam die wordt weergegeven in de zoekadvertentie en die wordt opgehaald van de advertentierekening waaruit de advertentie is opgelost. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht).</p>
      </td>
      <td>
        <p>adobe.com/Salesforce-for-GA</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van het trefwoord waarvan de advertentie is opgelost. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht).</p>
      </td>
      <td>
        <p>aw.6601259029.321586235.23182235435.35934468937</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van het trefwoord waarvan de advertentie is opgelost. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht).</p>
      </td>
      <td>
        <p>google analytics salesforce</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_MATCH_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het type overeenkomst dat wordt gevonden tussen de zoekuitdrukking en het aangekochte trefwoord.</p>
      </td>
      <td>
        <p>Woorden</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Geparseerd van de URL van utm_campagne.</p>
      </td>
      <td>
        <p>SU - ABC-accounts - Betaalde mediavaardigheden</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SOURCE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Geparseerd van URL van utm_source.</p>
      </td>
      <td>
        <p>gekoppeld</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MEDIUM</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Geparseerd van URL van utm_medium.</p>
      </td>
      <td>
        <p>Sociaal</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>TERM</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Geparseerd van de URL van utm_term.</p>
      </td>
      <td>
        <p>lisu07261601</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>INHOUD</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Geparseerd van de URL van utm_content.</p>
      </td>
      <td>
        <p>Verslag-Benchmark 2016</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>STAD</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De opgeloste stad van het IP adres.</p>
      </td>
      <td>Vancouver</td>
    </tr>
    <tr>
      <td>
        <p>REGIO</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het opgeloste gebied van het IP adres.</p>
      </td>
      <td>British Columbia</td>
    </tr>
    <tr>
      <td>
        <p>LAND</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het opgeloste land van het IP adres.</p>
      </td>
      <td>Canada</td>
    </tr>
    <tr>
      <td>
        <p>ISP_NAME</p>
      </td>
      <td>varchar</td>
      <td>Null verwacht omdat het veld verouderd is.</td>
      <td>
        <p>NULL</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IP_ADDRESS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het opgenomen IP-adres op het moment dat de sessie wordt gehouden.</p>
      </td>
      <td>
        <p>174 127 184 158</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Hiermee bepaalt u of deze sessie is samengevoegd met een andere sessie en moet worden verwijderd.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Foreign Key to the Biz_Facts view.</p>
      </td>
      <td>
        <p>-2712935512233520000</p>
      </td>
    </tr>
    <tr>
      <td>LANDING_PAGE_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>REFERRER_PAGE_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ACCOUNT_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ADVERTISER_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>SITE_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>PLACEMENT_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CAMPAIGN_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_GROUP_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CREATIVE_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>KEYWORD_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_SITES {#biz-sites}

Sites die zijn geïmporteerd uit een gekoppeld advertentieaccount.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Een unieke id voor de site.</p>
      </td>
      <td>aw.3284209</td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td>De site-id van het bronsysteem.</td>
      <td>39464932147</td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id voor de advertentieaccount waaruit de site is geïmporteerd.</p>
      </td>
      <td>aw.3284209</td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de advertentieaccount waaruit de site is geïmporteerd.</p>
      </td>
      <td>[!DNL Marketo Measure]</td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De id van de adverteerder voor de site, met name voor Doubleclick.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De naam van de adverteerder voor de site, met name voor Doubleclick.</p>
      </td>
      <td>
        <p>Marketinganalyses</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Null verwacht omdat er geen Advertentiegroep boven Site in enige advertentiehiërarchie is.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Null verwacht omdat er geen Advertentiegroep boven Site in enige advertentiehiërarchie is.</p>
      </td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de campagne voor de site.</p>
      </td>
      <td>
        <p>ba.3284209.132630532</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de campagne voor de site.</p>
      </td>
      <td>Revue-kenmerk</td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of de Site al dan niet nog actief is in het bronsysteem.</p>
      </td>
      <td>true</td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of de Site al dan niet is verwijderd in het bronsysteem.</p>
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de record voor het laatst is gewijzigd.</p>
      </td>
      <td>2018-08-02 06 :37: 29.000</td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum waarop de record voor het eerst uit het bronsysteem is geïmporteerd.</p>
      </td>
      <td>2018-08-02 06 :37: 29.000</td>
    </tr>
    <tr>
      <td>
        <p>NAAM</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de Plaats, van het bronsysteem.</p>
      </td>
      <td>Ontvangsten</td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of de site moet worden bijgewerkt voor [!DNL Marketo Measure] tagging.</p>
        <p>(Diagnostisch veld, gebruikt voor interne verwerking.)</p>
      </td>
      <td>false</td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>varchar</td>
      <td>Diagnostisch veld voor interne verwerking.</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het hoofdobject of de entiteit voor deze tabel. In dit geval "Site".</p>
      </td>
      <td>Vestiging</td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de advertentieprovider voor de site.</p>
      </td>
      <td>AdWords</td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Foreign Key to the Biz_Facts view.</p>
      </td>
      <td>
        <p>-2712935512233520000</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_SITE_LINKS {#biz-site-links}

Plaatst koppelingen van een verbonden advertentiekader.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Een unieke id voor de sitekoppeling</p>
      </td>
      <td>
        <p>aw.6601259029.285077795.1654234342</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>DISPLAY_ID</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td>
        <p>1654234342</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De id van de gekoppelde advertentie-account voor de sitekoppeling</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De naam van de verbonden advertenties is een account voor de sitekoppeling</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De id van de adverteerder voor de site-koppeling, met name voor Doubleclick.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De naam van de adverteerder voor de site-koppeling, met name voor Doubleclick.</p>
      </td>
      <td>
        <p>Marketinganalyses</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De id van de advertentiegroep voor de sitekoppeling</p>
      </td>
      <td>aw.6601259029.208548635.1675016675</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De naam van de advertentiegroep voor de sitekoppeling</p>
      </td>
      <td>Merk - Core</td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De id van de campagne voor de site-koppeling</p>
      </td>
      <td>
        <p>aw.6601259029.28507795</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De naam van de campagne voor de site-koppeling</p>
      </td>
      <td>
        <p>Merk</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_ACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of de site-koppeling al dan niet actief is in de account voor advertenties</p>
      </td>
      <td>
        <p>TRUE</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of de sitekoppeling al dan niet is verwijderd in de account voor advertenties</p>
      </td>
      <td>
        <p>FALSE</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De laatste gewijzigde datum van de rij</p>
      </td>
      <td>
        <p>2018-08-02 06 :36: 50.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_IMPORTED</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de sitekoppeling voor het eerst is gedownload [!DNL Marketo Measure]</p>
      </td>
      <td>
        <p>2018-08-02 06 :36: 50.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>NAAM</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De naam van de sitekoppeling</p>
      </td>
      <td>Koppeling A</td>
    </tr>
    <tr>
      <td>
        <p>NEEDS_UPDATE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of de site-koppeling moet worden bijgewerkt om de tag Marekto Meetlat te krijgen</p>
      </td>
      <td>
        <p>FALSE</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>GROUPING_KEY</p>
      </td>
      <td>varchar</td>
      <td></td>
      <td>
        <p>aw.6601259029.28507795</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ENTITY_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het hoofdobject of de entiteit voor deze tabel. In dit geval, "SiteLink"</p>
      </td>
      <td>
        <p>SiteLink</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PROVIDER_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De naam van de provider van advertenties voor de sitekoppeling</p>
      </td>
      <td>
        <p>AdWords</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>URL_CURRENT</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De URL voor de landingspagina.</p>
        <p>(Diagnostisch veld, voor interne verwerking.)</p>
      </td>
      <td>
        <p>http://adobe.com/b2b-marketing-attribution?_bt =</p>
        <p>{creative}&amp;_bk={keyword}&amp;_bm={matchType}</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>URL_OLD</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Vorige waarde voor URL_CURRENT.</p>
        <p>(Diagnostisch veld, voor interne verwerking.)</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>URL_REQUESTED</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Wat de URL zal worden versierd met [!DNL Marketo Measure] parameters.</p>
        <p>(Diagnostisch veld, voor interne verwerking.)</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Door de Snowflake gemaakte datum van de record</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Gewijzigde datum van de record van de Snowflake</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>Snowflake heeft de verwijderde datum van de record indien deze verwijderd is</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_STAGE_DEFINITIONS {#biz-stage-definitions}

Lijst met stadia die worden geïmporteerd of gedefinieerd in de [!DNL Marketo Measure] -toepassing.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Een unieke id voor het werkgebied.</p>
      </td>
      <td>
        <p>01J310000QE753EAD</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de record voor het laatst is gewijzigd.</p>
      </td>
      <td>
        <p>2018-08-22 17 :27: 27.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>STAGE_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van het werkgebied.</p>
      </td>
      <td>
        <p>Verticaal</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_INACTIVE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Geeft aan of het werkgebied als inactief wordt beschouwd.</td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_IN_CUSTOM_MODEL</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Hiermee wordt aangegeven of het werkgebied is geselecteerd om te worden bijgehouden in het aangepaste model.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_BOOMERANG</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Geeft aan of het werkgebied is geselecteerd om te worden bijgehouden als een boemerang-werkgebied.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_TRANSITION_TRACKING</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Geeft aan of het werkgebied is geselecteerd om overgangen bij te houden.</td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>STAGE_STATUS</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Status van het werkgebied, zoals gedefinieerd in de werkgebiedtoewijzing van de [!DNL Marketo Measure] -toepassing.</p>
      </td>
      <td>
        <p>Openen</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_FROM_SALESFORCE</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Geeft aan of het werkgebied wordt geïmporteerd uit een extern bronsysteem.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DEFAULT</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>Hiermee wordt aangegeven of het werkgebied als standaard is ingesteld.</td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>RANK</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>De numerieke positie van het werkgebied waarmee de stappen in de overgangsvolgorde worden gesorteerd.</p>
      </td>
      <td>
        <p>53</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of het werkgebied al dan niet is verwijderd.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_TOUCHPOINTS {#biz-touchpoints}

Aanraakpunten voor kopers, alle aanraakpunten die zijn gekoppeld aan een lead of contactpersoon. Deze tabel is leeg als Aanraakpunten op regelafstand of Aanraakpunten zijn uitgeschakeld.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Een unieke id voor de Buyer Touchpoint (BT).</p>
      </td>
      <td>
        <p>TP2_Person_00Q0Z000013e2PYUAY_2018-08-27:20-04-40-5655690.1ee8567c175a</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de record voor het laatst is gewijzigd.</p>
      </td>
      <td>
        <p>2018-08-29 22 :29: 30.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EMAIL</p>
      </td>
      <td>varchar</td>
      <td>E-mailadres dat aan de BT is gekoppeld.</td>
      <td>
        <p>person@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>CONTACT_ID</td>
      <td>varchar</td>
      <td>
        <p>Id voor de contactpersoon die aan de BT is gekoppeld.</p>
      </td>
      <td>0030Z0003K5bpKQAR</td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id voor de account die aan de BT is gekoppeld.</p>
      </td>
      <td>
        <p>001310001lSLScAO</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LEAD_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id voor de lead die aan de BT is gekoppeld.</p>
      </td>
      <td>
        <p>00Q0Z00013e2PYUAY</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>UNIQUE_ID_PERSON</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De ouderpersoonrecord die betrekking heeft op een lead of contactpersoon.</p>
      </td>
      <td>
        <p>Person_00Q0Z000013e2PYUAY</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>USER_TOUCHPOINT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id voor het aanraakpunt van de gebruiker dat de BT heeft gegenereerd.</p>
      </td>
      <td>
        <p>person@adobe.com_2018-08-29:18-14-53-8102030.10df92cbb414</p>
      </td>
    </tr>
    <tr>
      <td>VISITOR_ID</td>
      <td>varchar</td>
      <td>Id voor de bezoeker die aan de BT is gekoppeld.</td>
      <td>v_277d79d01678498fea067c9b631bf6df</td>
    </tr>
    <tr>
      <td>
        <p>TOUCHPOINT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>Datum van het aanraakpunt.</p>
      </td>
      <td>
        <p>2018-08-27 20 :04: 40.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MARKETING_TOUCH_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het type van activiteit, het Bezoek van het Web, de Vorm van het Web, het Praatje van het Web, de Vraag van de Telefoon, [CRM] Campagne, of [CRM] Activiteit. Wordt in de CRM aangeduid als "aanraakpunttype".</p>
      </td>
      <td>
        <p>Webformulier</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KANAAL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het kanaal waarin het aanraakpunt valt, zoals gedefinieerd in de aangepaste kanaaldefinities in de app [!DNL Marketo Measure] . Wordt in de CRM aangeduid als "Marketing Channel - Path".</p>
      </td>
      <td>Social.LinkedIn</td>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE1</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De segmentwaarde voor de eerste categorie waarin het aanraakpunt valt, zoals gedefinieerd in de segmentdefinities in de [!DNL Marketo Measure] -app. In de CRM aangeduid als "Segmenten".</p>
      </td>
      <td>ABC</td>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE2</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De segmentwaarde voor de tweede categorie waarin het aanraakpunt valt, zoals gedefinieerd in de segmentdefinities in de [!DNL Marketo Measure] -app. In de CRM aangeduid als "Segmenten".</p>
      </td>
      <td>
        <p>Ja</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE3</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De segmentwaarde voor de derde categorie waarin het aanraakpunt valt, zoals gedefinieerd in de segmentdefinities in de [!DNL Marketo Measure] -app. In de CRM aangeduid als "Segmenten".</p>
      </td>
      <td>
        <p>Anders</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE4</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De segmentwaarde voor de vierde categorie waarin het aanraakpunt valt, zoals gedefinieerd in de segmentdefinities in de [!DNL Marketo Measure] -app. In de CRM aangeduid als "Segmenten".</p>
      </td>
      <td>
        <p>Partner</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE5</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De segmentwaarde voor de vijfde categorie waarin het aanraakpunt valt, zoals gedefinieerd in de segmentdefinities in de [!DNL Marketo Measure] -app. In de CRM aangeduid als "Segmenten".</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE6</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De segmentwaarde voor de zesde categorie waarin het aanraakpunt valt, zoals gedefinieerd in de segmentdefinities in de [!DNL Marketo Measure] -app. In de CRM aangeduid als "Segmenten".</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE7</p>
      </td>
      <td>varchar</td>
      <td>De segmentwaarde voor de zevende categorie waarin het aanraakpunt valt, zoals gedefinieerd in de segmentdefinities in de [!DNL Marketo Measure] -app. In de CRM aangeduid als "Segmenten".</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE8</p>
      </td>
      <td>varchar</td>
      <td>De segmentwaarde voor de achtste categorie waarin het aanraakpunt valt, zoals gedefinieerd in de segmentdefinities in de [!DNL Marketo Measure] -app. In de CRM aangeduid als "Segmenten".</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE9</p>
      </td>
      <td>varchar</td>
      <td>De segmentwaarde voor de 9de categorie waarin het aanraakpunt valt, zoals gedefinieerd in de segmentdefinities in de [!DNL Marketo Measure] -app. In de CRM aangeduid als "Segmenten".</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE10</p>
      </td>
      <td>varchar</td>
      <td>De segmentwaarde voor de tiende categorie waarin het aanraakpunt valt, zoals gedefinieerd in de segmentdefinities in de [!DNL Marketo Measure] -app. In de CRM aangeduid als "Segmenten".</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE11</p>
      </td>
      <td>varchar</td>
      <td>De segmentwaarde voor de 11e categorie waarin het aanraakpunt valt, zoals gedefinieerd in de segmentdefinities in de [!DNL Marketo Measure] -app. In de CRM aangeduid als "Segmenten".</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE12</p>
      </td>
      <td>varchar</td>
      <td>De segmentwaarde voor de 12e categorie waarin het aanraakpunt valt, zoals gedefinieerd in de segmentdefinities in de [!DNL Marketo Measure] -app. In de CRM aangeduid als "Segmenten".</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE13</p>
      </td>
      <td>varchar</td>
      <td>De segmentwaarde voor de dertiende categorie waarin het aanraakpunt valt, zoals gedefinieerd in de segmentdefinities in de [!DNL Marketo Measure] -app. In de CRM aangeduid als "Segmenten".</td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE14</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De segmentwaarde voor de 14e categorie waarin het aanraakpunt valt, zoals gedefinieerd in de segmentdefinities in de [!DNL Marketo Measure] -app. In de CRM aangeduid als "Segmenten".</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>CATEGORIE15</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De segmentwaarde voor de 15e categorie waarin het aanraakpunt valt, zoals gedefinieerd in de segmentdefinities in de [!DNL Marketo Measure] -app. In de CRM aangeduid als "Segmenten".</p>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>BROWSER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Van javascript en IP adres, ontdekte browser dat de gebruiker tijdens de zitting was.</p>
      </td>
      <td>Chrome</td>
    </tr>
    <tr>
      <td>
        <p>BROWSER_VERSION</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Van javascript en IP adres, de ontdekte versie van browser die de gebruiker tijdens de zitting was.</p>
      </td>
      <td>
        <p>68</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLATFORM_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Van javascript en IP adres, het ontdekte platform dat de gebruiker tijdens de zitting was.</p>
      </td>
      <td>
        <p>Windows</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLATFORM_VERSION</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Van javascript en IP adres, de ontdekte versie van het platform dat de gebruiker tijdens de zitting was.</p>
      </td>
      <td>10_12</td>
    </tr>
    <tr>
      <td>
        <p>LANDING_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De eerste openingspagina van de sessie die tot een aanraakpunt heeft geleid. Wordt in de CRM aangeduid als "Landing Page".</p>
      </td>
      <td>
        <p>https://info.adobe.com/definitive-guide-to-pipeline-marketing</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LANDING_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De eerste openingspagina van de sessie die tot een aanraakpunt heeft geleid. Een onbewerkte bestemmingspagina bevat alle queryparameters in de URL. In de CRM aangeduid als "Landing Page - Raw".</p>
      </td>
      <td>
        <p>https://info.adpbe.com/definitive-guide-to-pipeline-marketing?utm_source=linkedin&amp;utm_medium=Social&amp;utm_campaign=SU_COM_Demand_ Skills&amp;utm_content=DGPM&amp;utm_term=lisu03151846&amp;_bl=66452504</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Doorgaans de externe bestemmingspagina vlak voordat de gebruiker op de website komt. Wordt in de CRM aangeduid als "Referrer Page".</p>
      </td>
      <td>https://www.linkedin.com/</td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Doorgaans de externe bestemmingspagina vlak voordat de gebruiker op de website komt. Een onbewerkte verwijzingspagina kan queryparameters in de URL bevatten. Wordt in de CRM aangeduid als "Referrer Page - Raw".</p>
      </td>
      <td>
        <p>https://www.linkedin.com/feed</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het eerste formulier dat is opgenomen in een sessie en dat heeft geresulteerd in een aanraakpunt. Verdere formulierverzendingen worden niet weergegeven in de tabel Touchpoints, maar in de tabel Form_Submits. Wordt in de CRM aangeduid als "formulier-URL".</p>
      </td>
      <td>
        <p>https://info.adobe.com/demo</p>
      </td>
    </tr>
    <tr>
      <td>FORM_PAGE_RAW</td>
      <td>varchar</td>
      <td>Het eerste formulier dat is opgenomen in een sessie en dat heeft geresulteerd in een aanraakpunt. Verdere formulierverzendingen worden niet weergegeven in de tabel Touchpoints, maar in de tabel Form_Submits. Een onbewerkte formulierpagina kan queryparameters in de URL bevatten. Wordt in de CRM aangeduid als "Form URL - Raw".</td>
      <td>https://info.adobe.com/demo?hsCtaTracking=98adcc2f-afe2-40c4-9d79-40dcc41663ee%7C3cfaa909-39cb-4f5d-93eb-be05de6b0180</td>
    </tr>
    <tr>
      <td>
        <p>FORM_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop het formulier is verzonden.</p>
      </td>
      <td>
        <p>2017-06-20 01 :06: 41.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>STAD</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Van javascript en IP adres, de ontdekte plaats de gebruiker binnen tijdens de zitting was.</p>
      </td>
      <td>
        <p>New York</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REGIO</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Van javascript en IP adres, het ontdekte gebied de gebruiker binnen tijdens de zitting was.</p>
      </td>
      <td>
        <p>New York</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAND</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Van javascript en IP adres, het ontdekte land de gebruiker binnen tijdens de zitting was.</p>
      </td>
      <td>
        <p>Verenigde Staten</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MEDIUM</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Hiermee definieert u het medium dat tot het aanraakpunt heeft geleid. Dit kan worden geparseerd vanaf de URL vanaf utm_medium. Of als [!DNL Marketo Measure] een advertentie kan oplossen, kan het waarden zijn zoals "cpc" of "display".</p>
      </td>
      <td>
        <p>Sociaal</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>WEB_SOURCE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Hiermee definieert u de bron die het aanraakpunt heeft veroorzaakt. Dit kan uit URL van utm_source worden ontleed, algemeen geplaatst als "Campaign van CRM"als het van CRM werd gesynchroniseerd, of als [!DNL Marketo Measure] een advertentie kan oplossen, kan het waarden zoals "Google AdWords"of "Facebook zijn." Wordt in de CRM aangeduid als "Touchpoint Source".</p>
      </td>
      <td>
        <p>LinkedIn</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SEARCH_PHRASE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De waarde die de gebruiker in de browser heeft ingevoerd om naar de website te zoeken en op de website is geëindigd. Afhankelijk van het trefwoord dat wordt gekocht, komt dit mogelijk wel of niet overeen met de trefwoorden die zijn aangeschaft op het platform Betaalde zoekopdracht.</p>
      </td>
      <td>
        <p>toewijzing markeringsmaatregel</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_PROVIDER</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Adplatform [!DNL Marketo Measure] kon oplossen van, typisch één van onze integratiepartners.</p>
      </td>
      <td>
        <p>LinkedIn</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van advertentierekening waarvan de advertentie is opgelost.</p>
      </td>
      <td>
        <p>li,502664737</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de advertentierekening waaruit de advertentie is opgelost.</p>
      </td>
      <td>
        <p>MM SC 2016_14605342_3/7-3/31/16</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de adverteerder van de advertentierekening waarin de advertentie is opgelost. Dit geldt alleen voor Dubbelklik op Campagnebeheer.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de adverteerder van de advertentierekening waarin de advertentie is opgelost. Dit geldt alleen voor Dubbelklik op Campagnebeheer.</p>
      </td>
      <td>
        <p>Marketo Marketing Analytics</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de site van de advertentieaccount waaruit de advertentie is opgelost. Dit geldt alleen voor Dubbelklik op Campagnebeheer.</p>
      </td>
      <td>
        <p>1695651</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de site van de advertentierekening waaruit de advertentie is opgelost. Dit geldt alleen voor Dubbelklik op Campagnebeheer.</p>
      </td>
      <td>
        <p>Quora.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de Plaatsing van de Advertentierekening waarin de Advertentie van werd opgelost. Dit geldt alleen voor Dubbelklik op Campagnebeheer.</p>
      </td>
      <td>
        <p>120839827</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de Plaatsing van de Advertentierekening waarin de Advertentie van werd opgelost. Dit geldt alleen voor Dubbelklik op Campagnebeheer.</p>
      </td>
      <td>
        <p>wegblokkeren</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de campagne van de advertentierekening waar de Advertentie van werd opgelost.</p>
      </td>
      <td>
        <p>li.502664737.138949954</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de campagne van de advertentierekening waarin Advertentie werd opgelost van.</p>
      </td>
      <td>
        <p>SU - COM-accounts - vraagvaardigheden</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de Advertentiegroep van de Advertentierekening waarin de Advertentie van werd opgelost. Dit geldt alleen voor Google Adwords.</p>
      </td>
      <td>aw.6601259029.317738075.23105327435</td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de Advertentiegroep van de Advertentierekening waarin de Advertentie werd opgelost van. Dit geldt alleen voor Google AdWords.</p>
      </td>
      <td>Marketing Attribution - General</td>
    </tr>
    <tr>
      <td>
        <p>AD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de advertentie van de advertentierekening waarin de advertentie is opgelost. Dit geldt voor Dubbelklik op Campagne Manager en Facebook (display).</p>
      </td>
      <td>dc.6114.882972.25272734.492579576</td>
    </tr>
    <tr>
      <td>
        <p>AD_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de advertentie van de advertentierekening waarin de advertentie is opgelost. Dit geldt voor Dubbelklik op Campagne Manager en Facebook (display).</p>
      </td>
      <td>Webinar - zijbalk</td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van Creative van de advertentie-account waaruit de advertentie is opgelost. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht).</p>
      </td>
      <td>
        <p>li.502664737.138949954.66452504</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De naam van de Creative vanuit het advertentieaccount waaruit de advertentie is opgelost. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht).</p>
      </td>
      <td>
        <p>lisu03151846</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_1</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De eerste regel van Creative van de zoekAdvertentie, getrokken uit de Advertentierekening waarin Advertentie werd opgelost van. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht).</p>
      </td>
      <td>
        <p>Loodgen wordt uitgevoerd</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_2</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De tweede regel van Creative van de zoekAdvertentie, getrokken uit de Advertentierekening waarin Advertentie werd opgelost van. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht).</p>
      </td>
      <td>
        <p>Download de definitieve gids aan pijpleiding marketing: https://lnkd.in/e9xYj5M</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESTINATION_URL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De landingspagina die door van de onderzoekAdvertentie klikt, die van de Advertentierekening wordt getrokken waarin Advertentie werd opgelost. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht).</p>
      </td>
      <td>
        <p>https://image-store.slidesharecdn.com/d29165c0-1e0b-4ffc-a494-d2c77e7cd4a6-large.jpeg</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DISPLAY_URL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De vriendelijke URL-naam die wordt weergegeven in de zoekadvertentie en die wordt opgehaald van de advertentierekening waaruit de advertentie is opgelost. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht).</p>
      </td>
      <td>
        <p>marektomeasure.com/guide</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De id van het trefwoord dat is aangeschaft bij de aankoop van de Betaalde zoekopdracht, is opgehaald van de advertentieaccount waarvan de advertentie is opgelost. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht).</p>
      </td>
      <td>
        <p>__GAId__lisu03151846</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van het trefwoord dat is aangeschaft bij de aankoop van de Betaalde zoekopdracht en dat is opgehaald van de advertentieaccount waarvan de advertentie is opgelost. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht)</p>
      </td>
      <td>
        <p>lisu03151846</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_MATCH_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het type overeenkomst dat wordt gevonden tussen de zoekuitdrukking en het aangekochte trefwoord.</p>
      </td>
      <td>
        <p>Breed</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_FIRST_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of dit aanraakpunt al dan niet wordt beschouwd als de eerste aanraking van de opportuniteitsreis.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_LEAD_CREATION_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of dit aanraakpunt al dan niet wordt beschouwd als de belangrijkste aanzet tot de opportuniteitsreis.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_OPP_CREATION_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of dit aanraakpunt al dan niet wordt beschouwd als de kans om de opportuniteitsreis te creëren.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_CLOSED_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of dit aanraakpunt al dan niet wordt beschouwd als een gesloten aanraking van de opportuniteitsreis.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>STAGES_TOUCHED</td>
      <td>varchar</td>
      <td>Dit veld is vervangen. Gebruik de tabellen Stage_Transitions voor werkgebiedinformatie.</td>
      <td>null</td>
    </tr>
    <tr>
      <td>
        <p>IS_FORM_SUBMISSION_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of dit aanraakpunt tijdens de sessie al dan niet een formuliervulling had.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_IMPRESSION_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of dit aanraakpunt al dan niet wordt beschouwd als de eerste indruk van de opportuniteitsreis</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FIRST_CLICK_PERCENTAGE</p>
      </td>
      <td>
        <p>nummer(22,19)</p>
      </td>
      <td>
        <p>Het berekende percentage dat aan dit aanraakpunt is toegewezen omdat het een eerste aanraking is (Zie Is_First_Touch).</p>
      </td>
      <td>
        <p>100</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAST_ANON_CLICK_PERCENTAGE</p>
      </td>
      <td>
        <p>nummer(22,19)</p>
      </td>
      <td>
        <p>Het berekende percentage dat is toegewezen aan dit aanraakpunt, omdat het een aanraakaanraakaanraakaanraakvlak is (zie Is_Lead_Creation_Touch).</p>
      </td>
      <td>
        <p>100</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>U_SHAPE_PERCENTAGE</p>
      </td>
      <td>
        <p>nummer(22,19)</p>
      </td>
      <td>
        <p>Het berekende percentage dat aan dit aanraakpunt is toegewezen omdat het deel uitmaakt van een u-vormige aanraking (zie Is_First_Touch en Is_Lead_Creation_Touch).</p>
      </td>
      <td>
        <p>100</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>W_SHAPE_PERCENTAGE</p>
      </td>
      <td>
        <p>nummer(22,19)</p>
      </td>
      <td>
        <p>Het berekende percentage dat aan dit aanraakpunt is toegewezen omdat het deel uitmaakt van een w-vormige aanraking (zie Is_First_Touch, Is_Lead_Creation_Touch en Is_Opp_Creation_Touch). De verwachting is 0 omdat dit een BT is.</p>
      </td>
      <td>
        <p>0</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FULL_PATH_PERCENTAGE</p>
      </td>
      <td>
        <p>nummer(22,19)</p>
      </td>
      <td>
        <p>Het berekende percentage dat aan dit aanraakpunt wordt toegewezen omdat het deel uitmaakt van een volledig padmodel (zie Is_First_Touch, Is_Lead_Creation_Touch, Is_Opp_Creation_Touch, Is_Closed_Touch). De verwachting is 0 omdat dit een BT is.</p>
      </td>
      <td>
        <p>0</p>
      </td>
    </tr>
    <tr>
      <td>CUSTOM_MODEL_PERCENTAGE</td>
      <td>nummer(22,19)</td>
      <td>Het berekende percentage dat aan dit aanraakpunt wordt toegewezen omdat het deel uitmaakt van een aangepast model (zie Is_First_Touch, Is_Lead_Creation_Touch, Is_Opp_Creation_Touch, Is_Closed_Touch). De verwachting is 0 omdat dit een BT is.</p>
      </td>
      <td>0</td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Hiermee wordt aangegeven of dit aanraakpunt wordt verwijderd.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ROW_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td>
        <p>Foreign Key to the Biz_Facts view.</p>
      </td>
      <td>
        <p>-9004910726709710000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CONTACT_ROW_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <p>LEAD_ROW_KEY</p>
      </td>
      <td>
        <p>getal (38,0)</p>
      </td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>LANDING_PAGE_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>REFERRER_PAGE_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>FORM_PAGE_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ACCOUNT_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ADVERISER_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>SITE_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>PLACEMENT_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CAMPAIGN_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_GROUP_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CREATIVE_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>KEYWORD_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_URLS {#biz-urls}

Samenvoeging van URL&#39;s van bestemmingspagina&#39;s, verwijzingspagina&#39;s, en paginameningen.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
      <td>ID</td>
      <td>varchar</td>
      <td>De volledige URL.</td>
      <td>https://www.adobe.com/blog/strategic-marketing-plangoals</td>
    </tr>
    <tr>
      <td>SCHEMA</td>
      <td>varchar</td>
      <td>De veilige communicatie van de webpagina via het netwerk.</td>
      <td>https</td>
    </tr>
    <tr>
      <td>HOST</td>
      <td>varchar</td>
      <td>Het domein van de URL, met alle subdomeinen.</td>
      <td>www.adobe.com</td>
    </tr>
    <tr>
      <td>PAGINA_TITEL</td>
      <td>varchar</td>
      <td>Titel van de pagina.</td>
      <td>De Gids van de GMO aan de Download van de Attributen van de Marketing B2B</td>
    </tr>
    <tr>
      <td>PAD</td>
      <td>varchar</td>
      <td>Het gedeelte van de URL dat naar een specifieke locatie op de host verwijst.</td>
      <td>/blog/strategische-marketing-planGoals</td>
    </tr>
    <tr>
      <td>POORT</td>
      <td>varchar</td>
      <td>De poort van een internethost, optioneel in een URL.</td>
      <td>584</td>
    </tr>
    <tr>
      <td>ROW_KEY</td>
      <td>getal (38,0)</td>
      <td>Foreign Key to the Biz_Facts view.</td>
      <td>5686109553536636820</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_USER_TOUCHPOINTS {#biz-user-touchpoints}

Alle aanraakpunten die zijn gemaakt op basis van een gebeurtenis die aan een e-mail is gekoppeld.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>
        <p>Een unieke id voor het aanraakpunt voor de gebruiker.</p>
      </td>
      <td>
        <p>person@adobe.com_2018-01-05:16-47-02-8803320.ddf67c101f58</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de record voor het laatst is gewijzigd.</p>
      </td>
      <td>
        <p>2018-09-05 23 :30: 53.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>EMAIL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>E-mailadres dat is gekoppeld aan het aanraakpunt van de gebruiker.</p>
      </td>
      <td>
        <p>person@adobe.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SESSION_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id voor de sessie waarmee het aanraakpunt voor de gebruiker is gemaakt.</p>
      </td>
      <td>
        <p>2018-01-05:16-47-02-8803320.ddf67c101f58</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_LID_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id voor het Campagne Lid dat tot het Aanraakpunt van de Gebruiker leidde.</p>
      </td>
      <td>
        <p>00v0Z0001VTgv1QAD</p>
      </td>
    </tr>
    <tr>
      <td>CRM_ACTIVITY_ID</td>
      <td>varchar</td>
      <td>Id voor de activiteit die het aanraakpunt voor de gebruiker heeft gemaakt.</td>
      <td>1678625515</td>
    </tr>
    <tr>
      <td>
        <p>CRM_EVENT_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id voor de gebeurtenis die het aanraakpunt voor de gebruiker heeft gemaakt.</p>
      </td>
      <td>
        <p>00U0Z0000pCZmyUAG</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CRM_TASK_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>TId voor de Taak die tot het Aanraakpunt van de Gebruiker leidde.</p>
      </td>
      <td>
        <p>00T0Z0004Qbd1jUAB</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IMPRESSION_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id voor de Indruk die tot het Aanraakpunt van de Gebruiker leidde.</p>
      </td>
      <td>00T0Z0004Qbd1jUAB</td>
    </tr>
    <tr>
      <td>IS_FIRST_KNOWN_TOUCH</td>
      <td>boolean</td>
      <td>Of dit aanraakpunt al dan niet wordt beschouwd als de eerste aanraking van de opportuniteitsreis.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>VISITOR_ID</td>
      <td>varchar</td>
      <td>De eerste cookie-id van de verwante bezoeker-id.</td>
      <td>v_36ec805b4db344d6e92c972c86aee34a</td>
    </tr>
    <tr>
      <td>
        <p>TOUCHPOINT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop het aanraakpunt voor de gebruiker is opgetreden.</p>
      </td>
      <td>
        <p>2018-01-05 16 :47: 02.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MARKETING_TOUCH_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het type van activiteit, het Bezoek van het Web, de Vorm van het Web, het Praatje van het Web, de Vraag van de Telefoon, [CRM] Campagne, of [CRM] Activiteit. Wordt in de CRM aangeduid als "aanraakpunttype".</p>
      </td>
      <td>
        <p>Webformulier</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KANAAL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het kanaal waarin het aanraakpunt valt, zoals gedefinieerd in de aangepaste kanaaldefinities in de app [!DNL Marketo Measure] . Wordt in de CRM aangeduid als "Marketing Channel - Path".</p>
      </td>
      <td>
        <p>Social.LinkedIn</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BROWSER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Van javascript en IP adres, ontdekte browser dat de gebruiker tijdens de zitting was.</p>
      </td>
      <td>
        <p>Firefox</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>BROWSER_VERSION</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Van javascript en IP adres, de ontdekte versie van browser die de gebruiker tijdens de zitting was.</p>
      </td>
      <td>
        <p>33</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLATFORM_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Van javascript en IP adres, het ontdekte platform dat de gebruiker tijdens de zitting was.</p>
      </td>
      <td>
        <p>Mac</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLATFORM_VERSION</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Van javascript en IP adres, de ontdekte versie van het platform dat de gebruiker tijdens de zitting was.</p>
      </td>
      <td>
        <p>10_12</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LANDING_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De eerste openingspagina van de sessie die tot een aanraakpunt heeft geleid. Wordt in de CRM aangeduid als "Landing Page".</p>
      </td>
      <td>
        <p>https://www.adobe.com/blog/budget-and-planning-maturity-model-b2b-marketing</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LANDING_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De eerste openingspagina van de sessie die tot een aanraakpunt heeft geleid. Een onbewerkte bestemmingspagina bevat alle queryparameters in de URL. In de CRM aangeduid als "Landing Page - Raw".</p>
      </td>
      <td>
        <p>https://www.adobe.com/blog/budget-and-planning-maturity-model-b2b-marketing?utm_source=feedburner&amp;utm_medium=feed&amp;utm_campaign=Feed%3A+ markto+%maat%27s+Pipeline+Marketing+blog%29</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Doorgaans de externe bestemmingspagina vlak voordat de gebruiker op de website komt. Wordt in de CRM aangeduid als "Referrer Page".</p>
      </td>
      <td>
        <p>https://www.google.com/</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REFERRER_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Doorgaans de externe bestemmingspagina vlak voordat de gebruiker op de website komt. Een onbewerkte verwijzingspagina kan queryparameters in de URL bevatten. Wordt in de CRM aangeduid als "Referrer Page - Raw".</p>
      </td>
      <td>
        <p>https://www.google.com/</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_PAGE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het eerste formulier dat is opgenomen in een sessie en dat heeft geresulteerd in een aanraakpunt. Verdere formulierverzendingen worden niet weergegeven in de tabel Attribution_Touchpoints, maar in de tabel Form_Submits. Wordt in de CRM aangeduid als "formulier-URL".</p>
      </td>
      <td>
        <p>http://info.adobe.com/adwords-for-lead-generation</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_PAGE_RAW</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het eerste formulier dat is opgenomen in een sessie en dat heeft geresulteerd in een aanraakpunt. Verdere formulierverzendingen worden niet weergegeven in de tabel Attribution_Touchpoints, maar in de tabel Form_Submits. Een onbewerkte formulierpagina kan queryparameters in de URL bevatten. Wordt in de CRM aangeduid als "Form URL - Raw".</p>
      </td>
      <td>
        <p>http://info.adobe.com/adwords-for-lead-generation?utm_source=linkedin&amp;utm_medium=paid&amp;utm_content=sfskill&amp;utm_campagne=Content%20-%20adWords%20Guide</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>FORM_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop het formulier is verzonden.</p>
      </td>
      <td>
        <p>2015-06-03 17 :49: 10.000</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>STAD</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Van javascript en IP adres, de ontdekte plaats de gebruiker binnen tijdens de zitting was.</p>
      </td>
      <td>
        <p>Oakland</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>REGIO</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Van javascript en IP adres, het ontdekte gebied de gebruiker binnen tijdens de zitting was.</p>
      </td>
      <td>
        <p>California</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>LAND</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Van javascript en IP adres, het ontdekte land de gebruiker binnen tijdens de zitting was.</p>
      </td>
      <td>
        <p>Verenigde Staten</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>MEDIUM</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Hiermee definieert u het medium dat tot het aanraakpunt heeft geleid. Dit kan worden geparseerd vanaf de URL vanaf utm_medium. Of als [!DNL Marketo Measure] een advertentie kan oplossen, kan het waarden zijn zoals "cpc" of "display".</p>
      </td>
      <td>
        <p>betaald</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>WEB_SOURCE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Hiermee definieert u de bron die het aanraakpunt heeft veroorzaakt. Dit kan uit URL van utm_source worden ontleed, algemeen geplaatst als "Campaign van CRM"als het van CRM werd gesynchroniseerd, of als [!DNL Marketo Measure] een advertentie kan oplossen, kan het waarden zoals "Google AdWords"of "Facebook zijn." Wordt in de CRM aangeduid als "Touchpoint Source".</p>
      </td>
      <td>
        <p>gekoppeld</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SEARCH_PHRASE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De waarde die de gebruiker in de browser heeft ingevoerd om naar de website te zoeken en op de website is geëindigd. Afhankelijk van het trefwoord dat wordt gekocht, komt dit mogelijk wel of niet overeen met de trefwoorden die zijn aangeschaft op het platform Betaalde zoekopdracht.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_PROVIDER</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Adplatform [!DNL Marketo Measure] kon oplossen van, typisch één van onze integratiepartners.</p>
      </td>
      <td>
        <p>Google</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van advertentierekening waarvan de advertentie is opgelost.</p>
      </td>
      <td>
        <p>aw.6601259029</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ACCOUNT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de advertentierekening waaruit de advertentie is opgelost.</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] Account</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de adverteerder van de advertentierekening waarin de advertentie is opgelost. Dit geldt alleen voor Dubbelklik op Campagnebeheer.</p>
      </td>
      <td>
        <p>300181641</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>ADVERTISER_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de adverteerder van de advertentierekening waarin de advertentie is opgelost. Dit geldt alleen voor Dubbelklik op Campagnebeheer.</p>
      </td>
      <td>
        <p>Marketinganalyses</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de site van de advertentieaccount waaruit de advertentie is opgelost. Dit geldt alleen voor Dubbelklik op Campagnebeheer.</p>
      </td>
      <td>
        <p>1695651</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>SITE_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de site van de advertentierekening waaruit de advertentie is opgelost. Dit geldt alleen voor Dubbelklik op Campagnebeheer.</p>
      </td>
      <td>
        <p>Quora.com</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de Plaatsing van de Advertentierekening waarin de Advertentie van werd opgelost. Dit geldt alleen voor Dubbelklik op Campagnebeheer.</p>
      </td>
      <td>
        <p>120839827</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>PLACEMENT_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de Plaatsing van de Advertentierekening waarin de Advertentie van werd opgelost. Dit geldt alleen voor Dubbelklik op Campagnebeheer.</p>
      </td>
      <td>
        <p>wegblokkeren</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de campagne van de advertentierekening waar de Advertentie van werd opgelost.</p>
      </td>
      <td>
        <p>aw.6601259029.208548635</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CAMPAIGN_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de campagne van de advertentierekening waarin Advertentie werd opgelost van.</p>
      </td>
      <td>
        <p>Merk</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de Advertentiegroep van de Advertentierekening waarin de Advertentie van werd opgelost. Dit geldt alleen voor Google Adwords.</p>
      </td>
      <td>
        <p>aw.6601259029.208548635.1675016675</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_GROUP_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de Advertentiegroep van de Advertentierekening waarin de Advertentie werd opgelost van. Dit geldt alleen voor Google AdWords.</p>
      </td>
      <td>
        <p>Merk - Core</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>AD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van de advertentie van de advertentierekening waarin de advertentie is opgelost. Dit geldt voor Dubbelklik op Campagne Manager en Facebook (display).</p>
      </td>
      <td>dc.6114.882972.25272734.492579576</td>
    </tr>
    <tr>
      <td>
        <p>AD_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van de advertentie van de advertentierekening waarin de advertentie is opgelost. Dit geldt voor Dubbelklik op Campagne Manager en Facebook (display).</p>
      </td>
      <td>Webinar - zijbalk</td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Id van Creative van de advertentie-account waaruit de advertentie is opgelost. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht).</p>
      </td>
      <td>
        <p>aw.6601259029.208548635.1675016675.195329631298</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De naam van de Creative vanuit het advertentieaccount waaruit de advertentie is opgelost. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht).</p>
      </td>
      <td>
        <p>[!DNL Marketo Measure] Officiële site</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_1</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De eerste regel van Creative van de zoekAdvertentie, getrokken uit de Advertentierekening waarin Advertentie werd opgelost van. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht).</p>
      </td>
      <td>
        <p>Ontvangsten plannen en toewijzen</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESCRIPTION_2</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De tweede regel van Creative van de zoekAdvertentie, getrokken uit de Advertentierekening waarin Advertentie werd opgelost van. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht).</p>
      </td>
      <td>
        <p>Lees waarom meer dan 250 bedrijven [!DNL Marketo Measure] kiezen voor marketingtoewijzing. Maak een demo!</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DESTINATION_URL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De landingspagina die door van de onderzoekAdvertentie klikt, die van de Advertentierekening wordt getrokken waarin Advertentie werd opgelost. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht).</p>
      </td>
      <td>
        <p>http://info.adobe.com/demo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>CREATIVE_DISPLAY_URL</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De vriendelijke URL-naam die wordt weergegeven in de zoekadvertentie en die wordt opgehaald van de advertentierekening waaruit de advertentie is opgelost. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht).</p>
      </td>
      <td>
        <p>adobe.com/demo</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_UNIQUE_ID</p>
      </td>
      <td>varchar</td>
      <td>
        <p>De id van het trefwoord dat is aangeschaft bij de aankoop van de Betaalde zoekopdracht, is opgehaald van de advertentieaccount waarvan de advertentie is opgelost. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht).</p>
      </td>
      <td>
        <p>aw.6601259029.208548635.1675016675.46267805426</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_NAME</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Naam van het trefwoord dat is aangeschaft bij de aankoop van de Betaalde zoekopdracht en dat is opgehaald van de advertentieaccount waarvan de advertentie is opgelost. Dit geldt voor Google AdWords en Bing Ads (zoekopdracht)</p>
      </td>
      <td>
        <p>[markeren]</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>KEYWORD_MATCH_TYPE</p>
      </td>
      <td>varchar</td>
      <td>
        <p>Het type overeenkomst dat wordt gevonden tussen de zoekuitdrukking en het aangekochte trefwoord.</p>
      </td>
      <td>
        <p>Exact</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_FORM_SUBMISSION_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of dit aanraakpunt tijdens de sessie al dan niet een formuliervulling had.</p>
      </td>
      <td>
        <p>true</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_IMPRESSION_TOUCH</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Of dit aanraakpunt al dan niet wordt beschouwd als de eerste indruk van de opportuniteitsreis.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>IS_DELETED</p>
      </td>
      <td>
        <p>boolean</p>
      </td>
      <td>
        <p>Bepaalt of het aanraakpunt wordt verwijderd.</p>
      </td>
      <td>
        <p>false</p>
      </td>
    </tr>
    <tr>
      <td>ROW_KEY</td>
      <td>getal (38,0)</td>
      <td>Foreign Key to the Biz_Facts view.</td>
      <td>-5269090762570690000</td>
    </tr>
    <tr>
      <td>LANDING_PAGE_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>REFERRER_PAGE_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>FORM_PAGE_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ACCOUNT_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>ADVERISER_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>SITE_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>PLACEMENT_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CAMPAIGN_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>AD_GROUP_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>CREATIVE_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>KEYWORD_ROW_KEY</td>
      <td>getal (38,0)</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

### BIZ_WEB_HOST_MAPPINGS {#biz-web-host-mappings}

Tabel toewijzen om sessie-id [!DNL Marketo Measure] toe te wijzen aan Adobe-ECID en Munckin-id.

<table>
  <tbody>
    <tr>
      <th>Kolom</th>
      <th>Gegevenstype</th>
      <th>Beschrijving</th>
      <th>Voorbeeldgegevens</th>
    </tr>
    <tr>
       <td>ID</td>
      <td>varchar</td>
      <td>Een unieke id voor de toewijzingsrecord.</td>
      <td>
        <p>0d643578c0c74753eff91abe668ed328|2020-06-17 :19: 03:36|0002|0|56868</p>
      </td>
    </tr>
    <tr>
      <td>
        <p>COOKIE_ID</p>
      </td>
      <td>varchar</td>
      <td>De [!DNL Marketo Measure] opgenomen cookie-id.</td>
      <td>0d643578c0c74753eff91abe668ed328</td>
    </tr>
    <tr>
      <td>
        <p>VISITOR_ID</p>
      </td>
      <td>varchar</td>
      <td>De eerste cookie-id van de verwante bezoeker-id.</td>
      <td>v_0d643578c0c74753eff91abe668ed328</td>
    </tr>
    <tr>
      <td>
        <p>SESSION_ID</p>
      </td>
      <td>varchar</td>
      <td>De sessie-id van [!DNL Marketo Measure] .</td>
      <td>2018-08-06:01-35-24-1231230.9bc63c34482f</td>
    </tr>
    <tr>
      <td>
        <p>EVENT_DATE</p>
      </td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de toewijzing is vastgelegd.</td>
      <td>
        <p>2020-06-17 19 :03: 36.000</p>
      </td>
    </tr>
    <tr>
      <td>MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>
        <p>De datum waarop de record voor het laatst is gewijzigd.</p>
      </td>
      <td>
        <p>2020-06-17 19 :03: 36.000</p>
      </td>
    </tr>
    <tr>
      <td>CURRENT_PAGE</td>
      <td>varchar</td>
      <td>URL van de paginaweergave, zonder queryparameters.</td>
      <td>
        <p>https://learn.atest.com/simplify-retention-starter-kit.html</p>
      </td>
    </tr>
    <tr>
      <td>CURRENT_PAGE_RAW</td>
      <td>varchar</td>
      <td>URL van de paginaweergave, inclusief queryparameters.</td>
      <td>
        <p>https://learn.atest.com/simplify-retention-starter-kit.html?x=nGfrBF&amp;utm_medium=cpc&amp;utm_source=intensify</p>
      </td>
    </tr>
    <tr>
      <td>IP_ADDRESS</td>
      <td>varchar</td>
      <td>Het opgenomen IP-adres.</td>
      <td>
        <p>15.203.142.127</p>
      </td>
    </tr>
    <tr>
      <td>TYPE</td>
      <td>varchar</td>
      <td>Geeft het type gebeurtenis aan.</td>
      <td>
        <p>HostMapping</p>
      </td>
    </tr>
    <tr>
      <td>USER_AGENT_STRING</td>
      <td>varchar</td>
      <td>Apparaat en browser die zijn opgenomen ten tijde van de paginaweergave.</td>
      <td>
        <p>Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/79.0.3945.130 Safari/537.36</p>
      </td>
    </tr>
    <tr>
      <td>CLIENT_SEQUENCE</td>
      <td>varchar</td>
      <td>Hiermee geeft u de volgorde aan waarin de paginaweergave is opgetreden tijdens de sessie.</td>
      <td>2</td>
    </tr>
    <tr>
      <td>CLIENT_RANDOM</td>
      <td>varchar</td>
      <td>Wordt gebruikt voor interne controle en verwerking.</td>
      <td>566868</td>
    </tr>
    <tr>
      <td>IS_DUPLICATED</td>
      <td>boolean</td>
      <td>Hiermee wordt aangegeven of de record wordt beschouwd als een duplicaat.</td>
      <td>false</td>
    </tr>
    <tr>
      <td>IS_PROCESSED</td>
      <td>boolean</td>
      <td>Wordt gebruikt voor interne verwerking.</td>
      <td>true</td>
    </tr>
    <tr>
      <td>MAPPING_TYPE</td>
      <td>varchar</td>
      <td>Het type id dat wordt toegewezen aan de cookie-id [!DNL Marketo Measure] .</td>
      <td>Adobe_OrgId_Ecid</td>
    </tr>
    <tr>
      <td>MAPPING_ORD_ID</td>
      <td>varchar</td>
      <td>Adobe IMS-organisatie-id.</td>
      <td>8CC867C25245ADC30A490D4C</td>
    </tr>
    <tr>
      <td>MAPPING_COOKIE_ID</td>
      <td>varchar</td>
      <td>Adobe ECID voor de opgegeven organisatie-id.</td>
      <td>09860926390077352923264316157493772857</td>
    </tr>
    <tr>
      <td>_CREATED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemaakt in Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_MODIFIED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record voor het laatst in de Snowflake is gewijzigd.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
    <tr>
      <td>_DELETED_DATE</td>
      <td>timestamp_ntz</td>
      <td>De datum waarop de record is gemarkeerd als verwijderd in de Snowflake.</td>
      <td>2020-01-01 01 :01: 00.000</td>
    </tr>
  </tbody>
</table>

## Voorbeeldquery&#39;s {#sample-queries}

**hoeveel Aanraakpunten van de Koper (BT) waren er voor elk kanaal/subkanaal vorige maand?**

```
--Note: This query can quickly be modified to show Buyer Attribution Touchpoint (BAT) counts by switching the biz_touchpoints table to the biz_attribution_touchpoints table.
 
select trim(split(ch.name,'.')[0])  as channel
      ,trim(split(ch.name,'.')[1])  as subchannel
      ,count(bt.id)                 as buyer_touchpoint_count
  from biz_user_touchpoints     ut
       left outer join
       biz_touchpoints          bt
        on bt.user_touchpoint_id    = ut.id
       and bt._deleted_date         is null
       left outer join
       biz_channels             ch
        on ut.channel               = ch.id
       and ch._deleted_date         is null
 where ut._deleted_date is null
   and ut.touchpoint_date between add_months(date_trunc(month,current_date),-1) and last_day(dateadd(month,-1,current_date))
group by 1,2
```

**hoeveel Attributed Inkomsten voor elk kanaal in de afgelopen maand, voor het volledige model van de wegattributie werd gesloten?**

```
--Note: This query does not perform any currency conversion.  If your data contains multiple currencies, you will need to add in logic to perform the conversion to the desired currency using the biz_conversion_rates table.
 
select trim(split(ch.name,'.')[0])  as channel
      ,sum(opp.amount*(bat.full_path_percentage/100))   as attributed_revenue
  from biz_user_touchpoints         ut
       inner join
       biz_attribution_touchpoints  bat
        on bat.user_touchpoint_id   = ut.id
       and bat._deleted_date        is null
       inner join
       biz_opportunities            opp
        on bat.opportunity_id       = opp.id
       and opp._deleted_date        is null
       and opp.is_closed            = true
       and opp.is_won               = true
       and opp.close_date between add_months(date_trunc(month,current_date),-1) and last_day(dateadd(month,-1,current_date))
       left outer join
       biz_channels                 ch
        on ut.channel               = ch.id
       and ch._deleted_date         is null
 where ut._deleted_date is null
group by 1
```

**wat is de volledige reis voor één persoon?  (Alle aanraakpunten weergeven voor één e-mailadres.)**

```
select ut.touchpoint_date
      ,ut.marketing_touch_type
      ,listagg(distinct ifnull(sdl.stage_name,sdo.stage_name),',')           as touchpoint_position
  from biz_user_touchpoints         ut
       left outer join
       biz_touchpoints              bt
        on bt.user_touchpoint_id    = ut.id
       and bt._deleted_date         is null
       left outer join
       biz_attribution_touchpoints  bat
        on bat.user_touchpoint_id   = ut.id
       and bat._deleted_date        is null
       left outer join
       biz_lead_stage_transitions   lst
        on lst.touchpoint_id        = bt.id
       and lst._deleted_date        is null
       and lst.is_pending           = false
       and lst.is_non_transitional  = false
       left outer join
       biz_stage_definitions        sdl
        on lst.stage_id             = sdl.id
       and sdl._deleted_date        is null
       left outer join
       biz_opp_stage_transitions    ost
        on ost.touchpoint_id        = bat.id
       and ost._deleted_date        is null
       and ost.is_pending           = false
       and ost.is_non_transitional  = false
       left outer join
       biz_stage_definitions        sdo
        on ost.stage_id             = sdo.id
       and sdo._deleted_date        is null
 where ut._deleted_date     is null
   and ut.email             = [email address]
group by 1,2
order by 1
```

**toon alle Aanraakpunten van de Attributie van de Koper (BAT) en hun Toegewezen Ontvangsten voor één enkele kans.**

>[!NOTE]
>
>Deze vraag keert bestemmingsopbrengst voor het model van de W vorm terug. Wijzig het model door het veld bij te werken in de berekening van de toegerekende opbrengsten.

```
select bat.id
      ,bat.touchpoint_date
      ,bat.email
      ,opp.amount*(bat.w_shape_percentage/100)             as attributed_revenue
      ,listagg(osd.stage_name,', ')                        as touchpoint_position
  from biz_opportunities               opp
       inner join
       biz_attribution_touchpoints     bat
        on bat.opportunity_id      = opp.id
       and bat._deleted_date       is null
       left outer join
       biz_opp_stage_transitions       ost
        on ost.touchpoint_id       = bat.id
       and ost._deleted_date       is null
       and ost.is_pending          = false
       and ost.is_non_transitional = false
       left outer join
       biz_stage_definitions            osd
        on ost.stage_id             = osd.id
       and osd._deleted_date        is null
 where opp._deleted_date    is null
   and opp.id               = [opportunity id]
group by 1,2,3,4
order by touchpoint_date
```

[Terug naar boven](#data-warehouse-schema)
