---
unique-page-id: 18874586
description: Verklarende woordenlijst van Marketo Measure Fields - Marketo Measure - Productdocumentatie
title: Woordenlijst met Marketo Measure-velden
exl-id: 8e23b102-6d4f-4919-b361-04d1b184e710
feature: Fundamentals
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '3213'
ht-degree: 0%

---

# Woordenlijst met Marketo Measure-velden {#glossary-of-marketo-measure-fields}

Dit artikel bevat een woordenlijst met alle Marketo Measure-velden die vanuit het Marketo Measure Base Package aan uw Salesforce zijn toegevoegd. U zult ook informatie vinden over welk Voorwerp het Gebied kan worden gevonden en hoe elk Gebied met informatie wordt bevolkt.

Voor een kaart waarvan Voorwerp elk gebied van Marketo Measure op betrekking heeft, [ klik hier ](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-object-and-field-taxonomy.md).

[ A ](#a) ・ [ B ](#b) ・ [ C ](#c) ・ [ D ](#d) ・ [ E ](#e) ・ [ F ](#f) ・ [ G ](#g) ・ H ・ I ・ J ・ J ・ [ K ](#k) ・ [ L ](#l) ・ M [ ・ N ・ ](#m) O [ ・ ](#o) P [ ・ Q ・ ](#p) R [ ・ ](#r) S [ ・ ](#s) T [ ・ ](#t) U [ ・ ](#u) V [ ・ X ・ Y Z](#v)

## A {#a}

**Rekening** | Gevonden op Buyer Attribution Touchpoint

Dit veld wordt gevuld met de accountnaam die aan de BAT is gekoppeld.

**Add Campagne identiteitskaart** | Gevonden op Buyer Touchpoint, Buyer Attribution Touchpoint

Er zijn drie manieren waarop dit veld kan worden ingevuld:

`1)` Als het aanraakpunt afkomstig is van een betaalde zoekactie (AdWords of BingAds), wordt de campagne-id voor Advertentie van het advertentieplatform hier weergegeven.

`2)` Als het aanraakpunt niet afkomstig is van een betaalde zoekopdracht, wordt het veld gevuld met de utm_campagne-waarde van de bestemmingspagina URL.

bijv. `http://info.marketomeasure.com/adwords-for-lead-generation?utm_source=Event&utm_medium=booth&utm_campaign=Marketo%20Virtual%20Event%20sep2014`

In dit voorbeeld, zou identiteitskaart van de Campagne Ad tonen: __GAId__ de Virtuele Gebeurtenis sept2014 van de Marketing

`3)` Als het aanraakpunt afkomstig is van een offline Salesforce-campagne (een conferentie, diner, enz.), wordt de campagne-id van Salesforce weergegeven op de pagina Campagne-id

Als geen van bovenstaande velden wordt gebruikt, is dit veld leeg.

**Add de Naam van de Campagne** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` Als het aanraakpunt afkomstig is van een betaalde zoekopdracht (AdWords/Bing Ads), wordt de naam van de advertentiecampagne van het advertentieplatform hier weergegeven.

`2)` Als het aanraakpunt niet afkomstig is van een betaalde zoekopdracht en de URL van de landingspagina een waarde bevat voor utm_campagne, wordt die waarde hier ingevuld.

`3)` Als het aanraakpunt afkomstig is van een Salesforce-campagne, wordt de naam van de Salesforce-campagne hier weergegeven.

`4)` Dit wordt gevuld met de naam van de campagne die is gedefinieerd voor aanraakpunten die zijn gegenereerd op basis van Activiteiten die zijn gemaakt in uw Marketo Measure-account.

Als geen van bovenstaande velden wordt gebruikt, is dit veld leeg.

**Add de Naam van de Campagne (FT)** | Buyer Touchpoint

Dit veld wordt op dezelfde manier gevuld als de naam van een advertentiecampagne. In dit veld wordt echter specifiek de naam getoond van de advertentiecampagne die het aanraakpunt First Touch heeft gegenereerd.

**Add de Naam van de Campagne (LC)** | Buyer Touchpoint

Dit veld wordt op dezelfde manier gevuld als de naam van een advertentiecampagne. In dit veld wordt echter specifiek de naam getoond van de advertentiecampagne die het aanraakpunt voor het maken van leads heeft gegenereerd.

**voeg Inhoud** toe | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` Als het aanraakpunt afkomstig is van een betaalde zoekopdracht (AdWords/Bing Ads), wordt in het veld de volledige advertentie-kopie van het advertentieplatform weergegeven.

