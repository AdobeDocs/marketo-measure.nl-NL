---
unique-page-id: 37355835
description: Aanraakpuntvelden - [!DNL Marketo Measure] - Productdocumentatie
title: Aanraakpuntvelden
exl-id: d6c2bd60-5341-4a52-939a-942afc093306
feature: Touchpoints
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '1942'
ht-degree: 0%

---

# Aanraakpuntvelden {#touchpoint-fields}

Historisch, wanneer klanten aan boord met [!DNL Marketo Measure] en in het geval dat we geen directe codering hebben, leidt ons team van Klantsucces onze klanten op de hoogte van de manier waarop ze hun landingspagina&#39;s op de juiste manier kunnen labelen, zodat ze de juiste UTM-indeling gebruiken en we hun advertenties kunnen oplossen. Sommige van deze klanten gebruiken geen UTMs maar eerder gebruiken hun eigen het etiketteren parameters, wat het zeer tijdrovend kan betekenen om al hun landingspagina&#39;s over al hun advertentienetwerken met een nieuwe etiketteringsstructuur uit te geven die [!DNL Marketo Measure] handhaven. Om zich aan hun het etiketteren structuur aan te passen, aanvaarden wij nu douaneparameters die met onze regeldefinities kunnen worden in kaart gebracht. Het doel is om aan het gebruik van klanten van hun douane het volgen parameters aan te passen zodat moeten wij hen niet vereisen om hun structuur URL te veranderen.

>[!AVAILABILITY]
>
>Beschikbaar nu met volledige segmentering in Tier 2 en Tier 3.

>[!NOTE]
>
>Dit is een geavanceerde functie die alleen door Professional Services moet worden ingesteld.

## De functie inschakelen {#enabling-the-feature}

Van de [!DNL Marketo Measure] Ga in het menu Instellingen naar de pagina Touchpoint Fields. Van daar kunt u de eigenschap toelaten door te selecteren **Ja** krachtens **Berekende velden inschakelen**. Zodra dat wordt toegelaten, kunt u aanraakpuntGebieden creëren.

![](assets/one.png)

## Procedure {#how-to}

Houd er rekening mee dat een gebruiker drie verschillende handelingen kan uitvoeren om een berekend veld te maken: extraheren, toewijzen en aaneenschakelen. Deze worden ook wel de operatoren voor het definiëren van een berekend veld genoemd.

Extracten

