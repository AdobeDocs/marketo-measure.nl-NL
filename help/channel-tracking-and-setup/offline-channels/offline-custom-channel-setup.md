---
unique-page-id: 18874598
description: Offline aangepaste kanaalinstelling - [!DNL Marketo Measure]
title: Aangepaste kanaalinstelling offline
exl-id: c5697714-1a79-40bd-8b7c-e10768f4ef67
feature: Channels
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '858'
ht-degree: 0%

---

# Aangepaste kanaalinstelling offline {#offline-custom-channel-setup}

## Aan de slag {#getting-started}

Vergeleken met hoe [!DNL Marketo Measure] handelt online kanaalregels af. De regels voor offlinekanalen vereisen niet het gebruik van een spreadsheet. Het implementatieplan bevat echter nog steeds een blad, omdat dat handig kan zijn om na te denken over de manier waarop u uw offlinekanalen wilt ordenen.

Het werkblad heeft drie kolommen:

![](assets/1-2.png)

**[!UICONTROL Salesforce]Type campagne** - Voeg de Types van Campagne toe die in worden geïdentificeerd [!DNL Salesforce] hier

* Dit kan bijvoorbeeld een e-mail, een webinar, een conferentie of een waarde zijn die u voor dit veld hebt gemaakt en waaraan u aanraakpunten wilt koppelen.

**[!UICONTROL Channel]** - voeg hier uw verschillende marketingkanalen toe

**[!UICONTROL Subchannel]** - voeg hier overeenkomstige subkanalen toe

## Offline Channel Logic {#offline-channel-logic}

[!DNL Marketo Measure] de logica voor offlinekanalen wordt bepaald door het Campagne-object, met name de [!DNL Salesforce] Type campagne. Elke offline inspanning moet een [!DNL Salesforce] Campagneringstype, zoals diner- of handelswijze, omdat [!DNL Marketo Measure] vertrouwt op dit gebied om te begrijpen aan welk Kanaal en SubChannel om toe te wijzen.

De typen SFDC-campagne worden weergegeven op het tabblad Offlinekanaal onder [!DNL Salesforce] Type campagne. Let op: [!DNL Marketo Measure] is alleen in staat SFDC-cameratypen te importeren voor campagnes waaraan Buyer-aanraakpunten zijn gekoppeld.

![](assets/2-2.png)

Hier kunt u de Kanaal/Subchannel-toewijzing maken in het dialoogvenster [!DNL Marketo Measure] app. Dit zal waarschijnlijk het creëren van nieuwe Kanalen en Subkanalen in [!DNL Marketo Measure] app, die wordt uitgevoerd in de sectie Kanalen maken van de app. Deze wordt weergegeven in de onderstaande afbeelding. Er moeten nieuwe kanalen en subkanalen worden gemaakt voor [!DNL Marketo Measure] om te begrijpen waar aanraakpunten moeten worden geplaatst. U kunt bepalen hoe u de soorten campagnes wilt toewijzen.

![](assets/3-2.png)

## Voorbeeld van kanaaltoewijzing {#channel-mapping-example}

Stel dat u twee aanwezigen bent [!DNL Salesforce] conferenties per jaar. Elke conferentie is echter heel anders en heeft een uniek doelpubliek. U wilt weten welke van beide meer waarde hebben. In uw [!DNL Salesforce] milieu, kunt u de gebeurtenis van Januari de &quot;Conferentie van het Type van Campagne,&quot;uw kanaal &quot;noemen[!DNL Salesforce]en uw subkanaal &quot;Conferentie van januari&quot;.

Nu wilt u hetzelfde doen voor de conferentie van juni. Omdat dit ook een conferentie is, kan het hetzelfde soort campagne krijgen, in dit geval &#39;Conferentie&#39;. Het kanaal is hetzelfde. [!DNL Salesforce]en het subkanaal voor deze tweede conferentie is &quot;Junilistan&quot;. Dit is logisch vanuit organisatorisch oogpunt. Het is echter zeer verwarrend voor de [!DNL Marketo Measure] logica om deze regels te lezen en toe te passen omdat beide campagnes hetzelfde campagnerype hebben. [!DNL Marketo Measure] script kan geen gegevens van het ene type toewijzen aan twee verschillende subkanalen. Dit betekent u een nieuw Type van Campagne voor elk subkanaal zou moeten tot stand brengen, maar subkanalen kunnen het zelfde kanaal hebben.

