---
unique-page-id: 42762749
description: '[!DNL Marketo Engage] Integratie van activiteiten -  [!DNL Marketo Measure]'
title: '[!DNL Marketo Engage] Integratie van activiteiten'
exl-id: 463ad9b2-e1bd-49dd-8bf5-0da7b7132f05
feature: Integration
source-git-commit: de366de2d1df3d4dc9fc33e5fd0dab225b6af081
workflow-type: tm+mt
source-wordcount: '1640'
ht-degree: 0%

---

# [!DNL Marketo Engage] Integratie van activiteiten {#marketo-engage-activities-integration}

Als onderdeel van de algemene [!DNL Marketo Measure] - en [!DNL Marketo Engage] -integratie speelt deze poging om Marketo-activiteiten te ontplooien een enorme rol. Via Marketo Activiteiten houdt het systeem gebeurtenissen zoals `Click Email` , `Change Score` of `Change Status in Progression` bij - deze typen activiteit kunnen worden geparseerd en gedefinieerd om een subset te selecteren die in aanmerking komt voor aanraakpunten. Zodra de aanraakpunten op deze activiteiten worden gecreeerd, worden zij gevolgd in de betrokkenheidsreis en samen met uw andere marketing kanalen zoals Betaald Onderzoek of de Marketing van de Partner gemeten.

## Vereisten {#requirements}

* Production Marketo-instantie
* Production [!DNL Salesforce] of [!DNL Microsoft Dynamics] -instantie
* Alle betaalde [!DNL Marketo Measure] -abonnementen
* Marketo People Sync Enabled ([!DNL Marketo Measure] Instellingen)
* Marketo-programma&#39;s ingeschakeld ([!DNL Marketo Measure] Instellingen)
* Marketo-activiteiten ingeschakeld ([!DNL Marketo Measure] instellingen)

## Instellen {#setup}

1. Beginnen met vestiging de Activiteiten van Marketo, navigeer aan **Mijn Rekening** > **Montages** > **Activiteiten**.

   ![](assets/one-1.png)

   ![](assets/two-1.png)

   Het eerste vereiste ding is de lijst van de Types van Activiteit te selecteren die u van plan bent om regels op te bouwen. Er is geen hard aantal vereiste activiteitstypen, maar u wordt aangeraden uw aanraakpunten niet te veel te laden en het belang van belangrijke mijlpalen af te zwakken. Met dat gezegd, hebt u misschien niet meer dan vijf soorten activiteit nodig om de relevante overeenkomsten te volgen.

1. Klik op het vervolgkeuzemenu onder [!UICONTROL Select Activities Types] om de verschillende typen te kiezen.

   ![](assets/three-1.png)

1. Wanneer alle activiteiten die u nodig hebt, zijn geselecteerd, worden deze in de [!UICONTROL Selected Activities List] en onder [!UICONTROL Define Rules] gevuld.

   ![](assets/four-1.png)

1. Voor elk Type van Activiteit, moet u één of meerdere regels bepalen die welke verslagen verkiesbaar voor aanraakpunten zijn. In dit voorbeeld voegen we een regel toe voor het activiteitstype &#39;Score wijzigen&#39;, zodat het systeem een aanraakpunt maakt wanneer een Marketo-persoon een score van 90 of hoger haalt.

1. Ten eerste moet u, afhankelijk van het type activiteit, mogelijk een [!DNL Marketo Measure] campagnenaam instellen die later kan worden gebruikt voor kanaaltoewijzing. [!DNL Marketo Measure] Campagnenamen kunnen op meerdere regels opnieuw worden gebruikt. Dit helpt bredere namen hebben die in één enkele kanaalregel kunnen worden gebruikt. Niet alle soorten activiteiten bevatten een Marketo-programma, vandaar de behoefte aan een naam als deze eerste stap.

   Hier is een voorbeeld van hoe die extra stap eruit zou zien:

   ![](assets/five-1.png)

