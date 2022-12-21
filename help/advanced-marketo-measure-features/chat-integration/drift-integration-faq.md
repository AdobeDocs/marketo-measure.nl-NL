---
unique-page-id: 27656441
description: Veelgestelde vragen over driftintegratie - [!DNL Marketo Measure] - Productdocumentatie
title: Veelgestelde vragen over driverintegratie
exl-id: ae5706b1-1f6c-4201-8585-0d7c587746e1
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 0%

---

# Veelgestelde vragen over driverintegratie {#drift-integration-faq}

Als onderdeel van het [!DNL Marketo Measure] Door de integratie met Drift hebben we een aantal van de meest gestelde vragen uiteengezet. Als er hieronder geen vragen zijn die niet worden beschreven, kunt u contact opnemen met uw Customer Success Manager of [Marketo-ondersteuning](https://nation.marketo.com/t5/support/ct-p/Support){target=&quot;_blank&quot;}.

**Hoe wordt de integratie ingeschakeld?**

Chattracering voor geforceerde bestanden [!DNL Marketo Measure] is standaard ingeschakeld. Als u het wilt uitschakelen (en geen aanraakpunten maakt van Drift Chats standaard), moet er een extra kenmerk aan uw [!DNL Marketo Measure] Javascript-implementatie, hieronder meegeleverd:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" id="bizible-settings" data-chatEnabled="false"></script>`

Voor degenen die [!DNL Google Tag Manager] om de [!DNL Marketo Measure] Script: als u wilt voorkomen dat uw driftchats geschikt zijn voor aanraakpunten, moet u het volgende toevoegen `<span>` direct na uw [!DNL Marketo Measure] Script:

`<span id="bizible-settings" data-chatEnabled="false"></span>`

**Wat doet de integratie?**

Dankzij de integratie is nu [!DNL Marketo Measure] om te volgen wanneer een eindgebruiker hun e-mailadres in een praatje van de Drijving verstrekt. Vanaf dat punt maken we aanraakpunten van deze interacties met een Touchpoint Type of &quot;Web Chat&quot;. Dankzij deze integratie kunnen marketers de prestaties van hun chatinteractie begrijpen, samen met de kanalen/subkanalen/campagnes die mensen aansporen om met deze chatten te werken.

**Wat gebeurt er als ik Drift bijhoud via de regels voor het synchroniseren van campagnes?**

Als er om het even welke regels van de campagnesynchronisatie op zijn plaats zijn om touchpoints voor de praatjeinteractie van de Drift tot stand te brengen, zult u moeten ervoor zorgen u ophouden toevoegend die bepaalde eind-gebruikers in de overeenkomstige Campagne van CRM. Anders zullen wij, zodra het eigenschapbeetje wordt toegelaten, een aanraakpunt van de Campagne van CRM en digitaal aanraakpunt voor één de praatjeinteractie van de Zrijving creëren.

**Wat als ik Drift via CRM Campaigns volg?**

Als er campagnes van CRM op zijn plaats zijn om touchpoints voor de praatjeinteractie van de Drift tot stand te brengen, zal een Datum van het Eind van het Aanraakpunt op die specifieke campagnes moeten worden geplaatst (de Datum van het Eind van het Aanraakpunt zou de datum moeten zijn het de eigenschapbeetje van de Integratie van het Praatje van het Web wordt toegelaten).

**Wat als ik Drift via Activiteiten volg?**

Als er activiteitsregels op zijn plaats zijn om touchpoints voor de praatjeinteractie van de Drijving tot stand te brengen, zal een extra stuk van logica aan de regels moeten worden toegevoegd. U zult logica moeten toevoegen gebruikend het Taak Gemaakte gebied van de Datum om dubbel aanraakpunten te verhinderen worden gecreeerd (IE CrmTask.CreatedDate is minder dan de datum waarin het eigenschapbeetje werd toegelaten). Zie onderstaande schermafbeelding.

![](assets/activity-rule-drift.png)
