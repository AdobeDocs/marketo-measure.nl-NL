---
description: Aanbevolen werkwijzen voor het gebruik van een Aangepast bedrag aan inkomsten - [!DNL Marketo Measure]
title: Aanbevolen werkwijzen voor het gebruik van een aangepaste opbrengstwaarde
exl-id: 553bd75a-512a-4733-a24b-8112eb420afc
feature: Custom Revenue Amount
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%

---

# Aanbevolen werkwijzen voor het gebruik van een aangepaste opbrengstwaarde {#best-practices-for-utilizing-a-custom-revenue-amount}

## Overzicht {#overview}

De kernfunctionaliteit van [!DNL Marketo Measure] is de mogelijkheid om tijdens de gehele reis van de koper een inkomstenkrediet toe te kennen aan marketingpunten. De sleutel tot een nauwkeurige toerekening van opbrengsten is de mogelijkheid voor [!DNL Marketo Measure] het juiste inkomstenbedrag op een Opportunity te vermelden, dat op zijn beurt via de verschillende toewijzingsmodellen over de marketingaanspreekpunten wordt verdeeld.

Tenzij tijdens de implementatie anders is opgegeven, kunt u [!DNL Marketo Measure] instantie wordt ingesteld om te verwijzen naar het standaardbedrag van de opportuniteit (SFDC Default) voor inkomstentoewijzing. Maar voor velen [!DNL Marketo Measure] rekeningen, geeft dit gebied niet het nauwkeurige opbrengstbedrag voor Kansen weer. In deze gevallen [!DNL Marketo Measure] biedt de mogelijkheid om een aangepaste opbrengstwaarde in te stellen voor [!DNL Marketo Measure] verwijzen naar en distribueren over de Attribution Touchpoints (BAT&#39;s).

## Beste praktijken {#best-practice}

Houd bij het instellen van een Aangepast inkomstenbedrag rekening met de volgende aanbevolen procedures om ervoor te zorgen dat [!DNL Marketo Measure] toewijzingsgegevens zijn nauwkeurig en consistent!

Denk aan de volgende zaken:

* Selecteer het opbrengstgebied dat voor alle Kansen nauwkeurig en gebruikt is
   * ARR of Total Contract Value us aanbevolen
* Gebruik geen veld met een formule
* Als u een Aangepast bedrag van Inkomsten voor valutaomrekeningen gebruikt, [!UICONTROL Marketo Measure Multiple Currencies] in plaats daarvan heeft de voorkeur aan functionaliteit.
   * De [!DNL Marketo Measure] Functionaliteit voor meerdere valuta&#39;s verwijst naar de conversiekoersen die zijn vastgesteld in [!DNL Salesforce] zo goed mogelijk te zorgen voor de onderlinge afstemming van de omrekening van valuta&#39;s. Hierdoor kunt u doorgaan met het gebruik van de standaard &#39;Amount&#39; (SFDC Default) of een ander aangepast veld Bedrag dat betrekking heeft op de [!DNL Salesforce] omrekeningskoersen.
* Als u het veld Bedrag bijwerkt, wilt u [!DNL Marketo Measure] gebruiken om naar te verwijzen, Data Loader gebruiken om eerdere opportuniteiten bij te werken om ervoor te zorgen dat uw inkomstengegevens consistent zijn en dat het juiste veld wordt gevuld via de workflow

## Aanbevolen werkwijzen voor onderhoud {#best-practice-for-maintenance}

Als u jaarlijks de instellingen van uw inkomstenbedrag controleert, worden de toewijzingsgegevens correct en afgestemd op de rest van de inkomstenrapportage van uw organisatie.

Als u een Bedrag van de Inkomsten van de Douane gebruikt, controleer uw opbrengstopstelling als volgt.

* In uw [!DNL Marketo Measure] account, ga naar de &#39;[!UICONTROL Opportunities]&quot;sectie onder CRM
* Identificeer [!UICONTROL Custom Opportunity Amount] Veld, hier uw [!UICONTROL custom revenue amount API] veld moet worden vermeld
* Bevestig dat dit nog steeds het juiste veld is
* Bevat ook uw [!DNL Salesforce] Admin bevestigt dat de workflow voor de aangepaste inkomstenhoeveelheid in [!DNL Salesforce] is nog actief

Naast een jaarlijkse evaluatie, kunnen bepaalde organisatorische veranderingen de behoefte om uw opstelling van de opbrengstbedragen te herzien...

* Omzet in uw marketingteam
* Wijzigingen in het veld Aangepaste inkomsten
* Wijzigingen in de manier waarop inkomsten worden gerapporteerd door de organisatie

>[!MORELIKETHIS]
>
>* [Een veld Aangepaste omzettingsbedrag gebruiken](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md)
>* [Veld voor aangepaste hoeveelheid bijwerken met gegevenslader](/help/advanced-marketo-measure-features/custom-revenue-amount/using-data-loader-to-update-marketo-measure-custom-amount-field.md)
>* [Overzicht van Meervoudig Valuta](/help/advanced-marketo-measure-features/multi-currency/overview.md)
>* [Instellingen voor meerdere valuta](/help/advanced-marketo-measure-features/multi-currency/settings.md)
