---
description: '[!DNL Marketo Measure] Rapportsjabloon - Power BI -  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] Rapportsjabloon - Power BI'
exl-id: c296b8f9-4033-4723-9a71-63a458640d27
feature: Reporting
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '2526'
ht-degree: 0%

---

# [!DNL Marketo Measure] Rapportsjabloon - Power BI {#marketo-measure-report-template-power-bi}

## Aan de slag {#getting-started}

U kunt tot het het rapportmalplaatje van Power BI [ hier ](https://github.com/adobe/Marketo-Measure-BI-Templates){target="_blank"} toegang hebben.

Open het Adobe [!DNL Marketo Measure] Reporting Template Power BI-bestand.

![](assets/marketo-bi-1.png)

U kunt uw specifieke server-, vakantie- en schemagegevens vinden in de gebruikersinterface van [!DNL Marketo Measure] op de informatiepagina van [!DNL Data Warehouse] . De instructies voor hoe te om van deze pagina de plaats te bepalen zijn gedetailleerd [ hier ](/help/marketo-measure-data-warehouse/data-warehouse-access-reader-account.md){target="_blank"}.

De parameters QueryFilterStartDate en QueryFilterEndDate worden gebruikt om de hoeveelheid geïmporteerde gegevens te beperken. Deze parameters moeten de SQL-indeling hebben, zoals ze worden gebruikt in de query&#39;s die naar [!DNL Snowflake] worden verzonden. Als u gegevens bijvoorbeeld wilt beperken tot de afgelopen twee jaar, is de QueryFilterStartDate `dateadd` (year,-2,current_date()). Deze parameters worden vergeleken met datetime gegevenstypen, zodat wordt geadviseerd `dateadd` (dag,1,current_date()) voor QueryFilterEndDate te gebruiken om alle gegevens aan de huidige tijd terug te keren.

## Gegevensverbinding {#data-connection}

De parameters die bij het openen van het bestand worden ingevoerd, worden gebruikt om native query&#39;s te structureren die tabellen importeren uit het gegevenspakhuis. U moet nog steeds een gegevensverbinding met uw [!DNL Snowflake] -instantie instellen. Voor dit, hebt u de zelfde namen van de Server en van het Pakhuis samen met uw Gebruikersnaam en Wachtwoord nodig. De details op waar te om uw Gebruikersnaam te vinden en uw Wachtwoord terug te stellen, indien nodig, worden gedocumenteerd [ hier ](/help/marketo-measure-data-warehouse/data-warehouse-access-reader-account.md){target="_blank"}.

## Gegevens importeren {#data-import}

Om rapportprestaties te verbeteren, en uit transformatiemogelijkheden in de Vraag van de Macht voordeel te halen, opstelling dit malplaatje gebruikend de de opslagmethode van de invoer.

### Zoekparameters {#query-parameters}

Om de gegevens te beperken die in het model worden ingevoerd, wordt elke lijst opstelling gebruikend een inheemse vraag als bron. Voor native query&#39;s is goedkeuring vereist om te worden uitgevoerd. U moet op uitvoering klikken voor elke query. Deze stap is slechts nodig de eerste keer dat de vragen in werking worden gesteld, of als de parameters veranderen.

![](assets/marketo-bi-2.png)

Alle query&#39;s filteren verwijderde rijen en de [!UICONTROL facts] -tabellen zijn ingesteld op filteren op rijen met een gewijzigde datum tussen de begin- en einddatum die als parameters zijn ingevoerd.

>[!NOTE]
>
>Omdat de datumfilters worden toegepast op de gewijzigde datum van een rij, is voorzichtigheid geboden bij het melden van datums die buiten het beperkte datumbereik vallen. Het gewijzigde datumbereik is bijvoorbeeld beperkt tot de afgelopen twee jaar. Dit kan een gebeurtenis omvatten met een datum van een gebeurtenis van drie jaar geleden, maar die onlangs is gewijzigd. De rapportage over gebeurtenissen van drie jaar geleden retourneert echter onvolledige resultaten, aangezien niet alle rijen binnen de termijn van twee jaar zijn gewijzigd.

![](assets/marketo-bi-3.png)

De volgende lijsten worden behandeld als feitenlijsten; de datumgrenzen op gewijzigde datum zijn toegevoegd aan deze vragen.

* Activiteit
* Aanraakpunt
* Aanraakpunt lead
* Attributie-aanraakpunt
* Kosten
* Siteformulier
* Sessie
* Campagnelid
* Taak
* Gebeurtenis
* Werkgebiedovergang voor lead/contact
* Overgang opportunity-werkgebied

De volgende lijsten worden behandeld als afmetingslijsten; geen datumgrenzen worden geplaatst voor deze vragen.

* Account
* Campaign
* Contact
* Conversiesnelheid
* Kans
* Lood
* Werkgebied
* Kanaal

## Gegevenstransformaties {#data-transformations}

Er zijn een paar transformaties toegepast op de gegevens in Power Query. Als u de specifieke transformaties voor een tabel wilt weergeven, opent u Power Query, navigeert u naar een tabel en noteert u de toegepaste stappen links in het venster. Enkele specifieke transformaties worden hieronder beschreven.

![](assets/marketo-bi-6.png)

### Verwijderde kolommen {#removed-columns}

Om het gegevensmodel te vereenvoudigen en overtollige en onnodige gegevens te verwijderen, hebben wij het aantal kolommen verminderd die in Power BI van de originele [!DNL Snowflake] lijst worden ingevoerd. Verwijderde kolommen bevatten onnodige externe sleutels, gedenormaliseerde dimensionale gegevens die beter kunnen worden toegepast via relaties met andere tabellen in het model, auditkolommen en velden die worden gebruikt voor interne [!DNL Marketo Measure] -verwerking. U kunt kolommen toevoegen of verwijderen zoals vereist voor uw bedrijfsbehoeften. Navigeer naar de stap &quot;Verwijderd overige kolommen&quot; na de stap &quot;Source&quot; in een tabel, klik op het tandwielpictogram en werk de geselecteerde kolommen bij in de opgegeven lijst.

>[!NOTE]
>
>* Wees voorzichtig wanneer u extra waarden voor vreemde sleutels toevoegt. Power BI is vaak ingesteld op automatisch detecteren van relaties in het model en het toevoegen van waarden voor externe sleutels kan ongewenste koppelingen tussen tabellen tot gevolg hebben en/of bestaande relaties uitschakelen.
>
>* De meeste tabellen in het [!DNL Marketo Measure] -gegevenspakhuis bevatten gedenormaliseerde dimensionale gegevens. We hebben er alles aan gedaan om het model in Power BI zoveel mogelijk te normaliseren en op te schonen om de prestaties en gegevensnauwkeurigheid te verbeteren. Wees voorzichtig met het opnemen van eventuele aanvullende gedenormaliseerde velden in feitentabellen, dit kan het filteren van dimensies in verschillende tabellen afbreken en kan ook leiden tot onjuiste rapportage.


![](assets/marketo-bi-7.png)

### Naam van kolommen wijzigen {#renamed-columns}

Tabellen en kolommen hebben een andere naam gekregen om ze gebruiksvriendelijker te maken en de naamgevingsconventies te standaardiseren. Als u de wijzigingen in de kolomnaam wilt weergeven, navigeert u naar de stap &#39;Kolommen hernoemd&#39; na de stap &#39;Overige kolommen verwijderd&#39; in een tabel.

![](assets/marketo-bi-5.png)

### Hernoemde segmenten {#renamed-segments}

Aangezien de segmentnamen aanpasbaar zijn, hebben zij generische kolomnamen in het de gegevenspakhuis van Snowflake. [!DNL BIZ_SEGMENT_NAMES] is een toewijzingstabel waarin de generieke segmentnaam en de toegewezen aangepaste segmentnaam worden vermeld, die worden gedefinieerd in de segmentsectie in de [!DNL Marketo Measure] -gebruikersinterface. De tabel Segmentnaam wordt gebruikt om de naam te wijzigen van de segmentkolommen in de tabellen Aanraakpunt lead en Kenmerk. Als er geen aangepast segment bestaat, blijft de generieke segmentnaam behouden.

![](assets/marketo-bi-4.png)

### Hoofdlettergevoelige ID-omzetting {#case-sensitive-id-conversion}

[!DNL Marketo Measure] -gegevens hebben een aantal tabellen waarin de waarden voor de primaire sleutel (id) hoofdlettergevoelig zijn, namelijk Touchpoint en Campagne. De gegevensengine die de Power BI-modelleringslaag aandrijft, is niet hoofdlettergevoelig en resulteert dus in &#39;dubbele&#39; id-waarden. Om de hoofdlettergevoeligheid van deze sleutelwaarden te behouden, hebben wij transformatiestappen uitgevoerd die onzichtbare karakters aan kleine hoofdletters vastmaken, die de uniciteit van identiteitskaart bewaren wanneer geëvalueerd in de laag van de gegevensmotor. Meer details over de kwestie en de gedetailleerde stappen op de methode wij hebben gewerkt kunnen [ hier ] worden gevonden (https://blog.crossjoin.co.uk/2019
/10/06/power-bi-and-case-sensitive/) {target="_blank"}. Deze hoofdlettergevoelige id-waarden worden gelabeld als &quot;Id&#39;s samenvoegen&quot; en worden gebruikt als verbindingssleutels in de relatielaag. We hebben de samenvoegings-id&#39;s uit de rapportlaag verborgen, zodat de oorspronkelijke id-waarden zichtbaar blijven voor gebruik in de rapportage, aangezien onzichtbare tekens de cut kunnen beïnvloeden
/paste functies en het filtreren.

