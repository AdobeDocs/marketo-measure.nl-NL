---
description: Opmerkingen bij de huidige release - [!DNL Marketo Measure]
title: Opmerkingen bij de huidige release
exl-id: e93ff03e-ea21-41f4-abb8-32313ee74c0c
feature: Release Notes
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '1376'
ht-degree: 0%

---


# Opmerkingen bij de release: 2024 {#release-notes-2024}

Zie hieronder voor alle nieuwe en bijgewerkte functies voor onze 2024-releases.

## Versie Q4 {#q4-release}

### Nieuw gedrag Kanaaloverdracht sessie

Het kanaal van de vorige sessie wordt nu overgedragen als een nieuwe sessie binnen zeven dagen na 30 minuten inactiviteit begint, en alleen van toepassing is op directe bezoeken (geen referentie of interne referentie). Na zeven dagen van inactiviteit, zal de zitting aan Direct/andere in gebreke blijven. Niet-directe kanalen worden niet overschreven door vorige sessiegegevens.

Bovendien worden sessies die gebruikmaken van aanmelden via een sociaal netwerk (Google, Microsoft of Apple) nu samengevoegd in één doorlopende sessie, zodat u een vloeiender ervaring hebt. Zonder deze overdrachtstoets kunnen sociale inloggen afzonderlijke sessies maken vanwege verschillen tussen externe referenties.

Voor nieuwe klanten, is de overdracht van het zittingskanaal nu het standaardgedrag. Bestaande klanten kunnen dit inschakelen door de optie Sessiekanaaloverdracht in te schakelen onder Instellingen > Aanraakkenmerk. Deze instelling kan niet ongedaan worden gemaakt nadat deze is geactiveerd.

