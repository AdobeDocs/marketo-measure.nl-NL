---
description: Opmerkingen bij de huidige release - [!DNL Marketo Measure]
title: Opmerkingen bij de huidige release
exl-id: e93ff03e-ea21-41f4-abb8-32313ee74c0c
feature: Release Notes
source-git-commit: 9f374537dd3690b5c904e2ac1933ff460dc66282
workflow-type: tm+mt
source-wordcount: '793'
ht-degree: 0%

---

# Opmerkingen bij de release: 2024 {#release-notes-2024}

Zie hieronder voor alle nieuwe en bijgewerkte functies voor onze 2024-releases.

## Q3 Release {#q3-release}

<p>

**Herinnering: Salesforce Field Deprecations - 14 juni**

Zoals vorig jaar is aangekondigd, zullen we [onze exporttaken geleidelijk afbouwen naar lead-/contactpersoonobjecten](https://nation.marketo.com/t5/employee-blogs/marketo-measure-salesforce-lead-and-contact-field-deprecation-06/ba-p/350179){target="_blank"} om onze integratie te vereenvoudigen en de noodzaak om naar Salesforce-standaardobjecten te exporteren te elimineren. U kunt dezelfde gegevens verkrijgen van uw Touchpoint-objecten door de stappen uit te voeren [hier gedocumenteerd](/help/release-notes/previous-releases/2023.md#deprecations){target="_blank"}. We delen ook documentatie over het maken van workflows om deze gegevens toe te voegen aan het object Lead/Contact. De afschrijving wordt van kracht op 14 juni 2024.

Deze wijziging zal twee belangrijke voordelen opleveren:

* **Lagere kosten voor salesforce-API**: Klanten kunnen verwachten hun kosten voor de Salesforce-API met ongeveer 10% te verlagen.
* **Gestroomlijnde integratie**: Het hoogste aantal fouten in onze exporttaken houdt verband met deze processen. Als we ze verwijderen, wordt onze integratie aanzienlijk gestroomlijnd.

**Toegewezen opportuniteitsdashboard**

We zijn blij om de nieuwe [Toegewezen opportuniteitsdashboard](/help/marketo-measure-discover-ui/dashboards/attributed-opportunity-dashboard.md){target="_blank"}, ontworpen om u een uitgebreid overzicht te geven van hoe uw marketinginspanningen bijdragen aan zowel de ontluikende als de rijpe pijpleidingsmogelijkheden. Met dit dashboard kunt u de details bekijken van elke open en gesloten kans die aan uw strategieën is toe te schrijven, met de flexibiliteit om per opportuniteitsfase te filteren. Het biedt inzicht in welke kanalen, subkanalen, of campagnes het hoogst in termen van toegewezen opportuniteitsbedrag zijn, en toont het totale toegewezen opportuniteitsbedrag samen met het aantal toegewezen open en gesloten kansen.

**Marketo Engage Cookie Sync voor Marketo Measure Ultimate**

Marketo Engage Cookie Sync is nu beschikbaar voor Marketo Measure Ultimate. Deze functie gebruiken:

1. Bewerk op de pagina AEP-schema&#39;s het B2B-personeschema en voeg de veldgroep &quot;Marketo Engage Person Details&quot; toe.
1. Wanneer het opnemen van de gegevens aan MMU, kaart het gebied van identiteitskaart van de Koek van de gebiedsgroep aan het gebied van Koekjes van Marketo Engage.

**Boomerang-fasen ingeschakeld voor Tier 2-klanten**

Voorheen alleen beschikbaar voor klanten van Tier 3, is de functie van het werkgebied van Boomerang ook beschikbaar voor alle klanten van Tier 2 die op 13 juni 2024 aanvangen. Raadpleeg de onderstaande documentatie voor meer informatie over deze functie.

* [Boomerang Stages en Touchpoints](/help/advanced-marketo-measure-features/boomerang/boomerang-stages-and-touchpoints.md){target="_blank"}
* [Boomerang Stages instellen](/help/advanced-marketo-measure-features/boomerang/setting-up-boomerang-stages.md){target="_blank"}
* [Boomerang Stage Scenarios](/help/advanced-marketo-measure-features/boomerang/boomerang-stage-scenarios.md){target="_blank"}

<p>

## V2-release {#q2-release}

<p>

**Veroudering van Marketo Measure-functies in reactie op Cookie-uitfasering van derden**

In reactie op de groeiende bezorgdheid over privacy worden cookies van derden geleidelijk afgeschaft, waarbij de deadline van Google Chrome van Q3 2024 het einde aangeeft. Marketo Measure zal bepaalde functies vervangen die afhankelijk zijn van cookies van derden, met name Cross-Domain Tracking en View-through Attribution, die afhankelijk zijn van het Google/DoubleClick-imitatiecookie. Deze wijziging heeft geen invloed op andere Marketo Measure-functies of het gebruik van cookies van andere leveranciers. Na de tijdlijn van Google zullen deze functies naar verwachting op 1 juni verouderd zijn, hoewel de gegevens die vóór deze datum verzameld zijn nog steeds toegankelijk zijn voor klanten.

* [Aanpassing aan Cookie Deprecation van derden in Marketo Measure](https://nation.marketo.com/t5/employee-blogs/adapting-to-third-party-cookie-deprecation-in-marketo-measure/ba-p/345110){target="_blank"}
* [Marketo Measure Cookies](/help/marketo-measure-tracking/setting-up-tracking/marketo-measure-cookies.md){target="_blank"}

**Gestroomlijnde implementatie van onze verbeterde foutafhandeling**

We introduceren een gefaseerde implementatie van verbeterde foutafhandeling voor exporttaken, te beginnen met directe pulsmeldingen in de app voor machtigingsfouten, en een overgang naar een nieuwe aanpak waarbij exporttaken worden gepauzeerd op het punt van de fout. Deze wijziging heeft tot doel de integriteit en de zichtbaarheid van gegevens te verbeteren, zodat onze gebruikers gemakkelijker en betrouwbaarder gegevensbeheerprocessen krijgen. Om een vlotte overgang en minimale verstoring van uw verrichtingen te verzekeren, voeren wij deze veranderingen in twee fasen uit:

* Directe beschikbaarheid van pulsmeldingen: u ontvangt pulsmeldingen in de app voor machtigingsfouten tijdens exporttaken. Hierdoor wordt uw export niet onderbroken, maar kunt u meer leren over de fouten zonder dat dit van invloed is op uw huidige taken.
* Tenuitvoerlegging van de taakpauze op 25 april: **POSTPONED** - Na de feedback van Marketo Measure-gebruikers te hebben overwogen, hebben we besloten de tenuitvoerlegging van het pauzeren van exporttaken uit te stellen op het punt van de fout, dat oorspronkelijk gepland was voor 25 april. We erkennen dat het stopzetten van banen wellicht niet de meest effectieve aanpak is. Wij streven naar een betere oplossing die gegevensintegriteit handhaaft en verstoring minimaliseert. We zullen elke wijziging in ons huidige systeem uitstellen totdat we een oplossing kunnen vinden die beter aansluit bij de behoeften van onze gebruikers.

_Waarom dit belangrijk is_

Verbeterde gegevensintegriteit en toekomstbestendigheid van uw integratie: we stoppen de taak bij het eerste teken van problemen om gegevensverlies te voorkomen en nauwkeurigheid te garanderen. Hierdoor kunt u problemen snel oplossen, waardoor de kwaliteit van de gegevensexport en de betrouwbaarheid van het systeem worden verbeterd.

Onmiddellijke zichtbaarheid: de introductie van pulsmeldingen maakt een snelle reactie op machtigingsfouten mogelijk, zodat mogelijke effecten op de activiteiten worden voorkomen.

_Uw overgang ondersteunen_

Om u aan deze verandering te helpen aanpassen, [we hebben documentatie gemaakt](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"} met duidelijke foutbeschrijvingen en uitgebreide stappen voor probleemoplossing.

<br>

**Actie vereist voor LinkedIn-integratie**

LinkedIn heeft onlangs een bijgewerkte versie uitgebracht van de bijbehorende API voor Lead Sync. Verifieer de LinkedIn-verbinding uiterlijk op 20 mei in uw Marketo Measure-exemplaar om onderbrekingen te voorkomen.

