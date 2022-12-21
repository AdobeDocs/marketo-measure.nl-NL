---
description: Beste praktijken voor Off-line Kanalen - [!DNL Marketo Measure] - Productdocumentatie
title: Aanbevolen procedures voor offlinekanalen
exl-id: 71c50614-8d5b-469f-bc02-3cc489464a4e
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '1050'
ht-degree: 0%

---

# Aanbevolen procedures voor offlinekanalen {#best-practices-for-offline-channels}

## Overzicht {#overview}

Om nauwkeurig te zijn [!DNL Marketo Measure] de rapportering, uw Kanalen van de Marketing moeten correct opstelling zijn. De &#39;[!UICONTROL Marketing Channel]In het veld wordt de groep marketing weergegeven waartoe een aanraakpunt op het hoogste niveau kan behoren (bijvoorbeeld Gebeurtenissen, Webinars, Inhoudssyntaxis, enz.).

Het instellen van uw marketingkanalen kent twee aspecten: online en offline. In dit document wordt de nadruk gelegd op de [!DNL Marketo Measure] Aanbevelingen voor best practices voor het instellen en onderhouden van uw offlinekanalen en de manier waarop deze worden gesynchroniseerd [!DNL Marketo Measure] via CRM-campagnes.

Offlinekanalen hebben twee belangrijke aspecten:

1. Offline kanaaltoewijzing, dit is het framework dat [!DNL Marketo Measure] tot welk kanaal en subkanaal het off line aanraakpunt behoort
1. Offlinecampagensynchronisatie die het creëren van off-line aanraakpunten is

Offline touchpoints worden gemaakt van een CRM-campagne en zijn bedoeld om marketinginteractie bij te houden die niet digitaal via de [!DNL Marketo Measure] JavaScript dat is geïmplementeerd op de pagina&#39;s van uw website. Wanneer een campagne van CRM met wordt gesynchroniseerd [!DNL Marketo Measure], worden er aanraakpunten gemaakt voor de gedefinieerde campagneleden in de campagne.

De waarde &#39;Marketing Channel&#39; voor deze aanraakpunten is gebaseerd op het veld &#39;Type&#39; in de campagne. De toewijzing van &#39;CRM Campaign Type&#39; aan &#39;Marketing Channel&#39; en &#39;Subchannel&#39; wordt beheerd op het tabblad &#39;Offlinekanalen&#39; van uw [!DNL Marketo Measure] Accountinstellingen. Als u ervoor zorgt dat uw offlinekanaaltoewijzing correct en up-to-date is, weet u zeker dat uw offline aanraakpuntgegevens worden toegewezen aan de juiste marketingkanalen en subkanalen binnen uw [!DNL Marketo Measure] Rapportage.

## Beste praktijken | Offline kanaaltoewijzing {#best-practice-offline-channel-mapping}

Of u uw Off-line Kanalen voor het eerst in kaart brengt of enkel hen controleert om nauwkeurigheid te controleren, houd de volgende beste praktijken in mening.

* Een doelbewust framework voor offlinekanalen maken
   * Neem wat tijd om na te denken over de organisatie van uw marketingcampagnes en hoe deze passen in de [!DNL Marketo Measure] kader. Bepaal welke Kanalen en Subkanalen in uw Off-line Kanalen zouden moeten worden vertegenwoordigd evenals welke Types van Campagne CRM die kanalen van elkaar onderscheiden
* Werk eerst om de huidige &#39;Type&#39;-waarden van de CRM-campagne te gebruiken
   * Offlinekanalen worden gedefinieerd door CRM-campagne &#39;Type&#39;, maar de aangepaste CRM-campagne &#39;Type&#39;-waarde moet mogelijk worden gemaakt om ruimte te bieden aan ideale offlinekanaal- en subkanaalwaarden. De ideale aangepaste CRM-campagne &#39;Type&#39;-waarden moeten de onderstaande naamgevingsconventie hebben:
      * KANAAL - SUBKANAAL
      * Voorbeeld: Gebeurtenis - Handelswijze
      * Hierdoor is het toewijzen aan subkanaalniveau zo eenvoudig en schoon mogelijk
* Eén subkanaal kan alleen worden toegewezen aan één CRM-campagne &#39;Type&#39;
   * De veelvoudige Campagne van CRM &quot;Types&quot;kan aan één enkel Kanaal worden in kaart gebracht, maar slechts kan één Campagne van CRM &quot;Type&quot;aan elk Subchannel binnen elk Kanaal in kaart worden gebracht
* Alleen OFFLINE CRM-campagne &#39;Types&#39; moet worden toegewezen aan offline kanalen, omdat alleen offline campagnes moeten worden gesynchroniseerd met [!DNL Marketo Measure] om aanraakpunten te maken:
   * ONLINE CRM-campagne &#39;Types&#39; moet worden toegewezen aan een [!UICONTROL Marketing Channel] = &quot;NULL&quot;. Deze waarde wordt aanbevolen omdat deze fungeert als een &#39;rode vlag&#39; die aangeeft dat uw offlinekanalen zijn gecontroleerd en dat een CRM-campagne &#39;Type&#39; die is toegewezen aan &#39;NULL&#39; een ONLINE &#39;Type&#39; is en niet mag worden gesynchroniseerd met [!DNL Marketo Measure]. Aanraakpunten met betrekking tot online CRM-campagne &#39;Types&#39; worden al bijgehouden via [!DNL Marketo Measure] Online functionaliteit en kanalen. Het synchroniseren van deze campagnes brengt het risico met zich mee van &quot;dubbele&quot; aanraakpunten/dubbeltelling

## Beste praktijken | Offline Campagne Sync {#best-practice-offline-campaign-sync}

