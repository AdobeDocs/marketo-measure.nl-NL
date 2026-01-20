---
description: Beste praktijken voor API Verbindingen -  [!DNL Marketo Measure]
title: Aanbevolen procedures voor API-verbindingen
exl-id: b8550e4e-a567-427f-b5d3-50232553a066
feature: APIs, Integration
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 0%

---

# Aanbevolen procedures voor API-verbindingen {#best-practices-for-api-connections}

## Overzicht {#overview}

[!DNL Marketo Measure] biedt API-verbindingen met [!DNL Google AdWords] , [!DNL Microsoft Bing Ads] , [!DNL Facebook Ads] en LinkedIn. Met deze API-verbindingen kan [!DNL Marketo Measure] verschillende gegevens ophalen van uw advertentieplatforms die vervolgens in uw Buyer Touchpoint-gegevens kunnen worden vermeld. Een belangrijke functie voor deze API-verbindingen is de mogelijkheid om gegevens automatisch door te geven, waardoor u en uw team de tijd en moeite besparen die nodig zijn om gegevens handmatig te uploaden voor het melden van investeringsrendement. Het is niet verplicht om deze API-verbindingen in [!DNL Marketo Measure] in te stellen om deze kanalen te volgen, maar ze bieden wel waardevolle gedetailleerde informatie die uw rapportage verbetert.

De API-verbindingen van [!DNL Marketo Measure] zijn een onschatbaar aspect van uw account en onze aanbevelingen voor best practices helpen u en uw team onze verbindingen optimaal te benutten.

## Beste praktijken {#best-practice}

Ongeacht het advertentieplatform dat u aansluit, zijn de volgende richtlijnen belangrijk om in mening te zijn!

* Een beheerder gebruiken om verbinding te maken
* U kunt meerdere advertentieraccounts verbinden voor één platform
* Sluit alle mogelijke advertentierapporten aan om uw uitgavenrapporten zoveel mogelijk te automatiseren
* Implementeer altijd een sjabloon voor bijhouden, indien beschikbaar. De sjabloon zorgt ervoor dat zelfs als de advertentieaccount wordt losgekoppeld, [!DNL Marketo Measure] nog steeds korrelige advertentiedetails kan weergeven

Volg de volgende aanbevolen procedures om elke [!DNL Marketo Measure] API te optimaliseren.

**[!DNL Facebook]**: verbinding maken met automatische labeling

Exporteer uw advertentiegeschiedenis naar een csv voordat u automatische labeling inschakelt. Als u automatische labeling inschakelt, worden de omzetgeschiedenis en de sociale proefdruk van alle advertenties die zijn gecodeerd door [!DNL Marketo Measure] opnieuw ingesteld.

Aan de hand van onze aanbevelingen voor best practices kan de [!DNL Marketo Measure] [!DNL Facebook] API:

* Alle [!DNL Facebook] Adds automatisch labelen met de benodigde [!DNL Marketo Measure] parameter `_bf ={creative}`
* Informatie over download en kosten voor alle actieve [!DNL Facebook] advertenties

>[!NOTE]
>
>Er is geen volgsjabloon voor [!DNL Facebook] . De API gebruikt de parameter auto-tagged (_bf) om de advertentiedetails te verzamelen.

**AdWords**: Voer een het volgen malplaatje op het rekeningsniveau uit en laat auto-etiketteren toe

[!DNL Marketo Measure] raadt u aan een sjabloon voor reeksspatiëring op accountniveau, op campagnereniveau of op groepsniveau toevoegen te gebruiken, omdat hiermee parameters kunnen worden toegevoegd en afgetrokken voor alle advertenties zonder dat het risico bestaat dat de advertentiehistorie wordt onderbroken of verwijderd.

Aan de hand van onze aanbevelingen voor best practices kan de API [!DNL Marketo Measure] AdWords:

* Automatisch alle Advertentiewoorden van labels voorzien met de [!DNL Marketo Measure] parameters van `_bk={keyword}, _bt={creative}, _bm={matchtype}, _bn={network}, _bg={adgroupID}`
* Informatie over alle actieve advertentie-advertenties downloaden en kosten

**Bing**: Voer een het volgen malplaatje op het rekeningsniveau uit en laat auto-etiketteren toe

