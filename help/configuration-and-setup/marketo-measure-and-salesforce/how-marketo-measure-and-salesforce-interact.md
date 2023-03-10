---
unique-page-id: 18874672
description: Hoe [!DNL Marketo Measure] en [!DNL Salesforce] Interactie - Marketo Measure - Productdocumentatie
title: Hoe [!DNL Marketo Measure] en [!DNL Salesforce] Interactie
exl-id: c2f9d7ce-c5b8-4664-8f92-cb54255190cd
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '1677'
ht-degree: 0%

---

# Hoe [!DNL Marketo Measure] en [!DNL Salesforce] Interactie {#how-marketo-measure-and-salesforce-interact}

>[!NOTE]
>
>Mogelijk ziet u instructies die &quot;[!DNL Marketo Measure]&quot; in onze documentatie, maar zie nog &quot;Bizible&quot;in uw CRM. We werken eraan dat dit wordt bijgewerkt en de herbranding wordt binnenkort weerspiegeld in uw CRM.

Laten we eens kijken naar de relatie tussen [!DNL Marketo Measure] en Salesforce.

## Salesforce en [!DNL Marketo Measure] {#salesforce-and-marketo-measure}

Wanneer de [!DNL Marketo Measure] account is gemaakt en [!DNL Salesforce] is verbonden, [!DNL Marketo Measure] begint marketinggegevens naar de instantie CRM te duwen zolang de [!DNL Marketo Measure] het beheerde pakket is geïnstalleerd en het [!DNL Marketo Measure] De Salesforce-gebruiker heeft bewerkingsmachtigingen.

Als u de [!DNL Marketo Measure] Salesforce-pakket [!DNL Marketo Measure] geen gegevens naar uw Salesforce-instantie schrijven.

![](assets/1-3.png)

Standaard, [!DNL Marketo Measure] Hiermee exporteert u 200 records per API-credit telkens wanneer een taak gegevens naar uw CRM verzendt. Voor de meeste klanten biedt dit de optimale balans tussen API-credits die worden verbruikt door [!DNL Marketo Measure] en CPU-resourcevereisten voor de CRM. Voor klanten met complexe CRM-configuraties, zoals workflows en triggers, kan een kleinere batch-omvang echter nuttig zijn om de CRM-prestaties te verbeteren. Daartoe [!DNL Marketo Measure] staat klanten toe om de grootte van de de uitvoerpartij van CRM te vormen. Deze instelling is beschikbaar op het tabblad [!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL General] pagina in de [!DNL Marketo Measure] De webtoepassing en klanten kunnen kiezen uit batchgrootten 200 (standaard), 100, 50 of 25.

![](assets/how-bizible-and-salesforce-interact-2.png)

Houd er bij het wijzigen van deze instelling rekening mee dat kleinere batchformaten meer API-credits van uw CRM verbruiken. Het is raadzaam om de partijgrootte te verminderen slechts als u Cpu ondervindt onderbreking of hoge lading van cpu in uw CRM.

## Standaardobjecten Salesforce en Toegang {#salesforce-standard-objects-and-access}

Hierin worden de [!DNL Salesforce] Standaardobjecten die [!DNL Marketo Measure] heeft invloed op deze objecten en op de aangepaste velden die we aan deze objecten toevoegen wanneer de verbinding tot stand is gebracht en de [!DNL Marketo Measure] pakket is geïnstalleerd. Uit de doos, [!DNL Marketo Measure] zal niet in enige norm schrijven [!DNL Salesforce] Objectvelden.

**Lood**

<table> 
 <tbody> 
  <tr> 
   <th><p>Velden</p></th> 
   <th><p>Standaard/Aangepast</p></th> 
   <th><p>Lezen</p></th> 
   <th><p>Schrijven</p></th> 
  </tr> 
  <tr> 
   <td><p>Id</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>E-mail</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>Status</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>CreatedDate</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>LastModifiedDate</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>ConvertedDate</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>ConvertedContactId</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>ConvertedOpportunityId</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>IsConverted</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>IsDelted</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>Website</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>Bedrijf</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Account__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Ad_Campaign_Name_FT__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_ad_Campaign_Name_LC_c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Landing_Page_FT__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Landing_Page_LC__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Marketing_Channel_FT__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Marketing_Channel_LC__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Date_FT__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Touchpoint_Date_LC__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Source_FT__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Source_LC__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x </p></td> 
  </tr> 
 </tbody> 
</table>

**Contact**

