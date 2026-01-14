---
description: Tips en trucs voor advies over offlinekanalen voor Marketo Measure-gebruikers
title: Aanbevolen procedures voor offlinekanalen
exl-id: 71c50614-8d5b-469f-bc02-3cc489464a4e
feature: Channels
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '1054'
ht-degree: 0%

---


# Aanbevolen procedures voor offlinekanalen {#best-practices-for-offline-channels}

## Overzicht {#overview}

Uw marketingkanalen moeten correct zijn ingesteld om een nauwkeurige [!DNL Marketo Measure] -rapportage te kunnen krijgen. Het &quot;[!UICONTROL Marketing Channel]&quot;gebied toont de groep van marketing op het hoogste niveau tactiek die een aanraakpunt tot (bijvoorbeeld, Gebeurtenissen, Webinars, de Syndicatie van de Inhoud, etc.) kan behoren.

Het instellen van uw marketingkanalen kent twee aspecten: online en offline. Dit document is gericht op de [!DNL Marketo Measure] aanbevelingen voor best practices voor het instellen en onderhouden van uw offlinekanalen en op de manier waarop deze via CRM-campagnes worden gesynchroniseerd met [!DNL Marketo Measure] .

Offlinekanalen hebben twee belangrijke aspecten:

1. Offline kanaaltoewijzing. Dit is het framework dat [!DNL Marketo Measure] aangeeft tot welk kanaal en subkanaal het Offline aanraakpunt behoort
1. Offlinecampagensynchronisatie die het creëren van off-line aanraakpunten is

Offlineaanraakpunten worden gemaakt op basis van een CRM-campagne en zijn bedoeld voor het bijhouden van elke marketinginteractie die niet digitaal kan worden bijgehouden via de JavaScript van [!DNL Marketo Measure] die is geïmplementeerd op de pagina&#39;s van uw website. Wanneer een CRM-campagne wordt gesynchroniseerd met [!DNL Marketo Measure] , worden aanraakpunten gemaakt voor de gedefinieerde Campagne-leden in de Campagne.

De waarde &#39;Marketing Channel&#39; voor deze aanraakpunten is gebaseerd op het veld &#39;Type&#39; in de campagne. De toewijzing van &#39;CRM-cameratype&#39; aan &#39;Marketing Channel&#39; en &#39;Subchannel&#39; wordt beheerd op het tabblad &#39;Offlinekanalen&#39; van uw [!DNL Marketo Measure] accountinstellingen. Als u ervoor zorgt dat uw offlinekanaaltoewijzing correct en up-to-date is, weet u zeker dat uw offline aanraakpuntgegevens worden toegewezen aan de juiste marketingkanalen en subkanalen in uw [!DNL Marketo Measure] -rapportage.

## Beste praktijken | Offline kanaaltoewijzing {#best-practice-offline-channel-mapping}

Of u uw Off-line Kanalen voor het eerst in kaart brengt of enkel hen controleert om nauwkeurigheid te controleren, houd de volgende beste praktijken in mening.

* Een doelbewust framework voor offlinekanalen maken
   * Neem wat tijd om na te denken over de organisatie van uw marketingcampagnes en hoe deze passen in het [!DNL Marketo Measure] -framework. Bepaal welke Kanalen en Subkanalen in uw Off-line Kanalen zouden moeten worden vertegenwoordigd en welke Types van Campagne van CRM die kanalen van elkaar onderscheiden
* Werk eerst om de huidige &#39;Type&#39;-waarden van de CRM-campagne te gebruiken
   * Offlinekanalen worden gedefinieerd door CRM-campagne &#39;Type&#39;, maar de aangepaste CRM-campagne &#39;Type&#39;-waarde moet mogelijk worden gemaakt om ruimte te bieden aan ideale offlinekanaal- en subkanaalwaarden. De ideale aangepaste CRM-campagne &#39;Type&#39;-waarden moeten de onderstaande naamgevingsconventie hebben:
      * KANAAL - SUBKANAAL
      * Voorbeeld: Event - Tradeshow
      * Hierdoor is het toewijzen aan subkanaalniveau zo eenvoudig en schoon mogelijk
* Eén subkanaal kan alleen worden toegewezen aan één CRM-campagne &#39;Type&#39;
   * De veelvoudige Campagne van CRM &quot;Types&quot;kan aan één enkel Kanaal worden in kaart gebracht, maar slechts kan één Campagne van CRM &quot;Type&quot;aan elk Subchannel binnen elk Kanaal in kaart worden gebracht
* Alleen OFFLINE CRM-campagnes &#39;Types&#39; moeten worden toegewezen aan offline kanalen, omdat alleen offline campagnes moeten worden gesynchroniseerd met [!DNL Marketo Measure] om aanraakpunten te maken:
   * ONLINE CRM-campagne &#39;Types&#39; moet worden toegewezen aan a [!UICONTROL Marketing Channel] = &quot;NULL&quot;. Deze waarde wordt aanbevolen omdat deze fungeert als een &#39;rode vlag&#39; die aangeeft dat uw offlinekanalen zijn gecontroleerd en dat een CRM-campagne &#39;Type&#39; die is toegewezen aan &#39;NULL&#39; een ONLINE &#39;Type&#39; is en niet mag worden gesynchroniseerd met [!DNL Marketo Measure] . Aanraakpunten met betrekking tot online CRM-campagne &#39;Types&#39; worden al bijgehouden via [!DNL Marketo Measure] Online functionaliteit en kanalen. Het synchroniseren van deze campagnes brengt het risico met zich mee van &quot;dubbele&quot; aanraakpunten/dubbeltelling

## Beste praktijken | Synchronisatie offlinecampagne {#best-practice-offline-campaign-sync}

