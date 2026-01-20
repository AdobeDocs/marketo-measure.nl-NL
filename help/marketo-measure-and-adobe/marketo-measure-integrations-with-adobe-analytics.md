---
description: '[!DNL Marketo Measure] Integraties met Adobe Analytics -  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] Integraties met  [!DNL Adobe Analytics]'
exl-id: 3a125a15-eb74-454a-afb3-75746a1dfac6
feature: Integration
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 0%

---

# [!DNL Marketo Measure] Integraties met Adobe Analytics {#marketo-measure-integrations-with-adobe-analytics}

Dankzij de integratie van B2B-klantkenmerken kunnen wederzijdse gebruikers van [!DNL Marketo Measure] en Adobe Analytics hun [!DNL Adobe Analytics] -gebruikersprofielen verrijken met waardevolle metagegevens die zijn afgeleid van de [!DNL Marketo Measure] -toewijzingsengine en via de synchronisatiefunctie ervan met CRM&#39;s ([!DNL Microsoft Dynamics] en [!DNL Salesforce] ). Deze is gratis beschikbaar voor alle klanten die [!DNL Adobe Analytics] en [!DNL Marketo Measure] gebruiken.

>[!PREREQUISITES]
>
>U moet actieve abonnementen op zowel [!DNL Marketo Measure] als [!DNL Adobe Analytics] hebben.

## De integratie configureren {#configuring-the-integration}

1. Maak een nieuwe Customer Attributes Data Source in uw Experience Cloud-console. De gedetailleerde instructies [ kunnen hier ](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html) worden gevonden.

   Neem nota van de volgende informatie, nodig in de recentere stappen:

   * De alias-id. Dit kan elke gewenste waarde zijn. We raden &#39;marketeasure_id&#39; aan

   * De hostnaam en referenties van de FTP-server (gebruikersnaam en wachtwoord)

1. Nadat de Customer Attributes Data Source is gemaakt, gaat u verder met het configuratieproces door naar het scherm **[!UICONTROL Integrations]** > **[!UICONTROL Connections]** in het beheermenu [!DNL Marketo Measure] .

1. Klik op de knop **[!UICONTROL Set Up New Customer Attributes Connection]** en volg de instructies om de integratie met klantkenmerken te configureren. De gebruikersinterface vraagt u om de gegevens over de Alias-id- en FTP-verbinding die u hebt verkregen bij het maken van de Customer Attributes Source in uw Core Services Console. Selecteer de set accountkenmerken die u wilt synchroniseren met uw [!DNL Adobe Analytics] -account.

   Voer uw Adobe IMS-organisatie-id in. Deze id wordt weergegeven in de rechterbenedenhoek van uw Adobe Experience Cloud Admin Console. Neem contact op met het Adobe-accountteam (uw accountmanager) voor meer hulp bij het vinden van deze id.

1. Nadat u klaar bent met het creëren van de verbinding in uw [!DNL Marketo Measure] rekening, moet u naar uw console van Experience Cloud terugleiden om [ het schema ](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/validate-schema.html?lang=en) te bevestigen. U hoeft zich geen zorgen te maken over het uploaden van FTP-bestanden. [!DNL Marketo Measure] heeft dat onderdeel voor u geautomatiseerd. Ga naar het schema &quot;Weergeven/bewerken&quot; voor de Source van klantkenmerken die u in Stap 1 hebt gemaakt en vertel Adobe wat de gegevenstypen zijn voor elk van de kenmerken die [!DNL Marketo Measure] namens u heeft geüpload. U kunt desgewenst ook nieuwe weergavefuncties voor de geüploade kenmerken maken.

   Als u ervoor hebt gekozen om kenmerken van uw CRM-accountobject te synchroniseren, wordt u ten zeerste aangeraden nieuwe weergavenamen voor deze kenmerken te kiezen, aangezien [!DNL Marketo Measure] alleen de namen op API-niveau voor deze kenmerken vult, die gewoonlijk niet rapportvriendelijk zijn.

1. De laatste stap bestaat uit het configureren van kenmerkabonnementen voor de Experience Cloud-toepassingen waarin u de kenmerken wilt gebruiken. U kunt Abonnementen configureren voor [!DNL Adobe Analytics] of [!DNL Adobe Target] .  Meer informatie over hoe te om dat te doen [ kan hier worden gevonden ](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/subscription.html).

## Kenmerkbeschrijvingen {#attribute-descriptions}

Wanneer u een B2B-klantkenmerkverbinding maakt, maakt [!DNL Marketo Measure] automatisch een standaardset B2B-klantkenmerken voor u. Deze kenmerken worden in de onderstaande tabel beschreven.

