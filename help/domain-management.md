---
description: Richtlijnen voor domeinbeheer voor Marketo Measure-gebruikers
title: Domeinbeheer
exl-id: 4db287a0-0267-463c-a359-266b41f15c59
feature: Integration, Tracking
hidefromtoc: true
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 0%

---

# Domeinbeheer {#domain-management}

Voor IMS-huurders die [!DNL Marketo Measure] uitvoeren in de Experience Cloud Interface, biedt [!DNL Marketo Measure] een interface waarmee gebruikers hun eigen lijst met domeinen kunnen beheren. [!DNL Marketo Measure] de gebruikers moeten eerst om het even welke domeinen verifiëren die zij om in [&#x200B; Adobe Admin Console &#x200B;](https://adminconsole.adobe.com/) wensen te volgen. Zodra domeinen in de Admin Console worden geverifieerd, kunnen gebruikers beheren als [!DNL Marketo Measure] deze domeinen gebruikt voor het bijhouden van websiteverkeer.

## Domeinen toevoegen in Admin Console {#adding-domains-in-admin-console}

IMS-gebruikers met toegang tot de Adobe Admin Console kunnen domeinen die ze bezitten, toevoegen en valideren. De bevestiging van het domein impliceert het toevoegen van een DNS verslag voor elk domein en dan het toestaan van Admin Console om dat verslag te verifiëren.

![&#x200B; IMS gebruikers met toegang tot Adobe Admin Console kunnen toevoegen en &#x200B;](assets/domain-management-4.png)

De instructies voor het toevoegen van domeinen kunnen in de [&#x200B; documentatie van Admin Console &#x200B;](https://helpx.adobe.com/enterprise/using/add-domains-directories.html) worden gevonden. Zodra een domein wordt toegevoegd, moet het [&#x200B; met een folder &#x200B;](https://helpx.adobe.com/enterprise/using/add-domains-directories.html#link-domains-to-directoies) worden verbonden.

## Domeinen beheren in [!DNL Marketo Measure] {#managing-domains-in-marketo-measure}

Nadat een domein in de Admin Console is toegevoegd, synchroniseert [!DNL Marketo Measure] deze record regelmatig in de database. Deze synchronisatie vindt elke avond plaats, en ook telkens wanneer een gebruiker de pagina **[!UICONTROL Domains]** in de gebruikersinterface van [!DNL Marketo Measure] bezoekt. Door gebrek, om het even welke verslagen die [!DNL Marketo Measure] invoert worden onbruikbaar gemaakt, en de huurder moet elk domein manueel toelaten.

![&#x200B; nadat een domein in Admin Console wordt toegevoegd, Marketo Measure &#x200B;](assets/domain-management-2.png)

Op de pagina **[!UICONTROL Integration]** > **[!UICONTROL Domains]** ziet de gebruiker alle domeinen die hij of zij in de Admin Console heeft geregistreerd, samen met zijn of haar status. Elk domein kan worden in- of uitgeschakeld. Als een domein wordt toegelaten, verzamelt het [!DNL Marketo Measure] volgen om het even welk verkeer dat op dat domein wordt gezien. Wanneer een domein is uitgeschakeld, negeert [!DNL Marketo Measure] elk verkeer dat uit dat domein komt en worden er geen aanraakpunten of andere gegevens gemaakt. [!DNL Marketo Measure] bevestigt de uitschakeling van een domein en waarschuwt voor mogelijke vertakkingen:

![&#x200B; op de pagina van de Domeinen van de Integratie, ziet de gebruiker alle domeinen &#x200B;](assets/domain-management-3.png)

Het effect van het schakelen van een domein is onmiddellijk en de wijzigingen zijn niet retroactief. In de toekomst verwijdert [!DNL Marketo Measure] gegevens uit uitgeschakelde domeinen na een ingestelde periode.

## Statussen {#statuses}

Admin Console-statussen worden als volgt ingedeeld:

* **VALIDATED**: Dit domein wordt geverifieerd in Admin Console
* **ONVERIFIED**: Dit domein wordt niet volledig geverifieerd in Admin Console en komt niet in aanmerking voor het volgen in [!DNL Marketo Measure]
* **ONGELDIG**: Dit domein kan verlopen zijn of uit Admin Console verwijderd. Gegevens bijhouden in [!DNL Marketo Measure] is gemarkeerd voor verwijdering
* **LEGACY**: Dit domein werd gecreeerd in [!DNL Marketo Measure] en bestaat niet in Admin Console

De volgende statussen kunnen worden gebruikt:

* **ACTIEF**: [!DNL Marketo Measure] ontvangt gegevens van dit domein
* **VERBINDEN**: Dit domein is beschikbaar voor het volgen, maar is gehandicapt
* **ONBESCHIKBAAR**: Dit domein is niet beschikbaar voor het volgen omdat het niet wordt geverifieerd

Als u de muis boven een afzonderlijk statusitem houdt, wordt knopinfo weergegeven waarin die status nader wordt uitgelegd.

## Veelgestelde vragen {#faq}

**wat gebeurt wanneer een domein in Admin Console wordt verwijderd?**

Wanneer een domein in de Admin Console wordt verwijderd, markeert [!DNL Marketo Measure] het domein als verwijderd. [!DNL Marketo Measure] houdt onmiddellijk het volgen van verkeer op dit domein op, maar zal geen eerder verzamelde gegevens verwijderen.

**waarom ben ik geen domein kan toelaten?**

Er zijn verschillende redenen waarom een domein niet mag worden geselecteerd op deze pagina. Als het domein niet wordt gevalideerd in de Admin Console, is het niet beschikbaar in [!DNL Marketo Measure] . Als het domein eigendom is van een andere Adobe Org dan de huidige [!DNL Marketo Measure] huurder, is het mogelijk niet beschikbaar voor selectie.

**hoe ik een domein uit deze lijst verwijder?**

Als voor een domein de schakeloptie &#39;enabled&#39; is uitgeschakeld, negeert [!DNL Marketo Measure] het domein en wordt het feitelijk verwijderd uit [!DNL Marketo Measure] . Als u een domein permanent uit [!DNL Marketo Measure] wilt verwijderen, moet u het uitschakelen in [!DNL Marketo Measure] en het vervolgens verwijderen uit de Admin Console.
