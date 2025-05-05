---
unique-page-id: 42762762
description: Marketo-verbinding instellen -  [!DNL Marketo Measure]
title: Marketo-verbinding instellen
exl-id: 11660539-1cc5-4768-8f22-d6f7cd0b94f3
feature: Integration
source-git-commit: de366de2d1df3d4dc9fc33e5fd0dab225b6af081
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 0%

---

# Marketo-verbinding instellen {#set-up-marketo-connection}

Hieronder wordt beschreven hoe u verbinding maakt met Marketo.

>[!PREREQUISITES]
>
>[ creeer een slechts rol van de Gebruiker van API ](https://experienceleague.adobe.com/docs/marketo/using/product-docs/administration/users-and-roles/create-an-api-only-user.html?lang=nl-NL){target="_blank"}  voor de [!DNL Marketo Measure] /Marketo Engage verbinding.

1. Klik in [!DNL Marketo Measure] op de vervolgkeuzelijst **[!UICONTROL My Account]** en selecteer **[!UICONTROL Settings]** .

   ![](assets/set-up-marketo-connection-1.png)

1. Klik onder [!UICONTROL Integrations] op **[!UICONTROL Connections]** .

   ![](assets/set-up-marketo-connection-2.png)

1. Klik op **[!UICONTROL Set Up New CRM Connection]**.

   ![](assets/set-up-marketo-connection-3.png)

1. Klik op de knop **[!UICONTROL Connect]** naast Marketo.

   ![](assets/set-up-marketo-connection-4.png)

1. Meld u aan bij uw Marketo Engage-account op een nieuw tabblad. Ga naar **Admin** > **Diensten van het Web**. Schuif omlaag naar REST API. Markeer en sla de URL van het eindpunt en de identiteitsservice op. U hebt ze nodig in de volgende stappen.

   ![](assets/set-up-marketo-connection-5.png)

1. Nog in Marketo Engage, uitgezochte **LaunchPoint** in de boom op de linkerzijde. Vind de douanedienst die u met Marketo Measure wilt verbinden en **Details van de Mening** klikken.

   ![](assets/set-up-marketo-connection-6.png)

1. Markeer en sla de client-id en het clientgeheim op. Klik **dicht**.

   ![](assets/set-up-marketo-connection-7.png)

1. Vul de velden weer in [!DNL Marketo Measure] met de gegevens die u hebt verzameld.

   ![](assets/set-up-marketo-connection-8.png)

1. Klik op **[!UICONTROL Authenticate]** nadat u de waarden hebt ingevoerd. Uw Marketo Engage-account is verbonden met [!DNL Marketo Measure] .

   ![](assets/set-up-marketo-connection-9.png)

   >[!NOTE]
   >
   >[!DNL Marketo Measure] roept namens u de Marketo API aan zonder uw Marketo API-limieten te verbruiken. U hoeft zich dus geen zorgen te maken over uiteinden en krediettoewijzing bij andere integraties.
