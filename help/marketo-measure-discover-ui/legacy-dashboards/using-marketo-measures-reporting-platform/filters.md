---
unique-page-id: 18874656
description: Filters - [!DNL Marketo Measure] - Productdocumentatie
title: Filters
exl-id: 249266c8-9ff5-4895-979c-4f377423d031
feature: Reporting
source-git-commit: e24e01a03218252c06c9a776e0519afbddbe2b8c
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

_Gebruikt in: Overzicht, Marketing, Ads ROI, Account Based Marketing, Web Traffic, CMO, Betaalde media, Content Marketing, Passport_

Kies één enkel attributiemodel dat op de plank moet worden toegepast: Eerste aanraking, Aanraakvlak lood, U-Vormd, W-Vormd, Volledig pad of Aangepast model. Volledig pad en aangepast model zijn niet beschikbaar in alle lagen.

**Campagne**

_Gebruikt in: Overzicht, Groei, Ads ROI, Webverkeer, CMO, Betaalde Media, Content Marketing, Paspoort_

Filter het bord met één of meerdere campagnemenamen. Operatoren geven het filter extra flexibiliteit, zoals het gebruik van de operatoren &quot;contains&quot; of &quot;start met&quot;. Als er een kanaal- of subkanaalfilter is toegepast, bestaat de lijst met campagnes die worden weergegeven uit een subset van de toegepaste filters.

**Categorie 1-10**

_Gebruikt in: Overzicht, Groei, Ads ROI, CMO, Betaalde media, Content Marketing, Snelheid, Momentopname, Cohort Funnel, Passport_

Pas segmentfilters op het board toe met behulp van de Categorieën en Segmenten die u in het [!DNL Marketo Measure] Instellingen. De lijst met categorieën die u hebt gemaakt, wordt weergegeven in het menu met filters. Als er geen categorieën zijn ingesteld, staan er geen categoriefilters in het menu. Segmentcategorieën zijn niet in alle lagen beschikbaar en het aantal beschikbare categorieën varieert ook per niveau.

**Kanaal**

_Gebruikt in: Overzicht, Groei, Marketing, Adds ROI, Web Traffic, CMO, Betaalde Media, Content Marketing, Snelheid, Paspoort_

Filter het bord met één of meerdere kanalen. Operatoren geven het filter extra flexibiliteit, zoals het gebruik van de operatoren &quot;contains&quot; of &quot;start met&quot;. Nadat een kanaal is ingevoerd, worden de waarden in de filters Subkanaal en Campagne weergegeven op basis van het toegepaste subkanaalfilter.

**Cohort Stage**

_Gebruikt in: Cohort Funnel_

Selecteer het werkgebied waarvan u een code wilt weergeven. Het werkgebied dat u selecteert, wordt boven aan de trechter weergegeven, waarbij alle omzettingen van boven naar beneden doorlopen.

**Datum**

_Gebruikt in: Overzicht, Groei, Marketingbestedingen, Advertentierendement, Account based Marketing, Web Traffic, CMO, Betaalde Media, Content Marketing, Snelheid, Momentopname, Cohort Funnel, Paspoort_

Selecteer een datumbereik om de gegevens in de tekengebieden te filteren met gebruik van flexibele datumoperatoren zoals &quot;bevindt zich in het bereik&quot;, &quot;bevindt zich in het jaar&quot; of &quot;is voor&quot; bijvoorbeeld. De uitzondering is Momentopname, waar u één enkele datum zult selecteren om een momentopname van de gegevens te bekijken.

**Datumtype**

_Gebruikt in: Overzicht, Groei, Marketing, Adds ROI, Account Based Marketing, Web Traffic, CMO, Betaalde Media, Content Marketing, Passport_

Kies het type datum dat u wilt gebruiken, gekoppeld aan het filter Datum. Het standaarddatumtype varieert per board. De Datum van het aanraakpunt verwijst naar de datum dat de marketing activiteit plaatsvond, Gemaakt Datum is de datum dat het Lood of Contact of de Kans in CRM werd gecreeerd, en de Dichte Datum is de datum dat de Kans werd gesloten.

**Dimension**

_Gebruikt in: Betaalde media_

Dimension is vergelijkbaar met de functie Groeperen op, behalve dat het op een iets andere manier wordt gebruikt op de Paid Media-board. In plaats van een grafiek te stapelen, verandert het Dimension de lijnen van de grafiek van het Overzicht evenals het belangrijke voorwerp in de lijsten.

![](assets/1.png)

Standaard is Dimension ingesteld op Subkanaal en u kunt dit wijzigen in:

