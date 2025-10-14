---
description: "[!DNL Marketo Measure] Rapportagehandleiding -  [!DNL Marketo Measure]"
title: "[!DNL Marketo Measure] Rapportagehandleiding"
exl-id: 9b991f9e-c187-4b43-b0a8-8ed3e9a6056b
feature: Reporting
source-git-commit: 3119b1754bba49139c1a6756851ada580e09c1ef
workflow-type: tm+mt
source-wordcount: '5602'
ht-degree: 0%

---

# [!DNL Marketo Measure] Rapportagehandleiding {#marketo-measure-reporting-guide}

>[!NOTE]
>
>U kunt instructies zien die &quot;[!DNL Marketo Measure]&quot;in de documentatie specificeren, maar nog zie &quot;Bizible&quot;in uw CRM. We werken eraan dat dit wordt bijgewerkt en de herbranding wordt binnenkort weerspiegeld in uw CRM.

Voordat u een [!DNL Marketo Measure] -rapport gaat maken, is het het meest belangrijk om te bevestigen dat uw [!DNL Marketo Measure] -accountinstellingen zijn gecontroleerd en geconfigureerd om ervoor te zorgen dat de gegevens in de rapporten accuraat zijn en de specifieke kenmerken van uw bedrijf weerspiegelen. Daarnaast werken de rapportageprojecten het best wanneer ze een gestructureerd proces volgen. Justin Norris, a [!DNL Marketo Measure] macht-gebruiker, pleitte en partner van [&#x200B; Perkuto &#x200B;](https://perkuto.com/){target="_blank"}  vatte deskundig samen [&#x200B; hoe te om rapporterend in  [!DNL Marketo Measure] &#x200B;](https://perkuto.com/blog/turning-attribution-data-into-actionable-insights/){target="_blank"}  te benaderen:

**Vestig Doelstellingen**: &quot;De eerste vraag is &quot;waarom meten wij?&quot; De Tovenaar van Lori van [&#x200B; Forrester Onderzoek &#x200B;](https://go.forrester.com/) vatte het in een mooi overzicht in webinar van a [&#x200B; Marketo &#x200B;](https://www.marketo.com/webinars/beyond-revenue-performance-real-kpis-of-b2b-marketing/){target="_blank"} . Volgens haar &quot;meten we om een besluit of de waarde van marketing te bewijzen of te valideren of om beter te worden (procesverbetering)&quot;. We willen hieraan toevoegen dat de inzichten van goede metingen ook input en begeleiding geven in het marketingplanningsproces.

Dus voordat je begint, is het essentieel om kristalhelder te zijn over je doelen, de vragen die je probeert te beantwoorden, of de problemen die je probeert op te lossen. Welk verhaal wil je vertellen? Welke besluiten zullen er naar aanleiding hiervan worden genomen? Maar al te vaak worden deze fundamentals slecht bedacht, wat leidt tot frustratie voor alle betrokkenen.&quot;

**Ontwerp van het Rapport**: &quot;daarna, moet u het rapport ontwerpen en de specifieke dimensies, metriek, en dataset bepalen het zal bevatten. Een algemene ervaring is om een zakelijke gebruiker precies te voorzien van wat hij of zij vraagt, alleen als hij of zij nog steeds het gevoel heeft dat hij of zij niet aan zijn of haar behoeften voldoet. Dit is omdat het inzicht een bedrijfsgebruiker eigenlijk zoekt niet altijd in het rapport bevat zij vragen. Een goede analist (of een MOPS-persoon met een analist die aanstaat) zal vragen stellen, gemeenschappelijke definities vaststellen (&quot;dus, wat bedoel je eigenlijk met lood?&quot;) en zelfs een visuele uitleg van het eindverslag geven om te zorgen dat er overeenstemming is. Pas dan bouwt u het rapport, wetend u hebt een stevige reeks vereisten.&quot;

**het Rapport bouwt**: &quot;Zodra u gaat bouwen, is het niet ongewoon om in wegversperringen of dood-einden in werking te stellen. Bijvoorbeeld, zou u kunnen ontdekken dat u een essentieel gegevenspunt mist of dat uw voorwerpen niet in de manier verbinden die u nodig hebt. Om deze problemen op te lossen, denk ik ook dat het cruciaal is om te begrijpen wat er gebeurt &quot;onder de kap&quot; in je rapportagemachine. Dankzij deze vloeiendheid kunt u snel een rapportageaanvraag samenstellen en beoordelen of dit haalbaar is (en eenvoudig creatieve oplossingen bedenken als dit niet het geval is).&quot;

Laten we eens kijken naar &quot;onder de kap&quot; om beter te begrijpen wat de [!DNL Marketo Measure] kenmerk-rapportagemachine uitvoert.

## Buyer Touchpoint Objects (CRM) {#buyer-touchpoint-objects-crm}

Op het hoogste niveau, zijn er twee rapporteringscategorieën die op de twee verschillende voorwerpen van Buyer Touchpoint worden gebaseerd: Deze categorieën bepalen welk type van [!DNL Marketo Measure] gegevens u zou willen rapporteren over: gegevens met betrekking tot een _individu_, of gegevens met betrekking tot een _kans_.

1. **Aanraakpunten van de koper** (BT) / Individuen / Totale Betrokkenheid

   * Vaak gebruikt voor &quot;bovenkant van de trechter&quot;metriek (TOFU) en het melden met betrekking tot _individuen_ (Leads, Contacten, [!DNL Marketo Measure] Personen)
   * BT worden gebruikt voor het begrip van alle marketing interactie met betrekking tot **mensen**, aangezien zij de volledige touchpoint geschiedenis voor elke persoon bevatten. Ter herinnering: deze aanraakpunten worden gemaakt in CRM voor de anonieme First Touch, de Aanwijzing voor leads en alle volgende formulierverzendingen of aanraakpunten die u via
een offlinecampagne of activiteit.

1. **Aanraakpunten van de Attributie van de Koper** (BAT) / Kans / het niveau van de Rekening / Inkomsten

   * Algemeen gebruikt voor &quot;midden en/of bodem van de trechter&quot;metriek (MOFU en BOFU) en het melden met betrekking tot _Kansen_.
   * BAT vertegenwoordigen de relevante touchpoints van alle mensen die met de **kans** worden verbonden (of via de Rollen van het Contact van de Kanaal of via gedeelde identiteitskaart van de Rekening, afhankelijk van uw montages). In tegenstelling tot BT die slechts op mensen betrekking hebben, kan BAT ook met **opbrengst** worden geassocieerd. Als dusdanig, zult u BAT gebruiken om vragen te beantwoorden met betrekking tot kansen, met inbegrip van hoeveel kansen werden geopend of gesloten, of de pijpleidingswaarde en de opbrengst won.

>[!NOTE]
>
>BAT worden gemaakt op basis van BT. In wezen, begint het volgen op het individuele niveau via de BT. Zodra een Kans op een Rekening wordt gecreeerd, zijn alle BT van Contacten onder de zelfde Rekening van verwijzingen voorzien en verkiesbaar om BAT tot stand te brengen die op de Kans betrekking hebben, zodat zult u één of andere afhankelijk van willen gebruiken welke vragen u probeert te antwoorden: vragen met betrekking tot de metriek van &quot;Mensen&quot;(BT rapporten), of vragen met betrekking tot de metriek van &quot;Kans&quot;(BAT rapporten)

Het Artikel van de steun: [&#x200B; Verschil tussen de Aanraakpunten van de Aanwijzing van de Koper en de Aanraakpunten van de Attributie van de Koper &#x200B;](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md#configuration-and-setup){target="_blank"}

## Buyer Touchpoint (BT) {#buyer-touchpoint-bt}

De Buyer Touchpoint (BT) is het object dat wordt gebruikt om elke marketinginteractie te volgen die iemand heeft met uw marketingmaterialen. De reis van elk individu (Lood/Contact/[!DNL Marketo Measure] Persoon) zou door hun verwante BT worden vertegenwoordigd. In [!DNL Marketo Measure] bestaat de reis van een individu uit:

1. Hoe communiceerde deze persoon eerst met ons merk? (Eerste aanraking of _FT_)
1. Hoe heeft deze persoon zich omgezet, gekend of een leider geworden? (Lood creatie of _LC_)
1. Hoe heeft deze persoon anders met ons merk en marketingmateriaal samengewerkt sinds hij een leider werd? (_PostLC_)

De Aanraakpunten van de koper worden gebruikt om vragen met betrekking tot _mensen_ te beantwoorden (&quot;mensen&quot;worden vertegenwoordigd door of Leidt of Contacten binnen CRM), zoals de generatie van het Lood/van het Contact of verwervingsmetriek, eerder dan de verwante metriek van de Kans. Bijvoorbeeld:

* Welke kanalen leveren de meeste Leads?
* Welke kanalen zijn min of meer kostbaar om een nieuwe Lood te creëren?
* Met welke inhoud werken mijn leads/contactpersonen?
* Wat is het marketingverhaal van bepaalde titels, rollen, persona&#39;s?
* Welke kanalen drijven MQLs, of andere lood/contactstatus?

Bedrijven moeten vooral weten: &quot;Waar komen mijn leads/contactpersonen vandaan?&quot; Historisch gezien werd dit beantwoord met een enkele, eendimensionale waarde (bijvoorbeeld Source-leads). Zoals hierboven in #1 en #2 is uiteengezet, weten we echter dat Leads meerdere aanraakpunten kunnen hebben tijdens hun reis om leider te worden. De Buyer Touchpoint stelt ons in staat inzicht te krijgen in de twee meest cruciale interacties die aangeven hoe een lead werd gegenereerd: hun First Touch en hun Lead Creation Touch. De aanraakpunten van de koper zijn ook _multidimensionaal_ betekenend zij ladingen marketing gegevens, hoofdzakelijk waar de persoon uit kwam (het Kanaal van de Marketing) en wat de persoon die met (Inhoud) in dienst wordt genomen.

De [&#x200B; attributiemodellen &#x200B;](/help/introduction-to-marketo-measure/overview-resources/marketo-measure-attribution-models.md){target="_blank"} die het beste inzicht in op mensen-gebaseerde metriek verstrekken zijn:

* **Eerste aanraking** - 100% attributietekening aan de Eerste Aanraking van de Lood (FT)
* **Lood creatie** - 100% attributietekening aan de Lood van de Aanraking van de Aanmaak van de Lood (LC)
* **u-Vormd** - multi-aanraking benadering, met 40% krediet aan FT, 40% krediet aan LC

<table> 
 <tbody>
  <tr>
   <td><img src="assets/bizible-reporting-guide-1.png"></td> 
   <td>Het U-Shape-model is ontworpen om krediet te bieden aan alle aanraakpunten voor kopers die een overzicht geven van hoe een lead een lead is geworden. Terwijl de verdere aanraakpunten van deze Leads ook kunnen worden gemeld om extra overeenkomst (Post LC) te begrijpen, zijn zij geen deel van de <strong> reis van de Aanmaak van de Lood </strong> zodat krijgen zij geen attributietekening in FT, LC of U-gevormde modellen.<p>

&#42; Meestal, wijst de U-vormige attributie op een zelfs 50/50 splitsing tussen FT en LC. Als de lead wordt omgezet in dezelfde sessie als de First Touch, geeft één aanraakpunt zowel de FT- als de LC-aanraakpunten weer. Daarom zou 100% van de toewijzing aan één enkel aanraakpunt worden gegeven.</td>
</tr>
 </tbody>
</table>

In deze modellen wordt veel nadruk gelegd op interacties in een vroeg stadium en op de inzet van trechter. U-Vormen attributie is het geadviseerde model aangezien het in zowel de aanraakpunten van FT als van LC factoren ervoor zorgt dat aan om het even welke aanraking wordt krediet gegeven die de Lood in verwezenlijking beïnvloedde. Met de modellen First Touch en Lead Creation Touch kunt u echter nog meer inzicht krijgen in de specifieke onderdelen van de Lead-reis.

## Aanbevolen rapporten met de Buyer Touchpoint (BT) {#recommended-reports-using-the-buyer-touchpoint-bt}

1. **LEIDEN MET KOPER TOUCHPOINTS**

**1.1 | Nieuwe leads door Marketing Channel**

Het samenvatten van de gegevens van Buyer Touchpoint van uw Lood door het gebied &quot;het Kanaal van de Marketing&quot;is de hoogste mening die vertegenwoordigt welke kanalen/tactieken nieuwe Lood in verwezenlijking beïnvloeden. Door dit rapport te structureren rond een &#39;Date Type&#39; = &quot;Created Date&quot; zorgt u ervoor dat een code van &#39;net new Leads&#39; (wanneer de lead in uw CRM is gemaakt) wordt vastgelegd in het rapport.

<table> 
 <tbody>
  <tr>
   <td>Vraag</td> 
   <td>Welke marketingkanalen beïnvloeden Leads in de creatie?</td> 
  </tr>
  <tr>
   <td>Rapporttype</td> 
   <td>Aanraakpunten voor leads en kopers (CRM) <br>
   Metrisch: leads ([!DNL Marketo Measure] Detecteren)</td> 
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
   <td>Eerste aanraking, Loodverwezenlijking, <strong> u-Vormd </strong><br>
   *SUM de velden 'Count' in uw CRM-rapporten (Count - First Touch, Count - Lead Creation, Count - U-Shaped)</td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>Voor om het even welk &quot;Leidingen met het rapporttype van Aanraakpunten van de Koper&quot;, begin door het pre-gebouwde rapport aan te passen getiteld &quot;[!DNL Marketo Measure] 101 | Leads by Channel&#39;. Dit rapport is beschikbaar buiten de doos en is een grote zandbak vooraf gebouwd zoals die in de lijst hierboven wordt beschreven en kan snel voor specifiekere rapporteringsbehoeften worden aangepast.

**1.2 | Nieuwe lood door Campagne (of meer korrelige inzichten)**

Voor meer gedetailleerd inzicht in de gegevens die in het rapport &#39;New Leads by Marketing Channel&#39; (1.1) worden samengevat, voegt u een extra samenvatting toe op campagnereniveau. Zo kunt u niet alleen begrijpen wat &#39;Marketing Channels&#39; de nieuwe leads in de creatie brengen, maar meer in het bijzonder welke campagnes binnen die kanalen het beste presteren:

<table> 
 <tbody>
  <tr>
   <td>Vraag</td> 
   <td>Welke <i> campagnes </i> beïnvloeden Leads in verwezenlijking?</td> 
  </tr>
  <tr>
   <td>Rapporttype</td> 
   <td>Aanraakpunten voor leads en kopers (CRM) <br>
   Metrisch: leads ([!DNL Marketo Measure] Detecteren)</td> 
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
   <td>Eerste aanraking, Loodverwezenlijking, <strong> u-Vormd </strong><br>
   *SUM de velden 'Count' in uw CRM-rapporten (Count - First Touch, Count - Lead Creation, Count - U-Shaped)</td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>Krijg nog meer korrelig inzicht door het rapport samen te vatten met andere beschikbare gebieden van het voorwerp van Buyer Touchpoint. Doe dit door extra groeperingen (CRM) of afmetingen (Discover) te plaatsen. Afhankelijk van het kanaal (dat uw rol kan vertegenwoordigen), kunnen er extra details voorbij het campagneniveau zijn waarin u inzicht wilt krijgen. Laten we bijvoorbeeld in de onderstaande tabel naar &#39;Betaalde zoekopdracht&#39; gaan...

<table> 
 <tbody>
  <tr>
   <td>Vraag</td> 
   <td>Welke <i> sleutelwoorden </i> beïnvloeden Leads in verwezenlijking?</td> 
  </tr>
  <tr>
   <td>Rapporttype</td> 
   <td>Aanraakpunten voor leads en kopers (CRM) <br>
   Metrisch: leads ([!DNL Marketo Measure] Detecteren)</td> 
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
   <td>Eerste aanraking, Loodverwezenlijking, <strong> u-Vormd </strong><br>
   *SUM de velden 'Count' in uw CRM-rapporten (Count - First Touch, Count - Lead Creation, Count - U-Shaped)</td> 
  </tr>
 </tbody>
</table>

De mate van granulariteit kan per kanaal variëren. De aanbevolen aanpak zou zijn om jezelf af te vragen: &quot;Hoe zit het met &#39;kanaal X&#39;? Ik wil dat graag in detail begrijpen?&quot; Betaalde zoekprogramma&#39;s zijn wellicht ook geïnteresseerd in extra dimensies, zoals:

* Naam advertentiecampagne
* Inhoud toevoegen
* Advertentiegroep

Gebeurtenismanagers zijn echter meer geïnteresseerd in welke specifieke gebeurtenissen of welke soorten gebeurtenissen de meeste leads voor het maken hebben beïnvloed:

* Campagnenaam toevoegen / Campagne Salesforce = specifieke gebeurtenis
* Medium = Campagne &#39;Type&#39;

**HERINNERING**: De extra filters kunnen aan om het even welke hierboven geschetste rapportvariaties of moeten worden toegevoegd onder. Deze filters zouden specifiek voor uw organisatie zijn en zouden iets zijn dat uw teams van Marketing Ops of van Verkoopmanager kon helpen adviseren. Het is niet ongebruikelijk voor een organisatie om de zelfde filters over alle rapporten in werking te stellen om het rapport te verzekeren zo schoon en nauwkeurig mogelijk is. Algemene voorbeelden kunnen zijn:

* Interne records uit tests, meestal per e-mailadres, filteren
* Filteren op basis van bepaalde &#39;recordtypen&#39; die specifiek zijn voor uw bedrijfseenheid

**1.3 | Nieuwe leads by Content (alleen CRM-rapporten)**

<table> 
 <tbody>
  <tr>
   <td>Vraag</td> 
   <td>Welke <i> inhoud </i> beïnvloedt Leads in verwezenlijking?</td> 
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
   <td>Openingspagina <br> 
   URL van formulier</td> 
  </tr>
  <tr>
   <td>Optimale modellen</td> 
   <td>Eerste aanraking, Loodverwezenlijking, <strong> u-Vormd </strong><br></td> 
  </tr>
 </tbody>
</table>

**HERINNERING**: De twee primaire gebieden voor het melden van digitale inhoud/activa zijn &quot;het Bestaan van Pagina&quot;en &quot;Vorm URL&quot;. Deze twee waarden kunnen het zelfde zijn als Lood (voorlegt een vorm) op de zelfde pagina omzet waarin zij &quot;landden&quot;(het Bestaan van Pagina), _nochtans_, soms zijn deze waarden verschillend. De lead kan bijvoorbeeld op een koppeling op Facebook klikken die de gebruiker naar een pagina van uw website stuurt (dit is de waarde &#39;Landing Page&#39;). De lead kan dan verder navigeren van die pagina, de sessie op de site voortzetten en een formulier op een andere pagina (formulier-URL) verzenden. Dit wordt samengevat in één aanraakpunt dat aangeeft waar de lead vandaan komt (marketingkanaal), welke inhoud deze naar de site heeft gebracht (bestemmingspagina) en welke inhoud ze uiteindelijk hebben gedownload (formulier-URL). &#39;Formulier-URL&#39; is ook het veld Ga naar voor rapportage op andere formulieren die niet aan downloadbare inhoud zijn gekoppeld, zoals &#39;Contact opnemen&#39; of &#39;Demo-aanvraag&#39;-formulieren.

>[!TIP]
>
>Meer informatie over specifieke &#39;content&#39; met extra filters
>
>* Filteren op: &#39;Landing Page&#39; BEVAT (bijvoorbeeld):
>   * /blog
>   * /ebook
>   * /webinar
>
>* OR: &#39;Form URL&#39; BEVAT (bijvoorbeeld)
>   * /contact
>   * /demo

Op inhoud gebaseerde rapporten bieden een grote waarde bij het rapporteren van informatie over een willekeurig deel van de trechter, maar worden meestal gebruikt boven aan de trechter om extra inzicht te verschaffen in een eerste betrokkenheid bij leads. Als we kijken naar &#39;Organic Search&#39;, dan is dat meestal het sterkste kanaal om de initiële betrokkenheid (FT) te stimuleren, dan zijn er niet zoveel &#39;Campaign&#39;-gegevens.

&#39;Op inhoud gebaseerde rapporten zijn ideaal om inzicht te krijgen in wat de drijvende kracht achter Leads is, meer bepaald binnen het marketingkanaal op hoger niveau, in dit geval &#39;Organic Search&#39;.

**1.4 | Totale Loodbetrokkenheid in een bepaald Datumbereik**

<table> 
 <tbody>
  <tr>
   <td>Vraag</td> 
   <td>Welke marketing kanalen hebben de meeste <i> totale Loodbetrokkenheid </i> in het verleden (week/maand/kwartaal) gehad?</td> 
  </tr>
  <tr>
   <td>Rapporttype</td> 
   <td>Aanraakpunten voor leads en kopers (CRM) <br> 
   Metrisch: leads ([!DNL Marketo Measure] Detecteren)</td> 
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
   <td>*This het rapport is minder over het meten waar de Leidingen van een attributiemodel maar meer over het <i> totale aantal aanraakpunten (hoeveelheid overeenkomst) </i> komen, inclusief die na de Aanraking van de Aanmaak van de Lood. De totale recordtelling van de aanraakpunten geeft aan welke kanalen de meest toonaangevende betrokkenheid hebben gezien.</td> 
  </tr>
 </tbody>
</table>

**HERINNERING**: Het baseren van uw rapporten rond &quot;Datum van het Aanraakpunt&quot;is de meest weerspiegelende manier om marketing prestaties tijdens een bepaalde datumwaaier te begrijpen. Met &#39;aanraakpunt datum&#39; wordt het rapport zodanig gestructureerd dat de toewijzing niet alleen verband houdt met het kanaal, de campagne of de inhoud, maar ook met het aanraakpunt. Dit is de meest effectieve manier om te begrijpen welke marketingactie op een bepaald tijdstip plaatsvond en ook de aanbevolen manier om de impact van marketing te meten, in vergelijking met de marketinguitgaven die tegelijkertijd werden geïnvesteerd. Het wordt aanbevolen om marketinguitgaven of een ROI-analyse uit te voeren (zie 5.1).

**2. HET MARKETEN VAN GEKWALIFICEERDE LEIDEN MET DE TOUCHPUNTEN VAN DE KOPER**

Een van de meest voorkomende rapporten is niet alleen gericht op de betrokkenheid van nieuwe leads of leidingniveau, maar meer in het bijzonder op &#39;marketing qualified leads&#39; (MQL&#39;s). Er zijn een aantal verschillende benaderingen voor het rapporteren van MQL&#39;s, afhankelijk van welke [!DNL Marketo Measure] -functies en -functionaliteit u kunt gebruiken.

**2.1 | Gekwalificeerde leads voor marketing via kanaal (multi-touch)**

Deze benadering van het meten van het effect van marketing op het beïnvloeden van MQL&#39;s is in wezen een voortzetting van het rapport &quot;New Leads by Marketing Channel&quot; (1.1), maar met de aanvullende criteria die worden gemeten, zijn meer bepaald MQL&#39;s. Het U-Vormde attributiemodel wordt nog geadviseerd hier te identificeren welke marketing kanalen en inhoud lood produceren die dan _waarschijnlijk_ zijn om MQL te worden:

<table> 
 <tbody>
  <tr>
   <td>Vraag</td> 
   <td>Welke marketing kanalen zijn best in het produceren van nieuwe Leidingen die <i> MQLs </i> worden?</td> 
  </tr>
  <tr>
   <td>Rapporttype</td> 
   <td>Aanraakpunten voor leads en kopers (CRM) <br> 
   Metrisch: leads ([!DNL Marketo Measure] Detecteren)</td> 
  </tr>
  <tr>
   <td>Filters</td> 
   <td>MQL = true*<br>
   *<i> MQLs kan verschillend per organisatie worden bepaald. Zorg ervoor dat het [!DNL Marketo Measure] -rapport wordt gefilterd voor MQL's met hetzelfde veld of dezelfde velden als andere MQL-rapporten. Een filter van het Segment zou op de zelfde manier voor rapportering over MQLs in [!DNL Marketo Measure] moeten worden gecreeerd ontdekken.</i></td> 
  </tr>
  <tr>
   <td>Datumveld / Datumtype</td> 
   <td>De Datum van MQL (of gelijkwaardig) / Gemaakt Datum ([!DNL Marketo Measure] ontdekken) <br> <i> leidde Gemaakt Datum kon ook in CRM worden gebruikt meldend als "Datum MQL"geen optie in uw CRM is. Het is belangrijk om in mening te houden welke het Gebied van de Datum u bij het gebruikt bepaalt de gecodeerde gegevensreeks.</i></td> 
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
   <td>Eerste aanraking, Loodverwezenlijking, <strong> u-Vormd </strong><br> 
   SUM the 'Count' fields in your CRM reports (Count - First Touch, Count - Lead Creation, Count - U-Shaped)</td> 
  </tr>
 </tbody>
</table>

**2.2 | Gekwalificeerde leads voor marketing via kanaal (één aanraking, alleen CRM)**

Deze benadering van het meten van het effect van marketing op het beïnvloeden MQLs wordt geconcentreerd meer op het identificeren van welk _enige aanraakpunt_ de laatste aanraking was alvorens Lood MQL bereikte.

>[!NOTE]
>
>Voor het uitvoeren van dit rapport is een &#39;Lead Status&#39;-waarde van &#39;MQL&#39; vereist om de MQL-fase voor traceringsdoeleinden te definiëren (Trechter Stage). Als MQLs niet via het gebied van de Status van de Leiding wordt gevolgd, is het Model van de Attributie van de Douane met de eigenschap van de Stages van de Tanden van de Douane noodzakelijk om een douane &quot;MQL&quot;Stadium in de Montages van de Rekening te bouwen [!DNL Marketo Measure].

<table> 
 <tbody>
  <tr>
   <td>Vraag</td> 
   <td>Welke marketingkanalen zijn het sterkst om Leads ertoe te bewegen de MQL-status te bereiken?</td> 
  </tr>
  <tr>
   <td>Rapporttype</td> 
   <td>Aanraakpunten voor leads en kopers (CRM) <br>
   <i> dit rapport is slechts mogelijk binnen CRM het melden. Het is niet mogelijk te filteren op bepaalde waarden voor Positie aanraakpunt in [!DNL Marketo Measure] Detecteren </i></td> 
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
   <td><i>Omdat dit rapport wordt gefilterd op één aanraakpunt, zijn de attributiemodellen op het niveau van de Lood niet zo relevant. Net als in het "Lead Engagement Report" (1.4) zou het aantal aanraakpuntrecords hier worden gebruikt om te begrijpen welke kanalen de sterkste zijn (elke Lood zou slechts één MQL-aanraakpunt hebben).</i></td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>Andere groepen of dimensies verkennen om meer inzicht te krijgen in MQL&#39;s. Zoals vermeld in de andere &#39;Leads with Buyer Touchpoints&#39;-rapporten, biedt de Buyer Touchpoint veel meer granulariteit dan alleen Marketing Channel. Een op inhoud gebaseerd rapport kan ook worden gecombineerd met een van de bovenstaande MQL-rapporten om beter te begrijpen welke inhoud het meest van invloed is op MQL&#39;s.

**3. [!DNL MARKETO MEASURE] PERSONEN MET KOPER TOUCHPOINTS**

Er is een derde douane [!DNL Marketo Measure] voorwerp in Salesforce dat zeer nuttig kan zijn wanneer het melden van mensen verwante metriek: **de [!DNL Marketo Measure] Persoon (BP)**. BP lost het eeuwenoude probleem van hoe te om zowel LEIDEN als contactgegevens in het zelfde rapport te vertegenwoordigen op. Het verenigt alle BT die betrekking hebben op een &quot;persoon&quot; (een [!DNL Marketo Measure] persoon-id is zijn e-mailadres). Of zij als Lood of een Contact bestaan, BP handelt als brugvoorwerp, om rapporten te helpen zich over Lood en Contact uitstrekken, en is zeer nuttig in het produceren van verfijndere rapporten over mensen.

De persoon van [!DNL Marketo Measure] heeft slechts betrekking op een van de aanraakpuntobjecten, de Buyer Touchpoint (BT). Dit betekent dat het niet voor een Kans of aan opbrengst verwante metriek kan worden gebruikt. Het rapporttype van personen en van de Aanraakpunten van de Koper van &#39;[!DNL Marketo Measure] is groot voor het begrip _totale overeenkomst_ aangezien het allen BT of BT op een Lood of Contact meer specifiek betrekking heeft. Bijvoorbeeld - als u een Campagne van Salesforce hebt die wordt gebruikt om een Gebeurtenis te volgen, kunt u campagsleden binnen de Campagne van CRM hebben die of als Leidingen OF Contacten bestaan. [!DNL Marketo Measure] zal aanraakpunten voor de campagneleden ongeacht tot stand brengen, maar zonder [!DNL Marketo Measure] Persoon, zou standaard Salesforce rapportering twee afzonderlijke rapporten vereisen om te begrijpen hoeveel _totale_ aanraakpunten u van de Gebeurtenis hebt: die &quot;Leidt met de Aanraakpunten van de Koper&quot;en die &quot;Contacten met de Aanraakpunten van de Koper&quot;is. Hieronder vindt u nog een paar andere gevallen van het gebruik van persoonlijke rapporten: [!DNL Marketo Measure]

**3.1 [!DNL Marketo Measure] Personen die &quot;ebooks&quot;of &quot;whitepapers&quot;(totale downloads) hebben gedownload**

Dit verslag zou hetzelfde zijn als een op inhoud gebaseerd verslag op het niveau van de hoofden. Nochtans, eerder dan het kijken om het aantal toe te schrijven Lood aan elk stuk van inhoud te meten, zal het gebruiken van een [!DNL Marketo Measure] rapport van Personen nuttig in het begrip van het totale _aantal downloads_ zijn als het element wordt opgenomen (het totale aantal touchpoints zou het totale aantal downloads/vormvoorlegging vertegenwoordigen).

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
   <td>De "vorm URL"BEVAT (bijvoorbeeld) <br>
   <li>/ebook</li>
   <li>/whitepaper</li>
   <i> de filterwaarden hierboven zijn slechts voorbeelden. De daadwerkelijke waarde zal op de structuur van URL van elke organisatie worden gebaseerd.</i></td> 
  </tr>
  <tr>
   <td>Datumveld / Datumtype</td> 
   <td>Aanraakpuntdatum <i> (wanneer is het element gedownload) </i></td> 
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
   <td>Dit rapport is minder over het meten waar de Leidingen of Contacten van met een attributiemodel komen, maar meer over het <i> totale aantal aanraakpunten (hoeveelheid overeenkomst) </i>, inclusief die na de Aanraking van de Aanmaak van de Lood. Met dit rapport kijken wij de <i> hoeveelheid totale overeenkomst </i> te begrijpen. De totale recordtelling van aanraakpunten geeft aan welke elementen het meest zijn gedownload.</td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>Voor om het even welk &quot;Leidingen met [!DNL Marketo Measure] het rapporttype van Personen&quot;, begin door het pre-gebouwde rapport aan te passen getiteld &quot;**[!DNL Marketo Measure]101 | Leidt/Contacten door Kanaal**&#39;. Dit rapport is beschikbaar buiten de doos en is een grote [!DNL Marketo Measure] op personen gebaseerde zandbak. Het is vooraf gebouwd en kan snel voor specifiekere rapporteringsbehoeften worden aangepast.

>[!TIP]
>
>U kunt dit rapport gebruiken om inzicht te krijgen in de totale betrokkenheid van elke marketingdimensie van het Buyer Touchpoint-object, niet alleen in het downloaden van inhoud zoals in het voorbeeld wordt getoond. Het rapport kan in plaats daarvan worden gegroepeerd of gefilterd op dimensies zoals &#39;Marketing Channel&#39; of &#39;Advertentie Campagnenaam&#39; om de totale betrokkenheid van zowel Leads als Contacten in uw database het best te begrijpen. Wijzig de filters of groepen in het rapport in nul voor andere afmetingen die worden vertegenwoordigd door andere velden van het aanraakpuntobject.

**3.2 [!DNL Marketo Measure] Personen die voor een Gebeurtenis (CRM slechts) hebben geregistreerd**

_Dit rapport is slechts van toepassing als de registratieformulieren op uw website(s) worden ontvangen die [!DNL Marketo Measure] digitaal kan volgen._

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
   <td>De "vorm URL"BEVAT (bijvoorbeeld) <br>
   <li>/event</li>
   <i> de filterwaarde hierboven is slechts voorbeelden. De daadwerkelijke waarde zal op de structuur van URL van elke organisatie worden gebaseerd.</i></td> 
  </tr>
  <tr>
   <td>Datumveld / Datumtype</td> 
   <td>Aanraakpuntdatum <i> (wanneer het registratieformulier werd verzonden) </i></td> 
  </tr>
  <tr>
   <td>Datumbereik</td> 
   <td><i>gewenste datumbereik selecteren</i></td> 
  </tr>
  <tr>
   <td>Groep/Dimension</td> 
   <td>URL van formulier <br>
   Marketingkanaal</td> 
  </tr>
  <tr>
   <td>Optimale modellen</td> 
   <td>Dit rapport is minder over het meten waar de Leidingen of Contacten uit met een attributiemodel komen, maar meer over het <i> totale aantal aanraakpunten (aantal registraties) </i>, inclusief die na de Aanraking van de Aanmaak van de Lood. Met dit rapport willen we inzicht krijgen in wat de drijvende kracht is achter gebeurtenisregistraties. Het totale aantal aanraakpunten per marketingkanaal geeft aan welke kanalen de meeste registraties hebben aangelegd.</td> 
  </tr>
 </tbody>
</table>

Het belangrijkste verschil met dit rapport is dat de Buyer Touchpoint-gegevens ook marketingkanaalgegevens bevatten. Hoewel u al inzicht hebt in het aantal personen dat zich voor uw gebeurtenissen heeft geregistreerd, biedt dit rapport ook inzicht in welke digitale marketingkanalen, bronnen en/of campagnes mensen naar uw website brengen om zich vervolgens voor de gebeurtenis te registreren.

>[!TIP]
>
>Deze zelfde benadering kan worden gevolgd wanneer het zoeken om inzicht in webinar registraties of misschien op bestelling webinar downloads (als zij een gevergd bezit zijn) te verkrijgen. Het enige verschil is de filterwaarde in &#39;Formulier-URL&#39; als deze formulieren worden gehost op unieke pagina&#39;s van uw website. Het doel is echter hetzelfde. Het beantwoordt de vragen, &quot;welke van mijn Kanalen van de Marketing drijven de meeste registraties/op bestelling webinar downloads.

**3.3 [!DNL Marketo Measure] Personen met de Aanraakpunten van de Koper (Bevestiging Aanraakpunt)**

Gezien de persoon van [!DNL Marketo Measure] staat ons toe om op alle aanraakpunten in één enkel rapport te melden, is het het ideale rapporttype aan gebruik wanneer het zoeken om uw gegevens te bevestigen. Wij willen ervoor zorgen dat wij geen touchpoints vergeten die kunnen onthullen waar, bijvoorbeeld, er een kwestie in de configuratie van uw &quot;Kanalen van de Marketing&quot;is (zie de steunartikelen verbonden hieronder voor meer informatie over het vormen van uw &quot;Kanalen van de Marketing&quot;).

* [&#x200B; Online Opstelling van het Kanaal van de Douane &#x200B;](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md){target="_blank"}
* [&#x200B; Offline Opstelling van het Kanaal van de Douane &#x200B;](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md){target="_blank"}

In wezen, zullen de aanraakpuntgegevens op wat door [!DNL Marketo Measure] wordt gevolgd wijzen en kunnen worden gecontroleerd om uw configuratie te verzekeren input die op dingen wordt gebaseerd zoals: UTM parameterwaarden, Verwijzende Pagina&#39;s, of de Types van Campagne aanpast. Als de aanraakpuntgegevens niet overeenkomen met uw configuratie, moet waarschijnlijk iets worden aangepast. Buiten de opstelling van het Kanaal van de Marketing, kunt u touchpoint gegevens bekijken om te bepalen welke touchpoints [&#128279;](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md) of [&#x200B; gesegmenteerde &#x200B;](/help/advanced-marketo-measure-features/segmentation/custom-segmentation.md){target="_blank"} moeten worden onderdrukt. Het wordt geadviseerd om uw aanraakpuntgegevens binnen een rapport van &quot;[!DNL Marketo Measure] Personen en Aanraakpunten van de Koper&quot;aan het eind van elke maand of elk kwartaal te controleren als mogelijk. Zo weet u zeker dat uw toewijzing zo nauwkeurig mogelijk is. De &#39;[!DNL Marketo Measure] 101 | Het rapport Leads/Contacts by Channel dat offline beschikbaar is, is een uitstekende plaats om aan de slag te gaan. Neem de volgende velden op als deze nog niet zijn opgenomen om enkele van de meest essentiële onderdelen van de configuratie te controleren:

* **het Marketing Kanaal** - Weg = Marketing Channel.Subchannel (waarden die in [!DNL Marketo Measure] worden geplaatst)
* **Aanraakpunt Source** = utm_source
* **Medium** = utm_medium (online touchpoints) OF het Type van Campagne van CRM (off-line touchpoints)
* **de Pagina van de Verwijzer** (gebruikt de &quot;Online configuratie van Kanalen&quot;)
* **het Bestaan Pagina - Ruwe** (gebruikt de &quot;Online Configuratie van Kanalen&quot;ook een gemeenschappelijke input voor touchpoint onderdrukking op het &quot;lusje van de Montages van het Aanraakpunt&quot;van uw Montages
* **Vorm URL** (een gemeenschappelijke input voor touchpoint onderdrukking op het lusje van de Montages van het Aanraakpunt van uw Montages)

**BUYER ATTRIBUTION TOUCHPOINT (BAT)**

Aanraakpunten voor koperkenmerken (BAT) geven de relevante aanraakpunten aan van alle contactpersonen die zijn verbonden met de opportunity (via Aanspreekrollen voor opportunity of via een id voor een gedeelde account, afhankelijk van uw instellingen). In tegenstelling tot BT (die hoofdzakelijk met mensen verbonden zijn) kan BAT met inkomsten worden geassocieerd. Als dusdanig, zult u BAT gebruiken om vragen met betrekking tot kansen te beantwoorden, hoofdzakelijk open _Kans/de Ontvangsten van de Pijpleiding_ en gesloten gewonnen _Kansen/Overeenkomsten/Ontvangsten_. Er wordt een BAT gemaakt via de BT records van een contactpersoon zodra een Opportunity is gemaakt onder dezelfde account als de contactpersoon (de BT wordt niet omgezet in een BAT. Er wordt gewoon verwezen naar de BT gegevens om een extra record te maken (de BAT die vervolgens betrekking heeft op de Opportunity).

De Buyer Attribution Touchpoint stelt ons in staat om de invloed van marketing in de trechter dieper te meten. _de diepte van de trechter waarbij u wilt meten kan door de diverse multitouch attributiemodellen_ worden vertegenwoordigd.

Aangezien BAT primaire verhouding met de Kans is, worden zij gebruikt om vragen zoals te beantwoorden:

* Welke van mijn marketinginspanningen hebben de meeste kansen beïnvloed?
* Hoeveel nieuwe pijpleidingsopbrengst kan ik aan elk van mijn marketing kanalen toeschrijven?
* Welke van mijn campagnes hebben vorig kwartaal het grootste rendement op investeringen gezien?

De [&#x200B; attributiemodellen &#x200B;](/help/introduction-to-marketo-measure/overview-resources/marketo-measure-attribution-models.md){target="_blank"} die beste inzicht in Op kansen-gebaseerde metriek verstrekken zijn:

**W-Vormde** - het &#39;_Model van de Pijpleiding_&#39;. In het W-Shaped-model zijn drie mijlpalen aanraakpunten opgenomen. In dit model worden de FT-, LC- en OC-aanraakpunten elk toegeschreven aan 30% van het attribuut credit. De resterende 10% wordt in gelijke mate toegeschreven aan alle tussenliggende aanraakpunten tussen de drie mijlpalen.

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

**Volledige Weg** - &quot;_Gesloten Won Model_&quot;. Dit model bevat de vier mijlpalen waarop de aanraakpunten liggen: FT, LC, OC en Closed. Elk krijgt 22,5% van de Opportunity credit en de resterende 10% wordt gelijkelijk verdeeld over de intermediaire toeslagen.

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

**Douane** - [!DNL Marketo Measure] biedt ook een model van de Attributie van de Douane aan dat gebruikers toestaat om te kiezen welke aanraakpunten of douanestadia in hun model te omvatten. Bovendien kunnen gebruikers het toewijzingspercentage bepalen dat aan deze aanraakpunten en fasen wordt toegewezen. Afhankelijk van de opstelling van uw douanemodel, kan het het meest geschikt worden gebruikt om of Kansen en Pijpleiding OF, Overeenkomsten en Gesloten Won Inkomsten te meten. Houd dit in gedachten wanneer u het gebruikt in uw rapportage.

>[!NOTE]
>
>Het aangepaste kenmerkingsmodel is een extra functie die niet voor alle klanten beschikbaar is. Neem contact op met het accountteam van de Adobe (uw accountmanager) voor meer informatie over het toevoegen van deze functie aan uw account.

Marktdeelnemers moeten meestal weten: &quot;Waar komen mijn kansen vandaan?&quot; Net als bij rapportage op hoofdniveau werd deze vraag historisch beantwoord met een enkele, eendimensionale waarde (bijvoorbeeld Primaire campagne-Source). We weten echter dat er veel meer gaat naar de ontwikkeling van een opportunity dan één aanraakpunt van één enkele contactpersoon. Er zijn typisch verscheidene aanraakpunten van diverse kanalen en door veelvoudige belanghebbenden die een Kans in verwezenlijking beïnvloeden. Met [!DNL Marketo Measure] kunnen we alle aanraakpunten van een account bekijken om te begrijpen waar een opportunity vandaan kwam. Daarna kunnen we echter elk aanraakpunt dat zich heeft voorgedaan nadat de Opportunity is gecreëerd en tot op het moment dat de Opportunity is is gesloten, aan de oppervlakte blijven. Op die manier kunnen we niet alleen een multi-touchbenadering gebruiken om te begrijpen waar een opportuniteit vandaan kwam, maar ook wat het heeft beïnvloed om af te sluiten en uiteindelijk een gesloten eigen inkomen te vertegenwoordigen. Dit geeft inzicht in verschillende vragen zoals, &quot;wat beïnvloedt marketing de invloed op het beïnvloeden van Deals om te sluiten?&quot;, &quot;welke marketing drijft gesloten Winst Winst.&quot; en uiteindelijk, &quot;welke van mijn marketing inspanningen zien het grootste ROI?&quot;

## AANBEVOLEN RAPPORTEN MET DE BUYER ATTRIBUTION TOUCHPOINT (BAT) {#recommended-reports-using-the-buyer-attribution-touchpoint}

**4.1 | Nieuwe Kanalen door het Kanaal van de Marketing**

Het samenvatten van uw gegevens van de Buyer Attribution Touchpoint van Kansen door het gebied &quot;het Kanaal van de Marketing&quot;is de hoogste mening die vertegenwoordigt welke kanalen/tactieken nieuwe Kansen in verwezenlijking beïnvloeden. Door dit rapport te structureren rond een &#39;Date Type&#39; = &#39;Opportunity Created Date&#39; zorgt u ervoor dat we ook een overzicht geven van het rapport op basis van wanneer de Opportunity daadwerkelijk is gemaakt in uw CRM. De aanraakpunten kunnen van enige tijd eerder zijn geweest, maar zij zullen nog steeds betrekking hebben op de Kansen die binnen de bepaalde Waaier van de Datum zijn gecreeerd en zo attributietoekening ontvangen aangezien zij worden erkend als beïnvloedend de Kans.

<table> 
 <tbody>
  <tr>
   <td>Vraag</td> 
   <td>Welke <i> marketing kanalen </i> Kansen in verwezenlijking beïnvloeden?</td> 
  </tr>
  <tr>
   <td>Rapporttype</td> 
   <td>Aanraakpunten voor koperkenmerk met mogelijkheden (CRM) <br> 
   Metrisch: mogelijkheden ([!DNL Marketo Measure] ontdekken)</td> 
  </tr>
  <tr>
   <td>Filters</td> 
   <td>
   <li>Opportunity Stage* <i> (optioneel, afhankelijk van de specifieke mogelijkheden die u wilt beperken tot het rapport. U kunt slechts over BAT willen rapporteren die nog aan slechts "Open"Kansen zoals) </i> worden geassocieerd</li>
   <li>Het Type van kans (het is gemeenschappelijk om binnen op bepaalde Kansen te filtreren i.e. "Nieuwe Zaken"in tegenstelling tot <i> alle </i> Kansen)</li><br>
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
   <td><strong> W-Vormd </strong><br>
   SUM de "W-Shaped"gebieden in uw CRM- rapporten (Telling - W-Vormd, Inkomsten - W-Vormd)</td> 
  </tr>
 </tbody>
</table>

>[!TIP]
>
>Voor om het even welk &quot;Aanraakpunten van de Attributie van de Koper met het rapporttype van Opportunity&quot;, begin door het pre-gebouwde rapport aan te passen getiteld &quot;[!DNL Marketo Measure] 101 | Kanaal&quot;. Dit rapport is beschikbaar uit-van-de doos en is een grote zandbak vooraf gebouwd zoals die in de lijst hierboven wordt beschreven en kan snel voor specifiekere rapporteringsbehoeften worden aangepast (het rapport gebruikt een Volledig model van de Weg uit-van-de-doos zodat zeker om het rapport aan te passen om een ander attributiemodel, in dit geval, het model W-Vormd) te omvatten.

>[!TIP]
>
>Het hierboven geschetste verslag zou ook worden gebruikt om te begrijpen hoeveel valuta ook moet worden toegewezen. Wanneer het melden op het niveau van de Kans gebruikend BAT, zijn er twee zeer belangrijke metriek die worden samengevat: munt (het bedrag van de Kans) en het verslag van de Kans zelf. In het bovenstaande voorbeeld meten we meer specifiek open Opportunity en nieuwe pijpleidinginkomsten.

>[!TIP]
>
>Krijg nog meer korrelig inzicht door het rapport samen te vatten met andere beschikbare gebieden van het voorwerp van Buyer Attribution Touchpoint. Dit gebeurt op dezelfde manier als bij Aanraakpunten voor koper (1.2). Doe dit door extra groeperingen (CRM) of dimensies (Discover) toe te voegen. Afhankelijk van het kanaal (dat uw rol kan vertegenwoordigen), kunnen er extra details voorbij het campagneniveau zijn waarin u meer inzicht zoekt. We gaan hieronder naar &#39;Betaalde zoekopdracht&#39;:

<table> 
 <tbody>
  <tr>
   <td>Vraag</td> 
   <td>Welke <i> sleutelwoorden </i> van mijn Betaalde advertenties van het Onderzoek de meeste pijpleidingsopbrengst produceren?
</td> 
  </tr>
  <tr>
   <td>Rapporttype</td> 
   <td>Aanraakpunten voor koperkenmerk met mogelijkheden (CRM) <br> 
   Metrisch: mogelijkheden ([!DNL Marketo Measure] ontdekken)</td> 
  </tr>
  <tr>
   <td>Filters</td> 
   <td>
   <li>Marketingkanaal = Betaalde zoekopdracht</li>
   <li>Opportunity Stage* <i> (optioneel, afhankelijk van de specifieke mogelijkheden die u wilt beperken tot het rapport. Dit voorbeeld is gebaseerd op de Opbrengst van de Pijpleiding die in [!DNL Marketo Measure] door "Open"Kansen wordt bepaald die potentiële opbrengst/open pijpleiding vertegenwoordigen) </i></li>
   <li>Het Type van kans (het is gemeenschappelijk om binnen op bepaalde Kansen te filtreren i.e. "Nieuwe Zaken"in tegenstelling tot <i> alle </i> Kansen)</li><br>
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
   <td>Trefwoordtekst (CRM) <br> 
   Trefwoord (vaststellen)</td> 
  </tr>
  <tr>
   <td>Optimale modellen</td> 
   <td><strong> W-Vormd </strong><br>
   SUM de "W-Shaped"gebieden in uw CRM- rapporten (Telling - W-Vormd, Inkomsten - W-Vormd)</td> 
  </tr>
 </tbody>
</table>

**4.2 | Overeenkomsten door het Kanaal van de Marketing**

Dit rapport zou in wezen het zelfde als het eerste voorbeeld van Buyer Attribution Touchpoint (4.1) zijn behalve metrisch is nu veranderd van open Kansen in gesloten woningen. De metrische waarde moet altijd aangeven welk toewijzingsmodel moet worden gebruikt. Aangezien we nu kijken naar gesloten won Deals en hun verwante BAT, zouden wij een model moeten gebruiken dat de volledige reis van de koper (Overeenkomst) vertegenwoordigt. Hierdoor wordt gegarandeerd dat elke marketingaanraaktrack tijdens de reis van de koper een toeschrijving ontvangt:

<table> 
 <tbody>
  <tr>
   <td>Vraag</td> 
   <td>Welke <i> marketing kanalen </i> beïnvloedt te sluiten Overeenkomsten?</td> 
  </tr>
  <tr>
   <td>Rapporttype</td> 
   <td>Aanraakpunten voor koperkenmerk met mogelijkheden (CRM) <br> 
   Metrisch: overeenkomsten ([!DNL Marketo Measure] ontdekken)</td> 
  </tr>
  <tr>
   <td>Filters</td> 
   <td>
   <li>Het Stadium van de kans (<i> slechts de Gesloten Kansen van het Won zouden in rapport </i>) OF moeten zijn,</li>
   <li>Opportunity Won = True</li>
   <li>Het Type van kans (het is gemeenschappelijk om binnen op bepaalde Kansen te filtreren i.e. "Nieuwe Zaken"in tegenstelling tot alle Kansen) <br>
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
   <td><strong> Volledige Weg </strong><br>
   SUM de "Volledige Weg"gebieden in uw rapporten van CRM (Telling - Volledige Weg, Inkomsten - Volledige Weg)</td> 
  </tr>
 </tbody>
</table>

**HERINNERING**: Het is cruciaal om voor de specifieke Kansen te herinneren u in BAT gebaseerde rapportering wilt omvatten, vooral wanneer het &quot;Open Opportunity en de Ontvangsten van de Pijpleiding&quot;vs. &quot;Overeenkomsten en Gesloten Won Ontvangsten&quot;komt. Dit gebeurt gewoonlijk via een filter &#39;Opportunity Stage&#39; (het filter &#39;Opportunity Won&#39; = true/false kan hier ook erg nuttig zijn).

>[!MORELIKETHIS]
>
>[&#x200B; Nieuwe Discover Gids van het Dashboard &#x200B;](/help/marketo-measure-discover-ui/dashboards/new-discover-dashboard-guide.md){target="_blank"}