* Zorg ervoor dat het veld Type correct is op elke CRM-campagne
   * Het &quot;Type&quot;bepaalt het Kanaal van de Marketing en Subchannel voor om het even welke touchpoints die uit de Campagne worden gesynchroniseerd
* Of de op CRM gebaseerde methode van de Synchronisatie van de Campagne gebruikt (laat Aanraakpunten van de Koper toe) of [!DNL Marketo Measure] Op toepassingen gebaseerde synchronisatiemethode (Aangepaste campagnesynchronisatie in de map &#39;[!UICONTROL Campaigns]&#39; tabblad van uw [!UICONTROL Marketo Measure] (Accountinstellingen), dienen offline aanraakpunten alleen te worden gemaakt als het Campagne-lid daadwerkelijk offline verbinding heeft met de campagne en uw merk:
   * Voor offlinekanalen zoals gebeurtenissen of webinars: &quot;registraties&quot; worden doorgaans bijgehouden via formulierverzendingen op uw website en [!DNL Marketo Measure] Online functionaliteit. Daarom mogen de campagneleden met de status &quot;geregistreerd&quot; geen offline aanspreekpunt uit de campagne ontvangen om dubbeltelling te voorkomen. Offline aanraakpunten moeten alleen representatief zijn voor de &quot;aanwezigheid&quot; van de gebeurtenis of het webinar.
   * Bepaalde offlinekanalen, zoals Content Syndication, zijn doorgaans eenvoudiger omdat elk campagnerelid dezelfde status ‘beantwoord’ heeft die aangeeft dat ze inderdaad hebben gereageerd op de campagne. In dit geval kunt u inhoud downloaden naar een externe site en daarom een offline aanraakpunt ontvangen
* Wanneer u de methode Aangepaste campagnecynchronisatie gebruikt in het dialoogvenster [!DNL Marketo Measure] Zorg ervoor dat het veld Aanraakpuntdatum is gebaseerd op het datumveld van de Campagne- of Campagnelid dat het meest indicatief is wanneer de aanraakpuntinteractie daadwerkelijk heeft plaatsgevonden
* Gebruik de knoop van het Aanraakpunt van de &quot;Bulk Update van de Datum&quot;als u de &quot;Datum van het Aanraakpunt&quot;voor om het even welke off-line aanraakpunten moet met voeten treden die uit een Campagne van CRM worden voortgebracht. De &quot;aanraakpuntdatum&quot; moet zo nauwkeurig mogelijk zijn om ervoor te zorgen dat het aanraakpunt de nauwkeurigst mogelijke &quot;aanraakpuntpositie&quot; heeft en dus de juiste hoeveelheid toekenningskrediet

## Best Practice for Maintenance {#best-practice-for-maintenance}

Nadat u de installatie hebt gestart, blijven de offlinekanaalinstellingen dienovereenkomstig offline aanraakpunten maken. We raden u aan uw Offlineinstelling ten minste twee keer per jaar te controleren. Dit garandeert schone en nauwkeurige gegevens voor aanspreekpunten voor kopers.

Bovendien, als u om het even welke veranderingen in uw het beheer of processen van de Campagne aanbrengt, zult u moeten ervoor zorgen u bijwerkt uw [!DNL Marketo Measure] Offline kanaaltoewijzing en/of synchronisatieproces.

Wijzigingen die uw team kunnen aanzetten om updates uit te voeren voor de installatie van het offlinekanaal in het dialoogvenster [!DNL Marketo Measure] kan het volgende omvatten:

* CRM-campagne &#39;Type(n)&#39; gemaakt of bewerkt
* Campagnelid &#39;Status&#39; gemaakt of bewerkt
* Als het gebruiken van de methode van de Synchronisatie van de Campagne van CRM via het &quot;laat de Aanraakpunten van de Koper&quot;gebied toe, zorg ervoor dit gebied voor elke Campagne van CRM wordt herzien en bijgewerkt die wordt gecreeerd. Als dit veld wordt genegeerd, zijn er geen gerelateerde offline aanraakpuntgegevens
* Als u om het even welke off-line aanraakpunten van een Campagne van CRM tegenkomt die online aanraakpunten (het Kanaal van de Marketing = ONGELDIG) kijken, zorg ervoor de verwante Campagne van CRM wordt herzien en de synchronisatie onbruikbaar gemaakt

Als uw team onlangs één van het bovengenoemde heeft ervaren: [!DNL Marketo Measure] U kunt het beste uw offlinekanaaltoewijzing en offline campagnes controleren om de juiste wijzigingen aan te brengen en ervoor te zorgen dat deze op de juiste wijze worden gesynchroniseerd.

>[!MORELIKETHIS]
>
>* [Offlinekanaal instellen](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)
>* [Aangepaste camerasynchronisatie - App Sync](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)
>* [Offlinecampagnes synchroniseren - CRM-synchronisatie](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md)
>* [Offlinecampagne- en campagnegeleden - CRM-synchronisatie](/help/channel-tracking-and-setup/offline-channels/campaigns-and-campaign-members.md)
>* [Synchronisatiedata voor campagne - CRM-synchronisatie](/help/channel-tracking-and-setup/offline-channels/campaign-sync-dates.md)
>* [Configuraties voor meerdere soorten campagnerecopnamen](/help/channel-tracking-and-setup/offline-channels/configurations-for-multiple-campaign-record-types.md)
>* [Een Campagnelijstweergave maken](/help/channel-tracking-and-setup/offline-channels/creating-a-campaign-list-view-for-salesforce-campaigns.md)
>* [Historische gegevens synchroniseren](/help/channel-tracking-and-setup/offline-channels/syncing-historical-data.md)

