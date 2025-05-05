---
unique-page-id: 18874793
description: Gebruikend een Gebied van de Bedrag van de Opbrengst van de Douane -  [!DNL Marketo Measure]
title: Een veld Aangepaste omzettingsbedrag gebruiken
exl-id: 517ea4f9-aa83-48d0-8ce7-003f4a907430
feature: Custom Revenue Amount
source-git-commit: 03342bde87b75ab702eea4c63b581479a7e303c1
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 0%

---

# Een veld Aangepaste omzettingsbedrag gebruiken {#using-a-custom-revenue-amount-field}

Standaard halen Aanraakpunten voor koperkenmerk de opportunity Amount uit een van de volgende twee velden:

* Bedrag (standaard SFDC)
* [!DNL Marketo Measure] Hoeveelheid opportunity (aangepast)

Als u een gebied van het Bedrag van de douane op uw Kansen gebruikt, zullen wij een werkschema moeten vormen om de Opbrengst van Buyer Touchpoint te berekenen. Hiervoor is wat meer geavanceerde kennis van [!DNL Salesforce] vereist, zodat u mogelijk hulp nodig hebt van uw SFDC-beheerder.

Om te beginnen hebben we de volgende informatie nodig:

* API Naam van uw veld Bedrag

Vanaf hier beginnen we de workflow te maken.

## De workflow maken in Salesforce Lightning {#create-the-workflow-in-salesforce-lightning}