`2)` Als het aanraakpunt niet afkomstig is van een betaalde zoekopdracht, wordt in dit veld de utm_content-waarde weergegeven in de URL van de bestemmingspagina.

`3)` Hiermee wordt het onderwerp gevuld met de waarde voor Onderwerp van de gerelateerde activiteit die het aanraakpunt heeft gegenereerd.

Als geen van beide bovenstaande velden wordt weergegeven, is dit veld leeg.

**Add Doel URL** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` Als het aanraakpunt afkomstig is van een betaalde zoekopdracht, wordt in dit veld de URL weergegeven waarnaar u wordt verwezen nadat u in de zoekfunctie op de advertentie hebt geklikt.

Als het aanraakpunt niet afkomstig is van een betaalde zoekopdracht, is het veld leeg.

**Add Groep ID** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` Als het aanraakpunt afkomstig is van een betaalde zoekopdracht, wordt de Advertentiegroep-id van AdWords/Bing Ads hier weergegeven.

Als het aanraakpunt niet afkomstig is van een betaalde zoekopdracht, is het veld leeg.

**Add de Naam van de Groep** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` Als het aanraakpunt afkomstig is van een betaalde zoekopdracht, wordt hier de naam van de Advertentiegroep van Advertentiegrames/Bing Ads weergegeven.

Als het aanraakpunt niet afkomstig is van een betaalde zoekopdracht, is het veld leeg.

**Advertentie ID** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` Als het aanraakpunt afkomstig is van een betaalde zoekopdracht, wordt de advertentie-id van Advertentie-woorden/Bing Ads hier weergegeven.

`2)` Hiermee wordt de externe ID van de activiteit ingevuld als het aanraakpunt wordt gegenereerd op basis van een CRM-activiteit.

Als het aanraakpunt niet afkomstig is van een betaalde zoekopdracht, is het veld leeg.

**Attribution % het Model van de Douane** | Buyer Attribution Touchpoint

Als u een Aangepast kenmerkingsmodel gebruikt, wordt in dit veld het percentage weergegeven van de inkomsten dat aan een aanraakpunt wordt toegewezen op basis van de waarden die in het Aangepaste model zijn ingesteld.

Als u geen aangepast model gebruikt, is dit veld leeg.

**Attribution % First Touch** | Buyer Attribution Touchpoint

In dit veld wordt het percentage weergegeven van de inkomsten die worden toegewezen aan een aanraakpunt volgens een First Touch Model.

**Attribution % Volledig** | Buyer Attribution Touchpoint

In dit veld wordt het percentage weergegeven van de inkomsten die worden toegewezen aan een aanraakpunt volgens een Volledig padmodel.

**Attribution % Lood creatie** | Buyer Attribution Touchpoint

In dit veld wordt het percentage weergegeven van de inkomsten die aan een aanraakpunt zijn toegewezen, volgens een Lead Creation Model.

**Attributie % U-Vormd** | Buyer Attribution Touchpoint

In dit veld wordt het percentage weergegeven van de inkomsten die worden toegewezen aan een aanraakpunt volgens een U-Vormd model.

**Attributie % b-Vormd** | Buyer Attribution Touchpoint

In dit veld wordt het percentage weergegeven van de inkomsten die worden toegewezen aan een aanraakpunt volgens een W-Shaped-model.

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

## B {#b}

**het Bedrag van de Kans van Marketo Measure** | Salesforce Opportunity

