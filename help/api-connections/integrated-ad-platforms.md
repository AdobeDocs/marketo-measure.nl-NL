---
description: Richtlijnen voor geïntegreerde ad-hocplatforms voor Marketo Measure-gebruikers
title: Geïntegreerde AD-platforms
exl-id: df30ee8a-8b07-4f14-94e8-cc482fca8b18
feature: APIs, Integration
hidefromtoc: true
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '1703'
ht-degree: 0%

---

# Geïntegreerde AD-platforms {#integrated-ad-platforms}

[!DNL Marketo Measure] heeft API-verbindingen met Google AdWords, Microsoft BingAds, [!DNL Facebook] Ads en DoubleClick Campagne Manager. Via deze API-verbindingen kan [!DNL Marketo Measure] eenvoudig gegevens ophalen en naar uw CRM verzenden, samen met de externe app voor kopers. Er is geen handmatig uploaden van kosten of gegevens vereist. Uw accounts moeten gewoon zijn verbonden met en geautoriseerd voor de app [!DNL Marketo Measure] . [!DNL Marketo Measure] downloadt vervolgens automatisch uw marketingkosten van de platforms en laadt deze in de app [!DNL Marketo Measure] . Als u automatische labeling inschakelt voor AdWords, BingAds of [!DNL Facebook] Ads, voegt [!DNL Marketo Measure] de parameters automatisch toe aan de URL&#39;s van uw advertenties.

## Verbinding maken met advertentieplatforms {#how-to-connect-ad-platforms}

Voordat we details van elk platform bekijken, gaan we na hoe we een van deze accounts kunnen verbinden met [!DNL Marketo Measure] . Meld u eerst aan bij de app [!DNL Marketo Measure] en navigeer naar de optie **[!UICONTROL Settings]** onder de tab **[!UICONTROL My Account]** linksboven in het scherm. Selecteer vervolgens **[!UICONTROL Connections]** onder de sectie **[!UICONTROL Integrations]** aan de linkerkant.

Zoals in de onderstaande afbeelding wordt weergegeven, ziet u een knop om nieuwe advertentieverbindingen in te stellen.

