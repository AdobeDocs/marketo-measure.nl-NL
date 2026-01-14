---
description: Tips en trucs voor Stage Mapping-richtlijnen voor Marketo Measure-gebruikers
title: Aanbevolen procedures voor werkgebiedtoewijzing
exl-id: 1ed380a1-4a3a-4761-b70f-cdf2e290329d
feature: Tracking, Custom Models
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 0%

---

# Aanbevolen procedures voor werkgebiedtoewijzing {#best-practices-for-stage-mapping}

## Overzicht {#overview}

Het gedeelte Werkgebiedtoewijzing van uw [!DNL Marketo Measure] -account bevat een overzicht van de fasen die [!DNL Marketo Measure] automatisch ophaalt vanuit uw CRM en van eventuele aangepaste stadia die u hebt gedefinieerd met het aangepaste kenmerkingsmodel. De geldigheid van uw [!DNL Marketo Measure] -gegevens is afhankelijk van de juiste volgorde van deze fasen, zodat [!DNL Marketo Measure] uw funnel en de voortgang van records in de hele funnel nauwkeurig kan begrijpen.

In de sectie Werkgebiedtoewijzing van uw [!DNL Marketo Measure] -instantie ziet u zowel actieve als inactieve stadia van uw CRM. U kunt alle fasen optimaal afstemmen op de huidige funnel.

Een extra functie die in deze sectie wordt beheerd, zijn Funnel-fasen, waarmee u fasen aan de funnel kunt toevoegen zonder toewijzing toe te passen. Funnel-werkruimten worden bijgehouden als aanraakpunten en worden ingevuld in het veld Aanraakpuntposities in uw CRM-systeem. Deze Funnel-fasen worden ook vertegenwoordigd in verschillende reisborden in [!DNL Marketo Measure] Discover.

## Aanbevolen procedures {#best-practices}

Of u nu voor het eerst de Stage Mapping evalueert of alleen de funnel-bestelling controleert, het is belangrijk dat u de volgende tips in acht neemt.

* Volgorde is alles!
   * Als u [!DNL Marketo Measure] stapels in zowel actieve als inactieve stadia van uw CRM in overweging neemt, moet u bevestigen dat elk werkgebied dat kan worden gebruikt voor een lead/contact of opportunity, wordt gegroepeerd en dienovereenkomstig wordt geordend
* Wanneer u een aangepast werkgebied definieert, moet het bijhouden van de veldgeschiedenis zijn ingeschakeld voor alle velden die worden gebruikt om het werkgebied te definiëren
* Gebruik geen formuleringsveld om een aangepast werkgebied te definiëren
   * Een Booleaans veld is de aanbevolen werkwijze
* Merk op dat de sectie Lood of Contactgebied is onderverdeeld in Verloren, Openen en Omgezet; controleer of de stappen zich in hun juiste werkgebiedsectie bevinden
   * Een werkgebied in de onjuiste werkgebiedsectie kan resulteren in zeer onjuiste [!DNL Marketo Measure] -gegevens
   * Als u een klant van Marketo Measure Ultimate bent en uw StandaardVoorwerp Dashboard als Contact hebt geplaatst, gebruik niet de hieronder twee gebieden specifiek voor Lood ([&#x200B; leert meer &#x200B;](/help/data-integrity-requirement.md){target="_blank"}).
      * b2b.personStatus
      * b2b.isConverted
* Merk op dat de sectie van het stadium van de Kans in Verloren, Open, en Won wordt verdeeld; bevestigt dat de stadia in hun aangewezen werkgebiedsectie zijn
   * Als een werkgebied in het onjuiste werkgebied staat, kunnen de inkomsten of de inkomsten uit de pijplijn sterk onjuist zijn[!DNL Marketo Measure]
* Gebruik geen dubbele werkgebiednamen (uw systeem detecteert deze en verwijdert er automatisch een).
* Als u een regel wilt instellen die NULL-waarden controleert, laat u het tekstvak Waarde leeg.

## Aanbevolen procedures voor onderhoud {#best-practices-for-maintenance}

Als u eenmaal per jaar uw werkgebiedtoewijzing controleert, worden de opportuniteitsgegevens in [!DNL Marketo Measure] nauwkeurig en up-to-date gehouden.

Andere redenen die een revisie van de werkgebiedtoewijzing kunnen activeren, zijn onder andere..

* Omzet in uw marketingteam
* Eventuele wijzigingen in uw CRM-fasen
* Updates van de funnel van uw organisatie
* Onjuiste inkomstengegevens weergeven in de [!DNL Marketo Measure] -rapportage

>[!MORELIKETHIS]
>
>[&#x200B; het Verschil tussen de Stages van Funnel en de Stages van het Model van de Douane &#x200B;](/help/channel-tracking-and-setup/custom-attribution-model-and-setup.md)
