---
description: OAuth met  [!DNL Azure Active Directory]  voor de begeleiding van CRM van de Dynamica voor de gebruikers van Marketo Measure
title: OAuth met  [!DNL Azure Active Directory]  voor Dynamica CRM
exl-id: 0a2f6b29-541d-4965-a460-e6f19b934edb
feature: Microsoft Dynamics
hidefromtoc: true
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 1%

---

# OAuth met [!DNL Azure Active Directory] voor Dynamics CRM {#oauth-with-azure-active-directory-for-dynamics-crm}

## Betrokken personen {#who-s-affected}

Deze setup is bedoeld voor nieuwe [!DNL Marketo Measure] -klanten die Dynamics CRM gebruiken met een [!DNL Azure Active Directory] (AAD)-account, of voor klanten die van hun oudere gebruikersnaam en wachtwoord naar [!DNL Azure Active Directory] willen migreren met OAuth.

>[!NOTE]
>
>Voor beide scenario&#39;s, wordt AAD opstelling hier om het verbinden van uw instantie van de Dynamiek in [!DNL Marketo Measure] als Leverancier van Gegevens te vergemakkelijken.

## Nieuwe toepassing instellen {#set-up-new-application}

1. Teken binnen aan uw [ Azure Portaal ](https://portal.azure.com/#home).

1. Kies de Azure AD-huurder door op uw account in de rechterbovenhoek van de pagina te klikken, gevolgd door op de navigatie Switch Directory te klikken en vervolgens de juiste huurder te selecteren. Sla deze stap over als u slechts één Azure AD-huurder onder uw account hebt of als u al de juiste Azure AD-huurder hebt geselecteerd.

   ![1. Kies de Azure AD huurder door uw rekening in te klikken ](assets/bizible-taxonomy-1.png)

1. Zoek naar &quot;[!DNL Azure Active Directory]&quot;in de onderzoeksbar en klik de naam om te openen.

   ![1. Zoek naar &quot;Azure Actieve Folder&quot;in de onderzoeksbar en ](assets/microsoft-guide-1.png)

1. Klik op **[!UICONTROL App Registrations]** in het menu aan de linkerkant.

   ![1. Klik de Registraties van de Toepassing in het linkermenu.](assets/microsoft-guide-2.png)

1. Klik op **[!UICONTROL New Registration]** boven.

   ![1. Klik op Nieuwe registratie bovenaan.](assets/microsoft-guide-3.png)

1. Volg de aanwijzingen en maak een toepassing. Het maakt niet uit als het een Webtoepassing of een openbare cliënt (mobiel &amp; Desktop) toepassing is, maar als u specifieke voorbeelden voor Webtoepassingen of openbare cliënttoepassingen zou willen, controleer uit [ quickstart ](https://learn.microsoft.com/en-us/azure/active-directory/develop/v2-overview).
a. De naam is de toepassingsnaam en beschrijft de toepassing die u voor de eindgebruikers wilt gebruiken.
b. Selecteer onder Ondersteunde accounttypen de optie Accounts in een willekeurige organisatiemap en persoonlijke Microsoft-accounts.
c. Geef de Redirect URI op. Voor webtoepassingen is dit de basis-URL van uw app waar gebruikers zich kunnen aanmelden. Bijvoorbeeld `http://localhost:12345` . Azure AD gebruikt deze voor openbare clients (mobiel en bureaublad) om tokenreacties te retourneren. Voer een waarde in die specifiek is voor uw toepassing. Bijvoorbeeld `http://MyFirstAADApp` .

1. Zodra u de registratie hebt voltooid, wijst Azure AD uw toepassing een unieke cliënt herkenningsteken (toepassings identiteitskaart) toe. U hebt deze waarde in de volgende sectie nodig, kopieer deze dus van de toepassingspagina.

1. Als u uw toepassing wilt zoeken in de Azure-portal, klikt u op **[!UICONTROL App Registrations]** en vervolgens op **[!UICONTROL All Applications]** . De nieuwe toepassing openen

1. Klik op **[!UICONTROL Authentication]** in het menu aan de linkerkant.

   ![1. Klik Authentificatie in het linkermenu.](assets/microsoft-guide-4.png)

1. Voeg de URL&#39;s [!DNL Marketo Measure] redirect: `https://apps.bizible.com/OAuth2` en `https://apps.bizible.com/OAuth2?identityOnly=true` toe aan de lijst met URL&#39;s omleiden.

   ![1. Voeg de omleidings-URL&#39;s voor Marketo Measure toe: https://apps.bizible.com/OAuth2 en https://apps.bizible.com/OAuth2?identityOnly=true ](assets/microsoft-guide-5.png)

1. Navigeer naar het tabblad API-machtigingen en controleer of de juiste machtigingen aan de toepassing zijn toegewezen.

   ![1. Navigeer aan het lusje van Toestemmingen API en zorg ervoor dat ](assets/microsoft-guide-6.png)

1. Van hier, ga &quot;[!UICONTROL enterprise]&quot;in het onderzoeksvakje in en klik **[!UICONTROL Enterprise Applications]**.

   ![1. Van hier, ga &quot;onderneming&quot;in het onderzoeksvakje in en klik ](assets/microsoft-guide-7.png)

1. Zoek en open de nieuwe toepassing opnieuw vanuit de lijst met toepassingen.

1. Klik op **[!UICONTROL Grant Admin Consent for (instance name)]** op het tabblad Machtigingen.

   ![1. Van het lusje van Toestemmingen, klik de Toestemming van Admin van de Verlening voor (instantie ](assets/microsoft-guide-8.png)

1. Klik op **[!UICONTROL Accept]**.

   ![1. Klik op Accepteren.](assets/microsoft-guide-9.png)

1. Van het &quot;[!UICONTROL Users and Groups]&quot;lusje, zorg ervoor dat de geldige &quot;Gebruikers en de Groepen&quot;aan de Toepassing worden toegewezen.

   ![1. Van het &quot;Gebruikers en Groepen&quot;lusje, zorg ervoor dat ](assets/microsoft-guide-10.png)

## Een toepassingsgebruiker maken {#creating-an-application-user}

Wanneer de toepassingsregistratie is voltooid, kan een toepassingsgebruiker worden gemaakt.

1. Navigeer naar uw omgeving Gemeenschappelijke gegevensservice (`https://[org].crm.dynamics.com`).

1. Navigeer naar **[!UICONTROL Settings]** > **[!UICONTROL Security]** > **[!UICONTROL Users]** .

1. Kies **[!UICONTROL Application Users]** in het weergavefilter.

1. Selecteer **[!UICONTROL + New]** .

1. Voer in het formulier Application User de vereiste gegevens in.

   >[!NOTE]
   >
   >* De gegevens van de gebruikersnaam mogen niet overeenkomen met een gebruiker die in de [!DNL Azure Active Directory] voorkomt.
   >
   >* Voer in het veld Toepassings-id de toepassings-id in van de toepassing die u eerder hebt geregistreerd in de Azure AD.

1. Als de instelling juist is, wordt de waarde automatisch ingevuld in de velden **[!UICONTROL Save]** en **[!UICONTROL Application ID URI]** nadat u **[!UICONTROL Azure AD Object Id]** hebt geselecteerd.

1. Voordat u het gebruikersformulier afsluit, kiest u **[!UICONTROL Manage Roles]** en wijst u een beveiligingsrol toe aan deze gebruiker van de toepassing, zodat de gebruiker van de toepassing toegang heeft tot de gewenste organisatiegegevens.

## De instantie van de Dynamiek verbinden via OAuth {#connecting-your-dynamics-instance-via-oAuth}

1. Wanneer vestiging uw verbinding van de Dynamiek voor het eerst, volg stappen 1-5 van &quot;CRM als sectie van de Leverancier van Gegevens&quot;in [ dit artikel ](/help/microsoft-dynamics-crm-installation-guide.md).

1. Wanneer ertoe aangezet voor OAuth geloofsbrieven, vul identiteitskaart van de Cliënt, Geheime cliënt, en identiteitskaart URI in van de Toepassing die opstelling in de sectie hierboven waren.

a. Client-id is de id uit stap 7 in de bovenstaande sectie. Als u het niet hebt weggeschreven, wordt de toepassings-id weergegeven in de instellingen van de toepassingsregistratie.

b. Client Secret is het toepassingsgeheim dat in de Azure Portal voor uw toepassing is gemaakt onder Certificates &amp; Secrets.

![ b. Clientgeheim is het toepassingsgeheim dat in het Azure Portal is gemaakt ](assets/microsoft-guide-11.png)

c. De URI van de toepassings-id is de URL van de doel-API (beveiligde bron). Als u de URL van de toepassings-id wilt zoeken, klikt u in de Azure Portal op [!DNL Azure Active Directory] , klikt u op Toepassingsregistraties, opent u de pagina Instellingen van de toepassing en klikt u vervolgens op Eigenschappen. Het kan ook een externe bron zijn zoals `https://graph.microsoft.com` . Dit is normaal de URL van de instantie Dynamics.

1. Nadat u op **[!UICONTROL Submit]** hebt geklikt, wordt u gevraagd u aan te melden bij [!DNL Azure Active Directory] . Wanneer de verificatie is gelukt, wordt uw Dynamics-account verbonden als een gegevensaanbieder binnen [!DNL Marketo Measure] .

## Uw rekening van de Dynamiek opnieuw voor authentiek verklaren {#re-authenticating-your-dynamics-account}

1. Ga in de [!DNL Marketo Measure] -toepassing naar **[!UICONTROL My Settings]** > **[!UICONTROL Settings]** > **[!UICONTROL Connections]** .

1. Klik het belangrijkste pictogram in de sectie van CRM naast de verbinding van de Dynamica.

1. Wanneer op de toets wordt geklikt, wordt een pop-up weergegeven en wordt u gevraagd om de URI voor de client-id, clientgeheim en toepassings-id in te voeren, vergelijkbaar met de aanmeldstroom.

   ![1. Wanneer op de toets wordt geklikt, wordt een pop-up weergegeven en bent u ](assets/microsoft-guide-12.png)

1. Nadat u op **[!UICONTROL Submit]** hebt geklikt, wordt u gevraagd u aan te melden bij [!DNL Azure Active Directory] . Wanneer de verificatie is gelukt, wordt uw Dynamics-account opnieuw geautoriseerd binnen [!DNL Marketo Measure] .
