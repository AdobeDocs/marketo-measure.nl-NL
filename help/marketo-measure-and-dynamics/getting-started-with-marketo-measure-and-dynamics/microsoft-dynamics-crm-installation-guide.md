---
unique-page-id: 18874763
description: "[!DNL Microsoft Dynamics] CRM Installation Guide - Marketo Measurement - Product Documentation"
title: "[!DNL Microsoft Dynamics] CRM Installation Guide"
exl-id: bc422c98-60bb-49ea-9bd1-c4149ae628b1
source-git-commit: 9de82556ca543aa8e6c53242eacae5c87019886c
workflow-type: tm+mt
source-wordcount: '1305'
ht-degree: 0%

---

# [!DNL Microsoft Dynamics] Installatiehandleiding voor CRM {#microsoft-dynamics-crm-installation-guide}

>[!NOTE]
>
>Mogelijk ziet u instructies die &quot;[!DNL Marketo Measure]&quot; in onze documentatie, maar zie nog &quot;Bizible&quot;in uw CRM. We werken eraan dat dit wordt bijgewerkt en de herbranding wordt binnenkort weerspiegeld in uw CRM.

## Ondersteunde versies {#supported-versions}

[!DNL Marketo Measure] ondersteunt het volgende: [!DNL Microsoft Dynamics CRM] versies:

* [!DNL Microsoft Dynamics 2016] (Online en op locatie)
* [!DNL Microsoft Dynamics 365] (Online en op locatie)

Voor verbinding en verificatie [!DNL Marketo Measure] steunt de volgende Actieve Verbond van de Folder van de Diensten (ADFS) versies:

* ADFS 4.0 - [!DNL Windows Server 2016]
* ADFS 5.0 - [!DNL Windows Server 2019]

## De beheerde oplossing installeren {#install-the-managed-solution}

[Downloaden en installeren](assets/marketo-measure-dynamics-extension.zip) het ZIP-bestand in Dynamics CRM.

**[!UICONTROL Settings]** > **[!UICONTROL Customizations]** > **[!UICONTROL Solutions]** > **[!UICONTROL Import]** (knop) > **[!UICONTROL Choose File]**.

![](assets/1.png)

>[!NOTE]
>
>De volgende twee schermafbeeldingen kunnen enigszins van u variëren, aangezien zij tijdens een oplossingsverbetering werden genomen.

![](assets/2.png)

![](assets/3.png)

## [!DNL Marketo Measure] Gebruikersmachtigingen {#marketo-measure-user-permissions}

We raden u aan een speciale [!DNL Marketo Measure] Gebruiker binnen Dynamiek voor ons om gegevens uit te voeren en in te voeren door om het even welke kwesties met andere gebruikers in uw CRM te vermijden. Neem nota van de gebruikersbenaming en het wachtwoord evenals het eindpunt URL aangezien dit zal worden gebruikt wanneer het creëren van [!DNL Marketo Measure] account.

## Beveiligingsrollen {#security-roles}

Als uw organisatie de Rollen van de Veiligheid van de Dynamiek gebruikt, gelieve de verbonden gebruiker, of specifiek te controleren [!DNL Marketo Measure] De gebruiker heeft voldoende lees-/schrijfmachtigingen voor de vereiste entiteiten.

Beveiligingsrollen bevinden zich hier: **[!UICONTROL Settings]** > **[!UICONTROL Security]** > **[!UICONTROL Security Roles]**.

Voor [!DNL Marketo Measure] aangepaste entiteiten hebben we volledige machtigingen voor al onze entiteiten nodig.

>[!NOTE]
>
>De gebruikers die kansen zullen sluiten zullen ook de volledige toestemmingen nodig hebben.

![](assets/4.png)

Raadpleeg voor dynamische standaardinstellingen de [!DNL Marketo Measure] Dynamisch schema-document. Op hoog niveau [!DNL Marketo Measure] moet alleen in bepaalde entiteiten lezen om de juiste gegevens te verzamelen en naar aangepaste velden te schrijven die met de beheerde oplossing worden geïnstalleerd. We maken geen nieuwe standaardrecords en we werken ook geen standaardvelden bij.

