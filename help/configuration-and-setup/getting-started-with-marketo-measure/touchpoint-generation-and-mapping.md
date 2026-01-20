---
unique-page-id: 18874554
description: Aanraakpunt genereren en toewijzen - [!DNL Marketo Measure]
title: Aanraakpunt genereren en toewijzen
exl-id: bb4988f5-4fbc-43b7-9544-da541b8e1d32
feature: Touchpoints
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 0%

---

# Aanraakpunt genereren en toewijzen {#touchpoint-generation-and-mapping}

[!DNL Marketo Measure] De attributieartikelen hebben twee processen:

* Het produceren van aanraakpunten, die aanraakpunten creeert die de interactie van een persoon met uw marketing en verkoopinspanningen vertegenwoordigen
* Aanraakpunttoewijzing, waarmee aanraakpunten worden toegewezen aan het juiste kanaal en subkanaal

Als u het beste uit [!DNL Marketo Measure] wilt halen, werkt u samen met uw [!DNL Marketo Measure] -vertegenwoordiger om beide processen aan te passen aan de behoeften van uw organisatie.

Methoden voor het genereren van aanraakpunten

Het aanraakpuntgeneratieproces beantwoordt de vraag: &quot;Hoe gaat [!DNL Marketo Measure] weten dat dit is gebeurd?&quot; Afhankelijk van uw eigenschapreeks en de soorten interactie uw potentiële klanten kunnen hebben, zijn er tot drie manieren [!DNL Marketo Measure] op een interactie kan opnemen en een touchpoint creëren om het te vertegenwoordigen.

>[!IMPORTANT]
>
>[!DNL Marketo Measure] genereert slechts één aanraakpunt per sessie. Als er meerdere formulieren zijn ingevuld, wordt alleen de eerste formuliervulling vastgelegd.

| **Type van Interactie** | **Voorbeeld** | **Methode van de Generatie van het Aanraakpunt** |
|---|---|---|
| Online, op uw sites | Formuliervulling | [!DNL Marketo Measure] JavaScript |
| Offline; niet online op uw sites | Handelaren; de partner van de syndicatie van de inhoud levert een lijst van Leidingen die met uw inhoud in dienst waren | Het lidmaatschap van de Campagne van CRM wordt gesynchroniseerd aan [!DNL Marketo Measure], of door het Type van Synchronisatie van de Campagne direct in de campagne te plaatsen of door regels op de pagina van Campagnes in te stellen in [!DNL Marketo Measure] |
| Verkoopactiviteit | Uitgaande vraag door SDR. | CRM-activiteitenrecord (taak of gebeurtenis) gesynchroniseerd met [!DNL Marketo Measure] via logica op de [!UICONTROL Activities] pagina in [!DNL Marketo Measure] |

Methoden voor aanraakpunten

Het toewijzingsproces voor aanraakpunten beantwoordt de vraag: &quot;Hoe weet [!DNL Marketo Measure] wanneer dit aanraakpunt is gemaakt, tot welk kanaal en subkanaal het behoort?&quot; Elke methode voor het genereren van aanraakpunten heeft een eigen methode voor het toewijzen van aanraakpunten.

| **Type van Interactie** | **de Methode van de Generatie** | **Toewijzingsmethode** |
|---|---|---|
| Online, op uw sites | [!DNL Marketo Measure] JavaScript | Via de [!DNL Online Channels] -pagina in [!DNL Marketo Measure] , door te verwijzen naar UTM-waarden, de landingspagina en de informatie over de verwijzingspagina |
| Offline; online, niet op uw sites | Synchronisatie CRM-cameralidmaatschap | Via de [!UICONTROL Offline Channels] -pagina in [!DNL Marketo Measure] , door naar het campagneretype te verwijzen |
| Verkoopactiviteit | CRM-activiteitssync | Via de [!UICONTROL Online Channels] -pagina in [!DNL Marketo Measure] , door te verwijzen naar de campagnenaam die is toegewezen op de [!UICONTROL Activities] -pagina |

>[!MORELIKETHIS]
>
>* [ het In kaart brengen Online Touchpoints aan  [!DNL Marketo Measure]  Kanalen/Subkanalen ](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
>* [ het synchroniseren van de Campagnes van CRM van binnen SFDC ](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md)
>* [ het synchroniseren van de Campagnes van CRM van binnen  [!DNL Marketo Measure]](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md)
>* [ het In kaart brengen van CRM Campagnes aan  [!DNL Marketo Measure]  Kanalen/Subkanalen ](/help/channel-tracking-and-setup/offline-channels/offline-custom-channel-setup.md)
>* [ Creërend Touchpoints van de Activiteiten van de Verkoop ](/help/advanced-marketo-measure-features/activities-attribution/salesforce-activities-attribution.md)
>* [ Veelgestelde vragen van Activiteiten en de Activiteiten van de Afbeelding richt aan Kanalen/Subkanalen ](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)

