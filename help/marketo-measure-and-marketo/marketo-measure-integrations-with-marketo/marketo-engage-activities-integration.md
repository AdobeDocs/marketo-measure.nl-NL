---
unique-page-id: 42762749
description: "[!DNL Marketo Engage] Integratie van activiteiten - [!DNL Marketo Measure]"
title: "[!DNL Marketo Engage] Activiteitenintegratie"
exl-id: 463ad9b2-e1bd-49dd-8bf5-0da7b7132f05
feature: Integration
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '1671'
ht-degree: 0%

---

# [!DNL Marketo Engage] Activiteitenintegratie {#marketo-engage-activities-integration}

Als onderdeel van het algemene [!DNL Marketo Measure] en [!DNL Marketo Engage] Integratie, deze poging om de activiteiten van Marketo te stimuleren speelt een enorme rol. Via Marketo Activiteiten volgt het systeem gebeurtenissen zoals Click Email, Change Score of Change Status in Progression. Deze activiteitstypen kunnen worden geplakt en gedefinieerd om een subset te selecteren die in aanmerking komt voor aanraakpunten. Zodra de aanraakpunten op deze activiteiten worden gecreeerd, worden zij gevolgd in de betrokkenheidsreis en samen met uw andere marketing kanalen zoals Betaald Onderzoek of de Marketing van de Partner gemeten.

## Vereisten {#requirements}

* Production Marketo-instantie
* Productie [!DNL Salesforce] of [!DNL Microsoft Dynamics] instance
* Betaald [!DNL Marketo Measure] abonnement
* Marketo People Sync Enabled ([!DNL Marketo Measure] Instellingen)
* Marketo-programma&#39;s ingeschakeld ([!DNL Marketo Measure] Instellingen)
* Marketo-activiteiten ingeschakeld ([!DNL Marketo Measure] Instellingen)

## Instellen {#setup}

1. Ga naar om Marketo-activiteiten op te zetten **Mijn account** > **Instellingen** > **Activiteiten**.

   ![](assets/one-1.png)

   ![](assets/two-1.png)

   Het eerste vereiste ding is de lijst van de Types van Activiteit te selecteren die u van plan bent om regels op te bouwen. Er is geen hard aantal vereiste activiteitstypen, maar wij adviseren ook dat u uw touchpoints niet overlaadt en het belang van significante mijlpalen sleept. Met dat gezegd, hebt u misschien niet meer dan vijf soorten activiteit nodig om de relevante overeenkomsten te volgen.

1. Klik op de vervolgkeuzelijst onder [!UICONTROL Select Activities Types] om de verschillende typen te kiezen.

   ![](assets/three-1.png)

1. Als alle benodigde activiteiten zijn geselecteerd, worden deze ook in uw [!UICONTROL Selected Activities List] en onder [!UICONTROL Define Rules].

   ![](assets/four-1.png)

1. Voor elk Type van Activiteit, zult u één of meerdere regels moeten bepalen die welke verslagen verkiesbaar voor aanraakpunten zijn. Bij ons voorbeeld voegen we een regel toe voor het activiteitstype &#39;Score wijzigen&#39;, zodat het systeem een aanraakpunt maakt wanneer een Marketo-persoon een score van 90 of hoger haalt.

1. Eerst moet u, afhankelijk van het type activiteit, mogelijk een [!DNL Marketo Measure] Campagnenaam die later voor kanaalafbeelding kan worden gebruikt. [!DNL Marketo Measure] De Namen van de campagne kunnen over veelvoudige regels opnieuw worden gebruikt. Dit helpt bredere namen hebben die in één enkele kanaalregel kunnen worden gebruikt. Niet alle soorten activiteiten bevatten een Marketo-programma, vandaar de behoefte aan een naam als deze eerste stap.

   Hier is een voorbeeld van hoe die extra stap eruit zou zien:

   ![](assets/five-1.png)

1. In ons voorbeeld van de &quot;Score van de Verandering&quot;, te hoeven wij niet om een Naam van de Campagne in te gaan aangezien wij die informatie van het Programma van Marketo kunnen trekken. Nu kunt u de regelexpressie maken. Als u ons voorbeeld volgt, wilt u het veld &quot;[!UICONTROL New Value]&quot; met een operator van &quot;[!UICONTROL is greater than]&quot; met een waarde van 90.

   U kunt de regels uitvouwen en aanvullende filters of criteria toevoegen door instructies &#39;en&#39; of &#39;of&#39; toe te voegen om de resultaten te beperken.

   ![](assets/six-1.png)

   ![](assets/seven-1.png)

