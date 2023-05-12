---
description: Domeinbeheer - [!DNL Marketo Measure] - Productdocumentatie
title: Domeinbeheer
exl-id: 4db287a0-0267-463c-a359-266b41f15c59
source-git-commit: 148cc203f1fd2a3b90771f2223bbacacdcfad7b0
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 0%

---

# Domeinbeheer {#domain-management}

Voor met IMS ingeschakelde huurders die worden uitgevoerd [!DNL Marketo Measure] in de Experience Cloud Interface, [!DNL Marketo Measure] verstrekt een interface die gebruikers toestaat om hun eigen lijst van domeinen te beheren. [!DNL Marketo Measure] gebruikers moeten eerst alle domeinen verifiëren die ze in de [Adobe Admin Console](https://adminconsole.adobe.com/). Zodra domeinen in de Admin Console worden geverifieerd, kunnen de gebruikers beheren als [!DNL Marketo Measure] gebruikt deze domeinen voor het volgen van websiteverkeer.

## Domeinen toevoegen in Admin Console {#adding-domains-in-admin-console}

IMS-gebruikers met toegang tot de Adobe Admin Console kunnen domeinen toevoegen en valideren die zij bezitten. De bevestiging van het domein impliceert het toevoegen van een DNS verslag voor elk domein en later het toestaan van de Admin Console om dat verslag te verifiëren.

![](assets/domain-management-1.png)

Instructies voor het toevoegen van domeinen vindt u in het dialoogvenster [Documentatie Admin Console](https://helpx.adobe.com/enterprise/using/set-up-identity.html#setup-domains). Wanneer een domein is toegevoegd, moet het worden [gekoppeld aan een map](https://helpx.adobe.com/enterprise/using/set-up-identity.html#link-domains-to-directories).

## Domeinen beheren in [!DNL Marketo Measure] {#managing-domains-in-marketo-measure}

Zodra een domein in de Admin Console wordt toegevoegd, [!DNL Marketo Measure] Deze record wordt regelmatig in onze database gesynchroniseerd. Deze synchronisatie vindt elke avond plaats, en ook elke keer dat een gebruiker de **[!UICONTROL Domains]** pagina in de [!DNL Marketo Measure] UI. Door gebrek, om het even welke verslagen die [!DNL Marketo Measure] de invoer zal worden onbruikbaar gemaakt, en de huurder moet elk domein manueel toelaten.

![](assets/domain-management-2.png)

Op de **[!UICONTROL Integration]** > **[!UICONTROL Domains]** pagina, ziet de gebruiker alle domeinen die zij in de Admin Console, samen met hun status hebben geregistreerd. Elk domein kan worden in- of uitgeschakeld. Als een domein wordt toegelaten, [!DNL Marketo Measure] het volgen zal om het even welk verkeer verzamelen dat op dat domein wordt gezien. Als een domein is uitgeschakeld, [!DNL Marketo Measure] zal om het even welk waargenomen verkeer dat uit dat domein komt negeren en zal geen touchpoints of andere gegevens creëren. [!DNL Marketo Measure] zal ook de uitschakeling van een domein bevestigen en waarschuwen voor de gevolgen:

![](assets/domain-management-3.png)

Het effect van het schakelen van een domein is onmiddellijk en de wijzigingen zijn niet retroactief. In de toekomst [!DNL Marketo Measure] gegevens uit uitgeschakelde domeinen na een ingestelde periode wissen.

## Statussen {#statuses}

De statussen van de Admin Console worden als volgt gecategoriseerd:

* **GEVALIDEERD**: Dit domein wordt geverifieerd in Admin Console
* **ONVERIFIEERD**: Dit domein is niet volledig geverifieerd in de Admin Console en komt niet in aanmerking voor tracking in [!DNL Marketo Measure]
* **ONGELDIG**: Dit domein is mogelijk verlopen of verwijderd uit de Admin Console. Gegevens bijhouden in [!DNL Marketo Measure] is gemarkeerd voor verwijderen
* **LEGACTIE**: Dit domein is gemaakt in [!DNL Marketo Measure] en bestaat niet in de Admin Console

De volgende statussen kunnen worden gebruikt:

* **ACTIEF**: [!DNL Marketo Measure] ontvangt momenteel gegevens van dit domein
* **UITGESCHAKELD**: Dit domein kan worden bijgehouden, maar is momenteel uitgeschakeld
* **NIET BESCHIKBAAR**: Dit domein is niet beschikbaar voor tracering omdat het niet is geverifieerd

Als u de muis boven een afzonderlijk statusitem houdt, wordt knopinfo weergegeven waarin die status nader wordt uitgelegd.

## Veelgestelde vragen {#faq}

**Wat gebeurt er wanneer een domein wordt verwijderd in de Admin Console?**

Wanneer een domein in de Admin Console wordt verwijderd, [!DNL Marketo Measure] markeert het domein als verwijderd. [!DNL Marketo Measure] zal onmiddellijk ophouden volgend verkeer op dit domein, maar zal eerder verzamelde gegevens niet verwijderen.

**Waarom kan ik geen domein toelaten?**

Er zijn verschillende redenen waarom een domein niet mag worden geselecteerd op deze pagina. Als het domein niet in de Admin Console wordt gevalideerd, is het niet beschikbaar in [!DNL Marketo Measure]. En als het domein eigendom is van een andere Adobe Org dan de huidige [!DNL Marketo Measure] huurder, is het mogelijk niet beschikbaar voor selectie.

**Hoe verwijder ik een domein uit deze lijst?**

Als voor een domein de schakeloptie &quot;enabled&quot; is uitgeschakeld, [!DNL Marketo Measure] wordt genegeerd en wordt het daadwerkelijk verwijderd uit [!DNL Marketo Measure]. Een domein permanent verwijderen uit [!DNL Marketo Measure], moet u deze uitschakelen in [!DNL Marketo Measure]en vervolgens uit de Admin Console te verwijderen.
