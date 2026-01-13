---
description: '[!DNL Marketo Measure] Gebieden op Standaard  [!DNL Salesforce]  Voorwerpen -  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] Gebieden op Standaard  [!DNL Salesforce]  Voorwerpen'
exl-id: c9d5254f-06bd-4813-bb29-1a4955b37041
feature: Salesforce
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '666'
ht-degree: 0%

---


# [!DNL Marketo Measure] Velden op standaard [!DNL Salesforce] -objecten {#marketo-measure-fields-on-standard-salesforce-objects}

>[!NOTE]
>U kunt instructies zien die &quot;[!DNL Marketo Measure]&quot;in de documentatie specificeren, maar nog zie &quot;Bizible&quot;in uw CRM. We werken eraan dat dit wordt bijgewerkt en de herbranding wordt binnenkort weerspiegeld in uw CRM.

Meer informatie over de verschillende [!DNL Marketo Measure] -velden die aan [!DNL Salesforce] -standaardobjecten worden toegevoegd.

## Account {#account}

Predictive Engagement Score: dit veld wordt met onze ABM-functie gebruikt om een score te leveren die gerelateerd is aan hoe betrokken de account is en houdt rekening met vele factoren zoals de recenentie van paginaweergaven, het aantal contactpersonen dat aan de account is gekoppeld, het aantal gesloten opp, enz.

## Campaign {#campaign}

Er zijn slechts vier toegevoegde velden, één knop en 1 validatieregel.

UniqueID: Dit veld wordt intern voor ons gebruikt om de verschillende campagnes bij te houden die met [!DNL Marketo Measure] worden gesynchroniseerd.

Aanraakpunten koper inschakelen: dit veld is bedoeld voor de feitelijke synchronisatie van campagnes voor het opnemen van offlinetoewijzingen en historische gegevens.

Begindatum aanraakpunt: dit veld wordt gebruikt voor het instellen van de begindatum van het toepassen van aanraakpunten op historische campagnes.

Einddatum aanraakpunt: dit veld wordt gebruikt voor het instellen van een einddatum voor het toepassen van aanraakpunten op historische campagnes. Een gemeenschappelijk voorbeeld zou de opneming van digitale campagnes pre- [!DNL Marketo Measure] en dan plaatsend de einddatum aangezien de dag het manuscript werd toegepast.

Bulk Update Touchpoint Date (Button): deze knop wordt gebruikt voor het beheren van de aanraakpuntdatum van de leden van de campagne wanneer de campagne wordt gesynchroniseerd omdat we verwijzen naar de datum van het Campagne-lidmaatschap of de eerste responsdatum uit het vak. Als die datumvelden geen nauwkeurige weergave zijn van de werkelijke aanraakpuntdatum, gebruiken we deze knop om de aanraakpuntdatum in te stellen.

[!DNL Marketo Measure] Kenmerk bijwerken (validatieregel): deze regel wordt vervangen na pakketversie 6.0.

## Campagnelid {#campaign-member}

Er zijn 5 velden en 1 Apex Trigger toegevoegd aan het pakket.

Status aanraakpunt (lead): dit is een diagnostisch veld dat gerelateerd is aan een functie die niet uit het vak is ingeschakeld. We gebruiken dit om te begrijpen of er een aanraakpunt is gemaakt tegen de verwante lead record, of zo niet, waarom.

Status aanraakpunt (contactpersoon): dit is een diagnostisch veld dat gerelateerd is aan een functie die niet uit het vak is ingeschakeld. We gebruiken dit om te begrijpen of er een aanraakpunt is gemaakt op basis van de bijbehorende lijst met contactpersonen, of zo niet, waarom.

Status aanraakpunt (Opportunity): dit is een diagnostisch veld dat gerelateerd is aan een functie die niet uit het vak is ingeschakeld. We gebruiken dit om te begrijpen of er een aanraakpunt is gemaakt tegen de verwante opportunityrecord of, zo niet, waarom.

Status aanraakpunt Datum: dit is de datum waarop de diagnostische velden zijn ingevuld.

Buyer Touchpoint Date: Dit is gerelateerd aan de knop [!UICONTROL Bulk Update Touchpoint date] van het Campagneobject. Wanneer dat wordt gebruikt, passen wij de bepaalde aanraakpuntdatum op het Lid van de Campagne toe.

OnCampaignMemberDelete: Out of the box, [!DNL Salesforce] maakt geen deel uit van de campagne wanneer leden van de campagne worden verwijderd, wat problemen kan veroorzaken met nauwkeurige toewijzingsrapportage. Wanneer een Campagnelid wordt geschrapt, wordt dit teweeggebracht om [!DNL Marketo Measure] te informeren om Aanraakpunten met betrekking tot dat niet bestaande Lid van de Campagne te verwijderen.

## Lood {#lead}

Het veld Bizible Account wordt gebruikt voor de toewijzing van leads aan account voor onze ABM-functie. We vullen dit veld om de opzoekrelatie tussen de twee objecten te maken.

## Account {#account-1}

Dit wordt gebruikt voor de toewijzing van leads aan account voor onze ABM-functie. We vullen dit veld om de opzoekrelatie tussen de twee objecten te maken.

## Kans {#opportunity}

[!DNL Marketo Measure] Bedrag van de Kans: Dit gebied wordt gebruikt in het scenario waar een gebied van de douanehoeveelheid op de Kans wordt gebruikt. Die aangepaste veldwaarde wordt aan de hand van een workflow toegewezen aan [!DNL Marketo Measure] Opportunity Amount en vervolgens wordt dit veld gelezen voor de toewijzingsvelden voor inkomsten in het Buyer Attribution Touchpoint-object.

## Activiteit {#activity}

BizibleID: Dit is voor ons om een aanraakpunt te relateren aan activiteiten voor onze activiteitstoewijzing en calltracking metrics integratie.

Buyer Touchpoint Date: Dit is een veld dat kan worden ingevuld via een workflow die kan worden gebruikt als datum voor activiteitentoewijzing en dat wordt gevuld zodat onze integratie van calltrackingmetrics weet wanneer de interactie heeft plaatsgevonden.
