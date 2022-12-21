---
unique-page-id: 42762310
description: Historische gegevens synchroniseren - [!DNL Marketo Measure] - Productdocumentatie
title: Historische gegevens synchroniseren
exl-id: 5a3c1a71-463a-4d75-98b9-fc225839512a
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '1487'
ht-degree: 0%

---

# Historische gegevens synchroniseren {#syncing-historical-data}

[!DNL Marketo Measure] is een oplossing die de korrelige, actiefste gegevens verstrekt. We begrijpen echter dat er bestaande gegevens zijn waarvoor u een kenmerk wilt hebben. Het is mogelijk om aanraakpunten te genereren voor historische gegevens, maar het is belangrijk om rekening te houden met een paar factoren voordat u verder gaat met dit proces.

## Te overwegen factoren {#factors-to-consider}

**Zijn de gegevens al in campagnes georganiseerd?**

a. De gegevens moeten in campagnes worden georganiseerd om te worden gesynchroniseerd [!DNL Marketo Measure] om aanraakpunten te genereren. Als het momenteel niet in Campagnes wordt georganiseerd, zult u willen evalueren als het de tijd en de middelen waard is nodig om de gegevens in de aangewezen campagnes te segmenteren.

b. De datum waarop het lid aan de campagne is toegevoegd of als geantwoord is gemarkeerd, wordt gebruikt voor de aanraakpuntdatum. Dit moet dus ook correct zijn. [!DNL Marketo Measure] biedt zowel in SFDC als in MSD tijdelijke oplossingen aan om de datums bij te werken, maar dit kan afhankelijk van het volume tijdrovend zijn.

**Hebt u een vrij gelijke hoeveelheid gegevens georganiseerd in campagnes voor alle Kanalen (betaalde onderzoek, gebeurtenissen, organisch, enz.)?**

Het is belangrijk om een evenwichtig beeld van attributie te hebben om nauwkeurige en &quot;eerlijke&quot;rapportering te hebben. Als u bijvoorbeeld alleen gegevens hebt voor historische offlinekanaals-inspanningen, zoals Events, zullen de gegevens van nature bevooroordeeld zijn zonder historische online gegevens als aanvulling hierop.

**Welk niveau van granulariteit verwacht u?**

In feite kent u alleen de naam Kanaal, Subkanaal en Campagne.

**Wat zijn uw rapporteringsdoelstellingen in de toekomst?**

Deze gegevens zullen beperkt blijven, dus is het belangrijk om te overwegen hoe u het wilt gebruiken. Het is misschien niet het meest logisch om historische gegevens te vergelijken met toekomstige gegevens.

**Hoe ver wil je terug?**

[!DNL Marketo Measure] beveelt ten stelligste aan het voorgaande jaar niet te overschrijden .

Dit is een onderwerp dat wij ten zeerste aanmoedigen om met uw [!DNL Marketo Measure] contact eerst. Als u het bovenstaande in overweging hebt genomen en wilt doorgaan, voert u algemene instructies uit (apart voor [!DNL Salesforce] en [!DNL Microsoft Dynamics]) staan hieronder.

## Historische campagnes synchroniseren in [!DNL Salesforce] {#syncing-historic-campaigns-in-salesforce}

**Online:**

Als u historische online gegevens wilt synchroniseren, moeten de gegevens worden ingedeeld in Salesforce-campagnes waarmee u vervolgens wilt synchroniseren [!DNL Marketo Measure] via [!DNL Salesforce] De regels van de Synchronisatie van de campagne in [!DNL Marketo Measure] app. Het is belangrijk ervoor te zorgen dat er geen aanraakpunten worden gegenereerd vanuit deze campagnes nadat uw JavaScript-code live is gegaan. De reden hiervoor is dubbele aanraakpunten te voorkomen. Nadat JavaScript live is, worden online-inspanningen automatisch bijgehouden, dus we willen ze niet meer bijhouden via een SFDC-campagne. Om dit probleem te vermijden, zeker om een gevoel van tijd aan de regel toe te voegen. Misschien is iets als &#39;Campagne Member Created Date&#39; kleiner dan [JavaScript-datum voor go-live]&quot;.

![](assets/syncing-historical-data-1.png)

De component voor kanaaltoewijzing voor historische online gegevens kan een beetje lastig zijn. We willen dat deze zo nauw mogelijk aansluit bij uw huidige regels voor online kanalen (van het online regelblad) voor een schone rapportage. Hieronder ziet u een voorbeeld van ideale kanaaltoewijzing.

