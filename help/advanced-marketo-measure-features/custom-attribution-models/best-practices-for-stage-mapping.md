---
description: Aanbevolen procedures voor werkgebiedtoewijzing - [!DNL Marketo Measure] - Productdocumentatie
title: Aanbevolen procedures voor werkgebiedtoewijzing
exl-id: 1ed380a1-4a3a-4761-b70f-cdf2e290329d
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 0%

---

# Aanbevolen procedures voor werkgebiedtoewijzing {#best-practices-for-stage-mapping}

## Overzicht {#overview}

Het gedeelte Werkgebiedtoewijzing van uw [!DNL Marketo Measure] beschrijft de stappen die [!DNL Marketo Measure] trekt automatisch van uw CRM en om het even welke douanestadia u als het gebruiken van het Model van de Attributie van de Douane hebt bepaald. De geldigheid van uw [!DNL Marketo Measure] gegevens berusten op de juiste volgorde van deze fasen, zodat [!DNL Marketo Measure] U kunt uw trechter nauwkeurig begrijpen en de voortgang van de registratie door deze trechter heen.

In het gedeelte Werkgebiedtoewijzing van uw [!DNL Marketo Measure] instantie, zult u zowel actieve als inactieve stadia van uw CRM zien. Orden alle fasen naar beste vermogen in overeenstemming met de huidige werking van uw trechter.

Een extra eigenschap die in deze sectie wordt beheerd is de Staven van het Trechter, die u de capaciteit geven om stadia aan het trechter toe te voegen zonder attributie toe te passen. De Stages van de trechter zullen als Aanraakpunten worden gevolgd en zullen op het gebied van AanraakpuntPosities in uw CRM bevolken. Deze treinstappen zullen ook in verschillende reisborden worden vertegenwoordigd [!DNL Marketo Measure] Detecteren.

## Aanbevolen werkwijzen {#best-practices}

Of u nu voor het eerst de Stage Mapping evalueert of alleen de trechter-volgorde controleert, het is belangrijk dat u de volgende aanbevolen procedures in acht neemt.

* Volgorde is alles!
   * Overweeg [!DNL Marketo Measure] pulls in zowel actieve als inactieve stadia van uw CRM, bevestig dat om het even welk stadium dat op een Lood/Contact of Kans kon worden gebruikt worden gegroepeerd en dienovereenkomstig worden bevolen
* Wanneer u een aangepast werkgebied definieert, moet het bijhouden van de veldgeschiedenis zijn ingeschakeld voor alle velden die worden gebruikt om het werkgebied te definiëren
* Gebruik geen formuleringsveld om een aangepast werkgebied te definiëren
   * Een Booleaans veld is de aanbevolen werkwijze
* Merk op dat de sectie van de Lood of van het Stadium van het Contact in Verloren, Open, en Omgezet wordt verdeeld; Controleren of de fasen zich in de juiste werkgebiedsectie bevinden
   * Als u een werkgebied in de onjuiste werkgebiedsectie hebt, kan dit leiden tot een zeer onjuiste [!DNL Marketo Measure] data
* Merk op dat de het werkgebiedsectie van de Kans in Verlies, Open, en Won wordt verdeeld; Controleren of de fasen zich in de juiste werkgebiedsectie bevinden
   * Als u een werkgebied in de onjuiste werkgebiedsectie hebt, kan dit leiden tot een zeer onjuiste [!DNL Marketo Measure] inkomstengegevens over inkomsten of pijpleidingen
* Gebruik geen dubbele werkgebiednamen (uw systeem detecteert deze en verwijdert er automatisch een).

## Aanbevolen procedures voor onderhoud {#best-practices-for-maintenance}

Als u eenmaal per jaar uw werkgebiedtoewijzing controleert, weet u zeker dat uw opportuniteitsgegevens in [!DNL Marketo Measure] nauwkeurig en up-to-date is.

Andere redenen die een revisie van de werkgebiedtoewijzing kunnen activeren, zijn onder andere..

* Omzet in uw marketingteam
* Eventuele wijzigingen in uw CRM-fasen
* Updates van de trechter van uw organisatie
* Onjuiste inkomstengegevens worden weergegeven in uw [!DNL Marketo Measure] rapportage

>[!MORELIKETHIS]
>
>[Het verschil tussen de fasen van de treinen en de fase van het aangepaste model](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md#the-difference-between-funnel-stages-and-custom-model-stages)
