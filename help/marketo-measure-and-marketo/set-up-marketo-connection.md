---
description: Richtlijnen voor Marketo Connection instellen voor Marketo Measure-gebruikers
title: Marketo-verbinding instellen
exl-id: 11660539-1cc5-4768-8f22-d6f7cd0b94f3
feature: Integration
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 0%

---

# Marketo-verbinding instellen {#set-up-marketo-connection}

Hieronder wordt beschreven hoe u verbinding maakt met Marketo.

>[!PREREQUISITES]
>
>[&#x200B; creeer een slechts rol van de Gebruiker van API &#x200B;](https://experienceleague.adobe.com/docs/marketo/using/product-docs/administration/users-and-roles/create-an-api-only-user.html) voor de [!DNL Marketo Measure]/verbinding van Marketo Engage.

1. Klik in [!DNL Marketo Measure] op de vervolgkeuzelijst **[!UICONTROL My Account]** en selecteer **[!UICONTROL Settings]** .

   ![](assets/set-connection-7.png)

1. Klik onder [!UICONTROL Integrations] op **[!UICONTROL Connections]** .

   ![](assets/set-connection-8.png)

1. Klik op **[!UICONTROL Set Up New CRM Connection]**.

   ![](assets/set-connection-9.png)

1. Klik op de knop **[!UICONTROL Connect]** naast Marketo.

   ![](assets/set-connection-5.png)

1. Meld u aan bij uw Marketo Engage-account op een nieuw tabblad. Ga naar **Admin** > **Diensten van het Web**. Schuif omlaag naar REST API. Markeer en sla de URL van het eindpunt en de identiteitsservice op. U hebt ze nodig in de volgende stappen.

   ![](assets/set-connection-6.png)

1. Nog in Marketo Engage, uitgezochte **LaunchPoint** in de boom op de linkerzijde. Vind de douanedienst die u met Marketo Measure wilt verbinden en **Details van de Mening** klikken.

   ![](assets/set-connection-4.png)

1. Markeer en sla de client-id en het clientgeheim op. Klik **dicht**.

   ![](assets/set-connection-3.png)

1. Vul de velden weer in [!DNL Marketo Measure] met de gegevens die u hebt verzameld.

   ![](assets/set-connection-1.png)

1. Klik op **[!UICONTROL Authenticate]** nadat u de waarden hebt ingevoerd. Uw Marketo Engage-account is verbonden met [!DNL Marketo Measure] .

   ![](assets/set-connection-2.png)

   >[!NOTE]
   >
   >[!DNL Marketo Measure] roept namens u de Marketo API aan zonder uw Marketo API-limieten te verbruiken. U hoeft zich dus geen zorgen te maken over uiteinden en krediettoewijzing bij andere integraties.
