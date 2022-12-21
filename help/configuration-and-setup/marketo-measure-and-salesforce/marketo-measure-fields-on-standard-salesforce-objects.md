---
unique-page-id: 18874574
description: "[!DNL Marketo Measure] Velden op standaard [!DNL Salesforce] Objecten - [!DNL Marketo Measure] - Productdocumentatie"
title: "[!DNL Marketo Measure] Velden op standaard [!DNL Salesforce] Objecten"
exl-id: c9d5254f-06bd-4813-bb29-1a4955b37041
source-git-commit: b910e5aedb9e178058f7af9a6907a1039458ce7a
workflow-type: tm+mt
source-wordcount: '1273'
ht-degree: 0%

---

# [!DNL Marketo Measure] Velden op standaard [!DNL Salesforce] Objecten {#marketo-measure-fields-on-standard-salesforce-objects}

>[!NOTE]
>
>Mogelijk ziet u instructies die &quot;[!DNL Marketo Measure]&quot; in onze documentatie, maar zie nog &quot;Bizible&quot;in uw CRM. We werken eraan dat dit wordt bijgewerkt en de herbranding wordt binnenkort weerspiegeld in uw CRM.

Meer informatie over de verschillende [!DNL Marketo Measure] velden die worden toegevoegd aan [!DNL Salesforce] standaardobjecten.

## Account {#account}

Predictieve betrokkenheidsscore: Dit veld wordt samen met onze ABM-functie gebruikt om een score te leveren met betrekking tot de mate van betrokkenheid van de account en houdt rekening met veel factoren, zoals de frequentie van paginaweergaven, het aantal contactpersonen dat aan de account is gekoppeld, het aantal gesloten opp, enz.

## Case {#case}

We voegen velden toe aan het Case-object voor de eerste aanraak en de eerste aanraakmijlpalen. Dit is voor klanten die het voorwerp van het Geval in plaats van de Lood of het Contact gebruiken en ook het doel van een andere manier dienen om de gegevens te bekijken voor het geval een klant niet ons wilde om verslagen van het Aanraakpunt tot stand te brengen.

Aanraakpuntbron (FT): Dit is de bron van de eerste aanraakinteractie.

Aanraakpuntbron (LC): Dit is de bron van de aanraakinteractie bij het maken van leads.

Marketingkanaal (FT): Dit is het marketingkanaal van de eerste aanraakinteractie.

Marketing Channel (LC): Dit is het marketingkanaal van de &#39;lead creation touch&#39; interactie.

Naam advertentiecampagne (FT): Dit is de campagne UTM, de campagne van de Advertentie van de netwerken van de Advertentie, of [!DNL Salesforce] Campagne van de eerste aanraakinteractie.

Naam advertentiecampagne (LC): Dit is de campagne UTM, de campagne van de Advertentie van de netwerken van de Advertentie, of [!DNL Salesforce] Campagne van de [!UICONTROL lead creation] aanraakinteractie.

Openingspagina (FT): Dit is de openingspagina van de eerste aanraakinteractie.

Openingspagina (LC): Dit is de landingspagina van de [!UICONTROL lead creation] aanraakinteractie.

Aanraakpuntdatum (FT): Dit is de datum van de eerste aanraakinteractie.

Aanraakpuntdatum (LC): Dit is de datum van de aanraakinteractie bij het maken van leads.

## Campagne {#campaign}

Er zijn slechts vier toegevoegde velden, één knop en 1 validatieregel.

UniqueID: Dit veld wordt intern voor ons gebruikt om de verschillende campagnes bij te houden waarmee [!DNL Marketo Measure].

Aanraakpunten koper inschakelen: Dit veld is bestemd voor de daadwerkelijke synchronisatie van campagnes voor het opnemen van offlinetoewijzingen en historische gegevens.

Begindatum aanraakpunt: Dit veld wordt gebruikt voor het instellen van een begindatum voor het toepassen van aanraakpunten op historische campagnes.

Einddatum aanraakpunt: Dit veld wordt gebruikt voor het instellen van een einddatum voor het toepassen van aanraakpunten op historische campagnes. Een algemeen voorbeeld zou de opname van digitale campagnes vóór[!DNL Marketo Measure] en dan het plaatsen van de einddatum als de dag het manuscript werd toegepast.

Aanraakpunt datum bulkupdate (knop): Deze knoop wordt gebruikt om de aanraakpuntdatum van de leden van de Campagne te beheren wanneer de Campagne wordt gesynchroniseerd aangezien wij of de datum van het Lidmaatschap van de Campagne of de eerste reactiedatum uit de doos zullen van verwijzingen voorzien. Als die datumvelden geen nauwkeurige weergave zijn van de werkelijke aanraakpuntdatum, gebruiken we deze knop om de aanraakpuntdatum in te stellen.

Bijwerken [!DNL Marketo Measure] Attributie (validatieregel): Deze regel is vervangen na pakketversie 6.0.

## Campagnelid {#campaign-member}

Er zijn 5 velden en 1 Apex Trigger toegevoegd aan het pakket.

Status aanraakpunt (lead): Dit is een diagnostisch gebied met betrekking tot een eigenschap die niet uit de doos wordt aangezet. We gebruiken dit om te begrijpen of er een aanraakpunt is gemaakt tegen de verwante lead record, of zo niet, waarom.

Status aanraakpunt (contactpersoon): Dit is een diagnostisch gebied met betrekking tot een eigenschap die niet uit de doos wordt aangezet. We gebruiken dit om te begrijpen of er een aanraakpunt is gemaakt op basis van de bijbehorende lijst met contactpersonen, of zo niet, waarom.

