---
unique-page-id: 18874596
description: Online aangepaste kanaalinstelling - [!DNL Marketo Measure] - Productdocumentatie
title: Online aangepaste kanaalinstelling
exl-id: 170ac564-6cdd-4036-abf0-b9b230bed4f7
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '1230'
ht-degree: 0%

---

# Online aangepaste kanaalinstelling {#online-custom-channel-setup}

Voor een juiste rapportage moeten de afzetkanalen zodanig zijn ingesteld dat ze de UTM-strategie van uw organisatie weerspiegelen. Deze gids zal u door de beste manier nemen om uw regels van het douanekanaal te vormen.

## Voordat u begint {#before-you-begin}

Voordat u begint met het maken van de kanaalregels voor [!DNL Marketo Measure], neemt u de tijd om na te denken over de organisatie van uw marketingcampagnes en hoe deze passen in de [!DNL Marketo Measure] kader. U moet bepalen welke kanalen, subkanalen, campagnes en websites u wilt bijhouden.

Denk aan de volgende zaken:

* Uw organisatie kan maximaal 40 aangepaste marketingkanalen maken. Dit geldt zowel voor offline als online kanalen.
* Uw organisatie kan tot 200 subkanalen tot stand brengen.
* Elke inzameling, of emmer, van gegevens heeft zijn eigen regel (rij in spreadsheet) nodig om te specificeren hoe de gegevens zullen worden georganiseerd. Wees zo specifiek mogelijk.
* [!DNL Marketo Measure] de logica geeft aan gegevens in dalende orde voorrang die met de hoogste rij van spreadsheet begint en zijn weg neer maakt. Het leest elke emmer, of cel, in rij door rij op zoek naar eerste pasvorm. De gegevens worden vervolgens gesorteerd op basis van de waarden in deze emmers. Hieronder vindt u meer informatie.
* Sorteer het blad niet in alfabetische volgorde, omdat dit de logische regels verstoort.
* Nadat het bestand is geüpload, kunt u de regels gedurende zeven dagen niet meer wijzigen. [!DNL Marketo Measure] gebruikt deze tijd om de aanraakpunten te verwerken en bij te werken.

## [!DNL Marketo Measure] Logica en prioriteiten {#marketo-measure-logic-and-priorities}

De eerste stap bestaat uit het downloaden van de aangepaste kanaalspreadsheet van de [!DNL Marketo Measure] app. Navigeren naar **Instellingen** onder de **Mijn account** en selecteert u **Online**. U kunt kiezen **Originele sjabloon downloaden** of **Huidige regels downloaden**.

![](assets/1.png)

De spreadsheet heeft 7 kolommen:

![](assets/2.png)

* **Kanaal:** Voeg hier uw verschillende marketingkanalen toe
* **Subkanaal:** Voeg hier de overeenkomstige subkanalen toe
* **Campagne:** Voeg hier campagnemenamen toe, of de waarde uit UTMs of Salesforce Campagnes voor [!DNL Marketo Measure] Activiteiten
* **Normaal:** De gemiddelde kolom vertegenwoordigt de waarde van de parameter utm_medium
* **Bron:** De bronkolom vertegenwoordigt de waarde van de parameter utm_source
* **Openingspagina:** bestemmingspagina hier toevoegen
* **Refererende website:** de URL&#39;s van websites die verwijzen naar uw pagina&#39;s of ingebouwde [!DNL Marketo Measure] logica (aangegeven door haakjes)

De achtste kolomnotities die regels bevatten die u niet uit het werkblad kunt verwijderen met &quot;Niet verwijderen&quot;. De bovenkant van het spreadsheet heeft standaardkanaalregels die [!DNL Marketo Measure] raadt u aan deze kanalen niet te wijzigen of te verwijderen, zelfs niet als u deze kanalen niet gebruikt. [!DNL Marketo Measure] heeft verregaande integratie met deze platforms zodat worden zij door gebrek inbegrepen.

De rijen vertegenwoordigen regels en de orde waarin [!DNL Marketo Measure] geeft voorrang aan de gegevens. De eerste rij heeft prioriteit over de tweede rij, de tweede rij heeft prioriteit over de derde rij, etc. Wanneer het bepalen van welk Kanaal van de Marketing &amp; Subchannel aan de aanraak aanraakpunten van de emmer in, [!DNL Marketo Measure] leest van boven naar beneden, van links naar rechts, tot het een rij vindt die aan de criteria van het aanraakpunt voldoet. (IE als een aanraakpunt een utm_source=Facebook heeft, wordt het aanraakpunt vastgezet in het kanaal Social.Facebook vanwege regel 15 in de schermafbeelding).

![](assets/3.png)

[!DNL Marketo Measure] wordt geleverd met 12 standaardkanalen voor uw gebruik. Deze kanalen correleren met platforms waarmee [!DNL Marketo Measure] volledig geïntegreerd is. Verwijder ze niet, of u ze nu gebruikt of niet. Als u wel een van deze platformen gebruikt, bijvoorbeeld Bing Ads, maar liever een andere naamgevingsconventie gebruikt voor het kanaal of subkanaal, kunt u de naam bijwerken. In de onderstaande afbeelding ziet u een voorbeeld.

![](assets/4.png)

