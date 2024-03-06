---
unique-page-id: 18874672
description: Hoe [!DNL Marketo Measure] en [!DNL Salesforce] Interactie - Marketo Measure - Productdocumentatie
title: Hoe [!DNL Marketo Measure] en [!DNL Salesforce] Interactie
exl-id: c2f9d7ce-c5b8-4664-8f92-cb54255190cd
feature: Salesforce
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '1264'
ht-degree: 0%

---

# Hoe [!DNL Marketo Measure] en [!DNL Salesforce] Interactie {#how-marketo-measure-and-salesforce-interact}

>[!NOTE]
>
>Mogelijk ziet u instructies die &quot;[!DNL Marketo Measure]&quot; in de documentatie, maar zie nog steeds &quot;Bizible&quot; in uw CRM. We werken eraan dat dit wordt bijgewerkt en de herbranding wordt binnenkort weerspiegeld in uw CRM.

Laten we eens kijken naar de relatie tussen [!DNL Marketo Measure] en Salesforce.

## Salesforce en [!DNL Marketo Measure] {#salesforce-and-marketo-measure}

Wanneer de [!DNL Marketo Measure] account is gemaakt en [!DNL Salesforce] is verbonden, [!DNL Marketo Measure] begint marketinggegevens naar de instantie CRM te duwen zolang de [!DNL Marketo Measure] het beheerde pakket is geïnstalleerd en [!DNL Marketo Measure] De Salesforce-gebruiker heeft bewerkingsmachtigingen.

Als u de [!DNL Marketo Measure] Salesforce-pakket [!DNL Marketo Measure] geen gegevens naar uw Salesforce-instantie schrijven.

![](assets/1-3.png)

Standaard, [!DNL Marketo Measure] Hiermee exporteert u 200 records per API-credit telkens wanneer een taak gegevens naar uw CRM verzendt. Voor de meeste klanten biedt dit de optimale balans tussen API-credits die worden verbruikt door [!DNL Marketo Measure] en CPU-resourcevereisten voor de CRM. Voor klanten met complexe CRM-configuraties, zoals workflows en triggers, kan een kleinere batch-omvang echter nuttig zijn om de CRM-prestaties te verbeteren. Daartoe: [!DNL Marketo Measure] staat klanten toe om de grootte van de de uitvoerpartij van CRM te vormen. Deze instelling is beschikbaar op het tabblad [!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL General] pagina in de [!DNL Marketo Measure] De webtoepassing en klanten kunnen kiezen uit batchgrootten 200 (standaard), 100, 50 of 25.

![](assets/how-bizible-and-salesforce-interact-2.png)

Houd er bij het wijzigen van deze instelling rekening mee dat kleinere batchformaten meer API-credits van uw CRM verbruiken. Het is raadzaam de batch alleen te verkleinen als u een CPU-time-out of een hoge CPU-belasting hebt in uw CRM.

## Standaardobjecten Salesforce en Toegang {#salesforce-standard-objects-and-access}

Hierin worden de [!DNL Salesforce] Standaardobjecten die [!DNL Marketo Measure] en de aangepaste velden die we aan deze objecten toevoegen wanneer de verbinding tot stand is gebracht en de [!DNL Marketo Measure] pakket is geïnstalleerd. Uit de doos, [!DNL Marketo Measure] zal niet in enige norm schrijven [!DNL Salesforce] Objectvelden.

**Lood**

<table> 
 <tbody> 
  <tr> 
   <th>Velden</th> 
   <th>Standaard/Aangepast</th> 
   <th>Lezen</th> 
   <th>Schrijven</th> 
  </tr> 
  <tr> 
   <td>Id</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>E-mail</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Status</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CreatedDate</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>LastModifiedDate</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ConvertedDate</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ConvertedContactId</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ConvertedOpportunityId</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsConverted</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDelted</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Website</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Bedrijf</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>bizible2__Account__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Ad_Campaign_Name_FT__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_ad_Campaign_Name_LC_c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Landing_Page_FT__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Landing_Page_LC__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Marketing_Channel_FT__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Marketing_Channel_LC__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Date_FT__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Touchpoint_Date_LC__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Source_FT__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Source_LC__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x </td> 
  </tr> 
 </tbody> 
</table>

**Contact**

