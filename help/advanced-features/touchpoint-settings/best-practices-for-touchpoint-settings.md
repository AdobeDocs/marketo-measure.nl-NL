---
description: Tips en trucs voor Marketo Measure-gebruikers bij het instellen van aanraakpunten
title: Aanbevolen werkwijzen voor aanraakpuntinstellingen
exl-id: 01e314a6-e33d-45cd-aaa3-c212afec07d1
feature: Touchpoints
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 0%

---

# Aanbevolen werkwijzen voor aanraakpuntinstellingen {#best-practices-for-touchpoint-settings}

## Overzicht {#overview}

In het gedeelte [!UICONTROL Touchpoint Settings] van uw [!DNL Marketo Measure] -app kunt u regels instellen die aanraakpunten uit uw [!DNL Marketo Measure] -gegevens en verwante systemen onderdrukken of verwijderen. Deze regels kunnen u helpen om bepaalde reeksen gegevens te isoleren die niet in uw gegevens van het Aanraakpunt van de Koper te hoeven worden vertegenwoordigd of die u geen attributietekening wilt ontvangen zonder uw het volgen en gegevensinzameling te verstoren.

**de Verwijdering van het Aanraakpunt** betekent [!DNL Marketo Measure] (d.w.z. verwijdert) om het even welke Aanraakpunten van uw CRM die de regelcriteria passen. De gegevens kunnen worden gerapporteerd op het [!DNL Marketo Measure] ROI-dashboard (Discover), maar niet in de CRM. Vaak gebruikt om stress op uw gegevensopslaggrenzen binnen uw CRM te verlichten

**Onderdrukking van het Aanraakpunt** is gelijkaardig aan de Verwijdering van het Aanraakpunt, maar de gegevens KUNNEN NIET op binnen het Dashboard van ROI worden gemeld. Eventuele onderdrukte aanraakpunten zijn niet toegankelijk in de CRM- of Discover-service. De onderdrukking zal ervoor zorgen dat uw gegevens van CRM en uw Discover gegevens zullen aanpassen. Wordt vaak gebruikt om de gegevens van aanraakpunten te perfectioneren en nader te bepalen welke aanraakpuntgegevens u attributietoekening wilt ontvangen.

In uw [!DNL Marketo Measure] -app wordt de [!UICONTROL Touchpoint Settings] -sectie opgedeeld in vier belangrijke secties. Elke sectie onderdrukt of verwijdert een andere set gegevens. Gebruik de onderstaande toets om ervoor te zorgen dat uw regels de gewenste aanraakpunten onderdrukken of verwijderen.

* Aanraakpunten met kopers verwijderen uit CRM
   * Gebruik deze sectie wanneer u een regel wilt tot stand brengen die **gegevens van Buyer Touchpoint** zal verwijderen (touchpoints die aan het individu, niet de kans) van uw **CRM** worden geassocieerd
* Aanraakpunten met kopers onderdrukken vanuit CRM
   * Gebruik deze sectie wanneer u een regel wilt tot stand brengen die **gegevens van Buyer Touchpoint** zal verwijderen (de touchpoints die aan het individu, niet de kans) van uw **CRM** en **ontdekken**
* Aanraakpunten voor koperkenmerken verwijderen uit CRM
   * Gebruik deze sectie wanneer u een regel wilt tot stand brengen die **Buyer Attribution Touchpoint** gegevens (touchpoints zal verwijderen die aan de kans en de opbrengst) van uw **CRM** worden geassocieerd
* Aanraakpunten voor koperkenmerken onderdrukken vanuit CRM
   * Gebruik deze sectie wanneer u een regel wilt tot stand brengen die **Buyer Attribution Touchpoint** gegevens (de touchpoints zal verwijderen die aan de kans en de opbrengst) van uw **CRM** en **ontdekken**

## Beste praktijken {#best-practice}

Denk aan de volgende best practices, of u nu voor het eerst regels voor het instellen van aanraakpunten opstelt of deze controleert op nauwkeurigheid.

* Stel de lijst met gegevens in die u wilt onderdrukken of verwijderen voordat u de regels maakt.
* Identificeer precies welke gebieden duidelijk de regel of de regels zullen aangeven u vestiging
* Zorg ervoor u de correcte exploitant voor de regel hebt gespecificeerd
* Controleer met behulp van de bovenstaande toets of uw regel is opgegeven in het juiste gedeelte van de Instellingen voor aanraakpunten
* Test uw regels alvorens hen uit te voeren door de regellogica in een Buyer touchpoint- rapport in CRM te herhalen om ervoor te zorgen het of het verwijderen van de gewenste gegevens onderdrukt

## Aanbevolen werkwijzen voor onderhoud {#best-practice-for-maintenance}

Het is belangrijk dat u [!UICONTROL Touchpoint Settings] controleert, omdat deze uw gegevens drastisch kan wijzigen wanneer deze niet correct zijn gedefinieerd. We raden u aan uw aanraakpuntinstellingen ten minste twee keer per jaar te controleren. Dit is een eenvoudige visuele revisie van de regels die zijn ingesteld in het gedeelte Instellingen aanraakpunt van uw [!DNL Marketo Measure] -app. Met deze revisie hebt u er zeker van dat de instellingen van uw aanraakpunt zijn bijgewerkt en dat eventuele wijzigingen daarop kunnen worden aangebracht.

Redenen om uw [!UICONTROL Touchpoint] -instellingen te bekijken zijn...

* Omzet in uw marketingteam
* Belangrijke updates van uw websitestructuur
* Identificatie van aanraakpuntgegevens die niet langer nuttig zijn
   * Telkens wanneer u aanraakpuntgegevens tegenkomt die volgens u geen attributietekort mogen ontvangen, zijn [!DNL touchpoint suppression] -regels de functionaliteit om ervoor te zorgen dat uw gegevens zo schoon en nauwkeurig mogelijk zijn.
* Wijzigingen in de velden die worden gebruikt om de onderdrukking- of verwijderingsregels te definiëren

>[!MORELIKETHIS]
>
>* [ het Overzicht van de Verwijdering en van de Onderdrukking van het Aanraakpunt ](/help/advanced-features/touchpoint-settings/touchpoint-removal-and-touchpoint-suppression.md)
>* [ waarom de Aanraakpunten nooit zouden moeten worden geschrapt ](/help/advanced-features/touchpoint-settings/why-you-should-never-delete-touchpoints.md)
>* [ Aanraakpunten van de Koper (BT) vs Aanraakpunten van de Attributie van de Koper (BAT) ](/help/configuration-and-setup/getting-started-with-marketo-measure/difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints.md)

