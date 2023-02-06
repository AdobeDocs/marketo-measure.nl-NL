---
unique-page-id: 35586080
description: linkedIn-integratie - [!DNL Marketo Measure] - Productdocumentatie
title: linkedIn-integratie
exl-id: 705209ef-1ece-496c-ac2f-6a31055bd993
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '2594'
ht-degree: 0%

---

# linkedIn-integratie {#linkedin-integration}

## Overzicht {#overview}

De [!DNL Marketo Measure] de integratie met LinkedIn bestaat uit twee delen:

Gesponsorde inhoud: Door de integratie van gesponsorde inhoud is [!DNL Marketo Measure] om doel-URL&#39;s te labelen op [!DNL LinkedIn] advertenties, waardoor [!DNL Marketo Measure] om een gebruiker door hun volledige touchpoint reis te volgen en de activiteit terug te brengen naar specifiek [!DNL LinkedIn] Campagne en creatief. Dit verstrekt inzicht aan klanten over het ROI van hun [!DNL LinkedIn] activiteit.

Generaal-leider Forms: Door de integratie met LinkedIn-leider Gen Forms krijgt Marketo Measure inzicht in formulieren die via het LinkedIn-platform zijn ingediend. Deze formuliervullingen worden vergeleken met leads van uw CRM of [!DNL Marketo Engage] zodat ze in aanmerking komen voor attributie. Met inzicht in de Campagne, Creative en Form die hebben bijgedragen tot het genereren van de formulieren, kunnen teams nu hun marketing- en advertentieuitgaven voor LinkedIn verder optimaliseren.

## Beschikbaarheid {#availability}

Beschikbaar voor alle klanten.

## Vereisten {#requirements}

**Rollen voor Campagnerbeheer**

Voor [!DNL Marketo Measure] Als u gegevens en extra kosten voor Advertentie wilt downloaden, moet u een van de volgende rollen hebben in Campagnebeheer:

* Factureringsbeheer
* Accountmanager
* Campagnebeheer

