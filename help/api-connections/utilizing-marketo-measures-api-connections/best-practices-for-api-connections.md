---
description: Aanbevolen procedures voor API-verbindingen - [!DNL Marketo Measure]
title: Aanbevolen procedures voor API-verbindingen
exl-id: b8550e4e-a567-427f-b5d3-50232553a066
feature: APIs, Integration
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 0%

---

# Aanbevolen procedures voor API-verbindingen {#best-practices-for-api-connections}

## Overzicht {#overview}

[!DNL Marketo Measure] biedt API-verbindingen aan met [!DNL Google AdWords], [!DNL Microsoft Bing Ads], [!DNL Facebook Ads]en LinkedIn. Deze API-verbindingen maken [!DNL Marketo Measure] om verschillende gegevens van uw advertentieplatforms te verzamelen, die vervolgens kunnen worden vermeld in uw gegevens van het aanraakpunt voor kopers. Een belangrijke functie voor deze API-verbindingen is de mogelijkheid om gegevens automatisch door te geven, waardoor u en uw team de tijd en moeite besparen die nodig zijn om gegevens handmatig te uploaden voor het melden van investeringsrendement. Het instellen van deze API-verbindingen is niet verplicht voor [!DNL Marketo Measure] om die kanalen te volgen, maar zij verstrekken waardevolle korrelige details die uw rapportering verbeteren.

De [!DNL Marketo Measure] API-verbindingen zijn een onschatbaar aspect van uw account en onze aanbevelingen voor best practices helpen u en uw team onze verbindingen optimaal te benutten.

## Beste praktijken {#best-practice}

Ongeacht het advertentieplatform dat u aansluit, zijn de volgende richtlijnen belangrijk om in mening te zijn!

* Een beheerder gebruiken om verbinding te maken
* U kunt meerdere advertentieraccounts verbinden voor één platform
* Sluit alle mogelijke advertentierapporten aan om uw uitgavenrapporten zoveel mogelijk te automatiseren
* Implementeer altijd een sjabloon voor bijhouden, indien beschikbaar. De sjabloon zorgt ervoor dat zelfs als de advertentie-account wordt losgekoppeld, [!DNL Marketo Measure] nog steeds korrelige details kunnen weergeven

Om elk te optimaliseren [!DNL Marketo Measure] API, voldoet aan de volgende aanbevolen procedures.

**[!DNL Facebook]**: Verbinding maken met automatische labeling

Exporteer uw advertentiegeschiedenis naar een csv voordat u automatische labeling inschakelt. Als u automatische labeling inschakelt, worden de omzetgeschiedenis en de sociale proefdruk van alle advertenties opnieuw ingesteld die zijn gecodeerd door [!DNL Marketo Measure].

Door onze aanbevelingen voor beste praktijken na te leven, [!DNL Marketo Measure] [!DNL Facebook] API kan:

* Alle tags automatisch labelen [!DNL Facebook] Bijdragen met de nodige [!DNL Marketo Measure] parameter `_bf ={creative}`
* Download- en kostengegevens over alle actieve [!DNL Facebook] advertenties

>[!NOTE]
>
>Er is geen volgsjabloon voor [!DNL Facebook], baseert de API zich op de auto-geëtiketteerde (_bf) parameter om de advertentiedetails te verzamelen.

**AdWords**: Een sjabloon voor bijhouden op accountniveau implementeren en automatische labeling inschakelen

[!DNL Marketo Measure] Het verdient aanbeveling om een sjabloon voor reeksspatiëring op accountniveau, op campagnereniveau of op groepsniveau toevoegen te gebruiken, omdat hiermee parameters voor alle advertenties kunnen worden toegevoegd en afgetrokken zonder dat het risico bestaat dat de advertentie wordt onderbroken of verwijderd.

Door onze aanbevelingen voor beste praktijken na te leven, [!DNL Marketo Measure] De API voor AdWords kan:

* Alle Advertentiewoorden automatisch van labels voorzien met de [!DNL Marketo Measure] parameters van `_bk={keyword}, _bt={creative}, _bm={matchtype}, _bn={network}, _bg={adgroupID}`
* Informatie over alle actieve advertentie-advertenties downloaden en kosten

**Bing**: Een sjabloon voor bijhouden op accountniveau implementeren en automatische labeling inschakelen

