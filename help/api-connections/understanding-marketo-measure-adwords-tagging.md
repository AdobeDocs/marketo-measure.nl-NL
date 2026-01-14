---
description: Begrijpend  [!DNL Marketo Measure]  AdWords die begeleiding voor de gebruikers van Marketo Measure etiketteren
title: Begrijpend  [!DNL Marketo Measure]  AdWords Tagging
exl-id: c6658766-d3a8-46ed-b2d2-826eb61ce269
feature: APIs, Integration, UTM Parameters
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 0%

---

# Werken met [!DNL Marketo Measure] AdwWords-tags {#understanding-marketo-measure-adwords-tagging}

Als u advertenties wilt bijhouden op een zeer granulair niveau, moeten de URL&#39;s voor het doel toevoegen uniek zijn. Hiervoor voegt [!DNL Marketo Measure] automatisch traceerparameters toe aan de URL&#39;s van het advertentiedoel van [!DNL AdWords] . Laten we een voorbeeld hieronder bekijken.

De volgende URL zal geen korrelige gegevens verstrekken:

* `http://example.com/landing-page?myParam=foo`

Dezelfde URL levert echter korrelige gegevens vanwege de parameters [!DNL Marketo Measure] :

* `http://example.com/landing-page?myParam=foo&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## Hoe [!DNL Marketo Measure] Automatisch labelen werkt {#how-marketo-measure-auto-tagging-works}

**als [!DNL Marketo Measure] een Volgend Malplaatje vindt:**

* [!DNL Marketo Measure] voegt de parameters ervan toe aan de sjabloon voor reeksspatiëring.
* Als een doorverwijzing van een derde wordt gevonden in een volgsjabloon zoals Kenshoo of Marin, voert [!DNL Marketo Measure] geen actie uit. In plaats daarvan, moet u [ parameters aan het derdehulpmiddel in uw rekening  [!DNL Marketo Measure]  toevoegen.](/help/api-connections/how-bid-management-tools-affect-marketo-measure.md){target="_blank"}

Als er echter geen volgsjabloon wordt gevonden, zal [!DNL Marketo Measure]:

* Scan alle URL&#39;s van het doel van de advertentie naar onze [!DNL Marketo Measure] -parameters.
* Indien gevonden, ben je goed om te gaan.
* Als deze optie niet wordt gevonden, voegt [!DNL Marketo Measure] de parameters ervan toe aan het einde van de URL&#39;s voor het toevoegen van doelen. Voor nieuwe advertenties voegt [!DNL Marketo Measure] de parameters ervan binnen twee uur na het maken toe aan de URL voor het toevoegen van bestemming.
* Het is belangrijk dat u een sjabloon voor bijhouden hebt voordat u automatische labeling inschakelt, zodat [!DNL Marketo Measure] eraan kan worden gekoppeld en een advertentiehistorie niet opnieuw kan worden ingesteld.

[!DNL Marketo Measure] raadt u aan een sjabloon voor reeksspatiëring op accountniveau, op campagnereniveau of op groepsniveau toevoegen te gebruiken, omdat hiermee parameters kunnen worden toegevoegd en afgetrokken voor alle advertenties zonder dat het risico bestaat dat de advertentiehistorie wordt onderbroken of verwijderd.

## Sjablonen bijhouden {#tracking-templates}

Zoals uitgelegd door [!DNL Google AdWords] is een sjabloon voor bijhouden de URL die wordt gebruikt om een bestemmingspagina te bereiken. De verzamelde trackinggegevens worden gebruikt om uw advertentieverkeer te begrijpen. [ klik hier ](https://support.google.com/adwords/answer/7197008?hl=en){target="_blank"} voor meer informatie van Google.

[!DNL Marketo Measure] raadt u aan een sjabloon voor het bijhouden van accounts, campagnes of groepen toevoegen te gebruiken, omdat hiermee parameters voor alle advertenties kunnen worden toegevoegd en afgetrokken zonder dat het risico bestaat dat de advertentie wordt onderbroken of verwijderd.

Er zijn twee volgsjablonen die [!DNL Marketo Measure] aanbeveelt. Gebruik het volgende om te bepalen welke versie geschikt is voor u:

* Als al je advertentie-URL&#39;s een &#39;?&#39; hebben in hen, gebruik deze URL:

`{lpurl}&_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

