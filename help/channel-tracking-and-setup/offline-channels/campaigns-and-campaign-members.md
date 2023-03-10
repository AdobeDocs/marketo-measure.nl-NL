---
unique-page-id: 18874578
description: Campagne en campagneleden - [!DNL Marketo Measure] - Productdocumentatie
title: Campagne en campagneleden
exl-id: e4e2b154-39ac-4295-a541-7fa6112672e3
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '1155'
ht-degree: 0%

---

# Campagne en campagneleden {#campaigns-and-campaign-members}

[!DNL Salesforce] De campagnes zijn bedoeld om lijsten van Leads en Contacten bij te houden die met een marketingprogramma, of activiteit worden geassocieerd. Dit zijn vaak webinars, of registraties, of beide bezoeken, bijvoorbeeld. Marketers kunnen kiezen of een campagne wordt gecrediteerd op een touchpoint-reis.

## Aanraakpunten inschakelen {#enabling-touchpoints}

De [!DNL Marketo Measure] [!DNL Salesforce] Het pakket bevat een veld met het label &#39;Aanraakpunten koper inschakelen&#39; in het campagneobject. Als het veld eenmaal aan de pagina-indeling is toegevoegd, ziet het er ongeveer als volgt uit:

![](assets/1.png)

De keuzelijst bevat de volgende opties:

![](assets/2.png)

* Inclusief alle campagneleden. Elke leider of contactpersoon die aan de campagne wordt toegevoegd, ontvangt een aanraakpunt dat aan de campagne is gekoppeld.
* Alleen &quot;Reageerde&quot; campagnegeleden opnemen - Alleen leads of Contacten met de status &quot;Responded&quot; voor campagnerelid ontvangen een aanraakpunt voor die campagne.
* Sluit alle campagneleden uit - Geen van de leads of contactpersonen ontvangt een aanraakpunt dat bij die campagne hoort.

Houd er rekening mee dat leden van een campagne een e-mailadres aan hun record moeten hebben gekoppeld om [!DNL Marketo Measure] om een aanraakpunt te maken. Zonder e-mailadres [!DNL Marketo Measure] geen aanraakpunt toewijzen aan het lid van de campagne.

## Synchronisatiedata voor campagne {#campaign-sync-dates}

Met de installatie van de verpakking [!DNL Marketo Measure] bevat ook twee datumvelden op het Campagneobject: Begindatum aanraakpunt en Einddatum aanraakpunt.

Deze data vertellen [!DNL Marketo Measure] wanneer we moeten beginnen of stoppen met het opnemen van campagneleden van de Campagne tot de tochpoint-reis. U kunt ????n datum of beide instellen of helemaal geen.

## Hoofdletters/kleine letters gebruiken voor begindatum aanraakpunt {#use-case-for-touchpoint-start-date}

De begindatum kan worden gebruikt in het geval dat een bestaande campagne wordt gebruikt voor het bijhouden van leads en contactpersonen, maar de gebruiker wil pas beginnen met het meten nadat nieuwe systemen of processen zijn ge??nstalleerd, zodat hij of zij een begindatum eenmalig kan instellen [!DNL Marketo Measure] moeten beginnen met het volgen van die campagneleden.

## Hoofdlettergebruik voor einddatum aanraakpunt {#use-case-for-touchpoint-end-date}

Indien v????r gebruik [!DNL Marketo Measure], gebruikte u een platform van de Automatisering van de Marketing dat de digitale interacties van Leads (de vormbijdragen van IE) bijhield, en toen uploadde die Leads in een [!DNL Saleforce] Tijdens het ontwerpen kunt u het veld Einddatum aanraakpunt gebruiken. U zou de Einddatum van het Aanraakpunt als uw begindatum instellen met [!DNL Marketo Measure] en de Aanraakpunten van de Koper inschakelen, dan zou elk van deze Leads&#39; digitale interactie worden gecre??erd als aanraakpunt. De reden dat u de Einddatum van het Aanraakpunt zult plaatsen om uw Datum van het Begin met te zijn [!DNL Marketo Measure] omdat we deze digitale interacties volgen via ons javascript, zodat we verder kunnen gaan.

![](assets/3.png)

## Campagneleden {#campaign-members}

Campagne-leden zijn genest onder [!UICONTROL Campaigns]en zijn gerelateerd aan een lead of contactpersoon. Een lead of een contactpersoon kan slechts eenmaal aan een campagne worden toegevoegd. Dit kan problematisch zijn afhankelijk van het gebruik van de campagne. Wanneer een Campagne wordt gesynchroniseerd, wordt het campagnemelid gebruikt als marketingactiviteit die in de tochpoint reis wordt gezet en als vormvulling wordt behandeld.

## Status aanraakpunt koper {#buyer-touchpoint-status}

Indien ingeschakeld, [!DNL Marketo Measure] Hiermee wordt een statuswaarde naar het Campagne-lid verplaatst over vier verschillende velden die in het ge??nstalleerde pakket zijn opgenomen: Status aanraakpunt (lead), status aanraakpunt (contact), status aanraakpunt (opportunity) en statusdatum aanraakpunt. Hierdoor kunnen klanten controleren of een aanraakpunt al dan niet is gemaakt als aanraakpunt voor kopers of als aanraakpunt voor koperkenmerken, afhankelijk van het object waarop het betrekking heeft. De datum van de Status van het Aanraakpunt is eenvoudig de laatste datum dat de status op het Lid van de Campagne werd bijgewerkt.

![](assets/4.png)

## Aanraakpunt koper {#buyer-touchpoint-date}

