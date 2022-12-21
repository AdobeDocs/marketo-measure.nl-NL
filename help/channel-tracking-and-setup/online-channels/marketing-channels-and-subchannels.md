---
unique-page-id: 18874682
description: Kanalen en subkanalen op de markt brengen - [!DNL Marketo Measure] - Productdocumentatie
title: Kanalen en subkanalen voor marketing
exl-id: fbe2a994-cf6d-439c-af96-a562216434cc
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 0%

---

# Kanalen en subkanalen voor marketing {#marketing-channels-and-subchannels}

## Doel {#purpose}

Om te bepalen wat een Kanaal en Subkanaal binnen zijn [!DNL Marketo Measure], hoe deze zich verhouden tot uw inhoud, het verschil tussen de twee classificaties en hoe deze worden gebruikt binnen de [!DNL Marketo Measure] app.

## Overzicht {#overview}

Marketingkanalen worden gebruikt om uw marketingactiviteiten te categoriseren (of &quot;emmer&quot;) voor een eenvoudige rapportage, zowel in de [!DNL Marketo Measure] ROI Dash en in uw CRM. [!DNL Marketo Measure] wordt geleverd met 12 uit de vakkanalen (die u kunt aanpassen/anders noemen om de overeenkomsten van uw organisatie te passen), evenals de capaciteit om de Kanalen van de Douane voor nog korrelige het filtreren verder tot stand te brengen.

Wanneer u een bezoeker aan één van uw pagina&#39;s van de Inhoud op uw plaats (of die Inhoud een Web-pagina, een Wit-document Download, een Pagina URL, enz.) ontvangt, zal die Lood &quot;gespeld&quot;in een Kanaal/Subkanaal worden gebaseerd op verscheidene parameters UTM die in URL worden gevonden:

* Normaal
* Bron
* Campagne
* Openingspagina
* Verwijzen naar website

Als u wilt aanpassen in welk segment uw leads worden geplaatst op basis van hun UTM-parameters, kunt u Kanaalregels gebruiken. Voor meer bij vestiging en het handhaven van uw Regels van het Kanaal, [klik hier](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md).

Leer hoe u uw [Onlinekanalen](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md) en [Offlinekanalen](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)en het verschil tussen beide.

**Marketingkanaal**

Het marketingkanaal is het breedste classificatieniveau en kan een groot aantal subkanalen bestrijken. U kunt dit het &quot;type&quot;van Subchannel overwegen dat uw lood uit komt. Voorbeelden van marketingkanalen zijn: **Betaald zoeken, biologisch zoeken, weergeven,** en **Betaald sociaal**. Het marketingkanaal komt meestal overeen met de parameterwaarde utm_medium die in de URL wordt gevonden.

**Subkanaal**

Subkanalen zijn het tweede stuk van de puzzel wanneer het knippen van uw inkomende Leads. Subkanalen vertellen het verhaal van precies _die_ Er is een herhaling van uw marketingkanaal gebruikt. In het kanaal voor betaalde sociale marketing hebt u mogelijk subkanalen voor **AdWords**, **BingAds**, **Facebook**, enz. Subkanaal beantwoordt gewoonlijk aan de utm_source parameterwaarde die in uw URL wordt gevonden.

## Voorbeeld van hoofdletters/kleine letters gebruiken {#use-case-example}

In het onderstaande diagram ziet u een voorbeeld van een marketingkanaal, subkanaal en inhoud op basis van een webpagina met de volgende URL:

* [http://info.bizible.com/intro-guide-b2b-marketing-attribution?utm_source=linkedin&amp;utm_medium=paidsocial](http://info.bizible.com/intro-guide-b2b-marketing-attribution?utm_source=linkedin&amp;utm_medium=paidsocial)*

In dit geval is de inhoud waartoe de gebruiker toegang probeert te krijgen de Intro Guide naar B2B Marketing Attribution. [!DNL Marketo Measure] analyseert u de URL die leidt naar deze inhoud met behulp van de kanaalregels die op deze org zijn ingesteld, en gebruikt u deze URL om naar het marketingkanaal &quot;Betaald sociaal&quot; en het subkanaal &quot;LinkedIn&quot; te &quot;emmer&quot;.

![](assets/1.jpg)

Andere voorbeelden...

**Marketingkanaal (gemiddeld)**

* PPC
* Betaald sociaal
* Organisch sociaal
* E-mail
* Gebeurtenissen en conferenties
* Organic Search/SEO
* PR
* Verwijzingsprogramma&#39;s

**Subkanaal (aanraakpuntbron)**

* Google AdWords
* BingAds
* Facebook-advertenties
* Adroll
* Dubbelklikken
* Capterra
* Drip Campaigns
* linkedIn-advertenties

**Inhoud (whitepapers, pagina-URL&#39;s, blogberichten)**

* www.adobe.com/blog1
* www.adobe.com/whitepaper
* www.adobe.com/sign-up-now
