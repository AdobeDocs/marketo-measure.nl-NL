---
unique-page-id: 37357059
description: OAuth met [!DNL Azure Active Directory] voor Dynamics CRM - [!DNL Marketo Measure]
title: OAuth met [!DNL Azure Active Directory] voor Dynamics CRM
exl-id: 0a2f6b29-541d-4965-a460-e6f19b934edb
feature: Microsoft Dynamics
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 0%

---

# OAuth met [!DNL Azure Active Directory] voor Dynamics CRM {#oauth-with-azure-active-directory-for-dynamics-crm}

## Betrokken personen {#who-s-affected}

Deze instelling is bedoeld voor nieuwe [!DNL Marketo Measure] klanten die Dynamische CRM met gebruiken [!DNL Azure Active Directory] (AAD) of voor klanten die van hun oude gebruikersnaam en wachtwoord willen migreren naar [!DNL Azure Active Directory] met OAuth.

>[!NOTE]
>
>Voor beide scenario&#39;s, wordt AAD opstelling hier om het verbinden van uw instantie van de Dynamiek in te vergemakkelijken [!DNL Marketo Measure] als een gegevensaanbieder.

## Nieuwe toepassing instellen {#set-up-new-application}

1. Meld u aan bij uw [Azure Portal](https://portal.azure.com/#home).

1. Kies uw Azure AD huurder door op uw rekening in de hoogste hoek van de pagina te klikken, door op de navigatie van de Folder van de Schakelaar te klikken en dan de aangewezen huurder te selecteren (sla deze stap over als u slechts één Azure AD huurder onder uw rekening hebt of als u reeds de aangewezen Azure AD huurder hebt geselecteerd).

   ![](assets/setup-2.png)

1. Zoeken naar &quot;[!DNL Azure Active Directory]&quot; in de zoekbalk en klik op de naam die u wilt openen.

   ![](assets/setup-3.png)

1. Klikken **[!UICONTROL App Registrations]** in het linkermenu.

   ![](assets/setup-4.png)

1. Klikken **[!UICONTROL New Registration]** bovenaan.

   ![](assets/setup-5.png)

1. Volg de aanwijzingen en maak een nieuwe toepassing. Het maakt niet uit of het een webtoepassing of een openbare clienttoepassing (mobiel en bureaublad) is, maar als u specifieke voorbeelden voor webtoepassingen of openbare clienttoepassingen wilt, bekijkt u onze [quickstart](https://docs.microsoft.com/en-us/azure/active-directory/develop/v1-overview).\
   a. De naam is de toepassingsnaam en beschrijft de toepassing die u voor de eindgebruikers wilt gebruiken.\
   b. Selecteer onder Ondersteunde accounttypen de optie Accounts in een willekeurige organisatiemap en persoonlijke Microsoft-accounts.\
   c. Geef de Redirect URI op. Voor webtoepassingen is dit de basis-URL van uw app waar gebruikers zich kunnen aanmelden. Bijvoorbeeld: `http://localhost:12345`. Azure AD gebruikt deze voor een openbare client (mobiel en bureaublad) om tokenreacties te retourneren. Voer een waarde in die specifiek is voor uw toepassing. Bijvoorbeeld: `http://MyFirstAADApp`.

1. Zodra u de registratie hebt voltooid, zal Azure AD uw toepassing een unieke cliënt herkenningsteken (toepassings identiteitskaart) toewijzen. U hebt deze waarde in de volgende sectie nodig, kopieer deze dus van de toepassingspagina.

1. Als u uw toepassing wilt zoeken in de Azure-portal, klikt u op **[!UICONTROL App Registrations]** en klik vervolgens op **[!UICONTROL All Applications]**. De nieuwe toepassing openen

1. Klikken **[!UICONTROL Authentication]** in het linkermenu.

   ![](assets/setup-9.png)

1. Voeg de [!DNL Marketo Measure] URL&#39;s omleiden: `https://apps.bizible.com/OAuth2` en `https://apps.bizible.com/OAuth2?identityOnly=true` aan de lijst van Redirect URLs.

   ![](assets/setup-10.png)

1. Navigeer naar het tabblad API-machtigingen en controleer of de juiste machtigingen aan de toepassing zijn toegewezen.

   ![](assets/setup-10a.png)

1. Voer van hier &quot;[!UICONTROL enterprise]&quot; in het zoekvak en klik op **[!UICONTROL Enterprise Applications]**.

   ![](assets/setup-11.png)

1. Zoek en open de nieuwe toepassing opnieuw vanuit de lijst met toepassingen.

1. Klik op het tabblad Machtigingen op **[!UICONTROL Grant Admin Consent for (instance name)]**.

   ![](assets/setup-13a.png)

1. Klik op **[!UICONTROL Accept]**.

   ![](assets/setup-13b.png)

1. Van de &quot;[!UICONTROL Users and Groups]&quot;, zorgt u ervoor dat de geldige &quot;Gebruikers en groepen&quot; zijn toegewezen aan de toepassing.

   ![](assets/setup-14.png)

## Een toepassingsgebruiker maken {#creating-an-application-user}

Wanneer de toepassingsregistratie is voltooid, kan een toepassingsgebruiker worden gemaakt.

1. Navigeer naar de omgeving van uw algemene gegevensservice (`https://[org].crm.dynamics.com`).

1. Navigeren naar **[!UICONTROL Settings]** > **[!UICONTROL Security]** > **[!UICONTROL Users]**.

1. Kies **[!UICONTROL Application Users]** in het weergavefilter.

1. Selecteren **[!UICONTROL + New]**.

1. Voer in het formulier Application User de vereiste gegevens in.

   >[!NOTE]
   >
   >* De gegevens van de gebruikersnaam mogen niet overeenkomen met een gebruiker die voorkomt in het dialoogvenster [!DNL Azure Active Directory].
   >
   >* Voer in het veld Toepassings-id de toepassings-id in van de toepassing die u eerder hebt geregistreerd in de Azure AD.

1. Als de setup correct is, selecteert u **[!UICONTROL Save]** de **[!UICONTROL Application ID URI]** en **[!UICONTROL Azure AD Object Id]** in de velden worden de juiste waarden automatisch ingevuld.

1. Voordat u het gebruikersformulier afsluit, kiest u **[!UICONTROL Manage Roles]** en wijs een veiligheidsrol aan deze toepassingsgebruiker toe zodat de toepassingsgebruiker tot de gewenste organisatiegegevens kan toegang hebben.

## De instantie van de Dynamiek verbinden via OAuth {#connecting-your-dynamics-instance-via-oAuth}

1. Wanneer het opzetten van uw verbinding van de Dynamica voor het eerst, volg stappen 1-5 van de &quot;CRM als sectie van de Leverancier van Gegevens&quot;in [dit artikel](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/microsoft-dynamics-crm-installation-guide.md).

1. Wanneer ertoe aangezet voor OAuth geloofsbrieven, vul identiteitskaart van de Cliënt, Geheime cliënt, en identiteitskaart URI in van de Toepassing die opstelling in de sectie hierboven waren.

a. Client-id is de id uit stap 7 in de bovenstaande sectie. Als u het niet hebt weggeschreven, wordt de toepassings-id weergegeven in de instellingen van de toepassingsregistratie.

b. Client Secret is het toepassingsgeheim dat in de Azure Portal voor uw toepassing is gemaakt onder Certificates &amp; Secrets.

![](assets/creating-2e.png)

c. De URI van de toepassings-id is de URL van de doel-API (beveiligde bron). Als u de URL van de toepassings-id wilt zoeken, klikt u in het Azure Portal op [!DNL Azure Active Directory], klikt u op Toepassingsregistraties, opent u de pagina Instellingen van de toepassing en klikt u vervolgens op Eigenschappen. Het kan ook een externe bron zijn zoals `https://graph.microsoft.com`. Dit is normaal de URL van de instantie Dynamics.

1. Nadat u op **[!UICONTROL Submit]**, wordt u gevraagd u aan te melden [!DNL Azure Active Directory]. Wanneer de verificatie is gelukt, wordt uw Dynamics-account verbonden als een gegevensaanbieder binnen [!DNL Marketo Measure].

## Uw rekening van de Dynamiek opnieuw voor authentiek verklaren {#re-authenticating-your-dynamics-account}

1. Als je in de [!DNL Marketo Measure] toepassing, ga naar **[!UICONTROL My Settings]** > **[!UICONTROL Settings]** > **[!UICONTROL Connections]**.

1. Klik op het sleutelpictogram in de sectie van CRM naast de verbinding van de Dynamica.

1. Zodra de sleutel wordt geklikt, zal een pop-up verschijnen en u zal worden ertoe aangezet om Cliënt ID, het Geheime punt van de Cliënt, en identiteitskaart URI van de Toepassing in te gaan, gelijkend op de inschrijvingsstroom.

   ![](assets/re-authenticating-3.png)

1. Nadat u op **[!UICONTROL Submit]**, wordt u gevraagd u aan te melden [!DNL Azure Active Directory]. Wanneer de authentificatie succesvol is, zal uw rekening van de Dynamica binnen opnieuw geautoriseerd worden [!DNL Marketo Measure].
