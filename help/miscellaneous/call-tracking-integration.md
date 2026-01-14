---
description: De leidraad van de Integratie van het Volgen van de vraag voor de gebruikers van Marketo Measure
title: Integratie van het bijhouden van oproepen
exl-id: bc35a789-e056-4456-9038-306ed34c2a8e
feature: Tracking, Integration
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 0%

---

# Integratie van het bijhouden van oproepen {#call-tracking-integration}

Onze integratie met [!DNL CallTrackingMetrics] is bedoeld om een Webzitting met een telefoongesprek samen te voegen. Een telefoongesprek wordt behandeld als een formulier dat wordt verzonden naar [!DNL Marketo Measure] . Het geeft krediet aan een Webzitting die anders slechts als Webbezoek zou worden beschouwd omdat er geen daadwerkelijke vormvoorlegging was geweest.

## Vraag die Verklaarde het Volgen {#call-tracking-explained}

&#39;Call Tracking&#39; in de algemene zin is een product van bedrijven zoals [!DNL CallTrackingMetrics] , [!DNL DiaglogTech] , [!DNL Invoca] of [!DNL CallRail] , om er een paar te noemen. De unieke telefoonaantallen worden getoond aan gebruikers die op de verschillende marketing kanalen of de campagnes worden gebaseerd die zij uit komen. Op deze manier kunnen marketeers zien hoe die kanalen of campagnes presteren.

![](assets/other-resources-6.png)

## Voor en Na {#before-and-after}

Bekijk het stroomschema hieronder om te zien hoe [!DNL Marketo Measure] gebruikte om telefoongesprekken zonder een integratie met CallTrackingMetrics te behandelen. Het telefoongesprek dat plaatsvond, werd niet bijgehouden, dus het werd gezien als een Webzitting en geen touchpoint werd gecreeerd voor het. Pas bij het volgende bezoek heeft de gebruiker een formulier ingevuld dat uiteindelijk door een aanraakpunt werd ingevuld.

Met de integratie, kunt u zien dat de Webzitting eigenlijk aan een telefoongesprek werd gebonden. De volgende invulling van het formulier wordt dan een PostLC-aanraking en wordt nog steeds bijgehouden tijdens de reis.

![](assets/other-resources-4.png)

## Hoe het werkt {#how-it-works}

CallTrackingMetrics moet wat ontwikkelingswerk op hun eind doen opdat dit werkt. Met de JavaScript die zij op uw plaats plaatsen, kan CallTrackingMetrics `_biz_uid` van het [!DNL Marketo Measure] koekje pakken. Dit &quot;BizibleId&quot;wordt dan opgeslagen door CallTrackingMetrics.

Wanneer een bezoeker naar uw plaats komt en een telefoongesprek voert, is het de baan van CallTrackingMetrics om die gegevens in [!DNL Salesforce] te duwen.  Doorgaans wordt een [!DNL Salesforce Task] gemaakt die gegevens zoals telefoonnummer, onderwerp, type en nu de [!DNL BizibleId] vult.

[!DNL BizibleId] is een veld dat wordt geïnstalleerd met versie 6.7+ van het [!DNL Marketo Measure] pakket Marketingkenmerken.

Hieronder ziet u een voorbeeld van een taakrecord met de map [!DNL BizibleId] .

![](assets/other-resources-5.png)

Wanneer [!DNL Marketo Measure] een taakrecord zoekt waarvan de bekende [!DNL BizibleId] waarde is ingevuld, kan [!DNL Marketo Measure] die gebruiker toewijzen aan een websessie met dezelfde [!DNL BizibleId] en die sessie toewijzen aan een telefoongesprek in plaats van een webbezoek.

## Het aanraakpunt {#the-touchpoint}

Wanneer [!DNL Marketo Measure] de taak kan importeren/downloaden, verwerken we die details samen met de websessie. Doorgaans kan de advertentie worden samengevoegd met een referentie of advertentie. In het onderstaande voorbeeld vond een bezoeker het bedrijf via een advertentie voor Betaalde Google en deed hij een telefoontje.

Het [!UICONTROL Touchpoint] Type &quot;Vraag&quot;wordt getrokken uit de Taak, van het hierboven geschetste scherm, dat ook door CallTrackingMetrics wordt bevolkt wanneer de Taak wordt gecreeerd.

![](assets/one-one-1.png)

## Rapportage {#reporting}

De waarden van het Type van aanraakpunt die [!DNL Marketo Measure] typisch duikt zijn het Bezoek van het Web, de Vorm van het Web, of het Praatje van het Web, maar in het geval van CallTrackingMetrics touchpoints, is het aanraakpunttype de Vraag van de Telefoon. Dit helpt marketers zien welke kanalen in de meeste telefoongesprekken trekken en opbrengst voor hun organisatie produceren.

![](assets/other-resources-1.png)

## Veelgestelde vragen {#faq}

**waarom is mijn touchpoint typeWebbezoek?**

Het Type van Aanraakpunt wordt bevolkt van het Task.Type gebied. Als het veld Task.Type leeg is, stelt [!DNL Marketo Measure] automatisch het aanraakpunttype in als Web Visit. Wanneer het veld Task.Type is ingevuld [!DNL Marketo Measure] , wordt die waarde gelezen en wordt het Type aanraakpunt dienovereenkomstig ingevuld.

**Welke andere gebieden bevolkt het Aanraakpunt van de telefoonvraag?**

Zowel het Type van Aanraakpunt als Medium bevat de gegevens die van Task.Type worden getrokken. Alle andere gegevenspunten worden opgehaald uit webtracking en javascript-gegevens.

**waarom is dit telefoongesprek niet gebonden aan een Webzitting?**

Controleer eerst de taak of er een [!DNL BizibleId] is ingevuld. Als er geen waarde is, kunnen we er geen aanraakpunt voor maken. Dit moet met CallTrackingMetrics worden geëscaleerd.

Als er een waarde is, merken wij op dat wij slechts alle Webzittingen als 30 minuten beschouwen. Als een Ad van Google bij 12 :17pm (begin van de zitting op de website) werd geklikt, maar het telefoongesprek kwam niet voor tot 1 :05pm, zullen wij niet de Webzitting en telefoongesprek samenvoegen. In plaats daarvan maakt [!DNL Marketo Measure] een apart [!DNL Salesforce Task] -aanraakpunt om het telefoongesprek bij te houden, maar heeft het geen websessiegegevens.

![](assets/other-resources-2.png)

## Partnerschappen {#partnerships}

[!DNL Marketo Measure] heeft momenteel één officiële partner van het Volgen van de Vraag die het &quot;officiële&quot;integratieproces met ons heeft doorlopen, die co-marketing en productopleiding omvatte. Deze ene partner is CallTrackingMetrics.
