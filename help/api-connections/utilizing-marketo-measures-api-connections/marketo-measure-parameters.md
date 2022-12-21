---
unique-page-id: 18874608
description: "[!DNL Marketo Measure] Parameters - [!DNL Marketo Measure] - Productdocumentatie"
title: "[!DNL Marketo Measure] Parameters"
exl-id: d66b9864-0d7e-455a-ae20-cca555f4d8c8
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 0%

---

# [!DNL Marketo Measure] Parameters {#marketo-measure-parameters}

## [!DNL Marketo Measure] Verklaarde parameters {#marketo-measure-parameters-explained}

Om meer inzicht te krijgen in het gebruik van UTM&#39;s, [!DNL Marketo Measure] voegt aangepaste parameters toe aan uw advertenties in [!DNL Google] Advertentievoorden, Bing Ads en [!DNL Facebook] Advertenties. [!DNL Marketo Measure] integreert met deze platforms om het grootste deel van het installatieproces te automatiseren. Als u automatische labeling wilt gebruiken, [!DNL Marketo Measure] voegt de parameters automatisch toe aan de URL&#39;s van uw advertenties. [!DNL Marketo Measure] worden uw marketingkosten ook automatisch gedownload van de platforms en geladen in de [!DNL Marketo Measure] app.

Voorbeeld van een URL zonder parameters:

`http://adobe.com/landing-page?myParam=foo`

Voorbeeld van een URL met [!DNL Marketo Measure] parameters:

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
   * De drie typen overeenkomsten zijn: breed, vaag en precies.

>[!NOTE]
>
>Voor meer informatie over gelijke types, [Hier is een relevant artikel van AdWords](https://support.google.com/adwords/answer/2497836?hl=en){target=&quot;_blank&quot;}.

* `_bn={network}`
   * Vertegenwoordigt het type van advertentienetwerk - [weergeven of zoeken](https://support.google.com/adwords/answer/1752334?hl=en){target=&quot;_blank&quot;}.
   * Dit is vergelijkbaar met de parameter UTM Source.

* `_bg={adgroupID}`
   * Vertegenwoordigt identiteitskaart van de Advertentiegroep de advertentie tot behoort

## Parameters voor bindingsadvertenties {#bing-ads-parameters}

* `_bt={adid}`
* `utm_medium=cpc`
* `utm_source=bing`
* `utm_term={keyword}`

## Facebook-parameters {#facebook-parameters}

* `_bf ={creative}`
   * Dit staat voor de creatieve id of naam