* Zorg ervoor dat het veld Type correct is op elke CRM-campagne
   * Het &quot;Type&quot;bepaalt het Kanaal van de Marketing en Subchannel voor om het even welke touchpoints die uit de Campagne worden gesynchroniseerd
* Of u nu de op CRM gebaseerde methode voor het synchroniseren van campagnes gebruikt (Enable Buyer Touchpoints) of de [!DNL Marketo Measure] op app gebaseerde synchronisatiemethode (Custom Campaign Sync op het tabblad &#39;[!UICONTROL Campaigns]&#39; van uw [!UICONTROL Marketo Measure] Account Settings), offline aanraakpunten moeten alleen worden gemaakt als het campagnemiddel een daadwerkelijke offline verbinding met de campagne en uw merk had:
   * Voor offlinekanalen zoals Gebeurtenissen of Webinars: &#39;registraties&#39; worden doorgaans bijgehouden via formulierverzendingen op uw website en [!DNL Marketo Measure] Online-functionaliteit. Daarom mogen de campagneleden met de status &quot;geregistreerd&quot; geen offline aanspreekpunt uit de campagne ontvangen om dubbeltelling te voorkomen. Offline aanraakpunten moeten alleen representatief zijn voor de &quot;aanwezigheid&quot; van de gebeurtenis of het webinar.
   * Sommige offlinekanalen zoals de Syndicatie van de Inhoud zijn gemakkelijker in die zin dat elk Lid van de Campagne de zelfde &quot;geantwoord&quot;status heeft die verklaart zij inderdaad aan de campagne antwoordden, in dit geval downloadt inhoud op een derdeplaats en daarom een off-line aanraakpunt zou moeten ontvangen
* Wanneer u de aangepaste methode Campagne Sync in de [!DNL Marketo Measure] -app gebruikt, moet u ervoor zorgen dat het veld Aanraakpuntdatum is gebaseerd op het datumveld van het Campagne- of Campagne-lid dat het meest aangeeft wanneer de aanraakpuntinteractie daadwerkelijk heeft plaatsgevonden
* Gebruik de knoop van het Aanraakpunt van de Update van het Bulk van de knoop als u de &quot;Datum van het Aanraakpunt&quot;voor om het even welke off-line aanraakpunten moet met voeten treden die uit een Campagne van CRM worden voortgebracht. De &quot;aanraakpuntdatum&quot; moet zo nauwkeurig mogelijk zijn om ervoor te zorgen dat het aanraakpunt de nauwkeurigst mogelijke &quot;aanraakpuntpositie&quot; heeft en dus de juiste hoeveelheid toekenningskrediet

## Aanbevolen werkwijzen voor onderhoud {#best-practice-for-maintenance}

Nadat u de Offlinekanaalinstellingen hebt ingesteld, worden er nog steeds overeenkomstige offlineaanraakpunten gemaakt. We raden u aan uw Offlineinstelling ten minste twee keer per jaar te controleren. Dit garandeert schone en nauwkeurige gegevens van aanraakpunten voor kopers.

Als u wijzigingen aanbrengt in uw Campagnebeheer of -processen, moet u ervoor zorgen dat u het [!DNL Marketo Measure] proces voor offlinekanaaltoewijzing en/of -synchronisatie bijwerkt.

Wijzigingen die uw team mogelijk kunnen aanzetten om updates uit te voeren voor de installatie van het offlinekanaal in [!DNL Marketo Measure] , zijn onder meer:

* CRM-campagne &#39;Types&#39; gemaakt of bewerkt
* Campagnelid &#39;Status&#39; gemaakt of bewerkt
* Als het gebruiken van de methode van de Synchronisatie van de Campagne van CRM via het &quot;laat de Aanraakpunten van de Koper&quot;gebied toe, zorg ervoor dat dit gebied voor elke Campagne van CRM wordt herzien en bijgewerkt die wordt gecreeerd. Als dit veld wordt genegeerd, zijn er geen gerelateerde offline aanraakpuntgegevens
* Als u om het even welke off-line aanraakpunten van een Campagne van CRM tegenkomt die online aanraakpunten (het Kanaal van de Marketing = ONGELDIG) kijken, zorg ervoor de verwante Campagne van CRM wordt herzien en de synchronisatie onbruikbaar gemaakt

Als uw team onlangs om het even welk bovengenoemd heeft ervaren, [!DNL Marketo Measure] adviseert dat u uw Offline Kanaalafbeelding en Off-line Campagnes controleert om de aangewezen veranderingen aan te brengen en hen te verzekeren correct gesynchroniseerd.

>[!MORELIKETHIS]
> [ Offline Opstelling van het Kanaal ](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)
> [Aangepaste campagnesynchronisatie - App Sync ](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)
> [Offlinecampagnes synchroniseren - de Synchronisatie van CRM ](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md)
> [Offline Campagne &amp; Campagne Leden - de Synchronisatie van CRM ](/help/channel-tracking-and-setup/offline-channels/legacy-processes/campaigns-and-campaign-members.md)
> [Datums van de Synchronisatie van de campagne - de Synchronisatie van CRM ](/help/channel-tracking-and-setup/offline-channels/legacy-processes/campaign-sync-dates.md)
> [Configuraties voor de Veelvoudige Types van Verslag van de Campagne ](/help/channel-tracking-and-setup/offline-channels/configurations-record-types.md)
> [Het creëren van een Mening van de Lijst van de Campagne ](/help/channel-tracking-and-setup/offline-channels/legacy-processes/creating-a-campaign-list-view-for-salesforce-campaigns.md)
> [Historische gegevens synchroniseren ](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-historical-data.md)