<table> 
 <tbody> 
  <tr> 
   <th><p>Velden</p></th> 
   <th><p>Standaard/Aangepast</p></th> 
   <th><p>Lezen</p></th> 
   <th><p>Schrijven</p></th> 
  </tr> 
  <tr> 
   <td><p>Account</p></td> 
   <td><p>Standaard</p></td> 
   <td><span>x</span></td> 
   <td><br></td> 
  </tr> 
  <tr> 
   <td><p>Id</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>E-mail</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>Aanmaakdatum</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>IsDelted</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>LastModifiedDate</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Ad_Campaign_Name_FT__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_ad_Campaign_Name_LC_c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Landing_Page_FT__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Landing_Page_LC__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Marketing_Channel_FT__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Marketing_Channel_LC__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Date_FT__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Touchpoint_Date_LC__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Source_FT__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Source_LC__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x </p></td> 
  </tr> 
 </tbody> 
</table>

**Case**

<table> 
 <tbody> 
  <tr> 
   <th><p>Velden</p></th> 
   <th><p>Standaard/Aangepast</p></th> 
   <th><p>Lezen</p></th> 
   <th><p>Schrijven</p></th> 
  </tr> 
  <tr> 
   <td><p>Id</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>CreatedDate</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>LastModifiedDate</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>SuppliedEmail</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>IsDelted</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Ad_Campaign_Name_FT__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_ad_Campaign_Name_LC_c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Landing_Page_FT__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Landing_Page_LC__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Marketing_Channel_FT__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Marketing_Channel_LC__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Date_FT__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Touchpoint_Date_LC__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Source_FT__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Source_LC__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x </p></td> 
  </tr> 
 </tbody> 
</table>

**Account**

<table> 
 <tbody> 
  <tr> 
   <th><p>Velden</p></th> 
   <th><p>Standaard/Aangepast</p></th> 
   <th><p>Lezen</p></th> 
   <th><p>Schrijven</p></th> 
  </tr> 
  <tr> 
   <td><p>Id</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>Website</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>LastModifiedDate</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>IsDelted</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Engagement_Score__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x </p></td> 
  </tr> 
 </tbody> 
</table>

**Opportunity**

<table> 
 <tbody> 
  <tr> 
   <th><p>Velden</p></th> 
   <th><p>Standaard/Aangepast</p></th> 
   <th><p>Lezen</p></th> 
   <th><p>Schrijven</p></th> 
  </tr> 
  <tr> 
   <td><p>Account</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td><br></td> 
  </tr> 
  <tr> 
   <td><p>Id</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>CreatedDate</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>LastModifiedDate</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>IsWon</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>IsClosed</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>IsDelted</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>CloseDate</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>StageName</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>Hoeveelheid</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Bizible_Opportunity_Amount__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x </p></td> 
  </tr> 
 </tbody> 
</table>

**Campagne**

<table> 
 <colgroup> 
  <col> 
  <col> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th><p>Velden</p></th> 
   <th><p>Standaard/Aangepast</p></th> 
   <th><p>Lezen</p></th> 
   <th><p>Schrijven</p></th> 
  </tr> 
  <tr> 
   <td><p>Id</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>E-mail</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>Status</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>CreatedDate</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>LastModifiedDate</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>ConvertedDate</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>ConvertedContactId</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>ConvertedOpportunityId</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>IsConverted</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>IsDelted</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>Website</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>Bedrijf</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>Type</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td><br></td> 
  </tr> 
 </tbody> 
</table>

**Campagnelid**

<table> 
 <tbody> 
  <tr> 
   <th><p>Velden</p></th> 
   <th><p>Standaard/Aangepast</p></th> 
   <th><p>Lezen</p></th> 
   <th><p>Schrijven</p></th> 
  </tr> 
  <tr> 
   <td><p>Id</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>CreatedDate</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>LastModifiedDate</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>IsDelted</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>FirstRespondedDate</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>HasResponded</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>ContactId</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>LeadId</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>IsConverted</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>CampagneId</p></td> 
   <td><p>Standaard</p></td> 
   <td><p>x</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Bizible_Touchpoint_Date_c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Touchpoint_Status_Date__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Status_Contact__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Touchpoint_Status_Leade_c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Status_Opportunity__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x </p></td> 
  </tr> 
 </tbody> 
</table>

## [!DNL Marketo Measure] Aangepaste objecten in [!DNL Salesforce] {#marketo-measure-custom-objects-in-salesforce}

Naast het maken van aangepaste velden op de standaardobjecten van SFDC, wordt [!DNL Marketo Measure] -pakket is geïnstalleerd, worden er een aantal aangepaste objecten gemaakt. Hieronder ziet u een lijst met deze aangepaste objecten en een tabel die de velden aangeeft die [!DNL Marketo Measure] zal schrijven naar.