Meer informatie: [Gebruikersrollen en -functies in Campagnebeheer](https://www.linkedin.com/help/lms/answer/a425731/user-roles-and-functions-in-campaign-manager).

**Betaalde rollen voor mediabeheer**

Voor [!DNL Marketo Measure] Als u Gesponsorde Creative Cloud wilt maken/bijwerken, moet u een van de volgende rollen voor Betaald mediabeheer hebben:

* Poster met gesponsorde inhoud
* Generaal-leider Forms Manager

Meer informatie: [linkedIn-rollen voor paginabeheer](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admin-roles-overview).

Er zijn andere [!DNL LinkedIn] rollen die wij vervullen **niet** vereist voor onze integratie. Deze rollen worden vaak verward met de vereiste rollen, dus let op een verschil!

**Paginabeheerrollen**

Voor [!DNL Marketo Measure] als u leads wilt kunnen downloaden/integreren van hoofdgeneratieformulieren, hebt u de volgende rol voor Paginabeheer nodig:

* Super Admin

Meer informatie: [linkedIn-rollen voor paginabeheer](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admin-roles-overview).

## linkedIn-advertentietypen {#linkedin-ad-types}

[!DNL Marketo Measure] ondersteunt:

**Gesponsorde inhoud:** Met gesponsorde inhoud kunt u inhoud leveren aan de [!DNL LinkedIn] voer van leden buiten degenen die uw bedrijf volgen. De gesponsorde Inhoud kan aan een specifiek publiek worden gericht en kan adverteerders helpen bereiken [!DNL LinkedIn] leden, waar en wanneer zij zich inzetten voor de [!DNL LinkedIn] platform op alle desktopcomputers, mobiele apparaten en tablets. Gesponsorde inhoud wordt ondersteund door Lead Gen Forms.

De typen gesponsorde inhoud en indelingen die worden ondersteund door [!DNL Marketo Measure] Dit zijn Single Image Ads en Video Ads (via Lead Gen Forms). Vanwege de complexiteit van het schema bieden we geen ondersteuning voor Carousel-advertenties.

[!DNL Marketo Measure] biedt geen ondersteuning voor gesponsorde berichten, tekstadvertenties of dynamische advertenties.

![](assets/one.png)

>[!TIP]
>
>Voor al uw campagnes/uitgaven die afkomstig zijn van een niet-gesponsorde inhoudsbron (zoals Campagneringstype &quot;Tekst toevoegen&quot; of &quot;Gesponsorde InMail&quot;), [!DNL Marketo Measure] doet _niet_ Het bijhouden van deze typen campagnes ondersteunen. Als u de uitgaven voor campagnes zoals deze naast uw &quot;Gesponsorde Inhoud&quot;uitgaven wilt volgen, ben zeker om van onze uitgave van de Marketing CSV gebruik te maken om gezegd uitgaven manueel te registreren.

## Hoe het werkt: Gesponsorde inhoud {#how-it-works-sponsored-content}

>[!NOTE]
>
>Voor het eerste gebruik moet deze functie-instelling worden ingeschakeld door naar [!DNL Marketo Measure] [!UICONTROL Settings] > [!UICONTROL Integrations] > [!UICONTROL Ads] > [!UICONTROL Enable LinkedIn Lead Gen Forms].

**[!DNL LinkedIn's]Unieke vereisten voor automatische labeling**

[!DNL Marketo Measure] kan u helpen uw [!DNL LinkedIn] door uw bestemmingspagina&#39;s automatisch te labelen.

[!DNL Marketo Measure] zoekt u naar creatieve producten met een unieke LinkedIn Share en voegt u een `?_bl={creativeId}` aan het einde van de parameter.

**Delen kopiëren**

Met deze [!DNL Marketo Measure/LinkedIn] Bij de integratie vragen we dat klanten bestaande Creative Clone niet kopiëren/klonen/dupliceren. Als er aandelen worden gevonden en waarvan wordt vastgesteld dat deze slechts op één Creative Cloud worden gebruikt, [!DNL Marketo Measure] U kunt de tag voor Delen op dezelfde manier plaatsen zonder dat u Creative Cloud of Share opnieuw hoeft te maken. Alle advertentiehistorie (indrukken, klikken, delen) blijft dan ongewijzigd.

Zodra is vastgesteld dat een aandeel door meerdere Creative Cloud wordt gedeeld, [!DNL Marketo Measure] moet een proces van pauzeren, kopiëren en opnieuw labelen doorlopen om een unieke set te maken. [!DNL Marketo Measure] onderbreekt en archiveert levende creatieve producten en wist daarom de geschiedenis van de advertentie, inclusief indrukken, klikken en sociale aandelen, om alles op de juiste manier te labelen.

Vooruit beweegt, [!DNL Marketo Measure] raadt u aan geen [!DNL LinkedIn] Deelt en bewaart alle creatieve partijen en aandelen zo uniek mogelijk, zodat we eenvoudig onze tracering kunnen toevoegen zonder dat we advertentiegeschiedenis hoeven te wissen.

**Kortere URL&#39;s**

De reden voor de extra stap is omdat LinkedIn toestaat dat doel-URL&#39;s een verkorte URL zijn (bit.ly, goog.le, enz.), wat betekent [!DNL Marketo Measure] ziet de lange, opgeloste URL niet en [!DNL Marketo Measure] moet volgparameters toevoegen aan een opgeloste URL. Om dit probleem op te lossen, [!DNL Marketo Measure] zoekt naar verkorte URL&#39;s voordat u een advertentie opnieuw maakt, breidt de URL uit en maakt vervolgens de nieuwe advertentie met de opgeloste URL en alle bijbehorende parameters, zodat [!DNL Marketo Measure] om codes toe te voegen. Als u een nieuwe advertentie maakt, wordt de historie gewist (indrukken, klikken en delen). Daarom is het nodig dat u toestemming hebt om ingekorte URL&#39;s van tags te voorzien.

Als u veel gebruik maakt van verkorte URL&#39;s, kan dit ernstige gevolgen hebben voor uw creatieve projecten. We raden u aan geen verkorte URL&#39;s meer te gebruiken, zodat [!DNL Marketo Measure] U kunt de bestemmingspagina&#39;s labelen zonder nieuwe advertenties te maken en Advertentiegeschiedenis te wissen.

**Het proces**

Laten we beginnen met een paar voorbeelden. Laten we zeggen dat we....

Creatief A: Aandeel 123\
Creatief B: Aandeel 234\
Creative C: Aandeel 234\
Creative D: Aandeel 234

![](assets/two.png)

`1)` [!DNL Marketo Measure] zal eerst alle campagnes, creatieve projecten en aandelen met de status &quot;Actief&quot; doornemen. [!DNL Marketo Measure] geen tags toevoegen aan gepauzeerde, gearchiveerde of geannuleerde advertenties. Als een advertentie is gepauzeerd, stelt u deze in op [!UICONTROL active]We labelen het zodra het programma weer actief is. Als wij een uniek Aandeel kunnen vinden, betekenend het niet over veelvoudige Creative of Campagnes (b.v., Creative A wordt gebruikt: Aandeel 123), [!DNL Marketo Measure] voegt onze aangepaste parameter toe `>> ?_bl={creativeId}` naar de gedeelde URL.

`2)` Nu als het Delen is gedeeld en zijn uniciteit (bijvoorbeeld Creative B: Delen 234 en Creative C: Delen 234 en Creative D: Aandeel 234), [!DNL Marketo Measure] pauzeren en archiveren alle vergelijkbare creatieve objecten (creatief B, Creative C en Creative D).

`3)` [!DNL Marketo Measure] maakt drie nieuwe creatieve projecten, Creative E, Creative F en Creative G, die de gearchiveerde inhoud van Creative B kopiëren.

`4)` [!DNL Marketo Measure] zal ook 3 nieuwe aandelen, Aandeel 345, Aandeel 456, en Aandeel 567 tot stand brengen, die de inhoud van Aandeel 234 kopieert, behalve het zal zijn eigen unieke hebben `?_bl` labelen.

`5)` [!DNL Marketo Measure] zullen regelmatig moeten controleren of de aandelen niet worden gedeeld en als zij dat doen, zullen wij het proces in stap 2 hierboven opnieuw beginnen.

>[!NOTE]
>
>Als u dit implementeert, verliezen onze klanten de advertentiegeschiedenis van Creative B: Share 234, Creative C: Delen 234 en Creative D: Deel 234 omdat het nu opnieuw wordt gemaakt met Creative E: Aandeel 345, Aandeel F: Delen 456 en Creative G: Aandeel 567.

![](assets/three.png)

## Hoe het werkt: Generaal-leider Forms {#how-it-works-lead-gen-forms}

**Het proces**

Doorheen [!DNL LinkedIn's] Met de API voor formulieren en de API voor formulierreacties kunnen we formulierverzendgegevens verzamelen voor een advertentieaccount en het e-mailadres koppelen aan een lead van de CRM of Marketo.

linkedIn-formulieren kunnen meerdere e-mailadressen bevatten. Wanneer we formulierreacties downloaden, zoeken we naar e-mailadressen met de volgende prioriteit: Werk-e-mail, E-mailadres (primair formulierveld) of aangepaste velden met een geldige e-mailwaarde.

Ongeacht de Campagne- of Creatieve status, zullen alle Reacties van het Vorm in een aanraakpunt resulteren. [!DNL Marketo Measure] heeft een terugzoekbeperking van 90 dagen, dus [!DNL Marketo Measure] heeft geen toegang tot formulierreacties ouder dan 90 dagen, maar hoe langer [!DNL Marketo Measure] en [!DNL LinkedIn] integratie is ingeschakeld, zullen de meer toonaangevende Gen Form-aanraakpunten zichtbaar zijn via [!DNL Marketo Measure].

>[!NOTE]
>
>linkedIn-kosten worden nog steeds gedownload als onderdeel van campagnes voor gesponsorde inhoud.

**Gen.-trainingsleider Forms volgen in CRM of Marketo**

Voor de [!DNL Marketo Measure] en LinkedIn Lead Gen Forms Integration bestond, was het gebruikelijk dat klanten hun formulierverzendingen naar een Marketo-programma en/of CRM-campagne zouden doorsturen om de formulieren te volgen en deze toe te wijzen. Nadat de instelling voor Gen-leider Forms is ingeschakeld, willen we ervoor zorgen dat deze formulierverzendingen niet dubbel worden geteld. Controleer het volgende:

* Het veld &quot;Aanraakpunten koper inschakelen&quot; in het CRM-object is ingesteld op &quot;Geen&quot; of &quot;Alle leden van campagne uitsluiten&quot;
* Gerelateerde regels voor Marketo-programma&#39;s of Marketo-activiteiten bijwerken
* Verwante regels voor CRM-campagnes bijwerken

>[!NOTE]
>
>De LinkedIn API heeft een terugkijkbeperking van 90 dagen, zodat als u Marketo of de regels van CRM gebruikt, wordt geadviseerd dat u de einddatum op de regel aan 90 dagen voorafgaand aan de datum plaatst u de integratie binnen toeliet [!DNL Marketo Measure].

## Details aanraakpunt {#touchpoint-details}

Eenmaal [!DNL Marketo Measure] heeft met succes uw landingspagina op de LinkedIn creatief getagd, zult u de opgeloste advertentiegegevens op touchpoint kunnen bekijken. Hier is de afbeelding van gegevenswaarden die u zou moeten verwachten te zien:

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th>Aanraakpuntveld</th> 
   <th>Samplewaarde</th> 
  </tr> 
  <tr> 
   <td><p>Advertentie-id </p></td> 
   <td><p>84186224 </p></td> 
  </tr> 
  <tr> 
   <td><p>Inhoud toevoegen </p></td> 
   <td><p>copy-1-image-2-man 95% van de #B2B-marketers beschouwt de strategie voor het creëren van vraag als succesvol. Meer informatie: [!DNL https]/lnkd.in/jgdi50vKrgv</p></td> 
  </tr> 
  <tr> 
   <td><p>Groep-id toevoegen </p></td> 
   <td><p>(leeg) </p></td> 
  </tr> 
  <tr> 
   <td><p>Naam advertentiegroep </p></td> 
   <td><p>(leeg) </p></td> 
  </tr> 
  <tr> 
   <td><p>Campagne-id toevoegen </p></td> 
   <td><p>138949954 </p></td> 
  </tr> 
  <tr> 
   <td><p>Naam advertentiecampagne </p></td> 
   <td><p>SU - COM-accounts - vraagvaardigheden </p></td> 
  </tr> 
  <tr> 
   <td><p>Doel-URL toevoegen </p></td> 
   <td><p>https://www.adobe.com/marketing-attribution-for-demand-generation-leaders?_bl=84186217 </p></td> 
  </tr> 
  <tr> 
   <td><p>URL van formulier </p></td> 
   <td><p>info.bizible.com/demo </p></td> 
  </tr> 
  <tr> 
   <td><p>URL formulier - Raw </p></td> 
   <td><p>info.bizible.com/demo </p></td> 
  </tr> 
  <tr> 
   <td><p>Trefwoord-id </p></td> 
   <td><p>(leeg) </p></td> 
  </tr> 
  <tr> 
   <td><p>Type trefwoordovereenkomst </p></td> 
   <td><p>(leeg) </p></td> 
  </tr> 
  <tr> 
   <td><p>Openingspagina </p></td> 
   <td><p>https://www.adobe.com/marketing-attribution-for-demand-generation-leaders </p></td> 
  </tr> 
  <tr> 
   <td><p>Openingspagina - Raw </p></td> 
   <td><p>https://www.adobe.com/marketing-attribution-for-demand-generation-leaders?_bl=84186217 </p></td> 
  </tr> 
  <tr> 
   <td><p>Marketingkanaal </p></td> 
   <td><p>Betaald sociaal </p></td> 
  </tr> 
  <tr> 
   <td><p>Marketingkanaal - pad </p></td> 
   <td><p>Betaald sociaal.LinkedIn </p></td> 
  </tr> 
  <tr> 
   <td><p>Normaal </p></td> 
   <td><p>"cpc" of "Lead Gen Form"</p></td> 
  </tr> 
  <tr> 
   <td><p>Referentiepagina </p></td> 
   <td><p>www.linkedin.com/ </p></td> 
  </tr> 
  <tr> 
   <td><p>Refereringspagina - Raw </p></td> 
   <td><p>www.linkedin.com/ </p></td> 
  </tr> 
  <tr> 
   <td><p>Serach Phrase </p></td> 
   <td><p>(leeg) </p></td> 
  </tr> 
  <tr> 
   <td><p>Type aanraakpunt </p></td> 
   <td><p>Webformulier </p></td> 
  </tr> 
  <tr> 
   <td><p>Aanraakpuntbron </p></td> 
   <td><p>LinkedIn </p></td> 
  </tr> 
 </tbody> 
</table>

## Kosten {#costs}

Omdat [!DNL Marketo Measure] heeft een directe integratie met [!DNL LinkedIn]We downloaden de opgenomen uitgaven voor elke campagne en Creative elke dag. Een klant hoeft geen melding te maken van [!DNL LinkedIn] binnen de [!DNL Marketo Measure] niet meer worden toegepast.

Net als bij andere vormen van integratie [!DNL Marketo Measure] heeft een marketingkanaalregel gedefinieerd om alles te plaatsen [!DNL LinkedIn] campagnes, creatieven en kosten. Om de regel te gebruiken, zal de klant een nieuwe rij voor hun Betaald willen opnemen [!DNL LinkedIn] inspanningen. Het kan een nieuw of bestaand kanaal zijn. Gebruik in de kolom Referenter de definitie &quot;[[!DNL LinkedIn] Betaald]&quot; [!DNL Marketo Measure] heeft gedefinieerd als een aanraakpunt met een [!DNL Marketo Measure] tag.

![](assets/four.png)

## [!DNL Marketo Measure] Discover {#marketo-measure-discover}

Er zijn enkele verbeteringen aangebracht in [!DNL Marketo Measure] Ontdek om rapportage van generaal-leider Forms te ondersteunen.

**Betaalde mediaraad**

Generaal-leider Forms-tegel: Nieuwe tegel die het aantal LinkedIn-formuliervullingen bevat. Doorloop van dit aantal geeft de activiteit-id, de formulierdatum, de formuliernaam en het e-mailadres weer.

**Padkaart voor betrokkenheid**

Reis van gebeurtenissen: Omvat het gebeurtenistype &quot;Activiteit&quot; en het gemiddelde lead Gen-formulier voor formulieren die door de integratie worden ontvangen. Tot de uitgebreide weergave behoren Campagne, Creatief en Formuliergegevens.

## Veelgestelde vragen over gesponsorde inhoud {#sponsored-content-faq}

**Wat is een donkere Delen?**

Een donker aandeel is een post waar het nooit op de bedrijfspagina wordt gepost en onmiddellijk wordt gecreeerd en direct als Creative toegevoegd. Dus [!DNL Marketo Measure]- Creatieve personen die u hebt gemaakt, staan niet bovenaan op de pagina van een bedrijf en worden weer gepromoveerd. Donkere aandelen worden gebruikt zodat ze achter de schermen kunnen verschijnen.

**Wat statussen doen [!DNL Marketo Measure] tag ?**

Er zijn vier verschillende statussen op een [!DNL LinkedIn] Campagne en creatief: Actief, Gepauzeerd, Gearchiveerd en Geannuleerd. We labelen alleen campagnes en Creative Cloud die actief zijn. Als u andere statussen codeert, stelt u deze opnieuw in op Actief. [!DNL Marketo Measure] De tag Gepauzeerde, Gearchiveerde of Geannuleerde campagnes of Creative Cloud wordt niet toegepast, maar de tag wordt hervat als de status verandert in Actief.

**Wat is de waarde van [!DNL Marketo Measure] gebruikt u de tag?**

Aan het einde van de doel-URL: [!DNL Marketo Measure] voegt de parameter toe `&_bl={creativeId}`, waarbij `{creativeId}` is de Creative ID uit LinkedIn. Met de Creative-id [!DNL Marketo Measure] kan ook de campagne-id bepalen sinds [!DNL LinkedIn] heeft een tamelijk basisstructuur voor advertenties, omdat elk creatief slechts tot één campagne kan behoren.

**Wat gebeurt er eens met mijn oude creatieve [!DNL Marketo Measure] een nieuwe versie ervan maken?**

Wanneer [!DNL Marketo Measure] Hiermee maakt u een Delen opnieuw en plaatst u deze in een nieuw Creative Suite-archief. Daarom [!DNL Marketo Measure] gearchiveerde campagnes of Creative Cloud worden niet van tags voorzien. Anders wordt er een lus uitgevoerd met [!DNL Marketo Measure] proberen het oneindig te labelen.

**Waarom komt de doel-URL van de gemaakte advertentie niet overeen met mijn oorspronkelijke advertentie?**

[!DNL Marketo Measure] moet de volgende parameters toevoegen aan een opgeloste URL, maar de URL die in API wordt voorgesteld kan een verkorte URL zijn zonder alle parameters aanwezig. Om dit probleem op te lossen, [!DNL Marketo Measure] zoekt naar verkorte URL&#39;s voordat u het toevoegen opnieuw maakt, lost het op en maakt vervolgens de nieuwe advertentie met de opgeloste URL en alle bijbehorende parameters, zodat [!DNL Marketo Measure] om codes toe te voegen.

**Ben je al mijn advertenties aan het labelen? Ik zie de parameter bl niet op al mijn landingspagina&#39;s?**

We hebben gezien dat sommige marketers een afbeeldingskoppeling in de doel-URL zullen plaatsen, die [!DNL Marketo Measure] Kan geen tag toevoegen, dus zoeken we naar de URL in de advertentie-inhoud. Indien [!DNL Marketo Measure] heeft machtigingen om ingekorte URL&#39;s te labelen, breiden we de URL en tag uit. Vanwege de kopieerstructuur van LinkedIn wordt de URL echter automatisch ingekort in de tekst. De tag wordt weergegeven in de verkorte URL van LinkedIn, die wordt weergegeven in het veld Advertentie-inhoud van het aanraakpunt in plaats van in het veld Landing Page - Raw.

**Oh nee, iemand in mijn team heeft per ongeluk een aandeel gekloond. Kan ik het pauzeren?**

Geen zorgen. [!DNL Marketo Measure] controleert programmatisch op aandelen die niet meer uniek zijn, wat betekent dat het sindsdien naar een ander Creative-bestand is gekopieerd. Zodra die kopie is gevonden, [!DNL Marketo Measure] volgt de gebruikelijke workflow om tags aan toe te wijzen en nieuwe advertenties te maken.

**Mijn advertentie was eerder in behandeling. Waarom is de herziening in behandeling na [!DNL Marketo Measure] gelabeld?**

linkedIn vereist dat alle advertenties die zijn gemaakt of gewijzigd, door het normale beveiligingsproces worden geleid voordat ze worden gepost. [!DNL Marketo Measure] probeert de advertentie zo snel mogelijk te onderscheppen, omdat deze elke 6 uur op nieuwe advertenties scant, maar met [!DNL LinkedIn's] een extra stap, kan de lancering met een paar uren vertragen.

**Er staan twee URL&#39;s op mijn advertentie. Welke wordt er getagd?**

Beide. De [!DNL Marketo Measure] Dankzij integratie kunnen we de doel-URL van de klik naar de afbeelding in de advertentie labelen, maar wordt de verkorte URL ook automatisch bijgewerkt in de beschrijving van de advertentie.

![](assets/five.png)

**Ik heb mijn [!DNL LinkedIn ads] account. Waarom niet? [!DNL Marketo Measure] mijn koppelingen labelen?**

De aangesloten [!DNL LinkedIn] gebruikers moeten over de juiste bewerkingstoegang beschikken. Dit houdt in dat de gebruiker een accountmanager, Campagne Manager of Creative Manager moet zijn.

**Hoe weet ik of mijn creatieve werk gekopieerd zal worden? Kan ik zien of mijn creatieven hetzelfde aandeel gebruiken?**

De aandeel-id is niet beschikbaar in een [!DNL LinkedIn] rapport, dus er is geen duidelijke en duidelijke manier om op creatief-aan-aandeel afbeeldingen te controleren. Als u vermoedt dat een creatief document een kopie is, kunt u dit handmatig controleren door de advertentie vanuit uw [!DNL LinkedIn] Campagne manager-dit zal de advertentie in een nieuw lusje openen en u zult aandeelidentiteitskaart in URL vinden.

![](assets/six.png)

## Generaal-leider Forms - Veelgestelde vragen {#lead-gen-forms-faq}

**Wat zijn de kosten van deze verbetering?**

Deze aanbieding wordt meegeleverd bij elke betaling [!DNL Marketo Measure] abonnement.

**Is de integratie met terugwerkende kracht?**

Ja, we downloaden historische reacties op advertentievormen van LinkedIn, maar we zijn beperkt tot het terugzoekvenster van 90 dagen. Hoe langer [!DNL Marketo Measure] en LinkedIn-integratie is ingeschakeld, zullen de meer toonaangevende Gen Form-touchpoints zichtbaar zijn via [!DNL Marketo Measure].

Er is geen optie om een specifieke datum voor download in te stellen, maar u kunt desgewenst regels voor het verwijderen van aanraakpunten instellen als er aanraakpunten zijn die u moet onderdrukken.

**Wordt automatisch ingeschakeld als ik de opdracht [!DNL Marketo Measure] linkedIn en integratie?**

Nee, we beginnen het niet automatisch voor alle klanten te downloaden, maar het is een heel eenvoudige switch om deze functie in te schakelen in instellingen.

**Zijn er formuliergegevens beschikbaar?**

Formuliergegevens zijn beschikbaar via [!DNL Marketo Measure] Zie onder andere Formulier-id en Formuliernaam. Formulierdetails zijn nog niet beschikbaar op de aanraakpuntobjecten in de CRM-toepassing.

**Wat gebeurt er met [!DNL LinkedIn] leads die eerder zijn gesynchroniseerd met Marketo-programma&#39;s of CRM-campagnes?**

U wordt aangeraden om de [!DNL Marketo Measure] regels om aanraakpunten te genereren uit deze specifieke programma&#39;s of campagnes om dubbel werk te voorkomen. De LinkedIn API heeft een terugkijkbeperking van 90 dagen, zodat als u Marketo of de regels van CRM gebruikt, wordt geadviseerd dat u de einddatum op de regel aan 90 dagen voorafgaand aan de datum plaatst u de integratie binnen toeliet [!DNL Marketo Measure]. Vanaf dat punt [!DNL Marketo Measure] U kunt deze leads voor u downloaden met meer inzicht en details.

**Is er sprake van automatische labeling of reeksspatiëring?**

Nee, dit is anders dan andere [!DNL Marketo Measure] integratie. In plaats van de landingspagina te wijzigen (omdat er geen klik is via de landingspagina), downloaden we alleen de relevante informatie van LinkedIn en behandelen we deze als activiteiten binnen [!DNL Marketo Measure].
