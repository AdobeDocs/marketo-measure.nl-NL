---
unique-page-id: 18874602
description: Kosten marketingkanaal - [!DNL Marketo Measure]
title: Kosten marketingkanaal
exl-id: 36ccaff3-db55-47bd-a24e-4aa1894f13e0
feature: Channels, Spend Management
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '1287'
ht-degree: 0%

---

# Kosten marketingkanaal {#marketing-channel-costs}

Een van de meest fundamentele voordelen van het gebruik van [!DNL Marketo Measure] is de capaciteit om marketing inspanningen aan het effect op opbrengst-met zo veel granulariteit direct aan te sluiten zoals gewenst. Het rendement van investeringen kan op het niveau van de aanspreekpunten worden gezien. Om van dit voordeel te profiteren, moeten de kanaalkosten eenvoudig aan worden geupload [!DNL Marketo Measure] app. ROI-rapporten worden automatisch gemaakt en beschikbaar in het dialoogvenster **Marketing ROI Dashboard** in [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}.

[Klik hier om rechtstreeks naar de instructies te navigeren.](/help/marketing-spend/spend-management/marketing-channel-costs.md#uploading-marketing-costs)

De [!DNL Marketo Measure] Met de functie marketinguitgaven kunnen klanten hun uitgaven uploaden naar alle kanalen, subkanalen en campagnes. Hoe meer gegevens door klanten worden toegevoegd, des te meer ROI-rapportage we kunnen doorvoeren in het Dashboard voor belastingkenmerken.

Kosten die worden gerapporteerd en geïmporteerd uit directe en indirecte verbindingen worden automatisch op het meest korrelige niveau binnengehaald en hoeven niet te worden geüpload. Dit omvat onze huidige integratie met Google AdWords, Bing Ads, Doubleclick, en Facebook.

[Klik hier om rechtstreeks naar de veelgestelde vragen te navigeren.](/help/marketing-spend/spend-management/marketing-channel-costs.md#faq)

## Definities {#definitions}

**Besteed door campagne**

Op het meest korrelige niveau, kunnen de klanten uitgaven door individuele Campagnes ingaan, die binnen zijn respectieve Kanaal worden gegroepeerd. voor CRM-campagnes, [!DNL Marketo Measure] heeft in identiteitskaart van de Campagne in een afzonderlijke kolom getrokken die u zal helpen off-line campagneuitgaven van uw CRM in deze lijst in kaart brengen. Als u op dit niveau uitgaven toevoegt, kunnen klanten het investeringsrendement van de campagne weergeven en de prestaties optimaliseren via Campagne.

Het totaal van alle campagnes te hoeven niet om tot om het even welke waarden samen te vatten ingegaan op Subchannel of Kanaal, maar het kan niet meer zijn dan om het even welke waarden ingegaan op Subchannel of Kanaal. Als de som lager is dan de waarde die is ingevoerd op Subchannel of Channel, [!DNL Marketo Measure] voegt automatisch een rij voor &quot;Andere&quot; toe om het verschil te dekken en eventuele tussenruimten op te vullen.

**Verdelen op subkanaal**

Op een hoger niveau kunnen klanten uitgaven per subkanaal invoeren, gegroepeerd onder het kanaal. Als u op dit niveau uitgaven toevoegt, kunnen klanten de ROI van Subchannel weergeven en de prestaties met Subchannel optimaliseren.

Het totaal van alle subkanalen te hoeven niet om tot om het even welke waarden samen te vatten ingegaan bij het Kanaal, maar het kan niet meer zijn dan om het even welke waarden ingegaan bij het Kanaal. Als de som lager is dan de waarde die op het Kanaal is ingevoerd, [!DNL Marketo Measure] voegt automatisch een rij voor &quot;Andere&quot; toe om het verschil te dekken en eventuele tussenruimten op te vullen.

**Per kanaal**

Op het hoogste niveau kunnen klanten uitgaven per kanaal invoeren. Als u op dit niveau extra uitgaven toevoegt, kunnen klanten de ROI van het Kanaal bekijken en de prestaties via het Kanaal optimaliseren.

**Datumkiezer**

Het standaarddatumbereik begint op uw begindatum met [!DNL Marketo Measure] tot de huidige maand. Om ervoor te zorgen dat de kosten correct blijven, kunt u geen kosten voor toekomstige maanden ingaan, maar u kunt kosten voor maanden vóór uw partnerschap ingaan met [!DNL Marketo Measure].

**Filter**

Als u de resultaten in de tabel marketinguitgaven wilt verkleinen, selecteert u bovenaan een kanaal om andere kanalen te filteren. Dit is handig wanneer u een team hebt dat zich richt op één kanaal.

**Zoeken**

Gebruik het vakje van het Onderzoek om passende teksten van Kanalen, Subkanalen, of Campagnes te vinden.

**Huidige kosten downloaden**

De gedownloade CSV haalt de resultaten uit het huidige scherm. Dit houdt in dat alle datums, filters of zoekopdrachten die worden toegepast, ongewijzigd worden gedownload.

**CSV uploaden**

Ongeacht welke mening in browser zit, als het een gefilterde mening of de standaardmening met alle data en kanalen is, kunt u om het even welke CSV uploaden.

De gemeenschappelijkste fout wij onder ogen zien is het formaat van de datumkolommen, die gebeurt als het datumformaat wordt veranderd en opzettelijk zou kunnen gebeuren als zich tussen Excel en/of de Bladen van Google beweegt. Onthoud dat de datum MM-YY moet zijn, dus sep-12 en niet sept-12, of mei-12 en niet 05-12.

## Voordat u begint {#before-you-begin}

[!DNL Marketo Measure] wordt geleverd met 13 standaardkanalen die kunnen worden gebruikt of uitgebreid. Daarnaast kunnen maximaal 40 online- en offlinekanalen worden gemaakt om uw unieke marketingstructuur te kunnen aanpassen. Voortbouwend op dit, kunnen in totaal 200 subkanalen worden gecreeerd om deze online en off-line kanalen eveneens te steunen.

[!DNL Marketo Measure] worden de kosten van marketingkanalen automatisch gedownload van platforms waarmee de software is geïntegreerd, zoals Bing Ads en Google AdWords. Kosten voor platforms die niet zijn geïntegreerd met [!DNL Marketo Measure] moet u handmatig uploaden. De afzetkanalen moeten worden opgezet voordat de kostengegevens worden geüpload.

## Marketingkosten uploaden {#uploading-marketing-costs}

Zodra afzetkanalen en regels zijn opgezet of bijgewerkt, kunnen de bijbehorende kosten worden geüpload. Hiervoor voert u de volgende stappen uit:

**Stap 1: Navigeer naar de pagina Marketing Spend in het dialoogvenster [!DNL Marketo Measure] App.**

Ga naar de **[!UICONTROL My Account]** menu, klik op **[!UICONTROL Settings]** en navigeer vervolgens naar de **[!UICONTROL Marketing Spend]** optie op de linkerzijbalk onder de optie **[!UICONTROL Reporting]** sectie.

![](assets/1.png)

**Stap 2: Download de huidige CSV-kosten**

Navigeer rechts van het scherm en klik op **[!UICONTROL Download Current Costs].** Met deze optie kunt u een werkblad in CSV-indeling downloaden.

![](assets/2.png)

**Stap 3: Open het CSV-bestand en breng wijzigingen aan**

U kunt het bestand importeren en openen met Google Sheets, Apple Numbers, Microsoft Excel of de software die u kiest. [!DNL Marketo Measure] raadt u aan Google Sheets te gebruiken.

Nadat u het blad hebt geïmporteerd, brengt u de gewenste wijzigingen aan, zoals kosten toevoegen aan kanalen en subkanalen of bestaande informatie bijwerken.

Controleer de logische regels in uw vel. Elke rij moet een kanaal en een van de subkanalen bevatten, gescheiden door een (.) punt aan het einde. Het is belangrijk deze indeling consistent te gebruiken.

Als u bijvoorbeeld Facebook als subkanaal en sociaal kanaal wilt aanduiden als kanaal, moet de regel als volgt worden geschreven: &quot;Social.Facebook&quot;. Op dezelfde manier moet de kanaalsyntaxis voor het bijhouden van een offlinegebeurtenis &#39;Events.Big Conference&#39; zijn. In de onderstaande afbeelding worden voorbeelden weergegeven:

![](assets/3.png)

_Aanvullende opmerkingen_:

Wijzig de datums in het werkblad niet omdat dit problemen kan veroorzaken wanneer het document wordt geüpload.

Laat geen veld leeg. Zelfs als er geen waarde van de dollar is om toe te voegen, ga $0 als dollarbedrag in.

Kosten voor Bing Ads en Google AdWords hoeven niet te worden ingevoerd of bijgewerkt omdat [!DNL Marketo Measure] Deze gegevens worden automatisch opgehaald vanaf de API-verbinding met deze platforms.

**Stap 4: Bestand opslaan in CSV-indeling**

Als u in Google Sheets werkt, moet u het bestand eerst downloaden. Sluit geen maandelijkse gegevens uit of verwijder ze niet omdat dit problemen veroorzaakt wanneer u probeert het CSV-bestand te uploaden naar [!DNL Marketo Measure] later.

**Stap 5: Het CSV-bestand uploaden**

Ga naar de **[!UICONTROL Cost]** van de [!DNL Marketo Measure] app en klik op **[!UICONTROL Upload.CSV]**. Het systeem zal zich vernieuwen en op de nieuwe informatie wijzen.

## Veelgestelde vragen {#faq}

**Waarom worden getallen weergegeven in de CSV**

Als geen waarde op een hoger niveau zoals Kanaal of Subkanaal is ingegaan, [!DNL Marketo Measure] De som van de onderliggende niveaus voor u wordt automatisch berekend. Deze niveaus worden weergegeven wanneer het bestand is geüpload. Als de som van de onderliggende items lager is dan een waarde die voor de bovenliggende toepassing is ingevoerd, [!DNL Marketo Measure] voegt een rij &quot;Overige&quot; toe om het verschil in het totaal aan te geven.

**Hoe worden de campagnes bepaald in de lijst die ik zie?**

Op dit moment geven onze resultaten een overzicht van de campagnes die we hebben gezien en die met een aanraakpunt zijn gecrediteerd. Als er activiteit van een Campagne was, zullen wij die Campagne tonen die op de Datum wordt gebaseerd van het Aanraakpunt dat het voorkwam.

**Er zijn te veel rijen en kolommen om door te kijken - kan ik de mening consolideren?**

Met de mogelijkheid om het datumbereik te wijzigen, het kanaal te filteren of naar waarden te zoeken, kunt u de resultaten van de tabel consolideren om beter aan uw behoeften te voldoen.

**Waarom kan ik een bestand niet uploaden?**

Er zijn verschillende rechtensets binnen het [!DNL Marketo Measure] App. Als u een bestand wilt uploaden, moet u een &quot;AccountAdmin&quot; zijn. U kunt dit omzeilen door toegang aan te vragen bij uw accountbeheerder of door uw accountbeheerder het bestand namens u te laten uploaden. Een lijst met gebruikers en hun rollen vindt u onder **[!UICONTROL My Account]** > **[!UICONTROL Settings]** > **[!UICONTROL View/Add Account Users]**.
