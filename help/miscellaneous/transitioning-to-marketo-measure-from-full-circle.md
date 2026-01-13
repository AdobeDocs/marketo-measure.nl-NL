---
description: Het overbrengen aan  [!DNL Marketo Measure]  van Volledige Cirkel -  [!DNL Marketo Measure]
title: Overgangen aan  [!DNL Marketo Measure]  van Volledige Cirkel
exl-id: fd471771-33e2-413a-b155-02ba6e32e10c
feature: Attribution, Fundamentals
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 0%

---


# Overschakelen naar [!DNL Marketo Measure] vanuit volledige cirkel {#transitioning-to-marketo-measure-from-full-circle}

Wilt u de overgang van Volledige cirkel naar [!DNL Marketo Measure] maken? Je bent niet alleen. Hier zijn de grootste overwegingen in mening en de lessen die wij van andere klanten hebben geleerd die de schakelaar hebben gemaakt.

## Campagne-based Tracking vs. multi-Source Tracking {#campaign-based-tracking-vs-multi-source-tracking}

Alle interacties in [!UICONTROL Full Circle] worden bijgehouden via het lidmaatschap van de CRM-campagne. Met [!DNL Marketo Measure] wordt de aankoopreis gecompileerd via een combinatie van onze JavaScript-, CRM-campagne- en CRM-activiteitengegevens. Het kan lastig zijn om de mentale verschuiving van &quot;alle interactie moet worden bijgehouden in een CRM-campagne om ervoor te zorgen dat onze toewijzingsrapportage functioneert&quot; naar &quot;alleen deze subset van interacties moet worden bijgehouden in een CRM-campagne voor onze attributie-rapportage naar functie&quot;.

Over het algemeen wordt hier uitgelegd hoe [!DNL Marketo Measure] aanraakpuntrecords maakt voor de belangrijkste typen interactie:

* Formuliervullingen op uw sites: [!DNL Marketo Measure] JavaScript
* Paginaweergaven op uw sites: alleen gemaakt door [!DNL Marketo Measure] JavaScript als in deze paginaweergave een aangewezen CRM-mijlpaal werd gebruikt (bijvoorbeeld Aanbieding of Opportunity maken)
* Offline interacties zoals conferenties of handelsvertegenwoordigingen: lidmaatschap van CRM-campagne
* Digitale interacties die overal op internet plaatsvinden en niet uw site zijn (zoals een webinar die wordt gehost op een externe site die een upload met een lijst genereert): lidmaatschap voor CRM-campagne
* Interacties met het verkoopteam: CRM-activiteitsgegevens

Als u vertrouwd bent met het campagnebeheer van CRM en verkiest bestaande processen op zijn plaats te houden, is dat prima. Het doet [!DNL Marketo Measure] geen pijn om alle interacties in CRM-campagnes te blijven volgen. U kunt logica ontwerpen die slechts aanraakpunten van een gewenste ondergroep van campagnes creeert om aanraakpuntduplicatie te vermijden.

## Zichtbaarheid versus kenmerk {#visibility-vs-attribution}

Met de meeste Volledige montages van de Cirkel, ziet u elke interactie een persoon met uw marketing of verkoopinspanningen heeft. Paginaweergaven, herhaalde paginabezoeken, lidmaatschap van drievoudige campagnes—Volledige cirkel heeft alle oppervlakken van deze campagnes. Als u een pagina 300 keer bekijkt, leidt de Volledige Cirkel tot 300 dubbele campagnes en geeft u een lidmaatschap in elk van hen. [!DNL Marketo Measure] niet, en dat was een bewuste ontwerpbeslissing van onze kant.

Met [!DNL Marketo Measure] krijgt u een attributieverhaal dat betekenisvolle interacties bevat en op de juiste wijze gewicht onder de meest onzichtbare aanraakpunten verdeelt. Het [!DNL Marketo Measure] -framework biedt bijvoorbeeld geen routinepunten voor paginaweergaven (zonder formuliervullingen). Een standalone paginamening zal waarschijnlijk geen invloed op het drijven van een koopreis vooruit hebben, maar wij creëren een aanraakpunt als het de meest recente interactie vóór een aangewezen mijlpaal van CRM (zoals Lood of het Creëren van de Kans) is. We willen jullie niet alles tonen. We willen jullie laten zien wat belangrijk is, vanuit een attributiestandpunt.

Werk met uw [!DNL Marketo Measure] rep om de juiste verwachtingen in te stellen ten aanzien van de gegevens die niet meer beschikbaar zijn voor uw team.

## Pre-[!DNL Marketo Measure] gegevens {#pre-marketo-measure-data}

De standaardaanbeveling is om te beginnen met het rapporteren van en het verzamelen van gegevens vanaf de dag dat u de [!DNL Marketo Measure] JavaScript voorwaarts hebt geïmplementeerd. Dit gaat twee keer zo voor voormalige klanten van Full Circle. Denk aan de twee bovenstaande secties: U bent gewend om een hogere hoeveelheid gegevens te zien, en u bent gewend aan al die gegevens die uit het campagnecolleid van CRM komen. Als u bepaalde of alle gegevens van vóór de [!DNL Marketo Measure] -implementatie wilt opnemen, vergelijkt u geen appels met appels op de JavaScript-implementatiedatum.

Dat gezegd hebbende, begrijpen wij zeker dat vele klanten deze historische gegevens nodig hebben; vooral als u een langere verkoopcyclus (groter dan 90 dagen) hebt, kunt u [!DNL Marketo Measure] zicht in pre [!DNL Marketo Measure] gegevens willen geven. Bespreek dit zorgvuldig met uw [!DNL Marketo Measure] rep en houd er altijd rekening mee dat scheeftrekken over de implementatiedatum kan leiden tot verbeteringen of een vermindering van de kanaalprestaties of -betrokkenheid, en andere mogelijk onjuiste conclusies.

## Samenvatting {#in-summary}

U bent in goed bedrijf, en wij hebben vele andere klanten geholpen deze veranderingen te behandelen. Werk met uw [!DNL Marketo Measure] rep om de bovenstaande effecten en eventuele andere problemen te begrijpen.