<table> 
 <tbody> 
  <tr> 
   <th>Velden</th> 
   <th>Standaard/Aangepast</th> 
   <th>Lezen</th> 
   <th>Schrijven</th> 
  </tr> 
  <tr> 
   <td>Account</td> 
   <td>Standaard</td> 
   <td><span>x</span></td> 
   <td><br></td> 
  </tr> 
  <tr> 
   <td>Id</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>E-mail</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Aanmaakdatum</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDelted</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>LastModifiedDate</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>bizible2_Ad_Campaign_Name_FT__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_ad_Campaign_Name_LC_c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Landing_Page_FT__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Landing_Page_LC__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Marketing_Channel_FT__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Marketing_Channel_LC__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Date_FT__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Touchpoint_Date_LC__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Source_FT__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Source_LC__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x </td> 
  </tr> 
 </tbody> 
</table>

**Kwestie**

<table> 
 <tbody> 
  <tr> 
   <th>Velden</th> 
   <th>Standaard/Aangepast</th> 
   <th>Lezen</th> 
   <th>Schrijven</th> 
  </tr> 
  <tr> 
   <td>Id</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CreatedDate</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>LastModifiedDate</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>SuppliedEmail</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDelted</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>bizible2_Ad_Campaign_Name_FT__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_ad_Campaign_Name_LC_c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Landing_Page_FT__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Landing_Page_LC__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Marketing_Channel_FT__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Marketing_Channel_LC__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Date_FT__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Touchpoint_Date_LC__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Source_FT__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Source_LC__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x </td> 
  </tr> 
 </tbody> 
</table>

**Account**

<table> 
 <tbody> 
  <tr> 
   <th>Velden</th> 
   <th>Standaard/Aangepast</th> 
   <th>Lezen</th> 
   <th>Schrijven</th> 
  </tr> 
  <tr> 
   <td>Id</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Website</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>LastModifiedDate</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDelted</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>bizible2_Engagement_Score__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x </td> 
  </tr> 
 </tbody> 
</table>

**Opportunity**

<table> 
 <tbody> 
  <tr> 
   <th>Velden</th> 
   <th>Standaard/Aangepast</th> 
   <th>Lezen</th> 
   <th>Schrijven</th> 
  </tr> 
  <tr> 
   <td>Naam</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td><br></td> 
  </tr>
  <tr> 
   <td>Account</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td><br></td> 
  </tr>
  <tr> 
   <td>Id</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CreatedDate</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>LastModifiedDate</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsWon</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsClosed</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDelted</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CloseDate</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>StageName</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Hoeveelheid</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>bizible2_Bizible_Opportunity_Amount__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x </td> 
  </tr> 
 </tbody> 
</table>

**Functie contactpersoon opportunity**

<table> 
 <tbody> 
  <tr> 
   <th>Velden</th> 
   <th>Standaard/Aangepast</th> 
   <th>Lezen</th> 
   <th>Schrijven</th> 
  </tr> 
  <tr> 
   <td>Id</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CreatedDate</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDelted</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr>
  <tr> 
   <td>LastModifiedDate</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>OpportunityId</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ContactId</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr>

<tr> 
   <td>IsPrimary</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Functie</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
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
   <th>Velden</th> 
   <th>Standaard/Aangepast</th> 
   <th>Lezen</th> 
   <th>Schrijven</th> 
  </tr> 
  <tr> 
   <td>Id</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>E-mail</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Status</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CreatedDate</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>LastModifiedDate</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ConvertedDate</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ConvertedContactId</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ConvertedOpportunityId</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsConverted</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDelted</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Website</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Bedrijf</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Type</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td><br></td> 
  </tr> 
 </tbody> 
</table>

**Campagnelid**

<table> 
 <tbody> 
  <tr> 
   <th>Velden</th> 
   <th>Standaard/Aangepast</th> 
   <th>Lezen</th> 
   <th>Schrijven</th> 
  </tr> 
  <tr> 
   <td>Id</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CreatedDate</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>LastModifiedDate</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDelted</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>FirstRespondedDate</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>HasResponded</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ContactId</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>LeadId</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsConverted</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CampagneId</td> 
   <td>Standaard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>bizible2_Bizible_Touchpoint_Date_c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Touchpoint_Status_Date__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Status_Contact__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Touchpoint_Status_Leade_c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Status_Opportunity__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Om ervoor te zorgen dat Marketo Measure verwijderingsgebeurtenissen vastlegt binnen uw Salesforce-account, zijn reproduceerbare machtigingen voor de onderstaande objecten vereist. Repliceerbare machtigingen worden standaard geleverd met de volgende objecten:
>
>* Account
>* Campagne
>* Campagnelid
>* Contact
>* Gebeurtenis
>* Lood
>* Opportunity
>* Taak