1. In het voorbeeld van de &quot;Score van de Verandering&quot;, is er behoefte om een Naam van de Campagne in te gaan aangezien die informatie uit het Programma van Marketo wordt getrokken. Maak nu de regelexpressie. Na dit voorbeeld, selecteer het gebied &quot;[!UICONTROL New Value]&quot;met een exploitant van &quot;[!UICONTROL is greater than]&quot;met een waarde van 90.

   U kunt de regels uitvouwen en aanvullende filters of criteria toevoegen door instructies &#39;en&#39; of &#39;of&#39; toe te voegen om de resultaten te beperken.

   ![](assets/six-1.png)

   ![](assets/seven-1.png)

1. Kies ten slotte de datum waarop u het aanraakpunt wilt gebruiken. Alle beschikbare datum- of datum-/tijdvelden worden hier weergegeven vanuit Marketo. Tenzij u de gebieden van de douanedatum hebt, ziet u &quot;[!UICONTROL Activity Date]&quot;.

   ![](assets/eight-1.png)

1. Zorg ervoor dat u onderweg op **[!UICONTROL Save As Draft]** klikt, zodat de wijzigingen niet verloren gaan.

   ![](assets/nine-1.png)

1. Ga naar het tabblad **[!UICONTROL Attribute Mapping]**.

   ![](assets/ten-1.png)

1. Voor elk type activiteit dat u hebt geselecteerd, kunt u extra Marketo-kenmerken toewijzen aan aanraakpuntvelden zodat u deze waarden kunt weergeven en rapporteren in [!DNL Marketo Measure Discover] of in de CRM.

   Veel van de velden zijn automatisch toegewezen en kunnen niet worden gewijzigd om consistent te zijn met onze andere integraties. Verwijs naar de sectie van de Toewijzingen van het Gebied hieronder om die waarden te vinden. Voor bepaalde typen activiteiten bevat Marketo kenmerken voor een openingspagina of een verwijzingspagina, of een browser die u optioneel kunt toewijzen aan een aanraakpuntveld. In het onderstaande voorbeeld hebben we enkele aanvullende suggesties gedaan die kunnen worden verwijderd.

1. Selecteer het Buyer Touchpoint-veld in de linkerkolom waarnaar u wilt toewijzen. Kies vervolgens het Marketo-kenmerk dat u wilt vullen in het Buyer Touchpoint-veld. Deze zijn optioneel, extra toewijzingen bovenop de toewijzingen die [!DNL Marketo Measure] al heeft gemaakt.

   Toewijzbare velden:

   * Stad
   * Land
   * Regio
   * Openingspagina
   * Referentiepagina
   * Formulierpagina
   * Formulierdatum
   * Platform
   * Browser

   >[!NOTE]
   >
   >Velden zoals Advertentie-inhoud of Trefwoord zijn niet beschikbaar in deze lijst, omdat ze zijn gereserveerd voor de integratie van ons advertentieplatform.

## Activiteitstypen {#activity-types}

Sommige activiteitentypes verstrekken ons van identiteitskaart van het Programma en de Naam van het Programma, zodat is het gemakkelijk om dat in de Campagne ID en de Naam van de Campagne op Buyer Touchpoint in kaart te brengen. Voor anderen is er geen programmakoppeling, dus voor een deel van de regeldefinitie moet u een [!DNL Marketo Measure] campagnenaam maken. Hieronder staan lijsten van elke categorie:

**Types van Activiteit met Programma Id**

E-mail verzenden (6)\
E-mail bezorgd (7)\
E-mail teruggestuurd (8)\
Abonnement op e-mail opzeggen (9)\
E-mail openen (10)\
Klik op E-mail (11)\
Gegevenswaarde wijzigen (13)\
Score wijzigen (22)\
Toevoegen aan lijst (24)\
Status wijzigen in Progressie (104)\
Toevoegen aan cultuur (113)\
Nurtuurkadentie wijzigen (115)

>[!NOTE]
>
>Van de activiteitstypen waar we een programma-id verwachten, accepteert [!DNL Marketo Measure] dit niet als een geschikt aanraakpunt, omdat we geen null-campagnewaarden kunnen hebben als een activiteit zonder een programma wordt gedetecteerd.

