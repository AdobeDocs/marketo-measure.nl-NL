---
description: Dubbelklik op de Weergave Campagnebeheer via kenmerkrichtlijnen voor Marketo Measure-gebruikers
title: Dubbelklik op de weergave Campagnebeheer via Attributie
exl-id: 2cc6c2cd-afb7-4052-b18b-9ad0bf16a9fa
feature: Attribution
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 0%

---

# Dubbelklik op de weergave Campagnebeheer via Attributie {#configuring-doubleclick-campaign-manager-view-through-attribution}

## Weergave meten via kenmerk {#measuring-view-through-attribution}

>[!IMPORTANT]
>
>Vanwege privacyproblemen zijn cookies van derden op weg. Google Chrome kondigde aan dat de cookies van derden in het derde kwartaal van 2024 zijn vervangen. Dit betekent dat deze vorm van bijhouden is geëindigd. Als gevolg hiervan is Adobe bezig Marketo Measure-functies af te schaffen die afhankelijk zijn van cookies van derden, met name Cross-Domain Tracking and View-through Attribution, die gebruikmaken van het Google/DoubleClick-imitatiecookie. Geen enkele andere functie van Marketo Measure wordt beïnvloed. Het cookie-gebruik van de eerste partij wordt ook niet beïnvloed. In het licht van het Google-schema is de verwachte vervaldatum voor de twee bovenstaande functies 16-01-2024. Gerelateerde gegevens die vóór deze datum zijn verzameld, blijven beschikbaar voor Adobe-klanten.

>[!NOTE]
>
>Als u [!DNL Marketo Measure] en [!DNL DoubleClick Campaign Manager] integratie gebruikt, vereisen wij een [ API verbinding ](/help/api-connections/integrated-ad-platforms.md) zodat kunnen wij details van de campagnes en de creatieven downloaden om de advertenties op te lossen.

Als u wilt beginnen met het verkrijgen van meer korrelige insight door het bijhouden van de gegevens met [!DNL Doubleclick Campaign Manager] , moet de volgende pixel worden geconfigureerd.

Voor meer informatie over de [!DNL Marketo Measure] Mening door de functionaliteit van de Attributie, verwijs naar [ Mening van Marketo Measure door Veelgestelde vragen van de Attributie ](/help/channel-tracking-and-setup/marketo-measure-view-through-attribution-faq.md).

[!DNL Marketo Measure] wordt beschouwd als een gyback-tag omdat het een aanroep van derden via de DCM-ad-tag is. Piggyback-tags werken niet met afbeeldingstags, alleen iframe- of javascript-tags. Volgens DCM Support is dit de laatste tijd niet veranderd en is dit altijd het geval geweest. Standaardcodes zijn afgekeurd op 2 oktober 2017, maar hebben geen invloed op de mogelijkheid van [!DNL Marketo Measure] om de afbeeldingen bij te houden.

Als u een bovenliggende en onderliggende hiërarchie in DCM gebruikt, moet de tag op alle niveaus worden toegepast om de indruk te volgen.

## De afbeeldingstag toevoegen {#how-to-add-the-image-tag}

Voeg de tag toe aan Doubleclick onder de instelling Advertiser en maak een Impression Event-tag.

1. Voeg de volgende code toe als een 1x1 afbeeldingspixel.

`https://cdn.bizibly.com/i?v=%eadv!&a=%eaid!&c=%ecid!&s=%esid!&p=%epid!&m=%m&n=%n`

1. Zodra het is toegevoegd, bevestig de afbakeningsapparaten als volgt in kaart worden gebracht. Deze instelling moet automatisch zijn wanneer de tag wordt toegepast:

   v = %eadv! [!DNL Expand] Advertiser-id\
   a = %eaid! Advertentie-id uitbreiden\
   c = %ecid! Creative-id uitbreiden\
   s = %esid! Site-id uitbreiden\
   p = %epid! Plaatsings-id uitbreiden\
   m = %m = Identieke macrocode\
   n = %n macro voor willekeurig getal

   ![ n = %n de Willekeurige Macro van het Aantal ](assets/view-attribution-1.png)

## Veelgestelde vragen {#faq}

**Q: Is de beeldmarkering veilig?**

A: Ja. Het is geen JavaScript-tag, het is een afbeeldingstag.

**Q: Welke toestemmingen vereist de verbonden gebruiker?**

A: fatrakes, foutrapportage, userinfo.email

**Q: Hoe lang kan het duren om uitgavengegevens in te voeren?**

A: Tot 6 uur

**Q: Hoe lang kan het aan invoer en gegevens vergen?**

A: Tot 6 uur