Er bestaat geen risico dat advertentiegeschiedenis verloren gaat bij het instellen van de [!DNL Bing] API-verbinding, in tegenstelling tot sommige andere API-verbindingen.

Aan de hand van onze aanbevelingen voor best practices kan de [!DNL Marketo Measure] Bing API:
* Alle Bing Ads automatisch labelen met de volgende parameters van `_bt={adid}, utm_medium=cpc, utm_source=bing, utm_term={keyword}`
* Downloaden en kostengegevens over alle actieve blogadvertenties

**LinkedIn**: Verbind met auto-etiketteren

Als u automatische labeling inschakelt, wordt een Delen opnieuw gemaakt en in een nieuwe Creative geplaatst, wordt de oude Creative gearchiveerd.

Aan de hand van onze aanbevelingen voor best practices kan de [!DNL Marketo Measure] LinkedIn API:

* Automatisch alle LinkedIn-advertenties labelen die gesponsorde inhoud met de benodigde [!DNL Marketo Measure] parameter _bl= {creativeId} toevoegen. Met deze parameter wordt de creatieve id opgehaald, zodat [!DNL Marketo Measure] de campagne en creatieve informatie kan oplossen.
* Download- en kostengegevens over alle actieve en ondersteunde [!DNL LinkedIn] advertenties

>[!NOTE]
>
>Er is geen sjabloon voor bijhouden van [!DNL LinkedIn] . De API gebruikt de parameter auto-tagged (_bl) om alle mogelijke advertentiedetails te verzamelen.

## Aanbevolen werkwijzen voor onderhoud {#best-practice-for-maintenance}

Terwijl het volgen van onze beste praktijken u zal beschermen tegen het verliezen van gegevens als losgemaakt, adviseren wij nog dat u regelmatig, maandelijks indien mogelijk uw verbinding herziet. Dit is een eenvoudige visuele controle van de sectie [!UICONTROL Connections] in uw [!DNL Marketo Measure] -app om te controleren of er geen rode-sleutelpictogrammen aanwezig zijn, die een losgekoppelde account aanduiden.

Wanneer de verbinding met een API-verbonden account wordt verbroken, kan [!DNL Marketo Measure] geen gegevens ophalen in of tags toewijzen aan nieuwe advertenties. Daarom adviseren wij altijd het uitvoeren van een het volgen malplaatje als mogelijk. Met de sjabloon zorgt u ervoor dat zelfs als de advertentieaccount wordt losgekoppeld, [!DNL Marketo Measure] nog steeds in staat is om de advertenties te voorzien van tags en om details in korrelige advertenties op te vragen. Zodra opnieuw aangesloten, zullen de uitgavengegevens terugvullen en de verstoring aan uw Betaalde Kanaalrapportering is minimaal.

Redenen voor het verbreken en opnieuw autoriseren zijn onder meer..

* Wachtwoord wijzigen in de persoonaccount waarmee verbinding wordt gemaakt
* Die persoon is niet meer bij het bedrijf
* Updates van de API&#39;s

Als uw team een van de bovenstaande scenario&#39;s heeft ervaren, controleert u uw API-verbindingen in de app van [!DNL Marketo Measure] om te controleren of deze niet opnieuw hoeven te worden geautoriseerd.

>[!MORELIKETHIS]
>
>* [ Geïntegreerde Ad Platforms (APIs) ](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md)
>* [ hoe Bodmanager de Hulpmiddelen beïnvloedt  [!DNL Marketo Measure]](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md)
>* [[!DNL Marketo Measure]  Verklaarde API Parameters ](/help/api-connections/utilizing-marketo-measures-api-connections/marketo-measure-parameters.md)
>* [ Facebook API Overzicht ](/help/api-connections/utilizing-marketo-measures-api-connections/facebook-api.md)
>* [[!DNL LinkedIn]  Overzicht van de Integratie ](/help/api-connections/utilizing-marketo-measures-api-connections/linkedin-integration.md)
>* [ het Overzicht van de Integratie AdWords ](/help/api-connections/utilizing-marketo-measures-api-connections/understanding-marketo-measure-adwords-tagging.md)
>* [ opnieuw goedkeurend Verbonden API Rekeningen ](/help/api-connections/utilizing-marketo-measures-api-connections/reauthorizing-connected-accounts.md)
