---
description: Beste praktijken voor het Model van de Douane -  [!DNL Marketo Measure]
title: Aanbevolen procedures voor aangepast model
exl-id: 7c19bb6a-30fc-4cbd-a58e-f20751102afe
feature: Custom Models
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 0%

---

# Aanbevolen procedures voor aangepast model {#best-practices-for-custom-model}

## Overzicht {#overview}

Naast [!DNL Marketo Measure] uit de doos Modellen van de Attributie, hebben de klanten van Rij 2 en hierboven toegang tot een Model van de Attributie van de Douane.

Met het [!DNL Marketo Measure] Aangepaste kenmerkingsmodel kunnen gebruikers kiezen welke mijlpaal-aanraakpuntposities en/of aangepaste stadia in het model worden opgenomen. Bovendien kunnen gebruikers bepalen welk percentage aan elk werkgebied in het model wordt toegewezen (gebruikers kunnen maximaal zes extra aangepaste fasen definiëren), of ze kunnen de waarden voor het toewijzingspercentage gebruiken die worden voorgesteld door het [!DNL Marketo Measure] Machine Learning Model.

Er zijn twee belangrijke aspecten van uw Aangepast kenmerkingsmodel:

**de Staven van de Douane** staan gebruikers toe om hun funnel te bepalen aangezien het op hun zaken en processen betrekking heeft. Aangepaste stappen moeten &#39;mijlpalen&#39; zijn tijdens de hele reis van de koper, net als de [!DNL Marketo Measure] -mijlpalen (First Touch, Lead Creation Touch, Opportunity Creation Touch en Closed Won Touch) die in de modellen voor voorraadtoewijzing worden gebruikt. Het is van cruciaal belang dat uw aangepaste stadia correct zijn gedefinieerd en in uw account zijn toegewezen om ervoor te zorgen dat [!DNL Marketo Measure] de werkgebiedovergangen correct bijhoudt. Hiermee wordt bepaald welke aanraakpunten aan elke fase moeten worden gekoppeld en wordt het krediet op passende wijze toegewezen. Aangepaste werkgebiedtoewijzing is in feite een uitbreiding van de standaard &#39;werkgebiedtoewijzing&#39; en moet dezelfde procedures volgen.

>[!NOTE]
>
>Verwijs naar de Werkgebiedtoewijzing Best Practice-bron voor meer informatie

**de Modellering van de Attributie van de Douane** wordt bepaald zodra u uw funnel van de Stages van de Douane selecteert. Gebruikers kunnen vervolgens bepalen hoeveel toewijzingkrediet aan elke aangepaste fase moet worden toegewezen, en welke mijlpaalfasen moeten worden gebruikt. [!DNL Marketo Measure] Gebruikers kunnen kredieten toewijzen aan elk werkgebied naar eigen inzicht, of verwijzen naar het [!DNL Marketo Measure] Machine Learning Model dat fungeert als een &quot;suggestief model&quot; op basis van historische gegevens.

Het is van cruciaal belang dat deze twee aspecten van uw aangepaste model correct en precies zijn gedefinieerd om ervoor te zorgen dat [!DNL Marketo Measure] een accuraat aangepast kenmerkingsmodel produceert.

## Beste praktijken {#best-practice}

Of u uw Model van de Douane voor het eerst, of het herzien van bekijkt wat eerder is gevestigd, is het belangrijk om de volgende beste praktijken in mening te houden.

* Eenvoudig starten
   * Identificeer de belangrijkste stadia die u aan uw Model van de Douane wilt toevoegen die voor uw [!DNL Marketo Measure] rapportering essentieel zijn. Doorgaans zijn dit stadia die u vaak tegengaat of waarvoor u insight wilt laten aanroepen
   * U kunt altijd in de loop der tijd een aangepast model toevoegen