* Als geen van je advertentie-URL&#39;s een &#39;?&#39; heeft in hen, gebruik deze URL:

`{lpurl}?_bt={creative}&_bk={keyword}&_bm={matchtype}&_bn={network}&_bg={adgroupid}`

## Een sjabloon voor bijhouden instellen op accountniveau {#setting-up-a-tracking-template-at-the-account-level}

1. Meld u aan bij uw [!DNL Google AdWords] -account.

1. Klik op **[!UICONTROL All campaigns]** en vervolgens op **[!UICONTROL Settings]** in het uitbreidende venster.

   ![](assets/utilizing-connections-13.png)

1. Klik op **[!UICONTROL Account Settings]** boven en vervolgens op **[!UICONTROL Tracking Template]** . Voer de [!DNL Marketo Measure] volgsjabloon in.

   ![](assets/bizible-guide-1.png)

1. Klik op **[!UICONTROL Save]**.

## Een sjabloon voor bijhouden instellen op campagneniveau {#setting-up-a-tracking-template-at-the-campaign-level}

1. Klik op **[!UICONTROL All campaigns]** en vervolgens op **[!UICONTROL Campaigns]** in het uitbreidende venster.

   ![](assets/utilizing-connections-12.png)

1. Selecteer alle toepasselijke campagnes of **[!UICONTROL Select All]**, klik **[!UICONTROL Edit]**, en klik dan **[!UICONTROL Change Tracking Templates]**.

   ![](assets/five-five-1.png)

1. Voer de [!DNL Marketo Measure] Sjabloon bijhouden in en klik op **[!UICONTROL Apply]** .

## Een volgsjabloon instellen op advertentiegroepniveau: {#setting-up-a-tracking-template-at-the-ad-group-level}

1. Klik op **[!UICONTROL All campaigns]** en vervolgens op **[!UICONTROL Ad Groups]** in het uitbreidende venster.

   ![](assets/four-four-1.png)

1. Selecteer alle toepasselijke Advertentiegroepen of selecteer allen, klik **[!UICONTROL Edit]** en klik dan **[!UICONTROL Change Tracking Templates]**.

1. Voer de [!DNL Marketo Measure] Sjabloon bijhouden in en klik op **[!UICONTROL Apply]** .

   ![](assets/one-one-1.png)

## Veelgestelde vragen {#faq}

**Q: Welke toestemmingen vereist de verbonden gebruiker?**

A: userinfo.email

**Q: Hoe lang kan het duren om uitgavengegevens in te voeren?**

A: 6 uur

**Q: Hoe lang kan het aan invoer en gegevens vergen?**

A: 4 uur

**Q: Voor Dynamische Advertenties van het Onderzoek, kunnen wij de combinatie van titel, beschrijving, enz. volgen, in creatief die werd gediend?**

A: We kunnen geen individuele creatieve details ophalen voor dynamische zoekopdrachten, maar als automatisering is ingeschakeld, krijgen we nog steeds de creatieve id en kenmerkinkomsten.

>[!NOTE]
>
>Als de wijzigingen eenmaal zijn aangebracht, bent u klaar. Voel vrij om uit te reiken aan [ de Steun van Marketo ](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} als er om het even welke vragen tijdens opstelling zijn.

[ klik hier ](https://support.google.com/adwords/answer/6076199?hl=en#tracking){target="_blank"} voor instructies van Google bij het creëren van de Malplaatjes van het Rekening-Vlakke Volgen.