Documentatie: [&#x200B; Definitie van de Zittingen van het Web van Marketo Measure &#x200B;](https://experienceleague.adobe.com/en/docs/marketo-measure/using/marketo-measure-tracking/setting-up-tracking/definition-of-marketo-measure-web-sessions){target="_blank"}

### Trefwoord ROI-dashboard

Het nieuwe ROI Dashboard van het Sleutelwoord biedt gedetailleerde inzichten in de prestaties van Paid onderzoekscampagnes, die een uitvoerig overzicht van sleutelwoordvlakke kosten, toegeschreven opbrengst, en de geproduceerde kansen verstrekken. Met dit dashboard kunt u de ROI van elk trefwoord evalueren in Google Adwords, LinkedIn, Bing Ads, enzovoort.

Documentatie: [&#x200B; het Dashboard van ROI van het Sleutelwoord &#x200B;](https://experienceleague.adobe.com/en/docs/marketo-measure/using/marketo-measure-discover-ui/dashboards/keyword-roi-dashboard){target="_blank"}

### Verbeterde segmentregels

U kunt nu segmenten maken met de velden Campagne en Campagne-lid, in aanvulling op de velden Aanraakpunt en Contactpersoon. Op deze manier kunt u uw gegevens effectiever analyseren en ontleden in Discover.

![&#x200B; Verbeterde Regels van het Segment &#x200B;](assets/mm-q4-release-1.png)

### Update: instelling voor foutafhandeling voor CRM-export

We hebben geluisterd naar uw feedback over de aanpak voor het stoppen van taken en introduceren een nieuwe functie in de gebruikersinterface. Vanaf vandaag kunt u kiezen of exporttaken moeten worden gepauzeerd wanneer er fouten optreden. Gebruik de nieuwe knevel in **Mijn Rekening** > **Montages** > **CRM** > **Algemeen**. Deze schakelaar is door gebrek om gegevensintegriteit en zicht te verbeteren. Als u deze functie echter liever niet gebruikt, kunt u deze uitschakelen in de gebruikersinterface en worden de exporttaken hervat. Deze update is ontworpen om de betrouwbaarheid van uw gegevensbeheerprocessen te verbeteren en u meer controle te geven.

#### Sleuteldatums en gefaseerde uitrol

1. **Onmiddellijke Beschikbaarheid van de knevel:** de knevel is nu levend in UI en door gebrek wordt toegelaten om gegevens te verhinderen tijdens uitvoerbanen worden overgeslagen. Schakel de schakeloptie uit als u wilt dat exporttaken actief blijven ondanks fouten.

1. **Baan die Activering pauzeert op 1 Oktober:** Begin Oktober 1, 2024, als de knevel actief is en een verslag-vlakke fout tijdens een uitvoerbaan wordt ontmoet, pauzeert de baan om ervoor te zorgen geen gegevens wordt verloren. Deze fouten zijn gewoonlijk het gevolg van ontbrekende machtigingen, onjuist toegepaste aangepaste validatieregels of problemen in workflows/triggers. U ontvangt meldingen over het probleem en zodra dit is gecorrigeerd, wordt de exporttaak vanaf het punt van onderbreking hervat. Als u het pauzeren van taken uitschakelt, ontvangt u nog steeds meldingen over problemen en nadat deze zijn gecorrigeerd, worden de overgeslagen records automatisch opnieuw geëxporteerd.

#### Waarom dit belangrijk is

* **Verbeterde Integriteit van Gegevens en Toekomstige-proef Uw Integratie:** door de baan bij het eerste teken van een kwestie te pauzeren, verhinderen wij gegevensverlies en verzekeren nauwkeurigheid. Dit maakt een snelle foutopsporing mogelijk, wat resulteert in een verbeterde kwaliteit van de gegevensuitvoer en een hogere betrouwbaarheid van het systeem.

* **Onmiddellijke Zichtbaarheid:** door impulsberichten, zult u geschikte alarm voor toestemmingsfouten ontvangen, toestaand voor snelle reacties en minimaliserend potentiële gevolgen voor uw verrichtingen.

#### Uw overgang ondersteunen

Om u aan deze verandering te helpen aanpassen, hebben wij documentatie over de nieuwe eigenschap en duidelijke foutenbeschrijvingen met uitvoerige het oplossen van problemenstappen gecreeerd.

* Nieuwe documentatie: [&#x200B; de Behandeling van de Fout die voor CRM uitvoert &#x200B;](/help/configuration-and-setup/marketo-measure-and-salesforce/crm-error-handling.md)
* [Foutmeldingen](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md)

## Q3 Release {#q3-release}

### Herinnering: Salesforce Field Deprecations - 14 juni

Zoals vorig jaar aangekondigd, zullen wij [&#x200B; geleidelijk aan onze uitvoerbanen aan Lood/de voorwerpen van het Contact &#x200B;](https://nation.marketo.com/t5/employee-blogs/marketo-measure-salesforce-lead-and-contact-field-deprecation-06/ba-p/350179){target="_blank"} zijn om onze integratie te vereenvoudigen en de behoefte te elimineren om naar Salesforce standaardvoorwerpen uit te voeren. U kunt de zelfde gegevens uit uw voorwerpen verkrijgen Touchpoint door de stappen te volgen [&#x200B; hier wordt gedocumenteerd &#x200B;](/help/release-notes/previous-releases/2023.md#deprecations){target="_blank"}. We delen ook documentatie over het maken van workflows om deze gegevens toe te voegen aan het object Lead/Contact. De afschrijving wordt van kracht op 14 juni 2024.

Deze wijziging zal twee belangrijke voordelen opleveren:

* **Verminderde kosten van Salesforce API**: De klanten kunnen verwachten om hun kosten van Salesforce API met rond 10% te drukken.
* **Gestroomlijnde Integratie**: Het hoogste aantal fouten in onze uitvoerbanen zijn verwant aan deze processen. Als we ze verwijderen, wordt onze integratie aanzienlijk gestroomlijnd.

### Toegewezen opportuniteitsdashboard

Wij zijn opgetogen om het nieuwe [&#x200B; Attributed Dashboard van de Kans &#x200B;](/help/marketo-measure-discover-ui/attributed-opportunity-dashboard.md){target="_blank"} te introduceren, die wordt ontworpen om u een uitvoerige mening van te geven hoe uw marketing inspanningen aan zowel ontluikende als volwassen pijpleidingskansen bijdragen. Met dit dashboard kunt u de details bekijken van elke open en gesloten kans die aan uw strategieën is toe te schrijven, met de flexibiliteit om per opportuniteitsfase te filteren. Het biedt inzicht in welke kanalen, subkanalen, of campagnes het hoogst in termen van toegewezen opportuniteitsbedrag zijn, en toont het totale toegewezen opportuniteitsbedrag samen met het aantal toegewezen open en gesloten kansen.

### Marketo Engage Cookie Sync voor Marketo Measure Ultimate

Marketo Engage Cookie Sync is nu beschikbaar voor Marketo Measure Ultimate. Deze functie gebruiken:

1. Bewerk op de pagina AEP-schema&#39;s het B2B-personenschema en voeg de veldgroep &quot;Marketo Engage Person Details&quot; toe.
1. Wanneer het opnemen van de gegevens aan MMU, kaart het gebied van identiteitskaart van de Koek van de gebiedsgroep aan het gebied van Koekjes van Marketo Engage.

### Boomerang-fasen ingeschakeld voor Tier 2-klanten

Voorheen alleen beschikbaar voor klanten van Tier 3, is de functie van het werkgebied van Boomerang ook beschikbaar voor alle klanten van Tier 2 die op 13 juni 2024 aanvangen. Raadpleeg de onderstaande documentatie voor meer informatie over deze functie.

* [&#x200B; Boomerang Stages en Touchpoints &#x200B;](/help/advanced-features/boomerang/boomerang-stages-and-touchpoints.md){target="_blank"}
* [&#x200B; Vestiging Boomerang Stages &#x200B;](/help/advanced-features/boomerang/setting-up-boomerang-stages.md){target="_blank"}
* [&#x200B; Boomerang de Scenario&#39;s van het Stadium &#x200B;](/help/advanced-features/boomerang/boomerang-stage-scenarios.md){target="_blank"}

## V2-release {#q2-release}

### Veroudering van Marketo Measure-functies in reactie op Cookie-uitfasering van derden

In reactie op de toenemende bezorgdheid over privacy worden cookies van derden geleidelijk afgeschaft, waarbij de Google Chrome de deadline van het derde kwartaal van 2024 aangeeft. Marketo Measure zal bepaalde functies vervangen die afhankelijk zijn van cookies van derden, met name Cross-Domain Tracking en View-through Attribution, die afhankelijk zijn van het Google/DoubleClick-imitatiecookie. Deze wijziging heeft geen invloed op andere Marketo Measure-functies of het gebruik van cookies van andere leveranciers. Na de tijdlijn van Google zullen deze functies naar verwachting op 1 juni verouderd zijn, hoewel de gegevens die vóór deze datum verzameld zijn nog steeds toegankelijk zijn voor klanten.

* [&#x200B; het Aanpassen aan de Verdringing van de Koekjesindustrie van de Derde in Marketo Measure &#x200B;](https://nation.marketo.com/t5/employee-blogs/adapting-to-third-party-cookie-deprecation-in-marketo-measure/ba-p/345110){target="_blank"}
* [&#x200B; de Koekjes van Marketo Measure &#x200B;](/help/marketo-measure-tracking/marketo-measure-cookies.md){target="_blank"}

### Gestroomlijnde implementatie van onze verbeterde foutafhandeling

We introduceren een gefaseerde implementatie van verbeterde foutafhandeling voor exporttaken, te beginnen met directe pulsmeldingen in de app voor machtigingsfouten, en een overgang naar een nieuwe aanpak waarbij exporttaken worden gepauzeerd op het punt van de fout. Deze wijziging heeft tot doel de integriteit en de zichtbaarheid van gegevens te verbeteren, zodat onze gebruikers gemakkelijker en betrouwbaarder gegevensbeheerprocessen krijgen. Om een vlotte overgang en minimale verstoring van uw verrichtingen te verzekeren, voeren wij deze veranderingen in twee fasen uit:

* Directe beschikbaarheid van pulsmeldingen: u ontvangt pulsmeldingen in de app voor machtigingsfouten tijdens exporttaken. Hierdoor wordt uw export niet onderbroken, maar kunt u meer leren over de fouten zonder dat dit van invloed is op uw huidige taken.
* Implementatie van Pauzeren van de Baan op 25 April: **POSTPONED** - Na het overwegen van terugkoppelt van gebruikers van Marketo Measure, hebben wij besloten om de implementatie van het pauzeren van uitvoerbanen op het punt van fout uit te stellen, oorspronkelijk gepland voor 25 April. We erkennen dat het stopzetten van banen wellicht niet de meest effectieve aanpak is. Wij streven naar een betere oplossing die gegevensintegriteit handhaaft en verstoring minimaliseert. We zullen elke wijziging in ons huidige systeem uitstellen totdat we een oplossing kunnen vinden die beter aansluit bij de behoeften van onze gebruikers.

_waarom dit_ van belang is

Verbeterde gegevensintegriteit en toekomstbestendigheid van uw integratie: we stoppen de taak bij het eerste teken van problemen om gegevensverlies te voorkomen en nauwkeurigheid te garanderen. Hierdoor kunt u problemen snel oplossen, waardoor de kwaliteit van de gegevensexport en de betrouwbaarheid van het systeem worden verbeterd.

Onmiddellijke zichtbaarheid: de introductie van pulsmeldingen maakt een snelle reactie op machtigingsfouten mogelijk, zodat mogelijke effecten op de activiteiten worden voorkomen.

_ondersteunend Uw Overgang_

Om u aan deze verandering aan te passen, [&#x200B; hebben wij documentatie &#x200B;](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"} met duidelijke foutenbeschrijvingen en uitvoerige het oplossen van problemenstappen gecreeerd.

### Actie vereist voor Integratie LinkedIn

LinkedIn heeft onlangs een bijgewerkte versie van hun API voor het synchroniseren van leads uitgebracht. Please re-authenticate the LinkedIn connection in your Marketo Measure instance by May 20 to avoid any onderbrekingen.