* Het [!DNL Marketo Measure] Machine Learning Model gebruiken
   * Als u moeite hebt om te beslissen over het percentage dat wordt toegewezen, kunt u met het [!DNL Marketo Measure] Machine Learning-model met kennis van zaken beslissingen nemen wanneer u het Aangepast kenmerkingsmodel instelt.
   * Bij het bekijken van het Machine Learning Model, weerspiegelen de attributiepercentages van elke fase de potentiële impact van uw marketing inspanningen
      * Een hoger percentage betekent dat het in de handel brengen de beweging van de funnel op dat punt rechtstreeks kan beïnvloeden
      * Een lager toewijzingspercentage betekent dat de stadia voor uw team minder belangrijk zijn om te controleren
* U moet de top van funnel-fasen definiëren op basis van de fasen Lead of Contact, en niet op basis van beide
   * Dit betekent dat u ervoor moet zorgen dat alle personen door dat stadium op het relatieve object gaan
      * Als u bijvoorbeeld het MQL-werkgebied definieert vanuit het object Lead, moeten alle personen naar uw systeem gaan als een lead en zijn gemarkeerd als een MQL in hun lijst met leads, zodat [!DNL Marketo Measure] nauwkeurig kan aangeven welke aanraking gerelateerd was aan de overgang van de lead naar MQL. Als dit niet het geval is, en sommige mensen aan Contact alvorens MQL als Lood te worden, [!DNL Marketo Measure] zal niet in staat zijn om dit in uw gegevens van het Aanraakpunt nauwkeurig rekenschap te geven en wij zullen moeten veronderstellen dat die persoon reeds MQL&#39;d heeft. [!DNL Marketo Measure] kan geen rekening houden met het hoppen in het werkgebied, dus we zullen concluderen dat er fasen zijn doorlopen, zelfs als dat niet het geval is.
* Zorg ervoor dat het bijhouden van de veldgeschiedenis is ingeschakeld voor alle velden die worden gebruikt om aangepaste stadia te definiëren die u opneemt
* Gebruik geen formules voor het definiëren van een aangepast werkgebied
   * Een Booleaans veld is een aanbevolen werkwijze
* Geen aangepaste werkruimten opnemen in uw aangepaste model die samenvallen met een [!DNL Marketo Measure] mijlpaalaanraakpuntpositie (FT, LC, OC, Gesloten won/Verloren)
   * Als u dit doet, vinden deze posities altijd tegelijkertijd plaats en kunnen er opgeblazen attributietekeningen ontstaan voor delen van uw funnel.
* Werken met je verkoopteam
   * Het brengen in het team dat het dichtst met stadia werkt en hun betekenis zorgt ervoor dat u de correcte stadia gebruikt en dat zij behoorlijk worden bepaald

## Aanbevolen werkwijzen voor onderhoud {#best-practice-for-maintenance}

Als u ten minste tweemaal per jaar uw aangepaste model controleert, weet u zeker dat de rapportage voor aangepaste toewijzingen correct en betrouwbaar is.

Als uw Aangepast model het Machine Learning Model gebruikt, zou u zijn toepassing binnen het Model van de Douane driemaandelijks moeten herzien om uw Model van de Douane te verzekeren is zo bijgewerkt mogelijk.

Andere redenen die een herziening van het aangepaste model kunnen veroorzaken, zijn onder meer...

* Omzet in uw marketingteam
* Eventuele wijzigingen in uw CRM-fasen
* Updates voor uw organisaties funnel
* Onnauwkeurige inkomstengegevens in uw [!DNL Marketo Measure] -rapport bekijken wanneer u het aangepaste model toepast
* Aanraakpunten weergeven die zijn gevuld en die niet meer relevant zijn voor uw organisaties funnel

>[!MORELIKETHIS]
>
>* [ Model en Opstelling van de Attributie van de Douane ](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md)
>* [ laat het Volgen van de Geschiedenis van het Gebied voor het Model van de Douane toe ](/help/advanced-marketo-measure-features/custom-attribution-models/custom-model-setup-enable-field-history-tracking.md)
>* [ het Leren van de Machine Model ](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md)