## Aanraakpunten opnemen op pagina-indelingen: {#include-touchpoints-on-page-layouts}

1. Navigeer voor elke entiteit naar de formuliereditor. U vindt dit onder **[!UICONTROL Settings]** > **[!UICONTROL Customizations]** > **[!UICONTROL Customize the System]** > `[Entity]` > **[!UICONTROL Forms]**. Of u kunt het op de montages vinden terwijl u een verslag bekijkt.

   * De te configureren entiteiten: Account, Opportunity, Contact, Lead en Campagne.

   * Als u campagnes wilt configureren, moet u de optie Campagnesynchronisatie inschakelen in **[!UICONTROL CRM]** > **[!UICONTROL Campaigns]**.

   ![](assets/5.png)

1. Pagina-indelingen: Voeg eerst een &quot;[!UICONTROL One Column]&quot;Plaats de tegel in de sectie waar u de aanraakpunten wilt plaatsen. Binnen die nieuwe kolom moeten we een subraster toevoegen aan elk formulier binnen uw account-, opportunity-, contact- en leidende entiteiten.

   ![](assets/6.png)

   ![](assets/7.png)

1. Selecteer het object (Aanraakpunten voor koperkenmerken of Aanraakpunten voor koper) dat in het subraster moet worden weergegeven. Dit is afhankelijk van de objectrelatie. Wijzig desgewenst de kolommen die worden weergegeven door op de knop Bewerken te klikken. Een standaardlay-out is geplaatst door de beheerde oplossing.

   Aanraakpunt voor koperkenmerken subraster - Accounts, Opportunity en Contact\
   Subraster met aanraakpunten koper - Leads en contactpersonen

   ![](assets/8.png)

1. Wanneer u het formulier hebt bijgewerkt, publiceert u de wijzigingen en slaat u deze op.

## Schemagerelateerde overwegingen {#schema-related-considerations}

**Ontvangsten**

[!DNL Marketo Measure] verwijst standaard naar het veld Werkelijke ontvangsten. Als u dit niet gebruikt, gelieve te verklaren hoe u over opbrengst aan uw Ingenieur van Oplossingen of de Manager van het Succes als douanewerkschema zult melden nodig zijn.

**Datum sluiten**

[!DNL Marketo Measure] verwijst naar het veld Datum feitelijk sluiten buiten het vak. Als u dit niet gebruikt of ook het Geschatte Dichte gebied van de Datum gebruikt, gelieve uw proces aan uw Ingenieur van Oplossingen of de Manager van het Succes uit te leggen. Voor beide velden kan een aangepaste workflow nodig zijn.

## Adobe Admin Console en identiteitsprovider instellen {#set-up-your-adobe-admin-console-and-identity-provider}

De eerste stap naar [!DNL Marketo Measure] is om te maken en u aan te melden bij uw Adobe Admin Console waarvoor u een abonnement hebt. Neem contact op met uw [!DNL Marketo Measure] Accountvertegenwoordiger.

