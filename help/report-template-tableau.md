---
description: '[!DNL Marketo Measure] Rapportsjabloon - Tableau -  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] Rapportsjabloon - Tableau'
exl-id: 18963be9-5c6e-4454-8244-b50460e2bed5
feature: Reporting
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '2445'
ht-degree: 0%

---

# [!DNL Marketo Measure] Rapportsjabloon - Tableau {#marketo-measure-report-template-tableau}

## Aan de slag {#getting-started}

U kunt tot het [!DNL Tableau] rapportmalplaatje [ hier ](https://github.com/adobe/Marketo-Measure-BI-Templates){target="_blank"} toegang hebben.

Open het werkboekbestand voor de [!DNL Adobe Marketo Measure] rapportsjabloon.

U moet de bestaande verbindingsgegevens bijwerken naar uw specifieke Snowflake-verbindingsgegevens. Klik op de knop [!UICONTROL Edit Connection] en volg de stappen die in de sectie [[!UICONTROL Data Connection]](#data-connection) van deze documentatie worden beschreven.

![ u moet de bestaande verbindingsgegevens aan uw specifieke Snowflake ](assets/marketo-tableau-7.png) bijwerken

## Gegevensverbinding {#data-connection}

U moet een gegevensverbinding instellen met uw Snowflake-exemplaar. Voor dit, hebt u de naam van de Server samen met uw Gebruikersnaam en Wachtwoord nodig. De details op waar te om deze informatie te vinden en uw wachtwoord terug te stellen, indien nodig, worden gedocumenteerd [ hier ](/help/data-warehouse-access-reader-account.md){target="_blank"}.

![ u moet opstelling een gegevensverbinding aan uw instantie van Snowflake.](assets/marketo-tableau-5.png)

U moet ook een eerste SQL-opdracht invoeren. Dit steunt het gebruik van douanevragen in dit gegevensmodel. De opdracht die moet worden ingevoerd, is &quot;Schema gebruiken `<your schema name>`&quot;. U kunt de naam van het schema vinden op de pagina [!UICONTROL data warehouse connections] . Raadpleeg hiervoor de documentatie.

![ u zult ook een eerste SQL bevel moeten ingaan. Dit ondersteunt ](assets/marketo-tableau-6.png)

### Aangepaste SQL-query&#39;s {#custom-sql-queries}

Omdat [!DNL Tableau] gegevensbronfilters op de algemene vraag en niet op de individuele lijst toepast wordt de filter geplaatst aan, hebben wij verkozen om douaneSQL voor elke lijst in het model te gebruiken. Hierdoor kan het model verwijderde en gedupliceerde rijen op tabelniveau verwijderen. Bijvoorbeeld, wanneer toegepast als gegevensbronfilter, zitting._delete_date is null zal worden toegevoegd aan waar clausule van de vraag, resulterend in de volgende vraag.

**Filters die aan Gegevens Source** worden toegevoegd

```sql
--A deleted session removes this row completely and the touchpoint data is lost. Select *
   From Touchpoint    tp
      join Session sn
      on tp.session_id = sn.session_id
 Where tp._deleted_date is null
    and sn._deleted_date is null
```

Dit is echter onjuist in die zin dat als een sessie is verwijderd, maar het bijbehorende aanraakpunt niet wordt verwijderd, de aanraakpuntgegevens uit de gegevensset worden verwijderd. We willen de aanraakpuntgegevens in de gegevensset, omdat het aanraakpunt niet is verwijderd. Als u aangepaste SQL toevoegt, weet u zeker dat de filtercriteria op tabelniveau worden toegepast. Dit leidt tot de volgende query.

**Filters die via Aangepaste SQL** worden toegepast

```sql
--A deleted session only removes the session related data, and the touchpoint data is preserved. Select *
   From Touchpoint       tp
      join Session sn
      on tp.session_id          = sn.session_id
      and sn._deleted_date      is null
  Where tp._deleted_date is null
```

## Gegevenstransformaties {#data-transformations}

Er zijn enkele transformaties toegepast op de gegevens in [!DNL Tableau] vanaf de oorspronkelijke staat in Snowflake. De meeste van deze transformaties worden toegepast in de aangepaste SQL-query&#39;s die de tabellen in het [!DNL Tableau] -model genereren. Als u de aangepaste SQL wilt weergeven die wordt gebruikt om een tabel te genereren, klikt u met de rechtermuisknop op de tabelnaam en selecteert u &quot;Aangepaste SQL-query bewerken&quot;. Enkele specifieke transformaties worden hieronder beschreven.

![ een paar transformaties zijn toegepast op de gegevens in Tableau ](assets/marketo-tableau-1.png)

![ een paar transformaties zijn toegepast op de gegevens in Tableau ](assets/marketo-tableau-2.png)

### Verwijderde kolommen {#removed-columns}

Om het gegevensmodel te vereenvoudigen en overtollige en onnodige gegevens te verwijderen, hebben wij het aantal kolommen verminderd die in Tableau van de originele Snowflake lijst worden ingevoerd. Verwijderde kolommen bevatten onnodige externe sleutels, gedenormaliseerde dimensionale gegevens die beter kunnen worden gebruikt via relaties met andere tabellen in het model, auditkolommen en velden die worden gebruikt voor interne [!DNL Marketo Measure] -verwerking. U kunt kolommen toevoegen of verwijderen zoals vereist voor uw bedrijfsbehoeften door de lijst van ingevoerde kolommen in de Uitgezochte sectie van douaneSQL uit te geven.

>[!NOTE]
>
>De meeste tabellen in het gegevenspakhuis bevatten gedenormaliseerde dimensionale gegevens. We hebben er alles aan gedaan om het model in [!DNL Tableau] zoveel mogelijk te normaliseren en op te schonen om de prestaties en gegevensnauwkeurigheid te verbeteren. Wees voorzichtig met het opnemen van eventuele aanvullende gedenormaliseerde velden in feitentabellen, dit kan het filteren van dimensies in verschillende tabellen afbreken en kan ook leiden tot onjuiste rapportage.

### Naam van kolommen wijzigen {#renamed-columns}

Tabellen en kolommen hebben een andere naam gekregen om ze gebruiksvriendelijker te maken en de naamgevingsconventies te standaardiseren. Als u de wijzigingen in de kolomnaam wilt weergeven, verwijst u naar de aangepaste SQL-instructies waarmee de tabellen worden gemaakt.

### Rijen toegevoegd {#rows-added}

Om de mogelijkheden van de valutaconversie aan de berekeningen in het model toe te voegen, hebben wij een collectieve omrekeningskoers en een kolom van de doelwisselkoers aan zowel de lijsten van de Mogelijkheid als van de Kosten toegevoegd. De waarde in deze kolommen wordt toegevoegd op rijniveau en door zich bij de lijst van het Tarief van de Omzetting op zowel datum als muntidentiteitskaart aan te sluiten geëvalueerd. Aangezien in Tableau geen gegevens kunnen worden uitgewisseld in tabellen die meer dan één dimensietabel delen, zijn de conversietarieven rechtstreeks toegevoegd aan de tabellen die deze tabel gebruiken. Voor meer details op hoe de muntomzetting in dit model werkt, zie de [ sectie van de Omzetting van de Valuta 0} {in deze documentatie.](#currency-conversion)

![ om de mogelijkheden van de muntomzetting aan de berekeningen in het model toe te voegen, hebben wij ](assets/marketo-tableau-4.png)

Er zijn een paar plaatsen waar twee lijsten van [!DNL Snowflake] met een vereniging zijn gecombineerd om één lijst in het [!DNL Tableau] gegevensmodel tot stand te brengen. In deze gevallen is een kolom &quot;Type&quot; toegevoegd om aan te geven uit welke [!DNL Snowflake] -tabel deze bestaat en om aan te geven welke entiteit de rij vertegenwoordigt. Zie de sectie Relatie en Gegevensstroom in deze documentatie voor meer informatie over de tabellen die zijn gecombineerd.

![ er zijn een paar plaatsen waar twee lijsten van Snowflake ](assets/marketo-tableau-3.png) hebben

### Segmentnamen {#segment-names}

Aangezien de segmentnamen aanpasbaar zijn, hebben zij generische kolomnamen in het de gegevenspakhuis van Snowflake. [!DNL BIZ_SEGMENT_NAMES] is een toewijzingstabel die van de generische segmentnaam met de aangepaste segmentnaam het aan, zoals bepaald in de segmentsectie in [!DNL Marketo Measure] UI een lijst maakt. Als u aangepaste segmentnamen gebruikt en uw [!DNL Tableau] -model wilt bijwerken om deze op te nemen, gebruikt u deze tabel en wijzigt u de naam van de kolommen in het tableau-model handmatig. De segmentkolommen bevinden zich in de tabel Aanraakpunt voor lead en kenmerk en hoeven slechts één keer te worden hernoemd.

De kolom [!UICONTROL CATEGORY] geeft het categorienummer weer en de kolom SEGMENT_NAME heeft de aangepaste segmentnaam die eraan is toegewezen.

![ de kolom van de CATEGORIE maakt een lijst van het categorienummer en de kolom SEGMENTNAME ](assets/marketo-tableau-13.png)

Namen kunnen op twee manieren worden bijgewerkt. De eerste optie is het bijwerken van de aangepaste SQL. In dit voorbeeld is de naam van de categorieën 1-6 gewijzigd op basis van de toewijzing in de tabel Segmentnamen.

![ de Namen kunnen op twee manieren worden bijgewerkt. De eerste optie is aan ](assets/marketo-tableau-14.png)

De andere optie is om de naam van de kolommen rechtstreeks in de tabel [!DNL Tableau] te wijzigen.

![ de andere optie moet de kolommen in ](assets/marketo-tableau-9.png) direct anders noemen

## Gegevensmodel {#data-model}

Klik op de onderstaande afbeelding voor de volledige versie.

[![Klik op de onderstaande afbeelding voor de volledige versie.](assets/marketo-tableau-8.png)](assets/tableau-model-1.png){target="_blank"}

### Relaties en gegevensstroom {#relationships-and-data-flow}

Gebeurtenisgegevens die worden gebruikt voor het maken van aanraakpunten, worden opgeslagen in de tabellen [!UICONTROL Session] , [!UICONTROL Task] , [!UICONTROL Event] , [!UICONTROL Activity] en [!UICONTROL Campaign Member] . Deze gebeurtenistabellen worden via de respectievelijke id&#39;s aan de tabel met aanraakpunten toegevoegd en als de gebeurtenis tot een aanraakpunt heeft geleid, worden de gegevens in de tabel met aanraakpunten opgeslagen.

Aanraakpunten voor leads en kenmerkaanraakpunten worden in dit model gecombineerd tot één tabel, met een koppeling naar de aanraakpunttabel. De kolom &quot;Type aanraakpunt&quot; is toegevoegd om aan te geven of een rij een aanraakpunt voor lead of kenmerk is. De meeste dimensionale gegevens voor aanraakpunten Lead en Attribution worden afkomstig van de koppeling naar het overeenkomstige aanraakpunt.

De overgangen van het Stadium van de kans en de Overgangen van het Stadium van de Lood worden gecombineerd in één lijst in dit model, met een verbinding aan de [!UICONTROL Lead and Attribution] lijst van het Aanraakpunt. De kolom Overgangstype is toegevoegd om aan te geven of een rij een opportunity- of Lead-werkgebiedovergang is.

Zowel de kosten als de gegevens van het Aanraakpunt delen het Kanaal en de afmetingen van de Campagne. Tableau is echter beperkt in zijn vermogen om gedeelde dimensies tussen feitenlijsten te modelleren. Aangezien wij tot één gedeelde afmetinglijst beperkt zijn, zijn de gegevens van het Kanaal en van de Campagne gecombineerd in één lijst. Ze worden gecombineerd met een kruis van de twee dimensies in één tabel in Tableau: Kanaal en Campagne. De unieke id wordt gemaakt door de kanaal- en campagne-id samen te voegen. Dezelfde id-waarde wordt toegevoegd aan de tabellen Touchpoint en Cost om een relatie met deze gecombineerde dimensie-tabel te maken.

![ zowel Kost als de gegevens van het Aanraakpunt delen het Kanaal en de afmetingen van de Campagne. Nochtans, Tableau ](assets/marketo-tableau-10.png)

In dit model zijn de afmetingen voor Campagne en Kanaal gekoppeld aan het aanraakpunt. Alle rapportage over deze afmetingen vindt dus plaats via deze koppeling. Dit betekent dat dimensionale rapportage over gebeurtenisgegevens mogelijk onvolledig is. Veel gebeurtenissen hebben namelijk pas koppelingen naar deze afmetingen nadat ze zijn verwerkt tot aanraakpunten.

>[!NOTE]
>
>Sommige gebeurtenissen, zoals sessies, hebben directe koppelingen naar de afmetingen Campagne en Kanaal. Als het rapporteren op het niveau van de Zitting over deze dimensies wordt gewenst, adviseert men dat een afzonderlijk gegevensmodel voor dit doel wordt gecreeerd.

Kostengegevens worden opgeslagen op verschillende aggregatieniveaus binnen de kostentabel van het Snowflake-gegevenspakhuis. Voor alle advertentieleveranciers, kunnen de het niveaugegevens van de Campagne tot het niveau van het Kanaal worden uitgebreid. Om deze reden, trekt dit model kostengegevens die op de &quot;campagne_is_aggregatable_cost&quot;vlag worden gebaseerd. De zelf-gemelde kosten kunnen op het niveau van het Kanaal slechts worden voorgelegd en worden vereist niet om de gegevens van de Campagne te hebben. Om de nauwkeurigste mogelijke kostenrapportage mogelijk te maken, worden zelf-gerapporteerde kosten opgehaald op basis van de markering &quot;channel_is_aggregatable_cost&quot;. De vraag die kostengegevens invoert wordt geschreven met de volgende logica: Als ad_provider = &quot;SelfReported&quot; dan channel_is_aggregatable_cost = waar, else campagne_is_aggregatable_cost = waar.

Binnen de context van dit model worden gegevens van het type Lead, [!UICONTROL Contact] , [!UICONTROL Account] en [!UICONTROL Opportunity] beschouwd als dimensionale gegevens en worden deze rechtstreeks gekoppeld aan de tabel met het aanraakpunt voor lead en Attribution.

### Valutaconversie {#currency-conversion}

De koersen in de tabel Conversierente geven de waarde aan die nodig is om een bedrag uit de bedrijfsvaluta om te zetten. Voor omrekening naar een valuta is een dubbele omrekening vereist, eerst van de oorspronkelijke valuta naar de bedrijfsvaluta en vervolgens van de bedrijfsvaluta naar de geselecteerde valuta. De eerste stap in deze keten in het model bestaat uit het toevoegen van twee kolommen met deze conversietarieven aan de tabellen met bedragen, Opportunity en Kosten. Deze stappen worden beschreven in de sectie Rijen toegevoegd in dit document. Omdat conversiekoersen niet statisch hoeven te zijn en kunnen worden gewijzigd met opgegeven datumbereiken, moeten alle berekeningen voor valutaomrekening op rijniveau worden uitgevoerd. De omrekening van de oorspronkelijke valuta naar de bedrijfsvaluta bestaat uit het delen van de waarde door de omrekeningskoers van de onderneming en vervolgens het vermenigvuldigen met de omrekeningskoers van het streefcijfer. De doelconversiekoers wordt bepaald door de geselecteerde valutaparameterwaarde.

* Zet de oorspronkelijke waarde om in de waarde van de bedrijfsvaluta / omrekeningskoers = waarde in de bedrijfsvaluta
* Omzetten van de waarde van de bedrijfswaarde in de geselecteerde valutawaarde in de bedrijfsvaluta `*` omrekeningskoers van de geselecteerde valuta = waarde in de geselecteerde valuta

![ zet de waarde van collectief in geselecteerde muntwaarde in collectieve munt ](assets/marketo-tableau-11.png) om

De omrekeningsmaatregelen in dit model vervangen de koers 1,0 als geen omrekeningskoers kan worden vastgesteld. Er zijn afzonderlijke maatregelen genomen om de valutawaarde voor de maatregel weer te geven en er wordt gewaarschuwd als een berekening meer dan één valutawaarde bevat (een waarde kan dus niet in de geselecteerde valuta worden omgezet). Deze maatstaven, Kostenvaluta en Winst Currency, zijn als tooltips opgenomen in elke visuele weergave die gegevens over kosten of opbrengsten weergeeft.

![ de maatregelen van de muntomzetting in dit model substitueren een waarde van 1.0 ](assets/marketo-tableau-12.png)

## Gegevensdefinities {#data-definitions}

Er zijn definities toegevoegd aan de [!DNL Tableau model] voor parameters, aangepaste kolommen en maatregelen.

![ de Definities zijn toegevoegd aan het model van Tableau voor parameters, douane ](assets/marketo-tableau-15.png)

Om definities voor kolommen te bekijken die direct uit [!DNL Snowflake] komen, zie de [ documentatie van het gegevenspakhuis ](/help/data-warehouse-schema.md){target="_blank"}.

## Verschillen tussen sjablonen en ontdekken {#discrepancies-between-templates-and-discover}

### Toegewezen inkomsten {#attributed-revenue}

Aanraakpunten met regelafstand en kenmerkaanraakpunten nemen dimensionale gegevens over van het originele aanraakpunt. Het rapportsjabloonmodel genereert alle overgeërfde dimensionale gegevens van de relatie tot het aanraakpunt, terwijl in het detectiemodel de dimensionale gegevens worden gedenormaliseerd naar de aanraakpuntrecords voor leads en Attributies. De totale toegerekende inkomsten of de toegerekende inkomsten uit pijpleidingen moeten tussen de twee verslagen worden afgestemd. Er kunnen echter discrepanties worden waargenomen wanneer de inkomsten worden uitgesplitst of gefilterd op basis van dimensionale gegevens (kanaal, subkanaal of campagne). Als de dimensionale opbrengstbedragen niet tussen het malplaatje en Discover aanpassen, is het waarschijnlijk er ontbrekende aanraakpuntverslagen in de reeks van het malplaatjerapport zijn. Dit gebeurt wanneer er een Lead- of Attribution Touchpoint-record is, maar er is geen overeenkomstige record in de Touchpoint-tabel in de gegevensset die in het rapport is geïmporteerd. Omdat deze tabellen op gewijzigde datum worden gefilterd, is het mogelijk dat de Touchpoint-record voor lead/Attribution later is gewijzigd dan de Touchpoint-record. Hierdoor is het aanraakpunt voor lead/Attribution in de gegevensset geïmporteerd terwijl de oorspronkelijke Touchpoint-record dat niet was. Als u dit probleem wilt verhelpen, vergroot u het gefilterde datumbereik voor de tabel met aanraakpunten of verwijder de datumbeperking samen.

>[!NOTE]
>
>Het aanraakpunt is een grote tabel. Houd daarom rekening met de voordelen van een vollediger gegevensset in vergelijking met de hoeveelheid gegevens die moet worden geïmporteerd.

### Kosten {#cost}

Kostenrapportage in de sjablonen is alleen beschikbaar op campagne- en kanaalniveau. Discover biedt echter aan dat voor sommige advertentieleveranciers (bijvoorbeeld creatief, trefwoord, en groepen, enz.) een lagere mate van granulariteit wordt gerapporteerd. Raadpleeg de sectie [!UICONTROL Data Model] van deze documentatie voor meer informatie over hoe de kostengegevens worden gemodelleerd in de sjablonen. Als het dimensiefilter in [!UICONTROL Discover] aan kanaal of campagne wordt geplaatst, zouden de kosten bij het kanaal, subchannel, en campagnespiegels tussen Discover en de rapportmalplaatjes omhoog moeten lijnen.

### ROI {#roi}

Aangezien het rendement van investeringen wordt berekend op basis van toegerekende opbrengsten en kosten, kunnen in het rendement van investeringen en om dezelfde redenen dezelfde verschillen optreden als in beide berekeningen, zoals in die afdelingen is opgemerkt.

### Aanraakpunten {#touchpoints}

Deze metriek, zoals aangetoond in de rapporteringsmalplaatjes, wordt niet weerspiegeld in Discover. Er is momenteel geen directe vergelijking mogelijk tussen beide.

### Webverkeer {#web-traffic}

Het gegevensmodel van het rapportmalplaatje normaliseert kanaal, subchannel, en campagnedimensionele gegevens via het verband tussen Zitting en Aanraakpunt. Dit is anders dan het gegevensmodel Discover, dat deze dimensies aan Zitting ontleedt. Wegens dit onderscheid, zouden de totale aantallen voor bezoeken en bezoekers tussen Discover en het rapporteringsmalplaatje moeten aanpassen, echter, zodra getoond of gefilterd door dimensie, worden deze aantallen niet verwacht om op te zetten. De reden hiervoor is dat de dimensionale gegevens in de sjabloon alleen beschikbaar zijn voor webgebeurtenissen die tot een aanraakpunt hebben geleid (dat wil zeggen, niet-anonieme gebeurtenissen). Voor meer details, verwijs het [ Model van Gegevens ](#data-model) sectie van deze documentatie.

Er kunnen kleine verschillen zijn in het totale aantal sitevormen tussen [!DNL Discover] en de sjabloon. Dit komt omdat het gegevensmodel in het rapporteringsmalplaatje dimensionele gegevens voor de Vorm van de Plaats via een verhouding aan Zitting en dan Aanraakpunt verkrijgt; er zijn een paar gevallen waar de gegevens van de plaatvorm geen gecorreleerde zitting hebben.

### Leads en accounts {#leads-and-accounts}

Dimensionele rapportage voor aangeroerde accounts kan enigszins verschillen tussen [!DNL Discover] en de sjabloon. Dit wordt opnieuw veroorzaakt door de dimensionale modellering die voortkomt uit de relatie tussen Touchpoint en Lead Touchpoint of Attribution Touchpoint. Verwijs naar de details die in de Attributed Revenue sectie worden geschetst voor meer details.

Alle aantallen lood in [!UICONTROL Discover] worden toegewezen lood tellingen, en in het rapporteringsmalplaatje is metrisch [!UICONTROL leads] aangeraakt. Er is dus geen rechtstreekse vergelijking mogelijk tussen de twee verslagen voor deze maatregel.

### Pad voor betrokkenheid {#engagement-path}

Er is geen directe vergelijking tussen het [!UICONTROL Engagement Path] -rapport in [!DNL Discover] en de sjabloon. Het rapport in [!DNL Discover] is gemodelleerd van het aanraakpunt terwijl het rapport in de sjabloon is gemodelleerd van het aanraakpunt. De sjabloon richt zich uitsluitend op kansen en de bijbehorende aanraakpunten in plaats van alle aanraakpuntgegevens weer te geven.

### Deal Velocity {#deal-velocity}

Er zou geen discrepantie tussen dit rapport in het malplaatje en de tegel van de Snelheid van de Overeenkomst op het dashboard van de Snelheid in Discover moeten zijn.