Met de installatie van de verpakking [!DNL Marketo Measure] bevat ook een veld op het campagnetelid met de naam &quot;Aanraakdatum koper&quot;. Hierdoor kan de gebruiker de datum overschrijven die [!DNL Marketo Measure] wordt gebruikt voor de aanraakpuntdatum in de aanraakpuntrecord.

Dit kan nodig zijn als een lijst dagen/weken/maanden na een gebeurtenis is ge??pload. Er zijn manieren om alle records tegelijk bij te werken, zoals hieronder wordt uitgelegd.

![](assets/5.png)

Als u wilt weten of u de datum van het aanraakpunt voor de koper moet gebruiken, kunt u hier zien hoe de datums worden bepaald door [!DNL Marketo Measure] afhankelijk van de [!UICONTROL Sync Type] die is geselecteerd voor de campagne.

Als de [!UICONTROL Sync Type] is ingesteld op &quot;Alle campagneleden opnemen&quot;. Het instellen van de datum van het aanraakpunt heeft prioriteit van boven naar beneden:

* Aanraakpunt koper
* Aanmaakdatum van campagnerelid

Als de [!UICONTROL Sync Type] is ingesteld op Alleen &#39;Reageerde&#39; Campagne-leden opnemen. Het instellen van de datum van het aanraakpunt heeft prioriteit van boven naar beneden:

* Aanraakpunt koper
* Eerste antwoorddatum
   * De eerste datum waarop wordt gereageerd, wordt automatisch ingesteld zodra de status is gewijzigd in &quot;Responded&quot; en is een standaard [!DNL Salesforce] veld dat niet kan worden gewijzigd

* Aanmaakdatum van campagnerelid

## Aanraakpunt datum bulkupdate {#bulk-update-touchpoint-date}

De datum van het aanraakpunt voor updates met bulkobjecten is opgenomen in de ge??nstalleerde versie [!DNL Marketo Measure] [!DNL Salesforce] -pakket en -knop moeten worden toegevoegd aan de pagina-indeling.

![](assets/6.png)

Als een groot aantal verslagen van het Lid van de Campagne moet worden bijgewerkt, kunt u gebruiken [!UICONTROL Bulk Update Touchpoint Date] aan massa bewerken.

Als er unieke gebruiksgevallen zijn die niet door deze interface worden bestreken, kunt u ook de opdracht [Data Loader](https://dataloader.io/){target="_blank"} als u de records wilt exporteren, brengt u de wijziging aan en uploadt u de records terug naar.

Begin door naar de verslagen te zoeken en degenen te filtreren die u een Datum van het Aanraakpunt van de Koper wilt plaatsen voor.

>[!CAUTION]
>
>Er is ????n zoekopdracht die niet werkt, die in het onderstaande voorbeeld wordt weergegeven. De gebruikersinterface biedt geen ondersteuning voor zoeken naar null-aanraakpuntdatums voor kopers (de onderstaande zoekopdracht werkt niet):

![](assets/7.png)

Als u de zoekopdracht niet hoeft te gebruiken en alleen de datums wilt toepassen op elke record in Campagne-leden, gebruikt u &quot;[!UICONTROL Include All Records]&quot; selectievakje (zie onderstaande schermafbeelding), waarmee alle records op alle pagina&#39;s worden gecontroleerd.

Selecteer de datum en tijd in de kalenderkiezer. Als u de huidige datum en tijd wilt selecteren, klikt u op de datum/tijd die naast de kalenderkiezer wordt weergegeven.

Wanneer uw datum en tijd zijn ingesteld, klikt u op de knop **[!UICONTROL Update Selected Records]** om de wijzigingen toe te passen.

![](assets/8.png)

## Campagnekosten {#campaign-costs}

Alles over campagnekosten [in dit artikel](/help/marketing-spend/spend-management/crm-campaign-costs.md).

## Campagne verwijderen {#campaign-member-removal}

De manier waarop [!DNL Marketo Measure] houdt bij met om het even welke geschrapte verslagen in Salesforce, of zij of de Rekeningen of de Kansen worden geschrapt moeten die verslagen in API zien en volgen dat een ingang als &quot;IsDelette&quot;wordt gemerkt. Helaas heeft Salesforce met Campagneleden een andere manier ge??ntroduceerd om deze Campagneleden uit een Campagne te verwijderen. Ze zijn eigenlijk net gemarkeerd als &quot;verwijderd&quot; in plaats van &quot;verwijderd&quot;. Het probleem is dus dat er nog steeds in Salesforce aanraakpunten woonden die verband hielden met verwijderde campagneleden.

Om dit probleem op te lossen, [!DNL Marketo Measure] een [!DNL Marketo Measure] Het voorwerp van de geschiedenis en een trekker om te volgen wanneer de Leden van de Campagne worden verwijderd en dan het overeenkomstige aanraakpunt schrappen. **U hebt [!DNL Marketo Measure] Marketing Analytics-pakket V6.15 of hoger** om deze functie te gebruiken.

>[!CAUTION]
>
>Houd er rekening mee dat met deze trigger geen campagnegeleden worden bijgehouden die in het verleden zijn verwijderd. Dit werkt dus alleen als u verder gaat. Als u een groot aantal aanraakpunten van leden van de campagne uit het verleden moet verwijderen, neemt u contact op met [Marketo-ondersteuning](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] Universiteit: Campagneobjectvelden](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c63007334d9f0367662b758)
>
>[[!DNL Marketo Measure] Universiteit: Offlinekanalen toewijzen](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c630eca34d9f0367662b77f)
