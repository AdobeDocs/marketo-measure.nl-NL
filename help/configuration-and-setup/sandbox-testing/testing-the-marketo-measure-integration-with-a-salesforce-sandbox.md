---
unique-page-id: 18874765
description: Het testen van de Integratie van de Maatregel van Marketo met een zandbak van Salesforce - [!DNL Marketo Measure] - Productdocumentatie
title: Het testen van de Integratie van de Maatregel van Marketo met een zandbak van Salesforce
exl-id: df40b000-4572-46df-aef5-8f690ca8ed7a
source-git-commit: 993a326c377b3b6ff48c4e0114b59297f9ca2ca6
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 0%

---

# Het testen van de Integratie van de Maatregel van Marketo met een zandbak van Salesforce {#testing-the-marketo-measure-integration-with-a-salesforce-sandbox}

>[!NOTE]
>
>Mogelijk ziet u instructies die &quot;[!DNL Marketo Measure]&quot; in onze documentatie, maar zie nog &quot;Bizible&quot;in uw CRM. We werken eraan dat dit wordt bijgewerkt en de herbranding wordt binnenkort weerspiegeld in uw CRM.

Een van de [!DNL Marketo Measure] kernfuncties zijn de mogelijkheid om uw digitale marketinginspanningen te volgen via acties op uw website en die gegevens vervolgens naar uw productie te verplaatsen [!DNL Salesforce org] via leads en contactpersonen. Er zijn echter meestal geen inkomende leads gemaakt van uw website binnen een Sandbox-integratie, zodat de focus op gegevens louter offline zal zijn.

Hier zijn de twee bronnen waarnaar voor beide fasen van de test wordt verwezen. [Stap 1-4](https://help.salesforce.com/apex/HTViewHelpDoc?id=lead_import_wizard.htm&amp;language=en_US) en [Stap 5-6](/help/channel-tracking-and-setup/offline-channels/syncing-offline-campaigns.md). We raden u aan deze documenten te herzien, omdat ze op sommige gebieden gedetailleerder zijn.

1. U moet enkele leads maken in een CSV zodat u deze kunt uploaden naar een campagne. De manier om dit te doen is sommige Leads door een rapport in uw productie Salesforce uit te voeren. Anders kunt u handmatig leads maken in een Excel-bestand en deze vervolgens opslaan als een CSV-bestand voor importeren. U hebt maar ongeveer 20 records nodig. Het bestand moet de volgende kolommen hebben:

   1. E-mail
   1. Bedrijf
   1. Achternaam
   1. Voornaam (optioneel, maar aanbevolen)

1. Meld u aan bij uw Sandbox-omgeving.
1. U zult eerst een testcampagne creëren. We raden u aan een type campagne te gebruiken, zoals Event of Newsletter.
1. Als de campagne eenmaal is gemaakt, uploadt u Leads als Campagneleden door **[!UICONTROL Manage Members]** > **[!UICONTROL Add Members]** > **[!UICONTROL Import Files]**.
1. Als dat is voltooid, gaat u terug naar de pagina-indeling Campagne en schakelt u Aanraakpunten voor kopers in. Dit is een keuzelijstveld. Kies de waarde: **[!UICONTROL Include All Campaign Members]**.

Zodra dit wordt gedaan, zal het een synchronisatie tussen [!DNL Marketo Measure] en [!DNL Salesforce] en past aanraakpunten toe op de records voor lead. We raden u aan de volgende dag terug te checken via een rapport met de naam: &quot;Aanraakpunt koper op leads&quot; gevonden in het dialoogvenster [!UICONTROL Buyer Touchpoints Reports] op het tabblad Rapporten. Als in het verslag een aanspreekpunt voor elke lead wordt ingevuld, is dit een teken van succes.
