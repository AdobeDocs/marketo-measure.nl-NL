---
unique-page-id: 18874594
description: Geïntegreerde AD-Platforms - [!DNL Marketo Measure] - Productdocumentatie
title: Geïntegreerde AD-Platforms
exl-id: df30ee8a-8b07-4f14-94e8-cc482fca8b18
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '1718'
ht-degree: 0%

---

# Geïntegreerde AD-Platforms {#integrated-ad-platforms}

[!DNL Marketo Measure] heeft API-verbindingen met Google AdWords, Microsoft BingAds, [!DNL Facebook] Advertentie en Dubbelklik de Manager van de Campagne. Via deze API-verbindingen [!DNL Marketo Measure] kan eenvoudig gegevens ophalen en naar uw CRM verzenden, samen met de externe app voor kopers. Er is geen handmatig uploaden van kosten of gegevens vereist. Uw accounts moeten gewoon zijn verbonden met en geautoriseerd voor de [!DNL Marketo Measure] app. [!DNL Marketo Measure] worden uw marketingkosten vervolgens automatisch gedownload van de platforms en geladen in de [!DNL Marketo Measure] app. Als u Automatisch labelen wilt inschakelen voor AdWords, BingAds of [!DNL Facebook] Advertenties, [!DNL Marketo Measure] voegt de parameters automatisch toe aan de URL&#39;s van uw advertenties.

## Verbinding maken met Advertentie-Platforms {#how-to-connect-ad-platforms}

Voordat we details van elk platform bekijken, gaan we na hoe we een van deze accounts kunnen verbinden met [!DNL Marketo Measure]. Eerste aanmelding bij de [!DNL Marketo Measure] en navigeer naar de **[!UICONTROL Settings]** optie onder de **[!UICONTROL My Account]** aan de linkerbovenhoek van het scherm. Selecteer vervolgens **[!UICONTROL Connections]** onder de **[!UICONTROL Integrations]** links.

Zoals in de onderstaande afbeelding wordt weergegeven, ziet u een knop om nieuwe advertentieverbindingen in te stellen.

![](assets/2.png)

Nadat u op de knop [!UICONTROL Set up New Ads Connection] -knop, verschijnt er een venster (hieronder weergegeven) met vier advertenties [!UICONTROL connect]iontypes. Klik op Verbinding maken en een ander venster verschijnt met de vraag naar referenties. Voer de referenties in en klik op [!UICONTROL authorize] om verbinding te maken met de account [!DNL Marketo Measure].

![](assets/select-account-type.png)

## Google AdWords {#google-adwords}

Wanneer u advertenties maakt in [!DNL Google AdWords]U wordt aangeraden uw campagnes op drie manieren te labelen: handmatig labelen, automatisch labelen of door een sjabloon voor bijhouden te maken. Het handmatig labelen van de URL van AdWords is afhankelijk van de manier waarop u de parameters aan het einde van de URL&#39;s van de advertenties definieert en toevoegt. Met handmatige codering kunnen niet-Google-platforms de gegevens die door de parameters zijn verzameld, gemakkelijk lezen.

De het Volgen Malplaatje is een hulpmiddel Google verstrekt om toe te voegen wat het parameters ValueTrack roept. Ze werken op dezelfde manier als UTM&#39;s en andere tagparameters.

## Wat gebeurt er als Automatisch labelen is ingeschakeld {#what-happens-when-auto-tagging-is-enabled}

[!DNL Marketo Measure] Zoekt naar Sjablonen bijhouden in uw [!DNL AdWords] account:

* *Optie A*: Trackingsjabloon is gevonden. [!DNL Marketo Measure] voegt de parameters ervan toe aan de sjabloon.
* *Optie B*: Omleiding door derden is gevonden. Als er een doorleiding van derden wordt gevonden in de sjabloon Volgen, [!DNL Marketo Measure] kan geen actie ondernemen. U moet de opdracht [!DNL Marketo Measure] -tags aan het systeem van derden. Een voorbeeld van omleiding door derden zou een instrument voor het beheren van biedingen zijn, zoals Kenshoo of Marin. Meer informatie over hoe [Bodembeheer heeft invloed op [!DNL Marketo Measure]](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md){target=&quot;_blank&quot;}.

* *Optie C*: Er is geen volgsjabloon gevonden. [!DNL Marketo Measure] doorzoekt al uw URL&#39;s voor advertentiebestemming naar de [!DNL Marketo Measure] parameters. Gebaseerd op de scan, indien:
   * Parameters worden gevonden: de installatie is voltooid!
   * Parameters niet gevonden: [!DNL Marketo Measure] voegt de parameters toe aan het einde van de URL&#39;s voor het toevoegen van doelen. [!DNL Marketo Measure] voegt nieuwe advertenties toe binnen twee uur nadat deze zijn gemaakt. Onthoud dat de parameters niet aan een sjabloon worden toegevoegd.

