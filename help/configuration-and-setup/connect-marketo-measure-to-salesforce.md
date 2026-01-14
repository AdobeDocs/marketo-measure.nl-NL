---
description: Richtlijnen voor Marketo Measure-verbinding met Salesforce voor Marketo Measure-gebruikers
title: Marketo Measure verbinden met Salesforce
exl-id: 9be8d3fa-1045-4e41-bc2e-5b9d4d3513ae
feature: Salesforce
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 1%

---

# Marketo Measure verbinden met Salesforce {#connect-marketo-measure-to-salesforce}

Dit artikel biedt een overzicht van hoe u uw [!DNL Salesforce] -account kunt verbinden met uw [!DNL Marketo Measure] -account.

## Verbinding maken [!DNL Marketo Measure] met [!DNL Salesforce] {#connecting-marketo-measure-with-salesforce}

1. Gebruik een incognitobrowser om u aan te melden bij [!DNL Marketo Measure] .

1. Navigeer in de menubalk boven aan het scherm naar **[!UICONTROL My Account]** en klik op de optie **[!UICONTROL Settings]** .

1. Klik in de kolom met opties links in het scherm op **[!UICONTROL Connections]** onder de sectie [!UICONTROL Integrations] .

   ![1. In de kolom van het plaatsen van opties op de linkerzijde, klik ](assets/bizible-full-1.png)

1. Klik onder de sectie CRM in Verbindingen op **[!UICONTROL Set Up New CRM Connection]** .

   ![1. Onder de sectie van CRM in Verbindingen, klik Nieuwe Opstelling ](assets/bizible-taxonomy-1.png)

1. Er verschijnt een pop-upvenster waarin u wordt gevraagd een CRM-verbinding te selecteren. Klik op **[!UICONTROL Connect]** naast het logo van [!DNL Salesforce] .

   ![1. Er verschijnt een pop-upvenster waarin u wordt gevraagd een CRM-verbinding te selecteren. Klikken ](assets/connect-salesforce-1.png)

1. Er wordt een laatste pop-upvenster weergegeven met de vraag naar uw [!DNL Salesforce] -referenties, sandbox of productie. Voer uw gegevens in en klik op **[!UICONTROL Authorize]** om de account te verbinden met [!DNL Marketo Measure] .

>[!NOTE]
>
>[!DNL Marketo Measure] kan slechts met één [!DNL Salesforce] -instantie tegelijk worden verbonden.
>
>* Een [!DNL Marketo Measure] -instantie kan met een SFDC Sandbox-instantie worden verbonden om de integratie te testen voordat de verbinding naar uw SFDC Production-instantie wordt overgeschakeld.
>* Als u eerst test met een SFDC-sandbox, raden we u ten zeerste aan om één test uit te voeren die een exacte replica is van uw SFDC-productiefunctie in termen van velden op de objecten Lead, Contact, Account, Opportunity, Campagne en Case. Als u actieve APEX-triggers in productie hebt die worden geactiveerd bij updates van de objecten Lead, Contact, Account, Opportunity, Campagne en Case, moet u proberen deze actief te maken in uw sandbox.
>* Wanneer u klaar bent met testen, werkt u uw [!DNL Marketo Measure] -account bij zodat deze naar uw productie verwijst [!DNL Salesforce] (in plaats van Sandbox [!DNL Salesforce] ). Als een [!DNL Marketo Measure] -account eenmaal is verbonden met Production [!DNL Salesforce] , kunt u vanwege de manier waarop de integratie is gemaakt, niet achterwaarts gaan en verbinding maken met een Sandbox [!DNL Salesforce] -org.

## Gebruik van API-credits {#api-credits-usage}

Marketo Measure gebruikt een CRM-integratietaak om te communiceren met de Salesforce van een klant via een geïntegreerde gebruiker. Alle gegevensuitwisselingen via deze gebruiker gebruiken Salesforce API-credits. U hebt de mogelijkheid om een kredietquotum toe te wijzen aan een integratiegebruiker, die buitensporige API-aanroepen reguleert. Deze quota of limiet wordt elke 24 uur opnieuw ingesteld.

U kunt tot deze grens in Marketo Measure toegang hebben via: **Mijn Rekening** > **Montages** > **CRM** > **Algemeen** > **Dagelijkse grens van CRM API**, en kan het voor uw huurders vormen.

![ u kunt tot deze grens in Marketo Measure toegang hebben via: Mijn Montages van de Rekening ](assets/connect-salesforce-2.png)

### Limiet instellen voor API-credits {#setting-a-limit-for-api-credits}

1. Navigeer aan **Mijn Rekening** > **Montages**.

1. Onder CRM, klik **Algemeen**. U ziet de **Dagelijkse de grens van CRM API** optie.

1. Klik op het vergrendelingspictogram dat u wilt bewerken.

   ![1. Klik op het vergrendelingspictogram dat u wilt bewerken.](assets/connect-salesforce-3.png)

1. Voer een gewenste limiet in van 100.000 of hoger. Klik **sparen** wanneer gedaan.

   ![1. Voer een gewenste limiet in van 100.000 of hoger. Klikken ](assets/connect-salesforce-1.png)

>[!NOTE]
>
>Om beschikbare Salesforce API kredieten voor uw verbonden oplossing te verhogen, contacteer uw beheerder van Salesforce en verwijs [ dit document van Salesforce ](https://developer.salesforce.com/docs/atlas.en-us.salesforce_app_limits_cheatsheet.meta/salesforce_app_limits_cheatsheet/salesforce_app_limits_platform_api.htm){target="_blank"}.

>[!MORELIKETHIS]
>
>[ Meldingen van de Fout ](/help/configuration-and-setup/error-notifications.md){target="_blank"}