Status aanraakpunt (opportunity): Dit is een diagnostisch gebied met betrekking tot een eigenschap die niet uit de doos wordt aangezet. We gebruiken dit om te begrijpen of er een aanraakpunt is gemaakt tegen de verwante opportunityrecord of, zo niet, waarom.

Status aanraakpunt: Dit is de datum waarop de diagnostische velden zijn ingevuld.

Aanraakdatum koper: Dit houdt verband met de [!UICONTROL Bulk Update Touchpoint date] in het Campagneobject. Wanneer dat wordt gebruikt, passen wij de bepaalde datum van het Aanraakpunt op het Lid van de Campagne toe.

OnCampaignMemberDelete: Uit de doos, [!DNL Salesforce] Wordt niet zichtbaar wanneer Campagne-leden worden verwijderd, wat problemen kan veroorzaken met nauwkeurige toewijzingsrapportage. Wanneer een Campagnelid wordt geschrapt, wordt dit teweeggebracht om [!DNL Marketo Measure] het verwijderen van aanraakpunten met betrekking tot dat niet-bestaande campagnelid.

## Contact {#contact}

We voegen velden toe aan het object Contact voor de eerste aanraak en de eerste aanraakmijlpalen. Dit is voor klanten die liever een kenmerk rechtstreeks aan velden laten rapporteren in plaats van aanraakpuntrecords te maken. De meeste van onze klanten gebruiken de recordroute Touchpoint, maar ook deze velden binnen hun automatiseringsplatform.

Aanraakpuntbron (FT): Dit is de bron van de eerste aanraakinteractie.

Aanraakpuntbron (LC): Dit is de bron van de aanraakinteractie bij het maken van leads.

Marketingkanaal (FT): Dit is het marketingkanaal van de eerste aanraakinteractie.

Marketing Channel (LC): Dit is het marketingkanaal van de &#39;lead creation touch&#39; interactie.

Naam advertentiecampagne (FT): Dit is de campagne UTM, de campagne van de Advertentie van de netwerken van de Advertentie, of [!DNL Salesforce] Campagne van de eerste aanraakinteractie.

Naam advertentiecampagne (LC): Dit is de campagne UTM, de campagne van de Advertentie van de netwerken van de Advertentie, of [!DNL Salesforce] Campagne van de [!UICONTROL lead creation] aanraakinteractie.

Openingspagina (FT): Dit is de openingspagina van de eerste aanraakinteractie.

Openingspagina (LC): Dit is de landingspagina van de [!UICONTROL lead creation] aanraakinteractie.

Aanraakpuntdatum (FT): Dit is de datum van de eerste aanraakinteractie.

Aanraakpuntdatum (LC): Dit is de datum van de aanraakinteractie bij het maken van leads.

BizibleID: Dit wordt gebruikt met betrekking tot onze activiteiten attributie en calltrackingmetrics integratie voor de vereniging van het Contact aan touchpoint.

## Lood {#lead}

We voegen velden toe aan het object Lead voor de eerste aanraak en de eerste aanraakmijlpalen. Dit is voor klanten die liever een kenmerk rechtstreeks aan velden laten rapporteren in plaats van aanraakpuntrecords te maken. De meeste van onze klanten gebruiken de recordroute Touchpoint, maar ook deze velden binnen hun automatiseringsplatform.

Aanraakpuntbron (FT): Dit is de bron van de eerste aanraakinteractie.

Aanraakpuntbron (LC): Dit is de bron van de aanraakinteractie bij het maken van leads.

Marketingkanaal (FT): Dit is het marketingkanaal van de eerste aanraakinteractie.

Marketing Channel (LC): Dit is het marketingkanaal van de &#39;lead creation touch&#39; interactie.

Naam advertentiecampagne (FT): Dit is de campagne UTM, de campagne van de Advertentie van de netwerken van de Advertentie, of [!DNL Salesforce] Campagne van de eerste aanraakinteractie.

Naam advertentiecampagne (LC): Dit is de campagne UTM, de campagne van de Advertentie van de netwerken van de Advertentie, of [!DNL Salesforce] Campagne van de aanraakinteractie bij het maken van leads.

Openingspagina (FT): Dit is de openingspagina van de eerste aanraakinteractie.

Openingspagina (LC): Dit is de landingspagina van de aanraakinteractie bij het maken van leads.

Aanraakpuntdatum (FT): Dit is de datum van de eerste aanraakinteractie.

Aanraakpuntdatum (LC): Dit is de datum van de aanraakinteractie bij het maken van leads.

BizibleID: Dit wordt gebruikt met betrekking tot onze activiteiten attributie en calltrackingmetrics integratie voor Lood associatie aan het touchpoint.

## Account {#account-1}

Dit wordt gebruikt voor de toewijzing van leads aan account voor onze ABM-functie. We vullen dit veld om de opzoekrelatie tussen de twee objecten te maken.

## Opportunity {#opportunity}

[!DNL Marketo Measure] Mate van opportunity: Dit gebied wordt gebruikt in het scenario waar een gebied van het douanebedrag hefboomwerking op de Kans is. We wijzen die aangepaste veldwaarde toe aan [!DNL Marketo Measure] Het Bedrag van de kans die een werkschema gebruikt en dan dit gebied voor onze gebieden van de Toewijzing van de Opbrengst op het voorwerp van het Aanraakpunt van de Attributie van de Koper leest.

## Activiteit {#activity}

BizibleID: Dit is voor ons om een aanraakpunt te relateren aan activiteiten voor onze activiteitstoewijzing en het noemen van metriek integratie.

Aanraakdatum koper: Dit is een gebied dat via een werkschema kan worden bevolkt om als datum voor activiteitenattributie te gebruiken en zal voor onze calltrackingmetrics integratie worden bevolkt om te weten wanneer de interactie voorkwam.
