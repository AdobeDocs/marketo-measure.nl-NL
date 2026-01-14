---
description: Richtlijnen voor aanraakpuntvelden voor Marketo Measure-gebruikers
title: Aanraakpuntvelden
exl-id: d6c2bd60-5341-4a52-939a-942afc093306
feature: Touchpoints
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '2122'
ht-degree: 0%

---

# Aanraakpuntvelden {#touchpoint-fields}

In het verleden, wanneer klanten aan boord met [!DNL Marketo Measure] zijn en in het geval dat wij geen directe codering hebben, richt ons team van Klantsucces onze klanten op hoe zij hun landingspagina&#39;s op de juiste manier kunnen labelen zodat zij de juiste UTM-indeling gebruiken en wij hun advertenties kunnen oplossen. Sommige van deze klanten gebruiken geen UTMs maar gebruiken eerder hun eigen etiketterende parameters, wat het zeer tijdrovend kan zijn om al hun landende pagina&#39;s over al hun advertentienetwerken met een nieuwe etiketteringsstructuur uit te geven die [!DNL Marketo Measure] handhaaft. Om zich aan hun het etiketteren structuur aan te passen, aanvaarden wij nu douaneparameters die met onze regeldefinities kunnen worden in kaart gebracht. Het doel is om aan het gebruik van klanten van hun douane het volgen parameters aan te passen zodat moeten wij hen niet vereisen om hun structuur URL te veranderen.

>[!AVAILABILITY]
>
>Beschikbaar nu met volledige segmentering in Tier 2 en Tier 3.

>[!NOTE]
>
>Dit is een geavanceerde functie die alleen door Professional Services moet worden ingesteld.

## De functie inschakelen {#enabling-the-feature}

Navigeer in het menu Instellingen van [!DNL Marketo Measure] naar de pagina Aanraakpuntvelden. Van daar, kunt u de eigenschap toelaten door **ja** te selecteren onder **laat Berekende Gebieden** toe. Nadat de functie is ingeschakeld, kunt u aanraakpuntvelden maken.

![ van het menu van de Montages van Marketo Measure, navigeer aan de Gebieden van het Aanraakpunt ](assets/touchpoint-fields-1.png)

## Procedure {#how-to}

Houd er rekening mee dat een gebruiker drie verschillende handelingen kan uitvoeren om een berekend veld te maken: extraheren, toewijzen en aaneenschakelen. Deze worden ook wel de operatoren voor het definiëren van een berekend veld genoemd.

Extracten

