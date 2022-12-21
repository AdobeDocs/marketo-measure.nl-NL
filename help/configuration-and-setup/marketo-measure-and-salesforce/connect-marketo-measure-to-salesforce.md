---
unique-page-id: 18874580
description: Marketo-maatregel verbinden met Salesforce - [!DNL Marketo Measure] - Productdocumentatie
title: Marketo-maatregel verbinden met Salesforce
exl-id: 9be8d3fa-1045-4e41-bc2e-5b9d4d3513ae
source-git-commit: 993a326c377b3b6ff48c4e0114b59297f9ca2ca6
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 0%

---

# Marketo-maatregel verbinden met Salesforce {#connect-marketo-measure-to-salesforce}

Dit artikel biedt een overzicht van hoe u verbinding kunt maken met uw [!DNL Salesforce] account aan uw [!DNL Marketo Measure] account.

## Verbinding maken [!DNL Marketo Measure] with [!DNL Salesforce] {#connecting-marketo-measure-with-salesforce}

1. Een incognitobrowser gebruiken om u aan te melden [!DNL Marketo Measure].

1. Navigeer in de menubalk boven aan het scherm naar **[!UICONTROL My Account]** en klik op de knop [!UICONTROL Settings] optie.

1. Klik in de kolom met opties links in het scherm op [!UICONTROL Connections] die zich onder [!UICONTROL Integrations] sectie.

   ![](assets/1.png)

1. Klik onder de sectie CRM in Verbindingen op **[!UICONTROL Set Up New CRM Connection]**.

   ![](assets/2.png)

1. Er verschijnt een pop-upvenster met de vraag of u de CRM-verbinding wilt selecteren. Klik op de knop [!UICONTROL Connect] naast de knop [!DNL Salesforce] logo.

   ![](assets/3.png)

1. Er wordt een laatste pop-upvenster weergegeven waarin u wordt gevraagd [!DNL Salesforce] referenties, sandbox of productie. Voer uw gegevens in en klik op **[!UICONTROL Authorize]** om verbinding te maken met de account [!DNL Marketo Measure].

>[!NOTE]
>
>[!DNL Marketo Measure] kan slechts met één worden verbonden [!DNL Salesforce] -instantie tegelijk.
>
>* A [!DNL Marketo Measure] -instantie kan worden aangesloten op een SFDC-sandbox-instantie om de integratie te testen voordat de verbinding naar uw SFDC Production-instantie wordt geschakeld.
>* Als u eerst met een zandbak SFDC test, adviseren wij hoogst u met één te testen die een nauwkeurige replica van uw productieInstantie van SFDC in termen van gebieden op Lead, Contact, Rekening, Opportunity, Campagne en HoofdObjecten is. Als u actieve APEX-triggers in productie hebt die worden geactiveerd bij updates van de objecten Lead, Contact, Account, Opportunity, Campagne en Case, moet u proberen deze actief te maken in uw sandbox.
>* Als u klaar bent met testen, werkt u uw [!DNL Marketo Measure] account voor aanwijzen bij productie [!DNL Salesforce] (in plaats van Sandbox [!DNL Salesforce]). Als gevolg van de manier waarop de integratie werd opgebouwd, [!DNL Marketo Measure] account is verbonden met productie [!DNL Salesforce]kunt u niet achterwaarts gaan en verbinding maken met een sandbox [!DNL Salesforce] org.