Als u een veld Aangepast bedrag gebruikt om inkomsten van opportunity te melden, kan Marketo Measure deze velden Aangepast bedrag niet lezen. Het Marketo Measure Opportunity Amount is een verborgen veld dat wordt gebruikt om een workflow te maken waarmee Marketo Measure aangepaste Mate-velden op de Opportunity kan lezen.

**Browser** | Buyer Touchpoint, Buyer Attribution Touchpoint

In dit veld wordt het type webbrowser weergegeven dat tijdens de websessie wordt gebruikt (Chrome, Safari, Firefox, enz.).

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

## C {#c}

**Contact** | Buyer Touchpoint, Buyer Attribution Touchpoint

In het veld wordt de contactpersoon weergegeven waartoe het aanraakpunt behoort.

**Telling - het Model van de Douane** | Buyer Attribution Touchpoint

Als u een Aangepast Attributiemodel gebruikt, toont dit gebied, in decimale vorm, het percentage van opbrengstkrediet dat aan een aanraakpunt volgens de waarden wordt gegeven die in uw Model van de Douane worden geplaatst.

Als u geen aangepast model gebruikt, is dit veld leeg.

**Telling - het Model van de Douane** | Buyer Touchpoint

Als u een Aangepast kenmerkingsmodel gebruikt, wordt in dit veld, in decimale vorm, het percentage van het toewijzingskrediet weergegeven dat aan een aanraakpunt wordt gegeven op basis van de waarden die zijn ingesteld in het Aangepaste model. Aangezien dit veld betrekking heeft op het object Buyer Touchpoint, is het geen weerspiegeling van het inkomstenkrediet, alleen maar van het toekenningskrediet.

Als u geen aangepast model gebruikt, is dit veld leeg.

**Telling - eerste aanraking** | Buyer Attribution Touchpoint

In dit veld wordt, in decimale vorm, het percentage weergegeven van de aan een aanraakpunt toegekende inkomsten volgens het First Touch-model.

**Telling - eerste aanraking** | Buyer Touchpoint

In dit veld wordt, in decimale vorm, het percentage van het toewijzingskrediet weergegeven dat aan een aanraakpunt wordt gegeven volgens een First Touch Model. Als het aanraakpunt de Eerste aanraking is, is dit veld altijd 1,0 (100% toewijzingskrediet). Als het aanraakpunt niet de First Touch is, is dit veld altijd 0 (0 % toewijzingskrediet).

Aangezien dit veld betrekking heeft op het object Buyer Touchpoint, is het geen weerspiegeling van het inkomstenkrediet, alleen maar van het toekenningskrediet.

**Telling - Volledige Weg** | Buyer Attribution Touchpoint

In dit veld wordt in decimale vorm het percentage weergegeven van de inkomsten die aan een aanraakpunt worden gegeven volgens een Volledig padmodel.

**Telling - de Aanraking van de Aanmaak van de Lood** | Buyer Attribution Touchpoint

In dit veld wordt, in decimale vorm, het percentage van de aan een aanraakpunt toegekende inkomsten weergegeven volgens het Aanmaakmodel voor lead.

**Telling - de Aanraking van de Aanmaak van de Lood** | Buyer Touchpoint

In dit veld wordt, in decimale vorm, het percentage van het toewijzingskrediet weergegeven dat aan een aanraakpunt wordt gegeven volgens het Aanmaakmodel voor lead. Als het aanraakpunt de Lead Creation touch is, is dit veld altijd 1,0 (100% toewijzingskrediet). Als het aanraakpunt niet de Aanraakaanraking voor lead is, is dit veld altijd 0 (0% toewijzingskrediet).

Aangezien dit veld betrekking heeft op het object Buyer Touchpoint, is het geen weerspiegeling van het inkomstenkrediet, alleen maar van het toekenningskrediet.

**Telling - U-Vormd** | Buyer Attribution Touchpoint

In dit veld wordt, in decimale vorm, het percentage van de aan een aanraakpunt toegekende inkomstenkredieten weergegeven volgens een U-Vormd model.

**Telling - U-Vormd** | Buyer Touchpoint

