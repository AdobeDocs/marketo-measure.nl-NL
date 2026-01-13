---
description: Campagnes en Campagneleden -  [!DNL Marketo Measure]
title: Campagne en campagneleden
exl-id: e4e2b154-39ac-4295-a541-7fa6112672e3
feature: Channels
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '1235'
ht-degree: 0%

---


# Campagne en campagneleden {#campaigns-and-campaign-members}

[!DNL Salesforce] Campagnes zijn bedoeld voor het bijhouden van lijsten met leads en contactpersonen die aan een marketingprogramma of -activiteit zijn gekoppeld. Dit zijn vaak webinars, of registraties, of beide bezoeken, bijvoorbeeld. Marketers kunnen kiezen of een campagne wordt gecrediteerd op een touchpoint-reis.

>[!NOTE]
>Dit artikel behandelt een verouderd proces. Wij moedigen gebruikers aan om het [ nieuwe, verbeterde in-app proces ](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"} te gebruiken.

## Aanraakpunten inschakelen {#enabling-touchpoints}

Het pakket [!DNL Marketo Measure] [!DNL Salesforce] bevat een veld met het label &#39;Aanraakpunten koper inschakelen&#39; in het object Campagne. Als het veld eenmaal aan de pagina-indeling is toegevoegd, ziet het er ongeveer als volgt uit:

![ de paginalay-out van de Campagne van Salesforce die het gebied van Aanraakpunten van de Koper toelaat ](assets/1.png) toont

De keuzelijst bevat de volgende opties:

![ laat de keuzelijst van de Aanraakpunten van de Koper met de opties van de campagnerelidopname toe ](assets/2.png)

* Inclusief alle campagneleden. Elke leider of contactpersoon die aan de campagne wordt toegevoegd, ontvangt een aanraakpunt dat aan de campagne is gekoppeld.
* Alleen &quot;Reageerde&quot; campagnegeleden opnemen - Alleen leads of Contacten met de status &quot;Responded&quot; voor campagnerelid ontvangen een aanraakpunt voor die campagne.
* Sluit alle campagneleden uit - Geen van de leads of contactpersonen ontvangt een aanraakpunt dat bij die campagne hoort.

Houd er rekening mee dat leden van een campagne een e-mailadres moeten hebben dat aan hun record is gekoppeld, zodat [!DNL Marketo Measure] een aanraakpunt kan maken. Zonder een e-mailadres wijst [!DNL Marketo Measure] geen aanraakpunt toe aan het lid van de campagne.

## Synchronisatiedata voor campagne {#campaign-sync-dates}

Bij de installatie van het pakket bevat [!DNL Marketo Measure] ook twee datumvelden in het Campagneobject: Begindatum aanraakpunt en Einddatum aanraakpunt.

Deze data vertellen [!DNL Marketo Measure] wanneer we moeten beginnen of stoppen met het opnemen van campagneleden van de Campagne tot de tochpoint-reis. U kunt één datum of beide instellen of helemaal geen.

## Hoofdletters/kleine letters gebruiken voor begindatum aanraakpunt {#use-case-for-touchpoint-start-date}

De begindatum kan worden gebruikt als een bestaande campagne wordt gebruikt voor het bijhouden van leads en contactpersonen, maar de gebruiker wil pas beginnen met meten als er nieuwe systemen of processen zijn geïnstalleerd, zodat hij of zij een begindatum kan instellen wanneer [!DNL Marketo Measure] de betreffende leden moet volgen.

## Hoofdlettergebruik voor einddatum aanraakpunt {#use-case-for-touchpoint-end-date}

Als u voor het gebruik van [!DNL Marketo Measure] een marketingplatform hebt gebruikt dat de digitale interacties van Leads bijhield (verzending van IE-formulieren) en deze Leads vervolgens uploadde naar een [!DNL Saleforce] -campagne, kunt u het veld Einddatum aanraakpunt gebruiken. Als u de einddatum van het aanraakpunt instelt als de begindatum met [!DNL Marketo Measure] en Aanraakpunten voor kopers inschakelt, wordt de digitale interactie van deze leads gemaakt als aanraakpunt. De reden dat u de Einddatum van het Aanraakpunt zult plaatsen om uw Datum van het Begin met [!DNL Marketo Measure] te zijn is omdat, vooruit, wij deze digitale interactie door ons javascript zullen volgen.

![ verslag van de Campagne die de gebieden van de Datum en van de Datum van het Einde van het Aanraakpunt tonen ](assets/3.png)

## Campagneleden {#campaign-members}

Campagneleden zijn genest onder [!UICONTROL Campaigns] en zijn verwant aan een lead of contactpersoon. Een lead of een contactpersoon kan slechts eenmaal aan een campagne worden toegevoegd. Dit kan problematisch zijn afhankelijk van het gebruik van de campagne. Wanneer een Campagne wordt gesynchroniseerd, wordt het campagnecelid gebruikt als marketingactiviteit die in de tochpoint reis wordt gezet en als vormvulling wordt behandeld.

## Buyer Touchpoint-status {#buyer-touchpoint-status}

Als deze optie is ingeschakeld, plaatst [!DNL Marketo Measure] een statuswaarde op het Campagne-lid in vier verschillende velden die in het geïnstalleerde pakket zijn opgenomen: Touchpoint Status (lead), Touchpoint Status (contact), Touchpoint Status (opportunity) en Status Date van het aanraakpunt. Hierdoor kunnen klanten controleren of een aanraakpunt al dan niet is gemaakt als Buyer Touchpoint of Buyer Attribution Touchpoint, afhankelijk van het object waarmee het is gerelateerd. De datum van de Status van het Aanraakpunt is eenvoudig de laatste datum dat de status op het Lid van de Campagne werd bijgewerkt.

![ het verslag van het Lid van de campagne die de gebieden van de Status van het Punt voor Lood, Contact, Kans, en Datum van de Status tonen ](assets/4.png)

## Buyer Touchpoint-datum {#buyer-touchpoint-date}

Als het pakket is geïnstalleerd, bevat [!DNL Marketo Measure] ook een veld in het campagnetelid met de naam &quot;Buyer Touchpoint Date&quot;. Hierdoor kan de gebruiker de datum overschrijven die [!DNL Marketo Measure] zou gebruiken voor de datum van het aanraakpunt in de aanraakpuntrecord.

Dit kan nodig zijn als een lijst dagen/weken/maanden na een gebeurtenis is geüpload. Er zijn manieren om alle records tegelijk bij te werken, zoals hieronder wordt uitgelegd.

![ het verslag van het Lid van de campagne met het gebied van de Datum van Buyer Touchpoint voor datumopheffing ](assets/5.png)

Als u wilt weten of u de Buyer Touchpoint-datum moet gebruiken, gaat u als volgt te werk hoe de datums door [!DNL Marketo Measure] worden bepaald, afhankelijk van de [!UICONTROL Sync Type] die voor de campagne is geselecteerd.

Als de instelling van [!UICONTROL Sync Type] is ingesteld op &quot;Alle leden van de campagne opnemen&quot;, heeft het instellen van de datum van het aanraakpunt prioriteit van boven naar beneden:

* Buyer Touchpoint-datum
* Aanmaakdatum van campagnerelid

Als de instelling van [!UICONTROL Sync Type] is ingesteld op Alleen &#39;Reageerde&#39; Campagne-leden opnemen, heeft het instellen van de datum van het aanraakpunt prioriteit van boven naar beneden:

* Buyer Touchpoint-datum
* Eerste beantwoorde datum
   * De eerste datum waarop wordt gereageerd, wordt automatisch ingesteld zodra de status is gewijzigd in &quot;Responded&quot; en is een standaard [!DNL Salesforce] veld dat niet kan worden gewijzigd

* Aanmaakdatum van campagnerelid

## Aanraakpunt datum bulkupdate {#bulk-update-touchpoint-date}

De datum van het aanraakpunt voor bulkupdates is opgenomen in het geïnstalleerde [!DNL Marketo Measure] [!DNL Salesforce] -pakket en de knop moet worden toegevoegd aan de pagina-indeling.

![ de paginalay-out van de Campagne met de Bulk knoop van de Datum van het Aanraakpunt van de Update ](assets/6.png)

Als een groot aantal Campagne-lidverslagen moet worden bijgewerkt, kunt u de [!UICONTROL Bulk Update Touchpoint Date] knoop aan massa uitgeven.

Als er unieke gebruiksgevallen zijn die deze interface niet behandelt, kunt u de [ Loader van Gegevens ](https://dataloader.io/){target="_blank"} ook gebruiken om de verslagen uit te voeren, de verandering aan te brengen, en de verslagen terug binnen te uploaden.

Begin door naar de verslagen te zoeken en degenen te filtreren die u een Datum van Buyer Touchpoint wilt plaatsen voor.

>[!CAUTION]
>Er is één zoekopdracht die niet werkt, die in het onderstaande voorbeeld wordt weergegeven. De gebruikersinterface biedt geen ondersteuning voor het zoeken naar null Buyer Touchpoint-datums (de onderstaande zoekopdracht werkt niet):

![ Bulk de interface die van de Update unsupported onderzoek naar ongeldige Datums van Buyer Touchpoint toont ](assets/7.png)

Als u niet het onderzoek hoeft te gebruiken en enkel de data op elk verslag van het Lid van de Campagne toe te passen, gebruik &quot;[!UICONTROL Include All Records]&quot;checkbox (zie hieronder screenshot), die alle verslagen op alle pagina&#39;s zal controleren.

Selecteer de datum en de tijd in de kalenderkiezer. Als u de huidige datum en tijd wilt selecteren, klikt u op de datum/tijd die naast de kalenderkiezer wordt weergegeven.

Nadat u de datum en tijd hebt ingesteld, klikt u op de knop **[!UICONTROL Update Selected Records]** om de wijzigingen toe te passen.

![ Bulk de interface van de Datum van het Aanraakpunt van de Update met kalenderplukker en Update Geselecteerde knoop van Verslagen ](assets/8.png)

## Campagnekosten {#campaign-costs}

Leer allen over de Kosten van de Campagne [ in dit artikel ](/help/marketing-spend/crm-campaign-costs.md){target="_blank"}.

## Campagne verwijderen van lid {#campaign-member-removal}

De manier waarop [!DNL Marketo Measure] bijhoudt met verwijderde records in Salesforce, of ze nu Leads of Accounts of Opportunity zijn verwijderd, is om die records in de API te bekijken en te controleren dat een item is gemarkeerd als &quot;IsDelette&quot;. Helaas heeft Salesforce met Campagneleden een andere manier geïntroduceerd om deze Campagneleden uit een campagne te verwijderen. Ze zijn eigenlijk net zo gemarkeerd als &quot;verwijderd&quot; in plaats van &quot;verwijderd&quot;. Het probleem is dus dat er nog steeds in Salesforce aanraakpunten woonden die verband hielden met verwijderde campagneleden.

Om dit probleem te verhelpen, heeft [!DNL Marketo Measure] een [!DNL Marketo Measure] History-object gemaakt en een trigger om te volgen wanneer Campagneleden worden verwijderd en vervolgens het overeenkomstige aanraakpunt verwijderd. **u [!DNL Marketo Measure] het pakket van Analytics van de Marketing V6.15 of hoger** zult nodig hebben om deze eigenschap te gebruiken.

>[!CAUTION]
>Houd er rekening mee dat met deze trigger geen campagnegeleden worden bijgehouden die in het verleden zijn verwijderd. Dit werkt dus alleen als u verder gaat. Als u een groot aantal afgelopen de contactpunten van campagnegeleden moet verwijderen, contacteer [ de Steun van Marketo ](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

>[!MORELIKETHIS]
>[[!DNL Marketo Measure]  Leerprogramma&#39;s: De Gebieden van de Objecten van de campagne ](https://experienceleague.adobe.com/en/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-salesforce/campaign-object-fields){target="_blank"}
>[[!DNL Marketo Measure] Zelfstudies: Offlinekanalen toewijzen ](https://experienceleague.adobe.com/en/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-salesforce/mapping-offline-channels){target="_blank"}