Als product binnen de Adobe Suite [!DNL Marketo Measure] Gebruikt de volledige functionaliteit van Adobe Admin Console for Identity Management. Meer bronnen zijn mogelijk [hier gevonden](https://helpx.adobe.com/nl/enterprise/using/admin-console.html).

We raden u aan alle bronnen, aanbevolen werkwijzen en beschikbare opties voor [Identity Management](https://helpx.adobe.com/enterprise/using/set-up-identity.html).

Voor hulp bij en een overzicht van het instellen van je Identity Management in de Adobe Admin Console, kun je contact opnemen met je [!DNL Marketo Measure] Accountvertegenwoordiger.

Om gebruikersverificatie en autorisatie met uw [!DNL Marketo Measure] -instantie(s), zijn de volgende stappen vereist in de Adobe Admin Console:

**Het instellen van de [!DNL Marketo Measure] Productkaart**

Als je de Adobe Admin Console opent, zie je je [!DNL Marketo Measure] Productvariant(en) in de sectie Overzicht.

![](assets/microsoft-dynamics-crm-installation-guide-8a.png)

Klik op de knop [!DNL Marketo Measure] De productkaart toont je al je [!DNL Marketo Measure] instantie(s). Standaard, elk [!DNL Marketo Measure] Instantie heeft een eigen profiel met het voorvoegsel &#39;[!DNL Marketo Measure]&quot;. Beheerders of gebruikers die aan dit profiel of een ander profiel in deze instantie zijn toegevoegd, kunnen zich aanmelden bij [!DNL Marketo Measure].

![](assets/microsoft-dynamics-crm-installation-guide-8b.png)

Er is geen actie vereist om een nieuw profiel te maken in het dialoogvenster [!DNL Marketo Measure] Product-exemplaar(s).

Beginnen met het toevoegen van gebruikers die toegang hebben tot [!DNL Marketo Measure], gelieve de [Toevoegen [!DNL Marketo Measure] Beheerders en [!DNL Marketo Measure] Gebruikers](#adding-marketo-measure-admins-and-marketo-measure-users) hieronder.

## Toevoegen [!DNL Marketo Measure] Beheerders en [!DNL Marketo Measure] Gebruikers {#adding-marketo-measure-admins-and-marketo-measure-users}

De volgende stap is het verlenen van toegang tot [!DNL Marketo Measure] door gebruikers toe te voegen. Dit kan in de beheers en gebruikersfolder van worden gedaan [!DNL Marketo Measure] productkaart.

| Gebruikerstype | Beschrijving |
|---|---|
| Admins | dit zijn beheerders en machtsgebruikers van [!DNL Marketo Measure] Toepassing met volledige mogelijkheid om bij te werken en te beheren [!DNL Marketo Measure]-specifieke configuratieopties |
| Gebruikers | dit zijn standaardgebruikers van de [!DNL Marketo Measure] Toepassing met alleen-lezen machtigingen binnen de [!DNL Marketo Measure] toepassing |

Wanneer u een gebruiker aan hun respectievelijke groep toevoegt, ziet u hun [Identiteitstype vermeld](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/set-up-identity.ug.html).

>[!NOTE]
>
>Om [!DNL Marketo Measure] beheerder (in [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}), moet een gebruiker als Gebruiker worden toegevoegd _en_ een beheerder voor [!DNL Marketo Measure] productprofiel in de [!DNL Marketo Measure] productkaart.

**Aanmelden bij[!DNL Marketo Measure]**

Nadat een gebruiker aan een Profiel van het Product is toegevoegd, kunnen zij tot hun toegang hebben [!DNL Marketo Measure] instantie(s) door de **Aanmelden met Adobe ID** optie bij [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}.

![](assets/microsoft-dynamics-crm-installation-guide-15.png)

## Verbindingen en gegevensproviders configureren {#configuring-your-connections-and-data-providers}

Nadat u zich bij hebt aangemeld [!DNL Marketo Measure] en zijn ingesteld als een gebruiker in de Adobe Admin Console, bestaat de volgende stap uit het instellen van verschillende gegevensverbindingen.

**CRM als gegevensaanbieder**

1. In uw [!DNL Marketo Measure] account, klik op **[!UICONTROL My Account]** vervolgkeuzelijst en selecteer **[!UICONTROL Settings]**.

   ![](assets/microsoft-dynamics-crm-installation-guide-16.png)

1. Onder [!UICONTROL Integrations] in de linkernav klikt u op **[!UICONTROL Connections]**.

   ![](assets/microsoft-dynamics-crm-installation-guide-17.png)

1. Klik op de knop **[!UICONTROL Set Up New CRM Connection]** knop.

   ![](assets/microsoft-dynamics-crm-installation-guide-18.png)

1. Volgende tot [!UICONTROL Microsoft Dynamics CRM]klikt u op de knop **[!UICONTROL Connect]** knop.

   ![](assets/microsoft-dynamics-crm-installation-guide-19.png)

1. Selecteren [!UICONTROL Credentials] of [!UICONTROL OAuth].

   ![](assets/microsoft-dynamics-crm-installation-guide-20.png)

   >[!NOTE]
   >
   >Ga voor meer informatie over OAuth naar [dit artikel](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/oauth-with-azure-active-directory-for-dynamics-crm.md). Neem contact op met uw [!DNL Marketo Measure] Accountvertegenwoordiger.

1. In dit voorbeeld hebben we Credentials gekozen. Voer uw gegevens in en klik op **[!UICONTROL Next]**.

Na het verbinden, zult u de details van uw verbinding van de Dynamica in de lijst van Verbindingen CRM/MAP zien.

**Advertentieverbindingen van account**

Je advertentiekeningen verbinden met [!DNL Marketo Measure], te beginnen door de [!UICONTROL Connections] binnen de [!DNL Marketo Measure] toepassing.

1. Volg stap 1 en 2 van het bovenstaande _CRM als gegevensaanbieder_ sectie.

1. Klik op de knop **[!UICONTROL Set up New CRM Connection]** knop.

   ![](assets/microsoft-dynamics-crm-installation-guide-21.png)

1. Selecteer het gewenste platform.

   ![](assets/microsoft-dynamics-crm-installation-guide-22.png)

**[!DNL Marketo Measure]Javascript**

Om [!DNL Marketo Measure] om uw Webactiviteiten te volgen, zijn er veelvoudige stappen voor opstelling.

1. Klik op de knop **[!UICONTROL My Account]** vervolgkeuzelijst en selecteer **[!UICONTROL Account Configuration]**.

   ![](assets/microsoft-dynamics-crm-installation-guide-23.png)

1. Voer uw telefoonnummer in. Voer bij Website het primaire hoofddomein in waarvoor u de [!DNL Marketo Measure] volgen op uw website. Klikken **[!UICONTROL Save]** wanneer gereed.

   ![](assets/microsoft-dynamics-crm-installation-guide-24.png)

   >[!NOTE]
   >
   >Neem contact op met uw [!DNL Marketo Measure] Accountvertegenwoordiger.

1. De [[!DNL Marketo Measure] JavaScript](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md) moet vervolgens over de gehele site en de landingspagina&#39;s worden geplaatst. Wij adviseren hardcoding het manuscript binnen het hoofd van uw landingspagina&#39;s of het toevoegen door een Systeem van Tag Management zoals [Google-tagbeheer](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-via-google-tag-manager.md).

   >[!NOTE]
   >
   >Standaard, [!DNL Marketo Measure] Hiermee exporteert u 200 records per API-credit telkens wanneer een taak gegevens naar uw CRM verzendt. Voor de meeste klanten biedt dit de optimale balans tussen API-credits die worden verbruikt door [!DNL Marketo Measure] en CPU-resourcevereisten voor de CRM. Voor klanten met complexe CRM-configuraties, zoals workflows en triggers, kan een kleinere batch-omvang echter nuttig zijn om de CRM-prestaties te verbeteren. Daartoe [!DNL Marketo Measure] staat klanten toe om de grootte van de de uitvoerpartij van CRM te vormen. Deze instelling is beschikbaar op de pagina Instellingen > CRM > Algemeen in het dialoogvenster [!DNL Marketo Measure] De webtoepassing en klanten kunnen kiezen uit batchgrootten 200 (standaard), 100, 50 of 25.
   >
   >Houd er bij het wijzigen van deze instelling rekening mee dat kleinere batchformaten meer API-credits van uw CRM verbruiken. Het is raadzaam om de partijgrootte te verminderen slechts als u Cpu ondervindt onderbreking of hoge lading van cpu in uw CRM.

   >[!NOTE]
   >
   >Als u het exporteren van gegevens naar Dynamics uitschakelt, worden er geen bestaande gegevens verwijderd. Neem contact op met de afdeling Dynamische ondersteuning voor hulp bij het verwijderen van bestaande gegevens.
