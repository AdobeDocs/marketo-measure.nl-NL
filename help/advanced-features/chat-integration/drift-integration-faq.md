---
description: Richtlijnen voor driftintegratie in veelgestelde vragen voor Marketo Measure-gebruikers
title: Veelgestelde vragen over driverintegratie
exl-id: ae5706b1-1f6c-4201-8585-0d7c587746e1
feature: Integration
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 0%

---

# Veelgestelde vragen over driverintegratie {#drift-integration-faq}

In het kader van de [!DNL Marketo Measure] -integratie met Drift stelt u enkele van de meest gestelde vragen. Als er om het even welke vragen zijn die hieronder niet worden geschetst, bereik aan het Team van de Rekening van Adobe (uw Manager van de Rekening) of [&#x200B; Steun van Marketo &#x200B;](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

**hoe wordt de integratie toegelaten?**

Chattracking voor [!DNL Marketo Measure] is standaard ingeschakeld. Als u deze wilt uitschakelen (en standaard geen aanraakpunten wilt maken van Drift Chats), voegt u een extra kenmerk toe aan de [!DNL Marketo Measure] JavaScript-implementatie, dat hieronder wordt weergegeven:

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async="" id="bizible-settings" data-chatEnabled="false"></script>`

Als u wilt voorkomen dat uw drift-chats geschikt zijn voor het aanraakpunt, kunt u het volgende toevoegen aan [!DNL Google Tag Manager] direct na het [!DNL Marketo Measure] -script voor diegenen die `<span>` gebruiken om het [!DNL Marketo Measure] -script te laden:

`<span id="bizible-settings" data-chatEnabled="false"></span>`

**wat doet de integratie?**

Dankzij de integratie kan [!DNL Marketo Measure] nu bijhouden wanneer een eindgebruiker zijn e-mailadres opgeeft in een zwevende chat. Vanaf dat punt maken we aanraakpunten van deze interacties met een Touchpoint Type of &quot;Web Chat&quot;. Dankzij deze integratie kunnen marketers de prestaties van hun chatinteractie begrijpen, samen met de kanalen/subkanalen/campagnes die mensen aansporen om met deze chatten te werken.

**wat als ik Drijving door de regels van de campagnesynchronisatie volg?**

Als er om het even welke regels van de campagnesynchronisatie op zijn plaats zijn om touchpoints voor de praatjeinteractie van de Drift tot stand te brengen, zorg u ophouden toevoegend die bepaalde eind - gebruikers in de overeenkomstige Campagne van CRM. Anders, zodra het eigenschapbeetje wordt toegelaten, creeer een aanraakpunt van de Campagne van CRM en digitaal aanraakpunt voor één de praatjeinteractie van de Zrijving.

**wat als ik Drift via de Campagnes van CRM volg?**

Als er campagnes CRM op zijn plaats zijn om touchpoints voor de praatjeinteractie van de Drift tot stand te brengen, moet een Datum van het Eind van het Aanraakpunt op die specifieke campagnes worden geplaatst (de Datum van het Eind van het Aanraakpunt zou de datum moeten zijn het de eigenschapbeetje van de Integratie van het Praatje van het Web wordt toegelaten).

**wat als ik Drift door Activiteiten volg?**

Als er activiteitsregels op zijn plaats zijn om touchpoints voor de praatjeinteractie van de Drijving tot stand te brengen, moet een extra stuk van logica aan de regels worden toegevoegd. Voeg logica toe gebruikend het Taak Gemaakte gebied van de Datum om dubbel aanraakpunten te verhinderen worden gecreeerd (IE CrmTask.CreatedDate is minder dan de datum waarin het eigenschapbeetje werd toegelaten). Zie onderstaande schermafbeelding.

![](assets/chat-integration-1.png)
