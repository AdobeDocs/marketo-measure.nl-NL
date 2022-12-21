---
unique-page-id: 18874656
description: Filters - [!DNL Marketo Measure] - Productdocumentatie
title: Filters
exl-id: 249266c8-9ff5-4895-979c-4f377423d031
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '1290'
ht-degree: 0%

---

# Filters {#filters}

Meer informatie over de verschillende filters die u in Discover kunt gebruiken en over de manier waarop u deze kunt gebruiken.

>[!NOTE]
>
>De operatoren &quot;Komt overeen met een gebruikerskenmerk&quot; en &quot;komt overeen met (gevorderd)&quot; binnen uw Discover-filters zijn zuiver administratief en kunnen veilig worden genegeerd.

**Account-id**

_Gebruikt in: Op account gebaseerde marketing_

Selecteer of plak in een reeks Account ID&#39;s van CRM om de resultaten te filteren. Account-ID&#39;s bieden meer eenheid dan accountnaam, aangezien namen hetzelfde kunnen zijn.

**Accountnaam**

_Gebruikt in: Op account gebaseerde marketing_

Selecteer of plak in een reeks Accountnamen van CRM om de resultaten te filteren. Tekenreeksen kunnen duplicaten bevatten, dus het is mogelijk meerdere &quot;[!DNL Marketo Measure]&quot; accounts bijvoorbeeld. Als er in dit geval één account nodig is, gebruikt u in plaats daarvan het filter Account ID.

**Attributiemodel**

_Gebruikt in: Overzicht, marketinguitgaven, Ads ROI, Account based Marketing, Web Traffic, CMO, Betaalde media, Content Marketing, Passport_

Kies één enkel attributiemodel dat op de raad moet worden toegepast: Met Aanraking voor eerste aanraking, Aanraakvlak, U-vorm, W-vorm, Volledig pad of Aangepast model. Volledig pad en aangepast model zijn niet beschikbaar in alle lagen.

**Campagne**

_Gebruikt in: Overzicht, Groei, Adds ROI, Webverkeer, CMO, Betaalde Media, Content Marketing, Paspoort_

Filter het bord met één of meerdere campagnemenamen. Operatoren geven het filter extra flexibiliteit, zoals het gebruik van de operatoren &quot;contains&quot; of &quot;start met&quot;. Als er een kanaal- of subkanaalfilter is toegepast, bestaat de lijst met campagnes die worden weergegeven uit een subset van de toegepaste filters.

**Categorie 1-10**

_Gebruikt in: Overzicht, Groei, ADO ROI, CMO, Betaalde media, Content Marketing, Snelheid, Momentopname, Cohort Funnel, Paspoort_

Pas segmentfilters op het board toe met behulp van de Categorieën en Segmenten die u in het [!DNL Marketo Measure] Instellingen. De lijst met categorieën die u hebt gemaakt, wordt weergegeven in het menu met filters. Als er geen categorieën zijn ingesteld, staan er geen categoriefilters in het menu. Segmentcategorieën zijn niet in alle lagen beschikbaar en het aantal beschikbare categorieën varieert ook per niveau.

**Kanaal**

_Gebruikt in: Overzicht, groei, marketinguitgaven, Ads ROI, Web Traffic, CMO, Betaalde media, Content Marketing, Snelheid, Paspoort_

Filter het bord met één of meerdere kanalen. Operatoren geven het filter extra flexibiliteit, zoals het gebruik van de operatoren &quot;contains&quot; of &quot;start met&quot;. Nadat een kanaal is ingevoerd, worden de waarden in de filters Subkanaal en Campagne weergegeven op basis van het toegepaste subkanaalfilter.

**Cohort Stage**

_Gebruikt in: Cohort Funnel_

Selecteer het werkgebied waarvan u een code wilt weergeven. Het werkgebied dat u selecteert, wordt boven aan de trechter weergegeven, waarbij alle omzettingen van boven naar beneden doorlopen.

**Datum**

_Gebruikt in: Overzicht, groei, marketinguitgaven, Ads ROI, Account Based Marketing, Web Traffic, CMO, Betaalde media, Content Marketing, Snelheid, Snapshot, Cohort Funnel, Passport_

