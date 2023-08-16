---
unique-page-id: 18874781
description: Dubbelklik op de Campagnebeheerweergave via Attributen - [!DNL Marketo Measure] - Productdocumentatie
title: Dubbelklik op de weergave Campagnebeheer via Attributie
exl-id: 2cc6c2cd-afb7-4052-b18b-9ad0bf16a9fa
feature: Attribution
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 0%

---

# Dubbelklik op de weergave Campagnebeheer via Attributie {#configuring-doubleclick-campaign-manager-view-through-attribution}

## Weergave meten via kenmerk {#measuring-view-through-attribution}

>[!NOTE]
>
>Als u de [!DNL Marketo Measure] en de integratie van de Manager van de Campagne van de Dubbelklik, vereisen wij een [API-verbinding](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md#how-to-connect-ad-platforms) zodat we details kunnen downloaden over de campagnes en creatieve projecten om advertenties op te lossen .

Om meer korrelig inzicht van mening door het volgen met de Manager van de Campagne van de Dubbelklik te krijgen, moet onze volgende pixel worden gevormd.

Gelieve [klik hier](/help/advanced-marketo-measure-features/view-through-attribution/marketo-measure-view-through-attribution-faq.md) voor meer informatie over de [!DNL Marketo Measure] Functionaliteit voor weergave door kenmerk.

[!DNL Marketo Measure] wordt beschouwd als een gyback-tag omdat het een aanroep van derden via de DCM-ad-tag is. Piggyback-tags werken niet met afbeeldingstags, alleen iframe- of javascript-tags. Volgens DCM Support is dit de laatste tijd niet veranderd en is dit altijd het geval geweest. Standaardcodes zijn afgekeurd op 2 oktober 2017, maar hebben geen invloed op de mogelijkheid van [!DNL Marketo Measure] om de beelden te volgen.

Als u een bovenliggende en onderliggende hiërarchie in DCM gebruikt, moet de tag op alle niveaus worden toegepast voor het bijhouden van de indruk.

## De afbeeldingstag toevoegen {#how-to-add-the-image-tag}

U voegt de tag toe aan Dubbleclick onder de instelling Advertiser en u wilt een Impression Event-tag maken.

1. Voeg de volgende code toe als een 1x1 afbeeldingspixel.

`https://cdn.bizibly.com/i?v=%eadv!&a=%eaid!&c=%ecid!&s=%esid!&p=%epid!&m=%m&n=%n`

1. Zodra het is toegevoegd, bevestig de afbakeningsapparaten als volgt in kaart worden gebracht. Deze instelling moet automatisch zijn wanneer de tag wordt toegepast:

   v = %eadv! Adverteerder-id uitbreiden\
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
