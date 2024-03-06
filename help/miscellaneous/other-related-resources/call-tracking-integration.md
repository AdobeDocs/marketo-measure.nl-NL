---
unique-page-id: 18874592
description: Integratie van bijhouden van oproepen - [!DNL Marketo Measure]
title: Integratie van het bijhouden van oproepen
exl-id: bc35a789-e056-4456-9038-306ed34c2a8e
feature: Tracking, Integration
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 0%

---

# Integratie van het bijhouden van oproepen {#call-tracking-integration}

Onze integratie met [!DNL CallTrackingMetrics] is bedoeld om een Webzitting met een telefoongesprek samen te voegen. Een telefoongesprek wordt behandeld als een formulierverzending naar [!DNL Marketo Measure]. Het geeft krediet aan een Webzitting die anders slechts als Webbezoek zou worden beschouwd omdat er geen daadwerkelijke vormvoorlegging was geweest.

## Vraag die Verklaarde het Volgen {#call-tracking-explained}

&quot;Vraag het Volgen&quot; in algemene zin is een product van bedrijven zoals [!DNL CallTrackingMetrics], [!DNL DiaglogTech], [!DNL Invoca], of [!DNL CallRail], om er een paar te noemen. De unieke telefoonaantallen worden getoond aan gebruikers die op de verschillende marketing kanalen of de campagnes worden gebaseerd die zij uit komen. Op deze manier kunnen marketeers zien hoe die kanalen of campagnes presteren.

![](assets/1.png)

## Voor en Na {#before-and-after}

Kijk hieronder naar het stroomschema om te zien hoe [!DNL Marketo Measure] gebruikt om telefoongesprekken zonder een integratie met CallTrackingMetrics te behandelen. Het telefoongesprek dat plaatsvond, werd niet bijgehouden, dus het werd gezien als een Webzitting en geen touchpoint werd gecreeerd voor het. Pas bij het volgende bezoek heeft de gebruiker een formulier ingevuld dat uiteindelijk door een aanraakpunt werd ingevuld.

Met de integratie, kunt u zien dat de Webzitting eigenlijk aan een telefoongesprek werd gebonden. De volgende invulling van het formulier wordt dan een PostLC-aanraking en wordt nog steeds bijgehouden tijdens de reis.

![](assets/2.png)

## Hoe het werkt {#how-it-works}

CallTrackingMetrics moet wat ontwikkelingswerk op hun eind doen opdat dit werkt. Met JavaScript dat zij op uw plaats plaatsen, kan CallTrackingMetrics _biz_uid van _biz_uid pakken [!DNL Marketo Measure] cookie. Dit &quot;[!DNL BizibleId]&quot; wordt dan opgeslagen door CallTrackingMetrics.

Wanneer een bezoeker naar uw plaats komt en een telefoongesprek voert, is het de baan van CallTrackingMetrics om die gegevens in te duwen [!DNL Salesforce].  Doorgaans wordt een [!DNL Salesforce Task] wordt gecreeerd die gegevens zoals telefoonaantal, onderwerp, type, en nu bevolkt, [!DNL BizibleId]

De [!DNL BizibleId] is een veld dat is geïnstalleerd met versie 6.7+ van de [!DNL Marketo Measure] Marketing Attribution package.

Hieronder ziet u een voorbeeld van een taakrecord met de [!DNL BizibleId] gevuld.

![](assets/3.png)

Wanneer [!DNL Marketo Measure] vindt een verslag van de Taak met bekende [!DNL BizibleId] ingevulde waarde, [!DNL Marketo Measure] kan die gebruiker toewijzen aan een websessie met dezelfde [!DNL BizibleId] en kenmerk die zitting aan een telefoongesprek in plaats van een Webbezoek.

## Het aanraakpunt {#the-touchpoint}

Wanneer [!DNL Marketo Measure] We kunnen de taak importeren/downloaden en verwerken die details samen met de websessie. Doorgaans kan de advertentie worden samengevoegd met een referentie of advertentie. In het onderstaande voorbeeld vond een bezoeker het bedrijf via een advertentie voor Betaalde Google en deed hij een telefoontje.

De [!UICONTROL Touchpoint] Het type &quot;Vraag&quot;wordt getrokken uit de Taak, van het hierboven opgenomen schermafbeelding, die ook door CallTrackingMetrics wordt bevolkt wanneer de Taak wordt gecreeerd.

![](assets/4.png)

## Rapportage {#reporting}

Type aanraakpunt waarden die [!DNL Marketo Measure] typisch duwt zijn het Bezoek van het Web, de Vorm van het Web, of het Praatje van het Web, maar in het geval van CallTrackingMetrics touchpoints, is het aanraakpunttype de Vraag van de Telefoon. Dit helpt marketers zien welke kanalen in de meeste telefoongesprekken trekken en opbrengst voor hun organisatie produceren.

![](assets/5.png)

## Veelgestelde vragen {#faq}

**Waarom is mijn touchpoint-webbezoek?**

Het Type van Aanraakpunt wordt bevolkt van het Task.Type gebied. Als het veld Task.Type leeg is, [!DNL Marketo Measure] Hiermee wordt het aanraakpunttype automatisch ingesteld als een webbezoek. Zodra het gebied Task.Type wordt bevolkt [!DNL Marketo Measure] Deze waarde wordt gelezen en het Type aanraakpunt wordt dienovereenkomstig gevuld.

**Welke andere gebieden vult het Aanraakpunt van het telefoongesprek?**

Zowel bevat het Type van Aanraakpunt als het Middel de gegevens die van Task.Type worden getrokken. Alle andere gegevenspunten worden opgehaald uit webtracking en javascript-gegevens.

**Waarom is dit telefoongesprek niet gekoppeld aan een websessie?**

Controleer eerst de taak om er zeker van te zijn dat er een [!DNL BizibleId] gevuld. Als er geen waarde is, kunnen we er geen aanraakpunt voor maken. Dit moet met CallTrackingMetrics worden geëscaleerd.

Als er een waarde is, merken wij op dat wij slechts alle Webzittingen als 30 minuten beschouwen. Als om 12:17 uur op een advertentie voor de Google is geklikt (begin van de sessie op de website), maar het telefoongesprek vond pas om 13:05 uur plaats, voegen we de websessie en het telefoongesprek niet samen. In plaats daarvan, [!DNL Marketo Measure] maakt een aparte [!DNL Salesforce Task] touchpoint om het telefoongesprek bij te houden, maar heeft geen websessiegegevens.

![](assets/6.png)

## Partnerschappen {#partnerships}

[!DNL Marketo Measure] Momenteel heeft één officiële partner van het Volgen van de Vraag die het &quot;officiële&quot;integratieproces met ons heeft doorlopen, die co-marketing en productopleiding omvatte. Deze ene partner is CallTrackingMetrics.