In dit veld wordt, in decimale vorm, het percentage van het toewijzingskrediet weergegeven dat aan een aanraakpunt wordt gegeven volgens een U-Vormd model. In het U-Vormd model wordt de creditering verdeeld tussen de First Touch, de Lead Creation Touch, en om het even welke intermediaire vormindieningen die tussen de Eerste Aanraking en de Aanmaak van de Lood plaatsvonden.

Aangezien dit veld betrekking heeft op het object Buyer Touchpoint, is het geen weerspiegeling van het inkomstenkrediet, alleen maar van het toekenningskrediet.

**Telling - W-Vormde** | Buyer Attribution Touchpoint

In dit veld wordt, in decimale vorm, het kredietpercentage weergegeven dat aan een aanraakpunt wordt toegekend volgens een W-Shaped-model.

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

## D {#d}

Datum van melding | Marketo Measure ABTest, Marketo Measure Event

Marketo Measure-gebeurtenis - de datum waarop een gebruiker een specifieke actie op uw website heeft uitgevoerd en een gebeurtenis heeft geactiveerd

Marketo Measure ABTest - de datum waarop een gebruiker heeft deelgenomen aan een A/B-test op uw website

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

## E {#e}

**Naam van de Gebeurtenis** | Marketo Measure-gebeurtenis

In dit veld wordt de naam weergegeven van de actie die de gebeurtenis heeft geactiveerd (bijvoorbeeld Paginaweergave).

**de Waarde van de Gebeurtenis** | Marketo Measure-gebeurtenis

De beschrijving van de gebeurtenis (bijvoorbeeld Homepage)

**Experimentnaam** | Marketo Measure ABTest

In dit veld wordt de naam van het experiment weergegeven (bijvoorbeeld de knop Proefversie)

**Experimentele identiteitskaart** |Marketo Measure AB-test

De unieke identificatiecode voor elk experiment

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

## F {#f}

URL van formulier | Buyer Touchpoint, Buyer Attribution Touchpoint

In dit veld wordt een verkorte versie van de URL van een pagina weergegeven waar het formulier is ingevuld (geen UTM-parameters)

URL formulier - Raw | Buyer Touchpoint, Buyer Attribution Touchpoint

In dit veld wordt de volledige pagina-URL weergegeven waar de formuliervulling is opgetreden, inclusief UTM-parameters

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

## G {#g}

Geo City | Buyer Touchpoint, Buyer Attribution Touchpoint

In dit veld wordt de naam weergegeven van de stad waar de lead/contactpersoon uw website heeft bezocht. Dit wordt gedaan via omgekeerde IP raadpleging.

Geo Land | Buyer Touchpoint, Buyer Attribution Touchpoint

In dit veld wordt weergegeven waar het land waar de lead/contactpersoon uw website heeft bezocht. Dit wordt gedaan via omgekeerde IP raadpleging.

Geo | Buyer Touchpoint, Buyer Attribution Touchpoint

In dit veld wordt het gebied of de staat weergegeven waar de lead/contactpersoon uw website heeft bezocht. Dit wordt gedaan via omgekeerde IP raadpleging.

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

## K {#k}

**identiteitskaart van het Sleutelwoord** | Buyer Touchpoint, Buyer Attribution Touchpoint

Als het aanraakpunt afkomstig is van een betaalde zoekopdracht, wordt in dit veld de trefwoordid van het advertentieplatform (Adwords/BingAds) weergegeven.

Als dit aanraakpunt niet afkomstig is van een betaalde zoekopdracht, is dit veld leeg.

**Keyword MatchType** | Buyer Touchpoint, Buyer Attribution Touchpoint

Als het aanraakpunt afkomstig is van een betaalde zoekopdracht, wordt in dit veld het type van het advertentieplatform (Adwords/Bing) weergegeven.

