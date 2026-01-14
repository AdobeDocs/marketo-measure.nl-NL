---
description: '[!DNL Marketo Engage] Integratie van personen -  [!DNL Marketo Measure]'
title: '[!DNL Marketo Engage] Integratie van personen'
exl-id: 51930e84-4ff8-4e35-9d44-ea017c24b051
feature: Integration
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '912'
ht-degree: 0%

---

# [!DNL Marketo Engage] Integratie van personen {#marketo-engage-people-integration}

Dankzij de integratie van Marketo-personen kan [!DNL Marketo Measure] beginnen met het downloaden van personen uit Marketo en beginnen met het koppelen van hun bijgehouden sessies aan het individu en het toewijzen van aanraakpunten aan hun afspraken. In het verleden kon [!DNL Marketo Measure] alleen aanraakpunten toewijzen aan een persoon van de CRM. Dit helpt marketeers hun marketingactiviteiten sneller te meten in plaats van te wachten op een podium of een trigger om deze te synchroniseren met de CRM.

## Vereisten {#requirements}

* Production Marketo-instantie
* Production [!DNL Salesforce] of [!DNL Microsoft Dynamics] -instantie
* Alle betaalde [!DNL Marketo Measure] -abonnementen
* SOLR toegelaten (reik uit aan [&#x200B; de Steun van Marketo &#x200B;](https://nation.marketo.com/t5/Support/ct-p/Support) om dit te hebben toegelaten)

## Hoe het werkt {#how-it-works}

Als huidige klant downloadt [!DNL Marketo Measure] al personen van uw CRM. Het standaardproces is dat [!DNL Marketo Measure] de mensen downloadt en het e-mailadres toewijst aan een Webzitting die wij via bizible.js hebben gevolgd.

Met de introductie van het downloaden van Marketo-personen kan [!DNL Marketo Measure] nu websessies toewijzen aan een groter aantal personen, personen die niet zijn gesynchroniseerd met de CRM. We zien dit vaak als gevolg van interne processen die wachten tot mensen een bepaalde status bereiken voordat ze naar de CRM worden geduwd.

Wanneer [!DNL Marketo Measure] de Marketo-persoon met succes toewijst aan een websessie, worden tijdens de verwerking relevante aanraakpunten voor de persoon gegenereerd. Deze zijn uiteindelijk te melden in [!DNL Marketo Measure Discover] . Als die Marketo-persoon naar de CRM wordt geduwd, zal [!DNL Marketo Measure] het gedupliceerde scenario afhandelen en zullen we het aanraakpunt voor de CRM-persoon opnieuw maken en de eerste set markeren als &#39;duplicate&#39;.

Om deze duplicaten te kunnen detecteren, moet u ervoor zorgen dat uw [!DNL Marketo-Salesforce] - of [!DNL Marketo-Dynamics] -sync de ID van de lead en contactpersoon vult op de Marketo-persoon. Als identiteitskaart behoorlijk synchroniseert, zou u CRM Id op het Persoon verslag moeten kunnen zien, als dit:

![&#x200B; zodat wij deze duplicaten ontdekken, zorg uw &#x200B;](assets/marketo-engage-programs-06.png) ervoor

![&#x200B; zodat wij deze duplicaten ontdekken, zorg uw &#x200B;](assets/marketo-engage-programs-07.png) ervoor

Klanten kunnen de volledige set Marketo-personen en CRM-personen rapporteren in [!DNL Marketo Measure] Discover. Als u in het melden van de mensen van CRM slechts geinteresseerd bent, adviseren wij het creëren van een Segment om hen te filtreren.

## [!DNL Marketo Measure Discover] {#marketo-measure-discover}

Bij rapportage over leads (personen) in [!DNL Marketo Measure Discover] wordt het totaal van uw Marketo- en CRM-leads weergegeven. Als u alleen Marketo-personen of alleen CRM-leads wilt rapporteren, wilt u een Segmentcategorie voor uw bron maken en vervolgens Segmentregels voor Marketo en CRM maken met het veld Source System om de regel te definiëren. Nadat u de segmenten hebt gemaakt, ziet u de Source-categorie die beschikbaar is om te filteren over de [!DNL Marketo Measure Discover] -dashboards.

![&#x200B; wanneer het melden van lood (mensen) in Marketo Measure Discover, zult u &#x200B;](assets/bizible-discover-1.png)

![&#x200B; wanneer het melden van lood (mensen) in Marketo Measure Discover, zult u &#x200B;](assets/bizible-discover-2.png)

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
   <td><p>updatedAt <strong>*</strong></p></td>
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

*Er is een bekend gedragsprobleem waarbij velden van de Marketo Company-entiteit geen invloed hebben op de updateAt-waarde van de persoon. Als relevante velden zoals Website of Bedrijf worden bijgewerkt, weet [!DNL Marketo Measure] niet dat deze waarden worden gewijzigd omdat de updateAt-datum/tijdwaarde niet wordt bijgewerkt. Dit is van invloed op de ABM-functie, waar we geen nieuwe gegevens zouden hebben om de Account for the lead op te lossen. Er is momenteel geen oplossing, maar er zijn plannen om dit in de toekomst aan te pakken.

## Veelgestelde vragen {#faq}

**waarom verschillen mijn loodtellingen tussen mijn CRM en [!DNL Marketo Measure Discover]?**

Omdat deze integratie ons in staat stelt aanraakpunten te maken voor leads die we direct uit Marketo hebben geïmporteerd, kunnen er leads zijn die niet werden gesynchroniseerd met de CRM zodat de telling binnen Discover hoger zou kunnen zijn dan de CRM omdat aanraakpunten alleen worden geduwd voor de CRM Leads.

**hoe vervangt dit mijn gegevens?**

Deze integratie voegt de gegevenssets in uw huidige [!DNL Marketo Measure] -instantie samen, zodat niets wordt vervangen. Wat we van je huidige CRM Leads zouden verwachten, is dat als we de 2 jaar Marketo Leads downloaden, we dat Lead-record gewoon zouden bijwerken om te laten zien dat er ook een match was met Marketo Lead. Dat gebeurt allemaal op de achtergrond en de aanraakpunten zullen naar verwachting hetzelfde blijven. We zouden ook verwachten dat we meer aanraakpunten zouden zien vanwege de in aanmerking komende Marketo Leads. Als we websessies kunnen vinden die overeenkomen met die Marketo-mensen, dan zien we de aanraakpunten geteld in [!DNL Marketo Measure] .

**kan ik mijn mensen slechts hebben die van Marketo worden gedownload en van de verbinding van CRM worden afgesneden?**

Op dit moment, nee. We hebben deze optie in de toekomst, maar we moeten andere fasen van deze Marketo-integratie uitbouwen zodat we de programma&#39;s, mogelijkheden en deals van Marketo met [!DNL Marketo Measure] kunnen verbinden.

**voert u ALLE van mijn mensen van Marketo in?**

Op dit moment zullen we ten vroegste mensen importeren vanaf 1 januari 2018, zodat we minimaal twee jaar aan gegevens hebben, wat hetzelfde gedrag is als we afdwingen van CRM-downloads. We implementeren verbeterd gedrag om een schuivend venster van twee jaar te downloaden zodra de Marketo-verbinding tot stand is gebracht.

We filteren ook niet voor andere soorten mensen, dus alle mensen binnen het tweejarige venster worden geïmporteerd en komen in aanmerking voor aanraakpunten.

**wat SOLR is en waarom moet ik het hebben toegelaten om deze eigenschap te gebruiken?**

Het inschakelen van SOLR voor uw Marketo-instantie is een triviale stap die hardwareruimte opent in Marketo, zodat uw abonnement de [!DNL Marketo Measure] -integratie kan gebruiken. Zonder toegelaten SOLR, hebben wij geen toegang tot bepaalde vraag die ons anders zou toestaan om de aangewezen mensen van uw instantie van Marketo te downloaden.
