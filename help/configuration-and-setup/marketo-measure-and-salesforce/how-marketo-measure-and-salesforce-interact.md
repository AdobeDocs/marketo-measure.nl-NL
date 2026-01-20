---
unique-page-id: 18874672
description: Hoe  [!DNL Marketo Measure]  en  [!DNL Salesforce]  in wisselwerking staan - Marketo Measure - de Documentatie van het Product
title: Hoe  [!DNL Marketo Measure]  en  [!DNL Salesforce]  interactie hebben
exl-id: c2f9d7ce-c5b8-4664-8f92-cb54255190cd
feature: Salesforce
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '1287'
ht-degree: 6%

---

# Hoe [!DNL Marketo Measure] en [!DNL Salesforce] werken {#how-marketo-measure-and-salesforce-interact}

>[!NOTE]
>
>U kunt instructies zien die &quot;[!DNL Marketo Measure]&quot;in de documentatie specificeren, maar nog zie &quot;Bizible&quot;in uw CRM. We werken eraan dat dit wordt bijgewerkt en de herbranding wordt binnenkort weerspiegeld in uw CRM.

Laten we eens kijken naar de relatie tussen [!DNL Marketo Measure] en Salesforce.

## Salesforce en [!DNL Marketo Measure]  {#salesforce-and-marketo-measure}

Nadat de [!DNL Marketo Measure] -account is gemaakt en [!DNL Salesforce] is verbonden, worden marketinggegevens door [!DNL Marketo Measure] naar de CRM-instantie verplaatst zolang het [!DNL Marketo Measure] beheerde pakket is geïnstalleerd en de [!DNL Marketo Measure] Salesforce-gebruiker over bewerkingsmachtigingen beschikt.

Als u het [!DNL Marketo Measure] Salesforce-pakket niet hebt geïnstalleerd, schrijft [!DNL Marketo Measure] geen gegevens naar uw Salesforce-instantie.

![](assets/1-3.png)

Standaard exporteert [!DNL Marketo Measure] 200 records per API-credit telkens wanneer een taak gegevens naar uw CRM verzendt. Voor de meeste klanten biedt dit de optimale balans tussen API-credits die door [!DNL Marketo Measure] worden verbruikt en CPU-bronvereisten voor de CRM. Voor klanten met complexe CRM-configuraties, zoals workflows en triggers, kan een kleinere batch-omvang echter nuttig zijn om de CRM-prestaties te verbeteren. Met het oog hierop kunnen klanten in [!DNL Marketo Measure] de grootte van de CRM-exportbatch configureren. Deze instelling is beschikbaar op de pagina [!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL General] in de [!DNL Marketo Measure] -webtoepassing. Klanten kunnen kiezen uit batchgrootten 200 (standaard), 100, 50 of 25.

![](assets/how-bizible-and-salesforce-interact-2.png)

Houd er bij het wijzigen van deze instelling rekening mee dat kleinere batchformaten meer API-credits van uw CRM verbruiken. Het wordt aangeraden de batch alleen te verkleinen als u een CPU-time-out of een hoge CPU-belasting in uw CRM-systeem hebt.

## Salesforce Connected-gebruikersmachtigingen {#salesforce-connected-user-permissions}

**de Toestemming van de Beheerder van Marketo Measure voor Specifieke Gebruiker** wordt geplaatst: Staat SFDC admin toe om verrichtingen CRUD op de voorwerpen van Marketo Measure uit te voeren die.

**Mening en geeft Omgezette Reeks van de Toestemming van Leads** uit: Dit staat Marketo Measure toe om lood te versieren nadat zij in contacten zijn omgezet.

**Checkbox van de Gebruiker van de Marketing van Salesforce**: Staat gebruikers toe om campagnes tot stand te brengen en de Tovenaars van de Invoer van de Campagne te gebruiken.

* Wij vereisen extra toestemmingen voor Campagne &quot;creeer&quot;en &quot;Update&quot;in uw CRMs.

* Wanneer een aanraakpunt wordt gemaakt op basis van een webactiviteit, moeten we het koppelen aan een campagne. Omdat webactiviteiten geen overeenkomstige CRM-campagnes hebben, moeten we er een maken om deze koppeling tot stand te brengen. Dit geldt zowel voor aanraakpunten met kansen als voor aanraakpunten. U hebt een updatetoestemming nodig omdat de aanroep die we gebruiken &#39;upsert&#39; is. Als de record bestaat, wordt deze bijgewerkt; anders maken we deze. Dit geldt alleen voor campagnes die we maken.

**StandaardGebruiker van Marketo Measure**: Biedt een gebruiker de capaciteit om verslagen van de voorwerpen van Marketo Measure te lezen.