**Tekst van het Sleutelwoord** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` Als het aanraakpunt afkomstig is van een betaalde zoekopdracht, wordt in dit veld de trefwoordtekst weergegeven van het advertentieplatform (Adwords/BingAds) OF de waarde van de parameter _bk in de URL van de bestemmingspagina.

bijv. `http://info.marketomeasure.com/intro-guide-b2b-marketing-attribution?_bt=12345678&_bk=marketing%20attribution&_bm=p&gclid=ABc123def456ghi789jkl`

`2)` Als het aanraakpunt niet afkomstig is van een betaalde zoekopdracht, wordt in dit veld de utm_term-waarde van de URL van de bestemmingspagina weergegeven.

`http://www.marketomeasure.com/blog/lead-generation?utm_source=linkedin&utm_medium=Social&utm_campaign=ABC%20Blog&utm_content=Lead%20Gen&utm_term=lead%20gen`.

Als het aanraakpunt niet afkomstig is van een betaalde zoekopdracht of als er geen waarde voor utm_term is, is dit veld leeg.

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

## L {#l}

**het Bestaan Pagina** | Buyer Touchpoint, Buyer Attribution Touchpoint

In dit veld wordt de verkorte versie van de URL (geen UTM-parameters) weergegeven van de eerste webpagina die tijdens een websessie wordt bezocht.

**het Bestaan Pagina - Ruwe** | Buyer Touchpoint, Buyer Attribution Touchpoint

In dit veld wordt de volledige URL (inclusief UTM-parameters) weergegeven van de eerste webpagina die tijdens een websessie wordt bezocht.

**Lood** | Buyer Touchpoint, Marketo Measure Person

In dit veld wordt de naam weergegeven van de lead waartoe een aanraakpunt behoort.

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

## M {#m}

**het Marketing Kanaal** | Buyer Touchpoint, Buyer Attribution Touchpoint

In dit veld ziet u de algemene groep marketingactiviteiten of het marketingkanaal waartoe het aanraakpunt behoort (d.w.z. Betaalde zoekopdracht, Direct, Sociaal, enz.). Aanraakpunten worden gegroepeerd op basis van de manier waarop uw kanalen zijn ingesteld in de Marketo Measure App. Voor meer informatie over marketing kanalen, of hoe te opstelling uw kanalen, [ klik hier ](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md).

**het Marketing Kanaal - Weg** | Buyer Touchpoint, Buyer Attribution Touchpoint

In dit veld ziet u het marketingkanaal en het subkanaal waartoe een aanraakpunt behoort. In het onderstaande voorbeeld is Marketing Channel - Path Social.Linkedin, waarbij het marketingkanaal Sociaal is, en het subkanaal LinkedIn.

![](assets/1-3.png)

