---
unique-page-id: 37356395
description: "[!DNL Marketo Engage] Integratie van mensen - [!DNL Marketo Measure]"
title: "[!DNL Marketo Engage] Personen integreren"
exl-id: 51930e84-4ff8-4e35-9d44-ea017c24b051
feature: Integration
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 0%

---

# [!DNL Marketo Engage] Integratie van mensen {#marketo-engage-people-integration}

De integratie van het Marketo-volk maakt [!DNL Marketo Measure] om te beginnen met het downloaden van mensen uit Marketo en hun bijgehouden sessies aan het individu te koppelen en aanraakpunten aan hun afspraken toe te wijzen. Historisch [!DNL Marketo Measure] kon slechts aanraakpunten toewijzen aan een persoon van de BCR, zodat kunnen marketeers hun marketinginspanningen sneller meten in plaats van te wachten op een podium of een trigger voor synchronisatie met de BCR.

## Vereisten {#requirements}

* Production Marketo-instantie
* Productie [!DNL Salesforce] of [!DNL Microsoft Dynamics] instance
* Betaald [!DNL Marketo Measure] abonnement
* SOLR ingeschakeld (bereik naar [Marketo-ondersteuning](https://nation.marketo.com/t5/Support/ct-p/Support) om dit ingeschakeld te hebben)

## Hoe het werkt {#how-it-works}

Als huidige klant [!DNL Marketo Measure] downloadt al mensen van je CRM. Het standaardproces is dat [!DNL Marketo Measure] downloadt de mensen en wijst het e-mailadres toe aan een Webzitting die wij via bizible.js hebben gevolgd.

Met de introductie van het downloaden van Marketo-personen, [!DNL Marketo Measure] is nu in staat websessies toe te wijzen aan een grotere groep personen, personen die niet zijn gesynchroniseerd met de CRM. We zien dit vaak als gevolg van interne processen die wachten tot mensen een bepaalde status bereiken voordat ze naar de CRM worden geduwd.

Wanneer [!DNL Marketo Measure] Met succes wordt de Marketo-persoon aan een websessie toegewezen. Tijdens de verwerking worden relevante aanraakpunten voor de persoon gegenereerd, die uiteindelijk worden gemeld in [!DNL Marketo Measure Discover]. Als die Marketo-persoon naar de CRM wordt geduwd, [!DNL Marketo Measure] zal het dubbele scenario behandelen en wij zullen touchpoint voor de persoon van CRM opnieuw creëren, en zullen de aanvankelijke reeks als &quot;duplicaat merken.&quot;

Om deze duplicaten te kunnen detecteren, moet u ervoor zorgen dat [!DNL Marketo-Salesforce] of [!DNL Marketo-Dynamics] Met sync worden de ID voor lead en contact op de Marketo-persoon ingevuld. Als identiteitskaart behoorlijk synchroniseert, zou u CRM Id op het Persoon verslag moeten kunnen zien, als dit:

![](assets/5a.png)

![](assets/5b.png)

Klanten hebben de mogelijkheid om de volledige set Marketo-personen en CRM-personen te rapporteren binnen [!DNL Marketo Measure] Detecteren. Als u in het melden van de mensen van CRM slechts geinteresseerd bent, adviseren wij het creëren van een Segment om hen te filtreren.

## [!DNL Marketo Measure Discover] {#marketo-measure-discover}

Bij rapportage over leads (personen) in [!DNL Marketo Measure Discover], je ziet het totaal van je Marketo- en CRM-leads. Als u alleen op Marketo-personen of alleen CRM-leads wilt rapporteren, wilt u een Segmentcategorie voor uw bron maken en vervolgens Segmentregels voor Marketo en CRM maken met het veld Bronsysteem om de regel te definiëren. Nadat u de segmenten hebt gemaakt, ziet u de categorie Bron die beschikbaar is om over de segmenten te filteren [!DNL Marketo Measure Discover] dashboards.

![](assets/bizible-discover-1.png)

![](assets/bizible-discover-2.png)

## Veldtoewijzingen {#field-mappings}

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th><p><strong>biz_leads</strong></p></th> 
   <th><p><strong>Marketo</strong></p></th> 
  </tr> 
  <tr> 
   <td><p>ID</p></td> 
   <td><p>id</p></td> 
  </tr> 
  <tr> 
   <td><p>MODIFIED_DATE</p></td> 
   <td><p>updatedAt<strong>*</strong></p></td> 
  </tr> 
  <tr> 
   <td><p>CREATED_DATE</p></td> 
   <td><p>createdAt</p></td> 
  </tr> 
  <tr> 
   <td><p>EMAIL</p></td> 
   <td><p>email</p></td> 
  </tr> 
  <tr> 
   <td><p>WEB_SITE</p></td> 
   <td><p>website</p></td> 
  </tr> 
  <tr> 
   <td><p>ONDERNEMING</p></td> 
   <td><p>bedrijf</p></td> 
  </tr> 
  <tr> 
   <td><p>IS_CONVERTED</p></td> 
   <td><p>nvt</p></td> 
  </tr> 
  <tr> 
   <td><p>ACCOUNT_ID</p></td> 
   <td><p>Account-ID (L2A)</p></td> 
  </tr> 
  <tr> 
   <td><p>BIZIBLE_STAGE</p></td> 
   <td><p>Status</p></td> 
  </tr> 
  <tr> 
   <td><p>IS_DELETED</p></td> 
   <td><p>true/false</p></td> 
  </tr> 
 </tbody> 
</table>

*Er is een bekend gedragsprobleem waarbij velden van de Marketo Company-entiteit geen invloed hebben op de updateAt-waarde van de persoon, zodat relevante velden zoals Website of Bedrijf worden bijgewerkt. [!DNL Marketo Measure] weet niet dat deze waarden worden gewijzigd omdat de datum-/tijdwaarde van de updateAt niet wordt bijgewerkt. Dit is van invloed op de ABM-functie, waar we geen nieuwe gegevens zouden hebben om de Account for the lead op te lossen. Er is momenteel geen oplossing, maar er zijn plannen om dit in de toekomst aan te pakken.

## Veelgestelde vragen {#faq}

**Waarom zijn mijn loodtellingen verschillend tussen mijn CRM en [!DNL Marketo Measure Discover]?**

Omdat deze integratie ons in staat stelt aanraakpunten te maken voor leads die we direct uit Marketo hebben geïmporteerd, kunnen er leads zijn die niet werden gesynchroniseerd met de CRM zodat de telling binnen Discover hoger zou kunnen zijn dan de CRM omdat aanraakpunten alleen worden geduwd voor de CRM Leads.

**Hoe vervangt dit mijn gegevens?**

Met deze integratie worden de gegevenssets in uw huidige [!DNL Marketo Measure] -instantie zodat er niets wordt vervangen. Wat we van je huidige CRM Leads zouden verwachten, is dat als we de 2 jaar Marketo Leads downloaden, we dat Lead-record gewoon zouden bijwerken om te laten zien dat er ook een match was met Marketo Lead. Dat gebeurt allemaal op de achtergrond en de aanraakpunten zullen naar verwachting hetzelfde blijven. We zouden ook verwachten dat we meer aanraakpunten zouden zien vanwege de in aanmerking komende Marketo Leads. Als we websessies kunnen vinden die overeenkomen met die Marketo-mensen, dan zien we de aanraakpunten geteld in [!DNL Marketo Measure].

**Kan ik mijn mensen alleen laten downloaden van Marketo en de CRM-verbinding uitschakelen?**

Op dit moment, nee. We hebben deze optie in de toekomst, maar we moeten andere fasen van deze Marketo-integratie uitbouwen, zodat we de programma&#39;s, mogelijkheden en deals van Marketo met elkaar kunnen verbinden [!DNL Marketo Measure].

**Importeer je AL mijn Marketo-mensen?**

Op dit moment zullen we ten vroegste mensen importeren vanaf 1 januari 2018, zodat we minimaal twee jaar aan gegevens hebben, wat hetzelfde gedrag is als we afdwingen van CRM-downloads. We implementeren verbeterd gedrag om een schuivend venster van twee jaar te downloaden zodra de Marketo-verbinding tot stand is gebracht.

We filteren ook niet voor andere soorten mensen, dus alle mensen binnen het tweejarige venster worden geïmporteerd en komen in aanmerking voor aanraakpunten.

**Wat is SOLR en waarom moet ik het toegelaten hebben om deze eigenschap te gebruiken?**

Het inschakelen van SOLR voor uw Marketo-instantie is een triviale stap die hardwareruimte in Marketo opent zodat uw abonnement de [!DNL Marketo Measure] integratie. Zonder toegelaten SOLR, hebben wij geen toegang tot bepaalde vraag die ons anders zou toestaan om de aangewezen mensen van uw instantie van Marketo te downloaden.
