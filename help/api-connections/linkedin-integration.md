---
description: Richtlijnen voor LinkedIn-integratie voor Marketo Measure-gebruikers
title: LinkedIn-integratie
exl-id: 705209ef-1ece-496c-ac2f-6a31055bd993
feature: APIs, Integration
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '2694'
ht-degree: 0%

---

# LinkedIn-integratie {#linkedin-integration}

## Overzicht {#overview}

De [!DNL Marketo Measure] integratie met LinkedIn bestaat uit twee delen:

Gesponsorde inhoud: dankzij de integratie van gesponsorde inhoud kunnen [!DNL Marketo Measure] bestemmings-URL&#39;s coderen op [!DNL LinkedIn] advertenties, waardoor [!DNL Marketo Measure] uiteindelijk de gebruiker door de volledige reis met het aanraakpunt kan volgen en de activiteit weer kan toewijzen aan de specifieke [!DNL LinkedIn] -campagne en Creative. Dit biedt klanten inzicht in de ROI van hun [!DNL LinkedIn] activiteit.

Generaal-leider Forms: Door de integratie met LinkedIn&#39;s leider-gen Forms krijgt Marketo Measure insight in formulieren die zijn ingediend via het LinkedIn-platform. Deze formuliervullingen worden vergeleken met leads van uw CRM- of [!DNL Marketo Engage] -instantie, zodat ze in aanmerking komen voor toewijzing. Met insight in de Campagne, Creative, en Vorm die hielpen om de vormen te produceren, kunnen de teams hun LinkedIn marketing en advertentie uitgaven verder optimaliseren.

## Beschikbaarheid {#availability}

Beschikbaar voor alle gebruikers.

## Vereisten {#requirements}

### Rollen voor Campagnerbeheer

[!DNL Marketo Measure] kan alleen kostengegevens voor Advertentiegegevens en -advertenties downloaden als u een van de volgende rollen hebt in Campagnebeheer:

* Factureringsbeheer
* Accountmanager
* Campagnebeheer