**Medium** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` Als het aanraakpunt afkomstig is van een betaalde zoekopdracht, wordt het medium van Adwords/BingAds hier weergegeven (d.w.z. CPC).

`2)` Als het aanraakpunt niet afkomstig is van een betaalde zoekopdracht, wordt in dit veld de utm_medium-waarde van de URL van de bestemmingspagina weergegeven.

`3)` Als het aanraakpunt afkomstig is van een offlinecampagne, wordt in dit veld het veld &#39;Type&#39; weergegeven in de Salesforce-campagne.

`4)` Hiermee wordt de waarde Type activiteit ingevuld van de gerelateerde activiteit die het aanraakpunt heeft gegenereerd.

Als geen van de bovenstaande opties aanwezig is, stelt Marketo Measure automatisch een Medium-waarde in.

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

O

**Kans** | Buyer Attribution Touchpoint

In dit veld wordt de mogelijkheid weergegeven waartoe de BAT behoort.

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

P

**Platform** | Buyer Touchpoint, Buyer Attribution Touchpoint

In dit veld worden het type computer of telefoon en het type besturingssysteem weergegeven dat tijdens de websessie is gebruikt.

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

R

**de Pagina van de Verwijzer** | Buyer Touchpoint, Buyer Attribution Touchpoint

In dit veld wordt de URL (zonder UTM-parameters) weergegeven van de laatste webpagina waarop de lead/contactpersoon zich bevond en die hen naar uw website heeft geleid.

Bijvoorbeeld:

- Als het aanraakpunt afkomstig is van een zoekopdracht in het veld Betaald/Organic, wordt de URL van het zoekprogramma weergegeven

- Als het aanraakpunt afkomstig is van Social, wordt in het veld de URL van de sociale website (d.w.z. LinkedIn) weergegeven

**Verwijzerpagina - Ruwe** | Buyer Touchpoint, Buyer Attribution Touchpoint

In dit veld wordt dezelfde informatie weergegeven als bij Referrer Page, behalve in dit veld wordt de volledige verwijzende URL (inclusief UTM-parameters) weergegeven.

**Inkomsten - het Model van de Douane** | Buyer Attribution Touchpoint

Als u een Aangepast kenmerkingsmodel gebruikt, wordt in dit veld het bedrag aan dollaropbrengsten weergegeven dat wordt toegewezen aan een aanraakpunt op basis van het toewijzingspercentage dat is ingesteld in het Aangepaste model.

Als u geen aangepast model gebruikt, is het dollarbedrag 0.

**Inkomsten - eerste aanraking** | Buyer Attribution Touchpoint

In dit veld wordt het bedrag aan dollaropbrengsten weergegeven dat wordt toegewezen aan een aanraakpunt volgens het toewijzingspercentage in het Eerste aanraakmodel.

**Inkomsten - Volledige Weg** | Buyer Attribution Touchpoint

In dit veld wordt het bedrag aan dollaropbrengsten weergegeven dat wordt toegewezen aan een aanraakpunt volgens het toewijzingspercentage in het volledige padmodel.

**Inkomsten - de Aanraking van de Aanmaak van de Lood** | Buyer Attribution Touchpoint

In dit veld wordt het bedrag aan dollaropbrengsten weergegeven dat aan een aanraakpunt wordt toegewezen op basis van het toewijzingspercentage in het Aanmaakmodel voor lead.

**Inkomsten - U-Vormd** | Buyer Attribution Touchpoint

In dit veld wordt het bedrag aan dollaropbrengsten weergegeven dat wordt toegewezen aan een aanraakpunt volgens het toewijzingspercentage in het U-Vormd model.

**Inkomsten - W-Vormd** | Buyer Attribution Touchpoint

In dit veld wordt het bedrag van de dollaropbrengsten weergegeven dat aan een aanraakpunt wordt toegewezen op basis van het toewijzingspercentage in het model W-Shaped.

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

S

**Campagne van Salesforce** | Buyer Touchpoint, Buyer Attribution Touchpoint

In dit veld wordt de Salesforce-campagne weergegeven waartoe het aanraakpunt behoort.

**Woorden van het Onderzoek** | Buyer Touchpoint, Buyer Attribution Touchpoint

Als het aanraakpunt afkomstig is van betaald of biologisch zoeken, wordt in dit veld de zoekuitdrukking weergegeven die in het zoekprogramma is getypt. Vanwege privacyredenen is deze informatie echter meestal niet beschikbaar.

**Segment** | Buyer Attribution Touchpoint

In dit veld worden de segmenten weergegeven waartoe het aanraakpunt behoort. Dit hangt af van de manier waarop u de segmentatieregels in de Marketo Measure-app hebt geconfigureerd.

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

T

**Datum van het Aanraakpunt** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` Als het aanraakpunt afkomstig is van een onlinebron, worden in dit veld de datum en tijd weergegeven waarop het aanraakpunt is opgetreden.

`2)` Als het aanraakpunt afkomstig is van een offlinegebeurtenis, worden in dit veld de datum en tijd weergegeven die zijn ingesteld in de Salesforce-campagne of vanuit het datumveld dat is geselecteerd in de Campagne Sync Rules.

`3)` Als het aanraakpunt afkomstig is van een activiteit, worden in dit veld de datum en tijd weergegeven van het veld dat is geselecteerd als aanraakpunt Datum in de activiteitregels.

**Datum van het Aanraakpunt (FT)** | Buyer Touchpoint