Selecteer een datumbereik om de gegevens in de tekengebieden te filteren met gebruik van flexibele datumoperatoren zoals &quot;bevindt zich in het bereik&quot;, &quot;bevindt zich in het jaar&quot; of &quot;is voor&quot; bijvoorbeeld. De uitzondering is Momentopname, waar u één enkele datum zult selecteren om een momentopname van de gegevens te bekijken.

**Datumtype**

_Gebruikt in: Overzicht, groei, marketinguitgaven, Ads ROI, Account based Marketing, Web Traffic, CMO, Betaalde media, Content Marketing, Passport_

Kies het type datum dat u wilt gebruiken, gekoppeld aan het filter Datum. Het standaarddatumtype varieert per board. De Datum van het aanraakpunt verwijst naar de datum dat de marketing activiteit plaatsvond, Gemaakt Datum is de datum dat het Lood of Contact of de Kans in CRM werd gecreeerd, en de Dichte Datum is de datum dat de Kans werd gesloten.

**Dimension**

_Gebruikt in: Betaalde media_

Dimension is vergelijkbaar met de functie Groep op, behalve dat deze op een iets andere manier wordt gebruikt op de Paid Media-board. In plaats van een diagram te stapelen, wijzigt Dimension de regels uit het overzichtsdiagram en het regelafstandobject in de tabellen.

![](assets/1.png)

Standaard is Dimension ingesteld op Subkanaal en u kunt deze wijzigen in:

* Geen: Hiermee worden alle items samen weergegeven zonder onderbreking
* Kanaal: Hier worden de gegevens weergegeven per marketingkanaal
* Subkanaal: Hiermee geeft u de gegevens weer op basis van het marketingsubkanaal
* Campagne: Hier worden de gegevens per campagne weergegeven
* Account: Hier worden de gegevens per account weergegeven. Van toepassing op [!DNL AdWords], [!DNL Bing], en [!DNL Facebook].
* Advertentiegroep: Hiermee geeft u de gegevens op basis van een advertentiegroep weer. Van toepassing op [!DNL AdWords], [!DNL Bing], en [!DNL Facebook].
* Advertentie: Hiermee geeft u de gegevens op advertentie weer. Is van toepassing op dubbelklik-advertenties. Als Dubbelklik niet wordt gebruikt, worden er geen resultaten weergegeven
* Adverteerder: Hier worden de gegevens weergegeven door adverteerder. Is van toepassing op de Dubbleclick-adverteerder. Als Doubleclick niet wordt gebruikt, worden er geen resultaten weergegeven
* Creatief: Hier worden de gegevens weergegeven op creatief. Van toepassing op [!DNL AdWords], [!DNL Bing], en [!DNL Facebook].
* Trefwoord: Hiermee geeft u de gegevens op trefwoord weer. Van toepassing op [!DNL AdWords], [!DNL Bing], en [!DNL Facebook].
* Plaatsing: Hier worden de gegevens weergegeven op plaatsing. Is van toepassing op Dubbleclick-plaatsingen. Als Dubbleclick niet wordt gebruikt, worden er geen resultaten weergegeven.
* Site: Hier worden de gegevens per site weergegeven. Is van toepassing op Dubbleclick-sites. Als Dubbleclick niet wordt gebruikt, worden er geen resultaten weergegeven

**Groeperen op**

_Gebruikt in: Overzicht, groei, marketinguitgaven, accountgebaseerde marketing, webverkeer, GMO_

Hiermee past u grafieken aan om de dimensie te wijzigen die wordt gestapeld en gegroepeerd. Standaard is Groeperen via ingesteld op Kanaal en kan deze worden gewijzigd in:

