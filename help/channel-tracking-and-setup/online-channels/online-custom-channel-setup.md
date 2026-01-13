---
description: Online aangepaste kanaalinstelling - [!DNL Marketo Measure]
title: Online aangepaste kanaalinstelling
exl-id: 170ac564-6cdd-4036-abf0-b9b230bed4f7
feature: Channels
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '1294'
ht-degree: 0%

---


# Online aangepaste kanaalinstelling {#online-custom-channel-setup}

Voor een juiste rapportage moeten de marketingkanalen zo zijn ingesteld dat ze de UTM-strategie van uw organisatie weerspiegelen. Deze gids neemt u door de beste manier om uw regels van het douanekanaal te vormen.

## Voordat u begint {#before-you-begin}

Voordat u begint met het maken van de kanaalregels voor [!DNL Marketo Measure] , moet u rekening houden met de organisatie van uw marketingcampagnes en de manier waarop deze in het [!DNL Marketo Measure] -framework passen. Bepaal welke kanalen, subkanalen, campagnes, en verwijzende websites u wilt volgen.

Denk aan de volgende zaken:

* Uw organisatie kan maximaal 40 aangepaste marketingkanalen maken. Dit geldt zowel voor offline als online kanalen.
* Uw organisatie kan tot 200 subkanalen tot stand brengen.
* Elke inzameling, of emmer, van gegevens heeft zijn eigen regel (rij in spreadsheet) nodig om te specificeren hoe de gegevens zullen worden georganiseerd. Wees zo specifiek mogelijk.
* [!DNL Marketo Measure] geeft aan gegevens de prioriteit in aflopende volgorde, te beginnen met de bovenste rij van het werkblad en het omlaag maken. Het leest elke emmer, of cel, in rij door rij op zoek naar eerste pasvorm. De gegevens worden vervolgens gesorteerd op basis van de waarden in deze emmers. Hieronder vindt u meer informatie.
* Sorteer het vel niet in alfabetische volgorde, omdat dit de logische regels aantast.
* Nadat het bestand is geüpload, kunt u de regels gedurende zeven dagen niet meer wijzigen. [!DNL Marketo Measure] gebruikt deze tijd om de aanraakpunten te verwerken en bij te werken.

## [!DNL Marketo Measure] Logica en prioriteiten {#marketo-measure-logic-and-priorities}

De eerste stap bestaat uit het downloaden van de aangepaste kanaalspreadsheet van de app [!DNL Marketo Measure] . Navigeer aan **Montages** onder **Mijn Account** tabel en selecteer **Online**. U kunt of **Originele Malplaatje van de Download** selecteren of **Huidige Regels van de Download**.

![ pagina die van Montages Online kanaalconfiguratie met het Originele Malplaatje van de Download tonen en de Huidige opties van Regels van de Download ](assets/1.png)

Het werkblad heeft zeven kolommen:

![ het kanaalspreadsheet van de Douane die zeven kolommen toont: Kanaal, Subchannel, Campagne, Medium, Source, het Landing Pagina, en Verwijzende Website ](assets/2.png)

* **Kanaal:** voeg hier uw diverse marketing kanalen toe
* **Subchannel:** voeg hier de overeenkomstige subkanalen toe
* **Campagne:** voeg hier campagnenamen toe, of de waarde uit UTMs of de Campagnes van Salesforce voor de [!DNL Marketo Measure] functionaliteit van Activiteiten komt
* **Medium:** de middelkolom vertegenwoordigt de waarde van de utm_medium parameter
* **Source:** de bronkolom vertegenwoordigt de waarde van de utm_source parameter
* **het Bestaan Pagina:** voeg hier het landen pagina toe
* **Verwijzend Website:** URLs van websites die verkeer naar uw pagina&#39;s of ingebouwde [!DNL Marketo Measure] logica (die door steunen wordt vermeld) verwijzen

In de achtste kolom wordt aangegeven welke regels u niet uit het werkblad kunt verwijderen met &quot;Niet verwijderen&quot;. De bovenkant van het spreadsheet heeft standaardkanaalregels die [!DNL Marketo Measure] u adviseert niet te veranderen of te verwijderen zelfs als u deze kanalen niet gebruikt. [!DNL Marketo Measure] heeft verregaande integratie met deze platforms, zodat deze standaard worden opgenomen.

De rijen vertegenwoordigen regels en de volgorde waarin [!DNL Marketo Measure] de gegevens prioriteert. De eerste rij heeft prioriteit over de tweede rij, de tweede rij heeft prioriteit over de derde rij, etc. Wanneer het bepalen van welk Kanaal van de Marketing en Subchannel aan emmertouchpoints in, [!DNL Marketo Measure] top-down, links aan recht leest, tot het een rij vindt die aan de criteria van touchpoint voldoet. (Als een aanraakpunt een `utm_source=Facebook` heeft, wordt het aanraakpunt naar het kanaal Social.Facebook verplaatst vanwege regel 15 in de schermafbeelding).

![ Spreadsheet die van de Regels van het Kanaal top-down prioritaire orde met sociaal.Facebook regelvoorbeeld benadrukte ](assets/3.png) tonen

[!DNL Marketo Measure] wordt geleverd met 12 standaardkanalen voor uw gebruik. Deze kanalen hebben betrekking op platforms waarmee [!DNL Marketo Measure] volledig is geïntegreerd. Verwijder ze niet, of u ze nu gebruikt of niet. Als u wel een van deze platformen gebruikt, bijvoorbeeld Bing Ads, maar liever een andere naamgevingsconventie gebruikt voor het kanaal of subkanaal, kunt u de naam bijwerken. In de onderstaande afbeelding ziet u een voorbeeld.

![ Standaard kanaalregels die 12 geïntegreerde platforms met klantgerichte kanaal en subchannel namen tonen ](assets/4.png)