**Types van Activiteit zonder Programma Id**

Klik op Koppeling (3)\
Nieuwe lead (12)\
Lead synchroniseren naar SFDC (19)\
Lood omzetten (21)\
Eigenaar wijzigen (23)\
Verwijderen uit lijst (25)\
SFDC-activiteit (26)\
Door e-mail afgestoten zacht (27)\
Lood uit SFDC verwijderen (29)\
Leads samenvoegen (32)\
Toevoegen aan opportunity (34)\
Verwijderen uit opportunity (35)\
Opportunity bijwerken (36)\
Lood verwijderen (37)\
Waarschuwing verzenden (38)\
Verkoop-e-mail verzenden (39)\
Verkoopbericht openen (40)\
Klik op E-mailadres voor verkoop (41)\
Toevoegen aan SFDC-campagne (42)\
Verwijderen uit SFDC-campagne (43)\
Status wijzigen in SFDC-campagne (44)\
E-mailadres voor verkoop ontvangen (45)\
Campagne aanvragen (47)\
Verkoop-e-mail teruggestuurd (48)\
Opbrengstfase wijzigen (101)\
Werkgebied voor inkomsten handmatig wijzigen (102)\
Segment wijzigen (108)\
Webhaak bellen (110)\
Doorsturen naar e-mail vriend(in) (111)\
Doorgestuurd naar e-mail vriend (112)\
Cursustrack wijzigen (114)\
Uitloop naar Marketo (145)\
Lead synchroniseren naar Microsoft (300)\
Inhoud delen (400)
Dialoogvenster ingeschakeld (158)
Document heeft interactie met (159)
Dialoogbenoeming gepland (160)
Dialoogdoel bereikt (161)
Aangepaste activiteit (xxx)

## Kanaaltoewijzing {#channel-mapping}

