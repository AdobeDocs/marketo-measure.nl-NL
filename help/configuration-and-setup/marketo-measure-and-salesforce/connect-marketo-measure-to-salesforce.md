---
unique-page-id: 18874580
description: Marketo Measure verbinden met Salesforce - [!DNL Marketo Measure]
title: Marketo Measure verbinden met Salesforce
exl-id: 9be8d3fa-1045-4e41-bc2e-5b9d4d3513ae
feature: Salesforce
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 0%

---

# Marketo Measure verbinden met Salesforce {#connect-marketo-measure-to-salesforce}

Dit artikel biedt een overzicht van hoe u verbinding kunt maken met uw [!DNL Salesforce] account aan uw [!DNL Marketo Measure] account.

## Verbinding maken [!DNL Marketo Measure] with [!DNL Salesforce] {#connecting-marketo-measure-with-salesforce}

1. Een incognitobrowser gebruiken om u aan te melden [!DNL Marketo Measure].

1. Navigeer in de menubalk boven aan het scherm naar **[!UICONTROL My Account]** en klik op de knop **[!UICONTROL Settings]** -optie.

1. Klik in de kolom met opties links in het scherm op **[!UICONTROL Connections]** die zich onder [!UICONTROL Integrations] sectie.

   ![](assets/connect-marketo-measure-to-salesforce-1.png)

1. Klik onder de sectie CRM in Verbindingen op **[!UICONTROL Set Up New CRM Connection]**.

   ![](assets/connect-marketo-measure-to-salesforce-2.png)

1. Er verschijnt een pop-upvenster waarin u wordt gevraagd een CRM-verbinding te selecteren. Klikken **[!UICONTROL Connect]** naast de [!DNL Salesforce] logo.

   ![](assets/connect-marketo-measure-to-salesforce-3.png)

1. Er verschijnt een laatste pop-upvenster waarin u wordt gevraagd [!DNL Salesforce] referenties, sandbox of productie. Voer uw gegevens in en klik op **[!UICONTROL Authorize]** om verbinding te maken met de account [!DNL Marketo Measure].

>[!NOTE]
>
>[!DNL Marketo Measure] kan slechts met één worden verbonden [!DNL Salesforce] -instantie tegelijk.
>
>* A [!DNL Marketo Measure] -instantie kan worden aangesloten op een SFDC-sandbox-instantie om de integratie te testen voordat de verbinding naar uw SFDC Production-instantie wordt geschakeld.
>* Als u eerst met een zandbak SFDC test, adviseren wij hoogst u met één te testen die een nauwkeurige replica van uw productieInstantie van SFDC in termen van gebieden op de Lood, het Contact, de Rekening, de Kans, de Campagne, en de voorwerpen van het Geval is. Als u actieve APEX-triggers in productie hebt die worden geactiveerd bij updates van de objecten Lead, Contact, Account, Opportunity, Campagne en Case, moet u proberen deze actief te maken in uw sandbox.
>* Wanneer u klaar bent met testen, werkt u uw [!DNL Marketo Measure] account voor aanwijzen bij productie [!DNL Salesforce] (in plaats van Sandbox [!DNL Salesforce]). Als gevolg van de manier waarop de integratie werd opgebouwd, [!DNL Marketo Measure] account is verbonden met productie [!DNL Salesforce]kunt u niet achterwaarts gaan en verbinding maken met een sandbox [!DNL Salesforce] org.

## Gebruik van API-credits {#api-credits-usage}

Marketo Measure gebruikt een integratietaak van CRM om met Salesforce van een cliënt door een Geïntegreerde Gebruiker om te zetten. Alle gegevensuitwisselingen via deze gebruiker maken gebruik van Salesforce API-credits. U hebt de mogelijkheid om een kredietquotum toe te wijzen aan een integratiegebruiker, die buitensporige API-aanroepen reguleert. Deze quota of limiet wordt elke 24 uur opnieuw ingesteld.

U kunt deze limiet in Marketo Measure openen via: **Mijn account** > **Instellingen** > **CRM** > **Algemeen** > **Limiet voor dagelijkse CRM-API** en kan het voor uw huurders configureren.

![](assets/connect-marketo-measure-to-salesforce-4.png)

### Limiet instellen voor API-credits {#setting-a-limit-for-api-credits}

1. Navigeren naar **Mijn account** > **Instellingen**.

1. Klik onder CRM op **Algemeen**. U ziet de **Limiet voor dagelijkse CRM-API** -optie.

1. Klik op het vergrendelingspictogram dat u wilt bewerken.

   ![](assets/connect-marketo-measure-to-salesforce-5.png)

1. Voer een gewenste limiet in van 100.000 of hoger. Klikken **Opslaan** wanneer gereed.

   ![](assets/connect-marketo-measure-to-salesforce-6.png)

>[!NOTE]
>
>Neem contact op met uw Salesforce-beheerder en neem contact op met uw Salesforce-beheerder om de beschikbare Salesforce API-credits voor de aangesloten oplossing te verhogen [dit Salesforce-document](https://developer.salesforce.com/docs/atlas.en-us.salesforce_app_limits_cheatsheet.meta/salesforce_app_limits_cheatsheet/salesforce_app_limits_platform_api.htm){target="_blank"}.

>[!MORELIKETHIS]
>
>[Foutmeldingen](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"}
