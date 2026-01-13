---
description: '[!DNL Marketo Measure] Parameters -  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] Parameters'
exl-id: d66b9864-0d7e-455a-ae20-cca555f4d8c8
feature: APIs, Integration, UTM Parameters
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 0%

---


# [!DNL Marketo Measure] Parameters {#marketo-measure-parameters}

## [!DNL Marketo Measure] Verklaarde parameters {#marketo-measure-parameters-explained}

[!DNL Marketo Measure] voegt aangepaste parameters aan uw advertenties toe in [!DNL Google] AdvertentieWords, Bing Ads and [!DNL Facebook] Ads om meer insight te bereiken van het gebruik van UTM&#39;s. [!DNL Marketo Measure] integreert met deze platforms om het grootste deel van het installatieproces te automatiseren. Als u Automatisch labelen kiest, voegt [!DNL Marketo Measure] de parameters ervan automatisch toe aan de URL&#39;s van uw advertenties. [!DNL Marketo Measure] downloadt ook automatisch uw marketingkosten van de platforms en laadt deze in de app [!DNL Marketo Measure] .

Voorbeeld van een URL zonder parameters:

`http://adobe.com/landing-page?myParam=foo`

Voorbeeld van een URL met [!DNL Marketo Measure] -parameters:

`http://adobe.com/landing-page?myParam=foo&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## Parameters Advertentiewoorden {#adwords-parameters}

* `_bk={keyword}`
   * Vertegenwoordigt het sleutelwoord de persoon die in het onderzoeksmotor wordt gebruikt.
   * Het lijkt op de UTM-parameter term.

* `_bt={creative}`
   * Vertegenwoordigt de creatieve id of naam.
   * Deze is vergelijkbaar met de parameter voor UTM-inhoud.

* `_bm={matchtype}`
   * Geeft aan hoe nauw het trefwoord is gevonden.
   * Trefwoordmatch-typen helpen u te bepalen welke zoekopdrachten uw advertentie activeren. U kunt bijvoorbeeld een brede overeenkomst gebruiken om uw advertentie voor een groot publiek weer te geven of u kunt een exacte overeenkomst gebruiken voor één in specifieke groepen klanten.
   * De drie typen overeenkomsten zijn: breed, vaag en exact.

>[!TIP]
>Voor meer informatie over gelijketypes, [&#x200B; is hier een relevant artikel AdWords &#x200B;](https://support.google.com/adwords/answer/2497836?hl=en){target="_blank"}.

* `_bn={network}`
   * Vertegenwoordigt het type van advertentienetwerk - [&#x200B; vertoning of onderzoek &#x200B;](https://support.google.com/adwords/answer/1752334?hl=en){target="_blank"}.
   * Dit lijkt op de UTM Source-parameter.

* `_bg={adgroupID}`
   * Vertegenwoordigt identiteitskaart van de Advertentiegroep de advertentie tot behoort

>[!NOTE]
>Redirect URL-parameters worden niet ondersteund.

## Parameters voor bindingsadvertenties {#bing-ads-parameters}

* `_bt={adid}`
* `utm_medium=cpc`
* `utm_source=bing`
* `utm_term={keyword}`

## Facebook-parameters {#facebook-parameters}

* `_bf ={creative}`
   * Dit staat voor de creatieve id of naam