* Geen: alles wordt samen weergegeven zonder onderbreking
* Kanaal: geeft de gegevens weer per marketingkanaal
* Subkanaal: geeft de gegevens weer op basis van het subkanaal voor marketing
* Campagne: geeft de gegevens weer op campagne
* Account: geeft de gegevens per account weer. Van toepassing op [!DNL AdWords], [!DNL Bing], en [!DNL Facebook].
* Advertentiegroep: geeft de gegevens per ad-groep weer. Van toepassing op [!DNL AdWords], [!DNL Bing], en [!DNL Facebook].
* Advertentie: geeft de gegevens weer op advertentie. Is van toepassing op dubbelklik-advertenties. Als Dubbelklik niet wordt gebruikt, worden er geen resultaten weergegeven
* Adverteerder: geeft de gegevens weer door adverteerder. Is van toepassing op de Dubbleclick-adverteerder. Als Doubleclick niet wordt gebruikt, worden er geen resultaten weergegeven
* Creatief: geeft de gegevens weer op basis van creatief. Van toepassing op [!DNL AdWords], [!DNL Bing], en [!DNL Facebook].
* Trefwoord: geeft de gegevens weer op trefwoord. Van toepassing op [!DNL AdWords], [!DNL Bing], en [!DNL Facebook].
* Plaatsing: geeft de gegevens weer op basis van plaatsing. Is van toepassing op Dubbelklik-plaatsingen. Als Dubbelklik niet wordt gebruikt, worden er geen resultaten weergegeven.
* Site: geeft de gegevens per site weer. Is van toepassing op Dubbleclick-sites. Als Dubbleclick niet wordt gebruikt, worden er geen resultaten weergegeven

**Groeperen op**

_Gebruikt in: Overzicht, Groei, Marketing, Op rekening gebaseerde Marketing, Web Traffic, CMO_

Hiermee past u grafieken aan om de dimensie te wijzigen die wordt gestapeld en gegroepeerd. Standaard is Groeperen via ingesteld op Kanaal en kan deze worden gewijzigd in:

* Geen: alles wordt samen weergegeven zonder onderbreking
* Kanaal: groepeert de gegevens door marketing kanaal
* Subkanaal: groepeert de gegevens door subkanaal op de markt te brengen
* Campagne: groepeert de gegevens door campagne
* Account: hiermee groepeert u de gegevens per account. Van toepassing op [!DNL AdWords], [!DNL Bing], en [!DNL Facebook].
* Advertentiegroep: groepeert de gegevens per ad-groep. Van toepassing op [!DNL AdWords], [!DNL Bing], en [!DNL Facebook].
* Toevoegen: groepeert de gegevens op advertentie. Is van toepassing op dubbelklik-advertenties. Als Dubbelklik niet wordt gebruikt, worden er geen resultaten weergegeven
* Adverteerder: groepeert de gegevens per adverteerder. Is van toepassing op de Dubbleclick-adverteerder. Als Doubleclick niet wordt gebruikt, worden er geen resultaten weergegeven
* Creatief: groepeert de gegevens door creatief. Van toepassing op [!DNL AdWords], [!DNL Bing], en [!DNL Facebook].
* Trefwoord: groepeert de gegevens op trefwoord. Van toepassing op [!DNL AdWords], [!DNL Bing], en [!DNL Facebook].
* Plaatsing: groepeert de gegevens door plaatsing. Is van toepassing op Dubbelklik-plaatsingen. Als Dubbelklik niet wordt gebruikt, worden er geen resultaten weergegeven.
* Site: groepeert de gegevens per site. Is van toepassing op Dubbleclick-sites. Als Dubbleclick niet wordt gebruikt, worden er geen resultaten weergegeven

![](assets/2.png)

**Openingspagina**

_Gebruikt in: Content Marketing_

Maak kennis met de prestaties van één landingspagina of landingspagina&#39;s met een bepaald woord zoals &quot;blog&quot;.

**Metrisch**

_Gebruikt in: Overzicht, Webverkeer, CMO, Betaalde Media, Inhoud Marketing_

Er zijn twee verschillende metrische kiezers die voor verschillende borden worden gebruikt. De metrische kiezer wijzigt de maatregel op een grafiek, zodat u kunt schakelen tussen bijvoorbeeld het bekijken van omzet of het uitgeven of het drukken.

Op het Overzicht en de Borden van GMO, is er een verkorte lijst van waarden met betrekking tot ROI metriek:

* Ontvangsten
* Draaien
* Overeenkomsten
* Opbrengst pijpleiding
* Kansen
* Contactpersonen
* Leads

Op het Verkeer van het Web, Betaalde Media, en de Marketingboards van de Inhoud, is er een langere lijst van waarden met betrekking tot zowel ROI als tintmetriek:

* Ontvangsten
* Draaien
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

Standaard geeft het snelheidsbord de tijden voor alle fasen weer, maar als u wilt inboren in een specifiek werkgebied, gebruikt u het werkgebiedfilter om het werkgebied te selecteren.

**Subkanaal**

_Gebruikt in: Overzicht, Groei, Marketing, Adds ROI, Web Traffic, CMO, Betaalde Media, Content Marketing, Passport_

Filter het bord met één of meerdere subkanalen. Operatoren geven het filter extra flexibiliteit, zoals het gebruik van de operatoren &quot;contains&quot; of &quot;start met&quot;. Als een filter Kanaal is toegepast, zal de lijst van subkanalen die verschijnen een ondergroep van de toegepaste filters zijn. Nadat een subkanaal is ingevoerd, worden de waarden in de Campagnefilters weergegeven op basis van het toegepaste subkanaalfilter.

**URL**

_Gebruikt in: Webverkeer_

Boor in het verkeer van één enkele URL, of misschien URLs die een bepaald woord zoals &quot;product&quot;bevatten.

**Won**

_Gebruikt in: Snelheid_

Door gebrek, rapporteert het Comité van Snelheid over slechts gesloten won kansen, maar pas dit filter aan om de snelheid voor of gesloten won of gesloten verloren kansen te bekijken.