Hieronder ziet u een voorbeeld van logica die [!DNL Marketo Measure] kan niet lezen:

![](assets/4-2.png)

In het bovenstaande scenario wilt u een uniek campagnetype maken, omdat u niet hetzelfde type campagne aan twee verschillende subkanalen kunt toewijzen. In plaats daarvan wilt u unieke typen instellen, zoals:

![](assets/5-2.png)

Alle bestaande campagneretypen moeten in uw kanaalkaart worden opgenomen en &quot;NULL&quot; moet als kanaal worden toegevoegd.

Neem de tijd om in te gaan [!DNL Salesforce] om het aantal en de aard van uw bestaande recordtypes te bepalen, die u wilt omvatten, en of u extra campagnes moet creëren die op de bovenstaande informatie worden gebaseerd. Als u alle benodigde gegevens hebt ingevuld, kunt u deze uploaden.

Meer informatie over [offline synchroniseren [!DNL Salesforce] Campagnes met [!DNL Marketo Measure]](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md).

## SFDC-campagnes verwerken voor online marketinginspanningen {#handling-sfdc-campaigns-for-online-marketing-efforts}

Het is gebruikelijk voor Marketing teams om te creëren [!DNL Salesforce] campagnes om verschillende inspanningen op het gebied van digitale marketing te volgen. Er is geen probleem met deze praktijk; het is echter belangrijk om deze campagnes anders te behandelen dan echte offlinecampagnes zoals direct mail of conferenties. Campagnes die betrekking hebben op digitale gebeurtenissen (interacties die plaatsvinden op uw website) mogen niet worden gesynchroniseerd met [!DNL Marketo Measure]. Het synchroniseren van deze campagnes zou resulteren in dubbele aanraakpunten omdat de [!DNL Marketo Measure] JavaScript volgt de online inspanningen al.

Een andere tip voor het verwerken van campagnes voor online activiteiten is om de [!DNL Salesforce] Campagneringstype naar NULL. Hiertoe maakt u eerst een kanaal in het dialoogvenster [!DNL Marketo Measure] app met de naam NULL, zoals wordt getoond in de onderstaande afbeelding. Deze vindt u in het dialoogvenster [!DNL Marketo Measure] onder de **Kanalen maken** sectie. Dit is handig als een campagne die niet mag worden gesynchroniseerd per ongeluk wordt gesynchroniseerd. Het is gemakkelijk om de campagne te vinden en de synchronisatiestatus te verbeteren door alles te bekijken die onder ONGELDIG wordt gevangen.

![](assets/6-2.png)

## Uw regels voor offlinekanalen invoeren in de app {#entering-your-offline-channel-rules-to-the-app}

Nadat u het spreadsheet hebt bewerkt en bijgewerkt met uw aangepaste regels, kunt u deze kanaaltoewijzing opnieuw maken in het dialoogvenster [!DNL Marketo Measure] app-u zult eigenlijk geen spreadsheet voor off-line kanalen uploaden. In plaats daarvan voert u de informatie in de keuzelijsten in die in de onderstaande afbeelding worden weergegeven. U vindt dit door op **[!UICONTROL Offline Channels]** onder de **[!UICONTROL Channels]** sectie.

![](assets/7-2.png)

>[!TIP]
>
>Wil bepalen _wanneer_ a [!DNL Salesforce] Campagnertype wordt naar beneden getrokken [!DNL Marketo Measure] kanaaltoewijzing? Ga naar **[!UICONTROL Setup]** > **[!UICONTROL Campaigns]** > **[!UICONTROL Fields]** > **[!UICONTROL Type]**. Vervolgens kunt u zien welke waarden in de keuzelijst staan en welke niet actief zijn. Niet-actieve groepen worden niet als een selecteerbaar type weergegeven in onze &quot;[!UICONTROL Offline Channels]&quot;. Dit proces kan een paar minuten tot 48 uur duren.

Klikken **[!UICONTROL Save]** wanneer u klaar bent en [!DNL Marketo Measure] uploadt de wijzigingen en verwerkt de gegevens opnieuw.

>[!MORELIKETHIS]
>
>* [[!DNL Marketo Measure] Universiteit: Offlinekanalen toewijzen](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c630eca34d9f0367662b77f)
>
>* [[!DNL Marketo Measure] University: Offlinecampagnes synchroniseren](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c63286e34d9f0367662b78b)
>
>* [Integratie van Marketo Engage-programma&#39;s](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md#channel-mapping)
