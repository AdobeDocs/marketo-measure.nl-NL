---
description: "[!DNL Marketo Measure] Integratie met Adobe Analytics - [!DNL Marketo Measure] - Productdocumentatie"
title: "[!DNL Marketo Measure] Integratie met [!DNL Adobe Analytics]"
exl-id: 3a125a15-eb74-454a-afb3-75746a1dfac6
source-git-commit: 51397a02872035fef41d308c1f855bcaecc29c4e
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 0%

---

# [!DNL Marketo Measure] Integratie met Adobe Analytics {#marketo-measure-integrations-with-adobe-analytics}

De integratie van B2B-klantkenmerken maakt wederzijdse gebruikers van [!DNL Marketo Measure] en Adobe Analytics om hun [!DNL Adobe Analytics] gebruikersprofielen met waardevolle metagegevens die zijn afgeleid van de [!DNL Marketo Measure] attributie-engine en via zijn synchronisatiemogelijkheid met CRM&#39;s ([!DNL Microsoft Dynamics] en [!DNL Salesforce]). Het is gratis beschikbaar voor alle klanten die [!DNL Adobe Analytics] en [!DNL Marketo Measure].

>[!PREREQUISITES]
>
>U moet actieve abonnementen op beide hebben [!DNL Marketo Measure] en [!DNL Adobe Analytics].

## De integratie configureren {#configuring-the-integration}

1. Begin door een nieuwe Bron van de Attributen van de Klant in uw console van Experience Cloud te creëren. Gedetailleerde instructies [hier te vinden](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-crs-usecase.html).

   Neem nota van de volgende informatie, aangezien u het voor enkele recentere stappen in het proces zult nodig hebben:

   * De alias-id. Dit kan elke gewenste waarde zijn. We raden &#39;marketeasure_id&#39; aan

   * De hostnaam en referenties van de FTP-server (gebruikersnaam en wachtwoord)

1. Zodra de Klant Gegevensbron van Attributen wordt gecreeerd, ga het configuratieproces door aan **[!UICONTROL Integrations]** > **[!UICONTROL Connections]** in het [!DNL Marketo Measure] beheermenu.

1. Klik op de knop **[!UICONTROL Set Up New Customer Attributes Connection]** en volg de instructies om de integratie van de Attributen van de Klant te vormen. De interface vraagt u naar de Alias ID- en FTP-verbindingsgegevens die u hebt verkregen bij het maken van de bron met klantkenmerken in uw Core Services Console en selecteert de set accountkenmerken die u wilt synchroniseren met uw [!DNL Adobe Analytics] account.

   U moet ook uw Adobe IMS-organisatie-id invoeren. Deze id wordt weergegeven in de rechterbenedenhoek van uw Adobe Experience Cloud-Admin Console. Neem contact op met het Adobe-accountteam (uw accountmanager) voor meer hulp bij het zoeken naar deze id.

1. Nadat u de verbinding in uw [!DNL Marketo Measure] -account, moet u teruggaan naar uw Experience Cloud-console om [valideer het schema](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/validate-schema.html). U hoeft zich geen zorgen te maken over het uploaden van FTP-bestanden, [!DNL Marketo Measure] heeft dat onderdeel voor u geautomatiseerd. Alles wat u hoeft te doen, gaat u naar het schema &quot;Weergave/Bewerken&quot; voor de kenmerkbron van de klant die u in Stap 1 hebt gemaakt en vertelt u Adobe wat de gegevenstypen zijn voor elk van de kenmerken die [!DNL Marketo Measure] heeft namens u geüpload. U kunt desgewenst ook nieuwe weergavefuncties voor de geüploade kenmerken maken.

   Als u ervoor hebt gekozen om kenmerken van uw CRM-accountobject te synchroniseren, wordt u ten zeerste aangeraden nieuwe weergavenamen voor deze kenmerken te kiezen, zoals [!DNL Marketo Measure] vult alleen de namen op API-niveau voor deze kenmerken in, die doorgaans niet rapportvriendelijk zijn.

1. De laatste stap moet de Abonnementen van Attributen voor de toepassingen vormen van Experience Cloud die u de attributen binnen wilt gebruiken.  U kunt Abonnementen configureren voor [!DNL Adobe Analytics] of [!DNL Adobe Target].  Meer informatie over hoe u dat kunt doen [hier te vinden](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/subscription.html).

## Kenmerkbeschrijvingen {#attribute-descriptions}

Wanneer u een nieuwe Verbinding van Attributen van de Klant B2B creeert, [!DNL Marketo Measure] automatisch een standaardset B2B-klantkenmerken voor u maken. Deze kenmerken worden in de onderstaande tabel beschreven.