## [!DNL Marketo Measure] Aangepaste objecten in [!DNL Salesforce] {#marketo-measure-custom-objects-in-salesforce}

Naast het maken van aangepaste velden op de standaardobjecten van SFDC [!DNL Marketo Measure] -pakket is geïnstalleerd, worden er een aantal aangepaste objecten gemaakt. Hieronder ziet u een lijst met deze aangepaste objecten en een tabel die de velden aangeeft die [!DNL Marketo Measure] zal schrijven naar.

**Aanraakpunt koper**

Het aanraakpunt voor kopers is een [!DNL Marketo Measure] Aangepast object om de marketinginteracties voor contactpersonen, leads en gevallen in te kapselen.

<table> 
 <tbody> 
  <tr> 
   <th>Velden</th> 
   <th>Standaard/Aangepast</th> 
   <th>Lezen</th> 
   <th>Schrijven</th> 
  </tr> 
  <tr> 
   <td>bizible2__Bizible_Person__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_SF_Campaign_c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__UniqueId__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Marketing_Channel__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Marketing_Channel_Path__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Touchpoint_Type__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__ad_id__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Ad_Content__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_ad_Group_id__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Ad_Group_Name__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_ad_Campaign_id_c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_ad_Campaign_Name__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Placement_id__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Placement_Name__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Site_Id__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Site_Name__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Form_URL_c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Form_URL_Raw__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Platform__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Browser__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Geo_City__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Geo_Country__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Geo_Region__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_trefwoord_id__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Keyword_MatchType__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Position__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Keyword_Text__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Landing_Page__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Landing_Page_Raw__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Medium__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Referrer_Page__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Referrer_Page_Raw__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_search_Phrase_c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Touchpoint_Date__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Source__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Segment__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Count_First_Touch__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_count_Lead_Creation_Touch_c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Count_U_Shaped__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Destination_URL__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Case__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Contact__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
 </tbody> 
</table>

**[!DNL Marketo Measure]Persoon**

De [!DNL Marketo Measure] Persoon is een [!DNL Marketo Measure] Aangepast object dat betrekking heeft op zowel de objecten Lead, Contact en Case.

<table> 
 <tbody> 
  <tr> 
   <th>Velden</th> 
   <th>Standaard/Aangepast</th> 
   <th>Lezen</th> 
   <th>Schrijven</th> 
  </tr> 
  <tr> 
   <td>bizible2__UniqueId__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Lead__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Case__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Contact__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x </td> 
  </tr> 
 </tbody> 
</table>

## Aanraakpunt koperkenmerk {#buyer-attribution-touchpoint}

Het aanraakpunt voor koperkenmerken is een [!DNL Marketo Measure] Aangepast object om de invloed van marketing op kansen in te kapselen.

**Aanraakpunt koperkenmerk**

<table> 
 <tbody> 
  <tr> 
   <th>Velden</th> 
   <th>Standaard/Aangepast</th> 
   <th>Lezen</th> 
   <th>Schrijven</th> 
  </tr> 
  <tr> 
   <td>bizible2__Account__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_SF_Campaign_c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Contact__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Opportunity__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__UniqueId__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Marketing_Channel__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Marketing_Channel_Path__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Touchpoint_Type__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__ad_id__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Ad_Content__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_ad_Group_id__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Ad_Group_Name__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_ad_Campaign_id_c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_ad_Campaign_Name__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Placement_id__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Placement_Name__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Site_Id__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Site_Name__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Form_URL_c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Form_URL_Raw__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Platform__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Browser__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Geo_City__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Geo_Country__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Geo_Region__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_trefwoord_id__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Keyword_MatchType__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Position__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Keyword_Text__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Landing_Page__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Landing_Page_Raw__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Medium__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Referrer_Page__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Referrer_Page_Raw__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_search_Phrase_c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Touchpoint_Date__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Touchpoint_Source__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Segment__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Attribution_First_Touch__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Attribution_Lead_Conversion_Touch__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Attribution_U_Shaped__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Attribution_W_Shaped__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Attribution_Custom_Model__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Attribution_Custom_Model_2_c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Count_First_Touch__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_count_Lead_Creation_Touch_c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Count_U_Shaped__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Count_W_Shaped__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Count_Custom_Model__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Count_Custom_Model_2_c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Ad_Destination_URL__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Revenue_First_Touch__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Revenue_Lead_Creation_Touch_c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2__Revenue_U_Shaped__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Revenue_W_Shaped__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Revenue_Custom_Model__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
  <tr> 
   <td>bizible2_Revenue_Custom_Model_2_c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
 </tbody> 
</table>
