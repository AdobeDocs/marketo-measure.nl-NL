---
unique-page-id: 18874574
description: "[!DNL Marketo Measure] Velden op standaard [!DNL Salesforce] Objecten - [!DNL Marketo Measure] - Productdocumentatie"
title: "[!DNL Marketo Measure] Velden op standaard [!DNL Salesforce] Objecten"
exl-id: c9d5254f-06bd-4813-bb29-1a4955b37041
feature: Salesforce
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '1273'
ht-degree: 0%

---

# [!DNL Marketo Measure] Velden op standaard [!DNL Salesforce] Objecten {#marketo-measure-fields-on-standard-salesforce-objects}

>[!NOTE]
>
>Mogelijk ziet u instructies die &quot;[!DNL Marketo Measure]&quot; in onze documentatie, maar zie nog &quot;Bizible&quot;in uw CRM. We werken eraan dat dit wordt bijgewerkt en de herbranding wordt binnenkort weerspiegeld in uw CRM.

Meer informatie over de verschillende [!DNL Marketo Measure] velden die worden toegevoegd aan [!DNL Salesforce] standaardobjecten

## Account {#account}

Predictive Engagement Score: dit veld wordt met onze ABM-functie gebruikt om een score te leveren die gerelateerd is aan hoe betrokken de account is en houdt rekening met vele factoren zoals de recenentie van paginaweergaven, het aantal contactpersonen dat aan de account is gekoppeld, het aantal gesloten opp, enz.

## Kwestie {#case}

We voegen velden toe aan het Case-object voor de eerste aanraak en de eerste aanraakmijlpalen. Dit is voor klanten die het voorwerp van het Geval in plaats van de Lood of het Contact gebruiken en ook het doel van een andere manier dienen om de gegevens te bekijken voor het geval een klant niet ons wilde om verslagen van het Aanraakpunt tot stand te brengen.

Aanraakpuntbron (FT): dit is de bron van de eerste aanraakinteractie.

Aanraakpuntbron (LC): dit is de bron van de aanraakinteractie bij het maken van leads.

Marketing Channel (FT): dit is het marketingkanaal van de eerste aanraakinteractie.

Marketing Channel (LC): dit is het marketingkanaal van de aanraakinteractie bij het maken van leads.

Ad Campaign Name (FT): Dit is de UTM-campagne, de Ad Campaign van de advertentienetwerken, of [!DNL Salesforce] Campagne van de eerste aanraakinteractie.

Naam advertentiecampagne (LC): Dit is de campagne UTM, en campagne van de Advertentienetwerken, of [!DNL Salesforce] Campagne van de [!UICONTROL lead creation] aanraakinteractie.

Landing Page (FT): Dit is de landingspagina van de eerste aanraakinteractie.

Openingspagina (LC): Dit is de landingspagina van de [!UICONTROL lead creation] aanraakinteractie.

Aanraakpunt Datum (FT): dit is de datum van de eerste aanraakinteractie.

Aanraakpunt Datum (LC): dit is de datum van de aanraakinteractie bij het maken van de lead.

## Campagne {#campaign}

Er zijn slechts vier toegevoegde velden, één knop en 1 validatieregel.

UniqueID: Dit veld wordt intern voor ons gebruikt om de verschillende campagnes bij te houden waarmee wordt gesynchroniseerd [!DNL Marketo Measure].

Aanraakpunten koper inschakelen: dit veld is bedoeld voor de feitelijke synchronisatie van campagnes voor het opnemen van offlinetoewijzingen en historische gegevens.

Begindatum aanraakpunt: dit veld wordt gebruikt voor het instellen van de begindatum van het toepassen van aanraakpunten op historische campagnes.

Einddatum aanraakpunt: dit veld wordt gebruikt voor het instellen van een einddatum voor het toepassen van aanraakpunten op historische campagnes. Een algemeen voorbeeld zou de opname van digitale campagnes vóór[!DNL Marketo Measure] en dan het plaatsen van de einddatum als de dag het manuscript werd toegepast.

Bulk Update Touchpoint Date (Button): deze knop wordt gebruikt voor het beheren van de aanraakpuntdatum van de leden van de campagne wanneer de campagne wordt gesynchroniseerd omdat we verwijzen naar de datum van het Campagne-lidmaatschap of de eerste responsdatum uit het vak. Als die datumvelden geen nauwkeurige weergave zijn van de werkelijke aanraakpuntdatum, gebruiken we deze knop om de aanraakpuntdatum in te stellen.

Bijwerken [!DNL Marketo Measure] Attribution (Validatieregel): deze regel wordt vervangen na pakketversie 6.0.

## Campagnelid {#campaign-member}

Er zijn 5 velden en 1 Apex Trigger toegevoegd aan het pakket.

Status aanraakpunt (lead): dit is een diagnostisch veld dat gerelateerd is aan een functie die niet uit het vak is ingeschakeld. We gebruiken dit om te begrijpen of er een aanraakpunt is gemaakt tegen de verwante lead record, of zo niet, waarom.

Status aanraakpunt (contactpersoon): dit is een diagnostisch veld dat gerelateerd is aan een functie die niet uit het vak is ingeschakeld. We gebruiken dit om te begrijpen of er een aanraakpunt is gemaakt op basis van de bijbehorende lijst met contactpersonen, of zo niet, waarom.

Status aanraakpunt (Opportunity): dit is een diagnostisch veld dat gerelateerd is aan een functie die niet uit het vak is ingeschakeld. We gebruiken dit om te begrijpen of er een aanraakpunt is gemaakt tegen de verwante opportunityrecord of, zo niet, waarom.