1. Tot slot kiest u wat we als aanraakpunt Datum moeten gebruiken. Alle beschikbare datum- of datum-/tijdvelden worden hier weergegeven vanuit Marketo. Tenzij u aangepaste datumvelden hebt, wordt &quot;[!UICONTROL Activity Date].&quot;

   ![](assets/eight-1.png)

1. Zorg ervoor dat u op **[!UICONTROL Save As Draft]** onderweg, zodat je je wijzigingen niet verliest.

   ![](assets/nine-1.png)

1. Ga naar het tabblad **[!UICONTROL Attribute Mapping]**.

   ![](assets/ten-1.png)

1. Voor elk type activiteit dat u hebt geselecteerd, kunt u extra Marketo-kenmerken toewijzen aan aanraakpuntvelden zodat u deze waarden kunt weergeven en melden in [!DNL Marketo Measure Discover] of in de CRM.

   Veel van de velden zijn automatisch toegewezen en kunnen niet worden gewijzigd om consistent te zijn met onze andere integraties. Verwijs naar de sectie van de Toewijzingen van het Gebied hieronder om die waarden te vinden. Voor bepaalde typen activiteiten bevat Marketo kenmerken voor een openingspagina of een verwijzingspagina, of een browser die u optioneel kunt toewijzen aan een aanraakpuntveld. In het onderstaande voorbeeld hebben we enkele aanvullende suggesties gedaan die kunnen worden verwijderd.

1. Selecteer het veld Aanraakpunt koper in de linkerkolom waarnaar u wilt toewijzen. Kies vervolgens het Marketo-kenmerk dat u wilt vullen in het veld Aanraakpunt koper. Vergeet niet dat dit optionele extra toewijzingen zijn boven op de toewijzingen die [!DNL Marketo Measure] heeft vastgesteld.

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

Sommige activiteitstypen voorzien ons van de Programma-id en de Naam van het Programma, zodat is het gemakkelijk om dat in de Campagne-id en de Naam van de Campagne op het Aanraakpunt van de Koper in kaart te brengen. Voor anderen, is er geen programmavereniging, zodat zal een deel van de regeldefinitie u vereisen om een [!DNL Marketo Measure] Naam campagne. Hieronder staan lijsten van elke categorie:

**Activiteitstypen met programma-id**

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
>Van de soorten activiteiten waar wij een programma-id verwachten, als een activiteit zonder een programma wordt ontdekt, [!DNL Marketo Measure] Dat is geen geschikt aanraakpunt, omdat we geen null Campagnewaarden kunnen hebben.

**Activiteitstypen zonder programma-id**

Klik op Koppeling (3)\
Nieuwe lead (12)\
Lood synchroniseren naar SFDC (19)\
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
Inhoud delen (400) Dialoogvenster ingesloten (158) Document heeft interactie gehad met (159) Dialoogaanduiding gepland (160) Dialoogoogvenster bereikt (161) Aangepaste activiteit (xxx)

## Kanaaltoewijzing {#channel-mapping}

