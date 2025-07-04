---
unique-page-id: 18874682
description: De Kanalen en Subkanalen van de marketing -  [!DNL Marketo Measure]
title: Kanalen en subkanalen voor marketing
exl-id: fbe2a994-cf6d-439c-af96-a562216434cc
feature: Channels
source-git-commit: 0ba036e7ebba77d870931704a59b19011e84271e
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 0%

---

# Kanalen en subkanalen voor marketing {#marketing-channels-and-subchannels}

## Doel {#purpose}

Om te bepalen wat een Kanaal en Subkanaal in [!DNL Marketo Measure] zijn, hoe zij op uw inhoud betrekking hebben, het verschil tussen de twee classificaties, en hoe zij binnen [!DNL Marketo Measure] worden gebruikt app.

## Overzicht {#overview}

Marketingkanalen worden gebruikt om uw marketingactiviteiten te categoriseren (of &quot;emmertje&quot;) voor een eenvoudige rapportage, zowel in het [!DNL Marketo Measure] ROI-streepje als in uw CRM. [!DNL Marketo Measure] wordt geleverd met 12 uit de vakkanalen (die u kunt aanpassen/anders noemen om de overeenkomsten van uw organisatie te passen), evenals de capaciteit om de Kanalen van de Douane voor nog korrelige het filtreren verder tot stand te brengen.

Wanneer u een bezoeker aan één van uw pagina&#39;s van de Inhoud op uw plaats (of die Inhoud een Web-pagina, een Wit-document Download, een Pagina URL, enz.) ontvangt, zal die Lood &quot;gespeld&quot;in een Kanaal/Subkanaal worden gebaseerd op verscheidene parameters UTM die in URL worden gevonden:

* Medium
* Bron
* Campaign
* Openingspagina
* Verwijzen naar website

Als u wilt aanpassen in welk segment uw leads worden geplaatst op basis van hun UTM-parameters, kunt u Kanaalregels gebruiken. Voor meer bij vestiging en het handhaven van uw Regels van het Kanaal, [ klik hier ](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md).

Leer hoe te opstelling uw [ Online Kanalen ](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md) en [ Offlinekanalen ](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md), evenals het verschil tussen hen.

**het Marketing Kanaal**

Het marketingkanaal is het breedste classificatieniveau en kan een groot aantal subkanalen bestrijken. U kunt dit het &quot;type&quot;van Subchannel overwegen dat uw lood uit komt. De voorbeelden van de Kanalen van de Marketing omvatten **Betaald Onderzoek, Organisch Onderzoek, Vertoning,** en **Betaalde Sociale**. Het marketingkanaal komt meestal overeen met de parameterwaarde utm_medium die in de URL wordt gevonden.

**Subchannel**

Subkanalen zijn het tweede stuk van de puzzel wanneer het knippen van uw inkomende Leads. Subkanalen vertellen het verhaal van precies _welke_ herhaling van uw Kanaal van de Marketing werd gebruikt. Bijvoorbeeld, binnen het Betaalde Sociale Marketing Kanaal, kunt u Subkanalen voor **hebben AdWords**, **BingAds**, **Facebook**, enz. Subkanaal beantwoordt gewoonlijk aan de utm_source parameterwaarde die in uw URL wordt gevonden.

## Voorbeeld van hoofdletters/kleine letters gebruiken {#use-case-example}

In het onderstaande diagram ziet u een voorbeeld van een marketingkanaal, subkanaal en inhoud op basis van een webpagina met de volgende URL:

`http://info.bizible.com/intro-guide-b2b-marketing-attribution?utm_source=linkedin&utm_medium=paidsocial`

In dit geval is de inhoud waartoe de gebruiker toegang probeert te krijgen de Intro Guide naar B2B Marketing Attribution. [!DNL Marketo Measure] analyseert de URL die naar deze inhoud leidt met behulp van de kanaalregels die op deze org zijn ingesteld, en gebruikt deze om deze lead te &quot;emmeren&quot; in het marketingkanaal &quot;Betaald sociaal&quot; en het subkanaal &quot;LinkedIn&quot;.

![](assets/1.jpg)

Andere voorbeelden...

**het Marketing Kanaal (Medium)**

* PPC
* Betaald sociaal
* Organisch sociaal
* E-mail
* Gebeurtenissen en conferenties
* Organic Search/SEO
* PR
* Verwijzingsprogramma&#39;s

**Subchannel (Touchpoint Source)**

* Google AdWords
* BingAds
* Facebook-advertenties
* Adroll
* Dubbelklikken
* Capterra
* Drip Campaigns
* LinkedIn Adds

**Inhoud (Witboeken, Pagina URLs, Blogberichten)**

* www.adobe.com/blog1
* www.adobe.com/whitepaper
* www.adobe.com/sign-up-now
