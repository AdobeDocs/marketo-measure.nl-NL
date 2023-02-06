---
unique-page-id: 18874586
description: Verklarende woordenlijst van Marketo Measure Fields - Marketo Measure - Productdocumentatie
title: Woordenlijst met Marketo Measure-velden
exl-id: 8e23b102-6d4f-4919-b361-04d1b184e710
source-git-commit: 334dcd3dcbddacc4920d182d94908babd3cb8c89
workflow-type: tm+mt
source-wordcount: '3211'
ht-degree: 0%

---

# Woordenlijst met Marketo Measure-velden {#glossary-of-marketo-measure-fields}

Dit artikel bevat een woordenlijst met alle Marketo Measure-velden die vanuit het Marketo Measure Base Package aan uw Salesforce worden toegevoegd. U zult ook informatie vinden over welk Voorwerp het Gebied kan worden gevonden en hoe elk Gebied met informatie wordt bevolkt.

Voor een kaart waarop Object elk Marketo Measure-veld betrekking heeft, gelieve [klik hier](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-object-and-field-taxonomy.md).

[A](#a) ・ [B](#b) ・ [C](#c) ・ [D](#d) ・ [E](#e) ・ [F](#f) ・ [G](#g) ・ H ・ I ・ J ・ J [K](#k) ・ [L](#l) ・ [M](#m) ・ N ・ [O](#o) ・ [P](#p) ・ Q ・ [R](#r) ・ [S](#s) ・ [T](#t) ・ [U](#u) ・ [V](#v) ・ W ・ X ・ Y ・ Z

## A {#a}

**Account** | Aanraakpunt voor koperkenmerk gevonden

In dit veld wordt de accountnaam ingevuld die is gekoppeld aan de BBT.

**Campagne-id toevoegen** | Aanraakpunt voor koperkenmerk gevonden op aanraakpunt voor koper

U kunt dit veld op drie manieren invullen:

`1)` Als het aanraakpunt afkomstig is van een betaalde zoekactie (AdWords of BingAds), wordt de campagne-id voor advertenties van het advertentieplatform hier weergegeven.

`2)` Als het aanraakpunt niet afkomstig is van een betaalde zoekopdracht, wordt het veld gevuld met de utm_campagne-waarde van de bestemmingspagina URL.

bijv. `http://info.marketomeasure.com/adwords-for-lead-generation?utm_source=Event&utm_medium=booth&utm_campaign=Marketo%20Virtual%20Event%20sep2014`

In dit voorbeeld wordt de campagne-id voor advertenties weergegeven: __GAId__ Virtuele marketinggebeurtenis september 2014

`3)` Als het aanraakpunt afkomstig is van een offline Salesforce-campagne (een conferentie, diner, enz.), wordt de campagne-id van Salesforce weergegeven op de pagina

Als geen van bovenstaande velden wordt gebruikt, is dit veld leeg.

**Naam advertentiecampagne** | Aanraakpunt koper, aanraakpunt koper

`1)` Als het aanraakpunt afkomstig is van een betaalde zoekopdracht (AdWords/Bing Ads), wordt de naam van de advertentiecampagne van het advertentieplatform hier weergegeven.

`2)` Als het aanraakpunt niet afkomstig is van een betaalde zoekopdracht en de bestemmingspagina-URL een waarde voor utm_campagne bevat, wordt die waarde hier ingevuld.

`3)` Als het aanraakpunt afkomstig was van een Salesforce-campagne, wordt de naam van de Salesforce-campagne hier weergegeven.

`4)` Dit wordt gevuld met de naam van de campagne die is gedefinieerd voor aanraakpunten die zijn gegenereerd op basis van Activiteiten die zijn gemaakt in uw Marketo Measure-account.

Als geen van bovenstaande velden wordt gebruikt, is dit veld leeg.

**Naam advertentiecampagne (FT)** | Aanraakpunt koper

Dit veld wordt op dezelfde manier gevuld als de naam van een advertentiecampagne. In dit veld wordt echter specifiek de naam getoond van de advertentiecampagne die het aanraakpunt First Touch heeft gegenereerd.

**Naam advertentiecampagne (LC)** | Aanraakpunt koper

Dit veld wordt op dezelfde manier gevuld als de naam van een advertentiecampagne. In dit veld wordt echter specifiek de naam getoond van de advertentiecampagne die het aanraakpunt voor het maken van leads heeft gegenereerd.

**Inhoud toevoegen** | Aanraakpunt koper, aanraakpunt koper

`1)` Als het aanraakpunt afkomstig is van een betaalde zoekopdracht (AdWords/Bing Ads), wordt in het veld de volledige advertentie-kopie van het advertentieplatform weergegeven.

`2)` Als het aanraakpunt niet afkomstig is van een betaalde zoekopdracht, geeft dit veld de utm_content-waarde weer in de URL van de bestemmingspagina.

`3)` Dit zal met de Onderwerpwaarde van de verwante Activiteit bevolken die het Aanraakpunt produceerde.

Als geen van beide bovenstaande velden wordt weergegeven, is dit veld leeg.

**Doel-URL toevoegen** | Aanraakpunt koper, aanraakpunt koper

`1)` Als het aanraakpunt afkomstig is van een betaalde zoekopdracht, wordt in dit veld de URL weergegeven waarnaar u wordt verwezen nadat u in de zoekfunctie op de advertentie hebt geklikt.

Als het aanraakpunt niet afkomstig is van een betaalde zoekopdracht, is het veld leeg.

**Groep-id toevoegen** | Aanraakpunt koper, aanraakpunt koperkenmerk

`1)` Als het aanraakpunt afkomstig is van een betaalde zoekopdracht, wordt de advertentie-groep-id van Advertentie-woorden/Bing Ads hier weergegeven.

Als het aanraakpunt niet afkomstig is van een betaalde zoekopdracht, is het veld leeg.

**Naam advertentiegroep** | Aanraakpunt koper, aanraakpunt koper

`1)` Als het aanraakpunt afkomstig is van een betaalde zoekopdracht, wordt hier de naam van de Advertentiegroep van Advertentiegrames/Bing Ads weergegeven.

Als het aanraakpunt niet afkomstig is van een betaalde zoekopdracht, is het veld leeg.

**Advertentie-id** | Aanraakpunt koper, aanraakpunt koper

`1)` Als het aanraakpunt afkomstig is van een betaalde zoekopdracht, wordt de advertentie-id van Advertentie-woorden/Bing Ads hier weergegeven.

`2)` Dit zal met de Externe identiteitskaart van de Activiteit bevolken als het Aanraakpunt van een Activiteit van CRM wordt geproduceerd.

Als het aanraakpunt niet afkomstig is van een betaalde zoekopdracht, is het veld leeg.

**Attributie % aangepast model** | Aanraakpunt voor koperkenmerk

Als u een Aangepast kenmerkingsmodel gebruikt, wordt in dit veld het percentage weergegeven van de inkomsten dat aan een aanraakpunt wordt toegewezen op basis van de waarden die in het Aangepaste model zijn ingesteld.

Als u geen aangepast model gebruikt, is dit veld leeg.

**Attributie % First Touch** | Aanraakpunt voor koperkenmerk

In dit veld wordt het percentage weergegeven van de inkomsten die worden toegewezen aan een aanraakpunt volgens een First Touch Model.

**Attributie % vol** | Aanraakpunt voor koperkenmerk

In dit veld wordt het percentage weergegeven van de inkomsten die worden toegewezen aan een aanraakpunt volgens een Volledig padmodel.

**Attributie % lead creation** | Aanraakpunt voor koperkenmerk

In dit veld wordt het percentage weergegeven van de inkomsten die aan een aanraakpunt zijn toegewezen, volgens een Lead Creation Model.

**Attributie % U-vorm** | Aanraakpunt voor koperkenmerk

In dit veld wordt het percentage weergegeven van de inkomsten die worden toegewezen aan een aanraakpunt volgens een U-Vormd model.

**Attributie % W-Shaped** | Aanraakpunt voor koperkenmerk

In dit veld wordt het percentage weergegeven van de inkomsten die worden toegewezen aan een aanraakpunt volgens een W-Shaped-model.

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

## B {#b}

**Aantal Marketo Measure-kansen** | Salesforce Opportunity

Als u een veld Aangepast bedrag gebruikt om inkomsten van opportunity te melden, kan Marketo Measure deze velden Aangepast bedrag niet lezen. Het Marketo Measure Opportunity Amount is een verborgen veld dat wordt gebruikt om een workflow te maken waarmee Marketo Measure aangepaste Mate-velden op de Opportunity kan lezen.

**Browser** | Aanraakpunt koper, aanraakpunt koper

In dit veld wordt het type webbrowser weergegeven dat tijdens de websessie wordt gebruikt (Chrome, Safari, Firefox, enz.).

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

## C {#c}

**Contact** | Aanraakpunt koper, aanraakpunt koper

In het veld wordt de contactpersoon weergegeven waartoe het aanraakpunt behoort.

**Tellen - aangepast model** | Aanraakpunt voor koperkenmerk

Als u een Aangepast Attributiemodel gebruikt, toont dit gebied, in decimale vorm, het percentage van opbrengstkrediet dat aan een aanraakpunt volgens de waarden wordt gegeven die in uw Model van de Douane worden geplaatst.

Als u geen aangepast model gebruikt, is dit veld leeg.

**Tellen - aangepast model** | Aanraakpunt koper

Als u een Aangepast kenmerkingsmodel gebruikt, wordt in dit veld, in decimale vorm, het percentage van het toewijzingskrediet weergegeven dat aan een aanraakpunt wordt gegeven volgens de waarden die zijn ingesteld in het Aangepaste model. Aangezien dit veld betrekking heeft op het object Aanraakpunt koper, is het geen weerspiegeling van inkomstenkrediet, alleen maar een toeschrijving.

Als u geen aangepast model gebruikt, is dit veld leeg.

**Aantal - eerste aanraking** | Aanraakpunt voor koperkenmerk

In dit veld wordt, in decimale vorm, het percentage weergegeven van de aan een aanraakpunt toegekende inkomsten volgens het First Touch-model.

**Aantal - eerste aanraking** | Aanraakpunt koper

In dit veld wordt, in decimale vorm, het percentage van het toewijzingskrediet weergegeven dat aan een aanraakpunt wordt gegeven volgens een First Touch Model. Als het aanraakpunt de Eerste aanraking is, is dit veld altijd 1,0 (100% toewijzingskrediet). Als het aanraakpunt niet de First Touch is, is dit veld altijd 0 (0 % toewijzingskrediet).

Aangezien dit veld betrekking heeft op het object Aanraakpunt koper, is het geen weerspiegeling van inkomstenkrediet, alleen maar een toeschrijving.

**Tellen - volledig pad** | Aanraakpunt voor koperkenmerk

In dit veld wordt in decimale vorm het percentage weergegeven van de inkomsten die aan een aanraakpunt worden gegeven volgens een Volledig padmodel.

**Tellen - Aanraakvlak voor lead-ontwerp** | Aanraakpunt voor koperkenmerk

In dit veld wordt, in decimale vorm, het percentage van de aan een aanraakpunt toegekende inkomsten weergegeven volgens het Aanmaakmodel voor lead.

**Tellen - Aanraakvlak voor lead-ontwerp** | Aanraakpunt koper

In dit veld wordt, in decimale vorm, het percentage van het toewijzingskrediet weergegeven dat aan een aanraakpunt wordt gegeven volgens het Aanmaakmodel voor lead. Als het aanraakpunt de Lead Creation touch is, is dit veld altijd 1,0 (100% toewijzingskrediet). Als het aanraakpunt niet de Aanraakaanraking voor lead is, is dit veld altijd 0 (0% toewijzingskrediet).

Aangezien dit veld betrekking heeft op het object Aanraakpunt koper, is het geen weerspiegeling van inkomstenkrediet, alleen maar een toeschrijving.

**Aantal - U-vorm** | Aanraakpunt voor koperkenmerk

In dit veld wordt, in decimale vorm, het percentage van de aan een aanraakpunt toegekende inkomstenkredieten weergegeven volgens een U-Vormd model.

**Aantal - U-vorm** | Aanraakpunt koper

In dit veld wordt, in decimale vorm, het percentage van het toewijzingskrediet weergegeven dat aan een aanraakpunt wordt gegeven volgens een U-Vormd model. In het U-Vormd model wordt de creditering verdeeld tussen de First Touch, de Lead Creation Touch, en om het even welke intermediaire vormindieningen die tussen de Eerste Aanraking en de Aanmaak van de Lood plaatsvonden.

Aangezien dit veld betrekking heeft op het object Aanraakpunt koper, is het geen weerspiegeling van inkomstenkrediet, alleen maar een toeschrijving.

**Aantal - W-vorm** | Aanraakpunt voor koperkenmerk

In dit veld wordt, in decimale vorm, het kredietpercentage weergegeven dat aan een aanraakpunt wordt toegekend volgens een W-Shaped-model.

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

## D {#d}

Datum van melding | Marketo Measure ABTest, Marketo Measure Event

Marketo Measure-gebeurtenis - de datum waarop een gebruiker een specifieke actie op uw website heeft uitgevoerd en een gebeurtenis heeft geactiveerd

Marketo Measure ABTest - de datum waarop een gebruiker heeft deelgenomen aan een A/B-test op uw website

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

## E {#e}

**Gebeurtenisnaam** | Marketo Measure-gebeurtenis

In dit veld wordt de naam weergegeven van de actie die de gebeurtenis heeft geactiveerd (bijvoorbeeld Paginaweergave).

**Gebeurteniswaarde** | Marketo Measure-gebeurtenis

De beschrijving van de gebeurtenis (bijvoorbeeld Homepage)

**Naam experiment** | Marketo Measure ABTest

In dit veld wordt de naam van het experiment weergegeven (bijvoorbeeld de knop Proefversie)

**Id van experiment** |Marketo Measure AB-test

De unieke identificatiecode voor elk experiment

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

## F {#f}

URL van formulier | Aanraakpunt koper, aanraakpunt koper

In dit veld wordt een verkorte versie van de URL van een pagina weergegeven waar de formuliervulling is opgetreden (geen UTM-parameters)

URL formulier - Raw | Aanraakpunt koper, aanraakpunt koper

In dit veld wordt de volledige pagina-URL weergegeven waar de formuliervulling is opgetreden, inclusief UTM-parameters

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

## G {#g}

Geo City | Aanraakpunt koper, aanraakpunt koperkenmerk

In dit veld wordt de naam weergegeven van de stad waar de lead/contactpersoon uw website heeft bezocht. Dit wordt gedaan via omgekeerde IP raadpleging.

Geo Land | Aanraakpunt koper, aanraakpunt koperkenmerk

In dit veld wordt weergegeven waar het land waar de lead/contactpersoon uw website heeft bezocht. Dit wordt gedaan via omgekeerde IP raadpleging.

Geo | Aanraakpunt koper, aanraakpunt koper

In dit veld wordt het gebied of de staat weergegeven waar de lead/contactpersoon uw website heeft bezocht. Dit wordt gedaan via omgekeerde IP raadpleging.

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

## K {#k}

**Trefwoord-id** | Aanraakpunt koper, aanraakpunt koper

Als het aanraakpunt afkomstig is van een betaalde zoekopdracht, wordt in dit veld de trefwoordid van het advertentieplatform (Adwords/BingAds) weergegeven.

Als dit aanraakpunt niet afkomstig is van een betaalde zoekopdracht, is dit veld leeg.

**Trefwoord MatchType** | Aanraakpunt koper, aanraakpunt koper

Als het aanraakpunt afkomstig is van een betaalde zoekopdracht, wordt in dit veld het type van het advertentieplatform (Adwords/Bing) weergegeven.

**Trefwoordtekst** | Aanraakpunt koper, aanraakpunt koper

`1)` Als het aanraakpunt afkomstig is van een betaalde zoekopdracht, wordt in dit veld de trefwoordtekst weergegeven van het advertentieplatform (Adwords/BingAds) OF de waarde van de parameter _bk in de URL van de bestemmingspagina.

bijv. `http://info.marketomeasure.com/intro-guide-b2b-marketing-attribution?_bt=12345678&_bk=marketing%20attribution&_bm=p&gclid=ABc123def456ghi789jkl`

`2)` Als het aanraakpunt niet afkomstig is van een betaalde zoekopdracht, wordt in dit veld de utm_term-waarde van de URL van de bestemmingspagina weergegeven.

`http://www.marketomeasure.com/blog/lead-generation?utm_source=linkedin&utm_medium=Social&utm_campaign=ABC%20Blog&utm_content=Lead%20Gen&utm_term=lead%20gen`.

Als het aanraakpunt niet afkomstig is van een betaalde zoekopdracht of als er geen waarde voor utm_term is, is dit veld leeg.

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

## L {#l}

**Openingspagina** | Aanraakpunt koper, aanraakpunt koper

In dit veld wordt de verkorte versie van de URL (geen UTM-parameters) weergegeven van de eerste webpagina die tijdens een websessie wordt bezocht.

**Openingspagina - Raw** | Aanraakpunt koper, aanraakpunt koper

In dit veld wordt de volledige URL (inclusief UTM-parameters) weergegeven van de eerste webpagina die tijdens een websessie wordt bezocht.

**Lood** | Aanraakpunt koper, Marketo Measure-persoon

In dit veld wordt de naam weergegeven van de lead waartoe een aanraakpunt behoort.

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

## M {#m}

**Marketingkanaal** | Aanraakpunt koper, aanraakpunt koperkenmerk

In dit veld ziet u de algemene groep marketingactiviteiten of het marketingkanaal waartoe het aanraakpunt behoort (d.w.z. Betaalde zoekopdracht, Direct, Sociaal, enz.). Aanraakpunten worden gegroepeerd op basis van de manier waarop uw kanalen zijn ingesteld in de Marketo Measure App. Voor meer informatie over marketingkanalen of hoe u uw kanalen instelt, raadpleegt u [klik hier](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md).

**Marketingkanaal - pad** | Aanraakpunt koper, aanraakpunt koper

In dit veld ziet u het marketingkanaal en het subkanaal waartoe een aanraakpunt behoort. In het onderstaande voorbeeld is Marketing Channel - Path Social.Linkedin, waarbij het marketingkanaal Sociaal is, en het subkanaal LinkedIn.

![](assets/1-3.png)

**Normaal** | Aanraakpunt koper, aanraakpunt koper

`1)` Als het aanraakpunt afkomstig is van een betaalde zoekopdracht, wordt het medium van Adwords/BingAds hier weergegeven (d.w.z. CPC).

`2)` Als het aanraakpunt niet afkomstig is van een betaalde zoekopdracht, wordt in dit veld de utm_medium-waarde van de URL van de bestemmingspagina weergegeven.

`3)` Als het aanraakpunt afkomstig is van een offline campagne, wordt in dit veld het veld Type weergegeven in de Salesforce-campagne.

`4)` Dit zal met de waarde van het Type van Activiteit van de verwante Activiteit bevolken die het Aanraakpunt produceerde.

Als geen van de bovenstaande opties aanwezig is, stelt Marketo Measure automatisch een gemiddelde waarde in.

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

O

**Opportunity** | Aanraakpunt voor koperkenmerk

In dit veld wordt de mogelijkheid weergegeven waartoe de BBT behoort.

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

P

**Platform** | Aanraakpunt koper, aanraakpunt koper

In dit veld worden het type computer of telefoon en het type besturingssysteem weergegeven dat tijdens de websessie is gebruikt.

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

R

**Referentiepagina** | Aanraakpunt koper, aanraakpunt koper

In dit veld wordt de URL (zonder UTM-parameters) weergegeven van de laatste webpagina waarop de lead/contactpersoon zich bevond en die hen naar uw website heeft geleid.

Bijvoorbeeld:

- Als het aanraakpunt afkomstig is van een zoekopdracht in het veld Betaald/Organic, wordt de URL van het zoekprogramma weergegeven

- Als het aanraakpunt afkomstig is van Social, wordt in het veld de URL van de sociale website (d.w.z. LinkedIn) weergegeven.

**Refereringspagina - Raw** | Aanraakpunt koper, aanraakpunt koperkenmerk

In dit veld wordt dezelfde informatie weergegeven als bij Referrer Page, behalve in dit veld wordt de volledige verwijzende URL (inclusief UTM-parameters) weergegeven.

**Inkomsten - aangepast model** | Aanraakpunt voor koperkenmerk

Als u een Aangepast kenmerkingsmodel gebruikt, wordt in dit veld het bedrag aan dollaropbrengsten weergegeven dat wordt toegewezen aan een aanraakpunt op basis van het toewijzingspercentage dat is ingesteld in het Aangepaste model.

Als u geen aangepast model gebruikt, is het dollarbedrag 0.

**Ontvangsten - eerste aanraking** | Aanraakpunt voor koperkenmerk

In dit veld wordt het bedrag aan dollaropbrengsten weergegeven dat wordt toegewezen aan een aanraakpunt volgens het toewijzingspercentage in het Eerste aanraakmodel.

**Inkomsten - volledig pad** | Aanraakpunt voor koperkenmerk

In dit veld wordt het bedrag aan dollaropbrengsten weergegeven dat wordt toegewezen aan een aanraakpunt volgens het toewijzingspercentage in het volledige padmodel.

**Ontvangsten - Aanraakvlak met lead** | Aanraakpunt voor koperkenmerk

In dit veld wordt het bedrag aan dollaropbrengsten weergegeven dat wordt toegewezen aan een aanraakpunt volgens het toewijzingspercentage in het Aanmaakmodel voor lead.

**Inkomsten - U-vorm** | Aanraakpunt voor koperkenmerk

In dit veld wordt het bedrag aan dollaropbrengsten weergegeven dat wordt toegewezen aan een aanraakpunt volgens het toewijzingspercentage in het U-Vormd model.

**Ontvangsten - W-vorm** | Aanraakpunt voor koperkenmerk

In dit veld wordt het bedrag van de dollaropbrengsten weergegeven dat aan een aanraakpunt wordt toegewezen op basis van het toewijzingspercentage in het model W-Shaped.

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

S

**Salesforce-campagne** | Aanraakpunt koper, aanraakpunt koper

In dit veld wordt de Salesforce-campagne weergegeven waartoe het aanraakpunt behoort.

**Zoekwoordgroep** | Aanraakpunt koper, aanraakpunt koperkenmerk

Als het aanraakpunt afkomstig is van betaald of biologisch zoeken, wordt in dit veld de zoekuitdrukking weergegeven die in het zoekprogramma is getypt. Vanwege privacyredenen is deze informatie echter meestal niet beschikbaar.

**Segment** | Aanraakpunt voor koperkenmerk

In dit veld worden de segmenten weergegeven waartoe het aanraakpunt behoort. Dit is afhankelijk van de configuratie van de segmentatieregels in de Marketo Measure-app.

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

T

**Aanraakpuntdatum** | Aanraakpunt koper, aanraakpunt koper

`1)` Als het aanraakpunt afkomstig is van een onlinebron, worden in dit veld de datum en tijd weergegeven waarop het aanraakpunt is opgetreden.

`2)` Als het aanraakpunt afkomstig is van een offline gebeurtenis, worden in dit veld de datum en tijd weergegeven die zijn ingesteld in de Salesforce-campagne of vanuit het datumveld dat is geselecteerd in de Campagne Sync Rules.

`3)` Als het aanraakpunt afkomstig is van een activiteit, worden in dit veld de datum en tijd weergegeven van het veld dat is geselecteerd als aanraakpunt Datum in de activiteitregels.

**Aanraakpuntdatum (FT)** | Aanraakpunt koper

Dit is hetzelfde veld als Aanraakpuntdatum, maar in dit veld worden specifiek de datum en tijd weergegeven waarop het eerste aanraakpunt is opgetreden.

**Aanraakpuntdatum (LC)** | Aanraakpunt koper

Dit is hetzelfde veld als Aanraakpuntdatum. In dit veld worden echter specifiek de datum en tijd weergegeven waarop het aanraakpunt voor aanwijzen is opgetreden.

**Positie aanraakpunt** | Aanraakpunt koper, aanraakpunt koper

In dit veld wordt de positie van het aanraakpunt weergegeven. De positie van het aanraakpunt weerspiegelt de belangrijkste mijlpalen in de reis van de klant (FT, Form, LC, OC, Closed). De positie van het aanraakpunt is afhankelijk van het tijdstip waarop het zich tijdens de reis van de klant heeft voorgedaan en één aanraakpunt kan meerdere posities hebben. De verschillende posities van aanraakpunten zijn als volgt:

First Touch (FT) - De allereerste marketinginteractie die iemand heeft met uw merk

Lood Creation (LC) - De allereerste bekende marketinginteractie (meestal een formulierverzending of een Salesforce Campaign-opname)

Formulier - Wanneer een bezoeker een onlineformulier invult

Opportunity Creation (OC) - De marketinginteractie die het dichtst bij het maken van de Opp ligt

Gesloten - De marketinginteractie die het dichtst bij wanneer Opp wordt gesloten (Won of Verloren)

**Aanraakpuntbron** | Aanraakpunt koper, aanraakpunt koperkenmerk

`1)` Als het aanraakpunt afkomstig is van een betaalde zoekopdracht, wordt in dit veld de naam van het advertentieplatform (AdWords/BingAds) weergegeven

`2)` Als het aanraakpunt afkomstig is van een organische zoekopdracht, wordt in dit veld de naam van de zoekfunctie weergegeven

`3)` Als #1 of #2 niet aanwezig is en de utm_source-waarde aanwezig is op de bestemmingspagina-URL voor het aanraakpunt, wordt die waarde hier weergegeven

`4)` Dit zal als Campagne van CRM bevolken als het Aanraakpunt van een Campagne van CRM wordt geproduceerd.

`5)` Dit wordt gevuld als CRM-activiteit als het aanraakpunt wordt gegenereerd op basis van een CRM-activiteit.

Als geen van bovenstaande velden wordt ingevuld, wordt dit veld ingevuld als &#39;Web Direct&#39; of &#39;Web&#39;.

**Aanraakpuntbron (FT)** | Aanraakpunt koper

Dit is hetzelfde veld als de aanraakpuntbron, maar in dit veld wordt specifiek de bron van het eerste aanraakpunt weergegeven.

**Aanraakpuntbron (LC)** | Aanraakpunt koper

Dit is hetzelfde veld als Touchpoint Source, maar in dit veld wordt specifiek de bron van het aanraakpunt voor het maken van leads weergegeven.

**Type aanraakpunt** | Aanraakpunt voor kopers en kenmerk Aanraakpunt voor kopers gevonden.

In dit veld wordt het type interactie van het aanraakpunt weergegeven. Deze wordt weergegeven als: Webbezoek, Webformulier of Webchat voor JavaScript-aanraakpunten. Voor CRM Campaign Touchpoints wordt deze weergegeven als CRM. Het zal met het Type van Taak of van de Gebeurtenis voor de Aanraakpunten van de Activiteit bevolken.

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

U

**UniqueId** | Aanraakpunt koper, aanraakpunt koper

De unieke id die aan elk aanraakpunt is gekoppeld

**Gebruikersnaam** | Marketo Measure ABTest

De unieke identificatiecode van optimalisatie voor elk gebruik

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

## V {#v}

**Variatie** | Marketo Measure ABTest

De naam van de variatie van de A/B-test

**Variatie-id** | Marketo Measure ABTest

De unieke identificatiecode voor elke variant van de A/B-test.

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)