Voor om het even welke regels van een Type van Activiteit met een Identiteitskaart van het Programma, wordt het Kanaal van het Programma van Marketo bepaald van het Programma. Wij gebruiken het Kanaal van het Programma om aan uw douane Offline Kanalen in kaart te brengen, zodat zult u uw kanalen moeten ervoor zorgen behoorlijk worden gevormd [zoals hier geïnstrueerd](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md#channel-mapping).

En voor om het even welke regels van een Type van Activiteit zonder Programma Id, was uw eerste stap een Naam van de Campagne te creëren. Met deze campagnenaam stelt u uw aangepaste onlinekanalen in [hier](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md).

Als de Kanalen voor uw Activiteiten van Marketo niet behoorlijk worden gevormd, is het waarschijnlijk uw nieuwe aanraakpunten onder het &quot;Andere&quot;kanaal zullen vallen.

## Programmakosten {#program-costs}

Via de gegevensimport van Marketo-programma&#39;s worden de kosten automatisch gedownload van de kosten van de periode en worden de gerapporteerde kosten in Marketo over de toegewezen maand verdeeld. Als bijvoorbeeld $1000 wordt gerapporteerd voor januari 2021, wordt $1000 gesplitst over 31 dagen. De kosten zijn te vinden in [!DNL Marketo Measure Discover].

## Cookie-toewijzing {#cookie-mapping}

Als gevolg van de [!DNL Marketo Measure] de integratie met Marketo [!DNL Marketo Measure] De cookie-id is nu ook toegewezen en gesynchroniseerd met de [!DNL Marketo Munchkin Id]. Zo kunt u de tussenruimte dichten en de anonieme eerste aanraking toewijzen aan een websessie in plaats van zowel de FT- als de LC-aanraking toe te wijzen aan een Marketo-activiteit. Stel je dit scenario voor:

Mark klikt op een Facebook advertentie en landt op wayneenterprises.com waar hij gekookt wordt [!DNL Marketo Measure] ID 123 en [!DNL Marketo Munchkin Id] 456. Er vindt geen formuliervulling plaats.

Het Wayne Enterprises Marketing-team stuurt een e-mailoverzicht naar specifieke beoogde leads, waarbij een van hen `mark@email.com`.

`mark@email.com` ontvangt het e-mailbericht en klikt en landt op `wayneenterprises.com`. Dit wordt `mark@email.com's` tweede bezoek aan `wayneenterprise.com` met dezelfde cookie-id, maar er was geen formuliervulling, dus om [!DNL Marketo Measure], zij zijn nog steeds een anonieme bezoeker.

Het Wayne Enterprises Marketing-team maakt een Marketo Activity-regel om aanraakpunten te genereren voor een activity type &quot;Click Email&quot;.

De implementatie van vandaag zou één enkel FT en LC aanraakpunt voor creëren `mark@email.com` van de Activiteit van Marketo van het type van &quot;klikE-mail&quot;activiteit.

Met deze functie voor het toewijzen van cookies zou FT teruggaan en worden gecrediteerd aan de Facebook-advertentie en zou de LC worden gecrediteerd aan de e-mail.

>[!NOTE]
>
>Met het gedrag van de koekjesafbeelding, kunt u sommige aanraakpunten vinden LC die van een Webbezoek komen. Het is mogelijk dat er een lead verscheen in Marketo zonder enige bijbehorende activiteit, dan [!DNL Marketo Measure] Deze lead is gedownload, er zijn overeenkomende cookies in opgenomen en vervolgens naar de meest recente websessie geleid, zelfs als de lead niet via een formulieractiviteit is gemaakt.

## Veelgestelde vragen {#faq}

**Hoe weet ik of ik een regel voor Marketo-programma&#39;s of een regel voor Marketo-activiteiten wil maken?**

De [!DNL Marketo Engage] De Integratie van programma&#39;s is een eenvoudige manier om aanraakpunten te produceren die op worden gebaseerd of een Persoon een programmalid van een programma is of niet. Als u in het bepalen van een regel geinteresseerd bent die op de tijd wordt gebaseerd een Persoon in een bepaalde status van het Programma verandert, [!DNL Marketo Engage] De Integratie van activiteiten zal de opstelling zijn u, specifiek het &quot;Status van de Verandering in Voortgang&quot;activiteitstype zodat uw Datum van het Aanraakpunt aan de systeem geproduceerde Datum van de Activiteit kan worden in kaart gebracht.

**Waarom wordt de naam van mijn Type Aanraakpunt ingekort?**

Het veld Type aanraakpunt is gemaakt in het dialoogvenster [!DNL Marketo Measure] pakket met 16 tekens. Helaas moet bij het wijzigen van de tekenlimiet van het veld het bestaande veld worden vervangen en een nieuw veld worden gemaakt. De waarde van Type aanraakpunt is het Type activiteit, dat ook wordt ingesteld in het veld Gemiddeld.

**Waarom verschijnt mijn Type van Activiteit van de Douane niet in de lijst van beschikbare activiteiten?**

We tonen alleen &#39;Goedgekeurde&#39; aangepaste activiteitstypen en niet Concept of Goedgekeurd met concept.

**Hoe bepaal ik welke Types van Activiteit ik een aanraakpunt voor wil produceren?**

Hoewel er geen grens op het aantal Types van Activiteit is kunt u tot stand brengen, adviseren wij over het algemeen niet meer dan 5 activiteitstypes. Het kost tijd om te bepalen welke marketingactiviteiten relevant genoeg zijn om deel uit te maken van de toeristenreis. U kunt bijvoorbeeld &quot;E-mail afmelden&quot; gebruiken als belangrijk aanraakpunt voor bijhouden, maar &quot;Klik op e-mail&quot; met extra filters is wellicht een goed aanraakpunt. Dit varieert per organisatie en elk team, zodat adviseren wij u met uw teams te werken om op de beste benadering hier te brainstormen.

**Waarom wordt mijn Browsernaam afgesloten?**

De [!DNL Marketo Measure] Browsernaam heeft een vaste limiet van 20 tekens, hoewel de waarde voor Gebruikersagent die we van Marketo krijgen, meestal een langere tekenreeks is.

BrowserInfo.Name\
BrowserInfo.Version\
PlatformInfo.Name\
PlatformInfo.Version