Er bestaat geen risico dat advertentiegeschiedenis verloren gaat wanneer u uw [!DNL Bing] API-verbinding, in tegenstelling tot sommige andere API-verbindingen.

Door onze aanbevelingen voor beste praktijken na te leven, [!DNL Marketo Measure] Bing API kan:
* Alle Bing Ads automatisch labelen met de volgende parameters van `_bt={adid}, utm_medium=cpc, utm_source=bing, utm_term={keyword}`
* Downloaden en kostengegevens over alle actieve blogadvertenties

**LinkedIn**: Verbinding maken met automatische labeling

Als u automatische labeling inschakelt, wordt een Delen opnieuw gemaakt en in een nieuw Creative-programma geplaatst. De oude Creative-code wordt dan gearchiveerd.

Door onze aanbevelingen voor beste praktijken na te leven, [!DNL Marketo Measure] LinkedIn API kan:

* Automatisch alle LinkedIn-advertenties van het type Gesponsorde inhoud voorzien van de vereiste tags [!DNL Marketo Measure] parameter _bl={creativeId}. Deze parameter haalt de creatieve id uit die [!DNL Marketo Measure] om de campagne en de creatieve informatie op te lossen.
* Download- en kostengegevens over alle actieve en ondersteunde [!DNL LinkedIn] advertenties

>[!NOTE]
>
>Er is geen volgsjabloon voor [!DNL LinkedIn], baseert de API zich op de auto-geëtiketteerde (_bl) parameter om alle mogelijke ad details te verzamelen.

## Aanbevolen werkwijzen voor onderhoud {#best-practice-for-maintenance}

Terwijl het volgen van onze beste praktijken u zal beschermen tegen het verliezen van gegevens als losgemaakt, adviseren wij nog dat u regelmatig, maandelijks indien mogelijk uw verbinding herziet. Dit is een eenvoudige visuele controle van de [!UICONTROL Connections] in uw [!DNL Marketo Measure] om er zeker van te zijn dat er geen rode-sleutelpictogrammen aanwezig zijn, wordt een losgekoppelde account gesignaleerd.

Wanneer een API-verbonden account wordt losgekoppeld, [!DNL Marketo Measure] kan geen gegevens ophalen in of tags toewijzen aan nieuwe advertenties. Daarom adviseren wij altijd het uitvoeren van een het volgen malplaatje als mogelijk. De sjabloon zorgt ervoor dat zelfs als de advertentie-account wordt losgekoppeld, [!DNL Marketo Measure] kan de advertenties nog steeds labelen en de details van de granulaire advertentie eruit halen. Zodra opnieuw aangesloten, zullen de uitgavengegevens terugvullen en de verstoring aan uw Betaalde Kanaalrapportering is minimaal.

Redenen voor het verbreken en opnieuw autoriseren zijn onder meer..

* Wachtwoord wijzigen in de persoonaccount waarmee verbinding wordt gemaakt
* Die persoon is niet meer bij het bedrijf
* Updates van de API&#39;s

Als uw team een van de bovenstaande scenario&#39;s heeft ervaren, controleert u uw API-verbindingen in het dialoogvenster [!DNL Marketo Measure] om ervoor te zorgen dat ze niet opnieuw hoeven te worden geautoriseerd.

>[!MORELIKETHIS]
>
>* [Geïntegreerde AD-platforms (API&#39;s)](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md)
>* [De invloed van Bodmanager-programma&#39;s [!DNL Marketo Measure]](/help/api-connections/utilizing-marketo-measures-api-connections/how-bid-management-tools-affect-marketo-measure.md)
>* [[!DNL Marketo Measure] API-parameters beschreven](/help/api-connections/utilizing-marketo-measures-api-connections/marketo-measure-parameters.md)
>* [Facebook API-overzicht](/help/api-connections/utilizing-marketo-measures-api-connections/facebook-api.md)
>* [[!DNL LinkedIn] Overzicht van integratie](/help/api-connections/utilizing-marketo-measures-api-connections/linkedin-integration.md)
>* [Overzicht van AdWords-integratie](/help/api-connections/utilizing-marketo-measures-api-connections/understanding-marketo-measure-adwords-tagging.md)
>* [Aangesloten API-accounts opnieuw autoriseren](/help/api-connections/utilizing-marketo-measures-api-connections/reauthorizing-connected-accounts.md)
