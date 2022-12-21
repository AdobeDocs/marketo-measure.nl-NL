---
unique-page-id: 18874720
description: De invloed van Bodmanager-programma's [!DNL Marketo Measure] - [!DNL Marketo Measure] - Productdocumentatie
title: De invloed van Bodmanager-programma's [!DNL Marketo Measure]
exl-id: 67c00ad9-8b12-4238-8a1f-2d2f5ed04423
source-git-commit: 65e7f8bc198ceba2f873ded23c94601080ad0546
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# De invloed van Bodmanager-programma&#39;s [!DNL Marketo Measure] {#how-bid-management-tools-affect-marketo-measure}

Meer informatie over de invloed van biedbeheerplatforms op [!DNL Marketo Measure] de mogelijkheid om AdWords en BingAds bij te houden, samen met de manier waarop u volgsjablonen instelt met onze parameters om ervoor te zorgen dat alles correct wordt bijgehouden.

Kenshoo en Marin zijn geweldige tools waarmee marketers hun advertentiecampagnes kunnen bijhouden, beheren en optimaliseren met verschillende zoekprogramma&#39;s. Om [!DNL Marketo Measure] parameters die aan deze advertentie-URL&#39;s moeten worden toegevoegd, moet u een volgsjabloon instellen met onze [!DNL Marketo Measure] parameters. Het is niet mogelijk om uw advertentieplatforms aan te sluiten op uw [!DNL Marketo Measure] account en autotageren inschakelen, zoals de oorzaak is van de [!DNL Marketo Measure] codering van het systeem om te concurreren met het merksysteem van Kenshoo/Marin. Hierdoor worden onze parameters gewijzigd en onjuist toegevoegd. Dit omzeilen door sjablonen te volgen met [!DNL Marketo Measure] in Kenshoo en Marin moeten parameters worden vastgesteld.

## Voor [!DNL Adwords] Accounts {#for-adwords-accounts}

Stel een volgsjabloon als volgt in:

* Klik op de knop **[!UICONTROL Campaigns]** tab.
* Klik op de knop **[!UICONTROL Shared library]** in de zijnavigatiebalk.
* Klikken **URL-opties**.
* Klik naast Sjabloon bijhouden op **Bewerken**.
* Vul de URL in:

   * Als ALLE advertentie-URL&#39;s een &#39;?&#39; hebben in hen, gebruik deze URL:
      * `{lpurl}&_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`
   * Als GEEN van je advertentie-URL&#39;s een &#39;?&#39; heeft in hen, gebruik deze URL:
      * `{lpurl}?_bk={keyword}&_bt={creative}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`


## Voor [!DNL Bing Ads] Accounts {#for-bing-ads-accounts}

Stel een volgsjabloon als volgt in:

* Klik op de knop **[!UICONTROL Campaigns]** tab.
* Klik op de knop **[!UICONTROL Shared library]** in de zijnavigatiebalk.
* Klikken **URL-opties**.
* Klik naast Sjabloon bijhouden op **Bewerken**.
* Vul de URL in:

   * Als ALLE advertentie-URL&#39;s een &#39;?&#39; hebben in hen, gebruik deze URL:
      * `{lpurl}&_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
   * Als GEEN van je advertentie-URL&#39;s een &#39;?&#39; heeft in hen, gebruik deze URL:
      * `{lpurl}?_bt={adid}&utm_term={keyword}&utm_source=Bing_Yahoo&utm_medium=CPC`
