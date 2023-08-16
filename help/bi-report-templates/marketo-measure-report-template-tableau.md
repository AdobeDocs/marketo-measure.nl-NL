---
description: "[!DNL Marketo Measure] Rapportsjabloon - Tabel - [!DNL Marketo Measure] - Productdocumentatie"
title: "[!DNL Marketo Measure] Rapportsjabloon - Tabel"
exl-id: 18963be9-5c6e-4454-8244-b50460e2bed5
feature: Reporting
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '2296'
ht-degree: 0%

---

# [!DNL Marketo Measure] Rapportsjabloon - Tableau {#marketo-measure-report-template-tableau}

## Aan de slag {#getting-started}

U hebt toegang tot [!DNL Tableau] rapportsjabloon [hier](https://github.com/adobe/Marketo-Measure-BI-Templates){target="_blank"}.

Open de [!DNL Adobe Marketo Measure] Werkboekbestand Sjabloon rapporteren.

U moet de bestaande verbindingsgegevens bijwerken naar de specifieke verbindingsgegevens van de Snowflake. Klik op de knop [!UICONTROL Edit Connection] en voert u de stappen uit die in het dialoogvenster [[!UICONTROL Data Connection]](#data-connection) van deze documentatie.

![](assets/marketo-measure-report-template-tableau-1.png)

## Gegevensverbinding {#data-connection}

U moet een gegevensverbinding met uw Snowflake-instantie instellen. Hiervoor hebt u de servernaam samen met uw gebruikersnaam en wachtwoord nodig. Details over waar u deze informatie kunt vinden en waar u uw wachtwoord opnieuw kunt instellen, worden gedocumenteerd [hier](/help/marketo-measure-data-warehouse/data-warehouse-access-reader-account.md){target="_blank"}.

![](assets/marketo-measure-report-template-tableau-2.png)

U moet ook een eerste SQL-opdracht invoeren. Dit steunt het gebruik van douanevragen in dit gegevensmodel. De opdracht om in te voeren is &quot;Schema gebruiken `<your schema name>`&quot;. U kunt de naam van het schema vinden in het dialoogvenster [!UICONTROL data warehouse connections] pagina, zie bovenstaande documentatie.

![](assets/marketo-measure-report-template-tableau-3.png)

### Aangepaste SQL-query&#39;s {#custom-sql-queries}

Omdat [!DNL Tableau] past gegevensbronfilters op de algemene vraag en niet op de individuele lijst toe de filter aan wordt geplaatst, hebben wij verkozen om douane SQL voor elke lijst in het model te gebruiken. Hierdoor kan het model verwijderde en gedupliceerde rijen op tabelniveau verwijderen. Bijvoorbeeld, wanneer toegepast als gegevensbronfilter, zitting._delete_date is null zal worden toegevoegd aan waar clausule van de vraag, resulterend in de volgende vraag.

**Aan gegevensbron toegevoegde filters**

```
--A deleted session removes this row completely and the touchpoint data is lost. Select *
   From Touchpoint    tp
      join Session sn
      on tp.session_id = sn.session_id 
 Where tp._deleted_date is null
    and sn._deleted_date is null
```

Dit is echter onjuist in die zin dat als een sessie is verwijderd, maar het bijbehorende aanraakpunt niet wordt verwijderd, de aanraakpuntgegevens uit de gegevensset worden verwijderd. We willen de aanraakpuntgegevens in de gegevensset, omdat het aanraakpunt niet is verwijderd. Als u aangepaste SQL toevoegt, worden de filtercriteria op tabelniveau toegepast. Dit leidt tot de volgende query.

**Filters toegepast via Aangepaste SQL**

```
--A deleted session only removes the session related data, and the touchpoint data is preserved. Select *
   From Touchpoint       tp
      join Session sn
      on tp.session_id          = sn.session_id 
      and sn._deleted_date      is null
  Where tp._deleted_date is null
```

## Gegevenstransformaties {#data-transformations}

Er zijn enkele transformaties toegepast op de gegevens in [!DNL Tableau] in de oorspronkelijke staat in Snowflake. De meeste van deze transformaties worden toegepast in de aangepaste SQL-query&#39;s die de tabellen in de [!DNL Tableau] model. Als u de aangepaste SQL wilt weergeven die wordt gebruikt om een tabel te genereren, klikt u met de rechtermuisknop op de tabelnaam en selecteert u &quot;Aangepaste SQL-query bewerken&quot;. Enkele specifieke transformaties worden hieronder beschreven.

![](assets/marketo-measure-report-template-tableau-4.png)

![](assets/marketo-measure-report-template-tableau-5.png)

### Verwijderde kolommen {#removed-columns}

Om het gegevensmodel te vereenvoudigen en overtollige en onnodige gegevens te verwijderen, hebben wij het aantal kolommen verminderd die in Tableau van de originele Snowflake lijst worden ingevoerd. Verwijderde kolommen bevatten onnodige externe sleutels, gedenormaliseerde dimensionale gegevens die beter kunnen worden gebruikt via relaties met andere tabellen in het model, auditkolommen en velden die worden gebruikt voor interne [!DNL Marketo Measure] verwerking. U kunt kolommen toevoegen of verwijderen zoals vereist voor uw bedrijfsbehoeften door de lijst van ingevoerde kolommen in de Uitgezochte sectie van douaneSQL uit te geven.

>[!NOTE]
>
>De meeste tabellen in het gegevenspakhuis bevatten gedenormaliseerde dimensionale gegevens. We hebben gewerkt om het model te normaliseren en op te schonen in [!DNL Tableau] de prestaties en de nauwkeurigheid van de gegevens zoveel mogelijk verbeteren. Wees voorzichtig met het opnemen van eventuele aanvullende gedenormaliseerde velden in feitentabellen, dit kan het filteren van dimensies in verschillende tabellen afbreken en kan ook leiden tot onjuiste rapportage.

### Naam van kolommen wijzigen {#renamed-columns}

Tabellen en kolommen zijn hernoemd om ze gebruiksvriendelijker te maken en de naamgevingsconventies te standaardiseren. Als u de wijzigingen in de kolomnaam wilt weergeven, verwijst u naar de aangepaste SQL-instructies waarmee de tabellen worden gemaakt.

### Rijen toegevoegd {#rows-added}

Om de mogelijkheden van de valutaconversie aan de berekeningen in het model toe te voegen, hebben wij een collectieve omrekeningskoers en een kolom van de doelwisselkoers aan zowel de lijsten van de Mogelijkheid als van de Kosten toegevoegd. De waarde in deze kolommen wordt toegevoegd op rijniveau en door zich bij de lijst van het Tarief van de Omzetting op zowel datum als muntidentiteitskaart aan te sluiten geëvalueerd. Aangezien in Tableau geen gegevens kunnen worden uitgewisseld in tabellen die meer dan één dimensietabel delen, zijn de conversietarieven rechtstreeks toegevoegd aan de tabellen die deze tabel gebruiken. Zie voor meer informatie over de werking van valutaconversie in dit model de optie [Valutaconversie](#currency-conversion) in deze documentatie.

![](assets/marketo-measure-report-template-tableau-6.png)

Er zijn enkele plaatsen waar twee tabellen van [!DNL Snowflake] zijn gecombineerd met een unie om één tabel in het [!DNL Tableau] gegevensmodel. In deze gevallen is een kolom &quot;Type&quot; toegevoegd om aan te geven welke [!DNL Snowflake] de lijst het uit komt en aanwijst welke entiteit de rij vertegenwoordigt. Zie de sectie Relatie en Gegevensstroom in deze documentatie voor meer informatie over de tabellen die zijn gecombineerd.

![](assets/marketo-measure-report-template-tableau-7.png)

### Segmentnamen {#segment-names}

Aangezien de segmentnamen klantgericht zijn, hebben zij generische kolomnamen in het de gegevenspakhuis van Snowflake. [!DNL BIZ_SEGMENT_NAMES] is een toewijzingstabel die van de generische segmentnaam met de aangepaste segmentnaam een lijst maakt het aan, zoals die in de segmentsectie in wordt bepaald [!DNL Marketo Measure] UI. Als u aangepaste segmentnamen gebruikt en uw [!DNL Tableau] gebruik deze tabel om deze in te voegen en wijzig de naam van de kolommen in het tableau-model handmatig. De segmentkolommen bevinden zich in de tabel Aanraakpunt voor lead en kenmerk en hoeven slechts één keer te worden hernoemd.

De [!UICONTROL CATEGORY] De kolom maakt een lijst van het categorienummer en de kolom SEGMENT_NAME heeft de aangepaste segmentnaam het aan in kaart brengt.

![](assets/marketo-measure-report-template-tableau-8.png)

Namen kunnen op twee manieren worden bijgewerkt. De eerste optie is het bijwerken van de aangepaste SQL. In dit voorbeeld is de naam van de categorieën 1-6 gewijzigd op basis van de toewijzing in de tabel Segmentnamen.

![](assets/marketo-measure-report-template-tableau-9.png)

De andere optie is om de naam van de kolommen rechtstreeks in het dialoogvenster [!DNL Tableau] tabel.

![](assets/marketo-measure-report-template-tableau-10.png)

## Gegevensmodel {#data-model}

Klik op de onderstaande afbeelding voor de volledige versie.

[![](assets/marketo-measure-report-template-tableau-11.png)](/help/bi-report-templates/assets/tableau-data-model.png){target="_blank"}

### Relaties en gegevensstroom {#relationships-and-data-flow}

Gebeurtenisgegevens, die worden gebruikt voor het maken van aanraakpunten, worden opgeslagen in de [!UICONTROL Session], [!UICONTROL Task], [!UICONTROL Event], [!UICONTROL Activity], en [!UICONTROL Campaign Member] tabellen. Deze gebeurtenistabellen worden via de respectievelijke id&#39;s aan de tabel met aanraakpunten toegevoegd en als de gebeurtenis tot een aanraakpunt heeft geleid, worden de gegevens in de tabel met aanraakpunten opgeslagen.

Aanraakpunten voor leads en kenmerkaanraakpunten worden in dit model gecombineerd tot één tabel, met een koppeling naar de aanraakpunttabel. De kolom &quot;Type aanraakpunt&quot; is toegevoegd om aan te geven of een rij een aanraakpunt voor lead of kenmerk is. De meeste dimensionale gegevens voor aanraakpunten Lead en Attribution worden afkomstig van de koppeling naar het overeenkomstige aanraakpunt.

De overgangen van het Stadium van de kans en van het Stadium van de Lood worden gecombineerd in één lijst in dit model, met een verbinding aan [!UICONTROL Lead and Attribution] Aanraakpunttabel. De kolom Overgangstype is toegevoegd om aan te geven of een rij een opportunity- of Lead-werkgebiedovergang is.

Zowel de kosten als de gegevens van het Aanraakpunt delen het Kanaal en de afmetingen van de Campagne. Maar Tableau is beperkt in het vermogen om gedeelde dimensies tussen feitenlijsten te modelleren. Aangezien wij tot één gedeelde afmetinglijst beperkt zijn, zijn de gegevens van het Kanaal en van de Campagne gecombineerd in één lijst. Ze worden gecombineerd met een kruis van de twee dimensies in één tabel in Tableau: Kanaal en Campagne. De unieke id wordt gemaakt door de kanaal- en campagne-id samen te voegen. Dezelfde id-waarde wordt toegevoegd aan de tabellen Touchpoint en Cost om een relatie met deze gecombineerde dimensie-tabel te maken.

![](assets/marketo-measure-report-template-tableau-12.png)

In dit model zijn de afmetingen voor Campagne en Kanaal gekoppeld aan het aanraakpunt. Alle rapportage over deze afmetingen vindt dus plaats via deze koppeling. Dit betekent dat dimensionale rapportage over gebeurtenisgegevens mogelijk onvolledig is. Veel gebeurtenissen hebben namelijk pas koppelingen naar deze afmetingen nadat ze zijn verwerkt tot aanraakpunten.

>[!NOTE]
>
>Sommige gebeurtenissen, zoals sessies, hebben directe koppelingen naar de afmetingen Campagne en Kanaal. Als het rapporteren op het niveau van de Zitting over deze dimensies wordt gewenst, adviseert men dat een afzonderlijk gegevensmodel voor dit doel wordt gecreeerd.

De gegevens van kosten worden opgeslagen bij verschillende samenvoegingsniveaus binnen de Snowflake gegevens pakhuisKostentabel. Voor alle advertentieleveranciers, kunnen de het niveaugegevens van de Campagne tot het niveau van het Kanaal worden uitgebreid. Om deze reden, trekt dit model kostengegevens die op de &quot;campagne_is_aggregatable_cost&quot;vlag worden gebaseerd. De zelf-gemelde kosten kunnen op het niveau van het Kanaal slechts worden voorgelegd en worden vereist niet om de gegevens van de Campagne te hebben. Om de nauwkeurigste mogelijke kostenrapportage mogelijk te maken, worden zelf-gerapporteerde kosten opgehaald op basis van de markering &quot;channel_is_aggregatable_cost&quot;. De vraag die kostengegevens invoert wordt geschreven met de volgende logica: Als ad_provider = &quot;SelfReported&quot; dan channel_is_aggregatable_cost = waar, else campagne_is_aggregatable_cost = waar.

In het kader van dit model: [!UICONTROL Contact], [!UICONTROL Account], en [!UICONTROL Opportunity] gegevens worden beschouwd als dimensionale gegevens en worden rechtstreeks gekoppeld aan de tabel met het aanraakpunt voor lead en Attribution.

### Valutaconversie {#currency-conversion}

De koersen in de tabel Conversierente geven de waarde aan die nodig is om een bedrag uit de bedrijfsvaluta om te zetten. Voor omrekening naar een valuta is een dubbele omrekening vereist, eerst van de oorspronkelijke valuta naar de bedrijfsvaluta en vervolgens van de bedrijfsvaluta naar de geselecteerde valuta. De eerste stap in deze keten in het model bestaat uit het toevoegen van twee kolommen met deze conversietarieven aan de tabellen met bedragen, Opportunity en Kosten. Deze stappen worden beschreven in de sectie Rijen toegevoegd in dit document. Omdat conversiekoersen niet statisch hoeven te zijn en kunnen worden gewijzigd met opgegeven datumbereiken, moeten alle berekeningen voor valutaomrekening op rijniveau worden uitgevoerd. De omrekening van de oorspronkelijke valuta naar de bedrijfsvaluta bestaat uit het delen van de waarde door de omrekeningskoers van de onderneming en vervolgens het vermenigvuldigen met de omrekeningskoers van het streefcijfer. De doelconversiekoers wordt bepaald door de geselecteerde valutaparameterwaarde.

* Zet de oorspronkelijke waarde om in de waarde van de bedrijfsvaluta / omrekeningskoers = waarde in de bedrijfsvaluta
* De waarde omzetten van bedrijfswaarde in geselecteerde valutawaarde in bedrijfsvaluta `*` omrekeningskoers van geselecteerde valuta = waarde in geselecteerde valuta

![](assets/marketo-measure-report-template-tableau-13.png)

De omrekeningsmaatregelen in dit model vervangen de koers 1,0 als geen omrekeningskoers kan worden vastgesteld. Er zijn afzonderlijke maatregelen genomen om de valutawaarde voor de maatregel weer te geven en er wordt een waarschuwing gegeven als een berekening meer dan één valutawaarde bevat (een waarde kan dus niet in de geselecteerde valuta worden omgezet). Deze maatstaven, Kostenvaluta en Winst Currency, zijn als tooltips opgenomen in elke visuele weergave die gegevens over kosten of opbrengsten weergeeft.

![](assets/marketo-measure-report-template-tableau-14.png)

## Gegevensdefinities {#data-definitions}

Er zijn definities toegevoegd aan de [!DNL Tableau model] voor parameters, aangepaste kolommen en maatregelen.

![](assets/marketo-measure-report-template-tableau-15.png)

Definities weergeven voor kolommen die rechtstreeks afkomstig zijn van [!DNL Snowflake], zie de [gegevensopslagdocumentatie](/help/marketo-measure-data-warehouse/data-warehouse-schema.md){target="_blank"}.

## Verschillen tussen sjablonen en ontdekken {#discrepancies-between-templates-and-discover}

### Toegewezen inkomsten {#attributed-revenue}

Aanraakpunten met regelafstand en kenmerkaanraakpunten nemen dimensionale gegevens over van het originele aanraakpunt. Het rapportsjabloonmodel genereert alle overgeërfde dimensionale gegevens van de relatie tot het aanraakpunt, terwijl in het detectiemodel de dimensionale gegevens worden gedenormaliseerd naar de aanraakpuntrecords voor leads en Attributies. De totale toegerekende inkomsten of de toegerekende inkomsten uit pijpleidingen moeten tussen de twee verslagen worden afgestemd. Er kunnen echter discrepanties worden waargenomen wanneer de inkomsten worden uitgesplitst of gefilterd op basis van dimensionale gegevens (kanaal, subkanaal of campagne). Als de dimensionale opbrengstbedragen niet tussen het malplaatje en Discover aanpassen, is het waarschijnlijk er ontbrekende aanraakpuntverslagen in de reeks van het malplaatjerapport zijn. Dit gebeurt wanneer er een Lead- of Attribution Touchpoint-record is, maar er is geen overeenkomstige record in de Touchpoint-tabel in de gegevensset die in het rapport is geïmporteerd. Omdat deze tabellen op gewijzigde datum worden gefilterd, is het mogelijk dat de Touchpoint-record voor lead/Attribution later is gewijzigd dan de Touchpoint-record. Hierdoor is het aanraakpunt voor lead/Attribution in de gegevensset geïmporteerd terwijl de oorspronkelijke Touchpoint-record dat niet was. Als u dit probleem wilt verhelpen, vergroot u het gefilterde datumbereik voor de tabel met aanraakpunten of verwijder de datumbeperking samen.

>[!NOTE]
>
>Het aanraakpunt is een grote tabel. Houd daarom rekening met de voordelen van een vollediger gegevensset in vergelijking met de hoeveelheid gegevens die moet worden geïmporteerd.

### Kosten {#cost}

Kostenrapportage in de sjablonen is alleen beschikbaar op campagne- en kanaalniveau. Discover biedt echter aan dat voor sommige advertentieleveranciers (bijvoorbeeld creatief, trefwoord, en groepen, enz.) een lagere mate van granulariteit wordt gerapporteerd. Voor meer informatie over de wijze waarop de kostengegevens in de sjablonen worden gemodelleerd, raadpleegt u de [!UICONTROL Data Model] van deze documentatie. Als de afmeting filtert in [!UICONTROL Discover] is ingesteld op kanaal of campagne, moeten de kosten op het kanaal, subchannel en campagneniveau worden afgestemd tussen Discover en de rapportsjablonen.

### ROI {#roi}

Aangezien het rendement van investeringen wordt berekend op basis van toegerekende opbrengsten en kosten, kunnen in het rendement van investeringen en om dezelfde redenen dezelfde verschillen optreden als in beide berekeningen, zoals in die afdelingen is opgemerkt.

### Aanraakpunten {#touchpoints}

Deze metriek, zoals aangetoond in de rapporteringsmalplaatjes, wordt niet weerspiegeld in Discover. Er is momenteel geen directe vergelijking mogelijk tussen beide.

### Webverkeer {#web-traffic}

Het gegevensmodel van het rapportmalplaatje normaliseert kanaal, subchannel, en campagnedimensionele gegevens via het verband tussen Zitting en Aanraakpunt. Dit is anders dan het gegevensmodel Discover, dat deze dimensies aan Zitting ontleedt. Wegens dit onderscheid, zouden de totale aantallen voor bezoeken en bezoekers tussen Discover en het rapporteringsmalplaatje moeten aanpassen, echter, zodra getoond of gefilterd door dimensie, worden deze aantallen niet verwacht om op te zetten. De reden hiervoor is dat de dimensionale gegevens in de sjabloon alleen beschikbaar zijn voor webgebeurtenissen die tot een aanraakpunt hebben geleid (d.w.z. niet-anonieme gebeurtenissen). Raadpleeg voor meer informatie de [Gegevensmodel](#data-model) van deze documentatie.

Er kunnen kleine verschillen zijn tussen de tellingen van de totale site [!DNL Discover] en de sjabloon. Dit komt omdat het gegevensmodel in het rapporteringsmalplaatje dimensionele gegevens voor de Vorm van de Plaats via een verhouding aan Zitting en dan Aanraakpunt verkrijgt; er zijn een paar gevallen waar de gegevens van de plaatvorm geen gecorreleerde zitting hebben.

### Leads en accounts {#leads-and-accounts}

De gedetailleerde rapportage voor aangeroerde accounts kan enigszins verschillen tussen [!DNL Discover] en de sjabloon, dit is opnieuw het gevolg van de dimensionale modellering die voortkomt uit de relatie tussen Touchpoint en Lead Touchpoint of Attribution Touchpoint. Raadpleeg de details in de sectie Toegewezen inkomsten voor meer informatie.

Alle loodtellingen in [!UICONTROL Discover] worden loodtellingen toegewezen en in de rapportagesjabloon is de maatstaf [!UICONTROL leads] aangeraakt. Er is dus geen rechtstreekse vergelijking mogelijk tussen de twee verslagen voor deze maatregel.

### Pad voor betrokkenheid {#engagement-path}

Er is geen directe vergelijking tussen de [!UICONTROL Engagement Path] rapporteren in [!DNL Discover] en de sjabloon. Het verslag in [!DNL Discover] wordt gemodelleerd van het aanraakpunt terwijl het rapport in de sjabloon gemodelleerd is van het aanraakpunt voor kenmerken. De sjabloon richt zich uitsluitend op kansen en de bijbehorende aanraakpunten in plaats van alle aanraakpuntgegevens weer te geven.

### Deal Velocity {#deal-velocity}

Er zou geen discrepantie tussen dit rapport in het malplaatje en de tegel van de Snelheid van de Overeenkomst op het dashboard van de Snelheid in Discover moeten zijn.