De structuur van de regels is ook belangrijk. De regels kunnen op herhaalde informatie en ontbrekende gegevens kijken maar deze structuur is opzettelijk. Voor nauwkeurige gegevenssortering, is het noodzakelijk om elke individuele bron aan het aangewezen kanaal afzonderlijk-zelfs bronnen in kaart te brengen die subkanalen en kanalen delen. Hoe gedetailleerder en gedetailleerder de regels zijn, des te meer inzicht de resultaten zullen krijgen. In feite, is het beste praktijken om een gedetailleerde regel voor elke enige marketing inspanning te schrijven u wilt volgen.

Houd rekening met het volgende: u hebt andere advertenties die u om een of andere reden niet wilt bijhouden, of u ontvangt bezoeken aan uw website via een bekend kanaal, maar niet via een vertrouwde bron. Deze situatie kan leiden tot gegevensverlies als [!DNL Marketo Measure] kan niet de aangewezen regel vinden om de gegevens te gebruiken te sorteren. Om dit te voorkomen, [!DNL Marketo Measure] Hiermee wordt u aangeraden de regel over meerdere rijen te verbreken.

Elke parameter of component van de regel wordt afzonderlijk toegewezen aan het kanaal. Bijvoorbeeld wanneer [!DNL Marketo Measure] heeft [!DNL Facebook] gegevens die moeten worden gesorteerd, zoekt het naar regels met betrekking tot [!DNL Facebook]. Het scant van boven naar beneden. In het onderstaande voorbeeld: [!DNL Marketo Measure] zou begrijpen dat [!DNL Facebook] subchannel, alles moet lezen is de bronparameter om gegevens in het emmertje van die regel te laten vallen.

![](assets/5.png)

De volgende regel vraagt slechts om de middelgrote parameter, zodat zullen om het even welke gegevens met die parameter in dit kanaal worden ingekapseld. Tot slot: [!DNL Facebook], worden alle gegevens die afkomstig zijn van de URL van Facebook in het laatste Facebook-emmertje geplaatst.

Het standaardkanaal &#39;Overige&#39; bestaat voor het afvangen van gegevens die niet aan de criteria van een regel voldoen. Merk op dat sommige emmers in het Andere kanaal sterretjes bevatten (&#42;). Deze sterretjes vertegenwoordigen jokertekens die als &#39;catch-all&#39; fungeren.

![](assets/6.png)

Door [!DNL Marketo Measure] logica die van boven naar beneden werkt, gelieve te merken op dat de vervangingsregel, met een asterisk ( wordt vermeld&#42;), moet helemaal aan het einde van het regelblad worden geplaatst. Alle gegevens die niet door andere regels worden gevangen of gesorteerd, worden automatisch toegevoegd aan dit jokertekenemmertje.

Hieronder vindt u meer voorbeelden van jokertekenlogica:

* &#42;email&#42; = bevat &quot;email&quot;
* &#42;email = eindigt met &quot;email&quot;
* email&#42; = [!UICONTROL starts with email]

Als u een subkanaal maakt voor een van uw kanalen, moet u bovendien een subkanaal maken voor alle regels onder dat kanaal. Met andere woorden, als u één subkanaal maakt, kunt u de rest van de kolommen niet leeg laten.

## De regels voor aangepaste kanalen instellen {#setting-up-your-custom-channels-rules}

Zodra u hebt beslist hoe u uw gegevens wilt organiseren en voorrang geven, bent u bereid om uw regels aan spreadsheet toe te voegen. Hieronder volgen enkele aanbevolen procedures:

* Houd je regels zo eenvoudig mogelijk vanaf het begin. U kunt altijd voortbouwen op de regels terwijl u verdergaat.
* Voeg geen speciale tekens toe aan de kanaalnamen (bijvoorbeeld $%#&amp;&#42;@)
* Bewerk de regels die aan BingAds en AdWords zijn gekoppeld niet. Deze regels zijn van cruciaal belang voor het opnemen van de gegevens die automatisch afkomstig zijn van de [!DNL Marketo Measure] API-integratie met deze platforms. Het is echter geen probleem om de naam van het subkanaal en het kanaal aan uw wensen aan te passen.
* Verwijder de regels met de opmerking &#39;Niet verwijderen&#39; niet.
* De regels voor biologisch zoeken worden altijd achter de [!UICONTROL Paid Search rules]
* U kunt geen regels maken op basis van verschillende subdomeinen.
* Als u meerdere waarden wilt toevoegen in een cel in het werkblad, moet u de waarden scheiden met een puntkomma `;` alleen. Geen komma&#39;s of spaties.
* U hoeft geen dot com (.com) aan het einde van de verwijzende URL toe te voegen.
* Plaats een verwijzende URL niet tussen haakjes, zoals de andere API-gerelateerde regels.

## Uw aangepaste kanaalregels uploaden {#uploading-your-custom-channels-rules}

Zorg ervoor dat alle nieuwe kanaal- en subkanaalwaarden die u toevoegt in de CSV, al zijn toegevoegd in het gebied met kanaalinstellingen van uw Bizible-account. Controleer of alle kanaal- en subkanaalnamen in de CSV overeenkomen met de kanaalinstellingen in het gedeelte [!DNL Marketo Measure] account. Controleer of er komma&#39;s en spaties zijn.

Als u een foutbericht ontvangt tijdens het uploaden, verhelpt u het probleem en uploadt u het opnieuw. Als er geen foutbericht is ontvangen, klikt u op **Opslaan en verwerken** onder aan de pagina.
