---
description: Aanbevolen procedures voor werkgebiedtoewijzing - [!DNL Marketo Measure]
title: Aanbevolen procedures voor werkgebiedtoewijzing
exl-id: 1ed380a1-4a3a-4761-b70f-cdf2e290329d
feature: Tracking, Custom Models
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 0%

---

# Aanbevolen procedures voor werkgebiedtoewijzing {#best-practices-for-stage-mapping}

## Overzicht {#overview}

Het gedeelte Werkgebiedtoewijzing van uw [!DNL Marketo Measure] beschrijft de stappen die [!DNL Marketo Measure] trekt automatisch van uw CRM en om het even welke douanestadia u als het gebruiken van het Model van de Attributie van de Douane hebt bepaald. De geldigheid van uw [!DNL Marketo Measure] gegevens berusten op de juiste volgorde van deze fasen, zodat [!DNL Marketo Measure] U kunt uw trechter nauwkeurig begrijpen en de voortgang van de registratie door deze trechter heen.

In het gedeelte Werkgebiedtoewijzing van uw [!DNL Marketo Measure] instantie, zult u zowel actieve als inactieve stadia van uw CRM zien. Orden alle fasen naar het beste van uw mogelijkheden in overeenstemming met hoe uw trechter vandaag is.

Een extra eigenschap die in deze sectie wordt beheerd is de Staven van het Trechter, die u de capaciteit geven om stadia aan het trechter toe te voegen zonder attributie toe te passen. De Stages van de trechter zullen als Aanraakpunten worden gevolgd en zullen op het gebied van AanraakpuntPosities in uw CRM bevolken. Deze treinstappen zullen ook in verschillende reisborden worden vertegenwoordigd [!DNL Marketo Measure] Detecteren.

## Aanbevolen procedures {#best-practices}

Of u nu voor het eerst de Stage Mapping evalueert of alleen de trechter-volgorde controleert, het is belangrijk dat u de volgende aanbevolen procedures in acht neemt.

* Volgorde is alles!
   * Overweeg [!DNL Marketo Measure] pulls in zowel actieve als inactieve stadia van uw CRM, bevestig dat om het even welk stadium dat op een Lood/Contact of Kans kon worden gebruikt worden gegroepeerd en dienovereenkomstig worden bevolen
* Wanneer u een aangepast werkgebied definieert, moet het bijhouden van de veldgeschiedenis zijn ingeschakeld voor alle velden die worden gebruikt om het werkgebied te definiëren
* Gebruik geen formuleringsveld om een aangepast werkgebied te definiëren
   * Een Booleaans veld is de aanbevolen werkwijze
* Merk op dat de sectie Lood of Contactgebied is onderverdeeld in Verloren, Openen en Omgezet; controleer of de stappen zich in hun juiste werkgebiedsectie bevinden
   * Als u een werkgebied in de onjuiste werkgebiedsectie hebt, kan dit leiden tot een zeer onjuiste [!DNL Marketo Measure] data
   * Als u een Marketo Measure Ultimate-klant bent en uw standaarddashboard-object als contactpersoon hebt ingesteld, gebruikt u de onderstaande twee velden niet die specifiek zijn voor Lead ([meer informatie hier](/help/marketo-measure-ultimate/data-integrity-requirement.md){target="_blank"}).
      * b2b.personStatus
      * b2b.isConverted
* Merk op dat de sectie van het stadium van de Kans in Verloren, Open, en Won wordt verdeeld; bevestigt dat de stadia in hun aangewezen werkgebiedsectie zijn
   * Als u een werkgebied in de onjuiste werkgebiedsectie hebt, kan dit leiden tot een zeer onjuiste [!DNL Marketo Measure] inkomstengegevens over inkomsten of pijpleidingen
* Gebruik geen dubbele werkgebiednamen (uw systeem detecteert deze en verwijdert er automatisch een).
* Als u een regel wilt instellen die NULL-waarden controleert, laat u het tekstvak Waarde leeg.

## Aanbevolen procedures voor onderhoud {#best-practices-for-maintenance}

Als u eenmaal per jaar uw werkgebiedtoewijzing controleert, worden uw opportuniteitsgegevens in [!DNL Marketo Measure] nauwkeurig en up-to-date is.

Andere redenen die een revisie van de werkgebiedtoewijzing kunnen activeren, zijn onder andere..

* Omzet in uw marketingteam
* Eventuele wijzigingen in uw CRM-fasen
* Updates van de trechter van uw organisatie
* Onjuiste inkomstengegevens in uw [!DNL Marketo Measure] rapportage

>[!MORELIKETHIS]
>
>[Het verschil tussen de fasen van de treinen en de fase van het aangepaste model](/help/advanced-marketo-measure-features/custom-attribution-models/custom-attribution-model-and-setup.md#the-difference-between-funnel-stages-and-custom-model-stages)