![&#x200B; zoals aangetoond in het beeld hieronder, zult u een knoop aan &#x200B;](assets/bizible-guide-1.png) zien

Nadat u op de knop [!UICONTROL Set up New Ads Connection] hebt geklikt, wordt een venster (dat hieronder wordt weergegeven) weergegeven met vier pictogramtypen. [!UICONTROL connect] Klik op Verbinding maken en een ander venster verschijnt met de vraag naar referenties. Voer de gegevens in en klik op [!UICONTROL authorize] om de account te verbinden met [!DNL Marketo Measure] .

![&#x200B; nadat u de Opstelling Nieuwe knoop van de Verbinding van Advertenties klikt, a &#x200B;](../assets/marketo-engage-activities-05.png)

## Google AdWords {#google-adwords}

Wanneer u advertenties maakt in [!DNL Google AdWords] , wordt u aangeraden uw campagnes op drie manieren te labelen: handmatig labelen, automatisch labelen of een sjabloon voor bijhouden maken. Het handmatig labelen van de URL van AdWords is afhankelijk van de manier waarop u de parameters aan het einde van de URL&#39;s van de advertenties definieert en toevoegt. Met handmatige codering kunnen niet-Google-platforms de gegevens die door de parameters zijn verzameld, gemakkelijk lezen.

De het Volgen Malplaatje is een hulpmiddel Google verstrekt om toe te voegen wat het parameters ValueTrack roept. Ze werken op dezelfde manier als UTM&#39;s en andere tagparameters.

## Wat gebeurt er als Automatisch labelen is ingeschakeld {#what-happens-when-auto-tagging-is-enabled}

[!DNL Marketo Measure] Zoekt naar Sjablonen bijhouden in uw [!DNL AdWords] -account:

* *Optie A*: Het Volgen Malplaatje wordt gevonden. [!DNL Marketo Measure] voegt de parameters ervan toe aan de sjabloon.
* *Optie B*: De herleiding van de derde wordt gevonden. Als er een doorverwijzing van derden wordt gevonden in de sjabloon voor reeksspatiëring, kan [!DNL Marketo Measure] geen actie ondernemen. U moet de [!DNL Marketo Measure] -tags handmatig toevoegen aan het systeem van derden. Een voorbeeld van omleiding door derden zou een instrument voor het beheren van biedingen zijn, zoals Kenshoo of Marin. Leer meer over hoe [&#x200B; de hulpmiddelen van het biedingsbeheer  [!DNL Marketo Measure]](/help/api-connections/how-bid-management-tools-affect-marketo-measure.md){target="_blank"} beïnvloeden.

* *Optie C*: Geen het Volgen Malplaatje wordt gevonden. [!DNL Marketo Measure] doorzoekt al uw URL&#39;s voor advertentiebestemming naar de [!DNL Marketo Measure] -parameters. Gebaseerd op de scan, indien:
   * Er zijn parameters gevonden: de installatie is voltooid!
   * Parameters worden niet gevonden: [!DNL Marketo Measure] voegt de parameters toe aan het einde van de URL&#39;s voor het toevoegen van doelen. [!DNL Marketo Measure] voegt nieuwe advertenties toe binnen twee uur nadat deze zijn gemaakt. Onthoud dat de parameters niet aan een sjabloon worden toegevoegd.

Leer meer over onze [[!DNL AdWords]  auto-etiketterende functionaliteit &#x200B;](/help/api-connections/understanding-marketo-measure-adwords-tagging.md){target="_blank"}.

## [!DNL Marketo Measure] Automatisch labelen voor Adwords inschakelen {#how-to-enable-marketo-measure-auto-tagging-for-adwords}

Alvorens [!DNL Marketo Measure] auto-etiketteren toe te laten, **zorg ervoor dat u een het volgen malplaatje hebt dat op het niveau van de Rekening, van de Campagne of van de Groep van de Adwords wordt toegelaten binnen uw rekening Adwords. Dit is vereist voor elke Adwords-account waarvoor [!DNL Marketo Measure] automatische labeling is ingeschakeld.** Als u een sjabloon voor bijhouden inschakelt, voorkomt u verlies van gegevens uit de prestatiegeschiedenis en -geschiedenis. Als trackingsjablonen worden ingeschakeld op het niveau Trefwoord, Sitelink of Toevoegen, wordt de advertentie doorlopen in het revisie- en goedkeuringsproces en kan de prestatiegeschiedenis van uw advertenties mogelijk opnieuw worden gestart. Als er helemaal geen traceringssjabloon is ingeschakeld, voegt [!DNL Marketo Measure] de [!DNL Marketo Measure] -trackingparameters rechtstreeks toe aan de &#39;Uiteindelijke URL&#39; van de advertentie, wat ook kan leiden tot verlies van gegevens uit de advertentiegeschiedenis.

Als u een sjabloon voor bijhouden hebt, volgt u de onderstaande instructies om [!DNL Marketo Measure] Automatisch labelen in te schakelen. Opmerking: in [!DNL Marketo Measure] worden ook eventuele gepauzeerde advertenties in uw account automatisch van tags voorzien.

1. Teken binnen aan uw [!DNL Marketo Measure] rekening in [&#x200B; experience.adobe.com/marketo-measure &#x200B;](https://experience.adobe.com/marketo-measure){target="_blank"}.

1. Ga naar [!UICONTROL My Account] > [!UICONTROL Settings] > [!UICONTROL Integrations] > [!UICONTROL Connections] .

   ![1. Ga naar Integrations Connections voor Mijn accountinstellingen.](assets/utilizing-connections-8.png)

1. Klik op het potloodpictogram naast het account Adwords waarvoor automatische labeling is ingeschakeld voor [!DNL Marketo Measure] .

   ![1. Klik op het potloodpictogram naast de Adwords-account die wordt geactiveerd &#x200B;](assets/utilizing-connections-9.png)

1. Schakel in de rechterbovenhoek de **[!UICONTROL Autotagging]** -schakelaar in op **[!UICONTROL Yes]** . Klik onder aan de pagina op **[!UICONTROL Learn More]** om het tekstvak uit te vouwen en klik op **[!UICONTROL Save]** . Setup voor automatisch labelen is voltooid.

   ![1. Schakel in de rechterbovenhoek de schakeloptie Autotagging in op &#x200B;](assets/utilizing-connections-10.png)

## Hoe te opstelling een het Volgen Malplaatje in AdvertentieWoorden met [!DNL Marketo Measure] Parameters {#how-to-set-up-a-tracking-template-in-adwords-with-marketo-measure-parameters}

Houd er rekening mee dat u volgsjablonen op het niveau [!UICONTROL Account] , [!UICONTROL Campaign] of Groep toevoegen aan Advertentie-woorden moet toevoegen. Als u volgsjablonen toevoegt aan het trefwoord-, sitelink- of advertentieniveau, moet uw advertentie het revisie- en goedkeuringsproces doorlopen en loopt u het risico dat de prestatiegeschiedenis van uw advertenties opnieuw wordt gestart. Leer meer over [&#x200B; het creëren van het volgen malplaatjes &#x200B;](https://support.google.com/adwords/answer/6076199?hl=en#tracking){target="_blank"}.

1. Meld u aan bij uw [!DNL Google AdWords] -account.
1. Ga naar de [!UICONTROL Campaigns] -weergave op de linkernavigatiebalk
1. Navigeer naar &quot;[!UICONTROL Settings]&quot;, ook in de linkernavigatiebalk
1. Wissel met de [!UICONTROL Account Settings] mening over de bovenkant van de knevel
1. De sectie &quot;[!UICONTROL Tracking]&quot; uitbreiden
1. Plak een van de volgende tekstreeksen in de sjabloon voor tekstspatiëring om de waarde van de sjabloon in te stellen:

   * Als u vraagtekens hebt in ALLE URL&#39;s, gebruikt u de volgende URL-tekst:

   `{lpurl}&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

   * Als u geen vraagtekens op een van uw URL&#39;s hebt, voegt u de volgende URL-tekst toe:

   `{lpurl}?_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}*`

   Om te voorkomen dat fouten optreden wanneer u uw URL&#39;s handmatig labelt, wordt doorgaans aanbevolen de UTM-parameters automatisch te genereren. Dit hoeft niet automatisch labelen met ADWoorden of [!DNL Marketo Measure] -parameters te betekenen, er zijn meerdere gereedschappen die het proces vereenvoudigen door de parameters voor de URL automatisch te genereren op basis van de informatie die u opgeeft.

   >[!TIP]
   >
   >Als er een fout optreedt met de mededeling dat de sjabloon voor bijhouden ongeldig is, probeert u de cache van de browser te wissen en het opnieuw te proberen. Dit lost het probleem vaak op.

## UTM-tags automatisch genereren voor [!DNL Google AdWords] {#how-to-automatically-generate-utm-tags-for-google-adwords}

UTM-tags kunnen in eerste instantie moeilijk worden gemaakt, maar er zijn veel gereedschappen beschikbaar waarmee u eenvoudig URL&#39;s kunt maken met UTM-parameters. U kunt een van de volgende bronnen gebruiken of op internet zoeken naar meer gereedschappen. Houd er rekening mee dat [!DNL Marketo Measure] niets ondersteunt of garandeert met deze platforms en gereedschappen.

**[!DNL Google URL]Builder**

Google URL Builder is een standaardprogramma voor het maken van correct opgemaakte URL&#39;s met UTM-tags. Ga URL en de gewenste waarde van elke parameter in en klik &quot;[!UICONTROL Generate URL]&quot;. Dit is een ideaal hulpmiddel om te gebruiken als u slechts een paar URLs aan markering hebt. Heb toegang tot het hulpmiddel [&#x200B; hier &#x200B;](https://support.google.com/analytics/answer/1033867?hl=en){target="_blank"}.

**Google Spreadsheet die door EpikOne** wordt geproduceerd

Dit spreadsheet heeft een formule die geëtiketteerde bestemmingsURLs automatisch zal produceren. Dit is een handig gereedschap als u een groot aantal koppelingen van tags wilt voorzien. Heb toegang tot spreadsheet [&#x200B; hier &#x200B;](https://spreadsheets.google.com/ccc?key=p7c_HKcmspSUfEYSO0gskKw&hl=en){target="_blank"}.

**Rafflecopter het Tags toevoegen Hulpmiddel van de Verbinding**

Het spreadsheet dat door Rafflecopter wordt gecreeerd is een gewijzigde versie van [!DNL EpikOne's] spreadsheet. Het bevat ook een formule die automatisch geëtiketteerde bestemmingsverbindingen voor u aan gebruik zal produceren.

Elk van deze hulpmiddelen heeft gedetailleerde instructies op hoe te om het te gebruiken en te wijzigen om aan uw behoeften te passen. Het hulpmiddel is beschikbaar [&#x200B; hier &#x200B;](https://docs.google.com/spreadsheets/d/1QCIr1WUJQHE68cA4VTks2XE7nxuryaUymCEy_23-Oew/edit#gid=0){target="_blank"}.

**efficiënt het Ongelofelijke Bouwer UTM**

Dit gereedschap is een Chrome-extensie waarmee u snel UTM-tags kunt genereren. Vind het [&#x200B; hier &#x200B;](https://chrome.google.com/webstore/detail/effin-amazing-utm-builder/eoaapiimcaimddnfhfnifgkinmpcbccp?hl=en){target="_blank"}.

## Bing Ads {#bing-ads}

Bing Ads is een geïntegreerd platform waarmee u automatische codering voor URL&#39;s kunt inschakelen of een hulpprogramma van derden, zoals [!DNL Marketo Measure] , kunt gebruiken om advertenties van tags te voorzien. [!DNL Bing Ads] is ook afhankelijk van UTM-parameters.

Onze integratie ondersteunt de volgende advertentietypen:

* Tekst toevoegen
* Mobiele advertentie
* Toegevoegde tekst uitgebreid


De functie voor automatische labeling van Bing Ads voegt de volgende UTM-parameters toe:

* Utm_source
* Utm_medium
* Utm_term

De automatische tagging van Bing Ads voegt ook de volgende aangepaste parameter toe:

`_bt={adid}`

De tekenreeks ziet er als volgt uit:

`{lpurl}?_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`

Het is belangrijk om op te merken dat [!DNL Bing Ads] u toestaat om nog meer parameters toe te voegen door hun douanemarkeringen in uw definitieve URLs te gebruiken om meer granulariteit te bereiken, als u zou willen.

U kunt desgewenst een sjabloon voor bijhouden gebruiken, maar [!DNL Bing Ads] en [!DNL Marketo Measure] hoeven niet te worden geïntegreerd. Dit komt doordat in [!DNL Bing] advertenties kunnen worden bewerkt zonder de geschiedenis te wijzigen, zodat [!DNL Marketo Measure] de doel-URL kan bijwerken.

Automatisch labelen moet zijn ingeschakeld via [!DNL Marketo Measure] , zodat de aangepaste [!DNL Marketo Measure] -parameters automatisch kunnen worden toegevoegd. Er bestaat geen risico dat de geschiedenis van eerdere advertenties met Bing Ads verloren gaat.

Ga naar de [[!DNL Bing Ads] &#x200B;](https://advertise.bingads.microsoft.com/en-us/blog/post/august-2016/upgraded-urls-now-available-in-bing-ads-an-easier-way-to-manage-your-tracking-urls){target="_blank"} website voor meer informatie over het toevoegen van markeringen op hun platform.

## Facebook-advertenties {#facebook-ads}

Dankzij de [!DNL Marketo Measure] -integratie met [!DNL Facebook] kan de URL automatisch worden gedownload en informatie worden toegevoegd en kunnen de parameters van de URL worden voorzien van tags. [!DNL Marketo Measure] haalt de gegevens voor Campagne en Advertentieset door middel van automatische labeling aan. In het veld Naam advertentieset wordt het veld Naam advertentiegroep ingevuld. Voor meer informatie bij vestigingURL markeringen op het [!DNL Facebook] platform, bezoek de [!DNL Facebook] [&#x200B; zaken &#x200B;](https://www.facebook.com/business/help/1016122818401732/?ref=u2u){target="_blank"} pagina.

Voordat u automatische labeling met [!DNL Facebook Ads] inschakelt, is het belangrijk dat u de vorige prestatiegeschiedenis exporteert als een CSV-bestand. Wanneer [!DNL Marketo Measure] tags [!DNL Facebook Ads] nu met de parameter _bf heeft, leest [!DNL Facebook] de advertenties als gloednieuw en wordt de prestatiegeschiedenis gewist. Daarom is het belangrijk om een verslag van de vorige prestaties uit te voeren als dat iets van waarde aan u en uw organisatie is.

U kunt uw [!DNL Facebook] -account op elk gewenst moment verbinden met de [!DNL Marketo Measure] -app en er gaan geen gegevens verloren. De prestatiegeschiedenis wordt alleen gewist wanneer automatische labeling is ingeschakeld.

Zie [&#x200B; dit artikel &#x200B;](https://www.facebook.com/business/help/393890194130036){target="_blank"} van Facebook voor meer informatie over het uitvoeren [!DNL Facebook] Ad- rapporten.

## GekoppeldIn gesponsorde inhoud {#linkedin-sponsored-content}

Met de integratie LinkedIn kan [!DNL Marketo Measure] bestemmings-URL&#39;s coderen op [!DNL LinkedIn] Gesponsorde inhoud. Hierdoor kan [!DNL Marketo Measure] uiteindelijk een gebruiker door zijn volledige touchpoint-reis volgen en de activiteit terugplaatsen naar de specifieke [!DNL LinkedIn] -campagne en Creative. Dit biedt klanten inzicht in de ROI van hun [!DNL LinkedIn] activiteit. [!DNL Marketo Measure] zoekt naar creatieve elementen met een unieke parameter [!DNL LinkedIn] Share en voegt hieraan een parameter `?_bl={creativeId}` toe.

Omdat [!DNL LinkedIn] Delen kunnen worden gebruikt voor meerdere campagnes en Creative Cloud, vragen we dat klanten bestaande Creative Cloud niet kopiëren of dupliceren, zodat ze hun unieke karakter kunnen behouden. Als Delen worden gevonden en slechts op één Creative worden gebruikt, kan [!DNL Marketo Measure] de Delen labelen zonder dat Creative of Shares opnieuw hoeft te worden gemaakt en blijft alle advertentiegeschiedenis (indrukken, klikken, delen) behouden.

Zodra een Delen op meerdere Creative Cloud wordt gedeeld, moet [!DNL Marketo Measure] een proces doorlopen om te pauzeren, te kopiëren en opnieuw te labelen om een unieke set te kunnen maken. [!DNL Marketo Measure] pauzeert en archiveert live creatieve producten. Dit betekent dat de creatieve elementen die de indrukken, klikken en sociale aandelen bevatten, ook worden gearchiveerd.

## Niet-geïntegreerde platforms {#non-integrated-platforms}

Voor platformen die niet met [!DNL Marketo Measure] zijn geïntegreerd, kan de functie voor automatische labeling van [!DNL Marketo Measure] niet worden gebruikt. De parameters moeten handmatig worden toegevoegd.