Meer informatie over onze [[!DNL AdWords] automatisch labelen, functionaliteit](/help/api-connections/utilizing-marketo-measures-api-connections/understanding-marketo-measure-adwords-tagging.md){target=&quot;_blank&quot;}.

## Inschakelen [!DNL Marketo Measure] Automatisch labelen voor Adwords {#how-to-enable-marketo-measure-auto-tagging-for-adwords}

Voor het inschakelen [!DNL Marketo Measure] automatische labeling, **Zorg ervoor dat u een sjabloon voor bijhouden hebt ingeschakeld op account-, campagne- of advertentiegroep-niveau in uw Adwords-account. Dit is vereist voor elk Adwords-account dat [!DNL Marketo Measure] automatische labeling ingeschakeld.** Als u een volgsjabloon inschakelt, voorkomt u verlies van gegevens uit de prestatiegeschiedenis. Houd er rekening mee dat het inschakelen van trackingsjablonen op het niveau Trefwoord, Sitelink of Advertentie ertoe leidt dat de advertentie het revisie- en goedkeuringsproces doorloopt en dat de prestatiegeschiedenis van uw advertenties mogelijk opnieuw wordt gestart. Als er helemaal geen volgsjabloon is ingeschakeld, [!DNL Marketo Measure] voegt de [!DNL Marketo Measure] parameters rechtstreeks bijhouden naar de &quot;Definitieve URL&quot; van de advertentie, wat ook kan leiden tot verlies van gegevens uit de advertentie.

Nadat u een trackingsjabloon hebt, volgt u de onderstaande instructies om [!DNL Marketo Measure] Automatisch labelen. Opmerking: [!DNL Marketo Measure] zullen ook automatisch tags toewijzen aan gepauzeerde advertenties in uw account.

1. Aanmelden bij uw [!DNL Marketo Measure] account op [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target=&quot;_blank&quot;}.

1. Ga naar [!UICONTROL My Account] > [!UICONTROL Settings] > [!UICONTROL Integrations] > [!UICONTROL Connections].

   ![](assets/4.png)

1. Klik op het potloodpictogram naast het account Adwords dat wordt geopend [!DNL Marketo Measure] automatische labeling ingeschakeld.

   ![](assets/5.png)

1. Schakel in de rechterbovenhoek het **[!UICONTROL Autotagging]** schakelen naar **[!UICONTROL Yes]**. Klik onder aan de pagina op **[!UICONTROL Learn More]** om het tekstvak uit te vouwen en klik op **[!UICONTROL Save]**. Setup voor automatisch labelen is voltooid.

   ![](assets/6.png)

## Hoe te opstelling een het Volgen Malplaatje in Advertenties met [!DNL Marketo Measure] Parameters {#how-to-set-up-a-tracking-template-in-adwords-with-marketo-measure-parameters}

