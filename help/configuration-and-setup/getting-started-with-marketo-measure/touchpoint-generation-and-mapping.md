---
unique-page-id: 18874554
description: Aanraakpunt genereren en toewijzen - [!DNL Marketo Measure]
title: Aanraakpunt genereren en toewijzen
exl-id: bb4988f5-4fbc-43b7-9544-da541b8e1d32
feature: Touchpoints
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 0%

---

# Aanraakpunt genereren en toewijzen {#touchpoint-generation-and-mapping}

[!DNL Marketo Measure] attributieartikelen zijn gebaseerd op twee processen:

* Het produceren van aanraakpunten, die aanraakpunten creeert die de interactie van een persoon met uw marketing en verkoopinspanningen vertegenwoordigen
* Aanraakpunttoewijzing, waarmee aanraakpunten worden toegewezen aan het juiste kanaal en subkanaal

Om optimaal te profiteren van [!DNL Marketo Measure], moet u met uw [!DNL Marketo Measure] rep. om beide processen aan te passen aan de behoeften van uw organisatie.

Methoden voor het genereren van aanraakpunten

Het aanraakpuntgeneratieproces beantwoordt de vraag: &quot;Hoe is [!DNL Marketo Measure] gaan we weten dat dit is gebeurd?&quot; Afhankelijk van uw eigenschapreeks en de types van interactie uw potentiële klanten kunnen hebben, zijn er tot drie manieren [!DNL Marketo Measure] kan een interactie oppakken en een aanraakpunt maken om deze weer te geven.

>[!IMPORTANT]
>
>[!DNL Marketo Measure] Er wordt slechts één aanraakpunt per sessie gegenereerd. Als er meerdere formulieren zijn ingevuld, wordt alleen de eerste formuliervulling vastgelegd.

| **Type interactie** | **Voorbeeld** | **Methode voor het genereren van aanraakpunten** |
|---|---|---|
| Online, op uw sites | Formuliervulling | [!DNL Marketo Measure] JavaScript |
| Offline; niet online op uw sites | Handelaren; de partner van de syndicatie van de inhoud levert een lijst van Leidingen die met uw inhoud in dienst waren | CRM-cameralidmaatschap gesynchroniseerd met [!DNL Marketo Measure]door het type Campagne Sync rechtstreeks in de campagne in te stellen of door regels voor de pagina Campagnes in te stellen in [!DNL Marketo Measure] |
| Verkoopactiviteit | Uitgaande vraag door SDR. | CRM-activiteitenrecord (taak of gebeurtenis) gesynchroniseerd met [!DNL Marketo Measure], door logica op de [!UICONTROL Activities] pagina in [!DNL Marketo Measure] |

Methoden voor aanraakpunten

Het proces van de touchpoint afbeelding beantwoordt de vraag, &quot;Zodra dit aanraakpunt wordt gecreeerd, hoe is [!DNL Marketo Measure] gaan we weten tot welk kanaal en subkanaal het behoort?&quot; Elke methode voor het genereren van aanraakpunten heeft een eigen methode voor het toewijzen van aanraakpunten.

| **Type interactie** | **Generatiemethode** | **Toewijzingsmethode** |
|---|---|---|
| Online, op uw sites | [!DNL Marketo Measure] JavaScript | Via de [!DNL Online Channels] pagina in [!DNL Marketo Measure]door te verwijzen naar UTM-waarden, de landingspagina en de informatie over de verwijzingspagina |
| Offline; online, niet op uw sites | Synchronisatie CRM-cameralidmaatschap | Via de [!UICONTROL Offline Channels] pagina in [!DNL Marketo Measure], door te verwijzen naar het type campagne |
| Verkoopactiviteit | CRM-activiteitssync | Via de [!UICONTROL Online Channels] pagina in [!DNL Marketo Measure]door naar de campagnenaam te verwijzen die is toegewezen aan de [!UICONTROL Activities] page |

>[!MORELIKETHIS]
>
>* [Online aanraakpunten toewijzen aan [!DNL Marketo Measure] Kanalen/Subkanalen](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
>* [CRM-campagnes synchroniseren vanuit SFDC](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md)
>* [CRM-campagnes synchroniseren vanuit [!DNL Marketo Measure]](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)
>* [CRM-campagnes toewijzen aan [!DNL Marketo Measure] Kanalen/Subkanalen](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)
>* [Aanraakpunten maken van verkoopactiviteiten](/help/advanced-marketo-measure-features/activities-attribution/salesforce-activities-attribution.md)
>* [Activiteiten - Veelgestelde vragen en Toewijzing van aanraakpunten aan kanalen/subkanalen](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)