![](assets/marketo-bi-8.png)

![](assets/marketo-bi-11.png)

### Rijen toegevoegd {#rows-added}

Om de mogelijkheden van de muntomzetting aan de berekeningen in het model toe te voegen, hebben wij een collectieve kolom van de omrekeningskoers aan zowel de lijsten van de Mogelijkheid als van de Kosten toegevoegd. De waarde in deze kolom wordt toegevoegd op rijniveau en door zich bij de lijst van het Tarief van de Omzetting op zowel datum als muntidentiteitskaart aan te sluiten geëvalueerd. Voor meer details op hoe de muntomzetting in dit model werkt, zie de [ sectie van de Omzetting van de Valuta 0} {in deze documentatie.](#currency-conversion)

![](assets/marketo-bi-10.png)

De in [!DNL Snowflake] opgeslagen tabel met conversiesnelheid bevat een datumbereik voor elke conversie. Power BI staat geen samenvoeging van criteria op een berekening toe (dat wil zeggen tussen een datumbereik). Om op datum toe te treden, hebben wij stappen aan de lijst van het Tarief van de Omzetting toegevoegd om de rijen uit te breiden zodat is er één rij voor elke datum in de waaier van de omzettingsdatum.

![](assets/marketo-bi-9.png)

## Gegevensmodel {#data-model}

Klik op de onderstaande afbeelding voor de volledige versie.

[![](assets/marketo-bi-12.png)](/help/bi-report-templates/assets/power-model-1.png){target="_blank"}

### Relaties en gegevensstroom {#relationships-and-data-flow}

Gebeurtenisgegevens die worden gebruikt voor het maken van aanraakpunten, worden opgeslagen in de tabellen [!UICONTROL Session] , [!UICONTROL Task] , [!UICONTROL Event] , [!UICONTROL Activity] en Campagne Member. Deze gebeurtenistabellen worden via de respectievelijke id&#39;s aan de tabel met aanraakpunten toegevoegd en als de gebeurtenis tot een aanraakpunt heeft geleid, worden de gegevens in de tabel met aanraakpunten opgeslagen.

Aanraakpunten voor leads en kenmerkaanraakpunten worden in hun eigen tabellen opgeslagen, met een koppeling naar de aanraakpunttabel. De meeste dimensionale gegevens voor aanraakpunten Lead en Attribution worden afkomstig van de koppeling naar het overeenkomstige aanraakpunt.

In dit model zijn de afmetingen voor Campagne en Kanaal gekoppeld aan het aanraakpunt. Alle rapportage over deze afmetingen vindt dus plaats via deze koppeling. Dit betekent dat dimensionale rapportage over gebeurtenisgegevens mogelijk onvolledig is. Veel gebeurtenissen hebben namelijk pas koppelingen naar deze afmetingen nadat ze zijn verwerkt tot aanraakpunten. Opmerking: sommige gebeurtenissen, zoals sessies, hebben directe koppelingen naar de afmetingen Campagne en Kanaal. Als het rapporteren op het niveau van de Zitting over deze dimensies wordt gewenst, adviseert men dat een afzonderlijk gegevensmodel voor dit doel wordt gecreeerd.

Kostengegevens worden op verschillende aggregatieniveaus opgeslagen in de tabel Kostprijs van het [!DNL Snowflake] -gegevenspakhuis. Voor alle advertentieleveranciers, kunnen de het niveaugegevens van de Campagne tot het niveau van het Kanaal worden uitgebreid. Om deze reden, trekt dit model kostengegevens die op de &quot;campagne_is_aggregatable_cost&quot;vlag worden gebaseerd. De zelf-gemelde kosten kunnen op het niveau van het Kanaal slechts worden voorgelegd, en worden vereist niet om de gegevens van de Campagne te hebben. Om de nauwkeurigste mogelijke kostenrapportage mogelijk te maken, worden zelf-gerapporteerde kosten opgehaald op basis van de markering &quot;channel_is_aggregatable_cost&quot;. De vraag die kostengegevens invoert wordt geschreven met de volgende logica: Als ad_provider = &quot;SelfReported&quot; dan channel_is_aggregatable_cost = waar, else campagne_is_aggregatable_cost = waar.

De gegevens van de kosten en de gegevens van het Aanraakpunt hebben sommige gemeenschappelijke dimensies, zodat hebben beide feitenlijsten verhoudingen met de de afmetingslijsten van de Campagne en van het Kanaal.

In de context van dit model worden [!UICONTROL Lead] -, [!UICONTROL Contact] -, [!UICONTROL Account] - en [!UICONTROL Opportunity] -gegevens beschouwd als dimensionale gegevens en rechtstreeks gekoppeld aan de [!UICONTROL Lead] Touchpoint- en [!UICONTROL Attribution] -aanraakpunttabellen.

### Toegevoegde tabellen {#added-tables}

**Datum**

Omdat Power BI voor verhoudingen tussen lijsten op één kolom slechts toestaat, werd een de dimensietabel van de Datum toegevoegd om te vergemakkelijken toetreedt noodzakelijk tussen de lijsten die bedragen (Kans en Kosten) en de lijst van het Tarief van de Omzetting bevatten. Zie het gedeelte Valutaconversie voor meer informatie over hoe valutaomrekeningen in dit model worden berekend.

**Maatregelen**

Alle maatregelen zijn toegevoegd aan een specifieke tabel voor maatregelen. Het is niet verbonden met het model maar dient als één enkele plaats om alle maatregelen op te slaan, voor gemak van gebruik.

**Model van de Attributie**

Er is een aparte tabel toegevoegd waarin de namen van de attributiemodellen worden opgeslagen. Deze tabel wordt gebruikt om filters te maken waarmee de gebruiker kan schakelen tussen toewijzingsmodellen voor de berekening van toegewezen opbrengsten.

### Valutaconversie {#currency-conversion}

De koersen in de tabel Conversierente geven de waarde aan die nodig is om een bedrag uit de bedrijfsvaluta om te zetten. Voor omrekening naar een valuta is een dubbele omrekening vereist, eerst van de oorspronkelijke valuta naar de bedrijfsvaluta en vervolgens van de bedrijfsvaluta naar de geselecteerde valuta. De eerste stap in deze keten in het model is het toevoegen van een kolom met de omrekeningskoers aan bedrijven aan de lijsten met bedragen, Opportunity en Kosten. Deze stappen worden gedetailleerd beschreven in de rij Toegevoegde kopbal van de sectie van de Transformaties van Gegevens in dit document. Omrekening van de oorspronkelijke valuta in de bedrijfsvaluta bestaat uit het delen van de waarde door deze toegevoegde kolom. De volgende stap bestaat uit het vermenigvuldigen van de waarde van de bedrijfsvaluta met de koers in de tabel Conversion Rate die overeenkomt met de geselecteerde valuta.

* Zet de oorspronkelijke waarde om in de waarde van de bedrijfsvaluta / omrekeningskoers = waarde in de bedrijfsvaluta
* Omzetten van de waarde van de bedrijfswaarde in de geselecteerde valutawaarde in de bedrijfsvaluta `*` omrekeningskoers van de geselecteerde valuta = waarde in de geselecteerde valuta

Omdat conversiekoersen niet statisch hoeven te zijn en kunnen worden gewijzigd met opgegeven datumbereiken, moeten alle berekeningen voor valutaomrekening op rijniveau worden uitgevoerd. Aangezien de conversiekoersen betrekking hebben op een specifiek datumbereik, moet de opzoekberekening worden uitgevoerd binnen de DAX van de maatregel, zodat de relatie kan worden gedefinieerd op zowel de valutacode als de datum.

De omrekeningsmaatregelen in dit model vervangen de koers 1,0 als geen omrekeningskoers kan worden vastgesteld. Er zijn afzonderlijke maatregelen genomen om de valutawaarde voor de maatregel weer te geven en er wordt gewaarschuwd als een berekening meer dan één valutawaarde bevat (een waarde kan dus niet in de geselecteerde valuta worden omgezet).

![](assets/marketo-bi-13.png)

## Gegevensdefinities {#data-definitions}

Er zijn definities toegevoegd aan het Power BI-model voor tabellen, aangepaste kolommen en maatregelen.

![](assets/marketo-bi-15.png)

![](assets/marketo-bi-16.png)

![](assets/marketo-bi-14.png)

Om definities voor kolommen te bekijken die direct uit [!DNL Snowflake] komen, zie de [ documentatie van het gegevenspakhuis ](/help/marketo-measure-data-warehouse/data-warehouse-schema.md){target="_blank"}

## Verschillen tussen sjablonen en ontdekken {#discrepancies-between-templates-and-discover}

### Toegewezen inkomsten {#attributed-revenue}

Aanraakpunten met regelafstand en kenmerkaanraakpunten nemen dimensionale gegevens over van het originele aanraakpunt. Het rapportsjabloonmodel genereert alle overgeërfde dimensionale gegevens van de relatie tot het aanraakpunt, terwijl in het detectiemodel de dimensionale gegevens worden gedenormaliseerd naar de aanraakpuntrecords voor leads en Attributies. De totale toegerekende inkomsten of de toegerekende inkomsten uit pijpleidingen moeten tussen de twee verslagen worden afgestemd. Er kunnen echter discrepanties worden waargenomen wanneer de inkomsten worden uitgesplitst of gefilterd op basis van dimensionale gegevens (kanaal, subkanaal of campagne). Als de dimensionale opbrengstbedragen niet tussen het malplaatje en Discover aanpassen, is het waarschijnlijk er ontbrekende aanraakpuntverslagen in de reeks van het malplaatjerapport zijn. Dit gebeurt wanneer er een Lead- of Attribution Touchpoint-record is, maar er is geen overeenkomstige record in de Touchpoint-tabel in de gegevensset die in het rapport is geïmporteerd. Omdat deze tabellen op gewijzigde datum worden gefilterd, is het mogelijk dat de Touchpoint-record voor lead/Attribution later is gewijzigd dan de Touchpoint-record. Hierdoor is het aanraakpunt voor lead/Attribution in de gegevensset geïmporteerd terwijl de oorspronkelijke Touchpoint-record dat niet was. Als u dit probleem wilt verhelpen, vergroot u het gefilterde datumbereik voor de tabel met aanraakpunten of verwijder de datumbeperking samen. Opmerking: het aanraakpunt is een grote tabel. Houd daarom rekening met de voordelen van een vollediger gegevensset ten opzichte van de hoeveelheid gegevens die moet worden geïmporteerd.

### Kosten {#cost}

Kostenrapportage in de sjablonen is alleen beschikbaar op campagne- en kanaalniveau. Discover biedt echter aan dat voor sommige advertentieleveranciers (creatief, trefwoord, groepen, enzovoort) een lagere mate van granulariteit wordt gerapporteerd. Raadpleeg de sectie Gegevensmodel van deze documentatie voor meer informatie over hoe de kostengegevens in de sjablonen zijn gemodelleerd. Als het dimensiefilter in [!UICONTROL Discover] aan kanaal of campagne wordt geplaatst, zouden de kosten bij het kanaal, subchannel, en campagnespiegels tussen Discover en de rapportmalplaatjes omhoog moeten lijnen.

### ROI {#roi}

Aangezien het rendement van investeringen wordt berekend op basis van toegerekende opbrengsten en kosten, kunnen in het rendement van investeringen en om dezelfde redenen dezelfde verschillen optreden als in beide berekeningen, zoals in die afdelingen is opgemerkt.

### Aanraakpunten {#touchpoints}

Deze metriek, zoals aangetoond in de rapporteringsmalplaatjes, wordt niet weerspiegeld in Discover. Er is momenteel geen directe vergelijking mogelijk tussen beide.

### Webverkeer {#web-traffic}

Het gegevensmodel van het rapportmalplaatje normaliseert kanaal, subchannel, en campagnedimensionele gegevens via het verband tussen Zitting en Aanraakpunt. Dit is anders dan het gegevensmodel Discover, dat deze dimensies aan Zitting ontleedt. Wegens dit onderscheid, zouden de totale aantallen voor bezoeken en bezoekers tussen Discover en het rapporteringsmalplaatje moeten aanpassen, echter, zodra getoond of gefilterd door dimensie, worden deze aantallen niet verwacht om op te zetten. De reden hiervoor is dat de dimensionale gegevens in de sjabloon alleen beschikbaar zijn voor webgebeurtenissen die tot een aanraakpunt hebben geleid (d.w.z. niet-anonieme gebeurtenissen). Voor meer details, verwijs het [ Model van Gegevens ](#data-model) sectie van deze documentatie.

Er kunnen kleine verschillen zijn in het totale aantal sitevormen tussen [!DNL Discover] en de sjabloon. Dit komt omdat het gegevensmodel in het rapporteringsmalplaatje dimensionele gegevens voor de Vorm van de Plaats via een verhouding aan Zitting en dan Aanraakpunt verkrijgt; er zijn een paar gevallen waar de gegevens van de plaatvorm geen gecorreleerde zitting hebben.

### Leads en accounts {#leads-and-accounts}

Dimensionele rapportage voor aangeroerde accounts kan enigszins verschillen tussen Discover en de sjabloon. Dit wordt opnieuw veroorzaakt door de dimensionale modellering die voortkomt uit de relatie tussen Touchpoint en Lead Touchpoint of Attribution Touchpoint. Verwijs naar de details die in de Attributed Revenue sectie worden geschetst voor meer details.

Alle loodtellingen in Discover worden toegewezen loodtellingen, en in het rapportagesjabloon wordt de metrische waarde afgeleid. Er is dus geen rechtstreekse vergelijking mogelijk tussen de twee verslagen voor deze maatregel.

### Pad voor betrokkenheid {#engagement-path}

Er is geen directe vergelijking tussen het [!UICONTROL Engagement Path] -rapport in Discover en de sjabloon. Het rapport in [!DNL Discover] is gemodelleerd van het aanraakpunt terwijl het rapport in de sjabloon is gemodelleerd van het aanraakpunt. De sjabloon richt zich uitsluitend op kansen en de bijbehorende aanraakpunten in plaats van alle aanraakpuntgegevens weer te geven.

### Deal Velocity {#deal-velocity}

Er zou geen discrepantie tussen dit rapport in het malplaatje en de tegel van de Snelheid van de Overeenkomst op het dashboard van de Snelheid in Discover moeten zijn.