Naast de kenmerken die hieronder worden vermeld, kunt u ook alle kenmerken uploaden die aan het accountobject in uw CRM zijn gekoppeld. Als er meer dan één account aan de opgegeven gebruiker is gekoppeld, vult [!DNL Marketo Measure] alle overeenkomende waarden van accountkenmerken in een lijst met door puntkomma&#39;s gescheiden waarden in.

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
   <td>De accountnamen die aan de opgegeven webbezoeker zijn gekoppeld. Als er meerdere accounts aan de opgegeven gebruiker zijn gekoppeld, vult [!DNL Marketo Measure] alle overeenkomende accountnamen in een lijst met door puntkomma's gescheiden accounts.<br/>
   <strong> Nota:</strong> account.name is de Salesforce-API-vlakke naam voor de naamattributen op het rekeningsvoorwerp. U kunt een betere vertoningsnaam (bijvoorbeeld, "Bedrijf") voor dit attribuut tijdens de stap van de Bevestiging van het Schema van de integratieconfiguratie (stap 4) kiezen.</td>
  </tr>
  <tr> 
   <td>Toegewezen inkomsten - ‹MODEL›</td> 
   <td>De opbrengsten die aan deze klant worden toegewezen vanwege zijn associatie met closed-won-mogelijkheden in uw CRM, zoals berekend door de [!DNL Marketo Measure] attribution engine.<br/>
   Er is één van deze kenmerken voor elk attributiemodel dat uw [!DNL Marketo Measure] -abonnementen toestaan (bijvoorbeeld "Toegewezen inkomsten - Volledig pad").</td>
  </tr>
  <tr> 
   <td>Deëtste Funnel Stage</td> 
   <td>De diepste funnel-fase van elke open mogelijkheid die aan de gegeven gebruiker is gekoppeld.</td>
  </tr>
  <tr> 
   <td>Open kansen</td> 
   <td>Een door puntkomma's gescheiden lijst met de opportuniteid's waaraan de gebruiker is gekoppeld volgens uw CRM-gegevens.</td>
  </tr> 
 </tbody> 
</table>

**een nota over attributengrenzen**

De kenmerken die via deze integratie worden opgehaald, tellen mee voor uw contractuele kenmerklimieten in [!DNL Adobe Analytics] en [!DNL Adobe Target] . Slechts worden de attributen die via een Abonnement van Attributen (stap 5 in [ Vormend de Integratie ](#configuring-the-integration)) tellen tegen uw grens voor de ingetekende toepassing.

## Veelgestelde vragen {#faqs}

**hoe ik de reeks attributen verander die ik via deze integratie wil delen?**

Als een kenmerk dat door [!DNL Marketo Measure] via deze integratie wordt gedeeld aan uw Adobe IMS-organisatie zichtbaar moet zijn en in [!DNL Adobe Analytics] moet worden gebruikt, moet dit kenmerk worden opgezocht via een kenmerkabonnement dat is geconfigureerd in de Core Services Console. Als u een kenmerk wilt verwijderen zodat het niet meer wordt weergegeven in [!DNL Adobe Analytics] , kunt u dit bereiken door het kenmerkabonnement te verwijderen.

U kunt ook de B2B-klantkenmerkverbinding verwijderen in [!DNL Marketo Measure] en deze opnieuw maken met het kenmerk dat u niet meer wilt delen en dat niet meer is uitgesloten van de verbindingsconfiguratie. En als u kenmerken wilt toevoegen aan de integratie, moet u de bestaande verbinding verwijderen en een nieuwe maken met de gewenste kenmerken die aan de configuratie zijn toegevoegd.

Gezien het bovenstaande, adviseert men hoogst dat wanneer het vormen van de attributenverbinding voor het eerst, zo inclusief mogelijk zijn wanneer het selecteren van attributen.

**wat zijn één of ander voorbeeld gebruiksgevallen voor deze integratie?**

1. Op rekening-Gebaseerde Metriek van het Verkeer: Gebruikend de attributen van de rekeningsnaam, kunt u segmenten van één of meerdere doelrekeningen in Adobe Analytics tot stand brengen en de metriek van het plaatsverkeer voor enkel de ondergroep van verkeer analyseren die uit doelrekeningen voortkomt.
1. Content Analytics: gebruik de maatstaf van opbrengsten om te analyseren welke site-inhoud het meest aantrekkelijk is voor klanten die uiteindelijk uw product of service kopen, of voor klanten die een specifieke funnel-fase bereiken.
1. Live-deal ondersteuning: behandel uw verkoopteam met actioneerbare insight door het gedrag van de site te analyseren voor gebruikers die zijn gekoppeld aan een specifieke open mogelijkheid in uw CRM.