Houd er rekening mee dat u trackingsjablonen wilt toevoegen in het menu [!UICONTROL Account], [!UICONTROL Campaign] of Groepniveau toevoegen in Advertentioorden. Als u volgsjablonen toevoegt aan het trefwoord-, sitelink- of advertentieniveau, moet uw advertentie het revisie- en goedkeuringsproces doorlopen en loopt u het risico dat de prestatiegeschiedenis van uw advertenties opnieuw wordt gestart. Meer informatie over [sjablonen voor bijhouden maken](https://support.google.com/adwords/answer/6076199?hl=en#tracking){target=&quot;_blank&quot;}.

1. Meld u aan bij uw [!DNL Google AdWords] Account.
1. Ga naar uw [!UICONTROL Campaigns] weergave op de linkernavigatiebalk
1. Navigeren naar &quot;[!UICONTROL Settings]&quot;, ook op de linkernavigatiebalk
1. In-/uitschakelen naar &quot;[!UICONTROL Account Settings]&quot; boven weergeven
1. De &quot;[!UICONTROL Tracking]&quot; sectie
1. Plak een van de volgende tekstreeksen in de sjabloon voor tekstspatiëring om de waarde van de sjabloon in te stellen:

   * Als u vraagtekens hebt in ALLE URL&#39;s, gebruikt u de volgende URL-tekst:

   `{lpurl}&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

   * Als u geen vraagtekens op een van uw URL&#39;s hebt, voegt u de volgende URL-tekst toe:

   `{lpurl}?_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}*`

   Om te voorkomen dat fouten optreden wanneer u uw URL&#39;s handmatig labelt, wordt doorgaans aanbevolen de UTM-parameters automatisch te genereren. Dit hoeft niet automatisch labelen met AdWords of [!DNL Marketo Measure] parameters, zijn er meerdere gereedschappen die het proces vereenvoudigen door de parameters voor de URL automatisch te genereren op basis van de informatie die u opgeeft.

   >[!TIP]
   >
   >Als er een fout optreedt met de mededeling dat de sjabloon voor bijhouden ongeldig is, probeert u de cache van de browser te wissen en het opnieuw te proberen. Dit lost het probleem vaak op.

## UTM-tags automatisch genereren voor [!DNL Google AdWords] {#how-to-automatically-generate-utm-tags-for-google-adwords}

UTM-tags kunnen in eerste instantie moeilijk worden gemaakt, maar er zijn veel gereedschappen beschikbaar waarmee u eenvoudig URL&#39;s kunt maken met UTM-parameters. U kunt een van de volgende bronnen gebruiken of op internet zoeken naar meer gereedschappen. Houd er rekening mee dat [!DNL Marketo Measure] met deze platforms en instrumenten niets onderschrijft of garandeert.

**[!DNL Google URL]Builder**

Google URL Builder is een standaardprogramma voor het maken van correct opgemaakte URL&#39;s met UTM-tags. Voer gewoon de URL en de gewenste waarde van elke parameter in en klik op &quot;[!UICONTROL Generate URL]&quot;. Dit is een ideaal hulpmiddel om te gebruiken als u slechts een paar URLs aan markering hebt. Toegang tot het gereedschap [hier](https://support.google.com/analytics/answer/1033867?hl=en){target=&quot;_blank&quot;}.

**Google Spreadsheet gegenereerd door EpikOne**

Dit spreadsheet heeft een formule die geëtiketteerde bestemmingsURLs automatisch zal produceren. Dit is een handig gereedschap als u een groot aantal koppelingen van tags wilt voorzien. De spreadsheet openen [hier](https://spreadsheets.google.com/ccc?key=p7c_HKcmspSUfEYSO0gskKw&amp;hl=en){target=&quot;_blank&quot;}.

**Reparatieopter - gereedschap Tags koppelen**

Het spreadsheet dat door Rafflecopter wordt gecreeerd is een gewijzigde versie van [!DNL EpikOne's] spreadsheet. Het bevat ook een formule die automatisch geëtiketteerde bestemmingsverbindingen voor u aan gebruik zal produceren.

Elk van deze hulpmiddelen heeft gedetailleerde instructies op hoe te om het te gebruiken en aan uw behoeften aan te passen. Het gereedschap is beschikbaar [hier](https://docs.google.com/spreadsheets/d/1QCIr1WUJQHE68cA4VTks2XE7nxuryaUymCEy_23-Oew/edit#gid=0){target=&quot;_blank&quot;}.

**Effin Amazing UTM Builder**

Dit gereedschap is een Chrome-extensie waarmee u snel UTM-tags kunt genereren. Zoeken [hier](https://chrome.google.com/webstore/detail/effin-amazing-utm-builder/eoaapiimcaimddnfhfnifgkinmpcbccp?hl=en){target=&quot;_blank&quot;}.

## Bing Ads {#bing-ads}

Bing Ads is een geïntegreerd platform waarmee u automatische codering voor URL&#39;s kunt inschakelen of een hulpprogramma van derden kunt gebruiken, zoals [!DNL Marketo Measure], om advertenties te labelen. [!DNL Bing Ads] vertrouwt ook op UTM-parameters.

De functie voor automatische labeling van Bing Ads voegt de volgende UTM-parameters toe:

* Utm_source
* Utm_medium
* Utm_term

De automatische tagging van Bing Ads voegt ook de volgende aangepaste parameter toe:

`_bt={adid}`

De tekenreeks ziet er als volgt uit:

`{lpurl}?_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`

Het is belangrijk om op te merken dat [!DNL Bing Ads] kunt u nog meer parameters toevoegen door hun douanetags in uw definitieve URLs te gebruiken om meer granulariteit te bereiken, als u zou willen.

Een volgsjabloon kan indien gewenst worden gebruikt, maar is niet nodig voor [!DNL Bing Ads] en [!DNL Marketo Measure] om te integreren. Dit komt omdat [!DNL Bing] Hiermee kunt u advertenties bewerken zonder de geschiedenis te wijzigen, zodat [!DNL Marketo Measure] kan de doel-URL bijwerken.

Automatisch labelen moet zijn ingeschakeld via [!DNL Marketo Measure] zodat de aangepaste [!DNL Marketo Measure] parameters kunnen automatisch worden toegevoegd. Er bestaat geen risico dat de geschiedenis van eerdere advertenties met Bing Ads verloren gaat.

Ga naar [[!DNL Bing Ads]](https://advertise.bingads.microsoft.com/en-us/blog/post/august-2016/upgraded-urls-now-available-in-bing-ads-an-easier-way-to-manage-your-tracking-urls){target=&quot;_blank&quot;} website voor meer informatie over het toevoegen van tags op hun platform.

## Facebook-advertenties {#facebook-ads}

De [!DNL Marketo Measure] integratie met [!DNL Facebook] Hiermee kan de URL automatisch worden gedownload en informatie worden gecodeerd met de bijbehorende parameters. [!DNL Marketo Measure] gebruikt automatisch labelen om informatie over Campagne en advertentieset weer te geven. In het veld Naam advertentieset wordt het veld Naam advertentiegroep ingevuld. Voor meer informatie over het instellen van URL-tags op het tabblad [!DNL Facebook] platform, bezoek [!DNL Facebook] [zakendoen](https://www.facebook.com/business/help/1016122818401732/?ref=u2u){target=&quot;_blank&quot;} pagina.

Voordat u automatische labeling inschakelt met [!DNL Facebook Ads], is het belangrijk om de vorige prestatiesgeschiedenis als CSV uit te voeren. Wanneer [!DNL Marketo Measure] tags [!DNL Facebook Ads] met de parameter _bf, [!DNL Facebook] leest de advertenties als gloednieuw en wist de prestatiegeschiedenis. Daarom is het belangrijk om een verslag van de vorige prestaties uit te voeren als dat iets van waarde aan u en uw organisatie is.

U kunt verbinding maken met uw [!DNL Facebook] op elk moment [!DNL Marketo Measure] en er gaan geen gegevens verloren. De prestatiegeschiedenis wordt alleen gewist als automatische labeling is ingeschakeld.

[Zie dit artikel](https://www.facebook.com/business/help/393890194130036){target=&quot;_blank&quot;} uit Facebook voor meer informatie over exporteren [!DNL Facebook] Advertenties.

## Door linkedIn gesponsorde inhoud {#linkedin-sponsored-content}

Dankzij de LinkedIn-integratie [!DNL Marketo Measure] om doel-URL&#39;s te labelen op [!DNL LinkedIn] Gesponsorde inhoud, waardoor uiteindelijk [!DNL Marketo Measure] om een gebruiker door hun volledige touchpoint reis te volgen en de activiteit terug te brengen naar specifiek [!DNL LinkedIn] Campagne en creatief. Dit verstrekt inzicht aan klanten over het ROI van hun [!DNL LinkedIn] activiteit. [!DNL Marketo Measure] zal zoeken naar creatieve producten met een unieke [!DNL LinkedIn] Delen en een `?_bl={creativeId}` aan het einde van de parameter.

Omdat [!DNL LinkedIn] Delen kunnen worden gebruikt voor meerdere campagnes en Creative Cloud. Wij vragen klanten om bestaande Creative Cloud niet te kopiëren of te dupliceren, zodat deze de unieke kenmerken behoudt. Als er aandelen worden gevonden en waarvan wordt vastgesteld dat deze slechts op één Creative Cloud worden gebruikt, [!DNL Marketo Measure] U kunt de tag voor Delen op dezelfde manier plaatsen zonder dat u Creative Cloud of Share opnieuw hoeft te maken. Alle advertentiehistorie (indrukken, klikken, delen) blijft dan ongewijzigd.

Zodra is vastgesteld dat een aandeel door meerdere Creative Cloud wordt gedeeld, [!DNL Marketo Measure] moet een proces van pauzeren, kopiëren en opnieuw labelen doorlopen om een unieke set te maken. [!DNL Marketo Measure] onderbreken en archiveren van levende creatieve elementen, hetgeen betekent dat ook de creatieve elementen die de indrukken, klikken en sociale aandelen bevatten, worden gearchiveerd.

## Niet-geïntegreerde Platforms {#non-integrated-platforms}

Voor platforms die niet zijn geïntegreerd met [!DNL Marketo Measure]de [!DNL Marketo Measure] functie voor automatische labeling kan niet worden gebruikt. De parameters moeten handmatig worden toegevoegd.