**Aanraakpunt koper**

Het aanraakpunt voor kopers is een [!DNL Marketo Measure] Aangepast object om de marketinginteracties voor contactpersonen, leads en gevallen in te kapselen.

<table> 
 <tbody> 
  <tr> 
   <th><p>Velden</p></th> 
   <th><p>Standaard/Aangepast</p></th> 
   <th><p>Lezen</p></th> 
   <th><p>Schrijven</p></th> 
  </tr> 
  <tr> 
   <td><p>bizible2__Bizible_Person__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_SF_Campaign_c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__UniqueId__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Marketing_Channel__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Marketing_Channel_Path__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Touchpoint_Type__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__ad_id__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Ad_Content__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_ad_Group_id__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Ad_Group_Name__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_ad_Campaign_id_c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_ad_Campaign_Name__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Placement_id__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Placement_Name__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Site_Id__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Site_Name__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Form_URL_c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Form_URL_Raw__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Platform__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Browser__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Geo_City__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Geo_Country__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Geo_Region__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_trefwoord_id__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Keyword_MatchType__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Position__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Keyword_Text__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Landing_Page__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Landing_Page_Raw__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Medium__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Referrer_Page__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Referrer_Page_Raw__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_search_Phrase_c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Touchpoint_Date__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Source__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Segment__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Count_First_Touch__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_count_Lead_Creation_Touch_c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Count_U_Shaped__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Ad_Destination_URL__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Case__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Contact__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
 </tbody> 
</table>

**[!DNL Marketo Measure]Persoon**

De [!DNL Marketo Measure] Persoon is een [!DNL Marketo Measure] Aangepast object dat betrekking heeft op zowel de objecten Lead, Contact en Case.

<table> 
 <tbody> 
  <tr> 
   <th><p>Velden</p></th> 
   <th><p>Standaard/Aangepast</p></th> 
   <th><p>Lezen</p></th> 
   <th><p>Schrijven</p></th> 
  </tr> 
  <tr> 
   <td><p>bizible2__UniqueId__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Lead__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Case__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Contact__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x </p></td> 
  </tr> 
 </tbody> 
</table>

## Aanraakpunt koperkenmerk {#buyer-attribution-touchpoint}

Het aanraakpunt voor koperkenmerken is een [!DNL Marketo Measure] Aangepast object om de invloed van marketing op kansen in te kapselen.

**Aanraakpunt koperkenmerk**

<table> 
 <tbody> 
  <tr> 
   <th><p>Velden</p></th> 
   <th><p>Standaard/Aangepast</p></th> 
   <th><p>Lezen</p></th> 
   <th><p>Schrijven</p></th> 
  </tr> 
  <tr> 
   <td><p>bizible2__Account__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_SF_Campaign_c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Contact__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Opportunity__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__UniqueId__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Marketing_Channel__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Marketing_Channel_Path__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Touchpoint_Type__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__ad_id__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Ad_Content__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_ad_Group_id__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Ad_Group_Name__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_ad_Campaign_id_c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_ad_Campaign_Name__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Placement_id__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Placement_Name__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Site_Id__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Site_Name__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Form_URL_c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Form_URL_Raw__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Platform__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Browser__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Geo_City__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Geo_Country__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Geo_Region__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_trefwoord_id__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Keyword_MatchType__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Position__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Keyword_Text__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Landing_Page__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Landing_Page_Raw__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Medium__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Referrer_Page__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Referrer_Page_Raw__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_search_Phrase_c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Touchpoint_Date__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Touchpoint_Source__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Segment__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Attribution_First_Touch__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Attribution_Lead_Conversion_Touch__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Attribution_U_Shaped__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Attribution_W_Shaped__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Attribution_Custom_Model__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Attribution_Custom_Model_2_c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Count_First_Touch__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_count_Lead_Creation_Touch_c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Count_U_Shaped__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Count_W_Shaped__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Count_Custom_Model__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Count_Custom_Model_2_c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Ad_Destination_URL__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Revenue_First_Touch__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Revenue_Lead_Creation_Touch_c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2__Revenue_U_Shaped__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Revenue_W_Shaped__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Revenue_Custom_Model__c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
  <tr> 
   <td><p>bizible2_Revenue_Custom_Model_2_c</p></td> 
   <td><p>Aangepast</p></td> 
   <td><p>x</p></td> 
   <td><p>x</p></td> 
  </tr> 
 </tbody> 
</table>
