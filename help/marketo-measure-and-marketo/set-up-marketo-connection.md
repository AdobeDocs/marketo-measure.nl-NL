---
description: Marketo-verbinding instellen -  [!DNL Marketo Measure]
title: Marketo-verbinding instellen
exl-id: 11660539-1cc5-4768-8f22-d6f7cd0b94f3
feature: Integration
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 0%

---


# Marketo-verbinding instellen {#set-up-marketo-connection}

Hieronder wordt beschreven hoe u verbinding maakt met Marketo.

>[!PREREQUISITES]
>
>[&#x200B; creeer een slechts rol van de Gebruiker van API &#x200B;](https://experienceleague.adobe.com/docs/marketo/using/product-docs/administration/users-and-roles/create-an-api-only-user.html){target="_blank"} voor de [!DNL Marketo Measure]/verbinding van Marketo Engage.

1. Klik in [!DNL Marketo Measure] op de vervolgkeuzelijst **[!UICONTROL My Account]** en selecteer **[!UICONTROL Settings]** .

   ![&#x200B; Marketo Measure Mijn drop-down Rekening met de optie van Montages &#x200B;](assets/set-up-marketo-connection-1.png)

1. Klik onder [!UICONTROL Integrations] op **[!UICONTROL Connections]** .

   ![&#x200B; het menu van de Integratie met de optie van Verbindingen &#x200B;](assets/set-up-marketo-connection-2.png)

1. Klik op **[!UICONTROL Set Up New CRM Connection]**.

   ![&#x200B; Opstelling Nieuwe knoop van de Verbinding van CRM &#x200B;](assets/set-up-marketo-connection-3.png)

1. Klik op de knop **[!UICONTROL Connect]** naast Marketo.

   ![&#x200B; verbind knoop naast de integratieoptie van Marketo &#x200B;](assets/set-up-marketo-connection-4.png)

1. Meld u aan bij uw Marketo Engage-account op een nieuw tabblad. Ga naar **Admin** > **Diensten van het Web**. Schuif omlaag naar REST API. Markeer en sla de URL van het eindpunt en de identiteitsservice op. U hebt ze nodig in de volgende stappen.

   ![&#x200B; de pagina die van de Diensten van het Web van Marketo REST API eindpunt en identiteit URLs toont &#x200B;](assets/set-up-marketo-connection-5.png)

1. Nog in Marketo Engage, uitgezochte **LaunchPoint** in de boom op de linkerzijde. Vind de douanedienst die u met Marketo Measure wilt verbinden en **Details van de Mening** klikken.

   ![&#x200B; het menu van StartPoint met de douanedienst en de optie van Details van de Mening &#x200B;](assets/set-up-marketo-connection-6.png)

1. Markeer en sla de client-id en het clientgeheim op. Klik **dicht**.

   ![&#x200B; de dienstdetails van LaunchPoint die identiteitskaart van de Cliënt en Geheime Cliënt tonen &#x200B;](assets/set-up-marketo-connection-7.png)

1. Vul de velden weer in [!DNL Marketo Measure] met de gegevens die u hebt verzameld.

   ![&#x200B; de verbindingsvorm van Marketo met eindpunt en credentiegebieden &#x200B;](assets/set-up-marketo-connection-8.png)

1. Klik op **[!UICONTROL Authenticate]** nadat u de waarden hebt ingevoerd. Uw Marketo Engage-account is verbonden met [!DNL Marketo Measure] .

   ![&#x200B; Succesvol bericht van de de verbindingsbevestiging van Marketo &#x200B;](assets/set-up-marketo-connection-9.png)

   >[!NOTE]
   >[!DNL Marketo Measure] roept namens u de Marketo API aan zonder uw Marketo API-limieten te verbruiken. U hoeft zich dus geen zorgen te maken over uiteinden en krediettoewijzing bij andere integraties.
