---
description: '''[!DNL Marketo Measure] Ultieme overzicht - [!DNL Marketo Measure] - Productdocumentatie"'
title: '[!DNL Marketo Measure] Ultimate Overview'
hide: true
hidefromtoc: true
exl-id: fada9479-0671-4698-8043-c67d7977577b
source-git-commit: 604db0227cc48e09743db317cc72488755586a48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# [!DNL Marketo Measure] Ultieme overzicht {#marketo-measure-ultimate-overview}

[!DNL Marketo Measure] (voorheen Bizible) geeft marketeers inzicht in welke marketinginspanningen het meest effectief zijn in het aansturen van inkomsten en het maximaliseren van het rendement van investeringen voor hun bedrijf. [!DNL Marketo Measure] is een marketingtoewijzingsoplossing die de kanaalprestaties automatisch bijhoudt en rapporteert, zodat u kunt zien in welke kanalen de meeste betrokkenheid van klanten wordt bevorderd en uw marketinguitgaven dienovereenkomstig kunt optimaliseren.

[!DNL Marketo Measure Ultimate] bevat de extra mogelijkheden:

* Maak gebruik van vrijwel elke gegevensbron en van meerdere gegevensbronnen van hetzelfde type om al uw gegevens voor attributie in te voeren.
   * Gebruik met bijna om het even welke CRM, niet alleen Salesforce en Dynamica.
   * Meerdere CRM-instanties en/of MAP-instanties verbinden met één [!DNL Marketo Measure] -instantie.
   * Gegevens over webinaire registratie en deelname van derden beschikbaar maken.

* Transformeer uw gegevens op zeer flexibele wijze met behulp van de veldomzetting en transformatiemogelijkheden voor de juiste gegevensvorm.

* Maak attributieinzichten beschikbaar aan externe toepassingen door het inbegrepen gegevenspakhuis om de inzichten in uw werkschema te integreren. Meer gedetailleerde resultaatgegevens en op BI-Gebaseerde rapportering, met inbegrip van de Data Warehouse van Snowflake, die toegang tot korrelresultaatgegevens en de capaciteit verleent om het even welk hulpmiddel van BI voor analyse en rapportering te gebruiken.

* Integratie met RTCDP (B2B of B2P Edition), die een geïntegreerde B2B-attributieoplossing biedt voor RTCDP-klanten als RTCDP en [!DNL Marketo Measure] beide werken van gecentraliseerde gegevens van Adobe Experience Platform (AEP).

**Marketo Measure Tiers 1-3**

![](assets/marketo-measure-ultimate-overview-1.png)

**Marketo Measure Ultimate**

![](assets/marketo-measure-ultimate-overview-2.png)

## Nieuwe functies in [!DNL Marketo Measure Ultimate] {#whats-new-in-marketo-measure-ultimate}

**KOPTEKSTTITEL - B2B-gegevens importeren via AEP**

Van markeerders wordt verwacht dat zij hun B2B-gegevens (bijv. account, opportuniteit, contactpersoon, lead, campagne, campagnelid, activiteit) via AEP doorgeven. De directe verbindingen CRM en Marketo Engage zijn niet meer beschikbaar voor Ultimate. De verkopers zullen gegevens van het Platform van de Advertentie door directe verbindingen en het volgen van Webactiviteiten door blijven brengen [!DNL Marketo Measure] javascript.

![](assets/marketo-measure-ultimate-overview-3.png)

**KOPTEKSTTITEL - Standaardinstelling valuta**

BRIEF INTRO???

![](assets/marketo-measure-ultimate-overview-4.png)

**HEADER TITLE - Marketo Measure Ultimate Sandbox**

[!DNL Marketo Measure Ultimate] instantie moet worden toegewezen aan een AEP-sandbox voordat de instantie wordt gemaakt [!DNL Marketo Measure] bestemmingsgegevensstromen in AEP.

>[!NOTE]
>
>A [!DNL Marketo Measure Ultimate] productie-instantie moet worden toegewezen aan een AEP-productiesandbox, een [!DNL Marketo Measure Ultimate] -ontwikkelaarsinstantie moet worden toegewezen aan een AEP-ontwikkelaarssandbox.

Als de selectie van de sandboxtoewijzing is opgeslagen, kunt u deze momenteel niet meer wijzigen in de toepassing. Als je het wilt wijzigen, kun je contact opnemen met [Marketo-ondersteuning](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

Gegevens voor een bepaalde entiteit (bv. Account) uit een bepaalde gegevensbron kunnen slechts in één gegevensset worden opgenomen. Elke dataset kan slechts in één gegevensstroom worden omvat. Overtredingen zullen de gegevensstroom tijdens runtime stoppen.

![](assets/marketo-measure-ultimate-overview-5.png)

**KOPTEKSTTITEL - Werkgebiedtoewijzing**

Alles [!DNL Marketo Measure Ultimate] de regels zijn datasetspecifiek. Er moeten regels voor werkgebiedtoewijzing worden gemaakt voor alle gegevenssets en alle geselecteerde fasen.

Er zijn zes ingebouwde stappen:

* Loodverlies
* Openen van lead
* Lood omgezet
* Opportunity verloren
* Opportunity open
* Opportunity Won

De secties Verlies, Won en Omgezet staan geen aangepaste stadia toe. Brongegevens kunnen echter worden toegewezen aan de ingebouwde stappen Verlies/Won/Omgezet door de toewijzingsregel bij te werken.

Aangepaste stadia kunnen alleen worden gedefinieerd voor Open secties.
CRM-fasen worden niet meer automatisch in de werkgebiedtoewijzing opgenomen.

Vier ingebouwde stappen moeten met regels worden in kaart gebracht (toewijzingsregels voor de andere twee, Lead Lost en Lead Converted, zijn facultatief):

* Openen van lead
* Opportunity verloren
* Opportunity open
* Opportunity Won

De voorwaarden van de regel zijn datasetspecifiek. Er moeten regels voor werkgebiedtoewijzing worden gemaakt voor alle gegevenssets en alle stadia, behalve Lead Lost en Lead Converted.

Geen selectie voor trechter versus boemerang versus aangepast model. Alle stadia worden geselecteerd voor trechter, boemerang, en douanemodel. Er is een limiet voor het aantal fases dat we ondersteunen: 15 aangepaste plus 6 ingebouwde stappen.

![](assets/marketo-measure-ultimate-overview-6.png)

De de aanraakpuntregels van het Lid van de campagne en van het aanraakpunt van de Activiteit zijn datasetspecifiek.

![](assets/marketo-measure-ultimate-overview-7.png)

![](assets/marketo-measure-ultimate-overview-8.png)

Attribution Touchpoints worden niet naar CRM geschreven omdat Ultimate geen directe CRM-verbinding heeft.

[!DNL Marketo Measure] ABM ML-services (Lood-to-Account Matching en Predictive Engagement Score) zijn niet beschikbaar voor [!DNL Marketo Measure Ultimate]. Dergelijke services worden gratis geleverd in de RT-CDP B2B-editie.

## Beperkingen {#limitations}

* Er zijn momenteel beperkte velden beschikbaar voor de regels voor gegevenstransformatie.
* Er is geen migratiepad voor bestaande gebruikers van niveau 1/2/3. Vereist een nieuwe implementatie, maar we helpen de bijgehouden webactiviteitsgegevens te migreren van het bestaande exemplaar.

>[!MORELIKETHIS]
>
>[Doelverbinding](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/set-up-marketo-connection.md){target="_blank"}