Voor om het even welke regels van een Type van Activiteit met een Identiteitskaart van het Programma, wordt het Kanaal van het Programma van Marketo bepaald van het Programma. Wij gebruiken het Kanaal van het Programma om aan uw douane Offline Kanalen in kaart te brengen, zodat moet u ervoor zorgen uw kanalen behoorlijk [ zoals hier geïnstrueerd ](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md#channel-mapping){target="_blank"} worden gevormd.

En voor om het even welke regels van een Type van Activiteit zonder Programma Id, was uw eerste stap een Naam van de Campagne te creëren. Gebruik deze Naam van de Campagne aan opstelling uw douane Online Kanalen [ hier opgemaakt ](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md){target="_blank"}.

Als de Kanalen voor uw Activiteiten van Marketo niet behoorlijk worden gevormd, is het waarschijnlijk uw nieuwe aanraakpunten onder het &quot;Andere&quot;kanaal vallen.

## Programmakosten {#program-costs}

Via de invoer van gegevens van Marketo-programma&#39;s worden de kosten automatisch gedownload van de kosten van de periode en worden de gerapporteerde kosten in Marketo over de toegewezen maand verdeeld. Als bijvoorbeeld $1000 wordt gerapporteerd voor januari 2021, wordt $1000 gesplitst over 31 dagen. De kosten vindt u in [!DNL Marketo Measure Discover] .

## Cookie-toewijzing {#cookie-mapping}

Dankzij de [!DNL Marketo Measure] -integratie met Marketo wordt de [!DNL Marketo Measure] cookie-id nu ook toegewezen en gesynchroniseerd met de [!DNL Marketo Munchkin Id] . Zo kunt u de tussenruimte dichten en de anonieme eerste aanraking toewijzen aan een websessie in plaats van zowel de FT- als de LC-aanraking toe te wijzen aan een Marketo-activiteit. Stel je dit scenario voor:

Mark klikt op een Facebook-advertentie en landt op wayneenterprises.com waar hij een cookie krijgt met [!DNL Marketo Measure] Id 123 en [!DNL Marketo Munchkin Id] 456. Er vindt geen formuliervulling plaats.

Het Wayne Enterprises Marketing-team stuurt een e-mailexplosie naar specifieke beoogde leads, waaronder `mark@email.com` .

`mark@email.com` ontvangt het e-mailbericht en klikt erop en landt op `wayneenterprises.com` . Dit wordt een `mark@email.com's` tweede bezoek aan `wayneenterprise.com` met dezelfde cookie-id, maar er is geen formuliervulling. In [!DNL Marketo Measure] zijn ze dus nog steeds een anonieme bezoeker.

Het Wayne Enterprises Marketing-team maakt een Marketo Activity-regel om aanraakpunten te genereren voor een activity type &quot;Click Email&quot;.

De implementatie van vandaag zou één enkel aanraakpunt van FT en van LC voor `mark@email.com` van de Activiteit van Marketo van het &quot;Klik E-mail&quot;activiteitstype tot stand brengen.

Met deze functie voor het toewijzen van cookies zou FT teruggaan en worden gecrediteerd aan de Facebook-advertentie en zou de LC worden gecrediteerd aan de e-mail.

>[!NOTE]
>
>Met het gedrag van de koekjesafbeelding, kunt u sommige aanraakpunten vinden LC die van een Webbezoek komen. Het is mogelijk dat een lead in Marketo verschijnt zonder bijbehorende activiteit, en dat [!DNL Marketo Measure] die lead heeft gedownload, de bijbehorende cookies heeft gevonden en deze vervolgens naar de meest recente websessie heeft getraceerd, zelfs als er geen formulieractiviteit was die de lead heeft gemaakt.

## Veelgestelde vragen {#faq}

**Hoe weet ik of om een regel van de Programma&#39;s van Marketo of een regel van de Activiteiten van Marketo te creëren?**

De integratie van programma&#39;s [!DNL Marketo Engage] is een eenvoudige manier om aanraakpunten te genereren op basis van het feit of een persoon lid is van een programma. Als u in het bepalen van een regel geinteresseerd bent die op de tijd wordt gebaseerd een Persoon in een bepaalde status van het Programma verandert, zal de [!DNL Marketo Engage] Integratie van Activiteiten de opstelling zijn u wilt, specifiek het &quot;Status van de Verandering in Voortgang&quot;activiteitstype zodat uw Datum van het Aanraakpunt aan de systeem-geproduceerde Datum van de Activiteit kan worden in kaart gebracht.

**waarom is de naam van mijn Type Aanraakpunt afgekapt?**

Het veld Type aanraakpunt is gemaakt in het pakket [!DNL Marketo Measure] met 16 tekens. Helaas moet bij het wijzigen van de tekenlimiet van het veld het bestaande veld worden vervangen en moet er een worden gemaakt. De waarde van Type aanraakpunt is het Type activiteit, dat ook wordt ingesteld in het veld Medium.

**waarom mijn Type van Activiteit van de Douane niet in de lijst van beschikbare activiteiten verschijnt?**

We tonen alleen &#39;Goedgekeurde&#39; aangepaste activiteitstypen en niet Concept of Goedgekeurd met concept.

**hoe ik bepaal welke Types van Activiteit ik een touchpoint voor wil produceren?**

Hoewel er geen grens op het aantal Types van Activiteit is kunt u tot stand brengen, adviseren wij over het algemeen niet meer dan vijf activiteitstypes. Het kost tijd om te bepalen welke marketingactiviteiten relevant genoeg zijn om deel uit te maken van de toeristenreis. U kunt bijvoorbeeld &quot;E-mail afmelden&quot; gebruiken als belangrijk aanraakpunt voor bijhouden, maar &quot;Klik op e-mail&quot; met extra filters is wellicht een goed aanraakpunt. Dit varieert per organisatie en elk team, zodat stellen wij u voor om met uw team te werken aan brainstorm op de beste benadering hier.

**waarom is mijn Browser Naam weg?**

De naam van de browser van [!DNL Marketo Measure] heeft een vaste limiet van 20 tekens, hoewel de waarde van de gebruikersagent die we van Marketo krijgen, meestal een langere tekenreeks is.

BrowserInfo.Name\
BrowserInfo.Version\
PlatformInfo.Name\
PlatformInfo.Version
