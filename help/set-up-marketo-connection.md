---
description: Richtlijnen voor Marketo Connection instellen voor Marketo Measure-gebruikers
title: Marketo-verbinding instellen
exl-id: 11660539-1cc5-4768-8f22-d6f7cd0b94f3
feature: Integration
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 3%

---

# Marketo-verbinding instellen {#set-up-marketo-connection}

Hieronder wordt beschreven hoe u verbinding maakt met Marketo.

>[!PREREQUISITES]
>
>[&#x200B; creeer een slechts rol van de Gebruiker van API &#x200B;](https://experienceleague.adobe.com/docs/marketo/using/product-docs/administration/users-and-roles/create-an-api-only-user.html) voor de [!DNL Marketo Measure]/verbinding van Marketo Engage.

1. Klik in [!DNL Marketo Measure] op de vervolgkeuzelijst **[!UICONTROL My Account]** en selecteer **[!UICONTROL Settings]** .

   ![1. Klik in Marketo Measure op de vervolgkeuzelijst Mijn account en &#x200B;](assets/set-connection-7.png)

1. Klik onder [!UICONTROL Integrations] op **[!UICONTROL Connections]** .

   ![1. Klik onder Integraties op Verbindingen.](assets/set-connection-8.png)

1. Klik op **[!UICONTROL Set Up New CRM Connection]**.

   ![1. Klik op Nieuwe CRM-verbinding instellen.](assets/set-connection-9.png)

1. Klik op de knop **[!UICONTROL Connect]** naast Marketo.

   ![1. Klik op de knop Verbinden naast Marketo.](assets/set-connection-5.png)

1. Meld u aan bij uw Marketo Engage-account op een nieuw tabblad. Ga naar **Admin** > **Diensten van het Web**. Schuif omlaag naar REST API. Markeer en sla de URL van het eindpunt en de identiteitsservice op. U hebt ze nodig in de volgende stappen.

   ![1. Meld u aan bij uw Marketo Engage-account op een nieuw tabblad.](assets/set-connection-6.png)

1. Nog in Marketo Engage, uitgezochte **LaunchPoint** in de boom op de linkerzijde. Vind de douanedienst die u met Marketo Measure wilt verbinden en **Details van de Mening** klikken.

   ![1. Stilstaand in Marketo Engage, uitgezochte LaunchPoint in de boom op &#x200B;](assets/set-connection-4.png)

1. Markeer en sla de client-id en het clientgeheim op. Klik **dicht**.

   ![1. Markeer en sla de client-id en het clientgeheim op. Klik op Sluiten.](assets/set-connection-3.png)

1. Vul de velden weer in [!DNL Marketo Measure] met de gegevens die u hebt verzameld.

   ![1. Terug in Marketo Measure, bevolk de gebieden met de gegevens &#x200B;](assets/set-connection-1.png)

1. Klik op **[!UICONTROL Authenticate]** nadat u de waarden hebt ingevoerd. Uw Marketo Engage-account is verbonden met [!DNL Marketo Measure] .

   ![1. Nadat u de waarden ingaat, klik voor authentiek verklaren. Uw Marketo Engage &#x200B;](assets/set-connection-2.png)

   >[!NOTE]
   >
   >[!DNL Marketo Measure] roept namens u de Marketo API aan zonder uw Marketo API-limieten te verbruiken. U hoeft zich dus geen zorgen te maken over uiteinden en krediettoewijzing bij andere integraties.