De structuur van de regels is ook belangrijk. De regels kunnen op herhaalde informatie en ontbrekende gegevens kijken maar deze structuur is opzettelijk. Voor nauwkeurige gegevenssortering, is het noodzakelijk om elke individuele bron aan het aangewezen kanaal afzonderlijk-zelfs bronnen in kaart te brengen die subkanalen en kanalen delen. Hoe gedetailleerder en korter de regels zijn, des te duidelijker de resultaten zijn. In feite is het aan te raden een gedetailleerde regel te schrijven voor elke marketinginspanning die u wilt bijhouden.

Denk aan de volgende situatie: u hebt andere advertenties die u om een of andere reden niet wilt bijhouden, of u ontvangt bezoeken aan uw website via een bekend kanaal, maar niet via een bekende bron. Deze situatie kan leiden tot gegevensverlies als [!DNL Marketo Measure] niet de juiste regel kan vinden om de gegevens te sorteren. Om dit te voorkomen, raadt [!DNL Marketo Measure] u aan de regel over een aantal rijen te verbreken.

Elke parameter of component van de regel wordt afzonderlijk toegewezen aan het kanaal. Wanneer [!DNL Marketo Measure] bijvoorbeeld [!DNL Facebook] -gegevens moet sorteren, zoekt het naar regels die betrekking hebben op [!DNL Facebook] . Het scant van boven naar beneden. In het onderstaande voorbeeld zou [!DNL Marketo Measure] begrijpen dat voor het eerste [!DNL Facebook] -subkanaal alleen de bronparameter hoeft te worden gelezen om gegevens in het emmertje van die regel te plaatsen.

![ het kanaalregels van Facebook voorbeeld die veelvoudige rijen met verschillende parameters tonen aan subkanalen ](assets/5.png) worden in kaart gebracht

De volgende regel vraagt alleen om de parameter medium, zodat alle gegevens met die parameter in dit kanaal worden gebundeld. Ten slotte worden voor [!DNL Facebook] alle gegevens die afkomstig zijn van de Facebook-URL in het laatste Facebook-emmertje geplaatst.

Het standaardkanaal &#39;Overige&#39; bestaat voor het afvangen van gegevens die niet aan de criteria van een regel voldoen. Merk op dat sommige emmers in het Andere kanaal sterretjes (&#42;) bevatten. Deze sterretjes vertegenwoordigen jokertekens die als &#39;catch-all&#39; fungeren.

![ Andere kanaalregels die vervangingssterretjes als vangst-alle emmers voor onovertroffen gegevens tonen ](assets/6.png)

Wegens [!DNL Marketo Measure] logica die van boven tot onder werkt, zou de vervangingsregel, met een asterisk (&#42; wordt vermeld), aan het zeer eind van uw regelblad moeten worden geplaatst. Alle gegevens die niet door de andere regels worden gevangen of gesorteerd, worden toegevoegd aan dit jokertekenemmertje.

Hieronder vindt u meer voorbeelden van jokertekenlogica:

* &#42; e-mail &#42; = bevat &quot;e-mail&quot;
* &#42; email = eindigt met &quot;email&quot;
* email&#42; = [!UICONTROL starts with email]

Als u een subkanaal maakt voor een van uw kanalen, moet u bovendien een subkanaal maken voor alle regels onder dat kanaal. Met andere woorden, als u één subkanaal maakt, kunt u de rest van de kolommen niet leeg laten.

## De regels voor aangepaste kanalen instellen {#setting-up-your-custom-channels-rules}

Zodra u hebt beslist hoe u uw gegevens wilt organiseren en voorrang geven, bent u bereid om uw regels aan spreadsheet toe te voegen. Hieronder vindt u een aantal aanbevolen procedures:

* Houd je regels zo eenvoudig mogelijk vanaf het begin. U kunt altijd voortbouwen op de regels terwijl u verdergaat.
* Voeg geen speciale tekens toe aan de kanaalnamen (bijvoorbeeld $%#&amp;&#42;@)
* Bewerk de regels die aan BingAds en AdWords zijn gekoppeld niet. Deze regels zijn van cruciaal belang voor het vastleggen van de gegevens die automatisch afkomstig zijn van de API-integratie van [!DNL Marketo Measure] met deze platforms. Het is echter geen probleem om de naam van het subkanaal en het kanaal aan uw wensen aan te passen.
* Verwijder de regels met de opmerking &#39;Niet verwijderen&#39; niet.
* Regels voor biologisch zoeken worden altijd achter [!UICONTROL Paid Search rules] geplaatst
* U kunt geen regels maken op basis van verschillende subdomeinen.
* Als u meerdere waarden wilt toevoegen in een cel in het werkblad, moet u de waarden scheiden met een puntkomma `;` . Geen komma&#39;s of spaties.
* U hoeft geen dot-com (.com) aan het einde van de verwijzende URL toe te voegen.
* Plaats een verwijzende URL niet tussen haakjes, zoals de andere API-gerelateerde regels.

## Uw aangepaste kanaalregels uploaden {#uploading-your-custom-channels-rules}

Zorg ervoor dat alle nieuwe kanaal- en subkanaalwaarden die u toevoegt in de CSV, al zijn toegevoegd in het gebied met kanaalinstellingen van uw Bizible-account. Controleer of alle kanaal- en subkanaalnamen in de CSV overeenkomen met het gebied met kanaalinstellingen van uw [!DNL Marketo Measure] -account. Controleer of er komma&#39;s en spaties zijn.

Als er een foutbericht wordt weergegeven tijdens het uploaden, verhelpt u het probleem en uploadt u het opnieuw. Als geen foutenmelding wordt ontvangen, klik **sparen &amp; Proces** bij bodem van de pagina.
