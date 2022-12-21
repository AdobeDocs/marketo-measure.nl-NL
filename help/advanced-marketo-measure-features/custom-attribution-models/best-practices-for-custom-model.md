---
description: Aanbevolen procedures voor aangepast model - [!DNL Marketo Measure] - Productdocumentatie
title: Aanbevolen procedures voor aangepast model
exl-id: 7c19bb6a-30fc-4cbd-a58e-f20751102afe
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 0%

---

# Aanbevolen procedures voor aangepast model {#best-practices-for-custom-model}

## Overzicht {#overview}

Naast de [!DNL Marketo Measure] uit de doos Modellen van de Attributie, hebben de klanten van Tier 2 en hierboven toegang tot een Model van de Attributie van de Douane.

De [!DNL Marketo Measure] Met het aangepaste kenmerkingsmodel kunnen gebruikers kiezen welke mijlpaal-aanraakpuntposities en/of aangepaste stadia in het model worden opgenomen. Bovendien kunnen gebruikers bepalen welk percentage aan elk stadium in het model wordt toegewezen (gebruikers kunnen maximaal zes extra aangepaste fasen definiëren) of kunnen ze de waarden voor het toewijzingspercentage gebruiken die door de [!DNL Marketo Measure] Machine Learning Model.

Er zijn twee belangrijke aspecten van uw Aangepast kenmerkingsmodel:

**Aangepaste stadia** gebruikers toestaan hun trechter te definiëren als zijnde gerelateerd aan hun bedrijf en processen. Aangepaste fasen moeten &#39;mijlpalen&#39; zijn gedurende de hele reis van de koper, net als de [!DNL Marketo Measure] De mijlpalen (First Touch, Lead Creation Touch, Opportunity Creation Touch en Closed Won Touch) doen dit in de modellen voor voorraadtoewijzing. Het is van cruciaal belang dat uw aangepaste fasen correct worden gedefinieerd en toegewezen binnen uw account, zodat u ervoor zorgt dat [!DNL Marketo Measure] wordt gebruikt voor het correct bijhouden van werkgebiedovergangen. Hiermee wordt bepaald welke aanraakpunten aan elke fase moeten worden gekoppeld en wordt het krediet op passende wijze toegewezen. Aangepaste werkgebiedtoewijzing is in feite een uitbreiding van de standaard &#39;werkgebiedtoewijzing&#39; en moet dezelfde procedures volgen.

>[!NOTE]
>
>Verwijs naar de Werkgebiedtoewijzing Best Practice-bron voor meer informatie

**Aangepaste kenmerkmodellen** wordt gedefinieerd nadat u de trechter Aangepaste werkruimten hebt geselecteerd. Gebruikers kunnen dan bepalen hoeveel toewijzingskrediet aan elke aangepaste fase moet worden toegewezen en [!DNL Marketo Measure] mijlpaalfasen. Gebruikers kunnen kredieten toewijzen aan elk stadium naar eigen inzicht, of verwijzen naar de [!DNL Marketo Measure] Machine Learning Model dat fungeert als &quot;suggestief model&quot; op basis van historische gegevens.

Het is van cruciaal belang dat deze twee aspecten van uw aangepaste model correct en precies worden gedefinieerd om ervoor te zorgen dat [!DNL Marketo Measure] produceert een accuraat aangepast kenmerkingsmodel.

## Beste praktijken {#best-practice}

Of u uw Model van de Douane voor het eerst opstelt, of het herzien van wat eerder is gevestigd, is het belangrijk om de volgende beste praktijken in mening te houden.

* Eenvoudig starten
   * Identificeer de belangrijkste stadia die u aan uw Model van de Douane wilt toevoegen die voor uw [!DNL Marketo Measure] rapportage. Doorgaans zijn dit stadia die u vaak tegenkomt of die u wilt laten ophelderen
   * U kunt altijd in de loop der tijd een aangepast model toevoegen
