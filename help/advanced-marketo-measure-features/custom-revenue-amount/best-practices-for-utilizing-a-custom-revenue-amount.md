---
description: Beste praktijken voor het Gebruiken van een Bedrag van de Inkomsten van de Douane -  [!DNL Marketo Measure]
title: Aanbevolen werkwijzen voor het gebruik van een aangepaste opbrengstwaarde
exl-id: 553bd75a-512a-4733-a24b-8112eb420afc
feature: Custom Revenue Amount
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%

---

# Aanbevolen werkwijzen voor het gebruik van een aangepaste opbrengstwaarde {#best-practices-for-utilizing-a-custom-revenue-amount}

## Overzicht {#overview}

De kernfunctionaliteit van [!DNL Marketo Measure] is de mogelijkheid om inkomstenkrediet toe te wijzen aan marketingaanraakpunten gedurende de hele reis van de koper. De sleutel tot nauwkeurige opbrengsttoewijzing is het vermogen voor [!DNL Marketo Measure] om het correcte opbrengstbedrag op een Kans te verwijzen, die beurtelings over de marketing aanraakpunten via de diverse attributiemodellen wordt verdeeld.

Tenzij anders opgegeven tijdens de implementatie, wordt de [!DNL Marketo Measure] -instantie ingesteld om te verwijzen naar het standaard Opportunity Amount (SFDC Default) voor inkomstentoewijzing. Voor veel [!DNL Marketo Measure] -accounts geeft dit veld echter niet het juiste inkomstenbedrag voor Opportunity weer. In deze gevallen biedt [!DNL Marketo Measure] de mogelijkheid om een aangepaste opbrengstwaarde voor [!DNL Marketo Measure] in te stellen voor referentie en distributie over de kenmerkende aanraakpunten (BAT&#39;s).

## Beste praktijken {#best-practice}

Houd bij het instellen van een Aangepast inkomstenbedrag rekening met de volgende aanbevolen procedures om ervoor te zorgen dat de toewijzingsgegevens van [!DNL Marketo Measure] accuraat en consistent zijn!

Denk aan de volgende zaken:

* Selecteer het opbrengstgebied dat voor alle Kansen nauwkeurig en gebruikt is
   * ARR of Total Contract Value us aanbevolen
* Gebruik geen veld met een formule
* Als u een Aangepast inkomstenbedrag gebruikt voor conversies naar valuta, heeft de functie [!UICONTROL Marketo Measure Multiple Currencies] in plaats daarvan de voorkeur.
   * De functie [!DNL Marketo Measure] Meerdere valuta&#39;s verwijst naar de conversiekoersen die in [!DNL Salesforce] zijn vastgesteld om de uitlijning tussen valutaomrekeningen het best te kunnen waarborgen. Op deze manier kunt u doorgaan met het gebruik van de standaard &#39;Bedrag&#39; (standaard SFDC-standaard) of een ander aangepast veld Bedrag dat betrekking heeft op de [!DNL Salesforce] -conversiekoersen.
* Als u het veld Hoeveelheid bijwerkt waarnaar u in [!DNL Marketo Measure] wilt verwijzen, gebruikt u Data Loader om oude opportunity bij te werken om ervoor te zorgen dat uw inkomstengegevens consistent zijn en dat het juiste veld wordt gevuld via de workflow

## Aanbevolen werkwijzen voor onderhoud {#best-practice-for-maintenance}

Als u jaarlijks de instellingen van uw inkomstenbedrag controleert, worden de toewijzingsgegevens correct en afgestemd op de rest van de inkomstenrapportage van uw organisatie.

Als u een Bedrag van de Inkomsten van de Douane gebruikt, controleer uw opbrengstopstelling als volgt.

* Ga in uw [!DNL Marketo Measure] account naar de sectie &#39;[!UICONTROL Opportunities]&#39; onder CRM
* Identificeer het veld [!UICONTROL Custom Opportunity Amount] , waar uw veld [!UICONTROL custom revenue amount API] moet worden vermeld
* Bevestig dat dit nog steeds het juiste veld is
* Zorg er ook voor dat uw [!DNL Salesforce] Admin bevestigt dat de workflow voor het bedrag van aangepaste inkomsten in [!DNL Salesforce] nog steeds wordt uitgevoerd

Naast een jaarlijkse evaluatie, kunnen bepaalde organisatorische veranderingen de behoefte om uw opstelling van de opbrengstbedragen te herzien...

* Omzet in uw marketingteam
* Wijzigingen in het veld Aangepaste inkomsten
* Wijzigingen in de manier waarop inkomsten worden gerapporteerd door de organisatie

>[!MORELIKETHIS]
>
>* [&#x200B; Gebruikend een Gebied van de Bedrag van de Opbrengst van de Douane &#x200B;](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)
>* [&#x200B; Gebruikend de Lader van Gegevens om het Gebied van het Bedrag van de Douane bij te werken &#x200B;](/help/advanced-marketo-measure-features/custom-revenue-amount/using-data-loader-to-update-marketo-measure-custom-amount-field.md)
>* [&#x200B; Overzicht van multi-Valuta &#x200B;](/help/advanced-marketo-measure-features/multi-currency/overview.md)
>* [&#x200B; multi-Currency Montages &#x200B;](/help/advanced-marketo-measure-features/multi-currency/settings.md)
