---
description: Aanraakpuntvelden - [!DNL Marketo Measure]
title: Aanraakpuntvelden
exl-id: d6c2bd60-5341-4a52-939a-942afc093306
feature: Touchpoints
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '2068'
ht-degree: 0%

---


# Aanraakpuntvelden {#touchpoint-fields}

In het verleden, wanneer klanten aan boord met [!DNL Marketo Measure] zijn en in het geval dat wij geen directe codering hebben, richt ons team van Klantsucces onze klanten op hoe zij hun landingspagina&#39;s op de juiste manier kunnen labelen zodat zij de juiste UTM-indeling gebruiken en wij hun advertenties kunnen oplossen. Sommige van deze klanten gebruiken geen UTMs maar gebruiken eerder hun eigen etiketterende parameters, wat het zeer tijdrovend kan zijn om al hun landende pagina&#39;s over al hun advertentienetwerken met een nieuwe etiketteringsstructuur uit te geven die [!DNL Marketo Measure] handhaaft. Om zich aan hun het etiketteren structuur aan te passen, aanvaarden wij nu douaneparameters die met onze regeldefinities kunnen worden in kaart gebracht. Het doel is om aan het gebruik van klanten van hun douane het volgen parameters aan te passen zodat moeten wij hen niet vereisen om hun structuur URL te veranderen.

>[!AVAILABILITY]
>Beschikbaar nu met volledige segmentering in Tier 2 en Tier 3.
>
>Beschikbaar met volledige segmentering in Tier 2-abonnementen.

>[!NOTE]
>Dit is een geavanceerde functie die alleen door Professional Services moet worden ingesteld.

## De functie inschakelen {#enabling-the-feature}

Navigeer in het menu Instellingen van [!DNL Marketo Measure] naar de pagina Aanraakpuntvelden. Van daar, kunt u de eigenschap toelaten door **ja** te selecteren onder **laat Berekende Gebieden** toe. Nadat de functie is ingeschakeld, kunt u aanraakpuntvelden maken.