* De opdracht [!DNL Marketo Measure] Machine Learning-model
   * Als u moeite hebt om het percentage van de toewijzingsdoorbraak te bepalen, [!DNL Marketo Measure] Het leren van de machine Model kan u helpen om geïnformeerde besluiten te nemen wanneer het plaatsen van u het Model van de Attributie van de Douane.
   * Bij het bekijken van het Machine Learning Model, weerspiegelen de attributiepercentages van elke fase de potentiële impact van uw marketing inspanningen
      * Een hoger percentage betekent dat het in de handel brengen de beweging van de trechter op dat punt rechtstreeks kan beïnvloeden
      * Een lager toewijzingspercentage betekent dat de stadia voor uw team minder belangrijk zijn om te controleren
* U moet de bovenkant van de trechterstadia definiëren op basis van de fasen Lood of Contact, niet op beide
   * Dit betekent dat u ervoor moet zorgen dat alle personen door dat stadium op het relatieve object gaan
      * Bijvoorbeeld: Als u het MQL-werkgebied definieert vanuit het Lead-object, moeten alle personen in uw systeem gaan als een lead en zijn gemarkeerd als een MQL in de lijst met leads voor [!DNL Marketo Measure] om nauwkeurig te weerspiegelen welke aanraking met de overgang van de Lood naar MQL verwant was. Als dit niet het geval is, en sommige mensen beginnen contact op te nemen alvorens MQL als leider te worden, [!DNL Marketo Measure] zal dit niet nauwkeurig kunnen verklaren in uw gegevens van het Aanraakpunt en wij zullen moeten veronderstellen dat de persoon reeds MQL&#39;d heeft. [!DNL Marketo Measure] we kunnen geen rekening houden met het hoppingsproces in de etappes , dus we zullen concluderen dat de etappes zijn doorlopen , ook al is dat niet het geval .
* Zorg ervoor dat het bijhouden van de veldgeschiedenis is ingeschakeld voor alle velden die worden gebruikt om aangepaste stadia te definiëren die u opneemt
* Gebruik geen formules voor het definiëren van een aangepast werkgebied
   * Een Booleaans veld is een aanbevolen werkwijze
* Geen aangepaste werkruimten opnemen in uw aangepaste model die samenvallen met een [!DNL Marketo Measure] Milestone Touchpoint Position (FT, LC, OC, Closed Won/Lost)
   * Als u dit doet, zullen deze posities altijd gelijktijdig voorkomen en kunnen opgeblazen attributiekrediet aan delen van uw trechter veroorzaken.
* Werken met je verkoopteam
   * Het in het team brengen dat het dichtst met stadia werkt en hun betekenis zal ervoor zorgen u de correcte stadia gebruikt en dat zij behoorlijk worden bepaald

## Best Practice for Maintenance {#best-practice-for-maintenance}

Als u ten minste tweemaal per jaar uw aangepaste model controleert, weet u zeker dat de rapportage voor aangepaste toewijzingen correct en betrouwbaar is.

Als uw Aangepast model het Machine Learning Model gebruikt, zou u zijn toepassing binnen het Model van de Douane driemaandelijks moeten herzien om uw Model van de Douane te verzekeren is zo bijgewerkt mogelijk.

Andere redenen die een herziening van het aangepaste model kunnen veroorzaken, zijn onder meer...

* Omzet in uw marketingteam
* Eventuele wijzigingen in uw CRM-fasen
* Updates voor uw organisatietrechter
* Onnauwkeurige inkomstengegevens in uw [!DNL Marketo Measure] rapporteren bij toepassing van het aangepaste model
* Aanraakpunten weergeven die zijn gevuld en die niet meer relevant zijn voor de trechter van uw organisatie

>[!MORELIKETHIS]
>
>* [Aangepast kenmerkmodel en aangepaste instellingen](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md)
>* [Enable Field History Tracking for Custom Model](/help/advanced-marketo-measure-features/custom-attribution-models/custom-model-setup-enable-field-history-tracking.md)
>* [Machine Learning-model](/help/advanced-marketo-measure-features/custom-attribution-models/machine-learning-model-faq.md)

