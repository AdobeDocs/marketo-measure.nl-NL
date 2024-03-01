---
unique-page-id: 18874606
description: UTM-parameters - [!DNL Marketo Measure]
title: UTM-parameters
exl-id: 2b20f3c4-1f39-4ac5-bad1-cb1d630d60e9
feature: UTM Parameters
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 0%

---

# UTM-parameters {#utm-parameters}

Tags toewijzen aan URL&#39;s is een eenvoudige en effectieve manier om gegevens over uw digitale marketingactiviteiten vast te leggen. Het is het proces om parameters aan het eind van URLs toe te voegen die gegevens verzamelen en registreren. De meest gebruikte parameters zijn Urchin Tracking Modules (UTMs), die door Google worden gesteund. Er zijn vijf belangrijke parameters van UTMs beschikbaar: Normaal, Bron, Campagne, Inhoud, en Term. Deze worden meer gedetailleerd besproken in de volgende sectie.

U kunt UTM-parameters handmatig aan URL&#39;s toevoegen of via automatische codering aan bepaalde platforms toevoegen, zoals AdWords. Automatisch labelen automatiseert het toevoegen van parameters aan URL&#39;s. Er is ook de mogelijkheid om [URL-builders](https://ga-dev-tools.web.app/campaign-url-builder/){target="_blank"} om het handmatig labelen van URL&#39;s te versnellen. Met een bouwer URL, specificeert u eenvoudig de waarden die voor elke parameter moeten worden gebruikt en de bouwer formatteert URL voor u.

## Wat zijn UTM-parameters? {#what-are-utm-parameters}

Als u wilt begrijpen hoe UTM-parameters werken, bekijkt u een typische URL zonder UTM&#39;s:

`http://www.adobe.com`

Nu, controleer een URL met UTMs:

`http://www.adobe.com?utm_medium=socialmedia&utm_source =facebook&utm_campaign=seasonal-sale&utm_content=photo-400x700px`

De tweede koppeling bevat meer tekst. UTM-parameters gaan altijd achter het domein op het hoogste niveau (.com in dit voorbeeld) en beginnen met een vraagteken. Hierna is de volgorde van de parameters niet van belang, maar wordt aangeraden een consistente naamgevingsconventie te volgen. Ampersanden moeten tussen elke parameter worden geplaatst om elke UTM te scheiden. Nu kunnen we meer in detail gaan over wat elke parameter vertegenwoordigt.

Meer informatie over [best practices voor het instellen van UTM-parameters](/help/channel-tracking-and-setup/online-channels/best-practices-for-setting-up-utm-parameters.md).

**utm_medium**

* Het medium identificeert de voertuigen die u gebruikt om uw bedrijf op de markt te brengen.
* Het beantwoordt de vraag: &quot;Hoe komen ze bij je terecht?&quot;
* Het geeft het kanaal op het hoogste niveau aan.
* Sociale media, e-mail, biologisch zoeken en betaalde zoekopdrachten zijn voorbeelden van mogelijke gemiddelde waarden.
* Deze parameter wijst gegevens toe aan de [!DNL Marketo Measure] Veld &#39;Normaal&#39;.
* _[!DNL Marketo Measure]Beste praktijken:_ Gebruik dit veld niet om een subkanaal uit te bellen, anders kunnen er problemen optreden bij het genereren van rapporten over het werkelijke kanaal. Gebruik dit om uw marketingvoertuig of -kanaal te identificeren. Als u bijvoorbeeld e-mail wilt gebruiken om uw product op de markt te brengen, is het medium e-mail.

**utm_source**

* De bron identificeert subchannel dat de bron van uw verkeer is.
* Het beantwoordt de vraag: &quot;Waar komt deze persoon vandaan?&quot;
* In een voorbeeld van sociale media is de bron van verkeer het sociale mediaplatform dat wordt gebruikt.
   * In dit voorbeeld: [!DNL Facebook] is de bronwaarde. Andere voorbeelden zijn Twitter en Instagram. Als het UTM-medium [!DNL Paid Search]Aan de andere kant zou de UTM-bron AdWords of BingAds kunnen zijn.

