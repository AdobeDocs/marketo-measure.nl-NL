---
description: Beheersmethoden voor uitgaven - [!DNL Marketo Measure]
title: Methoden voor uitgavenbeheer
exl-id: 36478d8d-986c-4d4f-8854-3287d6c57a9d
feature: Spend Management
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 0%

---

# Methoden voor uitgavenbeheer {#spend-management-methods}

De gegevens van de uitgaven zijn essentieel voor het succes van ROI rapportering met [!DNL Marketo Measure]. Om nauwkeurige en uitvoerige ROI rapportering over al uw kanalen en subkanalen te hebben, moet u ervoor zorgen u de aangewezen uitgavengegevens hebt die in worden getrokken [!DNL Marketo Measure].

Er zijn drie manieren om gegevens in te brengen [!DNL Marketo Measure]. Elke methode is ontworpen om te putten uit gegevens van bepaalde gegevensinput.

**1 met API verbonden accounts**

Elke advertentierekening waarmee u verbinding hebt [!DNL Marketo Measure] via een API wordt de uitgave automatisch aangetrokken [!DNL Marketo Measure] voor ROI-rapportage. Ga naar uw [!DNL Marketo Measure] App en selecteer de [!UICONTROL Connections] onder de [!UICONTROL Integrations] sectie. Raadpleeg voor meer informatie over het instellen van uw API-verbindingen [Geïntegreerde AD-platforms](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md#how-to-connect-ad-platforms).

**2 CRM-campagne kostensynchronisatie**

Elke [!DNL Marketo Measure] account heeft toegang tot een functie die [Kosten van CRM-campagne synchroniseren](/help/marketing-spend/spend-management/crm-campaign-costs.md#availability). Deze functiebit is standaard ingesteld op Nee, maar kan op elk gewenst moment worden ingeschakeld.

![](assets/spend-management-methods-1.png)

Wanneer toegelaten, trekt deze eigenschap automatisch binnen van om het even welke campagne/programma van CRM die aan de volgende criteria voldoet:

i. [!DNL Marketo Measure] kijkt eerst of creeert de Campagne/het Programma aanraakpunten, of van een gelijke [Campagnesynchronisatieregel](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md) die is gemaakt, of een overeenkomst [Programmasynchronisatieregel](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md) die is gemaakt, of de [Waarde van aanraakpunten koper inschakelen](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md#how-to-create-a-campaign-and-sync-buyer-touchpoints) is &quot;Inclusief alle campagneleden&quot; of &quot;Inclusief leden van de campagne die worden geantwoord&quot;.

ii. Een begindatum moet in de campagne/het programma worden ingevuld

iii. Een einddatum moet in de campagne/het programma worden ingevuld

iv. Werkelijke kosten (voor campagnes in SFDC) of Periode-kosten (voor programma&#39;s in Marketo) moeten worden gespecificeerd.

**3 Handmatige kosten uploaden**

Met deze methode kunt u [gegevens handmatig uploaden](/help/marketing-spend/spend-management/marketing-channel-costs.md#uploading-marketing-costs) voor de kanalen en subkanalen die niet door API Verbonden Rekeningen of de Kostensynchronisatie van de Campagne van CRM worden behandeld. Door naar de sectie Marketing Spend in uw [!DNL Marketo Measure] , kunt u via een CSV-bestand doorlopende gegevens uploaden voor elk van uw kanalen.

Klanten kunnen een combinatie van deze drie methoden gebruiken om hun uitgaven te beheren, afhankelijk van de specifieke instelling van het [!DNL Marketo Measure]. Omdat er drie methoden zijn voor het importeren van uitgaven in [!DNL Marketo Measure]We raden u ten zeerste aan om uw in Discover gevestigde Marketing Spend-board te gebruiken voor een uitgebreide weergave van alle gebruikte gegevens. Dit bord is de enige plaats waar u al uw kanalen en hun bijbehorende uitgaven kunt zien. Met het toetsenbord Marketing Spend kunt u snel bepalen waar er leemten in uw bestedingsgegevens zijn en hoe u uw ROI-rapportage kunt verbeteren.