De [!UICONTROL extracts] exploitant trekt de waarde uit een gebied van een andere plaats, zoals: een gebied van de Campagne, het gebied van het Lood, of in een geavanceerder gebruiksgeval, [ trekt douaneparameters van de het landen pagina ](https://docs.google.com/document/d/1NRViyCsXvPKbCTfGW32Yi2vWBjMDRF7bzkzKj9s2DDA/edit?ts=5e20b482#heading=h.xxwtissvw4){target="_blank"}. Het plaatst het dan op een Gebied van het Aanraakpunt (zie [ Kaarten aan Voorbeeld ](https://docs.google.com/document/d/1NRViyCsXvPKbCTfGW32Yi2vWBjMDRF7bzkzKj9s2DDA/edit?ts=5e20b482#heading=h.xxwtissvw4){target="_blank"} #2).

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

![.&amp;42; vertelt ons dat wij het volledige koord ](assets/touchpoint-fields-10.png) halen

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

![ neem nota van dat u een voorwaartse schuine streep en niet a ](assets/touchpoint-fields-11.png) gebruikt

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

![{6} is het aantal tekens dat we extraheren ](assets/touchpoint-fields-12.png)

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

![{6} is het aantal tekens dat we extraheren ](assets/touchpoint-fields-13.png)

**Kaarten aan**

De operator [!UICONTROL maps to] maakt een tabel met waarden die moeten worden omgezet of opgenomen in een andere waarde. Gewoonlijk heeft dit de vorm van een sleutelwaarde waarbij een code een vriendelijke naam vertegenwoordigt en aan die vriendelijke naam moet worden toegewezen.

**Voorbeeld #1**

Er zijn campagnes die je hebt gemaakt voor een &#39;Aanbieding voor einde zomer&#39; en &#39;Aanbieding voor Zwarte Vrijdag&#39; die via meerdere kanalen lopen. U wilt een Berekend Gebied tot stand brengen genoemd &quot;Initiatief&quot;en u wilt om het even welke aanraakpunten met een &quot;Bevordering van het Eind van de zomer&quot;of &quot;Zwarte Vrijdag&quot;aan een waarde van het Initiatief zoals &quot;Bevorderingen,&quot;naast andere mogelijke waarden in kaart brengen.

![ er zijn campagnes die u voor een &quot;Eind van zomerbevordering&quot;hebt gecreeerd ](assets/touchpoint-fields-2.png)

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

![ om 10 te halen, zou u de waarde als &quot;BZ= \ d \ {2 \} - \ d \ {2 \} - \ d \ {2 \} - \ d \ {2 \} - ( \ d \ {2 \}) &quot;](assets/touchpoint-fields-3.png) bepalen

**samenvoegt**

De operator [!UICONTROL concatenates] combineert waarden van meerdere velden tot één veld. Dit is handig om een aangepaste waarde te maken die gegevens in verschillende velden ophaalt om

**Voorbeeld #1**

Er zijn afzonderlijke velden in het object Opportunity voor Segment__c en Grade__c die de gebruiker voor rapportagedoeleinden in één veld op het Touchpoint-object wil combineren. Door de velden samen te voegen, ziet u waarden zoals Enterprise_A of Mid-Market_B.

![ er zijn afzonderlijke gebieden op het voorwerp van de Kanaal voor Segmentc en Gradec ](assets/touchpoint-fields-4.png)

## Aanraakpuntvelden en -segmenten {#touchpoint-fields-and-segments}

Nu de waarden van uw URL zijn geparseerd en aanwezig zijn op het aanraakpunt, ziet u de nieuwe velden op de plaats waar de aanraakpuntvelden worden gebruikt, zoals het maken van segmenten of het definiëren van regels voor het verwijderen van aanraakpunten.

De mogelijkheid om segmenten te maken met aanraakpuntvelden is beschikbaar in deze productrelease. Segmenten konden niet eerder met aanraakpuntvelden worden gemaakt.

![ De capaciteit om Segmenten tot stand te brengen die de gebieden van het Aanraakpunt gebruiken is beschikbaar met dit ](assets/touchpoint-fields-5.png)

Om de bouw van Segmenten gemakkelijker te maken, is het nu mogelijk om dynamische Segmenten van de Gebieden te creëren Touchpoint die werden gecreeerd. Als u bijvoorbeeld een aanraakpuntveld hebt gemaakt dat een geografisch gebied heeft geparseerd in plaats van een segment te maken voor elk mogelijk gebied, kunt u één segment instellen en maken we voor elke instantie een nieuwe waarde. Dit is bijzonder nuttig als een attribuut zoals postcode moest worden ontleed en als segment worden gebruikt!

Uw setup zou er ongeveer als de onderstaande schermafbeelding uitzien. De segmentnaam vult dynamisch de waarde van het aanraakpuntveld met de accolades naar het veld.

![ Uw opstelling zou iets als hieronder het schermschot kijken. De segmentnaam ](assets/touchpoint-fields-6.png)

De regel verwijst naar hetzelfde aanraakpuntveld en zoekt naar waarden die niet gelijk zijn aan null.

![ de regelverwijzingen het zelfde Gebied van het Aanraakpunt en onderzoeken naar waarden die ](assets/touchpoint-fields-7.png)

## Veelgestelde vragen {#faq}

**is er een maximumaantal Gebieden Touchpoint die wij kunnen creëren?**

Er geldt een limiet van 100 velden.

**ik zie mijn nieuw Gebied van het Aanraakpunt niet dat ik enkel in picklist creeerde. Waar is het?**

Vergeet niet uw regels op te slaan nadat u deze hebt gemaakt. Als u het nieuwe veld niet ziet, controleert u of u het hebt opgeslagen. U moet het nieuwe veld opslaan voordat u het kunt gebruiken voor de volgende regel.

>[!NOTE]
>
>Vanwege de complexiteit is een aanraakpuntveld dat de operator &quot;maps to&quot; gebruikt, niet beschikbaar voor gebruik in een ander aanraakpuntveld.

**welke uitdrukking ik gebruik om veelvoudige parameters uit één enkele het landen pagina te halen?**

Net als in Voorbeeld nr. 4 van het Uittreksel, moet u veelvoudige gebieden tot stand brengen om elk van de parameters te halen. Als u vijf verschillende waarden hebt, maakt u vijf aanraakpuntvelden om elk van deze te extraheren.

**waarom ik mijn nieuwe gebieden in het [!DNL Marketo Measure] schema niet zie?**

Er is extra werk nodig om de nieuwe gebieden in het schema van Data Warehouse van [!DNL Marketo Measure] bloot te stellen. Op dit ogenblik, worden de gebieden blootgesteld door montages en configuratie zodat kunt u de Gebieden van het Aanraakpunt in de bouw van Segmenten gebruiken of het creëren van de regels van de Schrapping van het Punt.

**Hoe kan ik bevestigen dat mijn extractie uitdrukking geldig is en de correcte waarde trekt?**

Er is een online hulpmiddel ([[!DNL https]://regex101.com/](https://regex101.com/){target="_blank"}) dat u kunt lopen en uittesten de uitdrukking. De expressie wordt groen weergegeven als deze geldig is of rood als deze ongeldig is. Het vak [!UICONTROL explanation] rechtsboven is bovendien handig en vertelt u wat u wilt extraheren.

![ er is een online hulpmiddel (https://regex101.com/(https://regex101.com/) {target="blank"}) dat u kunt lopen en testen ](assets/touchpoint-fields-8.png)

![ er is een online hulpmiddel (https://regex101.com/(https://regex101.com/) {target="blank"}) dat u kunt lopen en testen ](assets/touchpoint-fields-9.png)