* Deze parameter verwijst naar de [!DNL Marketo Measure] Veld &#39;aanraakpuntbron&#39; in SFDC.
* _[!DNL Marketo Measure]Beste praktijken:_ Deze parameter volgt de bron van uw verkeer, zodat is het niet geschikt om het te gebruiken om op het advertentietype te wijzen, bijvoorbeeld, herrichtend, gesponsord, etc. Het wordt het best gebruikt om het hoger-vlakke subkanaal te volgen. Herinner je, je beantwoordt de vraag &quot;waar komt mijn verkeer uit?&quot; U zoekt naar de referentie. In dit voorbeeld is UTM Source de plaats waar uw advertentie zich bevindt (niet de eigenlijke webpagina, omdat die automatisch buiten tags wordt bijgehouden). Als u een druppelcampagne voor e-mail volgt, is druppele-mail de bron.

**utm_campagne**

* Campagne wordt gebruikt om een specifieke marketing campagne te identificeren.
* Het beantwoordt de vraag: &quot;Waarom komen ze naar je toe?&quot;
* Gebruik dit label om de naam van de advertentiecampagne aan te geven zoals deze bestaat in [!DNL Google AdWords] of [!DNL BingAds]of om de naam aan te geven waarmee u de campagne intern identificeert. U kunt deze tag zelfs gebruiken om andere informatie op te geven, zoals geolocatie of netwerktype.
* Deze parameter verwijst naar de [!DNL Marketo Measure] &#39;Veld Campagnenaam toevoegen&#39; in SFDC.
* _[!DNL Marketo Measure]Beste praktijken_: Gebruik bij het bepalen van de naam van een campagne geen leestekens of lege spaties tussen de woorden, omdat het gebruik van deze markeringen tot fouten in de browsercodering kan leiden. Voor de beste resultaten gebruikt u onderstrepingstekens.

**utm_content**

* Gebruik de parameter UTM-inhoud wanneer u meerdere marketingonderdelen wilt bijhouden die op één webpagina staan. Als u bijvoorbeeld een knop &#39;Een demo aanvragen&#39; en een knop &#39;Aanmelden voor ons wekelijkse nieuwsbrief&#39; hebt en wilt weten welke knop het meeste verkeer genereert, geeft u elke knop een naam en gebruikt u een tag voor UTM-inhoud om de inhoud bij te houden. De naam van elk stuk &quot;inhoud&quot; is de waarde van de tag.
* Deze parameter verwijst naar de [!DNL Marketo Measure] Veld voor &#39;Inhoud toevoegen&#39; in SFDC.
* _[!DNL Marketo Measure]Beste praktijken_: Dit is een optionele waarde, maar [!DNL Marketo Measure] raadt u aan deze functie te gebruiken. Deze tag is gekoppeld aan de titel van de advertentie of het marketingartikel die u wilt bijhouden. Als u een afbeeldingsadvertentie gebruikt, moet u de afmetingen van de afbeelding in de titel schrijven.

**utm_term**

* De term komt overeen met de parameter UTM-inhoud. Term is ideaal voor het identificeren van trefwoorden in advertenties voor betaalde campagnes. Als u de functie voor automatische labeling gebruikt, gebeurt dit voor u. Als u de functie voor automatische tags van uw advertentieplatform niet gebruikt, moet u zorgvuldig alle trefwoorden toevoegen die u wilt bijhouden.
* Deze parameter verwijst naar de [!DNL Marketo Measure] Veld &#39;Trefwoordtekst&#39; in SFDC.
* _[!DNL Marketo Measure]Beste praktijken_: De tag UTM Term is optioneel, maar uitstekend voor het bijhouden van trefwoorden. Controleer de spelling en vermijd het gebruik van speciale tekens. Als er meer dan één woord nodig is, probeert u onderstrepingstekens of helemaal geen spaties te gebruiken.

Elke parameter verzamelt informatie die relevant is voor de toegewezen waarde. Met de waarde van elke tag kunt u al uw digitale campagnes bijhouden en sorteren en de vragen beantwoorden: waar, hoe en waarom?

Hier is een grafiek van de parameters UTM [!DNL Marketo Measure] parsen en het bijbehorende veld Touchpoint waaraan ze zijn gekoppeld:

| **UTM-parameter** | **Overeenkomend [!DNL Marketo Measure] Veld** |
|---|---|
| utm_medium | Normaal |
| utm_source | Aanraakpuntbron |
| utm_campagne | Naam advertentiecampagne |
| utm_content | Inhoud toevoegen |
| utm_term | Trefwoordtekst |
