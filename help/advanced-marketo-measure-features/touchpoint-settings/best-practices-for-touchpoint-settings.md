---
description: Aanbevolen procedures voor aanraakpuntinstellingen - [!DNL Marketo Measure]
title: Aanbevolen werkwijzen voor aanraakpuntinstellingen
exl-id: 01e314a6-e33d-45cd-aaa3-c212afec07d1
feature: Touchpoints
source-git-commit: 518a984b0d8d640290bd9b637221fcdc0948e5b9
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 0%

---

# Aanbevolen werkwijzen voor aanraakpuntinstellingen {#best-practices-for-touchpoint-settings}

## Overzicht {#overview}

De [!UICONTROL Touchpoint Settings] deel van uw [!DNL Marketo Measure] kunt u regels instellen die aanraakpunten uit uw [!DNL Marketo Measure] gegevens en aanverwante systemen. Deze regels kunnen u helpen om bepaalde reeksen gegevens te isoleren die niet in uw gegevens van het Aanraakpunt van de Koper te hoeven worden vertegenwoordigd of die u geen attributietekening wilt ontvangen zonder uw het volgen en gegevensinzameling te verstoren.

**Aanraakpunt verwijderen** middelen [!DNL Marketo Measure] alle aanraakpunten uit uw CRM die aan de criteria van de regel voldoen, worden gewist (d.w.z. verwijderd). De gegevens kunnen worden gerapporteerd binnen de [!DNL Marketo Measure] ROI Dashboard (Discover), maar niet in CRM. Vaak gebruikt om stress op uw gegevensopslaggrenzen binnen uw CRM te verlichten

**Aanraakpuntonderdrukking** is vergelijkbaar met het verwijderen van aanraakpunten, maar de gegevens kunnen NIET worden gerapporteerd op het ROI-dashboard. Eventuele onderdrukte aanraakpunten zijn niet toegankelijk in de CRM- of Discover-service. De onderdrukking zal ervoor zorgen dat uw gegevens van CRM en uw Discover gegevens zullen aanpassen. Wordt vaak gebruikt om de gegevens van aanraakpunten te perfectioneren en nader te bepalen welke aanraakpuntgegevens u attributietoekening wilt ontvangen.

In uw [!DNL Marketo Measure] de [!UICONTROL Touchpoint Settings] deze sectie wordt uitgesplitst in vier hoofdsecties. Elke sectie onderdrukt of verwijdert een andere set gegevens. Gebruik de onderstaande toets om ervoor te zorgen dat uw regels de gewenste aanraakpunten onderdrukken of verwijderen.

* Aanraakpunten met kopers verwijderen uit CRM
   * Gebruik deze sectie als u een regel wilt maken die wordt verwijderd **Aanraakpuntgegevens koper** (de aanraakpunten die aan het individu zijn gekoppeld, niet de mogelijkheid) van uw **CRM**
* Aanraakpunten met kopers onderdrukken vanuit CRM
   * Gebruik deze sectie als u een regel wilt maken die wordt verwijderd **Aanraakpuntgegevens koper** (de aanraakpunten die aan het individu zijn gekoppeld, niet de mogelijkheid) van uw **CRM** en **Discover**
* Aanraakpunten voor koperkenmerken verwijderen uit CRM
   * Gebruik deze sectie als u een regel wilt maken die wordt verwijderd **Aanraakpunt koperkenmerk** gegevens (de aanraakpunten die zijn gekoppeld aan de mogelijkheid en de opbrengst) van uw **CRM**
* Aanraakpunten voor koperkenmerken onderdrukken vanuit CRM
   * Gebruik deze sectie als u een regel wilt maken die wordt verwijderd **Aanraakpunt koperkenmerk** gegevens (de aanraakpunten die zijn gekoppeld aan de mogelijkheid en de opbrengst) van uw **CRM** en **Discover**

## Beste praktijken {#best-practice}

Ongeacht of u regels voor het instellen van aanraakpunten voor het eerst vaststelt of alleen controleert of deze correct zijn, houd dan rekening met de volgende aanbevolen procedures.

* Stel de lijst met gegevens in die u wilt onderdrukken of verwijderen voordat u de regels maakt.
* Identificeer precies welke gebieden duidelijk de regel of de regels zullen aangeven u vestiging
* Zorg ervoor u de correcte exploitant voor de regel hebt gespecificeerd
* Controleer met behulp van de bovenstaande toets of uw regel is opgegeven in het juiste gedeelte van de Instellingen voor aanraakpunten
* Test uw regels alvorens hen uit te voeren door de regellogica in een Buyer touchpoint- rapport in CRM te herhalen om ervoor te zorgen het of het verwijderen van de gewenste gegevens onderdrukt

## Aanbevolen werkwijzen voor onderhoud {#best-practice-for-maintenance}

Uw [!UICONTROL Touchpoint Settings] is belangrijk omdat deze uw gegevens drastisch kunnen wijzigen wanneer ze niet op de juiste wijze zijn gedefinieerd. We raden u aan uw aanraakpuntinstellingen ten minste twee keer per jaar te controleren. Dit is een eenvoudige visuele revisie van de regels die zijn ingesteld in het gedeelte Aanraakpuntinstellingen van uw [!DNL Marketo Measure] app. Met deze revisie hebt u er zeker van dat de instellingen van uw aanraakpunt zijn bijgewerkt en dat eventuele wijzigingen daarop kunnen worden aangebracht.

Redenen om uw [!UICONTROL Touchpoint] Instellingen zijn inclusief...

* Omzet in uw marketingteam
* Belangrijke updates van uw websitestructuur
* Identificatie van aanraakpuntgegevens die niet langer nuttig zijn
   * Telkens wanneer je aanraakpuntgegevens tegenkomt die je niet zou moeten ontvangen, [!DNL touchpoint suppression] regels zijn de functionaliteit om ervoor te zorgen dat uw gegevens zo schoon en nauwkeurig mogelijk zijn.
* Wijzigingen in de velden die worden gebruikt om de onderdrukking- of verwijderingsregels te definiëren

>[!MORELIKETHIS]
>
>* [Overzicht van het verwijderen en onderdrukken van aanraakpunten](/help/advanced-marketo-measure-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md)
>* [Waarom aanraakpunten nooit mogen worden verwijderd](/help/advanced-marketo-measure-features/touchpoint-settings/why-you-should-never-delete-touchpoints.md)
>* [Aanraakpunten koper (BT) vs Aanraakpunten koper (BBT)](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md)