Dit is hetzelfde veld als Aanraakpuntdatum, maar in dit veld worden specifiek de datum en tijd weergegeven waarop het eerste aanraakpunt is opgetreden.

**Datum van het Aanraakpunt (LC)** | Buyer Touchpoint

Dit is hetzelfde veld als Aanraakpuntdatum. In dit veld worden echter specifiek de datum en tijd weergegeven waarop het aanraakpunt voor aanwijzen is opgetreden.

**Positie van het Aanraakpunt** | Buyer Touchpoint, Buyer Attribution Touchpoint

In dit veld wordt de positie van het aanraakpunt weergegeven. De positie van het aanraakpunt weerspiegelt de belangrijkste mijlpalen in de reis van de klant (FT, Form, LC, OC, Closed). De positie van het aanraakpunt is afhankelijk van het tijdstip waarop het zich tijdens de reis van de klant heeft voorgedaan en één aanraakpunt kan meerdere posities hebben. De verschillende posities van aanraakpunten zijn als volgt:

First Touch (FT) - De allereerste marketinginteractie die iemand heeft met uw merk

Lood Creation (LC) - De allereerste bekende marketinginteractie (meestal een formulierverzending of een Salesforce Campagne-inclusie)

Formulier - Wanneer een bezoeker een online formulier invult

Opportunity Creation (OC) - De marketinginteractie die het dichtst bij het maken van de Opp ligt

Gesloten - De marketinginteractie die het dichtst bij wanneer Opp wordt gesloten (Won of Verloren)

**Aanraakpunt Source** | Buyer Touchpoint, Buyer Attribution Touchpoint

`1)` Als het aanraakpunt afkomstig is van een betaalde zoekopdracht, wordt in dit veld de naam van het advertentieplatform weergegeven (AdWords/BingAds)

`2)` Als het aanraakpunt afkomstig is van een organische zoekopdracht, wordt in dit veld de naam van de zoekfunctie weergegeven

`3)` Als #1 of #2 niet aanwezig is en de utm_source-waarde aanwezig is in de URL van de bestemmingspagina voor het aanraakpunt, wordt die waarde hier weergegeven

`4)` Dit wordt gevuld als CRM-campagne als het aanraakpunt is gegenereerd op basis van een CRM-campagne.

`5)` Dit wordt gevuld als CRM-activiteit als het aanraakpunt wordt gegenereerd op basis van een CRM-activiteit.

Als geen van bovenstaande velden wordt ingevuld, wordt dit veld ingevuld als &#39;Web Direct&#39; of &#39;Web&#39;.

**Aanraakpunt Source (FT)** | Buyer Touchpoint

Dit is hetzelfde veld als TouchPoint Source. In dit veld wordt echter specifiek de bron van het First Touch-aanraakpunt weergegeven.

**Aanraakpunt Source (LC)** | Buyer Touchpoint

Dit is hetzelfde veld als Touchpoint Source. In dit veld wordt echter specifiek de bron van het aanraakpunt voor het maken van leads weergegeven.

**Type Aanraakpunt** | Gevonden op de Buyer Touchpoint en Buyer Attribution Touchpoint.

In dit veld wordt het type interactie van het aanraakpunt weergegeven. Het wordt weergegeven als: Webbezoek, Webformulier of Webchat voor JavaScript-aanraakpunten. Voor CRM Campaign Touchpoints wordt deze weergegeven als CRM. Het wordt gevuld met het taak- of gebeurtenistype voor de aanraakpunten met activiteit.

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

U

**UniqueId** | Buyer Touchpoint, Buyer Attribution Touchpoint

De unieke id die aan elk aanraakpunt is gekoppeld

**identiteitskaart van de Gebruiker** | Marketo Measure ABTest

De unieke identificatiecode van optimalisatie voor elk gebruik

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)

## V {#v}

**Verandering** | Marketo Measure ABTest

De naam van de variatie van de A/B-test

**identiteitskaart van de Variatie** | Marketo Measure ABTest

De unieke identificatiecode voor elke variant van de A/B-test.

[Klik hier om terug te keren naar de bovenkant van de pagina](#top)
