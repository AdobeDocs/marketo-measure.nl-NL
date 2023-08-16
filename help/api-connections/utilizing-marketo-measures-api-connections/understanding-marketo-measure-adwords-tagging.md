---
unique-page-id: 18874678
description: Begrijpen [!DNL Marketo Measure] Advertentietags - [!DNL Marketo Measure] - Productdocumentatie
title: Begrijpen [!DNL Marketo Measure] Advertentietags
exl-id: c6658766-d3a8-46ed-b2d2-826eb61ce269
feature: APIs, Integration, UTM Parameters
source-git-commit: 3bad77a72c0dea6caf0daadbb594f10f791af715
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 0%

---

# Begrijpen [!DNL Marketo Measure] Advertentietags {#understanding-marketo-measure-adwords-tagging}

Als u advertenties wilt bijhouden op een zeer granulair niveau, moeten de URL&#39;s voor het doel toevoegen uniek zijn. Om dit te bereiken, [!DNL Marketo Measure] automatisch bijhouden voegt volgende parameters toe aan de URL&#39;s van het doel van de advertentie [!DNL AdWords] advertenties. Laten we een voorbeeld hieronder bekijken.

De volgende URL zal geen korrelige gegevens verstrekken:

* `http://example.com/landing-page?myParam=foo`

Dezelfde URL levert echter korrelige gegevens vanwege de [!DNL Marketo Measure] parameters:

* `http://example.com/landing-page?myParam=foo&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## Hoe [!DNL Marketo Measure] Automatisch labelen werkt {#how-marketo-measure-auto-tagging-works}

**Indien [!DNL Marketo Measure] zoekt een volgsjabloon:**

* [!DNL Marketo Measure] voegt de parameters ervan toe aan het volgsjabloon.
* Als een derde wordt gevonden omleiding in een het Volgen Malplaatje zoals Kenshoo of Marin, [!DNL Marketo Measure] geen actie ondernemen. In plaats daarvan moet u [toevoegen [!DNL Marketo Measure] parameters voor het hulpprogramma van derden in uw account](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md){target="_blank"}.

Als er echter geen volgsjabloon wordt gevonden, [!DNL Marketo Measure] zal:

* Scan alle URL&#39;s van de advertentie-bestemming naar onze [!DNL Marketo Measure] Parameters.
* Als je gevonden wordt, ben je goed om te gaan.
* Indien niet gevonden, [!DNL Marketo Measure] voegt de parameters toe aan het einde van de URL&#39;s voor het toevoegen van doelen. Voor nieuwe advertenties: [!DNL Marketo Measure] voegt de parameters binnen twee uur na het maken toe aan de URL voor het toevoegen van de bestemming.
* Het is belangrijk dat u een sjabloon voor bijhouden hebt voordat u automatische labeling inschakelt, zodat [!DNL Marketo Measure] kan eraan worden gekoppeld en voorkomen dat een advertentiehistorie opnieuw wordt ingesteld.

[!DNL Marketo Measure] Het verdient aanbeveling om een sjabloon voor reeksspatiëring op accountniveau, op campagnereniveau of op groepsniveau toevoegen te gebruiken, omdat hiermee parameters voor alle advertenties kunnen worden toegevoegd en afgetrokken zonder dat het risico bestaat dat de advertentie wordt onderbroken of verwijderd.

## Sjablonen bijhouden {#tracking-templates}

Zoals uiteengezet in [!DNL Google AdWords], is een volgsjabloon de URL die wordt gebruikt om een landingspagina te bereiken. De verzamelde trackinggegevens worden gebruikt om uw advertentieverkeer te begrijpen. [Klik hier](https://support.google.com/adwords/answer/7197008?hl=en){target="_blank"} voor meer informatie van Google.

[!DNL Marketo Measure] Het wordt aanbevolen een sjabloon voor het bijhouden van accounts, campagnes of groepen toevoegen te gebruiken, omdat hiermee parameters voor alle advertenties kunnen worden toegevoegd en afgetrokken zonder het risico van onderbrekingen of verwijderingen in de advertentie.

Er zijn twee volgsjablonen [!DNL Marketo Measure] raadt u aan deze functie te gebruiken. Gebruik het volgende om te bepalen welke versie geschikt is voor u:

* Als al je advertentie-URL&#39;s een &#39;?&#39; hebben in hen, gebruik deze URL:

`{lpurl}&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

* Als geen van je advertentie-URL&#39;s een &#39;?&#39; heeft in hen, gebruik deze URL:

`{lpurl}?_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## Een sjabloon voor bijhouden instellen op accountniveau {#setting-up-a-tracking-template-at-the-account-level}

1. Aanmelden bij uw [!DNL Google AdWords] Account.

1. Klikken **[!UICONTROL All campaigns]** en vervolgens **[!UICONTROL Settings]** in het uitbreidende venster.

   ![](assets/1.png)

1. Klikken **[!UICONTROL Account Settings]** boven en vervolgens **[!UICONTROL Tracking Template]**. Voer de [!DNL Marketo Measure] Sjabloon bijhouden.

   ![](assets/2-1.png)

1. Klik op **[!UICONTROL Save]**.

## Een sjabloon voor bijhouden instellen op campagneniveau {#setting-up-a-tracking-template-at-the-campaign-level}

1. Klikken **[!UICONTROL All campaigns]** en vervolgens **[!UICONTROL Campaigns]** in het uitbreidende venster.

   ![](assets/3.png)

1. Selecteer alle toepasselijke campagnes of **[!UICONTROL Select All]**, klikt u op **[!UICONTROL Edit]** en klik vervolgens op **[!UICONTROL Change Tracking Templates]**.

   ![](assets/4-1.png)

1. Voer de [!DNL Marketo Measure] Sjabloon bijhouden en klik op **[!UICONTROL Apply]**.

## Een volgsjabloon instellen op advertentiegroepniveau: {#setting-up-a-tracking-template-at-the-ad-group-level}

1. Klikken **[!UICONTROL All campaigns]** en vervolgens **[!UICONTROL Ad Groups]** in het uitbreidende venster.

   ![](assets/5-1.png)

1. Selecteer alle toepasselijke Advertentiegroepen of selecteer allen, klik **[!UICONTROL Edit]** en klik vervolgens op **[!UICONTROL Change Tracking Templates]**.

1. Voer de [!DNL Marketo Measure] Sjabloon bijhouden en klik op **[!UICONTROL Apply]**.

   ![](assets/6-1.png)

## Veelgestelde vragen {#faq}

**V: Welke machtigingen heeft de verbonden gebruiker nodig?**

A: userinfo.email

**V: Hoe lang duurt het om uitgavengegevens te importeren?**

A: 6 uur

**V: Hoe lang duurt het om gegevens te importeren?**

A: 4 uur

**V: Kunnen we voor Dynamic Search Ads de combinatie van kop, beschrijving, enzovoort volgen in de creatieve functies die werden aangeboden?**

A: We kunnen geen individuele creatieve details ophalen voor dynamische zoekopdrachten, maar als automatisering is ingeschakeld, krijgen we nog steeds de creatieve id en kenmerkinkomsten.

>[!NOTE]
>
>Als de wijzigingen eenmaal zijn aangebracht, bent u klaar. Voel u vrij om uit te reiken tot [Marketo-ondersteuning](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} als er vragen zijn tijdens de installatie.

[Klik hier](https://support.google.com/adwords/answer/6076199?hl=en#tracking){target="_blank"} voor instructies van Google over het maken van trackingsjablonen op accountniveau.
