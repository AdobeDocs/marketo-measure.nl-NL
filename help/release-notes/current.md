---
description: Opmerkingen bij de huidige release - [!DNL Marketo Measure]
title: Opmerkingen bij de huidige release
exl-id: e93ff03e-ea21-41f4-abb8-32313ee74c0c
feature: Release Notes
source-git-commit: 81ce4ead229e461eeb9e6e3b1e951108b627a4e8
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 0%

---

# Opmerkingen bij de release: 2024 {#release-notes-2024}

Zie hieronder voor alle nieuwe en bijgewerkte functies voor onze 2024-releases.

## V2-release {#q2-release}

<p>

**Veroudering van Marketo Measure-functies in reactie op Cookie-uitfasering van derden**

In reactie op de groeiende bezorgdheid over privacy worden cookies van derden geleidelijk afgeschaft, waarbij de deadline van Google Chrome van Q3 2024 het einde aangeeft. Marketo Measure zal bepaalde functies vervangen die afhankelijk zijn van cookies van derden, met name Cross-Domain Tracking en View-through Attribution, die afhankelijk zijn van het Google/DoubleClick-imitatiecookie. Deze wijziging heeft geen invloed op andere Marketo Measure-functies of het gebruik van cookies van andere leveranciers. Na de tijdlijn van Google zullen deze functies naar verwachting op 1 juni verouderd zijn, hoewel de gegevens die vóór deze datum verzameld zijn nog steeds toegankelijk zijn voor klanten.

* [Aanpassing aan Cookie Deprecation van derden in Marketo Measure](https://nation.marketo.com/t5/employee-blogs/adapting-to-third-party-cookie-deprecation-in-marketo-measure/ba-p/345110){target="_blank"}
* [Marketo Measure Cookies](/help/marketo-measure-tracking/setting-up-tracking/marketo-measure-cookies.md){target="_blank"}

**Gestroomlijnde implementatie van onze verbeterde foutafhandeling**

We introduceren een gefaseerde implementatie van verbeterde foutafhandeling voor exporttaken, te beginnen met directe pulsmeldingen in de app voor machtigingsfouten en op 25 april over te schakelen naar een nieuwe aanpak waarbij exporttaken worden gepauzeerd op het punt van de fout. Deze wijziging heeft tot doel de integriteit en de zichtbaarheid van gegevens te verbeteren, zodat onze gebruikers gemakkelijker en betrouwbaarder gegevensbeheerprocessen krijgen. Om een vlotte overgang en minimale verstoring van uw verrichtingen te verzekeren, voeren wij deze veranderingen in twee fasen uit:

* Directe beschikbaarheid van pulsmeldingen: u ontvangt pulsmeldingen in de app voor machtigingsfouten tijdens exporttaken. Hierdoor wordt uw export niet onderbroken, maar kunt u meer leren over de fouten zonder dat dit van invloed is op uw huidige taken.
* Implementatie van taakonderbreking op 25 april: vanaf 25 april wordt de taak gepauzeerd om ervoor te zorgen dat er geen gegevens worden overgeslagen als er in ons systeem een machtigingsfout optreedt tijdens een exporttaak. U wordt op de hoogte gesteld van eventuele problemen. Zodra de machtigingen zijn gecorrigeerd, wordt de exporttaak probleemloos hervat vanaf het punt waar deze was uitgeschakeld.

_Waarom dit belangrijk is_

Verbeterde gegevensintegriteit en toekomstbestendigheid van uw integratie: we stoppen de taak bij het eerste teken van problemen om gegevensverlies te voorkomen en nauwkeurigheid te garanderen. Hierdoor kunt u problemen snel oplossen, waardoor de kwaliteit van de gegevensexport en de betrouwbaarheid van het systeem worden verbeterd.

Onmiddellijke zichtbaarheid: de introductie van pulsmeldingen maakt een snelle reactie op machtigingsfouten mogelijk, zodat mogelijke effecten op de activiteiten worden voorkomen.

_Uw overgang ondersteunen_

Om u aan deze verandering te helpen aanpassen, [we hebben documentatie gemaakt](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"} met duidelijke foutbeschrijvingen en uitgebreide stappen voor probleemoplossing.

**Actie vereist voor LinkedIn-integratie**

LinkedIn heeft onlangs een bijgewerkte versie uitgebracht van de bijbehorende API voor Lead Sync. Verifieer de LinkedIn-verbinding uiterlijk op 20 mei in uw Marketo Measure-exemplaar om onderbrekingen te voorkomen.