Status aanraakpunt Datum: dit is de datum waarop de diagnostische velden zijn ingevuld.

Aanraakpunt koper Datum: Dit is gerelateerd aan de [!UICONTROL Bulk Update Touchpoint date] in het Campagneobject. Wanneer dat wordt gebruikt, passen wij de bepaalde aanraakpuntdatum op het Lid van de Campagne toe.

OnCampaignMemberDelete: Out of the box, [!DNL Salesforce] Wordt niet zichtbaar wanneer Campagne-leden worden verwijderd, wat problemen kan veroorzaken met nauwkeurige toewijzingsrapportage. Wanneer een Campagnelid wordt geschrapt, wordt dit teweeggebracht om [!DNL Marketo Measure] het verwijderen van aanraakpunten met betrekking tot dat niet-bestaande campagnelid.

## Contact {#contact}

We voegen velden toe aan het object Contact voor de eerste aanraak en de eerste aanraakmijlpalen. Dit is voor klanten die liever een kenmerk rechtstreeks aan velden laten rapporteren in plaats van aanraakpuntrecords te maken. De meeste van onze klanten gebruiken de recordroute van het aanraakpunt, maar ook deze velden binnen hun automatiseringsplatform.

Aanraakpuntbron (FT): dit is de bron van de eerste aanraakinteractie.

Aanraakpuntbron (LC): dit is de bron van de aanraakinteractie bij het maken van leads.

Marketing Channel (FT): dit is het marketingkanaal van de eerste aanraakinteractie.

Marketing Channel (LC): dit is het marketingkanaal van de aanraakinteractie bij het maken van leads.

Ad Campaign Name (FT): Dit is de UTM-campagne, de Ad Campaign van de advertentienetwerken, of [!DNL Salesforce] Campagne van de eerste aanraakinteractie.

Naam advertentiecampagne (LC): Dit is de campagne UTM, en campagne van de Advertentienetwerken, of [!DNL Salesforce] Campagne van de [!UICONTROL lead creation] aanraakinteractie.

Landing Page (FT): Dit is de landingspagina van de eerste aanraakinteractie.

Openingspagina (LC): Dit is de landingspagina van de [!UICONTROL lead creation] aanraakinteractie.

Aanraakpunt Datum (FT): dit is de datum van de eerste aanraakinteractie.

Aanraakpunt Datum (LC): dit is de datum van de aanraakinteractie bij het maken van de lead.

BizibleID: Dit wordt gebruikt met betrekking tot onze activiteiten attributie en calltrackingmetrics integratie voor de vereniging van het Contact aan touchpoint.

## Lood {#lead}

We voegen velden toe aan het object Lead voor de eerste aanraak en de eerste aanraakmijlpalen. Dit is voor klanten die liever een kenmerk rechtstreeks aan velden laten rapporteren in plaats van aanraakpuntrecords te maken. De meeste van onze klanten gebruiken de recordroute van het aanraakpunt, maar ook deze velden binnen hun automatiseringsplatform.

Aanraakpuntbron (FT): dit is de bron van de eerste aanraakinteractie.

Aanraakpuntbron (LC): dit is de bron van de aanraakinteractie bij het maken van leads.

Marketing Channel (FT): dit is het marketingkanaal van de eerste aanraakinteractie.

Marketing Channel (LC): dit is het marketingkanaal van de aanraakinteractie bij het maken van leads.

Ad Campaign Name (FT): Dit is de UTM-campagne, de Ad Campaign van de advertentienetwerken, of [!DNL Salesforce] Campagne van de eerste aanraakinteractie.

Naam advertentiecampagne (LC): Dit is de campagne UTM, en campagne van de Advertentienetwerken, of [!DNL Salesforce] Campagne van de aanraakinteractie bij het maken van leads.

Landing Page (FT): Dit is de landingspagina van de eerste aanraakinteractie.

Openingspagina (LC): dit is de openingspagina van de aanraakinteractie bij het maken van de lead.

Aanraakpunt Datum (FT): dit is de datum van de eerste aanraakinteractie.

Aanraakpunt Datum (LC): dit is de datum van de aanraakinteractie bij het maken van de lead.

BizibleID: Dit wordt gebruikt met betrekking tot onze activiteiten attributie en calltrackingmetrics integratie voor Lood associatie aan touchpoint.

## Account {#account-1}

Dit wordt gebruikt voor de toewijzing van leads aan account voor onze ABM-functie. We vullen dit veld om de opzoekrelatie tussen de twee objecten te maken.

## Opportunity {#opportunity}

[!DNL Marketo Measure] Het Bedrag van de kans: Dit gebied wordt gebruikt in het scenario waar een gebied van het douanebedrag hefboomwerking op de Kans is. We wijzen die aangepaste veldwaarde toe aan [!DNL Marketo Measure] Het Bedrag van de kans die een werkschema gebruikt en dan dit gebied voor onze gebieden van de Toewijzing van de Opbrengst op het voorwerp van het Aanraakpunt van de Attributie van de Koper leest.

## Activiteit {#activity}

BizibleID: Dit is voor ons om een aanraakpunt te relateren aan activiteiten voor onze activiteitstoewijzing en calltracking metrics integratie.

Aanraakdatum koper: dit is een veld dat kan worden ingevuld via een workflow die kan worden gebruikt als de datum voor activiteitentoewijzing en dat zal worden gevuld zodat onze integratie van calltrackingmetriek weet wanneer de interactie heeft plaatsgevonden.