![&#x200B; de montagespagina van de Gebieden van het Aanraakpunt met toelaat de Berekende optie van Gebieden &#x200B;](assets/one.png)

## Procedure {#how-to}

Houd er rekening mee dat een gebruiker drie verschillende handelingen kan uitvoeren om een berekend veld te maken: extraheren, toewijzen en aaneenschakelen. Deze worden ook wel de operatoren voor het definiëren van een berekend veld genoemd.

### Extracten {#extracts}

De operator [!UICONTROL extracts] haalt de waarde uit een veld van een andere locatie, zoals: een Campagneveld, Lead-veld of, in een geavanceerder gebruiksgeval, aangepaste parameters uit de bestemmingspagina. Vervolgens wordt het op een aanraakpuntveld geplaatst.

**Voorbeeld #1**

Er is een douanegebied op het Contact, campagne_source__c, dat de klant op het Aanraakpunt voor rapporteringsdoeleinden wenst te laten vallen. U kunt een regel definiëren om een berekend veld met de naam ‘Campagne Source’ te maken en de waarde in dat veld neer te zetten.

Doel: gebruik de waarde van een aangepast veld en plaats dit in het Touchpoint-object om de melding eenvoudiger te maken.

* Een berekend veld maken en het label ‘Campagne Source’ geven
* Bepaal de regel door uit te beginnen met het zoeken naar het gebied Contact.Campaign_Source__c
* Gebruik de operator &quot;extracts&quot; omdat we de waarde uit de parameter moeten halen
* Om het volledige koord van het gebied te halen, zullen wij de uitdrukking &quot; (.&#42;)&quot; gebruiken

   * **(** merkt het begin van de extractie
   * **)** merkt het eind van de extractie
   * **.&#42;** vertelt ons dat we de volledige tekenreeks extraheren

![&#x200B; Berekende configuratie van het Gebied voor het gebiedsextractie van Source van de Campagne &#x200B;](assets/two.png)

**Voorbeeld #2**

Een veel voorkomend geval waarin deze functie wordt ingeschakeld, is het uittrekken van waarden uit aangepaste parameters van een URL-tekenreeks. Dit is handig als u andere parameters gebruikt dan UTM&#39;s, maar de waarden wilt parseren op aanraakpuntvelden.

**Verbinding:** `https://www.adobe.com/blog/marketing-revenue-reporting-overview?promo=5OFF` of `https://www.adobe.com/blog/marketing-revenue-reporting-overview?promo=25OFF`.\
**Doel:** creeer een douanegebied genoemd &quot;Code van de Korting&quot;en daling in de waarde &quot;5OFF&quot;of &quot;25OFF,&quot;welke waarde wordt overgegaan.

* Een berekend veld maken en dit veld het label &quot;Discount Code&quot; geven
* Definieer de regel door te beginnen met zoeken naar het veld Touchpoint.Session.LandingPage
* Gebruik de operator &quot;extracts&quot; omdat we de waarde uit de parameter moeten halen
* Als u de waarde van de promotie wilt extraheren, definiëren we de waarde als &quot;promo=(\w+)&quot;

   * **(** merkt het begin van de extractie
   * **)** merkt het eind van de extractie
   * **\w** vertelt ons dat wij een &quot;woord&quot;halen dat 0-9 omvat
   * **+** extraheert de volledige waarde van de parameter zonder limiet voor tekens
   * Let op: u gebruikt een slash in plaats van een slash

![&#x200B; het gebiedsconfiguratie die van de Code van de Korting promo parameter uit URL haalt &#x200B;](assets/three.png)

**Voorbeeld #3**

Laten we een vergelijkbaar voorbeeld proberen waarbij we een trackingcode extraheren, zoals: `https://www.adobe.com/blog/marketing-revenue-reporting-overview?cid=123456` .

**Doel:** creeer een Berekend Gebied en etiketteer het &quot;Identiteitskaart van Adobe Campaign&quot;met de waarde van de cid parameter.

* Een berekend veld maken en het label Adobe Campaign-id geven
* Definieer de regel door te beginnen met zoeken naar het veld Touchpoint.Session.LandingPage
* Gebruik de operator &quot;extracts&quot; omdat we de waarde uit de parameter moeten halen
* Als u de waarde &quot;123456&quot; wilt extraheren, definiëren we de waarde als &quot;cid=(\d{6})&quot;

   * **(** merkt het begin van de extractie
   * **)** merkt het eind van de extractie
   * **\ d** vertelt ons dat wij een &quot;cijfer&quot;halen
   * **{6}** is het aantal karakters wij extraheren

![&#x200B; het gebied van identiteitskaart van Adobe Campaign die 6-cijferig cid parameter haalt &#x200B;](assets/four.png)

**Voorbeeld #4**

Aangezien uw landingspagina&#39;s ingewikkelder worden en u veelvoudige het volgen parameters hebt, zou u veelvoudige touchpoint gebieden kunnen moeten bouwen en waarden veelvoudige tijden, zoals halen:
`https://www.adobe.com/blog/marketing-revenue-reporting-overview?trackID=123456&country=US&campaign_ID=7890`.

**Doel:** creeer veelvoudige Berekende Gebieden voor &quot;Land van het Doel&quot;en &quot;Identiteitskaart van de Campagne van de Douane&quot;met de respectieve waarden van de parameters.

* Een berekend veld maken en het label ‘Doelland’ geven
* Definieer de regel door te beginnen met zoeken naar het veld Touchpoint.Session.LandingPage
* Gebruik de operator &quot;extracts&quot; omdat we de waarde uit de parameter moeten halen
* Als u de waarde &quot;US&quot; wilt extraheren, definieert u de waarde als &quot;country=(\w{2})&quot;

   * **(** merkt het begin van de extractie
   * **)** merkt het eind van de extractie
   * **\w** vertelt ons dat wij een &quot;woord&quot; halen
   * **\{2 \}** is het aantal karakters wij extraheren

* Een berekend veld maken en dit veld het label &quot;Aangepaste campagne-id&quot; geven
* Definieer de regel door te beginnen met zoeken naar het veld Touchpoint.Session.LandingPage
* Gebruik de operator &quot;extracts&quot; omdat we de waarde uit de parameter moeten halen
* Als u de waarde 123456 wilt extraheren, definiëren we de waarde als &quot;campagne_ID=(\d{6})&quot;

   * **(** merkt het begin van de extractie
   * **)** merkt het eind van de extractie
   * **\ d** vertelt ons dat wij een &quot;cijfer&quot;halen
   * **{6}** is het aantal karakters wij extraheren

![&#x200B; Veelvoudige berekende gebieden die land en campagneID parameters &#x200B;](assets/five.png) halen

### Kaarten aan {#maps-to}

De operator [!UICONTROL maps to] maakt een tabel met waarden die moeten worden omgezet of opgenomen in een andere waarde. Gewoonlijk heeft dit de vorm van een sleutelwaarde waarbij een code een vriendelijke naam vertegenwoordigt en aan die vriendelijke naam moet worden toegewezen.

**Voorbeeld #1**

Er zijn campagnes die je hebt gemaakt voor een &#39;Aanbieding voor einde zomer&#39; en &#39;Aanbieding voor Zwarte Vrijdag&#39; die via meerdere kanalen lopen. U wilt een Berekend Gebied tot stand brengen genoemd &quot;Initiatief&quot;en u wilt om het even welke aanraakpunten met een &quot;Bevordering van het Eind van de zomer&quot;of &quot;Zwarte Vrijdag&quot;aan een waarde van het Initiatief zoals &quot;Bevorderingen,&quot;naast andere mogelijke waarden in kaart brengen.

![&#x200B; het gebied van het Initiatief in kaart brengende campagnes aan promotiecategorieën &#x200B;](assets/six.png)

**Voorbeeld #2**

Nu we hebben geleerd hoe we die acties kunnen extraheren en toewijzen aan velden, combineren we ze om eerst een waarde uit een parameter te extraheren, en dan toewijzen we ze aan een vriendelijke naam die wat meer zin heeft. Laten we dus beginnen met de landingspagina: `https://www.adobe.com/blog/marketing-revenue-reporting-overview?BZ=04-01-09-03-10` .

**Doel:** creeer veelvoudige Berekende Gebieden, waar het eerste aantal kaarten aan een Gebied, de tweede kaarten aan een Product, de derde kaarten aan een Initiatief, de vierde kaarten aan een Persoon, en de vijfde kaarten aan een Platform van Media. Wijs vervolgens de numerieke waarde toe aan een &quot;vriendelijke naam&quot;.

* Een berekend veld maken en dit veld het label Regio geven
* Definieer de regel door te beginnen met zoeken naar het veld Touchpoint.Session.LandingPage
* Gebruik de exploitant &quot;[!UICONTROL extracts]&quot;aangezien wij de waarde uit de parameter moeten trekken
* Als u de waarde &quot;04&quot; wilt extraheren, definiëren we de waarde als &quot;BZ=(\d{2})-\d{2}-\d{2}-\d{2}-\d{2}&quot;

   * **(** merkt het begin van de extractie

      * Let op: aangezien we alleen de 4 cijfers extraheren, hebben alleen de eerste cijfers het haakje openen
   * **)** merkt het eind van de extractie

      * Let op: aangezien we alleen de 4 extraheren, hebben alleen de eerste cijfers het haakje gesloten
   * **\ d** vertelt ons dat wij een &quot;cijfer&quot;halen
   * **\{2 \}** is het aantal karakters wij extraheren

* Klik op [!UICONTROL Save]. U moet het nieuwe veld opslaan voordat het beschikbaar is voor de volgende regel.
* Vervolgens willen we alle mogelijke waarden voor de eerste cijfers toewijzen aan de vriendelijke namen
* Een berekend veld maken en dit veld het label Regio_Naam geven
* Bepaal de regel door uit te beginnen met het zoeken naar uw geëxtraheerde veld. In dit geval, [!DNL Touchpoint.Region]
* Gebruik de exploitant &quot;[!UICONTROL maps to]&quot;aangezien wij een afbeelding voor elk aantal aan zijn waarde willen tot stand brengen
* U krijgt een tabel te zien waarin elke toewijzing wordt vermeld. Uiteindelijk zal het er ongeveer als volgt uitzien:
* Op basis van de toewijzing en de bovenstaande URL zou &quot;Region_Value&quot; voor een aanraakpunt met deze landingspagina &quot;EMEA&quot; zijn
* Herhaal de extractie en de toewijzing voor de resterende vier cijfersets

   * Als u 01 wilt extraheren, definieert u de waarde als &quot;BZ=\d{2}-**(\d{2})**-\d{2}-\d{2}-\d{2}&quot;
   * Als u 09 wilt extraheren, definieert u de waarde als &quot;BZ=\d{2}-\d{2}-**(\d{2})**-\d{2}-\d{2}&quot;
   * Als u 03 wilt extraheren, definieert u de waarde als &quot;BZ=\d{2}-\d{2}-\d{2}-**(\d{2})**-\d{2}&quot;
   * Als u de 10-waarde wilt extraheren, definieert u deze als &quot;BZ=\d{2}-\d{2}-\d{2}-\d{2}-**(\d{2})**&quot;

![&#x200B; de toewijzingstabel van de Naam van het Gebied met numerieke codes aan gebiedsnamen &#x200B;](assets/seven.png)

### Concatenaten {#concatenates}

De operator [!UICONTROL concatenates] combineert waarden van meerdere velden tot één veld. Dit is handig om een aangepaste waarde te maken die gegevens in verschillende velden ophaalt om

**Voorbeeld #1**

Er zijn afzonderlijke velden in het object Opportunity voor Segment__c en Grade__c die de gebruiker voor rapportagedoeleinden in één veld op het Touchpoint-object wil combineren. Door de velden samen te voegen, ziet u waarden zoals Enterprise_A of Mid-Market_B.

![&#x200B; samenvoegen configuratie die de gebieden van het Segment en van de Grade combineert &#x200B;](assets/eight.png)

## Aanraakpuntvelden en -segmenten {#touchpoint-fields-and-segments}

Nu de waarden van uw URL zijn geparseerd en aanwezig zijn op het aanraakpunt, ziet u de nieuwe velden op de plaats waar de aanraakpuntvelden worden gebruikt, zoals het maken van segmenten of het definiëren van regels voor het verwijderen van aanraakpunten.

De mogelijkheid om segmenten te maken met aanraakpuntvelden is beschikbaar in deze productrelease. Segmenten konden niet eerder met aanraakpuntvelden worden gemaakt.

![&#x200B; de aanmaakinterface die van het Segment beschikbare touchpoint gebieden toont &#x200B;](assets/nine.png)

Om de bouw van Segmenten gemakkelijker te maken, is het nu mogelijk om dynamische Segmenten van de Gebieden te creëren Touchpoint die werden gecreeerd. Als u bijvoorbeeld een aanraakpuntveld hebt gemaakt dat een geografisch gebied heeft geparseerd in plaats van een segment te maken voor elk mogelijk gebied, kunt u één segment instellen en maken we voor elke instantie een nieuwe waarde. Dit is bijzonder nuttig als een attribuut zoals postcode moest worden ontleed en als segment worden gebruikt!

Uw setup zou er ongeveer als de onderstaande schermafbeelding uitzien. De segmentnaam vult dynamisch de waarde van het aanraakpuntveld met de accolades naar het veld.

![&#x200B; Dynamische segmentconfiguratie met de krullende verwijzing van het steungebied &#x200B;](assets/ten.png)

De regel verwijst naar hetzelfde aanraakpuntveld en zoekt naar waarden die niet gelijk zijn aan null.

![&#x200B; regel van het Segment met niet gelijk aan ongeldige voorwaarde &#x200B;](assets/eleven.png)

## Veelgestelde vragen {#faq}

**is er een maximumaantal Gebieden Touchpoint die wij kunnen creëren?**

Er geldt een limiet van 100 velden.

**ik zie mijn nieuw Gebied van het Aanraakpunt niet dat ik enkel in picklist creeerde. Waar is het?**

Vergeet niet uw regels op te slaan nadat u deze hebt gemaakt. Als u het nieuwe veld niet ziet, controleert u of u het hebt opgeslagen. U moet het nieuwe veld opslaan voordat u het kunt gebruiken voor de volgende regel.

>[!NOTE]
>Vanwege de complexiteit is een aanraakpuntveld dat de operator &quot;maps to&quot; gebruikt, niet beschikbaar voor gebruik in een ander aanraakpuntveld.

**welke uitdrukking ik gebruik om veelvoudige parameters uit één enkele het landen pagina te halen?**

Net als in Voorbeeld nr. 4 van het Uittreksel, moet u veelvoudige gebieden tot stand brengen om elk van de parameters te halen. Als u vijf verschillende waarden hebt, maakt u vijf aanraakpuntvelden om elk van deze te extraheren.

**waarom ik mijn nieuwe gebieden in het [!DNL Marketo Measure] schema niet zie?**

Er is extra werk nodig om de nieuwe gebieden in het schema van Data Warehouse van [!DNL Marketo Measure] bloot te stellen. Op dit ogenblik, worden de gebieden blootgesteld door montages en configuratie zodat kunt u de Gebieden van het Aanraakpunt in de bouw van Segmenten gebruiken of het creëren van de regels van de Schrapping van het Punt.

**Hoe kan ik bevestigen dat mijn extractie uitdrukking geldig is en de correcte waarde trekt?**

Er is een online hulpmiddel ([[!DNL https]://regex101.com/](https://regex101.com/){target="_blank"}) dat u kunt lopen en uittesten de uitdrukking. De expressie wordt groen weergegeven als deze geldig is of rood als deze ongeldig is. Het vak [!UICONTROL explanation] rechtsboven is bovendien handig en vertelt u wat u wilt extraheren.

![&#x200B; Regex bevestigingshulpmiddel dat geldige uitdrukking in groen toont &#x200B;](assets/twelve.png)

![&#x200B; Regex bevestigingshulpmiddel dat ongeldige uitdrukking in rood toont &#x200B;](assets/thirteen.png)
