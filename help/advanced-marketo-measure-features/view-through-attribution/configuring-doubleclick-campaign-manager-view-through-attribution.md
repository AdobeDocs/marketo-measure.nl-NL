---
unique-page-id: 18874781
description: Dubbelklik op de Campagnebeheerweergave via Attributen - [!DNL Marketo Measure]
title: Dubbelklik op de weergave Campagnebeheer via Attributie
exl-id: 2cc6c2cd-afb7-4052-b18b-9ad0bf16a9fa
feature: Attribution
source-git-commit: 48962b999fdd16fe96d18708ec301e64a39bc76e
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 0%

---

# Dubbelklik op de weergave Campagnebeheer via Attributie {#configuring-doubleclick-campaign-manager-view-through-attribution}

## Weergave meten via kenmerk {#measuring-view-through-attribution}

>[!IMPORTANT]
>
>Vanwege privacyproblemen zijn cookies van derden op weg. Google Chrome kondigde in het derde kwartaal van 2024 de afleiding van cookies van derden aan, en markeert in feite het einde van deze vorm van bijhouden. Als gevolg hiervan worden Marketo Measure-functies die afhankelijk zijn van cookies van derden afgekeurd door de Adobe, met name Cross-Domain Tracking en View-through Attribution, die gebruikmaken van het Google/DoubleClick-imitatiecookie. Geen enkele andere functie van Marketo Measure wordt beïnvloed. Het cookie-gebruik van de eerste partij wordt ook niet beïnvloed. In het licht van het Google-schema is de verwachte vervaldatum voor de twee bovenstaande functies 16-01-2024. Verwante gegevens die vóór deze datum zijn verzameld, blijven beschikbaar voor klanten van de Adobe.

>[!NOTE]
>
>Als u het [!DNL Marketo Measure] en [!DNL DoubleClick Campaign Manager] integratie , we hebben een [API-verbinding](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md#how-to-connect-ad-platforms) zodat we details kunnen downloaden over de campagnes en creatieve projecten om advertenties op te lossen .

Meer granulair inzicht uit zicht krijgen door het volgen met [!DNL Doubleclick Campaign Manager], moet onze volgende pixel worden gevormd.

Voor meer informatie over de [!DNL Marketo Measure] Functionaliteit van Weergeven via kenmerk, zie [Veelgestelde vragen over Marketo Measure View through Attribution](/help/advanced-marketo-measure-features/view-through-attribution/marketo-measure-view-through-attribution-faq.md).

[!DNL Marketo Measure] wordt beschouwd als een gyback-tag omdat het een aanroep van derden via de DCM-ad-tag is. Piggyback-tags werken niet met afbeeldingstags, alleen iframe- of javascript-tags. Volgens DCM Support is dit de laatste tijd niet veranderd en is dit altijd het geval geweest. Standaardcodes zijn afgekeurd op 2 oktober 2017, maar hebben geen invloed op de mogelijkheid van [!DNL Marketo Measure] om de beelden te volgen.

Als u een bovenliggende en onderliggende hiërarchie in DCM gebruikt, moet de tag op alle niveaus worden toegepast om de indruk te volgen.

## De afbeeldingstag toevoegen {#how-to-add-the-image-tag}

Voeg de tag toe aan Doubleclick onder de instelling Advertiser en maak een Impression Event-tag.

1. Voeg de volgende code toe als een 1x1 afbeeldingspixel.

`https://cdn.bizibly.com/i?v=%eadv!&a=%eaid!&c=%ecid!&s=%esid!&p=%epid!&m=%m&n=%n`

1. Zodra het is toegevoegd, bevestig de afbakeningsapparaten als volgt in kaart worden gebracht. Deze instelling moet automatisch zijn wanneer de tag wordt toegepast:

   v = %eadv! [!DNL Expand] Adverteerder-id\
   a = %eaid! Advertentie-id uitbreiden\
   c = %ecid! Creatieve id uitbreiden\
   s = %esid! Site-id uitbreiden\
   p = %epid! Plaatsings-id uitbreiden\
   m = %m = Identieke macrocode\
   n = %n macro voor willekeurig getal

   ![](assets/1.png)

## Veelgestelde vragen {#faq}

**V: Is de tag image veilig?**

A: Ja. Het is geen JavaScript-tag, het is een afbeeldingstag.

**V: Welke machtigingen heeft de verbonden gebruiker nodig?**

A: fatrakes, foutrapportage, userinfo.email

**V: Hoe lang duurt het om uitgavengegevens te importeren?**

A: Tot 6 uur

**V: Hoe lang duurt het om gegevens te importeren?**

A: Tot 6 uur
