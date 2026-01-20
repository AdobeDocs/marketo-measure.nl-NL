---
description: Methoden voor uitgavenbeheer - [!DNL Marketo Measure]
title: Methoden voor uitgavenbeheer
exl-id: 36478d8d-986c-4d4f-8854-3287d6c57a9d
feature: Spend Management
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 0%

---

# Methoden voor uitgavenbeheer {#spend-management-methods}

De gegevens van de uitgaven zijn zeer belangrijk voor het succes van ROI rapportering met [!DNL Marketo Measure]. Als u nauwkeurige en uitgebreide ROI-rapporten wilt hebben over al uw kanalen en subkanalen, moet u ervoor zorgen dat u de juiste uitgavengegevens in [!DNL Marketo Measure] hebt opgenomen.

Er zijn drie manieren om gegevens in [!DNL Marketo Measure] te krijgen. Elke methode is ontworpen om te putten uit gegevens van bepaalde gegevensinput.

**1 API Verbonden Rekeningen**

Voor elke advertentierekening waarmee u via een API verbinding hebt gemaakt met [!DNL Marketo Measure], wordt de uitgave automatisch naar [!DNL Marketo Measure] getrokken voor ROI-rapportage. Als u wilt controleren welke accounts u hebt verbonden en dus uw uitgaven opgeeft, gaat u naar de [!DNL Marketo Measure] -app en selecteert u de tab [!UICONTROL Connections] onder de sectie [!UICONTROL Integrations] . Voor meer details over vestiging uw API verbindingen, overzicht [ Geïntegreerde Ad Platforms ](/help/api-connections/utilizing-marketo-measures-api-connections/integrated-ad-platforms.md#how-to-connect-ad-platforms).

**2 de Kostensynchronisatie van de Campagne van CRM**

Elke [!DNL Marketo Measure] rekening heeft toegang tot een eigenschap genoemd [ de Kosten van de Campagne van CRM van de Synchronisatie ](/help/marketing-spend/spend-management/crm-campaign-costs.md#availability). Deze functiebit is standaard ingesteld op Nee, maar kan op elk gewenst moment worden ingeschakeld.

![](assets/spend-management-methods-1.png)

Wanneer toegelaten, trekt deze eigenschap automatisch binnen van om het even welke campagne/programma van CRM die aan de volgende criteria voldoet:

i. [!DNL Marketo Measure] kijkt eerst om te zien of creeert de Campagne/het Programma aanraakpunten, of van een passende [ regel van de Synchronisatie van de Campagne ](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md) die werd gecreeerd, of een passende [ regel van de Synchronisatie van het Programma ](/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md) die werd gecreeerd, of [ laat de waarde van de Aanraakpunten van de Koper ](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md#how-to-create-a-campaign-and-sync-buyer-touchpoints) toe is &quot;omvat Alle Leden van de Campagne&quot;of &quot;omvat Beantwoorde&quot;Campagne.

ii. Een begindatum moet in de campagne/het programma worden ingevuld

iii. Een einddatum moet in de campagne/het programma worden ingevuld

iv. De werkelijke kosten (voor campagnes in SFDC) of de kosten voor de periode (voor programma&#39;s in Marketo) moeten worden gespecificeerd.

**3 Handmatig uploaden van Kosten**

Deze methode staat u toe om [ manueel te uploaden besteedt gegevens ](/help/marketing-spend/spend-management/marketing-channel-costs.md#uploading-marketing-costs) voor die kanalen en subchannel die niet door API Verbonden Rekeningen of de Synchronisatie van de Kosten van de Campagne van CRM worden behandeld. Door naar de sectie Marketinguitgaven in uw [!DNL Marketo Measure] -instellingen te navigeren, kunt u via een CSV-bestand gegevens uploaden voor elk van uw kanalen.

Klanten kunnen een combinatie van deze drie methoden gebruiken om hun uitgaven te beheren, afhankelijk van de specifieke instellingen van de [!DNL Marketo Measure] . Omdat er drie methoden zijn om uitgaven in [!DNL Marketo Measure] te importeren, raden we u ten zeerste aan uw in Discover gevestigde Marketing Spend-board te gebruiken voor een uitgebreide weergave van alle gebruikte gegevens. Dit bord is de enige plaats waar u al uw kanalen en hun bijbehorende uitgaven kunt zien. Met het toetsenbord Marketing Spend kunt u snel bepalen waar er leemten in uw bestedingsgegevens zijn en hoe u uw ROI-rapportage kunt verbeteren.
