---
description: Richtlijnen voor offlineaangepaste kanaalinstelling voor Marketo Measure-gebruikers
title: Aangepaste kanaalinstelling offline
exl-id: c5697714-1a79-40bd-8b7c-e10768f4ef67
feature: Channels
hidefromtoc: true
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '863'
ht-degree: 0%

---

# Aangepaste kanaalinstelling offline {#offline-custom-channel-setup}

## Aan de slag {#getting-started}

In vergelijking met de manier waarop [!DNL Marketo Measure] de regels voor onlinekanalen hanteert, zult u zien dat de regels voor offlinekanalen het gebruik van een spreadsheet niet vereisen. Het implementatieplan bevat echter nog steeds een blad, omdat dat handig kan zijn om na te denken over de manier waarop u uw offlinekanalen wilt ordenen.

Het werkblad heeft drie kolommen:

![](assets/offline-channels-1.png)

**[!UICONTROL Salesforce]Campagneringstype** - voeg de Types van Campagne toe die in [!DNL Salesforce] hier worden geïdentificeerd

* Dit kan bijvoorbeeld een e-mail, een webinar, een conferentie of een waarde zijn die u voor dit veld hebt gemaakt en waaraan u aanraakpunten wilt koppelen.

**[!UICONTROL Channel]** - voeg hier uw verschillende marketingkanalen toe

**[!UICONTROL Subchannel]** - voeg hier overeenkomende subkanalen toe

## Offline Channel Logic {#offline-channel-logic}

[!DNL Marketo Measure] De logica voor offlinekanalen wordt bepaald door het Campagneobject, in het bijzonder het [!DNL Salesforce] Campagneringstype. Elke offline inspanning moet een [!DNL Salesforce] Type van Campagne, zoals diner of handel hebben, omdat [!DNL Marketo Measure] op dit gebied baseert om te begrijpen aan welk Kanaal en SubChannel om in kaart te brengen.

De SFDC-campagneretypen worden weergegeven op het tabblad Offline kanaal, dat wordt weergegeven onder [!DNL Salesforce] Campagneringstype. Houd er rekening mee dat [!DNL Marketo Measure] alleen SFDC-cameratypen kan importeren voor campagnes waaraan wel aanraakpunten met kopers zijn gekoppeld.

![](assets/offline-channels-10.jpg)

Hier kunt u de Kanaal/Subchannel-toewijzing maken in de app [!DNL Marketo Measure] . Hiervoor moeten waarschijnlijk nieuwe kanalen en subkanalen worden gemaakt in de app [!DNL Marketo Measure] , die wordt uitgevoerd in de sectie Kanalen maken van de app (zie de onderstaande afbeelding). Er moeten nieuwe kanalen en subkanalen worden gemaakt om in [!DNL Marketo Measure] te begrijpen waar aanraakpunten moeten worden geplaatst. U kunt bepalen hoe u de soorten campagnes wilt toewijzen.

![](assets/offline-channels-11.png)

## Voorbeeld van kanaaltoewijzing {#channel-mapping-example}

Stel dat u twee [!DNL Salesforce] conferenties per jaar bijwoont. Elke conferentie is echter heel anders en heeft een uniek doelpubliek. U wilt weten welke van beide meer waarde hebben. In uw [!DNL Salesforce] milieu, kunt u de gebeurtenis van Januari de &quot;Conferentie van het Type van Campagne,&quot;uw kanaal &quot;[!DNL Salesforce],&quot;en uw subkanaal &quot;Conferentie van Januari&quot;geven.

Nu wilt u hetzelfde doen voor de conferentie van juni. Omdat dit ook een conferentie is, kan het hetzelfde soort campagne krijgen, in dit geval &#39;Conferentie&#39;. Het kanaal is hetzelfde, [!DNL Salesforce] , en het subkanaal voor deze tweede conferentie is &#39;June Conference&#39;. Dit is logisch vanuit organisatorisch oogpunt. Het is echter erg verwarrend voor de logica van [!DNL Marketo Measure] om deze regels te lezen en toe te passen, omdat beide campagnes hetzelfde type campagne hebben. [!DNL Marketo Measure] kan geen gegevens van één type aan twee verschillende subkanalen in kaart brengen. Dit betekent u een nieuw Type van Campagne voor elk subkanaal zou moeten tot stand brengen, maar subkanalen kunnen het zelfde kanaal hebben.

Hieronder ziet u een voorbeeld van logica die [!DNL Marketo Measure] niet kan lezen:

![](assets/offline-channels-12.png)