* Geen: Hiermee worden alle items samen weergegeven zonder onderbreking
* Kanaal: Hiermee groepeert u de gegevens per marketingkanaal
* Subkanaal: Groepeert de gegevens door subkanaal op de markt te brengen
* Campagne: Hiermee groepeert u de gegevens op campagne
* Account: Hiermee groepeert u de gegevens per account. Van toepassing op [!DNL AdWords], [!DNL Bing], en [!DNL Facebook].
* Advertentiegroep: Hiermee groepeert u de gegevens op ad-groep. Van toepassing op [!DNL AdWords], [!DNL Bing], en [!DNL Facebook].
* Advertentie: Hiermee groepeert u de gegevens op advertentie. Is van toepassing op dubbelklik-advertenties. Als Dubbelklik niet wordt gebruikt, worden er geen resultaten weergegeven
* Adverteerder: Hiermee groepeert u de gegevens door adverteerder. Is van toepassing op de Dubbleclick-adverteerder. Als Doubleclick niet wordt gebruikt, worden er geen resultaten weergegeven
* Creatief: Hiermee groepeert u de gegevens op creatief. Van toepassing op [!DNL AdWords], [!DNL Bing], en [!DNL Facebook].
* Trefwoord: Hiermee groepeert u de gegevens op trefwoord. Van toepassing op [!DNL AdWords], [!DNL Bing], en [!DNL Facebook].
* Plaatsing: Hiermee groepeert u de gegevens door plaatsing. Is van toepassing op Dubbleclick-plaatsingen. Als Dubbleclick niet wordt gebruikt, worden er geen resultaten weergegeven.
* Site: Hiermee groepeert u de gegevens per site. Is van toepassing op Dubbleclick-sites. Als Dubbleclick niet wordt gebruikt, worden er geen resultaten weergegeven

![](assets/2.png)

**Openingspagina**

_Gebruikt in: Inhoud marketing_

Maak kennis met de prestaties van één landingspagina of landingspagina&#39;s met een bepaald woord zoals &quot;blog&quot;.

**Metrisch**

_Gebruikt in: Overzicht, Webverkeer, GMO, Betaalde media, Inhoud marketing_

Er zijn twee verschillende metrische kiezers die voor verschillende borden worden gebruikt. De metrische kiezer wijzigt de maatregel op een grafiek, zodat u kunt schakelen tussen bijvoorbeeld het bekijken van omzet of het uitgeven of het drukken.

Op het Overzicht en de Borden van GMO, is er een verkorte lijst van waarden met betrekking tot ROI metriek:

* Ontvangsten
* Spend
* Overeenkomsten
* Opbrengst pijpleiding
* Kansen
* Contactpersonen
* Leads

Op het Verkeer van het Web, Betaalde Media, en de Marketingboards van de Inhoud, is er een langere lijst van waarden met betrekking tot zowel ROI als tintmetriek:

* Ontvangsten
* Spend
* Overeenkomsten
* Opbrengst pijpleiding
* Kansen
* Contactpersonen
* Leads
* Klikken
* indrukken
* Bezoeken
* Unieke bezoeken
* Paginaweergaven
* Forms

**Werkgebied**

_Gebruikt in: Snelheid_

Standaard geeft het snelheidsbord de tijden voor alle fasen weer, maar als u wilt inboren in een specifiek werkgebied, selecteert u het werkgebied met het werkgebiedfilter.

**Subkanaal**

_Gebruikt in: Overzicht, groei, marketinguitgaven, Ads ROI, Web Traffic, CMO, Betaalde media, Content Marketing, Passport_

Filter het bord met één of meerdere subkanalen. Operatoren geven het filter extra flexibiliteit, zoals het gebruik van de operatoren &quot;contains&quot; of &quot;start met&quot;. Als een filter Kanaal is toegepast, zal de lijst van subkanalen die verschijnen een ondergroep van de toegepaste filters zijn. Nadat een subkanaal is ingevoerd, worden de waarden in de Campagnefilters weergegeven op basis van het toegepaste subkanaalfilter.

**URL**

_Gebruikt in: Webverkeer_

Boor in het verkeer van één enkele URL, of misschien URLs die een bepaald woord zoals &quot;product&quot;bevatten.

**Won**

_Gebruikt in: Snelheid_

Door gebrek, rapporteert het Comité van Snelheid over slechts gesloten won kansen, maar pas dit filter aan om de snelheid voor of gesloten won of gesloten verloren kansen te bekijken.