## Salesforce Standard-objecten en -toegang {#salesforce-standard-objects-and-access}

Hier worden de [!DNL Salesforce] standaardobjecten weergegeven waarmee [!DNL Marketo Measure] werkt en de aangepaste velden die we aan deze objecten toevoegen nadat de verbinding tot stand is gebracht en het [!DNL Marketo Measure] -pakket is geïnstalleerd. Uit het vak schrijft [!DNL Marketo Measure] NIET naar standaardobjectvelden van [!DNL Salesforce] .

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
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>E-mail</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Status</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CreatedDate</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>LastModifiedDate</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ConvertedDate</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ConvertedContactId</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ConvertedOpportunityId</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsConverted</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDelted</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Website</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Bedrijf</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>bizible2__Account__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
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
   <td>Standard</td> 
   <td><span>x</span></td> 
   <td><br></td> 
  </tr> 
  <tr> 
   <td>Id</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>E-mail</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Aanmaakdatum</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDelted</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>LastModifiedDate</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr>
 </tbody> 
</table>

**Rekening**

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
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Website</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>LastModifiedDate</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDelted</td> 
   <td>Standard</td> 
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

**Kans**

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
   <td>Standard</td> 
   <td>x</td> 
   <td><br></td> 
  </tr>
  <tr> 
   <td>Account</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td><br></td> 
  </tr>
  <tr> 
   <td>Id</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CreatedDate</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>LastModifiedDate</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsWon</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsClosed</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDelted</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CloseDate</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>StageName</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Hoeveelheid</td> 
   <td>Standard</td> 
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

**de Rol van het Contact van 0&rbrace; Opportunity**

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
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CreatedDate</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDelted</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr>
  <tr> 
   <td>LastModifiedDate</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>OpportunityId</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ContactId</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr>

<tr> 
   <td>IsPrimary</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Functie</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

**Campaign**

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
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>E-mail</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Status</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CreatedDate</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>LastModifiedDate</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDelted</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Website</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Bedrijf</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Type</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr>
  <tr> 
   <td>StartDate</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr>
  <tr> 
   <td>EndDate</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr>
  <tr> 
   <td>Naam</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td>x</td> 
  </tr>
  <tr> 
   <td>bizible2__UniqueId__c</td> 
   <td>Aangepast</td> 
   <td>x</td> 
   <td>x</td> 
  </tr> 
 </tbody> 
</table>

**Lid van de Campagne**

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
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CreatedDate</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>LastModifiedDate</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsDelted</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>FirstRespondedDate</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>HasResponded</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>ContactId</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>LeadId</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>IsConverted</td> 
   <td>Standard</td> 
   <td>x</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>CampagneId</td> 
   <td>Standard</td> 
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
>Om ervoor te zorgen dat Marketo Measure verwijderingsgebeurtenissen vastlegt in uw Salesforce-account, zijn repliceerbare machtigingen voor de onderstaande objecten vereist. Repliceerbare machtigingen worden standaard geleverd met de volgende objecten:
>
>* Account
>* Campaign
>* Campagnelid
>* Contact
>* Gebeurtenis
>* Lood
>* Kans
>* Taak


## [!DNL Marketo Measure] Aangepaste objecten in [!DNL Salesforce]  {#marketo-measure-custom-objects-in-salesforce}

Naast het maken van aangepaste velden op standaardobjecten van SFDC, maakt het pakket een aantal aangepaste objecten nadat het [!DNL Marketo Measure] -pakket is geïnstalleerd. Hieronder ziet u een lijst met deze aangepaste objecten, samen met een tabel die de velden aangeeft waarnaar [!DNL Marketo Measure] gaat schrijven.

**Buyer Touchpoint**

De Buyer Touchpoint is een [!DNL Marketo Measure] aangepast object waarmee de marketinginteracties voor Contactpersonen, Leads en Kwesties worden ingekapseld.

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

De persoon van [!DNL Marketo Measure] is een [!DNL Marketo Measure] aangepast object dat betrekking heeft op zowel de objecten voor lead, contact en case.

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

## Buyer Attribution Touchpoint {#buyer-attribution-touchpoint}

De Buyer Attribution Touchpoint is een [!DNL Marketo Measure] aangepast object waarmee de invloed van marketing op Opportunity wordt ingekapseld.

**Buyer Attribution Touchpoint**

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

>[!MORELIKETHIS]
>
>[&#x200B; Overzicht van de Toestemmingen van de Integratie &#x200B;](/help/api-connections/utilizing-marketo-measures-api-connections/integration-permissions-overview.md){target="_blank"}