In het bovenstaande scenario wilt u een uniek campagnetype maken, omdat u niet hetzelfde type campagne aan twee verschillende subkanalen kunt toewijzen. In plaats daarvan wilt u unieke typen instellen, zoals:

![](assets/offline-channels-13.png)

Alle bestaande campagneretypen moeten in uw kanaalkaart worden opgenomen en &quot;NULL&quot; moet als kanaal worden toegevoegd.

Neem de tijd om in [!DNL Salesforce] te gaan om het aantal en de aard van uw bestaande recordtypen te bepalen, die u wilt opnemen, en of u aanvullende campagnes moet maken op basis van de bovenstaande informatie. Als u alle benodigde gegevens hebt ingevuld, kunt u deze uploaden.

Leer meer over [ synchroniserend off-line  [!DNL Salesforce]  Campagnes met  [!DNL Marketo Measure]](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md).

## SFDC-campagnes verwerken voor online marketinginspanningen {#handling-sfdc-campaigns-for-online-marketing-efforts}

Het is gebruikelijk dat marketingteams [!DNL Salesforce] -campagnes maken om verschillende digitale marketingactiviteiten bij te houden. Er is geen probleem met deze praktijk; het is echter belangrijk om deze campagnes anders te behandelen dan echte offlinecampagnes zoals direct mail of conferenties. Campagnes die verwant zijn aan digitale gebeurtenissen (interacties die plaatsvinden op uw website) moeten niet worden gesynchroniseerd met [!DNL Marketo Measure] . Het synchroniseren van deze campagnes zou leiden tot dubbele aanraakpunten, omdat de [!DNL Marketo Measure] JavaScript de online inspanningen al volgt.

Een andere tip voor het verwerken van campagnes voor online activiteiten is het toewijzen van het type campagne van [!DNL Salesforce] aan NULL. Hiertoe maakt u eerst een kanaal in de app [!DNL Marketo Measure] NULL, zoals in de onderstaande afbeelding wordt getoond. Dit wordt gevonden in [!DNL Marketo Measure] app onder **creeer Kanalen** sectie. Dit is handig als een campagne die niet mag worden gesynchroniseerd per ongeluk wordt gesynchroniseerd. Het is gemakkelijk om de campagne te vinden en de synchronisatiestatus te verbeteren door alles te bekijken die onder ONGELDIG wordt gevangen.

![](assets/offline-channels-14.png)

## Uw regels voor offlinekanalen invoeren in de app {#entering-your-offline-channel-rules-to-the-app}

Nadat u het spreadsheet hebt bewerkt en bijgewerkt met uw aangepaste regels, kunt u deze kanaaltoewijzing opnieuw maken in de app [!DNL Marketo Measure] . In dat geval uploadt u geen spreadsheet voor offlinekanalen. In plaats daarvan voert u de informatie in de keuzelijsten in die in de onderstaande afbeelding worden weergegeven. U vindt dit door te klikken op **[!UICONTROL Offline Channels]** onder de sectie **[!UICONTROL Channels]** .

![](assets/offline-channels-20.png)

>[!TIP]
>
>Wilt u _bepalen wanneer_ a [!DNL Salesforce] het Type van Campagne neer in [!DNL Marketo Measure] kanaalafbeelding wordt getrokken? Ga naar **[!UICONTROL Setup]** > **[!UICONTROL Campaigns]** > **[!UICONTROL Fields]** > **[!UICONTROL Type]** . Vervolgens kunt u zien welke waarden in de keuzelijst staan en welke niet actief zijn. Inactieve degenen zullen niet als selecteerbaar type in onze &quot;[!UICONTROL Offline Channels]&quot;sectie verschijnen. Dit proces kan een paar minuten tot 48 uur duren.

Klik op **[!UICONTROL Save]** als u klaar bent en [!DNL Marketo Measure] uploadt de wijzigingen en verwerkt de gegevens opnieuw.

>[!MORELIKETHIS]
>
>* [[!DNL Marketo Measure]  Leerprogramma&#39;s: Het in kaart brengen van Off-line Kanalen ](https://experienceleague.adobe.com/en/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-salesforce/mapping-offline-channels){target="_blank"}
>
>* [[!DNL Marketo Measure]  Leerprogramma&#39;s: Het synchroniseren Offline Campagnes ](https://experienceleague.adobe.com/en/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-salesforce/syncing-offline-campaigns){target="_blank"}
>
>* [ de Integratie van de Programma&#39;s van Marketo Engage ](/help/marketo-measure-and-marketo/marketo-engage-programs-integration.md#channel-mapping){target="_blank"}
