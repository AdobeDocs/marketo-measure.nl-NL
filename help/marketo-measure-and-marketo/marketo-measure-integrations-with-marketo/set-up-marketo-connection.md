---
unique-page-id: 42762762
description: Marketo-verbinding instellen - [!DNL Marketo Measure]
title: Marketo-verbinding instellen
exl-id: 11660539-1cc5-4768-8f22-d6f7cd0b94f3
feature: Integration
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 0%

---

# Marketo-verbinding instellen {#set-up-marketo-connection}

Hieronder wordt beschreven hoe u verbinding maakt met Marketo.

>[!PREREQUISITES]
>
>[Een gebruikersrol met alleen API maken](https://experienceleague.adobe.com/docs/marketo/using/product-docs/administration/users-and-roles/create-an-api-only-user.html) voor de [!DNL Marketo Measure]/Marketo Engage-verbinding.

1. In [!DNL Marketo Measure]klikt u op de knop **[!UICONTROL My Account]** vervolgkeuzelijst en selecteer **[!UICONTROL Settings]**.

   ![](assets/set-up-marketo-connection-1.png)

1. Onder [!UICONTROL Integrations], klikt u op **[!UICONTROL Connections]**.

   ![](assets/set-up-marketo-connection-2.png)

1. Klik op **[!UICONTROL Set Up New CRM Connection]**.

   ![](assets/set-up-marketo-connection-3.png)

1. Klik op de knop **[!UICONTROL Connect]** naast Marketo.

   ![](assets/set-up-marketo-connection-4.png)

1. Meld u aan bij uw Marketo Engage-account op een nieuw tabblad. Ga naar **Beheerder** > **Webservices**. Schuif omlaag naar REST API. Markeer en sla de URL van het eindpunt en de identiteitsservice op. Je hebt ze zo nodig.

   ![](assets/set-up-marketo-connection-5.png)

1. Stilstaand in Marketo Engage, selecteer **LaunchPoint** in de boomstructuur links. Zoek de aangepaste service waarmee u verbinding wilt maken met Marketo Measure en klik op **Details weergeven**.

   ![](assets/set-up-marketo-connection-6.png)

1. Markeer en sla de client-id en het clientgeheim op. Klikken **Sluiten**.

   ![](assets/set-up-marketo-connection-7.png)

1. Terug naar [!DNL Marketo Measure]Vul de velden in met de gegevens die u zojuist hebt verzameld.

   ![](assets/set-up-marketo-connection-8.png)

1. Klik op **[!UICONTROL Authenticate]**. Uw Marketo Engage-account wordt dan verbonden met [!DNL Marketo Measure].

   ![](assets/set-up-marketo-connection-9.png)

   >[!NOTE]
   >
   >[!DNL Marketo Measure] roept namens u de Marketo API aan zonder uw Marketo API-limieten te gebruiken. U hoeft zich dus geen zorgen te maken over de plafonds en de krediettoewijzing aan andere integraties.
