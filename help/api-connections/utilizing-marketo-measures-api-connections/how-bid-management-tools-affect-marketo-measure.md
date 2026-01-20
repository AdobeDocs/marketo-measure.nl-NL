---
unique-page-id: 18874720
description: De invloed van Bodmanager-programma's op  [!DNL Marketo Measure]  -  [!DNL Marketo Measure]
title: De invloed van Bodmanager-programma's  [!DNL Marketo Measure]
exl-id: 67c00ad9-8b12-4238-8a1f-2d2f5ed04423
feature: APIs, Integration, UTM Parameters
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 0%

---

# De invloed van Bodmanager-programma&#39;s [!DNL Marketo Measure] {#how-bid-management-tools-affect-marketo-measure}

Leer hoe biedbeheerplatforms de mogelijkheid van [!DNL Marketo Measure] om AdWords en BingAds bij te houden beïnvloeden, samen met hoe u volgsjablonen met onze parameters instelt om ervoor te zorgen dat alles correct wordt bijgehouden.

Kenshoo en Marin zijn geweldige tools waarmee marketers hun advertentiecampagnes kunnen bijhouden, beheren en optimaliseren met verschillende zoekmachines. Als u wilt dat [!DNL Marketo Measure] -parameters aan deze advertentie-URL&#39;s worden toegevoegd, moet u een sjabloon voor bijhouden met de [!DNL Marketo Measure] -parameters instellen. Het is niet mogelijk om uw advertentieplatforms aan te sluiten op uw [!DNL Marketo Measure] -account en automatische codering in te schakelen, aangezien het [!DNL Marketo Measure] -tagsysteem hierdoor kan concurreren met het labelsysteem van Kenshoo/Marin. Hierdoor worden onze parameters gewijzigd en onjuist toegevoegd. Om dit te omzeilen, moeten sjablonen bijhouden met [!DNL Marketo Measure] -parameters worden ingesteld in Kenshoo en Marin.

## Voor [!DNL Adwords] accounts {#for-adwords-accounts}

Stel een volgsjabloon als volgt in:

* Klik op de tab **[!UICONTROL Campaigns]** .
* Klik op de koppeling **[!UICONTROL Shared library]** op de zijnavigatiebalk.
* Klik **opties URL**.
* Naast &quot;het Volgen malplaatje,&quot;klik **geeft** uit.
* Vul de URL in:

   * Als ALLE advertentie-URL&#39;s een &#39;?&#39; hebben in hen, gebruik deze URL:
      * `{lpurl}&_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`
   * Als GEEN van je advertentie-URL&#39;s een &#39;?&#39; heeft in hen, gebruik deze URL:
      * `{lpurl}?_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`


## Voor [!DNL Bing Ads] accounts {#for-bing-ads-accounts}

Stel een volgsjabloon als volgt in:

* Klik op de tab **[!UICONTROL Campaigns]** .
* Klik op de koppeling **[!UICONTROL Shared library]** op de zijnavigatiebalk.
* Klik **opties URL**.
* Naast &quot;het Volgen malplaatje,&quot;klik **geeft** uit.
* Vul de URL in:

   * Als ALLE advertentie-URL&#39;s een &#39;?&#39; hebben in hen, gebruik deze URL:
      * `{lpurl}&_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
   * Als GEEN van je advertentie-URL&#39;s een &#39;?&#39; heeft in hen, gebruik deze URL:
      * `{lpurl}?_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
