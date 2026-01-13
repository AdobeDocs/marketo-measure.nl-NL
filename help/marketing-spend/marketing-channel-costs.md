---
description: Kosten marketingkanaal
title: Kosten marketingkanaal
exl-id: 36ccaff3-db55-47bd-a24e-4aa1894f13e0
feature: Channels, Spend Management
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '1294'
ht-degree: 0%

---


# Kosten marketingkanaal {#marketing-channel-costs}

Een van de meest fundamentele voordelen van het gebruik van [!DNL Marketo Measure] is de mogelijkheid om marketinginspanningen rechtstreeks te koppelen aan de invloed op de inkomsten, met zo veel granulariteit als u wilt. Het rendement van investeringen kan op het niveau van de aanspreekpunten worden gezien. Als u van dit voordeel wilt profiteren, moeten de kanaalkosten naar de app [!DNL Marketo Measure] worden geüpload. ROI de rapporten worden automatisch gecreeerd en beschikbaar in het **Op de markt brengend ROI Dashboard** in [&#x200B; experience.adobe.com/marketo-measure &#x200B;](https://experience.adobe.com/marketo-measure){target="_blank"}.

[Klik hier om rechtstreeks naar de instructies te navigeren.](/help/marketing-spend/marketing-channel-costs.md#uploading-marketing-costs)

Met de functie [!DNL Marketo Measure] Marketing Spend kunnen klanten hun uitgaven uploaden via alle kanalen, subkanalen en campagnes. Hoe meer gegevens door klanten worden toegevoegd, hoe meer ROI-rapportage wordt weergegeven in het Dashboard Indelingskenmerk.

Kosten die worden gerapporteerd en geïmporteerd uit directe en indirecte verbindingen worden automatisch op het meest korrelige niveau binnengehaald en hoeven niet te worden geüpload. Dit omvat onze huidige integratie met Google AdWords, Bing Ads, Doubleclick, en Facebook.

[Klik hier om rechtstreeks naar de veelgestelde vragen te navigeren.](/help/marketing-spend/marketing-channel-costs.md#faq)

## Definities {#definitions}

**uitgaven door Campagne**

Op het meest korrelige niveau, kunnen de klanten uitgaven door individuele Campagnes ingaan, die binnen zijn respectieve Kanaal worden gegroepeerd. Voor CRM-campagnes heeft [!DNL Marketo Measure] de campagne-id in een aparte kolom geplaatst, zodat u de uitgaven voor offlinecampagnes van uw CRM in deze tabel kunt toewijzen. Als u op dit niveau uitgaven toevoegt, kunnen klanten het investeringsrendement van de campagne bekijken en de prestaties optimaliseren via Campagne.

Het totaal van alle campagnes te hoeven niet om tot om het even welke waarden samen te vatten ingegaan op Subchannel of Kanaal, maar het kan niet meer zijn dan om het even welke waarden ingegaan op Subchannel of Kanaal. Als de som lager is dan de waarde die is ingevoerd in Subchannel of Channel, voegt [!DNL Marketo Measure] automatisch een rij voor &quot;Anders&quot; toe om het verschil te dekken en eventuele tussenruimten op te vullen.

**uitgaven door Subchannel**

Op een hoger niveau kunnen klanten uitgaven per subkanaal invoeren, gegroepeerd onder het kanaal. Door uitgaven op dit niveau toe te voegen, kunnen klanten het rendement van Subchannel weergeven en de prestaties met Subchannel optimaliseren.

Het totaal van alle subkanalen te hoeven niet om tot om het even welke waarden samen te vatten ingegaan bij het Kanaal, maar het kan niet meer zijn dan om het even welke waarden ingegaan bij het Kanaal. Als de som lager is dan de waarde die is ingevoerd op het Kanaal, voegt [!DNL Marketo Measure] automatisch een rij voor &quot;Anders&quot; toe om het verschil te dekken en eventuele tussenruimten op te vullen.

**uitgaven door Kanaal**

Op het hoogste niveau kunnen klanten uitgaven per kanaal invoeren. Als u op dit niveau uitgaven toevoegt, kunnen klanten de ROI van het kanaal bekijken en de prestaties via het kanaal optimaliseren.

**de Plukker van de Datum**

Het standaarddatumbereik begint op uw begindatum met [!DNL Marketo Measure] tot en met de huidige maand. Om ervoor te zorgen dat de kosten correct blijven, kunt u geen kosten voor toekomstige maanden ingaan, maar u kunt kosten voor maanden ingaan alvorens uw partnerschap met [!DNL Marketo Measure].

**Filter**

Als u de resultaten in de tabel marketinguitgaven wilt verkleinen, selecteert u bovenaan een kanaal om andere kanalen te filteren. Dit is handig wanneer u een team hebt dat zich richt op één kanaal.

**Onderzoek**

Gebruik het vakje van het Onderzoek om passende teksten van Kanalen, Subkanalen, of Campagnes te vinden.

**Download Huidige Kosten**

De gedownloade CSV trekt de resultaten van uw huidig scherm, betekenend dat om het even welke data, filters, of onderzoek die worden toegepast zal worden gedownload zoals is.

**uploadt CSV**

Ongeacht welke mening in browser zit, als het een gefilterde mening of de standaardmening met alle data en kanalen is, kunt u om het even welke CSV uploaden.

De meest voorkomende fout waarmee u wordt geconfronteerd, is de indeling van de datumkolommen. Deze fout treedt op als de datumnotatie wordt gewijzigd en kan opzettelijk optreden als u van Excel naar Google Sheets gaat. Onthoud dat de datum MM-YY moet zijn, dus sep-12 en niet sept-12, of mei-12 en niet 05-12.

## Voordat u begint {#before-you-begin}

[!DNL Marketo Measure] wordt geleverd met 13 standaardkanalen die kunnen worden gebruikt of uitgebreid. Daarnaast kunnen maximaal 40 online- en offlinekanalen worden gemaakt om uw unieke marketingstructuur te kunnen aanpassen. Voortbouwend op dit, kunnen in totaal 200 subkanalen worden gecreeerd om deze online en off-line kanalen eveneens te steunen.

[!DNL Marketo Measure] downloadt automatisch de kosten van marketingkanalen van platforms met een API-integratie, zoals Bing Ads en Google AdWords. Kosten voor platformen die niet met [!DNL Marketo Measure] zijn geïntegreerd, moeten handmatig worden geüpload. De afzetkanalen moeten worden opgezet voordat de kostengegevens worden geüpload.

## Marketingkosten uploaden {#uploading-marketing-costs}

Zodra afzetkanalen en regels zijn opgezet of bijgewerkt, kunnen de bijbehorende kosten worden geüpload. Hiervoor voert u de volgende stappen uit:

**Stap 1: Navigeer aan de pagina van de Uitgaven van de Marketing in [!DNL Marketo Measure] App.**

Ga naar het menu **[!UICONTROL My Account]** , klik **[!UICONTROL Settings]** en navigeer naar de optie **[!UICONTROL Marketing Spend]** in de linkerzijbalk onder de sectie **[!UICONTROL Reporting]** .

![&#x200B; de montagespagina van de Uitgaven van de Marketing in Marketo Measure &#x200B;](assets/1.png)

**Stap 2: Download de Huidige Kosten CSV**

Navigeer rechts van het scherm en klik op **[!UICONTROL Download Current Costs].** Met deze optie kunt u een spreadsheet in CSV-indeling downloaden.

![&#x200B; de Huidige optie van de Kosten van de Download op de pagina van de Uitgaven van de Marketing &#x200B;](assets/2.png)

**Stap 3: Open het CSV- Dossier en maak Veranderingen**

U kunt het bestand importeren en openen met Google Sheets, Apple Numbers, Microsoft Excel of de software die u kiest. [!DNL Marketo Measure] raadt u aan Google Sheets te gebruiken.

Nadat u het blad hebt geïmporteerd, brengt u de gewenste wijzigingen aan, zoals kosten toevoegen aan kanalen en subkanalen of bestaande informatie bijwerken.

Controleer de logische regels in uw vel. Elke rij moet een kanaal en een van de subkanalen bevatten, gescheiden door een punt (.) aan het einde. Het is belangrijk deze indeling consistent te gebruiken.

Als u bijvoorbeeld Facebook als subkanaal en sociaal kanaal wilt aanduiden als kanaal, moet de regel als volgt worden geschreven: &quot;Social.Facebook&quot;. Op dezelfde manier moet de kanaalsyntaxis voor het bijhouden van een offlinegebeurtenis &#39;Events.Big Conference&#39; zijn. In de onderstaande afbeelding worden voorbeelden weergegeven:

![&#x200B; Csv- voorbeeld die kanaal en subchannel kosteningangen tonen &#x200B;](assets/3.png)

_Extra Nota&#39;s_:

Wijzig de datums in het werkblad niet omdat dit problemen kan veroorzaken wanneer het document wordt geüpload.

Laat geen veld leeg. Zelfs als er geen waarde van de dollar is om toe te voegen, ga $0 als dollarbedrag in.

De kosten voor Bing Ads en Google AdWords hoeven niet te worden ingevoerd of bijgewerkt omdat [!DNL Marketo Measure] deze gegevens automatisch ophaalt via de API-verbinding met deze platforms.

**Stap 4: Sparen dossier in formaat CSV**

Als u in Google Sheets werkt, moet u het bestand eerst downloaden. Sluit maandgegevens niet uit of verwijder ze niet omdat dit problemen veroorzaakt wanneer u probeert het CSV-bestand later te uploaden naar [!DNL Marketo Measure] .

**Stap 5: Upload het CSV- dossier**

Ga naar de sectie **[!UICONTROL Cost]** van de [!DNL Marketo Measure] app en klik op **[!UICONTROL Upload.CSV]** . Het systeem zal zich vernieuwen en op de nieuwe informatie wijzen.

## Veelgestelde vragen {#faq}

**waarom zijn de aantallen die in CSV** verschijnen

Als er geen waarde wordt ingevoerd op een hoger niveau, zoals Kanaal of Subkanaal, zal [!DNL Marketo Measure] automatisch de som kindniveaus voor u ingaan, die zullen worden voorgesteld zodra uw dossier wordt geupload. Als de som van de onderliggende items lager is dan een waarde die voor het bovenliggende element is ingevoerd, voegt [!DNL Marketo Measure] een rij &quot;Overige&quot; toe om het verschil in het totaal weer te geven.

**hoe worden de Campagnes bepaald in de lijst die ik zie?**

Op dit moment geven onze resultaten een overzicht van de campagnes die we hebben gezien en die met een aanraakpunt zijn gecrediteerd. Als er activiteit van een Campagne was, tonen wij die Campagne die op de Datum van het Aanraakpunt wordt gebaseerd dat het voorkwam.

**er zijn teveel rijen en kolommen om door te bewegen - kan ik de mening consolideren?**

Met de mogelijkheid om het datumbereik te wijzigen, het kanaal te filteren of naar waarden te zoeken, kunt u de resultaten van de tabel consolideren om beter aan uw behoeften te voldoen.

**waarom kan ik geen dossier uploaden?**

Er zijn verschillende machtigingssets binnen de [!DNL Marketo Measure] -app. Als u een bestand wilt uploaden, moet u een &quot;AccountAdmin&quot; zijn. U kunt dit omzeilen door toegang aan te vragen bij uw accountbeheerder of door uw accountbeheerder het bestand namens u te laten uploaden. Een lijst met gebruikers en hun rollen vindt u onder **[!UICONTROL My Account]** > **[!UICONTROL Settings]** > **[!UICONTROL View/Add Account Users]** .