>[!NOTE]
>
>Deze kanaaltoewijzing wordt uitgevoerd in het dialoogvenster [!UICONTROL Offline Channels] van de [!DNL Marketo Measure] -toepassing omdat we SFDC-campagnes gebruiken.

| Type Salesforce-campagne | Kanaal | Subkanaal |
|---|---|---|
| Betaalde zoekopdracht - Advertentiewoorden | Betaalde zoekopdracht | AdWords |
| Betaalde zoekopdracht - Bing | Betaalde zoekopdracht | Bing |
| Betaalde zoekopdracht - Yahoo | Betaalde zoekopdracht | Yahoo |

Online gegevens die op deze manier worden toegevoegd, zijn van nature minder korrelig dan online gegevens [!DNL Marketo Measure] tracks via JavaScript. Velden zoals de URL van het formulier, de bestemmingspagina, de verwijzingspagina, enz. worden bijvoorbeeld niet gevuld. Daarom wordt aangeraden de campagnes zo mogelijk over elke bron te verdelen. Zoals in het voorbeeld hierboven wordt gezien, zou u veelvoudige Types van Campagne voor elke bron moeten hebben om granulariteit in rapportering te hebben.

Het zou niet mogelijk of redelijk kunnen zijn om het aantal Types van Campagne SFDC te hebben om korrelige kanaalafbeelding te steunen, zodat kunt u aan enkel afbeelding aan het niveau van het Kanaal en het negeren van subkanalen toevallen. Als het kanaalniveau ook niet bekend is, kunt u een proxykanaal instellen als &quot;Historiaal digitaal&quot;, zodat u tenminste weet dat het een online aanraking was.

Als u de aanraakpuntdatum die voor deze historische online inspanningen zal worden gepropageerd, op grote schaal moet bewerken, gebruikt u de [!DNL Marketo Measure] aangepast &quot;[!UICONTROL Bulk Update Touchpoint Date]&quot; (dit is beschikbaar als een aangepast veld op het Campagneobject in SFDC). Als de campagne een korte tijdspanne heeft, zou het misschien nuttig zijn om de aanraakpuntdatum op een dag door daginterval uit te geven, terwijl het zou kunnen logisch zijn om wekelijks massale update als de Campagne een langere tijdspanne heeft. Als u de functie Aanraakdatum bulkupdate wel gebruikt, moet u de regel Campagne synchroniseren bijwerken bijwerken zodat u de datum van het aanraakpunt voor kopers kunt gebruiken in het datumveld. Houd er rekening mee dat u hiervoor creatief moet zijn met de regels voor Campagne Sync als dit alleen van toepassing is op een campagne of twee en niet alle.

**Off line:**

Historische gegevens over offlinemarketingactiviteiten (die niet via JavaScript kunnen worden bijgehouden) moeten ook in SFDC-campagnes worden georganiseerd. SFDC-campagnes zijn de weg [!DNL Marketo Measure] houdt off-line inspanningen ongeacht als de activiteit &quot;historisch&quot;of &quot;huidig/post is[!DNL Marketo Measure] implementatie&quot;. Volg daarom dezelfde kanaaltoewijzing als in de oorspronkelijke training voor offlinekanaalconfiguratie is vastgelegd.

Indien nodig gebruikt u de knop Aanraakpunt datum bulkupdate om de aanraakpuntdatum voor campagsleden in massa te wijzigen. Bijvoorbeeld, als u campagnes SFDC na gebeurtenis voorkwam-u zou willen massa uitgeven voor de correcte datum. Als u de functie Aanraakdatum bulkupdate wel gebruikt, moet u de regel Campagne synchroniseren bijwerken bijwerken zodat u de datum van het aanraakpunt voor kopers in het datumveld kunt gebruiken. Houd er rekening mee dat u hiervoor creatief moet zijn met de regels voor Campagne Sync als dit alleen van toepassing is op een campagne of twee en niet alle.

## Historische campagnes synchroniseren in [!DNL Dynamics] {#syncing-historic-campaigns-in-dynamics}

[!DNL Marketo Measure] kan met terugwerkende kracht aanraakpunten voor interactie produceren die in het verleden voorkwamen, zolang zij in Campagnes binnen worden georganiseerd [!DNL Dynamics].

Hierbij gaat het gewoonlijk om werkzaamheden in de BCR om rekening te houden met historische data. De verwerking zal ook anders zijn voor online-inspanningen (bijgehouden door JS) en offlineinspanningen (niet door JS kunnen worden gevolgd).

