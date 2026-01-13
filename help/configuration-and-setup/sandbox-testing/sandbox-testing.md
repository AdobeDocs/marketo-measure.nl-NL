---
description: Het testen van de Integratie van Marketo Measure met een Sandbox van Salesforce -  [!DNL Marketo Measure]
title: Marketo Measure-integratie testen met een Salesforce-sandbox
exl-id: df40b000-4572-46df-aef5-8f690ca8ed7a
feature: Salesforce
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 0%

---


# Marketo Measure-integratie testen met een Salesforce-sandbox {#testing-the-marketo-measure-integration-with-a-salesforce-sandbox}

>[!NOTE]
>U kunt instructies zien die &quot;[!DNL Marketo Measure]&quot;in de documentatie specificeren, maar nog zie &quot;Bizible&quot;in uw CRM. We werken eraan dat dit wordt bijgewerkt en de herbranding wordt binnenkort weerspiegeld in uw CRM.

Een van de kernfuncties van [!DNL Marketo Measure] is de mogelijkheid om uw digitale marketinginspanningen te volgen via acties op uw website en deze gegevens vervolgens naar uw productie te verplaatsen [!DNL Salesforce org] via leads en contactpersonen. Er zijn echter meestal geen inkomende leads gemaakt van uw website binnen een Sandbox-integratie, zodat de focus op gegevens louter offline zal zijn.

Hier zijn de twee bronnen waarnaar voor beide fasen van de test wordt verwezen. [ Stappen 1-4 ](https://help.salesforce.com/s/articleView?id=lead_import_wizard.htm&language=en_US&type=5) en [ Stappen 5-6 ](/help/channel-tracking-and-setup/offline-channels/legacy-processes/syncing-offline-campaigns.md). Het wordt aanbevolen deze documenten te herzien omdat ze op sommige gebieden gedetailleerder zijn.

1. U moet enkele leads maken in een CSV zodat u deze kunt uploaden naar een campagne. De manier om dit te doen is sommige Leads door een rapport in uw productie Salesforce uit te voeren. Anders kunt u handmatig leads maken in een Excel-bestand en deze vervolgens opslaan als een CSV-bestand voor importeren. U hebt maar ongeveer 20 records nodig. Het bestand moet de volgende kolommen hebben:

   1. E-mail
   1. Bedrijf
   1. Achternaam
   1. Voornaam (optioneel, maar aanbevolen)

1. Meld u aan bij uw Sandbox-omgeving.
1. Maak een testcampagne. Gebruik een type campagne, zoals Event of Newsletter.
1. Als de campagne eenmaal is gemaakt, uploadt u Leads als Campagneleden door **[!UICONTROL Manage Members]** > **[!UICONTROL Add Members]** > **[!UICONTROL Import Files]** te selecteren.
1. Als dat is voltooid, gaat u terug naar de pagina-indeling Campagne en schakelt u Aanraakpunten voor kopers in. Dit is een keuzelijstveld. Kies de waarde: **[!UICONTROL Include All Campaign Members]** .

Nadat dit is gedaan, schakelt het een synchronisatie uit tussen [!DNL Marketo Measure] en [!DNL Salesforce] en past aanraakpunten toe op de records voor lead. U wordt aangeraden de volgende dag een rapport weer te geven met de naam &quot;Buyer Touchpoint on Leads&quot; in de map [!UICONTROL Buyer Touchpoints Reports] op het tabblad Rapporten. Als in het verslag een aanspreekpunt voor elke lead wordt ingevuld, is dit een teken van succes.
