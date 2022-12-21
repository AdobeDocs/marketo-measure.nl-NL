---
unique-page-id: 42762628
description: Documentatie van het Paspoort-dashboard - [!DNL Marketo Measure] - Productdocumentatie
title: Documentatie paspoortdashboard
exl-id: 43cb01a8-d02e-4086-af57-d7ec9275f87a
source-git-commit: f13e55f009f33140ff36523212ed8b9ed5449a4d
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 0%

---

# Documentatie paspoortdashboard {#passport-dashboard-documentation}

Het dashboard van het paspoort laat de Verkopers toe om Hoofd/Contacten en Kansen te bekijken die door elke pijpleidingsstadium tijdens een bepaald tijdkader zijn gegaan.

Dit dashboard heeft twee tegels:

* Kansen: Het aantal opportuniteitsrecords dat tijdens het opgegeven tijdframe door elk werkgebied wordt doorgegeven.
* Leads/contactpersonen: Het aantal lead- of contactrecords dat tijdens het opgegeven tijdkader door elk werkgebied is doorgegeven.

>[!NOTE]
>
>Op alle Discover-dashboards kan slechts één persoonlijk object, Lead of Contact, worden gerapporteerd. Deze is ingesteld in [!UICONTROL Settings] > [!UICONTROL Reporting] > [!UICONTROL Attribution Settings] > [!UICONTROL Default Dashboard Object].

Dit dashboard ondersteunt de volgende filters (alle filters zijn van toepassing op beide tegels):

* Datum: selecteer het tijdkader.
* Kanaal: filtert de records via kanalen. Een record is gekoppeld aan een kanaal als een van de aanraakpunten aan het kanaal is gekoppeld.
* Subkanaal: filtreer de records op subkanalen. Een record is gekoppeld aan een subkanaal als een van de aanraakpunten ervan is gekoppeld aan het subkanaal.
* Campagne: filtreer de verslagen door campagnes. Een record is gekoppeld aan een campagne als een van de aanraakpunten aan de campagne is gekoppeld.
* Bron campagne: filtreer de verslagen door campagnebronnen. Voorbeelden van campagnebronnen zijn Adwords, BingAds, Facebook, LinkedIn enz. Een record wordt gekoppeld aan een campagnebron als een van de aanraakpunten aan de campagnebron is gekoppeld.
* Naam CRM-account: filtert de verslagen door de Namen van de Rekening van CRM.
* Segmentfilters: filtreer de records op aangepaste segmenten. Een record is gekoppeld aan een segment als een van de aanraakpunten ervan aan het segment is gekoppeld.

Voor alle filters wordt de logica AND gebruikt.

>[!NOTE]
>
>Als een record het werkgebied op de geselecteerde datum wijzigt, wordt de record geteld voor de stappen van en naar de fasen en voor alle doorloopfasen.

## Kansen {#opportunities}

![](assets/one-1.png)

De stadia omvatten OC, geselecteerde stadia van de Trechter in Open Stadium van de Kansen ([!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL Stage Mapping]), en de Staven van de Kans van de Won ([!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL Stage Mapping]).

>[!NOTE]
>
>Voor de fasen van het Won, zijn de verslagtellingen slechts voor verslagen die in het stadium tijdens het geselecteerde tijdkader worden overgebracht.

U kunt vanaf elke balk naar beneden boren om de opportuniteitsrecords voor elk werkgebied weer te geven.

## Leads/contactpersonen {#leads-contacts}

![](assets/two-1.png)

De stadia omvatten FT, LC, geselecteerde stadia van de Trechter in Open Lood/ContactStages op Montages - CRM - de Afbeelding van het Stadium, en Omgezette Lood/ContactStages op Montages - CRM - de Afbeelding van het Stadium.

>[!NOTE]
>
>Voor Omgezette stadia, zijn de verslagtellingen slechts voor verslagen die in het stadium tijdens het geselecteerde tijdkader worden overgebracht.

U kunt vanaf elke balk naar beneden boren om de lijst met leads/contactpersonen voor elk werkgebied weer te geven.
