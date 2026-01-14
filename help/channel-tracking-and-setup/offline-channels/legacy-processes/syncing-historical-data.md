---
description: Historische gegevensrichtlijnen synchroniseren voor Marketo Measure-gebruikers
title: Historische gegevens synchroniseren
exl-id: 5a3c1a71-463a-4d75-98b9-fc225839512a
feature: Channels
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '1507'
ht-degree: 0%

---

# Historische gegevens synchroniseren {#syncing-historical-data}

[!DNL Marketo Measure] is een oplossing die de meest korrelige, uitvoerbare gegevens verstrekt. We begrijpen echter dat er bestaande gegevens zijn waarvoor u een kenmerk wilt hebben. Het is mogelijk om aanraakpunten te genereren voor historische gegevens, maar het is belangrijk om rekening te houden met een paar factoren voordat u verder gaat met dit proces.

>[!NOTE]
>
>Dit artikel behandelt een verouderd proces. Wij moedigen gebruikers aan om het [ nieuwe, verbeterde in-app proces ](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"} te gebruiken.

## Te overwegen factoren {#factors-to-consider}

**is de gegevens reeds georganiseerd in campagnes?**

a. De gegevens moeten worden ingedeeld in campagnes die moeten worden gesynchroniseerd met [!DNL Marketo Measure] om aanraakpunten te kunnen genereren. Als het momenteel niet in Campagnes wordt georganiseerd, zult u willen evalueren als het de tijd en de middelen waard is nodig om de gegevens in de aangewezen campagnes te segmenteren.

b. De datum waarop het lid aan de campagne is toegevoegd of als geantwoord is gemarkeerd, wordt gebruikt voor de aanraakpuntdatum, zodat dit ook correct moet zijn. [!DNL Marketo Measure] biedt zowel in SFDC als in MSD een oplossing voor het bijwerken van de datums. Afhankelijk van het volume kan dit echter veel tijd in beslag nemen.

**hebt u een vrij gelijke hoeveelheid gegevens die in campagnes voor alle Kanalen (betaald onderzoek, gebeurtenissen, organisch, enz.) worden georganiseerd?**

Het is belangrijk om een evenwichtig beeld van attributie te hebben om nauwkeurige en &quot;eerlijke&quot;rapportering te hebben. Als u bijvoorbeeld alleen gegevens hebt voor historische offlinekanaals-inspanningen, zoals Events, zullen de gegevens van nature bevooroordeeld zijn zonder historische online gegevens als aanvulling hierop.

**Welk niveau van granulariteit verwacht u?**

In feite kent u alleen de naam Kanaal, Subkanaal en Campagne.

**wat zijn uw rapporteringsdoelstellingen in de toekomst?**

Deze gegevens zullen beperkt blijven, dus is het belangrijk om te overwegen hoe u het wilt gebruiken. Het zou niet het meest logisch kunnen zijn om historische gegevens te vergelijken met toekomstige gegevens.

**hoe ver terug wilt u gaan?**

[!DNL Marketo Measure] raadt u ten zeerste aan het voorgaande jaar niet te overschrijden.

Dit is een onderwerp dat we ten zeerste aanmoedigen om eerst met uw [!DNL Marketo Measure] -contactpersoon te bespreken. Als u het bovenstaande in overweging hebt genomen en wilt doorgaan, staan de algemene instructies (apart voor [!DNL Salesforce] en [!DNL Microsoft Dynamics] ) hieronder.

## Historische campagnes synchroniseren in [!DNL Salesforce] {#syncing-historic-campaigns-in-salesforce}

**Online:**

Als u historische online gegevens wilt synchroniseren, moeten de gegevens worden ingedeeld in Salesforce-campagnes die u vervolgens synchroniseert met [!DNL Marketo Measure] via [!DNL Salesforce] Campagne Sync rules in de app [!DNL Marketo Measure] . Het is belangrijk om ervoor te zorgen dat er geen aanraakpunten worden gegenereerd uit deze campagnes na de datum waarop je JavaScript live ging. De reden hiervoor is dubbele aanraakpunten te voorkomen. Nadat de JavaScript live is, worden online-inspanningen automatisch bijgehouden, dus we willen ze niet ook volgen via een SFDC-campagne. Om dit probleem te vermijden, zeker om een gevoel van tijd aan de regel toe te voegen. Misschien is iets als &quot;Gemaakte Datum van het Lid van de Campagne minder dan [ JavaScript go-live datum ]&quot;.

![](assets/dynamics-lists-1.png)

De component voor kanaaltoewijzing voor historische online gegevens kan een beetje lastig zijn. We willen dat deze zo nauw mogelijk aansluit bij uw huidige regels voor online kanalen (van het online regelblad) voor een schone rapportage. Hieronder ziet u een voorbeeld van ideale kanaaltoewijzing.

>[!NOTE]
>
>Deze kanaaltoewijzing vindt plaats in de sectie [!UICONTROL Offline Channels] van de app [!DNL Marketo Measure] , omdat we SFDC-campagnes gebruiken.

| Salesforce-type campagne | Kanaal | Subkanaal |
|---|---|---|
| Betaalde zoekopdracht - Advertentiewoorden | Betaalde zoekopdracht | AdWords |
| Betaalde zoekopdracht - Bing | Betaalde zoekopdracht | Bing |
| Betaalde zoekopdracht - Yahoo | Betaalde zoekopdracht | Yahoo |

Onlinegegevens die op deze manier worden toegevoegd, zijn van nature minder korrelig dan [!DNL Marketo Measure] -tracks voor onlinegegevens via JavaScript. Velden zoals de URL van het formulier, de bestemmingspagina, de verwijzingspagina, enz. worden bijvoorbeeld niet gevuld. Daarom wordt aangeraden de campagnes zo mogelijk over elke bron te verdelen. Zoals in het voorbeeld hierboven wordt gezien, zou u veelvoudige Types van Campagne voor elke bron moeten hebben om granulariteit in rapportering te hebben.

Het is mogelijk of redelijk om het aantal SFDC-cameratypen te hebben voor ondersteuning van korrelkanaaltoewijzing. U kunt dus gewoon toewijzen naar het Kanaalniveau en subkanalen negeren. Als het kanaalniveau ook niet bekend is, kunt u een proxykanaal instellen zoals &quot;Historisch digitaal&quot;, zodat u tenminste weet dat het een online aanraking was.

Als u de aanraakpuntdatum die voor deze historische online inspanningen wordt geduwd op grote schaal moet uitgeven, gebruik [!DNL Marketo Measure] douane &quot;[!UICONTROL Bulk Update Touchpoint Date]&quot;knoop (dit is beschikbaar als douanegebied op het Voorwerp van de Campagne in SFDC). Als de campagne een korte tijdspanne heeft, zou het misschien nuttig zijn om de aanraakpuntdatum op een dag door daginterval uit te geven, terwijl het zou kunnen logisch zijn om wekelijks massale update als de Campagne een langere tijdspanne heeft. Als u wel de functie Aanraakpunt datum bulkupdate gebruikt, moet u de regel Campagne Sync bijwerken bijwerken zodat u de Buyer Touchpoint-datum in het datumveld kunt gebruiken. Houd er rekening mee dat u hiervoor creatief moet zijn met de regels voor Campagne Sync als dit alleen van toepassing is op een campagne of twee en niet alle.

**Off-line:**

Historische gegevens over offlinemarketingactiviteiten (die niet via JavaScript kunnen worden bijgehouden) moeten ook in SFDC-campagnes worden georganiseerd. SFDC-campagnes zijn de manier waarop [!DNL Marketo Measure] offline inspanningen bijhoudt, ongeacht of de activiteit &quot;historisch&quot; of &quot;huidige/post- [!DNL Marketo Measure] implementatie&quot; is, dus dezelfde kanaaltoewijzing volgt als in de oorspronkelijke training voor offlinekanaalconfiguratie is besloten.

Indien nodig gebruikt u de knop Aanraakpunt datum bulkupdate om de aanraakpuntdatum voor campagsleden in massa te wijzigen. Als u bijvoorbeeld SFDC-campagnes maakt nadat de gebeurtenis heeft plaatsgevonden, wilt u massabewerkingen uitvoeren voor de juiste datum. Als u wel de functie Aanraakpunt datum bulkupdate gebruikt, moet u de regel Campagne Sync bijwerken bijwerken zodat u de Buyer Touchpoint-datum in het datumveld kunt gebruiken. Houd er rekening mee dat u hiervoor creatief moet zijn met de regels voor Campagne Sync als dit alleen van toepassing is op een campagne of twee en niet alle.

## Historische campagnes synchroniseren in [!DNL Dynamics] {#syncing-historic-campaigns-in-dynamics}

[!DNL Marketo Measure] kan retroactief aanraakpunten genereren voor interacties die in het verleden hebben plaatsgevonden, zolang deze maar zijn ingedeeld in Campagnes binnen [!DNL Dynamics] .

Hierbij gaat het gewoonlijk om werkzaamheden in de BCR om rekening te houden met historische data. De verwerking zal ook anders zijn voor online-inspanningen (bijgehouden door JS) en offlineinspanningen (niet door JS kunnen worden gevolgd).

Volg de onderstaande instructies voor het ordenen van historische gegevens in [!DNL Dynamics] in een indeling die kan worden gesynchroniseerd met [!DNL Marketo Measure] .

**Online:**

Historische digitale gegevens moeten worden georganiseerd in [!DNL Dynamics] -campagnes om een back-up te kunnen maken. In het ideale geval is deze structuur al aanwezig.

Als de gegevens ergens anders worden gehuisvest (bijvoorbeeld nog steeds in Marketing Automation wonen), moeten ze naar [!DNL Dynamics] worden geduwd en in de juiste campagnes worden georganiseerd. Dan zult u voor de Datum van het Aanraakpunt moeten rekenschap geven aangezien u het de datum van het verleden wilt weerspiegelen, niet de datum u het in [!DNL Dynamics] duwde. Als u deze datum wilt overschrijven, kunt u het aangepaste veld Buyer Touchpoint Date gebruiken om de datum te wijzigen. U moet dit toevoegen aan het formulier voor de marketinglijst.

![](assets/dynamics-lists-10.png)

Dientengevolge, kunt u massa plaatsen de datum voor iedereen in die Lijst van de Marketing die voor de Datum van het Aanraakpunt zal worden gebruikt. Als u nauwkeuriger historische datums wilt, maakt u meerdere marketinglijsten voor dezelfde campagne, elk met een eigen aanraakpuntdatum. Als de Campagne een korte tijdspanne heeft, misschien zou het nuttig zijn om een Lijst van de Marketing voor elke dag tot stand te brengen. Als de Campagne een langere tijdspanne heeft, zou het steek kunnen zijn om een Lijst van de Marketing op een wekelijkse basis tot stand te brengen.

Meer informatie bij het Synceren van de Lijst van de Marketing kan hier worden gevonden: [[!DNL Dynamics]  Campagnes en de Lijst van de Marketing ](/help/channel-tracking-and-setup/offline-channels/legacy-processes/dynamics-campaigns-and-marketing-lists.md)

>[!NOTE]
>
>Als om het even welke reden u een campagne het volgen online activiteit hebt die voorbij de levende datum van JavaScript actief is, ben zeker om het &quot;[!UICONTROL Touchpoint End Date]&quot;gebied aan de datum te plaatsen JS live ging. Dit om dubbele aanraakpunten voor dezelfde interactie te vermijden.

Overwegingen: onlinegegevens die op deze manier worden toegevoegd, zijn van nature minder korrelig dan online [!DNL Marketo Measure] -tracks via JavaScript. Velden zoals: formulier-URL, bestemmingspagina, verwijzingspagina, enzovoort, worden bijvoorbeeld niet gevuld. Daarom wordt aangeraden de campagnes zo mogelijk over elke bron te verdelen. Hieronder ziet u een voorbeeld van ideale mapping.

| Type dynamicampagne | Kanaal | Subkanaal |
|---|---|---|
| Betaalde zoekopdracht - Advertentiewoorden | Betaalde zoekopdracht | AdWords |
| Betaalde zoekopdracht - Bing | Betaalde zoekopdracht | Bing |
| Betaalde zoekopdracht - Yahoo | Betaalde zoekopdracht | Yahoo |

Als u geen manier hebt om een bron te identificeren of het niet de tijd en de inspanning waard is, kunt u één Type van Campagne gebruiken dat aan een kanaal wordt toegewezen genoemd iets zoals &quot;Verouderde Digitale&quot;of &quot;Historische Website.

**Off-line:**

Als u aanraakpunten wilt hebben voor offlinemarketinginspanningen uit het verleden, moeten de gegevens worden georganiseerd in [!DNL Dynamics] -campagnes en worden gesynchroniseerd met [!DNL Marketo Measure] . Het proces is hetzelfde als voor de huidige offlinekanalen (synchroniseer de campagne via Marketinglijsten of Campagnereacties). Hieronder ziet u een voorbeeld van kanaaltoewijzing.

| Type dynamicampagne | Kanaal | Subkanaal |
|---|---|---|
| Gebeurtenissen - gesponsorde conferenties | Gebeurtenissen | Gesponsorde conferenties |
| Gebeurtenissen - Partner Events | Gebeurtenissen | Partnergebeurtenissen |
| Gebeurtenissen - gehoste gebeurtenissen | Gebeurtenissen | Gehoste gebeurtenissen |
| Webinar - Partner Webinar | Webinar | Partner Webinar |

Als deze gegevens nog niet zijn geordend in campagnes waarvoor de juiste datums zijn ingesteld, kunt u het veld Datum Buyer Touchpoint gebruiken om de juiste datum van de offlineactiviteit in het verleden weer te geven.

