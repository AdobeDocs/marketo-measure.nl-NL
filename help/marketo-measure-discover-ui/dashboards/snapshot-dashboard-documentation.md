---
unique-page-id: 42762600
description: Documentatie van dashboard voor momentopnamen - [!DNL Marketo Measure] - Productdocumentatie
title: Documentatie van dashboard voor momentopnamen
exl-id: 4dfc92d2-ccab-4726-a869-3ae32aa89a5f
feature: Reporting
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 0%

---

# Documentatie van dashboard voor momentopnamen {#snapshot-dashboard-documentation}

Het dashboard van de momentopname laat u toe om de staat van uw CRM op om het even welk bepaald punt in tijd, met de distributie van verslagen over Lood/Contact en stadia van de Kans te bekijken.

Dit dashboard heeft twee tegels:

* **Momentopname van lead/contactpersoon:** Het aantal lead- of contactrecords in elk werkgebied op de geselecteerde datum.

>[!NOTE]
>
>Op alle Discover-dashboards kan slechts één persoonlijk object, Lead of Contact, worden gerapporteerd. Deze is ingesteld in [!UICONTROL Settings] > [!UICONTROL Reporting] > [!UICONTROL Attribution Settings] > [!UICONTROL Default Dashboard Object].

* **Momentopname opportunity:** Het aantal opportuniteitsrecords in elk werkgebied op de geselecteerde datum.

Dit dashboard ondersteunt de volgende filters (alle filters zijn van toepassing op beide tegels):

* Datum opname: selecteer de datum van opname.
* CRM-account-id/-naam: filter de records op CRM-account-id&#39;s of -namen.

>[!NOTE]
>
>Suggesties geven alleen namen weer.

* Kanaal: filtert de records via kanalen. Een record is gekoppeld aan een kanaal als een van de aanraakpunten aan het kanaal is gekoppeld.
* Subkanaal: filter de records op subkanalen. Een record is gekoppeld aan een subkanaal als een van de aanraakpunten ervan is gekoppeld aan het subkanaal.
* Campagne: filter de records door campagnes. Een record is gekoppeld aan een campagne als een van de aanraakpunten aan de campagne is gekoppeld.
* Bron campagne: filter de verslagen door campagnebronnen. Voorbeelden van campagnebronnen zijn [!DNL Adwords], [!DNL BingAds], [!DNL Facebook], [!DNL LinkedIn], enz. Een record wordt gekoppeld aan een campagnebron als een van de aanraakpunten aan de campagnebron is gekoppeld.
* Account-id/-naam toevoegen: filter de records op Account-id&#39;s of Namen toevoegen. Een record is gekoppeld aan een advertentiekader als een van de aanraakpunten is gekoppeld aan een campagne van de geselecteerde advertentiekeningen.

>[!NOTE]
>
>Alleen namen van suggesties worden weergegeven.

* Segmentfilters: filtert de records op aangepaste segmenten. Een record is gekoppeld aan een segment als een van de aanraakpunten ervan aan het segment is gekoppeld.

Voor alle filters wordt de logica &quot;AND&quot; gebruikt.

>[!NOTE]
>
>Als een record het werkgebied op de geselecteerde datum wijzigt, wordt de record geteld voor de stappen van en naar de fasen en voor alle doorloopfasen.

## Opname van lead/contactpersoon {#lead-contact-snapshot}

![](assets/one.png)

De fasen omvatten FT, LC en geselecteerde stadia van de Trechter in Open Lood/ContactStaven ([!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL Stage Mapping]).

U kunt vanaf elke balk naar beneden boren om de lijst met leads/contactpersonen voor elk werkgebied weer te geven.

## Opportunity-opname {#opportunity-snapshot}

![](assets/two.png)

De fasen omvatten FT, LC, geselecteerde stadia van de Trechter in Open Lood/ContactStaven ([!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL Stage Mapping]). En OC en geselecteerde stadia van de Trechter in Open Kans Stages ([!UICONTROL Settings] > [!UICONTROL CRM] > [!UICONTROL Stage Mapping]).

U kunt vanaf elke balk naar beneden boren om de opportuniteitsrecords voor elk werkgebied weer te geven.
