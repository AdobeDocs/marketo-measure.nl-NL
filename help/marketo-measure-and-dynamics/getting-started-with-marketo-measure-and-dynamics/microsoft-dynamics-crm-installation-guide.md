---
unique-page-id: 18874763
description: '[!DNL Microsoft Dynamics] Installatiehandleiding voor CRM - Marketo Measure - Productdocumentatie'
title: '[!DNL Microsoft Dynamics] Installatiehandleiding voor CRM'
exl-id: bc422c98-60bb-49ea-9bd1-c4149ae628b1
feature: Installation, Microsoft Dynamics
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 0%

---

# [!DNL Microsoft Dynamics] Installatiehandleiding voor CRM {#microsoft-dynamics-crm-installation-guide}

>[!NOTE]
>
>U kunt instructies zien die &quot;[!DNL Marketo Measure]&quot;in de documentatie specificeren, maar nog zie &quot;Bizible&quot;in uw CRM. We werken eraan dat dit wordt bijgewerkt en de herbranding wordt binnenkort weerspiegeld in uw CRM.

## Ondersteunde versies {#supported-versions}

[!DNL Marketo Measure] ondersteunt de volgende [!DNL Microsoft Dynamics CRM] -versies:

* [!DNL Microsoft Dynamics 2016] (Online en op locatie)
* [!DNL Microsoft Dynamics 365] (Online en op locatie)

Voor verbinding en authentificatie, steunt [!DNL Marketo Measure] de volgende Actieve Versies van de Diensten van de Folder Federated (ADFS):

* ADFS 4.0 - [!DNL Windows Server 2016]
* ADFS 5.0 - [!DNL Windows Server 2019]

## De beheerde oplossing installeren {#install-the-managed-solution}