De extractoperator haalt de waarde uit een veld van een andere locatie, zoals: een Campagneveld, Lead-veld of in een geavanceerder gebruiksgeval, [aangepaste parameters ophalen van de bestemmingspagina](https://docs.google.com/document/d/1NRViyCsXvPKbCTfGW32Yi2vWBjMDRF7bzkzKj9s2DDA/edit?ts=5e20b482#heading=h.xxwtissvw4){target="_blank"}. It then places it onto a Touchpoint Field (See [Maps To Example](https://docs.google.com/document/d/1NRViyCsXvPKbCTfGW32Yi2vWBjMDRF7bzkzKj9s2DDA/edit?ts=5e20b482#heading=h.xxwtissvw4){target="_blank"} #2).

**Voorbeeld 1**

Er is een douanegebied op het Contact, campagne_source__c, dat de klant op het Aanraakpunt voor rapporteringsdoeleinden wenst te laten vallen. U kunt een regel definiëren om een Berekend veld met de naam &quot;Campagnebron&quot; te maken en de waarde in dat veld neer te zetten.

Doel: gebruik de waarde van een aangepast veld en plaats dit in het Touchpoint-object om de melding eenvoudiger te maken.

* Een berekend veld maken en dit veld het label Campagnebron geven
* Bepaal de regel door uit te beginnen met het zoeken naar het gebied Contact.Campaign_Source__c
* Gebruik de operator &quot;extracts&quot; omdat we de waarde uit de parameter moeten halen
* Als u de volledige tekenreeks uit het veld wilt extraheren, gebruiken we de expressie &quot;(.&#42;)&quot;

   * **(** markeert het begin van de extractie
   * **)** markeert het einde van de extractie
   * **.&#42;** vertelt ons dat we de volledige tekenreeks extraheren

![](assets/two.png)

**Voorbeeld 2**

Een veel voorkomend geval waarin deze functie wordt ingeschakeld, is het uittrekken van waarden uit aangepaste parameters van een URL-tekenreeks. Dit is handig als u andere parameters gebruikt dan UTM&#39;s, maar de waarden wilt parseren op aanraakpuntvelden.

**Koppeling:** `https://www.adobe.com/blog/marketing-revenue-reporting-overview?promo=5OFF` of `https://www.adobe.com/blog/marketing-revenue-reporting-overview?promo=25OFF`.\
**Doel:** Maak een aangepast veld met de naam &quot;Discount Code&quot; en zet de waarde &quot;5OFF&quot; of &quot;25OFF&quot; neer, ongeacht de waarde die wordt doorgegeven.

* Een berekend veld maken en dit veld het label &quot;Discount Code&quot; geven
* Definieer de regel door te beginnen met zoeken naar het veld Touchpoint.Session.LandingPage
* Gebruik de operator &quot;extracts&quot; omdat we de waarde uit de parameter moeten halen
* Als u de waarde van de promotie wilt extraheren, definiëren we de waarde als &quot;promo=(\w+)&quot;

   * **(** markeert het begin van de extractie
   * **)** markeert het einde van de extractie
   * **\w** vertelt ons dat we een &quot;woord&quot; halen dat 0-9 omvat
   * **+** haalt de volledige waarde van de parameter zonder limiet op tekens uit
   * Let op: je gebruikt een slash in plaats van een slash

![](assets/three.png)

**Voorbeeld 3**

Laten we een vergelijkbaar voorbeeld proberen waarbij we een trackingcode extraheren, zoals: `https://www.adobe.com/blog/marketing-revenue-reporting-overview?cid=123456`.

**Doel:** Maak een berekend veld en geef dit veld de naam Adobe Campaign-id met de waarde van de parameter cid.

* Een berekend veld maken en het label Adobe Campaign-id geven
* Definieer de regel door te beginnen met zoeken naar het veld Touchpoint.Session.LandingPage
* Gebruik de operator &quot;extracts&quot; omdat we de waarde uit de parameter moeten halen
* Als u de waarde &quot;123456&quot; wilt extraheren, definiëren we de waarde als &quot;cid=(\d{6})&quot;

   * **(** markeert het begin van de extractie
   * **)** markeert het einde van de extractie
   * **\d** vertelt ons dat wij een &quot;cijfer&quot;halen
   * **{6}** is het aantal tekens dat we extraheren

![](assets/four.png)

**Voorbeeld 4**

Aangezien uw landingspagina&#39;s ingewikkelder worden en u veelvoudige het volgen parameters hebt, zou u veelvoudige touchpoint gebieden kunnen moeten bouwen en waarden veelvoudige tijden, zoals halen:
`https://www.adobe.com/blog/marketing-revenue-reporting-overview?trackID=123456&country=US&campaign_ID=7890`.

**Doel:** Maak meerdere berekende velden voor &quot;Doelland&quot; en &quot;Aangepaste campagne-id&quot; met de respectieve waarden van de parameters.

* Een berekend veld maken en het label ‘Doelland’ geven
* Definieer de regel door te beginnen met zoeken naar het veld Touchpoint.Session.LandingPage
* Gebruik de operator &quot;extracts&quot; omdat we de waarde uit de parameter moeten halen
* Als u de waarde &quot;US&quot; wilt extraheren, definieert u de waarde als &quot;country=(\w{2})&quot;

   * **(** markeert het begin van de extractie
   * **)** markeert het einde van de extractie
   * **\w** vertelt ons dat we een &quot;woord&quot; halen
   * **{2}** is het aantal tekens dat we extraheren

* Een berekend veld maken en dit veld het label &quot;Aangepaste campagne-id&quot; geven
* Definieer de regel door te beginnen met zoeken naar het veld Touchpoint.Session.LandingPage
* Gebruik de operator &quot;extracts&quot; omdat we de waarde uit de parameter moeten halen
* Als u de waarde 123456 wilt extraheren, definiëren we de waarde als &quot;campagne_ID=(\d{6})&quot;

   * **(** markeert het begin van de extractie
   * **)** markeert het einde van de extractie
   * **\d** vertelt ons dat wij een &quot;cijfer&quot;halen
   * **{6}** is het aantal tekens dat we extraheren

![](assets/five.png)

**Kaarten aan**

De kaarten aan exploitant leiden tot een lijst van waarden die in een andere waarde moeten worden vertaald of worden verpakt. Gewoonlijk heeft dit de vorm van een sleutelwaarde waarbij een code een vriendelijke naam vertegenwoordigt en aan die vriendelijke naam moet worden toegewezen.

**Voorbeeld 1**

Er zijn campagnes die je hebt gemaakt voor een &#39;Aanbieding voor einde zomer&#39; en &#39;Aanbieding voor Zwarte Vrijdag&#39; die via meerdere kanalen lopen. U wilt een Berekend Gebied tot stand brengen genoemd &quot;Initiatief&quot;en u wilt om het even welke aanraakpunten met een &quot;Bevordering van het Eind van de zomer&quot;of &quot;Zwarte Vrijdag&quot;aan een waarde van het Initiatief zoals &quot;Bevorderingen,&quot;naast andere mogelijke waarden in kaart brengen.

![](assets/six.png)

**Voorbeeld 2**

Nu we hebben geleerd hoe we die acties kunnen extraheren en toewijzen aan velden, combineren we ze om eerst een waarde uit een parameter te extraheren, en dan toewijzen we ze aan een vriendelijke naam die wat meer zin heeft. Laten we dus beginnen met deze landingspagina: `https://www.adobe.com/blog/marketing-revenue-reporting-overview?BZ=04-01-09-03-10`.

**Doel:** Maak meerdere Berekende velden, waarbij het eerste getal wordt toegewezen aan een regio, het tweede aan een product, het derde aan een initiatief, het vierde aan een persoon en het vijfde aan een Media-Platform. Wijs vervolgens de numerieke waarde toe aan een &quot;vriendelijke naam&quot;.

* Een berekend veld maken en dit veld het label Regio geven
* Definieer de regel door te beginnen met zoeken naar het veld Touchpoint.Session.LandingPage
* De operator &quot;[!UICONTROL extracts]&quot; omdat we de waarde uit de parameter moeten halen
* Als u de waarde &quot;04&quot; wilt extraheren, definiëren we de waarde als &quot;BZ=(\d{2})-\d{2}-\d{2}-\d{2}-\d{2}&quot;

   * **(** markeert het begin van de extractie

      * Let op: aangezien we alleen de 4 cijfers extraheren, hebben alleen de eerste cijfers het haakje openen

   * **)** markeert het einde van de extractie

      * Let op: aangezien we alleen de 4 extraheren, hebben alleen de eerste cijfers het haakje gesloten

   * **\d** vertelt ons dat wij een &quot;cijfer&quot;halen
   * **{2}** is het aantal tekens dat we extraheren

* Klik op [!UICONTROL Save]. U moet het nieuwe veld opslaan voordat het beschikbaar is voor de volgende regel.
* Vervolgens willen we alle mogelijke waarden voor de eerste cijfers toewijzen aan de vriendelijke namen
* Een berekend veld maken en dit veld het label Regio_Naam geven
* Bepaal de regel door uit te beginnen met het zoeken naar uw geëxtraheerde veld. In dit geval, Touchpoint.Region
* De operator &quot;[!UICONTROL maps to]&quot; omdat wij een afbeelding voor elk aantal aan zijn waarde willen creëren
* U zult met een lijst worden voorgesteld om van elke afbeelding een lijst te maken. Uiteindelijk zal het er ongeveer als volgt uitzien:
* Op basis van de toewijzing en de bovenstaande URL zou &quot;Region_Value&quot; voor een aanraakpunt met deze landingspagina &quot;EMEA&quot; zijn
* Herhaal de extractie en de toewijzing voor de resterende vier cijfersets

   * Als u 01 wilt extraheren, definieert u de waarde als &quot;BZ=\d{2}-**(\d{2})**-\d{2}-\d{2}-\d{2}&quot;
   * Als u 09 wilt extraheren, definieert u de waarde als &quot;BZ=\d{2}-\d{2}-**(\d{2})**-\d{2}-\d{2}&quot;
   * Als u 03 wilt extraheren, definieert u de waarde als &quot;BZ=\d{2}-\d{2}-\d{2}-**(\d{2})**-\d{2}&quot;
   * Als u de 10 wilt extraheren, definieert u de waarde als &quot;BZ=\d{2}-\d{2}-\d{2}-\d{2}-**(\d{2})**&quot;

![](assets/seven.png)

**Concatenaten**

De operator concatenates combineert waarden van meerdere velden tot één veld. Dit is handig om een aangepaste waarde te maken die gegevens in verschillende velden ophaalt om

**Voorbeeld 1**

Er zijn afzonderlijke velden in het object Opportunity voor Segment__c en Grade__c die de gebruiker voor rapportagedoeleinden in één veld op het Touchpoint-object wil combineren. Door de velden samen te voegen, ziet u waarden zoals Enterprise_A of Mid-Market_B.

![](assets/eight.png)

## Aanraakpuntvelden en -segmenten {#touchpoint-fields-and-segments}

Nu de waarden van uw URL zijn geparseerd en aanwezig zijn op het aanraakpunt, ziet u de nieuwe velden op de plaats waar de aanraakpuntvelden worden gebruikt, zoals het maken van segmenten of het definiëren van regels voor het verwijderen van aanraakpunten.

De mogelijkheid om segmenten te maken met aanraakpuntvelden is beschikbaar in deze productrelease. Segmenten konden niet eerder met aanraakpuntvelden worden gemaakt.

![](assets/nine.png)

Om de bouw van Segmenten gemakkelijker te maken, is het nu mogelijk om dynamische Segmenten van de Gebieden te creëren Touchpoint die werden gecreeerd. Als u bijvoorbeeld een aanraakpuntveld hebt gemaakt dat een geografisch gebied heeft geparseerd in plaats van een segment te maken voor elk mogelijk gebied, kunt u één segment instellen en maken we voor elke instantie een nieuwe waarde. Dit is bijzonder nuttig als een attribuut zoals postcode moest worden ontleed en als segment worden gebruikt!

Uw setup zou er ongeveer als de onderstaande schermafbeelding uitzien. De segmentnaam vult dynamisch de waarde van het aanraakpuntveld met de accolades naar het veld.

![](assets/ten.png)

De regel verwijst naar hetzelfde aanraakpuntveld en zoekt naar waarden die niet gelijk zijn aan null.

![](assets/eleven.png)

## Veelgestelde vragen {#faq}

**Is er een maximum aantal aanraakpuntvelden dat we kunnen maken?**

Er geldt een limiet van 100 velden.

**Ik zie mijn nieuwe aanraakpuntveld dat ik net in de keuzelijst heb gemaakt, niet. Waar is het?**

Vergeet niet uw regels op te slaan nadat u deze hebt gemaakt. Als u het nieuwe veld niet ziet, controleert u of u het hebt opgeslagen. U moet het nieuwe veld opslaan voordat u het kunt gebruiken voor de volgende regel.

>[!NOTE]
>
>Vanwege de complexiteit is een aanraakpuntveld dat de operator &quot;maps to&quot; gebruikt, niet beschikbaar voor gebruik in een ander aanraakpuntveld.

**Welke uitdrukking gebruikt ik om veelvoudige parameters uit één enkele landingspagina te halen?**

Net als in Voorbeeld nr. 4 van het Uittreksel, zult u veelvoudige gebieden moeten tot stand brengen om elk van de parameters te halen. Als u vijf verschillende waarden hebt, maakt u vijf aanraakpuntvelden om elk van deze te extraheren.

**Waarom zie ik mijn nieuwe velden niet in de [!DNL Marketo Measure] schema?**

Er is extra werk nodig om de nieuwe velden in de [!DNL Marketo Measure] Schema Data Warehouse. Op dit ogenblik, worden de gebieden blootgesteld door montages en configuratie zodat kunt u de Gebieden van het Aanraakpunt in de bouw van Segmenten gebruiken of het creëren van de regels van de Schrapping van het Punt.

**Hoe kan ik valideren dat mijn extractie-expressie geldig is en de juiste waarde ophalen?**

Er is een online hulpmiddel ([https://regex101.com/](https://regex101.com/){target="_blank"}) die u kunt uitvoeren en uittesten. De expressie wordt groen weergegeven als deze geldig is of rood als deze ongeldig is. Ook, is de verklaringsdoos bij het hoogste recht nuttig en vertelt u wat u uithaalt.

![](assets/twelve.png)

![](assets/thirteen.png)