Volg de onderstaande instructies voor het ordenen van historische gegevens in [!DNL Dynamics] in een indeling waarnaar kan worden gesynchroniseerd [!DNL Marketo Measure].

**Online:**

De historische digitale gegevens moeten worden georganiseerd in [!DNL Dynamics] campagnes om te worden teruggevuld. In het ideale geval is deze structuur al aanwezig.

Als de gegevens elders worden gehuisvest (bijvoorbeeld nog steeds in Marketing Automation wonen), moet dit worden ingedrukt [!DNL Dynamics] en georganiseerd in de passende campagnes. Dan zult u voor de Datum van het Aanraakpunt moeten rekenschap geven aangezien u het de datum van het verleden wilt weerspiegelen, niet de datum u het in duwde [!DNL Dynamics]. Als u deze datum wilt overschrijven, kunt u de datum wijzigen in het veld Aanraakpunt koper. U moet dit toevoegen aan het formulier voor de marketinglijst.

![](assets/syncing-historical-data-2.png)

Dientengevolge, kunt u massa plaatsen de datum voor iedereen in die Lijst van de Marketing die voor de Datum van het Aanraakpunt zal worden gebruikt. Als u nauwkeuriger historische datums wilt, maakt u meerdere marketinglijsten voor dezelfde campagne, elk met een eigen aanraakpuntdatum. Als de Campagne een korte tijdspanne heeft, misschien zou het nuttig zijn om een Lijst van de Marketing voor elke dag tot stand te brengen. Als de Campagne een langere tijdspanne heeft, zou het steek kunnen zijn om een Lijst van de Marketing op een wekelijkse basis tot stand te brengen.

Meer informatie over het synchroniseren van Marketing Lists vindt u hier: [[!DNL Dynamics] Campagnes en marketinglijsten](/help/marketo-measure-and-dynamics/dynamics-reporting/dynamics-campaigns-and-marketing-lists.md)

>[!NOTE]
>
>Als u om het even welke reden een campagne het volgen online activiteit hebt die voorbij de levende datum van JavaScript actief is, zeker om te plaatsen &quot;[!UICONTROL Touchpoint End Date]&quot; veld tot de datum waarop het JS live is gegaan. Dit om dubbele aanraakpunten voor dezelfde interactie te vermijden.

Overwegingen: Online gegevens die op deze manier worden toegevoegd, zijn van nature minder korrelig dan online gegevens [!DNL Marketo Measure] tracks via JavaScript. Velden zoals: De URL van het formulier, de bestemmingspagina, de verwijzingspagina, enz. worden niet ingevuld. Daarom wordt aangeraden de campagnes zo mogelijk over elke bron te verdelen. Hieronder ziet u een voorbeeld van ideale mapping.

| Type dynamicampagne | Kanaal | Subkanaal |
|---|---|---|
| Betaalde zoekopdracht - Advertentiewoorden | Betaalde zoekopdracht | AdWords |
| Betaalde zoekopdracht - Bing | Betaalde zoekopdracht | Bing |
| Betaalde zoekopdracht - Yahoo | Betaalde zoekopdracht | Yahoo |

Als u geen manier hebt om een bron te identificeren of het niet de tijd en de inspanning waard is, kunt u één Type van Campagne gebruiken dat aan een kanaal wordt toegewezen genoemd iets zoals &quot;Verouderde Digitale&quot;of &quot;Historische Website.

**Off line:**

Om aanraakpunten te hebben voor offlinemarketinginspanningen uit het verleden, moeten de gegevens worden georganiseerd in [!DNL Dynamics] campagnes en gesynchroniseerd met [!DNL Marketo Measure]. Het proces is hetzelfde als voor de huidige offlinekanalen (synchroniseer de campagne via Marketinglijsten of Campagnereacties). Hieronder ziet u een voorbeeld van kanaaltoewijzing.

| Type dynamicampagne | Kanaal | Subkanaal |
|---|---|---|
| Gebeurtenissen - gesponsorde conferenties | Gebeurtenissen | Gesponsorde conferenties |
| Gebeurtenissen - Partner Events | Gebeurtenissen | Partnergebeurtenissen |
| Gebeurtenissen - gehoste gebeurtenissen | Gebeurtenissen | Gehoste gebeurtenissen |
| Webinar - Partner Webinar | Webinar | Partner Webinar |

Als deze gegevens nog niet zijn geordend in campagnes met de juiste datums ingesteld, kunt u het veld Aanraakpunt koper gebruiken om de juiste datum van de offlineactiviteit in het verleden weer te geven.

