---
description: "[!DNL Marketo Measure] Rapportagehandleiding - [!DNL Marketo Measure] - Productdocumentatie"
title: "[!DNL Marketo Measure] Rapportagehandleiding"
exl-id: 9b991f9e-c187-4b43-b0a8-8ed3e9a6056b
source-git-commit: 51397a02872035fef41d308c1f855bcaecc29c4e
workflow-type: tm+mt
source-wordcount: '6395'
ht-degree: 0%

---

# [!DNL Marketo Measure] Rapportagehandleiding {#marketo-measure-reporting-guide}

>[!NOTE]
>
>Mogelijk ziet u instructies die &quot;[!DNL Marketo Measure]&quot; in onze documentatie, maar zie nog &quot;Bizible&quot;in uw CRM. We werken eraan dat dit wordt bijgewerkt en de herbranding wordt binnenkort weerspiegeld in uw CRM.

Voordat u een [!DNL Marketo Measure] rapport, is het meest essentieel om uw [!DNL Marketo Measure] Accountinstellingen zijn gecontroleerd en geconfigureerd om te zorgen dat de gegevens in de rapporten accuraat zijn en de specifieke kenmerken van uw bedrijf weerspiegelen. Daarnaast werken de rapportageprojecten het best wanneer ze een gestructureerd proces volgen. Justin Norris, a [!DNL Marketo Measure] machtsgebruiker, pleitbezorger en partner van [Perkuto](https://perkuto.com/) deskundig samengevat [hoe wordt de rapportage benaderd in [!DNL Marketo Measure]](https://perkuto.com/blog/turning-attribution-data-into-actionable-insights/):

**Doelstellingen vaststellen**: &quot;De eerste vraag die moet worden gesteld is: &quot;Waarom meten we?&quot; Lori Wizdo van [Forrester Research](https://go.forrester.com/) het in een [Marketo webinar](https://www.marketo.com/webinars/beyond-revenue-performance-real-kpis-of-b2b-marketing/). Volgens haar &quot;meten we om een besluit of de waarde van marketing te bewijzen of te valideren of om beter te worden (procesverbetering)&quot;. We willen hieraan toevoegen dat de inzichten van goede metingen ook input en begeleiding geven in het marketingplanningsproces.

Dus voordat je begint, is het essentieel om kristalhelder te zijn over je doelen, de vragen die je probeert te beantwoorden, of de problemen die je probeert op te lossen. Welk verhaal wil je vertellen? Welke besluiten zullen er naar aanleiding hiervan worden genomen? Maar al te vaak worden deze fundamentals slecht bedacht, wat leidt tot frustratie voor alle betrokkenen.&quot;

**Rapportontwerp**: &quot;Daarna, moet u het rapport ontwerpen en de specifieke afmetingen, metriek, en dataset bepalen het zal bevatten. Een algemene ervaring is om een zakelijke gebruiker precies te voorzien van wat hij of zij vraagt, alleen als hij of zij nog steeds het gevoel heeft dat hij of zij niet aan zijn of haar behoeften voldoet. Dit is omdat het inzicht een bedrijfsgebruiker eigenlijk zoekt niet altijd in het rapport bevat zij vragen. Een goede analist (of een MOPS-persoon met een analist die aanstaat) zal vragen stellen, gemeenschappelijke definities vaststellen (&quot;dus, wat bedoel je eigenlijk met lood?&quot;) en zelfs een visuele uitleg van het eindverslag geven om te zorgen dat er overeenstemming is. Pas dan bouwt u het rapport, wetend u hebt een stevige reeks vereisten.&quot;

**Rapport samenstellen**: &quot;Zodra je gaat bouwen, is het niet ongebruikelijk om in wegversperringen of dode-einden te lopen. Bijvoorbeeld, zou u kunnen ontdekken dat u een essentieel gegevenspunt mist of dat uw voorwerpen niet in de manier verbinden die u nodig hebt. Om deze problemen op te lossen, denk ik ook dat het cruciaal is om te begrijpen wat er gebeurt &quot;onder de kap&quot; in je rapportagemachine. Dankzij deze vloeiendheid kunt u snel een rapportageaanvraag samenstellen en beoordelen of dit haalbaar is (en eenvoudig creatieve oplossingen bedenken als dit niet het geval is).&quot;

Laten we eens kijken &quot;onder de kap&quot; om beter te begrijpen wat de [!DNL Marketo Measure] attributierapportmachine wordt uitgevoerd.

## Aanraakpunt voor koper (CRM) {#buyer-touchpoint-objects-crm}

Op het hoogste niveau zijn er twee rapportcategorieën gebaseerd op de twee verschillende objecten van het Aanraakpunt voor kopers: Deze categorieën bepalen welk type van [!DNL Marketo Measure] gegevens die u wilt rapporteren over: gegevens met betrekking tot een _individueel_ of gegevens die verband houden met een _kans_.

1. **Aanraakpunten koper** (BT&#39;s) / Individuen / Totale betrokkenheid

   * Doorgaans gebruikt voor &quot;top of the trechter&quot; (TOFU)-metingen en rapportage in verband met _individuen_ (Leads, Contacten, [!DNL Marketo Measure] Personen)
   * BT&#39;s worden gebruikt voor het begrijpen van alle marketinginteracties met betrekking tot **mensen**, aangezien zij de volledige geschiedenis van het aanraakpunt voor elke persoon bevatten. Ter herinnering worden deze aanraakpunten gemaakt in CRM voor de anonieme First Touch, de Aanraking voor het maken van leads en alle volgende formulierverzendingen of aanraakpunten die u kiest om te synchroniseren vanuit een offlinecampagne of activiteit.

1. **Aanraakpunten voor koperkenmerk** (BBT&#39;s) / opportuniteit / rekeningniveau / inkomsten

   * Vaak gebruikt voor metriek en rapportage met betrekking tot de &quot;middelste en/of onderkant van de trechter&quot; (MOFU en BOFU) _Kansen_.
   * De BBT&#39;s vertegenwoordigen de relevante aanraakpunten van alle personen die verbonden zijn met de **kans** (Of via de Rollen van het Contact van de Kans of via een gedeelde identiteitskaart van de Rekening, afhankelijk van uw montages). In tegenstelling tot BT&#39;s die alleen betrekking hebben op mensen, kunnen BBT&#39;s ook worden geassocieerd met **inkomsten**. Als dusdanig, zult u BBTs gebruiken om vragen te beantwoorden met betrekking tot kansen, met inbegrip van hoeveel kansen werden geopend of gesloten, of de pijpleidingswaarde en de opbrengst won.

>[!NOTE]
>
>BBT&#39;s worden gemaakt op basis van BT&#39;s. In wezen begint het bijhouden op het individuele niveau via de BT&#39;s. Zodra een Kans op een Rekening wordt gecreeerd, worden alle BTs van Contacten onder de zelfde Rekening van verwijzingen voorzien en verkiesbaar om BBTs tot stand te brengen die op de Kans betrekking hebben, zodat zult u één of andere willen gebruiken afhankelijk van welke vragen u probeert te antwoorden: vragen met betrekking tot de metriek &quot;Mensen&quot; (BT-verslagen) of vragen met betrekking tot de meetgegevens &quot;opportuniteit&quot; (BBT-verslagen)

Ondersteuningsartikel: [Verschil tussen aanraakpunten voor kopers en aanraakpunten voor koperkenmerken](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md#configuration-and-setup)

## Aanraakpunt koper (BT) {#buyer-touchpoint-bt}

Het aanraakpunt voor kopers (BT) is het object dat wordt gebruikt om elke marketinginteractie te volgen die iemand heeft met uw marketingmaterialen. Elke persoon (lead/contact/[!DNL Marketo Measure] Person) de reis zou worden vertegenwoordigd door hun verwante BT&#39;s. In [!DNL Marketo Measure], bestaat een individuele reis uit:

1. Hoe communiceerde deze persoon eerst met ons merk? (Eerste aanraking of _FT_)
1. Hoe heeft deze persoon zich omgezet, gekend of een leider geworden? (Lead maken of _LC_)
1. Hoe heeft deze persoon anders met ons merk en marketingmateriaal gecommuniceerd sinds hij een leider is geworden? (_PostLC_)

Aanraakpunten met kopers worden gebruikt om vragen te beantwoorden die betrekking hebben op _mensen_ (&quot;mensen&quot; worden vertegenwoordigd door of Leidingen of Contacten binnen een CRM), zoals Lood/Contact het produceren of verwervingsmetriek, eerder dan Kans verwante metriek. Bijvoorbeeld:

* Welke kanalen leveren de meeste Leads?
* Welke kanalen zijn min of meer kostbaar om een nieuwe Lood te creëren?
* Met welke inhoud werken mijn leads/contactpersonen?
* Wat is het marketingverhaal van bepaalde titels, rollen, persona&#39;s?
* Welke kanalen drijven MQLs, of andere lood/contactstatus?

Bedrijven moeten vooral weten: &quot;Waar komen mijn leads/contactpersonen vandaan?&quot; Historisch gezien, werd dit beantwoord met één enkele, eendimensionale waarde (de Bron van de Lood bijvoorbeeld). Zoals hierboven in #1 en #2 is uiteengezet, weten we echter dat Leads meerdere aanraakpunten kunnen hebben tijdens hun reis om leider te worden. Met het aanraakpunt voor kopers kunnen we inzicht krijgen in de twee meest cruciale interacties die aangeven hoe een lead is gegenereerd: hun First Touch en hun Lead Creation Touch. Aanraakpunten met kopers zijn ook _multidimensionaal_ Dit wil zeggen dat zij een groot aantal marketinggegevens bij zich hebben, voornamelijk waar de persoon vandaan komt (Marketing Channel) en wat de persoon die ermee bezig is (Content).

De [toewijzingsmodellen](/help/introduction-to-marketo-measure/overview-resources/marketo-measure-attribution-models.md) het beste inzicht in op mensen gebaseerde metriek bieden is:

* **Eerste aanraking** - 100% toeschrijving aan de Eerste Touch van de Lood (FT)
* **Aanmaken van lead** - 100% toeschrijving aan de Lead Creation Touch (LC)
* **U-vorm** - multi-touchbenadering, met 40% krediet aan FT, 40% krediet aan LC

<table> 
 <tbody>
  <tr>
   <td><img src="assets/bizible-reporting-guide-1.png"></td> 
   <td>Het U-Shape-model is ontworpen om krediet te bieden aan alle aanraakpunten voor kopers die een overzicht geven van hoe een lead een lead is geworden. Terwijl volgende aanraakpunten van deze leads ook kunnen worden gerapporteerd om meer betrokkenheid (Post LC) te begrijpen, maken ze geen deel uit van de <strong>Reis voor ontwerpen van leads</strong> zij krijgen dus geen toeschrijvingskrediet in de FT-, LC- of U-modellen.<p>

&#42;Meestal geeft een U-vormige attributie een even 50/50-splitsing weer tussen FT en LC. Als de lead wordt omgezet in dezelfde sessie als de First Touch, geeft één aanraakpunt zowel de FT- als de LC-aanraakpunten weer. Daarom zou 100% van de toewijzing aan één aanraakpunt worden gegeven.</td>
</tr>
 </tbody>
</table>

In deze modellen wordt veel nadruk gelegd op interacties in een vroeg stadium en op de inzet van trechter. U-Vormen attributie is het geadviseerde model aangezien het in zowel de aanraakpunten van FT als van LC factoren ervoor zorgt dat aan om het even welke aanraking wordt krediet gegeven die de Lood in verwezenlijking beïnvloedde. Met de modellen First Touch en Lead Creation Touch kunt u echter nog meer inzicht krijgen in de specifieke onderdelen van de Lead-reis.

## Aanbevolen rapporten met gebruik van het Aanraakpunt voor kopers (BT) {#recommended-reports-using-the-buyer-touchpoint-bt}

1. **LEIDEN MET KOPER-TOUCHPUNTEN**

**1,1 | Nieuwe leads per marketingkanaal**

Het samenvatten van de gegevens van het Aanraakpunt van de Koper van uw Lood door het gebied &quot;het Kanaal van de Marketing&quot;is de hoogste mening die vertegenwoordigt welke kanalen/tactieken nieuwe Lood in verwezenlijking beïnvloeden. Door dit rapport te structureren rond een &#39;Date Type&#39; = &quot;Created Date&quot; zorgt u ervoor dat een code van &#39;net new Leads&#39; (wanneer de lead in uw CRM is gemaakt) wordt vastgelegd in het rapport.

<table> 
 <tbody>
  <tr>
   <td>Vraag</td> 
   <td>Welke marketingkanalen beïnvloeden Leads in de creatie?</td> 
  </tr>
  <tr>
   <td>Rapporttype</td> 
   <td>Aanraakpunten voor leads en kopers (CRM)<br>
   Metrisch: Leads ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Datumveld / Datumtype</td> 
   <td>Aanmaakdatum van lead (CRM) / Aanmaakdatum (Discover)</td> 
  </tr>
  <tr>
   <td>Datumbereik</td> 
   <td><i>gewenste datumbereik selecteren</i></td> 
  </tr>
  <tr>
   <td>Groep/Dimension</td> 
   <td>Marketingkanaal</td> 
  </tr>
  <tr>
   <td>Optimale modellen</td> 
   <td>First Touch, Lead Creation <strong>U-vorm</strong><br>
   *SUM de velden 'Count' in uw CRM-rapporten (Count - First Touch, Count - Lead Creation, Count - U-Shaped)</td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>Voor elk rapporttype &#39;Leads with Buyer Touchpoints&#39; begint u met het aanpassen van het vooraf gebouwde rapport met de naam &#39;[!DNL Marketo Measure] 101 | Leads via kanaal&quot;. Dit rapport is beschikbaar buiten de doos en is een grote zandbak vooraf gebouwd zoals die in de lijst hierboven wordt beschreven en kan snel voor specifiekere rapporteringsbehoeften worden aangepast.

**1,2 | Nieuwe leads per campagne (of meer granulaire inzichten)**

Voor meer gedetailleerd inzicht in de gegevens die in het rapport &#39;New Leads by Marketing Channel&#39; (1.1) worden samengevat, voegt u een extra samenvatting toe op campagnereniveau. Zo kunt u niet alleen begrijpen wat &#39;Marketing Channels&#39; de nieuwe leads in de creatie brengen, maar meer in het bijzonder welke campagnes binnen die kanalen het beste presteren:

<table> 
 <tbody>
  <tr>
   <td>Vraag</td> 
   <td>Wat <i>campagnes</i> beïnvloeden Leads de creatie?</td> 
  </tr>
  <tr>
   <td>Rapporttype</td> 
   <td>Aanraakpunten voor leads en kopers (CRM)<br>
   Metrisch: Leads ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Datumveld / Datumtype</td> 
   <td>Aanmaakdatum van lead (CRM) / Aanmaakdatum (Discover)</td> 
  </tr>
  <tr>
   <td>Datumbereik</td> 
   <td><i>gewenste datumbereik selecteren</i></td> 
  </tr>
  <tr>
   <td>Groep/Dimension</td> 
   <td>Naam advertentiecampagne (CRM)</td> 
  </tr>
  <tr>
   <td>Optimale modellen</td> 
   <td>First Touch, Lead Creation <strong>U-vorm</strong><br>
   *SUM de velden 'Count' in uw CRM-rapporten (Count - First Touch, Count - Lead Creation, Count - U-Shaped)</td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>Nog gedetailleerder inzicht krijgt u door het rapport samen te vatten met andere beschikbare velden van het object Buyer Touchpoint. Doe dit door extra groeperingen (CRM) of afmetingen (Discover) te plaatsen. Afhankelijk van het kanaal (dat uw rol kan vertegenwoordigen), kunnen er extra details voorbij het campagneniveau zijn waarin u inzicht wilt krijgen. Laten we bijvoorbeeld in de onderstaande tabel naar &#39;Betaalde zoekopdracht&#39; gaan...

<table> 
 <tbody>
  <tr>
   <td>Vraag</td> 
   <td>Wat <i>trefwoorden</i> beïnvloeden Leads de creatie?</td> 
  </tr>
  <tr>
   <td>Rapporttype</td> 
   <td>Aanraakpunten voor leads en kopers (CRM)<br>
   Metrisch: Leads ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Filters</td> 
   <td>Marketingkanaal = Betaalde zoekopdracht</td> 
  </tr>
  <tr>
   <td>Datumveld / Datumtype</td> 
   <td>Aanmaakdatum van lead (CRM) / Aanmaakdatum (Discover)</td> 
  </tr>
  <tr>
   <td>Datumbereik</td> 
   <td><i>gewenste datumbereik selecteren</i></td> 
  </tr>
  <tr>
   <td>Groep/Dimension</td> 
   <td>Trefwoordtekst (CRM) / Trefwoord (Discover)</td> 
  </tr>
  <tr>
   <td>Optimale modellen</td> 
   <td>First Touch, Lead Creation <strong>U-vorm</strong><br>
   *SUM de velden 'Count' in uw CRM-rapporten (Count - First Touch, Count - Lead Creation, Count - U-Shaped)</td> 
  </tr>
 </tbody>
</table>

De mate van granulariteit kan per kanaal variëren. De aanbevolen aanpak zou zijn om jezelf af te vragen: &quot;Hoe zit het met &#39;kanaal X&#39;? Ik wil dat graag in detail begrijpen?&quot; Betaalde zoekprogramma&#39;s zijn wellicht ook geïnteresseerd in extra dimensies, zoals:

* Naam advertentiecampagne
* Inhoud toevoegen
* Advertentiegroep

Gebeurtenismanagers zijn echter meer geïnteresseerd in welke specifieke gebeurtenissen of welke soorten gebeurtenissen de meeste leads voor het maken hebben beïnvloed:

* Campagnenaam toevoegen / Salesforce-campagne = specifieke gebeurtenis
* Normaal = Campagne &#39;Type&#39;

**HERINNERING**: Het is mogelijk dat aanvullende filters moeten worden toegevoegd aan een van de hierboven of hieronder beschreven rapportvariaties. Deze filters zouden specifiek voor uw organisatie zijn en zouden iets zijn dat uw teams van Marketing Ops of van Verkoopmanager kon helpen adviseren. Het is niet ongebruikelijk voor een organisatie om de zelfde filters over alle rapporten in werking te stellen om het rapport te verzekeren zo schoon en nauwkeurig mogelijk is. Algemene voorbeelden kunnen zijn:

* Interne records uit tests, meestal per e-mailadres, filteren
* Filteren op basis van bepaalde &#39;recordtypen&#39; die specifiek zijn voor uw bedrijfseenheid

**1,3 | Nieuwe leads by Content (alleen CRM-rapporten)**

<table> 
 <tbody>
  <tr>
   <td>Vraag</td> 
   <td>Wat <i>content</i> beïnvloeden Leads de creatie?</td> 
  </tr>
  <tr>
   <td>Rapporttype</td> 
   <td>Aanraakpunten voor leads en kopers (CRM)</td> 
  </tr>
  <tr>
   <td>Datumveld</td> 
   <td>Aanmaakdatum lead</td> 
  </tr>
  <tr>
   <td>Datumbereik</td> 
   <td><i>gewenste datumbereik selecteren</i></td> 
  </tr>
  <tr>
   <td>Groep/Dimension</td> 
   <td>Openingspagina<br> 
   URL van formulier</td> 
  </tr>
  <tr>
   <td>Optimale modellen</td> 
   <td>First Touch, Lead Creation <strong>U-vorm</strong><br></td> 
  </tr>
 </tbody>
</table>

**HERINNERING**: De twee primaire velden voor rapportage over digitale inhoud/middelen zijn &#39;Landing Page&#39; en &#39;Form URL&#39;. Deze twee waarden kunnen gelijk zijn als de lead op dezelfde pagina waarop ze zijn geland, wordt geconverteerd (een formulier indient) (de landingspagina wordt verzonden). _echter_ Soms zijn deze waarden verschillend. De lead kan bijvoorbeeld op een koppeling op Facebook klikken die de gebruiker naar een pagina van uw website stuurt (dit is de waarde &#39;Landing Page&#39;). De lead kan dan verder navigeren van die pagina, de sessie op de site voortzetten en een formulier op een andere pagina (formulier-URL) verzenden. Dit wordt samengevat in één aanraakpunt dat aangeeft waar de lead vandaan komt (marketingkanaal), welke inhoud deze naar de site heeft gebracht (bestemmingspagina) en welke inhoud ze uiteindelijk hebben gedownload (formulier-URL). &#39;Formulier-URL&#39; is ook het &#39;go-to&#39;-veld voor rapportage op andere formulieren die niet aan downloadbare inhoud zijn gekoppeld, zoals &#39;Contact opnemen&#39; of &#39;Demo-aanvraag&#39;-formulieren.

>[!TIP]
>
>Meer informatie over specifieke &#39;content&#39; met extra filters
>
>* Filteren op: &#39;Openingspagina&#39; BEVAT (bijvoorbeeld):
   >   * /blog
   >   * /ebook
   >   * /webinar
>
>* OF: &#39;URL formulier&#39; BEVAT (bijvoorbeeld)
   >   * /contact
   >   * /demo


Op inhoud gebaseerde rapporten bieden een grote waarde bij het rapporteren van informatie over een willekeurig deel van de trechter, maar worden meestal gebruikt boven aan de trechter om extra inzicht te verschaffen in een eerste betrokkenheid bij leads. Als we kijken naar &#39;Organic Search&#39;, dan is dat meestal het sterkste kanaal om de initiële betrokkenheid (FT) te stimuleren, dan zijn er niet zoveel &#39;Campaign&#39;-gegevens.

&#39;Op inhoud gebaseerde rapporten zijn ideaal om inzicht te krijgen in wat de drijvende kracht achter Leads is, meer bepaald binnen het marketingkanaal op hoger niveau, in dit geval &#39;Organic Search&#39;.

**1,4 | Totale hoofdbetrokkenheid in een bepaald datumbereik**

<table> 
 <tbody>
  <tr>
   <td>Vraag</td> 
   <td>Welke afzetkanalen hadden het meest <i>totale betrokkenheid bij leads</i> in het verleden (week/maand/kwartaal)?</td> 
  </tr>
  <tr>
   <td>Rapporttype</td> 
   <td>Aanraakpunten voor leads en kopers (CRM)<br> 
   Metrisch: Leads ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Datumveld / Datumtype</td> 
   <td>Aanraakpuntdatum</td> 
  </tr>
  <tr>
   <td>Datumbereik</td> 
   <td><i>gewenste datumbereik selecteren</i></td> 
  </tr>
  <tr>
   <td>Groep/Dimension</td> 
   <td>Marketingkanaal (of meer korrelig)</td> 
  </tr>
  <tr>
   <td>Optimale modellen*</td> 
   <td>*Dit rapport gaat minder over het meten waar Leads vandaan komen met een attributiemodel, maar meer over het <i>totaal aantal aanraakpunten (bedrag van de betrokkenheid)</i>, inclusief de deelnemers na de Aanraking voor leads. De totale recordtelling van de aanraakpunten geeft aan welke kanalen de meest toonaangevende betrokkenheid hebben gezien.</td> 
  </tr>
 </tbody>
</table>

**HERINNERING**: Het baseren van uw rapporten rond &quot;AanraakpuntDatum&quot;is de meest weerspiegelende manier om marketing prestaties tijdens een bepaalde datumwaaier te begrijpen. Met Aanraakpunt datum wordt het rapport zodanig gestructureerd dat de toewijzing niet alleen gerelateerd is aan het kanaal, de campagne of de inhoud, maar ook wordt getoond wanneer het aanraakpunt is opgetreden. Dit is de meest effectieve manier om te begrijpen welke marketingactie op een bepaald tijdstip plaatsvond en ook de aanbevolen manier om de impact van marketing te meten, in vergelijking met de marketinguitgaven die tegelijkertijd werden geïnvesteerd. Het wordt aanbevolen om marketinguitgaven of een ROI-analyse uit te voeren (zie 5.1).

**2. GEREKATIFICEERDE LEADEN VOOR MARKETING MET AANWIJZINGEN VOOR KOPERS**

Een van de meest voorkomende rapporten is niet alleen gericht op de betrokkenheid van nieuwe leads of leidingniveau, maar meer in het bijzonder op &#39;marketing qualified leads&#39; (MQL&#39;s). Er zijn een aantal verschillende benaderingen wat betreft de rapportage over MQL&#39;s, afhankelijk van wat [!DNL Marketo Measure] -functies en -functionaliteit waartoe u toegang hebt.

**2,1 | Marketinggekwalificeerde leads per kanaal (multi-touch)**

Deze benadering van het meten van het effect van marketing op het beïnvloeden van MQL&#39;s is in wezen een voortzetting van het rapport &quot;New Leads by Marketing Channel&quot; (1.1), maar met de aanvullende criteria die worden gemeten, zijn meer bepaald MQL&#39;s. Het U-Vormed attributiemodel wordt hier nog steeds aanbevolen om te bepalen welke marketingkanalen en inhoud leads genereren die dan _waarschijnlijk_ om een MQL te worden:

<table> 
 <tbody>
  <tr>
   <td>Vraag</td> 
   <td>Welke marketingkanalen het beste zijn om nieuwe leads te genereren die worden <i>MQLs</i>?</td> 
  </tr>
  <tr>
   <td>Rapporttype</td> 
   <td>Aanraakpunten voor leads en kopers (CRM)<br> 
   Metrisch: Leads ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Filters</td> 
   <td>MQL = true*<br>
   *<i>MQL's kunnen per organisatie verschillend worden gedefinieerd. Zorg ervoor dat de [!DNL Marketo Measure] rapport wordt gefilterd voor MQLs die het zelfde gebied(en) gebruiken zoals andere op MQL gebaseerde rapporten. Een segmentfilter moet op dezelfde manier worden gemaakt voor rapportage over MQL's in [!DNL Marketo Measure] Detecteren.</i></td> 
  </tr>
  <tr>
   <td>Datumveld / Datumtype</td> 
   <td>MQL-datum (of equivalent) / Aanmaakdatum ([!DNL Marketo Measure] Discover)<br> <i>Aanmaakdatum van lead kan ook worden gebruikt in CRM-rapportage als 'MQL-datum' geen optie is in uw CRM. Het is belangrijk om in mening te houden welke het Gebied van de Datum u bij het gebruikt bepaalt de gecodeerde gegevensreeks.</i></td> 
  </tr>
  <tr>
   <td>Datumbereik</td> 
   <td><i>gewenste datumbereik selecteren</i></td> 
  </tr>
  <tr>
   <td>Groep/Dimension</td> 
   <td>Marketingkanaal</td> 
  </tr>
  <tr>
   <td>Optimale modellen</td> 
   <td>First Touch, Lead Creation <strong>U-vorm</strong><br> 
   SUM the 'Count' fields in your CRM reports (Count - First Touch, Count - Lead Creation, Count - U-Shaped)</td> 
  </tr>
 </tbody>
</table>

**2,2 | Marketinggekwalificeerde leads per kanaal (één aanraking, alleen CRM)**

Deze benadering van het meten van de invloed van marketing op de invloed van MKN is meer gericht op het bepalen van welke _enkel aanraakpunt_ was de laatste aanraking voordat de lead MQL bereikte.

>[!NOTE]
>
>Voor het uitvoeren van dit rapport is een &#39;Lead Status&#39;-waarde van &#39;MQL&#39; vereist om de MQL-fase voor traceringsdoeleinden te definiëren (Trechter Stage). Als MQLs niet via het gebied van de Status van de Leiding wordt gevolgd, is het Model van de Attributie van de Douane met de eigenschap van de Banden van de Douane noodzakelijk om een douane &quot;MQL&quot;Stadium in te bouwen [!DNL Marketo Measure] Accountinstellingen.

<table> 
 <tbody>
  <tr>
   <td>Vraag</td> 
   <td>Welke marketingkanalen zijn het sterkst om Leads ertoe te bewegen de MQL-status te bereiken?</td> 
  </tr>
  <tr>
   <td>Rapporttype</td> 
   <td>Aanraakpunten voor leads en kopers (CRM)<br>
   <i>dit rapport is alleen mogelijk binnen CRM-rapportage. Het is niet mogelijk om op bepaalde waarden voor de positie van het aanraakpunt te filteren in [!DNL Marketo Measure] Discover</i></td> 
  </tr>
  <tr>
   <td>Filters</td> 
   <td><strong>De positie van het aanraakpunt bevat "MQL"</strong></td> 
  </tr>
  <tr>
   <td>Datumveld / Datumtype</td> 
   <td>MQL-datum (of gelijkwaardig)</td> 
  </tr>
  <tr>
   <td>Datumbereik</td> 
   <td><i>gewenste datumbereik selecteren</i></td> 
  </tr>
  <tr>
   <td>Groep/Dimension</td> 
   <td>Marketingkanaal</td> 
  </tr>
  <tr>
   <td>Optimale modellen</td> 
   <td><i>Omdat dit rapport wordt gefilterd op één aanraakpunt, zijn de attributiemodellen op het niveau van de Lood niet zo relevant. Net als in het "Lead Engagement Report" (1.4) zou het aantal touchpoint records hier worden benut om te begrijpen welke kanalen de sterkste zijn (elke lead zou slechts één MQL-aanraakpunt hebben).</i></td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>Andere groepen of dimensies verkennen om meer inzicht te krijgen in MQL&#39;s. Zoals vermeld in de andere &#39;Leads with Buyer Touchpoints&#39;-rapporten, biedt het Aanraakpunt voor kopers veel meer granulariteit dan alleen Marketing Channel. Een op inhoud gebaseerd rapport kan ook worden gecombineerd met een van de bovenstaande MQL-rapporten om beter te begrijpen welke inhoud het meest van invloed is op MQL&#39;s.

**3. [!DNL MARKETO MEASURE] PERSONEN MET KOPER TOUCHPOINES**

Er is een derde aangepaste versie [!DNL Marketo Measure] -object in Salesforce dat erg nuttig kan zijn bij het rapporteren van aan mensen gerelateerde metriek: **de [!DNL Marketo Measure] Persoon (BP)**. BP lost het eeuwenoude probleem van hoe te om zowel LEIDEN als contactgegevens in het zelfde rapport te vertegenwoordigen op. Het verenigt alle BT&#39;s die verband houden met een &quot;persoon&quot; (a [!DNL Marketo Measure] De persoon-id is zijn e-mailadres). Of zij als Lood of een Contact bestaan, BP handelt als brugvoorwerp, om rapporten te helpen zich over Lood en Contact uitstrekken, en is zeer nuttig in het produceren van verfijndere rapporten over mensen.

De [!DNL Marketo Measure] Persoon heeft slechts betrekking op een van de aanraakpuntobjecten, het aanraakpunt voor kopers (BT). Dit betekent dat het niet voor een Kans of aan opbrengst verwante metriek kan worden leveraged. A &#39;[!DNL Marketo Measure] Het rapporttype van personen- en kopersaanraakpunten is ideaal voor begrip _totale betrokkenheid_ aangezien het alle BT&#39;s behandelt of het BT op een lood of een Contact meer specifiek betrekking heeft. Bijvoorbeeld - als u een Campagne Salesforce hebt die wordt gebruikt om een Gebeurtenis te volgen, kunt u campagneleden binnen de Campagne van CRM hebben die of als Leidingen OF Contacten bestaan. [!DNL Marketo Measure] zal aanraakpunten creëren voor de campagneleden ongeacht wie, maar zonder [!DNL Marketo Measure] Persoonlijk, standaard zou de rapportering van Salesforce twee afzonderlijke rapporten vereisen om te begrijpen hoeveel _totaal_ aanraakpunten die u hebt van de gebeurtenis: Een die &#39;Leads with Buyer Touchpoints&#39; is en een die &#39;Contact with Buyer Touchpoints&#39; is. Enkele andere [!DNL Marketo Measure] Onderstaande lijst bevat gebruiksgevallen voor individuele rapportage:

**3,1 [!DNL Marketo Measure] Personen die &#39;ebooks&#39; of &#39;whitepapers&#39; hebben gedownload (totale downloads)**

Dit verslag zou hetzelfde zijn als een op inhoud gebaseerd verslag op het niveau van de leiding. In plaats van het aantal toe te wijzen leads aan elk stuk inhoud te meten, gebruikt u een [!DNL Marketo Measure] Personen die verslag uitbrengen, zullen het totaal _aantal downloads_ indien het actief wordt gekapt (het totale aantal aanraakpunten zou het totale aantal downloads/formulierverzendingen vertegenwoordigen).

<table> 
 <tbody>
  <tr>
   <td>Vraag</td> 
   <td>Hoeveel mensen hebben een bepaald middel gedownload?</td> 
  </tr>
  <tr>
   <td>Rapporttype</td> 
   <td>[!DNL Marketo Measure] Personen en aanraakpunten voor kopers (CRM)</td> 
  </tr>
  <tr>
   <td>Filters</td> 
   <td>'URL formulier' BEVAT (bijvoorbeeld)<br>
   <li>/ebook</li>
   <li>/whitepaper</li>
   <i>De bovenstaande filterwaarden zijn alleen voorbeelden. De werkelijke waarde wordt gebaseerd op de URL-structuur van elke organisatie.</i></td> 
  </tr>
  <tr>
   <td>Datumveld / Datumtype</td> 
   <td>Aanraakpuntdatum <i>(wanneer is het element gedownload)</i></td> 
  </tr>
  <tr>
   <td>Datumbereik</td> 
   <td><i>gewenste datumbereik selecteren</i></td> 
  </tr>
  <tr>
   <td>Groep/Dimension</td> 
   <td>URL van formulier</td> 
  </tr>
  <tr>
   <td>Optimale modellen</td> 
   <td>Dit rapport gaat minder over het meten waar de Leads of Contacten van met een attribuutmodel komen, maar meer over het <i>totaal aantal aanraakpunten (bedrag van de betrokkenheid)</i>, inclusief de deelnemers na de Aanraking voor leads. Met dit rapport willen we de <i>bedrag van totale betrokkenheid</i>. De totale recordtelling van aanraakpunten geeft aan welke elementen het meest zijn gedownload.</td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>Voor alle &#39;Leads&#39; met [!DNL Marketo Measure] Het rapporttype van personen, begin door het pre-gebouwde rapport met de titel &quot; aan te passen **[!DNL Marketo Measure]101 | Leads/contactpersonen per kanaal**&quot;. Dit rapport is beschikbaar buiten de doos en is groot [!DNL Marketo Measure] Op personen gebaseerde sandbox. Het is vooraf gebouwd en kan snel voor specifiekere rapporteringsbehoeften worden aangepast.

>[!TIP]
>
>U kunt dit rapport gebruiken om inzicht te krijgen in de totale betrokkenheid van elke marketingdimensie bij het object Buyer Touchpoint, en niet alleen in het downloaden van inhoud zoals in het voorbeeld wordt getoond. Het rapport kan in plaats daarvan worden gegroepeerd of gefilterd op dimensies zoals &#39;Marketing Channel&#39; of &#39;Advertentie Campagnenaam&#39; om de totale betrokkenheid van zowel Leads als Contacten in uw database het best te begrijpen. Wijzig gewoon de filters of groepen in het rapport in nul voor andere dimensies die door andere velden worden vertegenwoordigd vanuit het aanraakpuntobject.

**3,2 [!DNL Marketo Measure] Personen die zich voor een gebeurtenis hebben geregistreerd (alleen CRM)**

_Dit rapport is alleen van toepassing als registratieformulieren worden gehost op uw website(s) die [!DNL Marketo Measure] kan digitaal volgen._

<table> 
 <tbody>
  <tr>
   <td>Vraag</td> 
   <td>Welke Kanalen van de Marketing drijven mijn gebeurtenisregistratie?</td> 
  </tr>
  <tr>
   <td>Rapporttype</td> 
   <td>[!DNL Marketo Measure] Personen en aanraakpunten voor kopers (CRM)</td> 
  </tr>
  <tr>
   <td>Filters</td> 
   <td>'URL formulier' BEVAT (bijvoorbeeld)<br>
   <li>/event</li>
   <i>De bovenstaande filterwaarde zijn alleen voorbeelden. De werkelijke waarde wordt gebaseerd op de URL-structuur van elke organisatie.</i></td> 
  </tr>
  <tr>
   <td>Datumveld / Datumtype</td> 
   <td>Aanraakpuntdatum <i>(wanneer het registratieformulier is ingediend)</i></td> 
  </tr>
  <tr>
   <td>Datumbereik</td> 
   <td><i>gewenste datumbereik selecteren</i></td> 
  </tr>
  <tr>
   <td>Groep/Dimension</td> 
   <td>URL van formulier<br>
   Marketingkanaal</td> 
  </tr>
  <tr>
   <td>Optimale modellen</td> 
   <td>Dit rapport gaat minder over het meten waar de Leads of Contacten van met een attribuutmodel komen, maar meer over het <i>totaal aantal aanraakpunten (aantal registraties)</i>, inclusief de deelnemers na de Aanraking voor leads. Met dit rapport willen we inzicht krijgen in wat de drijvende kracht is achter gebeurtenisregistraties. Het totale aantal aanraakpunten per marketingkanaal geeft aan welke kanalen de meeste registraties hebben aangelegd.</td> 
  </tr>
 </tbody>
</table>

Het belangrijkste verschil met dit rapport is dat de gegevens van het Aanraakpunt voor kopers ook marketingkanaalgegevens zullen leveren. Hoewel u al inzicht hebt in het aantal personen dat zich voor uw gebeurtenissen heeft geregistreerd, biedt dit rapport ook inzicht in welke digitale marketingkanalen, bronnen en/of campagnes mensen naar uw website brengen om zich vervolgens voor de gebeurtenis te registreren.

>[!TIP]
>
>Deze zelfde benadering kan worden gevolgd wanneer het zoeken om inzicht in webinar registraties of misschien op bestelling webinar downloads (als zij een gevergd bezit zijn) te verkrijgen. Het enige verschil is de filterwaarde in de URL van het formulier als deze formulieren worden gehost op unieke pagina&#39;s van uw website. Het doel is echter hetzelfde. Het beantwoordt de vragen, &quot;welke van mijn Kanalen van de Marketing drijven de meeste registraties/op bestelling webinar downloads.

**3,3 [!DNL Marketo Measure] Personen met aanraakpunten met koper (aanraakpuntvalidatie)**

Het overwegen van [!DNL Marketo Measure] De persoon staat ons toe om over alle aanraakpunten in één enkel rapport te rapporteren, is het ideale rapporttype om te gebruiken wanneer het zoeken om uw gegevens te bevestigen. Wij willen ervoor zorgen dat wij geen touchpoints vergeten die kunnen onthullen waar, bijvoorbeeld, er een kwestie in de configuratie van uw &quot;Kanalen van de Marketing&quot;is (zie de steunartikelen verbonden hieronder voor meer informatie over het vormen van uw &quot;Kanalen van de Marketing&quot;).

* [Online aangepaste kanaalinstelling](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
* [Aangepaste kanaalinstelling offline](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)

Hoofdzakelijk, zullen de aanraakpuntgegevens op wat zijn gevolgd door wijzen [!DNL Marketo Measure] en kan worden gecontroleerd om ervoor te zorgen dat uw configuratie input aanpast die op dingen zoals wordt gebaseerd: UTM-parameterwaarden, Verwijzen naar pagina&#39;s of Campagnetypen. Als de aanraakpuntgegevens niet overeenkomen met uw configuratie, moet waarschijnlijk iets worden aangepast. Buiten de opstelling van het Kanaal van de Marketing, kunt u touchpoint gegevens bekijken om te bepalen welke aanraakpunten kunnen moeten worden vereist [onderdrukt](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md) of [gesegmenteerd](/help/advanced-marketo-measure-features/segmentation/custom-segmentation.md). Het wordt aanbevolen uw aanraakpuntgegevens te controleren in een &#39;[!DNL Marketo Measure] Rapport van personen en aanspreekpunten voor kopers, indien mogelijk, aan het einde van elke maand of elk kwartaal. Zo weet u zeker dat uw toewijzing zo nauwkeurig mogelijk is. De &#39;[!DNL Marketo Measure] 101 | Het rapport Leads/Contacts by Channel dat offline beschikbaar is, is een uitstekende plaats om aan de slag te gaan. Neem de volgende velden op als deze nog niet zijn opgenomen om enkele van de meest essentiële onderdelen van de configuratie te controleren:

* **Marketingkanaal** - Path = Marketing Channel.Subchannel (waarden ingesteld in [!DNL Marketo Measure])
* **Aanraakpuntbron** = utm_source
* **Normaal** = utm_medium (online aanraakpunten) OF CRM-cameratype (offline aanraakpunten)
* **Referentiepagina** (gebruikt de configuratie &#39;Onlinekanalen&#39;)
* **Openingspagina - Raw** (gebruikt de configuratie &#39;Onlinekanalen&#39;) ook als veelgebruikte invoer voor onderdrukking van aanraakpunten op het tabblad &#39;Instellingen aanraakpunt&#39; van uw instellingen)
* **URL van formulier** (veelvoorkomende invoer voor aanraakpuntonderdrukking op het tabblad Aanraakpuntinstellingen van uw instellingen)

**KOPER ATTRIBUTION TOUCHPOINT (BAT)**

Aanraakpunten voor koperkenmerken (BBT&#39;s) vertegenwoordigen de relevante aanraakpunten van alle contactpersonen die zijn verbonden met de opportunity (via de rol van contactpersoon voor opportunity of via een id van een gedeelde account, afhankelijk van uw instellingen). In tegenstelling tot BT&#39;s (die voornamelijk met mensen zijn verbonden) kunnen BBT&#39;s met inkomsten worden geassocieerd. Als dusdanig, zult u BBTs gebruiken om vragen te beantwoorden met betrekking tot kansen, hoofdzakelijk open _Opportuniteiten/inkomsten pijpleiding_ en gesloten won _Opportunity/Deals/Revenue_. Een BBT wordt gecreëerd via de BT-records van een contactpersoon zodra een Opportunity wordt gecreëerd onder dezelfde account als de contactpersoon (het BT wordt niet omgezet in een BBT). Er wordt alleen naar de BT-gegevens verwezen om een extra record te creëren - de BBT die vervolgens betrekking heeft op de Opportunity).

Met het Aanraakpunt voor koperkenmerken kunnen we de invloed van marketing in de trechter dieper meten. _De diepte van de trechter waarop u wilt meten, kan worden weergegeven door de verschillende multitouch-attributiemodellen_.

Het overwegen van BBTs primaire verhouding is met de Kans, worden zij gebruikt om vragen zoals te beantwoorden:

* Welke van mijn marketinginspanningen hebben de meeste kansen beïnvloed?
* Hoeveel nieuwe pijpleidingsopbrengst kan ik aan elk van mijn marketing kanalen toeschrijven?
* Welke van mijn campagnes hebben vorig kwartaal het grootste rendement op investeringen gezien?

De [toewijzingsmodellen](/help/introduction-to-marketo-measure/overview-resources/marketo-measure-attribution-models.md) het verstrekken van beste inzicht in Op kansen-gebaseerde metriek zijn:

**W-vorm** - De &#39;_Pipettenmodel_&quot;. In het W-Shaped-model zijn drie mijlpalen aanraakpunten opgenomen. In dit model worden de FT-, LC- en OC-aanraakpunten elk toegeschreven aan 30% van het attribuut credit. De resterende 10% wordt in gelijke mate toegeschreven aan alle tussenliggende aanraakpunten tussen de drie mijlpalen.

<table> 
 <tbody>
  <tr>
   <td><img src="assets/bizible-reporting-guide-2.png"></td> 
   <td>Dit model vat hoofdzakelijk de reis van een nieuwe Kans samen die typisch synoniem met de generatie van nieuwe Inkomsten van de Pijpleiding is.<p>
   <p>
   Wanneer het zoeken om het effect van marketing op nieuwe Kansen of nieuwe geproduceerde pijpleiding te meten, wordt het model W-Vormd geadviseerd.</td> 
  </tr>
 </tbody>
</table>

**Volledig pad** - De &#39;_Afgesloten winstmodel_&quot;. Dit model omvat de vier mijlpalen touchpoints: FT, LC, OC en Gesloten. Elk krijgt 22,5% van de Opportunity credit en de resterende 10% wordt gelijkelijk verdeeld over de intermediaire toeslagen.

<table> 
 <tbody>
  <tr>
   <td><img src="assets/bizible-reporting-guide-3.png"></td> 
   <td>Dit model vat hoofdzakelijk de reis van een gesloten won Overeenkomst samen die typisch synoniem met gesloten woningen/boekingen is.<p>
   <p>
   Wanneer het zoeken om het effect van de marketing op gesloten won Deals of gesloten won Ontvangsten te meten, wordt het Volledige Model van de Weg geadviseerd.</td> 
  </tr>
 </tbody>
</table>

Dit model vat hoofdzakelijk de reis van een gesloten won Overeenkomst samen die typisch synoniem met gesloten woningen/boekingen is.

Wanneer het zoeken om het effect van de marketing op gesloten won Deals of gesloten won Ontvangsten te meten, wordt het Volledige Model van de Weg geadviseerd.

**Aangepast** - [!DNL Marketo Measure] biedt ook een model van de Attributie van de Douane dat gebruikers toestaat om te kiezen welke aanraakpunten of douanefasen in hun model te omvatten. Bovendien kunnen gebruikers het toewijzingspercentage bepalen dat aan deze aanraakpunten en fasen wordt toegewezen. Afhankelijk van de opstelling van uw douanemodel, kan het het meest geschikt worden gebruikt om of Kansen en Pijpleiding OF, Overeenkomsten en Gesloten Won Inkomsten te meten. Houd dit in gedachten wanneer u het gebruikt in uw rapportage.

>[!NOTE]
>
>Het aangepaste kenmerkingsmodel is een extra functie die niet voor alle klanten beschikbaar is. Neem contact op met het accountteam van Adobe (uw accountmanager) voor meer informatie over het toevoegen van deze functie aan uw account.

Marktdeelnemers moeten meestal weten: &quot;Waar komen mijn kansen vandaan?&quot; Net als bij rapportage op hoofdniveau werd deze vraag historisch beantwoord met één eendimensionale waarde (bijvoorbeeld primaire campagnebron). We weten echter dat er veel meer gaat naar de ontwikkeling van een opportunity dan één aanraakpunt van één enkele contactpersoon. Er zijn typisch verscheidene aanraakpunten van diverse kanalen en door veelvoudige belanghebbenden die een Kans in verwezenlijking beïnvloeden. Met [!DNL Marketo Measure], kunnen we alle aanraakpunten van een account bekijken om te begrijpen waar een opportunity vandaan kwam. Daarna kunnen we echter elk aanraakpunt dat zich heeft voorgedaan nadat de Opportunity is gecreëerd en tot op het moment dat de Opportunity is is gesloten, aan de oppervlakte blijven. Op die manier kunnen we niet alleen een multi-touchbenadering gebruiken om te begrijpen waar een opportuniteit vandaan kwam, maar ook wat het heeft beïnvloed om af te sluiten en uiteindelijk een gesloten eigen inkomen te vertegenwoordigen. Dit geeft inzicht in verschillende vragen zoals, &quot;wat beïnvloedt marketing de invloed op het beïnvloeden van Deals om te sluiten?&quot;, &quot;welke marketing drijft gesloten won Ontvangsten.&quot; en uiteindelijk, &quot;welke van mijn marketing inspanningen zien het grootste ROI?&quot;

## AANBEVOLEN RAPPORTEN MET BEHULP VAN HET TOUCHPOINT VOOR DE KENMERK VAN DE KOPER (BAT) {#recommended-reports-using-the-buyer-attribution-touchpoint}

**4,1 | Nieuwe kansen per marketingkanaal**

Het samenvatten van de gegevens van het Aanraakpunt van de Attributie van de Koper van Uw Kanalen door het gebied &quot;het Kanaal van de Marketing&quot;is de hoogste mening die vertegenwoordigt welke kanalen/tactieken nieuwe Kansen in verwezenlijking beïnvloeden. Door dit rapport te structureren rond een &#39;Date Type&#39; = &#39;Opportunity Created Date&#39; zorgt u ervoor dat we ook een overzicht geven van het rapport op basis van wanneer de Opportunity daadwerkelijk is gemaakt in uw CRM. De aanraakpunten kunnen van enige tijd eerder zijn geweest, maar zij zullen nog steeds betrekking hebben op de Kansen die binnen de bepaalde Waaier van de Datum zijn gecreeerd en zo attributietoekening ontvangen aangezien zij worden erkend als beïnvloedend de Kans.

<table> 
 <tbody>
  <tr>
   <td>Vraag</td> 
   <td>Wat <i>afzetkanalen</i> beïnvloeden we kansen op creatie?</td> 
  </tr>
  <tr>
   <td>Rapporttype</td> 
   <td>Aanraakpunten voor koperkenmerken met opportunity (CRM)<br> 
   Metrisch: Kansen ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Filters</td> 
   <td>
   <li>Opportunity Stage* <i>(optioneel, afhankelijk van welke specifieke mogelijkheden u wilt beperken tot het rapport. U wilt alleen BBT's rapporteren die nog steeds alleen betrekking hebben op 'Open'-kansen (bijvoorbeeld)</i></li>
   <li>Het Type van kans (het is gemeenschappelijk om binnen op bepaalde Kansen te filtreren, d.w.z. 'Nieuwe zakelijke activiteiten' in tegenstelling tot <i>alles</i> Kansen)</li><br>
   *Een segmentfilter voor 'Opportunity Type' moet worden gebruikt in [!DNL Marketo Measure] Discover</td> 
  </tr>
  <tr>
   <td>Datumveld / Datumtype</td> 
   <td>Aanmaakdatum van opportunity (CRM) / Aanmaakdatum (Discover)</td> 
  </tr>
  <tr>
   <td>Datumbereik</td> 
   <td><i>gewenste datumbereik selecteren</i></td> 
  </tr>
  <tr>
   <td>Groep/Dimension</td> 
   <td>Marketingkanaal</td> 
  </tr>
  <tr>
   <td>Optimale modellen</td> 
   <td><strong>W-vorm</strong><br>
   SUM de "W-Shaped"gebieden in uw CRM- rapporten (Telling - W-Vormd, Inkomsten - W-Vormd)</td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>Voor elk rapporttype &#39;Aanraakpunten voor koperskenmerk met opportuniteiten&#39; begint u met het aanpassen van het vooraf gebouwde rapport met de naam &#39;[!DNL Marketo Measure] 101 | Kanaalmogelijkheden&quot;. Dit rapport is beschikbaar uit-van-de doos en is een grote zandbak vooraf gebouwd zoals die in de lijst hierboven wordt beschreven en kan snel voor specifiekere rapporteringsbehoeften worden aangepast (het rapport gebruikt een Volledig model van de Weg uit-van-de-doos zodat zeker om het rapport aan te passen om een ander attributiemodel, in dit geval, het model W-Vormd) te omvatten.

>[!TIP]
>
>Het hierboven geschetste verslag zou ook worden gebruikt om te begrijpen hoeveel valuta ook moet worden toegewezen. Bij rapportage op opportuniteitsniveau met behulp van BBT&#39;s zijn er twee belangrijke metriek die moeten worden samengevat: valuta (het bedrag van de Kans) en het verslag van de Kans zelf. In het bovenstaande voorbeeld meten we meer specifiek open Opportunity en nieuwe pijpleidinginkomsten.

>[!TIP]
>
>Nog gedetailleerder inzicht krijgt u door het rapport samen te vatten met andere beschikbare velden van het Touchpoint-object voor koperkenmerken. Dit gebeurt op dezelfde manier als bij Aanraakpunten voor koper (1.2). Doe dit door extra groeperingen (CRM) of dimensies (Discover) toe te voegen. Afhankelijk van het kanaal (dat uw rol kan vertegenwoordigen), kunnen er extra details voorbij het campagneniveau zijn waarin u meer inzicht wilt krijgen. We gaan hieronder naar &#39;Betaalde zoekopdracht&#39;:

<table> 
 <tbody>
  <tr>
   <td>Vraag</td> 
   <td>Welke <i>trefwoorden</i> van mijn advertenties van de Gebetaling van het Onderzoek de meeste pijpleidingsinkomsten genereren?
</td> 
  </tr>
  <tr>
   <td>Rapporttype</td> 
   <td>Aanraakpunten voor koperkenmerken met opportunity (CRM)<br> 
   Metrisch: Kansen ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Filters</td> 
   <td>
   <li>Marketingkanaal = Betaalde zoekopdracht</li>
   <li>Opportunity Stage* <i>(optioneel, afhankelijk van welke specifieke mogelijkheden u wilt beperken tot het rapport. Dit voorbeeld is gebaseerd op de waarde van Pipeline Revenue (Belastingstelsel), die wordt gedefinieerd in [!DNL Marketo Measure] door "Open" Opportuniteiten die potentiële inkomsten vertegenwoordigen/open pijpleiding)</i></li>
   <li>Het Type van kans (het is gemeenschappelijk om binnen op bepaalde Kansen te filtreren, d.w.z. 'Nieuwe zakelijke activiteiten' in tegenstelling tot <i>alles</i> Kansen)</li><br>
   *Een segmentfilter voor 'Opportunity Type' moet worden gebruikt in [!DNL Marketo Measure] Discover</td> 
  </tr>
  <tr>
   <td>Datumveld / Datumtype</td> 
   <td>Aanmaakdatum van opportunity</td> 
  </tr>
  <tr>
   <td>Datumbereik</td> 
   <td><i>gewenste datumbereik selecteren</i></td> 
  </tr>
  <tr>
   <td>Groep/Dimension</td> 
   <td>Trefwoordtekst (CRM)<br> 
   Trefwoord (vaststellen)</td> 
  </tr>
  <tr>
   <td>Optimale modellen</td> 
   <td><strong>W-vorm</strong><br>
   SUM de "W-Shaped"gebieden in uw CRM- rapporten (Telling - W-Vormd, Inkomsten - W-Vormd)</td> 
  </tr>
 </tbody>
</table>

**4,2 | Overeenkomsten per marketingkanaal**

Dit rapport zou in wezen het zelfde als het eerste Voorbeeld van het Aanraakpunt van de Attributie van de Koper (4.1) zijn behalve metrisch is nu veranderd van open Kansen in gesloten woningen. De metrische waarde moet altijd aangeven welk toewijzingsmodel moet worden gebruikt. Aangezien we nu naar gesloten won Deals en hun verwante BBTs bekijken, zouden wij een model moeten gebruiken dat de volledige reis van de koper (Overeenkomst) vertegenwoordigt. Hierdoor wordt gegarandeerd dat elke marketingaanraaktrack tijdens de reis van de koper een toeschrijving ontvangt:

<table> 
 <tbody>
  <tr>
   <td>Vraag</td> 
   <td>Wat <i>afzetkanalen</i> beïnvloeden om Overeenkomsten te sluiten?</td> 
  </tr>
  <tr>
   <td>Rapporttype</td> 
   <td>Aanraakpunten voor koperkenmerken met opportunity (CRM)<br> 
   Metrisch: Deals ([!DNL Marketo Measure] Discover)</td> 
  </tr>
  <tr>
   <td>Filters</td> 
   <td>
   <li>Opportunity-werkgebied (<i>Alleen gesloten onlinemogelijkheden moeten in het rapport worden opgenomen</i>) OF</li>
   <li>Opportunity Won = true</li>
   <li>Het Type van kans (het is gemeenschappelijk om binnen op bepaalde Kansen te filtreren, d.w.z. "Nieuwe Zaken"in tegenstelling tot alle Kansen)<br>
   </td> 
  </tr>
  <tr>
   <td>Datumveld / Datumtype</td> 
   <td>Datum van sluiting opportunity</td> 
  </tr>
  <tr>
   <td>Datumbereik</td> 
   <td><i>gewenste datumbereik selecteren</i></td> 
  </tr>
  <tr>
   <td>Groep/Dimension</td> 
   <td>Marketingkanaal</td> 
  </tr>
  <tr>
   <td>Optimale modellen</td> 
   <td><strong>Volledig pad</strong><br>
   SUM de "Volledige Weg"gebieden in uw rapporten van CRM (Telling - Volledige Weg, Inkomsten - Volledige Weg)</td> 
  </tr>
 </tbody>
</table>

**HERINNERING**: Het is belangrijk om te herinneren aan filter voor de specifieke Kansen u in BBT gebaseerde rapportering wilt omvatten, vooral wanneer het &quot;Open Kansen en de Inkomsten van de Pijpleiding&quot;vs komt. &quot;Deals and Closed Won Revenue&quot; (Belastingovereenkomsten en gesloten winsten). Dit gebeurt gewoonlijk via een filter &#39;Opportunity Stage&#39; (het filter &#39;Opportunity Won&#39; = true/false kan hier ook erg nuttig zijn).

**5. ROI ([!DNL Marketo Measure] Alleen zoeken)**

De [!DNL Marketo Measure] Ontdek dashboards verstrekken een high-level mening van uw Marketing Prestaties gebruikend [!DNL Marketo Measure] toewijzingsgegevens. Deze samengevoegde dashboards verstrekken zeer belangrijke marketing uitgaven en ROI gegevens die niet in uw CRM- rapportering beschikbaar zijn. Dankzij deze vooraf gebouwde omgeving kunt u uw marketingprestaties afstemmen op uw ROI-gegevens, zodat u beslissingen kunt nemen die u kunt nemen met betrekking tot uw marketing.

>[!TIP]
>
>Wanneer u een vraag hebt met betrekking tot investeringsrendement, uitgaven of kosten, [!DNL Marketo Measure] Discover is de beste plaats voor rapportage!

De [!DNL Marketo Measure] Detectie-dashboards bestaan uit gegevens van aanraakpunten voor kopers en kenmerk-aanraakpunten voor kopers en belangrijke CRM-gegevens. Het belangrijkste verschil tussen CRM-rapportage en -rapportage in [!DNL Marketo Measure] Detecteren is dat de aanraakpuntgegevens in Discover meer op &#39;geaggregeerde&#39; wijze worden gepresenteerd en per dimensie worden samengevat (marketingkanaal, campagne, enz.) in tegenstelling tot individuele aanraakpuntrecords die vervolgens kunnen worden samengevat. [!DNL Marketo Measure] Ontdek op een hoog niveau welke van uw inspanningen de grootste invloed op Leads, Opps, Deals hebben en hoeveel inkomsten eraan moeten worden toegeschreven. Zodra wij de toegeschreven opbrengst hebben die via de diverse attributiemodellen wordt berekend (het Volledige Weg wordt geadviseerd voor het toewijzen van gesloten woningen/het boeken), kunnen wij het dan meten tegen hoeveel in de zelfde dimensie (het Kanaal van de Marketing, Subchannel, of Campagne) werd uitgegeven. Dat geeft ons de **ROI**.

>[!TIP]
>
>Één van de belangrijkste dingen om te herinneren wanneer het melden in Discover is welk Type van Gegevens u gebruikt om te filtreren. Het Type van datum zal dicteren welke gegevensreeks [!DNL Marketo Measure] wordt gebruikt in de verschillende tegels.

* **Aanraakpuntdatum**: Geeft de verwante gegevens weer die een &#39;aanraakpuntdatum&#39; hadden in de opgegeven tijdlijn
* **Aanmaakdatum**: Geeft de verwante gegevens weer die een &#39;Aanmaakdatum&#39; hadden in de opgegeven tijdlijn
* **Gesloten datum**: Geeft de verwante gegevens weer die een &#39;Sluiten Datum&#39; in de opgegeven tijdlijn hadden

Bij rapportage over investeringsrendement [!DNL Marketo Measure] Het wordt aanbevolen een Date Type = &quot;Touchpoint Date&quot; te gebruiken. Om het rendement van elke geïnvesteerde dollar te bepalen, moeten we ervoor zorgen dat de opbrengsten worden toegerekend aan de datum waarop de investering is gedaan. Het &quot;Type van Datum&quot;= &quot;Datum van het Aanraakpunt&quot;verzekert de rapporten op deze manier in tegenstelling tot wanneer de Kans werd gecreeerd (creeer Datum) of gesloten (Gesloten Datum). Laten we eens nader kijken:

De hieronder gemarkeerde filters zijn van cruciaal belang voor een ROI-rapport in [!DNL Marketo Measure] (Meestal zult u deze filters instellen in de printplaten &#39;Overzicht&#39;, &#39;CMO&#39; of &#39;ROI&#39;):

**5,1 | ROI in de Raad &quot;Overzicht&quot;**

![](assets/bizible-reporting-guide-4.png)

Het bereik &#39;Datum&#39; stelt niet alleen de cohort van aanraakpunten (op aanraakpuntdatum) in die de toewijzing ontvangen, maar definieert ook het bereik dat de tegel of kolommen van de &#39;Snijden&#39; vertegenwoordigen.
[!DNL Marketo Measure] bekijkt eenvoudig de waaier van de &quot;Datum&quot;om te bepalen hoeveel of in totaal, of op het Kanaal van de Marketing, Subchannel, of de niveaus van de Campagne werd uitgegeven Zie hieronder:

![](assets/bizible-reporting-guide-5.png)

In de bovenstaande screenshot worden de gegevens over marketinguitgaven in de afgelopen 3 volledige maanden weergegeven. In dit voorbeeld werd $12.970 uitgegeven over alle kanalen. Dit nummer bestaat uit de gegevens over marketinguitgaven [!DNL Marketo Measure] heeft van integratie met om het even welk van uw verbonden advertenties (Google AdWords, Bing Ads, Facebook Ads, LinkedIn, DoubleClick) en om het even welke extra Marketing die uitgaven zijn geupload binnen uw rekening, of automatisch getrokken uit een verslagen van de Campagne in uw CRM. In het voorbeeld wordt ook getoond hoeveel gesloten &#39;Revenue&#39; ook kan worden toegeschreven aan aanraakpunten die zich in hetzelfde datumbereik (groene vakken) hebben voorgedaan. Dit is hoe ROI wordt berekend: inkomsten die worden toegerekend aan aanraakpunten die afkomstig zijn van investeringen in dezelfde datumbereik:

![](assets/bizible-reporting-guide-6.png)

**HERINNERING**: [!DNL Marketo Measure] definieert &#39;Inkomsten&#39; als afgesloten ontvangsten of boekingen en definieert &#39;Inkomsten uit pijpleidingen&#39; als _open/potentiële inkomsten uit open kansen_.

Een andere belangrijke terugname van het hierboven vermelde ROI-verslag is de &quot;Pipeline Revenue&quot; (inkomsten uit pijpleidingen) die in de rode doos zijn vertegenwoordigd. Dit betekent dat van de $12.970 die in de afgelopen drie volledige maanden wordt geïnvesteerd, wij momenteel $705.199 van gesloten &quot;opbrengst&quot;toeschrijven maar wij ook $6.905.532 van open, potentiële opbrengst (&quot;de Opbrengst van de Pijpleiding) aan aanraakpunten die van de zelfde investering worden gecreeerd! Wat we zouden verwachten is dat een deel van de &#39;Pipeline Revenue&#39; in de loop der tijd dicht bij elkaar komt, dat het &#39;Revenue&#39;-nummer voedt, en dus het ROI-nummer zou stijgen in de loop der tijd. Het &#39;bestedingsnummer&#39; is gecorrigeerd omdat we niet terug in de tijd kunnen gaan om meer door te brengen in de laatste drie maanden. Dit is het belang van het gebruik van een &#39;Date Type&#39; van &quot;Touchpoint Date&quot;binnen om het even welke ROI rapportering: De waarde (**I**) en zorgt voor de hoeveelheid (**R**() de toegerekende inkomsten worden toegerekend aan dezelfde aanraakpunten die afkomstig waren van de investering (voor elke uitgegeven dollar, hoeveel werd er gemaakt?).

>[!TIP]
>
>Filter in op de Kanalen van de Marketing, Subkanalen, en/of Campagnes waarin u de gegevens van de Uitgaven van de Marketing kent volledig en nauwkeurig is. Het bovenstaande voorbeeld is voor alle Kanalen van de Marketing, maar als sommige Kanalen niet de verwante geuploade gegevens van de Uitgaven van de Marketing hebben, zou de ROI rapportering onnauwkeurig kunnen zijn. Zie het voorbeeld hieronder, dit keer in het &quot;ROI&quot;bord dat op de Campagnes binnen het Kanaal van de Marketing van &quot;Betaalde Onderzoek&quot;wordt geconcentreerd, een Kanaal met zeer korrelige gegevens van de Uitgaven van de Marketing via de integraties.

![](assets/bizible-reporting-guide-7.png)