Naast de kenmerken die hieronder worden vermeld, kunt u ook alle kenmerken uploaden die aan het accountobject in uw CRM zijn gekoppeld. Als er meer dan één account is gekoppeld aan de opgegeven gebruiker, [!DNL Marketo Measure] Hiermee worden alle overeenkomende accountkenmerkwaarden ingevuld in een lijst met door puntkomma&#39;s gescheiden waarden.

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td><b>Kenmerknaam</b></td> 
   <td><b>Beschrijving</b></td>
  </tr> 
  <tr> 
   <td>Account.Name</td> 
   <td>De accountnamen die aan de opgegeven webbezoeker zijn gekoppeld. Als er meer dan één account is gekoppeld aan de opgegeven gebruiker, [!DNL Marketo Measure] Hiermee worden alle overeenkomende accountnamen ingevuld in een lijst met door puntkomma's gescheiden accounts.<br/>
   <strong>Opmerking:</strong> account.name is de naam op Salesforce-API-niveau voor het naamkenmerk op het accountobject. U kunt een betere vertoningsnaam (b.v., "Bedrijf") voor dit attribuut tijdens de stap van de Bevestiging van het Schema van de integratieconfiguratie (stap 4) kiezen.</td>
  </tr>
  <tr> 
   <td>Toegewezen inkomsten - ‹MODEL›</td> 
   <td>De opbrengsten die aan deze klant worden toegerekend uit hoofde van zijn associatie met closed-won-mogelijkheden in uw CRM, zoals berekend door de [!DNL Marketo Measure] attributie-engine.<br/>
   Er zal één van deze attributen voor elk attribuutmodel zijn dat uw [!DNL Marketo Measure] abonnementen zijn toegestaan (bijv. "Attributed Revenue - Full Path").</td>
  </tr>
  <tr> 
   <td>Deepest Funnel Stage</td> 
   <td>De diepste trechterfase van elke open kans die aan de gegeven gebruiker wordt geassocieerd.</td>
  </tr>
  <tr> 
   <td>Open kansen</td> 
   <td>Een door puntkomma's gescheiden lijst met de opportuniteid's waaraan de gebruiker is gekoppeld volgens uw CRM-gegevens.</td>
  </tr> 
 </tbody> 
</table>

**Een opmerking over kenmerklimieten**

Houd er rekening mee dat de kenmerken die via deze integratie worden opgehaald, nog steeds worden afgeboekt op de limieten van uw contractuele kenmerken in [!DNL Adobe Analytics] en [!DNL Adobe Target]. Alleen kenmerken die worden weergegeven via een kenmerkabonnement (stap 5 in [De integratie configureren](#configuring-the-integration)) wordt in mindering gebracht op uw limiet voor de geabonneerde toepassing.

## Veelgestelde vragen {#faqs}

**Hoe verander ik de reeks attributen die ik via deze integratie wil delen?**

Voor een kenmerk dat wordt gedeeld door [!DNL Marketo Measure] naar uw Adobe IMS-organisatie via deze integratie zodat deze zichtbaar is en wordt gebruikt in [!DNL Adobe Analytics], moet het worden opgezocht via een Abonnement van Attributen dat in de Console van de Diensten van de Kern wordt gevormd. Daarom als u een attribuut wilt verwijderen zodat het niet meer binnen verschijnt [!DNL Adobe Analytics], kunt u dit eenvoudig bereiken door het attributenabonnement te schrappen.

U kunt ook de B2B-klantkenmerkverbinding verwijderen in [!DNL Marketo Measure] en maak het opnieuw met het attribuut u niet meer uitgesloten van de verbindingsconfiguratie wenst te delen. Op dezelfde manier om attributen aan de integratie toe te voegen, zult u de bestaande verbinding moeten schrappen en nieuwe creëren met de gewenste attributen die aan de configuratie worden toegevoegd.

Gezien het bovenstaande, adviseert men hoogst dat wanneer het vormen van de attributenverbinding voor het eerst, zo inclusief mogelijk zijn wanneer het selecteren van attributen.

**Wat zijn voorbeelden van gevallen voor deze integratie?**

1. Op account gebaseerde verkeerscijfers: Gebruikend de attributen van de rekeningsnaam, kunt u segmenten van één of meerdere doelrekeningen in Adobe Analytics tot stand brengen en de metriek van het plaatsverkeer voor enkel de ondergroep van verkeer analyseren die uit doelrekeningen voortkomt.
1. Inhoud analyseren: Gebruik de opbrengstmetrische informatie om te analyseren welke plaatsinhoud het meest aansprekend aan klanten die uiteindelijk uw product of dienst kopen, of die een specifieke treinstand van belang bereiken.
1. Live-deal ondersteuning: Verdeel uw verkoopteam met actionable inzicht door plaatsgedrag voor gebruikers te analyseren verbonden aan een specifieke open kans in uw CRM.