De volgende stappen zijn bedoeld voor gebruikers van Salesforce Lightning. Als u nog Salesforce Klassiek gebruikt, zijn die stappen [ hieronder vermeld ](#create-the-workflow-in-salesforce-classic).

1. Typ in Setup &quot;Stroom&quot; in het vak Snel zoeken en selecteer **[!UICONTROL Flows]** om de Flow Builder te starten. Klik in het rechterdeelvenster op de knop **[!UICONTROL New Flow]** .

   ![](assets/using-a-custom-revenue-amount-field-1.png)

1. Selecteer **[!UICONTROL Record-Triggered Flow]** en klik op **[!UICONTROL Create]** rechtsonder.

   ![](assets/using-a-custom-revenue-amount-field-2.png)

1. Selecteer het object Opportunity in het venster Start configureren. Selecteer in de sectie [!UICONTROL Configure Trigger] de optie **[!UICONTROL A record is created or updated]** .

   ![](assets/using-a-custom-revenue-amount-field-3.png)

1. Selecteer **[!UICONTROL Custom Condition Logic Is Met]** onder [!UICONTROL Condition Requirements] in het gedeelte Invoervoorwaarden instellen.
   * Selecteer in het zoekveld het veld Aangepast bedrag.
   * Plaats de exploitant aangezien **Null** is, en de waarde als **[!UICONTROL False]**.
   * Stel de evaluatiecriteria in op **[!UICONTROL Every time a record is updated and meets the condition requirements]** .

   ![](assets/using-a-custom-revenue-amount-field-4.png)

1. Selecteer onder de sectie &quot;De stroom optimaliseren voor&quot; de optie **[!UICONTROL Fast Field Updates]** . Klik op **[!UICONTROL Done]** rechtsonder.

   ![](assets/using-a-custom-revenue-amount-field-5.png)

1. Als u het element wilt toevoegen, klikt u op de plusknop (+) en selecteert u **[!UICONTROL Update Triggering Record]** .

   ![](assets/using-a-custom-revenue-amount-field-6.png)

1. Voer het volgende in het venster Nieuwe updateverslagen in:

   * Voer een label in. De API-naam wordt automatisch gegenereerd
   * Onder &quot;Hoe te om Verslagen te vinden om bij te werken en hun waarden te plaatsen,&quot;uitgezocht **[!UICONTROL Use the opportunity record that triggered the flow]**.
   * Selecteer in de sectie &quot;[!UICONTROL Set Filter Conditions]&quot; **[!UICONTROL Always Update Record]** als voorwaarde voor het bijwerken van een record.
   * In &quot;[!UICONTROL Set Field Values for the Campaign Record],&quot;van gebied, selecteer het Bedrag van de Kans van Marketo Measure (**bizible2_Bizible_Opportunity_Amount__c**) en van waarde. Selecteer vervolgens het veld Aangepast bedrag.
   * Klik op **[!UICONTROL Done]**.

   ![](assets/using-a-custom-revenue-amount-field-7.png)

1. Klik op **[!UICONTROL Save]**. Er wordt een pop-up weergegeven. Typ &quot;Flow Label&quot; in het venster Save the Flow (de naam van de Flow-API wordt automatisch gegenereerd). Klik nogmaals op **[!UICONTROL Save]** .

   ![](assets/using-a-custom-revenue-amount-field-8.png)

1. Klik op de knop **[!UICONTROL Activate]** om de flow te activeren.

   ![](assets/using-a-custom-revenue-amount-field-9.png)

## De workflow maken in Salesforce Classic {#create-the-workflow-in-salesforce-classic}

De volgende stappen gelden voor Salesforce Classic-gebruikers. Als u de schakelaar aan de Bliksem van Salesforce hebt gemaakt, kunnen die stappen [ hierboven ](#create-the-workflow-in-salesforce-lightning) worden gevonden.

1. Navigeer naar **[!UICONTROL Setup]** > **[!UICONTROL Create]** > **[!UICONTROL Workflow & Approvals]** > **[!UICONTROL Workflow Rules]** .

   ![](assets/using-a-custom-revenue-amount-field-10.png)

1. Selecteer **[!UICONTROL New Rule]**, stel het object in als &#39;Opportunity&#39; en klik op **[!UICONTROL Next]** .

   ![](assets/using-a-custom-revenue-amount-field-11.png)

   ![](assets/using-a-custom-revenue-amount-field-12.png)

1. Configureer de workflow. Stel de naam van de regel in op &quot;Aantal kansen bijwerken [!DNL Marketo Measure]&quot;. Stel de evaluatiecriteria in op &quot;Gemaakt en telkens wanneer het wordt bewerkt.&quot; Selecteer bij Regelcriteria het veld Aangepast bedrag en selecteer Operator [!UICONTROL as "Not Equal To"] en laat het veld Waarde leeg.

   ![](assets/using-a-custom-revenue-amount-field-13.png)

1. Voeg een workflowactie toe. Plaats deze picklist aan &quot;[!UICONTROL New Field Update]&quot;.
   ![](assets/using-a-custom-revenue-amount-field-14.png)

1. Hier kunt u veldgegevens invullen. Op het gebied van de &quot;Naam&quot;, adviseren wij gebruikend dit noemend: &quot;[!DNL Marketo Measure] het Bedrag van Opp.&quot; De &quot;Unieke Naam&quot; wordt automatisch ingevuld op basis van het veld &quot;Naam&quot;. Selecteer in de keuzelijst &quot;Bij te werken veld&quot; de optie &quot;[!DNL Marketo Measure] Hoeveelheid opportuniteit&quot;. Nadat u het veld hebt geselecteerd, selecteert u het vak &quot;Workflowregels opnieuw toepassen na wijziging van veld&quot;. Selecteer in het vak &quot;Nieuwe veldwaarde opgeven&quot; de optie &quot;Een formule gebruiken om de nieuwe waarde in te stellen.&quot; Laat in het lege vak de API-naam van het veld Aangepast bedrag vallen. Klik op **[!UICONTROL Save]**.

   ![](assets/using-a-custom-revenue-amount-field-15.png)

1. u wordt teruggebracht naar een roll-up pagina voor uw werkschema, zeker ben om &quot;te activeren&quot;en u zult goed zijn te gaan. Klik op **[!UICONTROL Edit]** naast de nieuwe workflow en klik vervolgens op **[!UICONTROL Activate]** om deze te activeren.

   Nadat u deze stappen hebt uitgevoerd, moeten de kansen worden bijgewerkt om de workflow te activeren en de nieuwe waarde uit het veld [!UICONTROL custom opportunity] te laten ophalen.

   Dit kan door uw kansen door de Lader van Gegevens in SFDC in werking te stellen worden verwezenlijkt. Vind details bij het gebruiken van de Lader van Gegevens in [ dit artikel ](/help/advanced-marketo-measure-features/custom-revenue-amount/using-data-loader-to-update-marketo-measure-custom-amount-field.md){target="_blank"}.

Als er om het even welke vragen langs de manier zijn, aarzel niet om uit te reiken aan het Team van de Rekening van de Adobe (uw Manager van de Rekening) of [[!DNL Marketo]  Steun ](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} .
