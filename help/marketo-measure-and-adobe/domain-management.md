---
description: Domeinbeheer - [!DNL Marketo Measure]
title: Domeinbeheer
exl-id: 4db287a0-0267-463c-a359-266b41f15c59
feature: Integration, Tracking
source-git-commit: 4c68fa08797c252a89ba097c723fb8afee82451f
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 0%

---

# Domeinbeheer {#domain-management}

Voor met IMS ingeschakelde huurders die worden uitgevoerd [!DNL Marketo Measure] in de interface van het Experience Cloud, [!DNL Marketo Measure] verstrekt een interface die gebruikers toestaat om hun eigen lijst van domeinen te beheren. [!DNL Marketo Measure] gebruikers moeten eerst alle domeinen controleren die ze in de [Adobe Admin Console](https://adminconsole.adobe.com/). Zodra domeinen in de Admin Console worden geverifieerd, kunnen de gebruikers beheren als [!DNL Marketo Measure] gebruikt deze domeinen voor het volgen van websiteverkeer.

## Domeinen toevoegen in Admin Console {#adding-domains-in-admin-console}

IMS-gebruikers met toegang tot de Adobe Admin Console kunnen domeinen die ze bezitten, toevoegen en valideren. De bevestiging van het domein impliceert het toevoegen van een DNS verslag voor elk domein en dan het toestaan van de Admin Console om dat verslag te verifiëren.

![](assets/domain-management-1.png)

Instructies voor het toevoegen van domeinen vindt u in het dialoogvenster [Documentatie Admin Console](https://helpx.adobe.com/enterprise/using/add-domains-directories.html). Wanneer een domein is toegevoegd, moet het worden [gekoppeld aan een map](https://helpx.adobe.com/enterprise/using/add-domains-directories.html#link-domains-to-directoies).

## Domeinen beheren in [!DNL Marketo Measure] {#managing-domains-in-marketo-measure}

Nadat een domein in de Admin Console wordt toegevoegd, [!DNL Marketo Measure] synchroniseert deze record regelmatig in de database. Deze synchronisatie vindt elke avond plaats, en ook elke keer dat een gebruiker de **[!UICONTROL Domains]** pagina in de [!DNL Marketo Measure] UI. Standaard alle records die [!DNL Marketo Measure] de invoer wordt onbruikbaar gemaakt, en de huurder moet elk domein manueel toelaten.

![](assets/domain-management-2.png)

Op de **[!UICONTROL Integration]** > **[!UICONTROL Domains]** pagina, ziet de gebruiker alle domeinen die zij in de Admin Console, samen met hun status hebben geregistreerd. Elk domein kan worden in- of uitgeschakeld. Als een domein wordt toegelaten, [!DNL Marketo Measure] het volgen verzamelt om het even welk verkeer dat op dat domein wordt gezien. Als een domein is uitgeschakeld, [!DNL Marketo Measure] negeert om het even welk verkeer dat uit dat domein komt en leidt tot geen aanraakpunten of andere gegevens. [!DNL Marketo Measure] bevestigt de uitschakeling van een domein en waarschuwt voor eventuele vertakkingen:

![](assets/domain-management-3.png)

Het effect van het schakelen van een domein is onmiddellijk en de wijzigingen zijn niet retroactief. In de toekomst [!DNL Marketo Measure] gegevens uit uitgeschakelde domeinen na een ingestelde periode wissen.

## Statussen {#statuses}

De statussen van de Admin Console worden als volgt gecategoriseerd:

* **GEVALIDEERD**: Dit domein wordt geverifieerd in Admin Console
* **ONVERIFIEERD**: Dit domein is niet volledig geverifieerd in de Admin Console en komt niet in aanmerking voor tracking in [!DNL Marketo Measure]
* **ONGELDIG**: Dit domein is mogelijk verlopen of verwijderd uit Admin Console. Gegevens bijhouden in [!DNL Marketo Measure] is gemarkeerd voor verwijderen
* **LEGACTIE**: Dit domein is gemaakt in [!DNL Marketo Measure] en bestaat niet in de Admin Console

De volgende statussen kunnen worden gebruikt:

* **ACTIEF**: [!DNL Marketo Measure] ontvangt gegevens van dit domein
* **UITGESCHAKELD**: Dit domein kan worden bijgehouden, maar is uitgeschakeld
* **NIET BESCHIKBAAR**: Dit domein is niet beschikbaar voor tracering omdat het niet is geverifieerd

Als u de muis boven een afzonderlijk statusitem houdt, wordt knopinfo weergegeven waarin die status nader wordt uitgelegd.

## Veelgestelde vragen {#faq}

**Wat gebeurt er wanneer een domein wordt verwijderd in de Admin Console?**

Wanneer een domein in de Admin Console wordt verwijderd, [!DNL Marketo Measure] markeert het domein zoals geschrapt. [!DNL Marketo Measure] houdt onmiddellijk het volgen van verkeer op dit domein op, maar zal geen eerder verzamelde gegevens verwijderen.

**Waarom kan ik geen domein toelaten?**

Er zijn verschillende redenen waarom een domein niet mag worden geselecteerd op deze pagina. Als het domein niet in de Admin Console wordt bevestigd, is het niet beschikbaar in [!DNL Marketo Measure]. En als het domein eigendom is van een andere Adobe Org dan de huidige [!DNL Marketo Measure] huurder, is het mogelijk niet beschikbaar voor selectie.

**Hoe verwijder ik een domein uit deze lijst?**

Als voor een domein de schakeloptie &quot;enabled&quot; is uitgeschakeld, [!DNL Marketo Measure] wordt genegeerd en daadwerkelijk verwijderd uit [!DNL Marketo Measure]. Een domein permanent verwijderen uit [!DNL Marketo Measure], moet u deze uitschakelen in [!DNL Marketo Measure]en verwijder deze vervolgens uit de Admin Console.