[&#x200B; Download en installeer &#x200B;](assets/marketo-measure-dynamics-extension.zip) het zip dossier binnen Dynamica CRM.

**[!UICONTROL Settings]** > **[!UICONTROL Customizations]** > **[!UICONTROL Solutions]** > **[!UICONTROL Import]** (knop) > **[!UICONTROL Choose File]** .

![](assets/1.png)

>[!NOTE]
>
>De volgende twee schermafbeeldingen kunnen van u lichtjes variëren, aangezien zij tijdens een oplossingsverbetering werden genomen.

![](assets/2.png)

![](assets/3.png)

## Een [!DNL Marketo Measure] gebruiker maken {#creating-a-marketo-measure-user}

Het wordt aanbevolen een speciale Marketo Measure-gebruiker als een &#39;Application User&#39; in Dynamics te maken om gegevens te exporteren en te importeren, zodat problemen met andere gebruikers in uw CRM worden voorkomen. Let op de gebruikersnaam en het wachtwoord en de URL van het eindpunt, zoals deze worden gebruikt bij het maken van de [!DNL Marketo Measure] -account.

## Beveiligingsrollen {#security-roles}

Als uw organisatie de Rollen van de Veiligheid van de Dynamiek gebruikt, zorg ervoor de verbonden gebruiker, of de specifieke [!DNL Marketo Measure] Gebruiker voldoende lees-schrijf toestemmingen aan de vereiste entiteiten heeft.

Beveiligingsrollen bevinden zich hier: **[!UICONTROL Settings]** > **[!UICONTROL Security]** > **[!UICONTROL Security Roles]** .

Voor [!DNL Marketo Measure] aangepaste entiteiten hebben we volledige machtigingen voor al onze entiteiten nodig.

Campagne &quot;Maken&quot;-machtigingen zijn ook vereist, naast de lees- en schrijfmachtigingen voor standaardentiteiten.

>[!NOTE]
>
>De gebruikers die kansen sluiten hebben ook de volledige toestemming nodig.

![](assets/4.png)

Raadpleeg het document over het dynamicaschema van [!DNL Marketo Measure] voor dynamische standaardeenheden. Op hoog niveau leest [!DNL Marketo Measure] in bepaalde entiteiten om de juiste gegevens te verzamelen en naar aangepaste velden te schrijven die met de beheerde oplossing zijn geïnstalleerd. Er worden geen standaardrecords gemaakt en standaardvelden worden niet bijgewerkt.

## Aanraakpunten opnemen op pagina-indelingen: {#include-touchpoints-on-page-layouts}

1. Navigeer voor elke entiteit naar de formuliereditor. U vindt dit onder **[!UICONTROL Settings]** > **[!UICONTROL Customizations]** > **[!UICONTROL Customize the System]** > `[Entity]` > **[!UICONTROL Forms]** . U kunt de record ook op de instellingen vinden terwijl u een record bekijkt.

   * De te configureren entiteiten: Account, Opportunity, Contact, Lead en Campagne.

   * Als u campagnes wilt configureren, moet u de optie Campagnesynchronisatie inschakelen in **[!UICONTROL CRM]** > **[!UICONTROL Campaigns]** .

   ![](assets/5.png)

1. Pagina-indelingen: voeg eerst een tegel &quot;[!UICONTROL One Column]&quot; toe in de sectie die u wilt gebruiken voor de aanraakpunten. Binnen die nieuwe kolom moeten we een subraster toevoegen aan elk formulier binnen uw account-, opportunity-, contact- en leidende entiteiten.

   ![](assets/6.png)

   ![](assets/7.png)

1. Selecteer het object (Aanraakpunten voor koperkenmerken of Aanraakpunten voor koper) dat in het subraster moet worden weergegeven. Dit is afhankelijk van de objectrelatie. Wijzig desgewenst de kolommen die worden weergegeven door op de knop Bewerken te klikken. De standaardlay-out wordt geplaatst door de beheerde oplossing.

   Buyer Attribution Touchpoint Subgrid - Accounts, Opportunity, and Contact\
   Buyer Touchpoint Subgrid - Leads en contactpersonen

   ![](assets/8.png)

1. Wanneer u het formulier hebt bijgewerkt, publiceert u de wijzigingen en slaat u deze op.

## Schemagerelateerde overwegingen {#schema-related-considerations}

**Ontvangsten**

[!DNL Marketo Measure] verwijst standaard naar het veld Werkelijke ontvangsten. Als u dit niet gebruikt, verklaar hoe u over opbrengst aan uw Ingenieur van Oplossingen of de Manager van het Succes als douanewerkschema zult worden gemeld nodig.

**Sluiten Datum**

[!DNL Marketo Measure] verwijst naar het veld Datum feitelijk sluiten buiten het vak. Als u dit niet gebruikt of ook het Geschatte Dichte gebied van de Datum gebruikt, verklaar uw proces aan uw Ingenieur van Oplossingen of de Manager van het Succes. Mogelijk is een aangepaste workflow nodig om voor beide velden rekening te houden.

## Verbindingen en gegevensproviders configureren {#configuring-your-connections-and-data-providers}

Nadat u zich hebt aangemeld bij de [!DNL Marketo Measure] -toepassing en u bent ingesteld als een gebruiker in de Adobe Admin Console, bestaat de volgende stap uit het instellen van de verschillende gegevensverbindingen.

**CRM als Leverancier van Gegevens**

1. Klik in uw [!DNL Marketo Measure] -account op de vervolgkeuzelijst **[!UICONTROL My Account]** en selecteer **[!UICONTROL Settings]** .

   ![](assets/microsoft-dynamics-crm-installation-guide-16.png)

1. Klik onder [!UICONTROL Integrations] in de linkernav op **[!UICONTROL Connections]** .

   ![](assets/microsoft-dynamics-crm-installation-guide-17.png)

1. Klik op **[!UICONTROL Set Up New CRM Connection]** .

   ![](assets/microsoft-dynamics-crm-installation-guide-18.png)

1. Klik op de knop [!UICONTROL Microsoft Dynamics CRM] naast **[!UICONTROL Connect]** .

   ![](assets/microsoft-dynamics-crm-installation-guide-19.png)

1. Selecteer [!UICONTROL Credentials] of [!UICONTROL OAuth] .

   ![](assets/microsoft-dynamics-crm-installation-guide-20.png)

   >[!NOTE]
   >
   >Voor meer informatie over OAuth, bezoek [&#x200B; dit artikel &#x200B;](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/oauth-with-azure-active-directory-for-dynamics-crm.md). Neem contact op met uw [!DNL Marketo Measure] accountvertegenwoordiger als u vragen hebt over het proces.

1. In dit voorbeeld hebben we Credentials gekozen. Voer uw referenties in en klik op **[!UICONTROL Next]** .

Na het verbinden, zult u de details van uw verbinding van de Dynamica in de lijst van Verbindingen CRM/MAP zien.

**Add de Verbindingen van de Rekening**

Als u een verbinding wilt maken met Advertentierekeningen met [!DNL Marketo Measure] , begint u door het tabblad [!UICONTROL Connections] in de [!DNL Marketo Measure] -toepassing te bezoeken.

1. Volg Stappen 1 &amp; 2 van hierboven _CRM als a sectie van de Leverancier van Gegevens_.

1. Klik op **[!UICONTROL Set up New CRM Connection]** .

   ![](assets/microsoft-dynamics-crm-installation-guide-21.png)

1. Selecteer het gewenste platform.

   ![](assets/microsoft-dynamics-crm-installation-guide-22.png)

**[!DNL Marketo Measure]JavaScript**

[!DNL Marketo Measure] kan uw webactiviteiten volgen door meerdere stappen in te stellen.

1. Klik op de vervolgkeuzelijst **[!UICONTROL My Account]** en selecteer **[!UICONTROL Account Configuration]** .

   ![](assets/microsoft-dynamics-crm-installation-guide-23.png)

1. Voer uw telefoonnummer in. Voer bij Website het primaire hoofddomein in dat wordt gebruikt voor [!DNL Marketo Measure] tracking op uw website. Klik op **[!UICONTROL Save]** als u klaar bent.

   ![](assets/microsoft-dynamics-crm-installation-guide-24.png)

   >[!NOTE]
   >
   >Neem contact op met uw [!DNL Marketo Measure] accountvertegenwoordiger als u meerdere hoofddomeinen wilt toevoegen.

1. [[!DNL Marketo Measure]  JavaScript &#x200B;](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script.md) dan moet over de volledige plaats en landende pagina&#39;s worden geplaatst. Wij adviseren hardcoding het manuscript binnen het hoofd van uw landende pagina&#39;s of het toevoegen door een Systeem van Tag Management zoals [&#x200B; de Manager van de Markering van Google &#x200B;](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-via-google-tag-manager.md).

   >[!NOTE]
   >
   >Standaard exporteert [!DNL Marketo Measure] 200 records per API-credit telkens wanneer een taak gegevens naar uw CRM verzendt. Voor de meeste klanten biedt dit de optimale balans tussen API-credits die door [!DNL Marketo Measure] worden verbruikt en CPU-bronvereisten voor de CRM. Voor klanten met complexe CRM-configuraties, zoals workflows en triggers, kan een kleinere batch-omvang echter nuttig zijn om de CRM-prestaties te verbeteren. Met het oog hierop kunnen klanten in [!DNL Marketo Measure] de grootte van de CRM-exportbatch configureren. Deze instelling is beschikbaar op de pagina Instellingen > CRM > Algemeen in de [!DNL Marketo Measure] -webtoepassing. Klanten kunnen kiezen uit batchgrootten 200 (standaard), 100, 50 of 25.
   >
   >Houd er bij het wijzigen van deze instelling rekening mee dat kleinere batchformaten meer API-credits van uw CRM verbruiken. Het wordt aangeraden de batch alleen te verkleinen als u een CPU-time-out of een hoge CPU-belasting in uw CRM-systeem hebt.

   >[!NOTE]
   >
   >Wanneer u het exporteren van gegevens naar Dynamics uitschakelt, worden bestaande gegevens niet verwijderd. Voor hulp bij het verwijderen van bestaande gegevens, contacteer de Steun van de Dynamiek.

   >[!MORELIKETHIS]
   >
   >[&#x200B; Meldingen van de Fout &#x200B;](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"}