Leer meer: [&#x200B; Rollen en Functies van de Gebruiker in de Manager van de Campagne &#x200B;](https://www.linkedin.com/help/lms/answer/a425731/user-roles-and-functions-in-campaign-manager).

### Betaalde rollen voor mediabeheer

Als u wilt dat [!DNL Marketo Measure] gesponsorde Creative Cloud kan maken/bijwerken, moet u een van de volgende rollen voor Gesteunde media Admin hebben:

* Poster met gesponsorde inhoud
* Generaal-leider Forms Manager

Leer meer: [&#x200B; LinkedIn Rollen van Admin van de Pagina &#x200B;](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admin-roles-overview).

Er zijn andere [!DNL LinkedIn] rollen die wij **niet** voor onze integratie vereisen. Deze rollen worden vaak verward met de vereiste rollen, zodat is er een verschil!

### Paginabeheerrollen

Als u wilt dat [!DNL Marketo Measure] leads kan downloaden/integreren van lead gen-gen-formulieren, hebt u de volgende rol voor Paginanummer nodig:

* Super Admin

Leer meer: [&#x200B; LinkedIn Rollen van Admin van de Pagina &#x200B;](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admin-roles-overview).

## LinkedIn-advertentietypen {#linkedin-ad-types}

[!DNL Marketo Measure] biedt ondersteuning voor:

Met gesponsorde inhoud kunt u inhoud leveren aan de [!DNL LinkedIn] -feed van leden die verder gaan dan diegenen die uw bedrijf volgen. Gesponsorde inhoud kan worden gericht op een specifiek publiek en kan adverteerders helpen [!DNL LinkedIn] leden te bereiken, waar en wanneer ze zich op het [!DNL LinkedIn] -platform engageren voor desktops, mobiele apparaten en tablets. Gesponsorde inhoud wordt ondersteund door Gen Forms.

De typen inhoud en indelingen die door [!DNL Marketo Measure] worden ondersteund, zijn Single Image Ads en Video Ads (via Lead Gen Forms). Vanwege de complexiteit van het schema ondersteunen we Carousel-advertenties niet.

[!DNL Marketo Measure] biedt geen ondersteuning voor gesponsorde berichten, tekstadvertenties of dynamische advertenties.

![&#x200B; Marketo Measure steunt geen Gesponsord Overseinen, de Advertentie van de Tekst, of Dynamisch &#x200B;](assets/bizible-guide-1.png)

>[!TIP]
>
>Voor om het even welk van uw Campagnes/uitgaven die uit een niet-Gesponsorde inhoudsbron (zoals het Type van Campagne van &quot;Tekst Ad&quot;of &quot;Gesponsorde InMail&quot;) voortkomen, [!DNL Marketo Measure] steunt _niet_ inherent het volgen van deze Types van Campagne. Als u de uitgaven voor campagnes zoals deze naast uw &quot;Gesponsorde Inhoud&quot;uitgaven wilt volgen, ben zeker om van onze uitgave van de Marketing CSV gebruik te maken om gezegd uitgaven manueel te registreren.

## Hoe het werkt: gesponsorde inhoud {#how-it-works-sponsored-content}

>[!NOTE]
>
>Voordat u de functie voor het eerst gaat gebruiken, moet u deze instelling inschakelen door naar [!DNL Marketo Measure] [!UICONTROL Settings] > [!UICONTROL Integrations] > [!UICONTROL Ads] > [!UICONTROL Enable LinkedIn Lead Gen Forms] te navigeren.

### [!DNL LinkedIn's] Unieke vereisten voor automatische labeling

[!DNL Marketo Measure] kan u helpen de prestaties van uw [!DNL LinkedIn] -campagne te volgen door uw bestemmingspagina&#39;s automatisch te labelen.

[!DNL Marketo Measure] zoekt naar creatieve elementen met een unieke LinkedIn Share en voegt een `?_bl={creativeId}` -parameter toe aan het einde ervan.

### Delen kopiëren

Met deze [!DNL Marketo Measure/LinkedIn] -integratie vragen we dat klanten bestaande Creative Cloud niet kopiëren of dupliceren. Als Delen worden gevonden en slechts op één Creative worden gebruikt, kan [!DNL Marketo Measure] de Delen labelen zonder dat Creative of Shares opnieuw hoeft te worden gemaakt en blijft alle advertentiegeschiedenis (indrukken, klikken, delen) behouden.

Zodra een Delen op meerdere Creative Cloud wordt gedeeld, moet [!DNL Marketo Measure] een proces doorlopen om te pauzeren, te kopiëren en opnieuw te labelen om een unieke set te kunnen maken. [!DNL Marketo Measure] pauzeert en archiveert live creatieve producten en wist daarom de advertentiegeschiedenis, inclusief indrukken, klikken en sociale aandelen, om alles op de juiste manier te labelen.

Als u voorwaarts gaat, raadt [!DNL Marketo Measure] u aan geen [!DNL LinkedIn] -aandelen te dupliceren en alle creatieve en andere delen zo uniek mogelijk te houden, zodat we eenvoudig onze &#39;tracking&#39; kunnen toevoegen zonder dat u de advertentiegeschiedenis hoeft te wissen.

### Kortere URL&#39;s

De reden voor de extra stap is dat LinkedIn bestemmings-URL&#39;s een verkorte URL (bit.ly, goog.le, enz.) toestaat, wat betekent dat [!DNL Marketo Measure] de lange, opgeloste URL niet ziet en [!DNL Marketo Measure] volgparameters aan een opgeloste URL moet toevoegen. Om dit probleem te verhelpen, zoekt [!DNL Marketo Measure] naar verkorte URL&#39;s voordat u een advertentie opnieuw maakt, breidt het de URL uit en maakt het vervolgens de nieuwe advertentie met de opgeloste URL en alle bijbehorende parameters, zodat [!DNL Marketo Measure] tags kan toevoegen. Als u een nieuwe advertentie maakt, wordt de historie gewist (indrukken, klikken en delen). Daarom is het nodig dat u toestemming hebt om ingekorte URL&#39;s van tags te voorzien.

Als u veel gebruik maakt van verkorte URL&#39;s, kan dit ernstige gevolgen hebben voor uw creatieve projecten. We raden u aan geen verkorte URL&#39;s meer te gebruiken, zodat [!DNL Marketo Measure] de bestemmingspagina&#39;s kan labelen zonder dat u nieuwe advertenties hoeft te maken en Advertentiegeschiedenis hoeft te wissen.

### Het proces

Laten we beginnen met een paar voorbeelden. Laten we zeggen dat we...

Creative A : Share 123\
Creative B : Share 234\
Creative C: Share 234\
Creative D : Share 234

![&#x200B; Creative D: Deel 234 &#x200B;](../assets/marketo-engage-activities-05.png)

`1)` [!DNL Marketo Measure] doorzoekt eerst alle campagnes, Creative Cloud en shares met de status Actief. In [!DNL Marketo Measure] worden geen tags toegewezen voor gepauzeerde, gearchiveerde of geannuleerde advertenties. Als een advertentie is gepauzeerd, wordt deze ingesteld op [!UICONTROL active] , labelen we deze zodra de advertentie weer actief is. Als we een uniek Delen kunnen vinden, wat betekent dat het niet wordt gebruikt voor meerdere Creative Cloud of Campagnes (bijvoorbeeld Creative A: Share 123), voegt [!DNL Marketo Measure] onze aangepaste parameter `>> ?_bl={creativeId}` toe aan de gedeelde URL.

`2)` Nu als het Delen is gedeeld en zijn unieke karakter verliest (bijvoorbeeld Creative B: Share 234 en Creative C: Share 234 en Creative D: Share 234), zal [!DNL Marketo Measure] alle gelijkaardige creatieve personen pauzeren en archiveren (zoals Creative B, Creative C en Creative D).

`3)` [!DNL Marketo Measure] maakt drie nieuwe creatieve projecten, Creative E, Creative F en Creative G, die de gearchiveerde inhoud van Creative B kopiëren.

`4)` [!DNL Marketo Measure] maakt ook drie nieuwe shares, Share 345, Share 456 en Share 567, waarmee de inhoud van Share 234 wordt gekopieerd, maar waarvoor een eigen unieke `?_bl` -tag wordt gebruikt.

`5)` [!DNL Marketo Measure] moet regelmatig controleren of Delen niet worden gedeeld en als dat het geval is, wordt het proces opnieuw gestart in stap 2 hierboven.

>[!NOTE]
>
>Dit betekent dat onze klanten de advertentiegeschiedenis van Creative B zullen verliezen: Share 234, Creative C: Share 234 en Creative D: Share 234 omdat het nu opnieuw wordt gemaakt met Creative E: Share 345, Share F: Share 456, en Creative G: Share 567 respectievelijk.

![&#x200B; Uitvoerend dit zal betekenen dat onze klanten de advertentiegeschiedenis &#x200B;](assets/api-connections-01.png) zullen verliezen

## Hoe het werkt: Gen-leider Forms {#how-it-works-lead-gen-forms}

[!DNL Marketo Measure] kan u helpen de prestaties van uw [!DNL LinkedIn] -campagne te volgen door uw bestemmingspagina&#39;s automatisch te labelen.

[!DNL Marketo Measure] zoekt naar creatieve elementen met een unieke LinkedIn Share en voegt een `?_bl={creativeId}` -parameter toe aan het einde ervan.

Via de API voor het toevoegen van formulieren en de API voor het toevoegen van formulierreacties kunnen we formulierverzendgegevens verzamelen voor een advertentieaccount en het e-mailadres koppelen aan een lead van de CRM of Marketo.[!DNL LinkedIn's]

LinkedIn-formulieren kunnen meerdere e-mailadressen bevatten. Wanneer we formulierreacties downloaden, zoeken we naar e-mailadressen met de volgende prioriteit: Werk-e-mail, E-mailadres (primair formulierveld) of aangepaste velden met een geldige e-mailwaarde.

Ongeacht de Campagne- of Creative-status, zullen alle reacties op formulieren resulteren in een aanraakpunt. [!DNL Marketo Measure] heeft een terugkijkbeperking van 90 dagen, zodat [!DNL Marketo Measure] geen toegang heeft tot reacties op formulieren die ouder zijn dan 90 dagen, maar hoe langer de integratie van [!DNL Marketo Measure] en [!DNL LinkedIn] is ingeschakeld, des te groter de aantal aanraakpunten van het Formulier Lead Gen zijn zichtbaar via [!DNL Marketo Measure] .

>[!NOTE]
>
>LinkedIn-kosten worden nog steeds gedownload als onderdeel van campagnes voor gesponsorde inhoud.


Voordat de integratie van [!DNL Marketo Measure] en LinkedIn-leider Forms bestond, was het gebruikelijk dat klanten hun formulierverzendingen naar een Marketo-programma en/of CRM-campagne zouden doorsturen om de formulieren te volgen en deze toe te wijzen aan deze activiteiten. Nadat de instelling voor Gen-leider Forms is ingeschakeld, willen we ervoor zorgen dat deze formulierverzendingen niet dubbel worden geteld. Controleer het volgende:

* Het veld &quot;Aanraakpunten koper inschakelen&quot; in het CRM-object is ingesteld op &quot;Geen&quot; of &quot;Alle leden van campagne uitsluiten&quot;
* Gerelateerde regels voor Marketo-programma&#39;s of Marketo-activiteiten bijwerken
* Verwante regels voor CRM-campagnes bijwerken

>[!NOTE]
>
>LinkedIn API heeft een terugkijkbeperking van 90 dagen, zodat als u Marketo of de regels van CRM gebruikt, wordt geadviseerd dat u de einddatum op de regel aan 90 dagen voorafgaand aan de datum plaatst u de integratie in [!DNL Marketo Measure] toeliet.

## Details aanraakpunt {#touchpoint-details}

Nadat [!DNL Marketo Measure] uw landingspagina op LinkedIn creatief met succes heeft geëtiketteerd, kunt u de opgeloste advertentiegegevens op touchpoint bekijken. Hier is de afbeelding van gegevenswaarden die u zou moeten verwachten te zien:

<table>
 <colgroup>
  <col>
  <col>
 </colgroup>
 <tbody>
  <tr>
   <th style="width:30%">Aanraakpuntveld</th>
   <th>Samplewaarde</th>
  </tr>
  <tr>
   <td>Advertentie-id</td>
   <td>84186224</td>
  </tr>
  <tr>
   <td>Inhoud toevoegen</td>
   <td>copy-1-image-2-man 95% van de #B2B-marketers beschouwt de strategie voor het creëren van vraag als succesvol. Meer informatie: [!DNL https] /lnkd.in/jgdi50vKrgv</td>
  </tr>
  <tr>
   <td>Groep-id toevoegen</td>
   <td>(leeg)</td>
  </tr>
  <tr>
   <td>Naam advertentiegroep</td>
   <td>(leeg)</td>
  </tr>
  <tr>
   <td>Campagne-id toevoegen</td>
   <td>138949954</td>
  </tr>
  <tr>
   <td>Naam advertentiecampagne</td>
   <td>SU - COM-accounts - vraagvaardigheden</td>
  </tr>
  <tr>
   <td>Doel-URL toevoegen <b>*</b></td>
   <td>https://www.adobe.com/marketing-attribution-for-demand-generation-leaders?_bl=84186217</td>
  </tr>
  <tr>
   <td>URL van formulier</td>
   <td>info.bizible.com/demo</td>
  </tr>
  <tr>
   <td>URL formulier - Raw</td>
   <td>info.bizible.com/demo</td>
  </tr>
  <tr>
   <td>Trefwoord-id</td>
   <td>(leeg)</td>
  </tr>
  <tr>
   <td>Type trefwoordovereenkomst</td>
   <td>(leeg)</td>
  </tr>
  <tr>
   <td>Openingspagina</td>
   <td>https://www.adobe.com/marketing-attribution-for-demand-generation-leaders</td>
  </tr>
  <tr>
   <td>Openingspagina - Raw</td>
   <td>https://www.adobe.com/marketing-attribution-for-demand-generation-leaders?_bl=84186217</td>
  </tr>
  <tr>
   <td>Marketingkanaal</td>
   <td>Betaald sociaal</td>
  </tr>
  <tr>
   <td>Marketingkanaal - pad</td>
   <td>Betaald sociaal.LinkedIn</td>
  </tr>
  <tr>
   <td>Medium</td>
   <td>"cpc" of "Lead Gen Form"</td>
  </tr>
  <tr>
   <td>Referentiepagina</td>
   <td>www.linkedin.com/</td>
  </tr>
  <tr>
   <td>Refereringspagina - Raw</td>
   <td>www.linkedin.com/</td>
  </tr>
  <tr>
   <td>Serach Phrase</td>
   <td>(leeg)</td>
  </tr>
  <tr>
   <td>Type aanraakpunt</td>
   <td>Webformulier</td>
  </tr>
  <tr>
   <td>Aanraakpunt Source</td>
   <td>LinkedIn</td>
  </tr>
 </tbody>
</table>

**&#42;** _Het veld &#39;URL van bestemming toevoegen&#39; wordt alleen gevuld voor gesponsorde inhoud. Het is niet bevolkt voor Lead Gen Forms._

<br>

## Kosten {#costs}

Omdat [!DNL Marketo Measure] rechtstreeks is geïntegreerd met [!DNL LinkedIn] , downloaden we elke dag de opgenomen uitgaven voor elke campagne en Creative. Een klant hoeft niet meer te rapporteren over [!DNL LinkedIn] uitgaven binnen de [!DNL Marketo Measure] -toepassing.

Net als bij andere vormen van advertentie-integratie heeft [!DNL Marketo Measure] een regel voor het marketingkanaal gedefinieerd waarin alle [!DNL LinkedIn] -campagnes, -creatieven en -kosten worden geplaatst. Om de regel te gebruiken, zal de klant een nieuwe rij voor hun Betaalde [!DNL LinkedIn] inspanningen willen opnemen. Het kan een nieuw of bestaand kanaal zijn. In de kolom Referenter gebruikt u de definitie &quot;[[!DNL LinkedIn] Betaald]&quot; die [!DNL Marketo Measure] heeft gedefinieerd als elk aanraakpunt met een tag [!DNL Marketo Measure] .

![&#x200B; zoals met andere advertentierespelingen, heeft Marketo Measure marketing &#x200B;](../assets/marketo-engage-activities-01.png) bepaald

## [!DNL Marketo Measure] Detecteren {#marketo-measure-discover}

Er zijn enkele verbeteringen aangebracht in [!DNL Marketo Measure] Discover ter ondersteuning van de rapportage van lead Gen Forms.

**Betaalde Raad van Media**

Generaal-leider Forms-tegel: Nieuwe tegel die het aantal LinkedIn-formuliervullingen bevat. Doorloop van dit aantal geeft de activiteit-id, de formulierdatum, de formuliernaam en het e-mailadres weer.

**Raad van de Weg van de Aanwezigheid**

Reis of Events: Omvat het gebeurtenistype &quot;Activiteit&quot; en het gemiddelde &quot;Lead Gen Form&quot; voor formulieren die door de integratie heen komen. Tot de uitgebreide weergave behoren Campagne, Creative en Formuliergegevens.

## Veelgestelde vragen over gesponsorde inhoud {#sponsored-content-faq}

**wat een Donker Aandeel is?**

Een donker aandeel is een post waar het nooit op de bedrijfspagina wordt gepost en onmiddellijk wordt gecreeerd en direct als Creative wordt toegevoegd. Om ervoor te zorgen dat [!DNL Marketo Measure] gemaakte Creative Cloud niet boven aan de pagina van een bedrijf wordt weergegeven en opnieuw wordt bevorderd, worden donkere aandelen gebruikt zodat deze achter de schermen kunnen worden geïntroduceerd.

**wat Statussen [!DNL Marketo Measure] eigenlijk etiketteren?**

Er zijn vier verschillende statussen voor een [!DNL LinkedIn] -campagne en Creative: Actief, Gepauzeerd, Gearchiveerd en Geannuleerd. We labelen alleen campagnes en Creative Cloud die actief zijn. Als u andere statussen codeert, stelt u deze opnieuw in op Actief. In [!DNL Marketo Measure] worden geen tags voor Gepauzeerde, Gearchiveerde of Geannuleerde campagnes of Creative Cloud toegewezen, maar de codering wordt hervat als de status verandert in Actief.

**wat is de waarde die [!DNL Marketo Measure] aan markering gebruikt?**

Aan het einde van de doel-URL voegt [!DNL Marketo Measure] de parameter `&_bl={creativeId}` toe, waarbij `{creativeId}` de Creative-id van LinkedIn is. Met de Creative-id kan [!DNL Marketo Measure] ook de campagne-id bepalen, aangezien [!DNL LinkedIn] een tamelijk eenvoudige advertentiefunctie heeft, aangezien elke Creative slechts tot één campagne kan behoren.

**wat gebeurt met mijn oude creatieve eens [!DNL Marketo Measure] creeert een nieuwe versie van het?**

Als [!DNL Marketo Measure] een Delen opnieuw maakt en deze in een nieuwe Creative plaatst, wordt de oude Creative gearchiveerd. Daarom zal in [!DNL Marketo Measure] ook geen tag worden toegewezen aan gearchiveerde campagnes of Creative Cloud. Anders wordt er een lus uitgevoerd met [!DNL Marketo Measure] die probeert er oneindig tags aan toe te wijzen.

**waarom past niet bestemmingsURL van de gecreeerde advertentie mijn originele advertentie aan?**

[!DNL Marketo Measure] moet de volgende parameters toevoegen aan een opgeloste URL, maar de URL die in API wordt voorgesteld kan een verkorte URL zijn zonder alle parameters aanwezig. Om dit probleem te verhelpen, zoekt [!DNL Marketo Measure] naar verkorte URL&#39;s voordat u het toevoegen opnieuw maakt, lost het probleem op en maakt vervolgens de nieuwe advertentie met de opgeloste URL en alle bijbehorende parameters, zodat [!DNL Marketo Measure] tags kan toevoegen.

**Ben u al mijn advertenties etiketteren? Ik zie niet de bl parameter op al mijn landingspagina&#39;s?**

We hebben vastgesteld dat sommige marketers een afbeeldingskoppeling in de doel-URL plaatsen, die [!DNL Marketo Measure] niet kan labelen, zodat we naar de URL in de advertentie-inhoud zoeken. Als [!DNL Marketo Measure] toestemming heeft om verkorte URLs van markeringen te voorzien, zullen wij URL en markering uitbreiden die, maar wegens de exemplaarstructuur van LinkedIn, het automatisch binnen de tekst wordt verkort. De tag wordt weergegeven in de verkorte URL van LinkedIn, die wordt weergegeven in het veld Advertentie-inhoud van het aanraakpunt in plaats van in het veld Landing Page - Raw.

**Oh nee, iemand op mijn team heeft per ongeluk een aandeel gekloond. Mag ik het pauzeren?**

Geen zorgen. [!DNL Marketo Measure] controleert via programmacode op aandelen die niet meer uniek zijn, wat betekent dat het sindsdien naar een andere Creative is gekopieerd. Zodra die kopie is gevonden, volgt [!DNL Marketo Measure] de gebruikelijke stroom om tags toe te wijzen en nieuwe advertenties te maken.

**Mijn advertentie was in afwachting van beoordeling eerder. Waarom is het in afwachting van revisie opnieuw nadat [!DNL Marketo Measure] het etiketteerde?**

LinkedIn vereist dat alle advertenties die worden gecreeerd of gewijzigd door het normale veiligheidsproces gaan alvorens het wordt gepost. [!DNL Marketo Measure] probeert de advertentie zo snel mogelijk te onderscheppen, omdat deze elke 6 uur naar nieuwe advertenties scant, maar met [!DNL LinkedIn's] extra stap kan de opstart enkele uren worden vertraagd.

**er zijn 2 URLs op mijn advertentie. Welke wordt geëtiketteerd?**

Beide. Dankzij de integratie met [!DNL Marketo Measure] kunnen we de doel-URL van de klik tot en met de afbeelding in de advertentie labelen, maar wordt ook automatisch de verkorte URL in de beschrijving van de advertentie bijgewerkt.

![&#x200B; allebei. De integratie van Marketo Measure staat ons toe om de bestemming &#x200B;](assets/select-type-1.png) te etiketteren

**Ik heb mijn [!DNL LinkedIn ads] rekening verbonden. Waarom is het niet [!DNL Marketo Measure] etiketteren van mijn verbindingen?**

De verbonden gebruiker van [!DNL LinkedIn] moet juiste het uitgeven toegang hebben, wat betekent de gebruiker een Manager van de Rekening, Campagne, of Manager van Creative moet zijn.

**Hoe weet ik of mijn creatieve zal worden gekopieerd? Kan ik zien of gebruiken mijn creatieven het zelfde aandeel?**

De aandeel-id is niet opgenomen in een [!DNL LinkedIn] -rapport, dus er is geen duidelijke en duidelijke manier om te controleren op toewijzingen van creatief naar gedeeld materiaal. Als u vermoedt dat een creatief item een kopie is, kunt u dit handmatig controleren door de advertentie te openen vanuit uw [!DNL LinkedIn] Campagne-manager. Hierdoor wordt de advertentie op een nieuw tabblad geopend en kunt u de id voor delen vinden in de URL.

![&#x200B; identiteitskaart van het aandeel wordt niet verstrekt in een rapport LinkedIn, zodat &#x200B;](assets/linkedin-integration-02.png)

## Generaal-leider Forms - Veelgestelde vragen {#lead-gen-forms-faq}

**wat is de kosten van deze verhoging?**

Deze aanbieding wordt meegeleverd bij elk betaald [!DNL Marketo Measure] -abonnement.

**is de integratie retroactief?**

Ja, wij zullen historische en vormreacties van LinkedIn downloaden, hoewel wij tot het venster van 90 dagen terugblik beperkt zijn. Hoe langer de integratie van [!DNL Marketo Measure] en LinkedIn is ingeschakeld, des te meer aanraakpunten op basis van lead Gen-formulieren zichtbaar zijn via [!DNL Marketo Measure] .

Er is geen optie om een specifieke datum voor download in te stellen, maar u kunt desgewenst regels voor het verwijderen van aanraakpunten instellen als er aanraakpunten zijn die u moet onderdrukken.

**zal dit automatisch worden toegelaten als ik reeds [!DNL Marketo Measure] LinkedIn en integratie gebruik?**

Nee, we beginnen het niet automatisch voor alle klanten te downloaden, maar het is een heel eenvoudige switch om deze functie in te schakelen in instellingen.

**is de beschikbare gegevens van de Vorm?**

Formuliergegevens zijn beschikbaar via [!DNL Marketo Measure] Detecteren, waaronder Formulier-id en Formuliernaam. Formulierdetails zijn nog niet beschikbaar voor de aanraakpuntobjecten in de CRM-toepassing.

**wat gebeurt met om het even welke [!DNL LinkedIn] lood die eerder aan de Programma&#39;s van Marketo of de Campagnes van CRM zijn gesynchroniseerd?**

U wordt aangeraden de [!DNL Marketo Measure] -regels aan te passen om aanraakpunten te maken van deze specifieke programma&#39;s of campagnes, om dubbel werk te voorkomen. LinkedIn API heeft een terugkijkbeperking van 90 dagen, zodat als u Marketo of de regels van CRM gebruikt, wordt geadviseerd dat u de einddatum op de regel aan 90 dagen voorafgaand aan de datum plaatst u de integratie in [!DNL Marketo Measure] toeliet. Vanaf dit punt kan [!DNL Marketo Measure] deze leads voor je downloaden met meer insight en meer informatie.

**is er om het even welk auto-etiketteren of het volgen betrokken?**

Nee, dit verschilt van andere [!DNL Marketo Measure] -integraties. In plaats van de bestemmingspagina te wijzigen (aangezien er geen klik door landingspagina) is, downloaden wij slechts de relevante informatie van LinkedIn en behandelen zij als activiteiten binnen [!DNL Marketo Measure].
