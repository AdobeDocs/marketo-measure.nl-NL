---
unique-page-id: 18874793
description: Met een veld Aangepaste inkomstenbedrag - [!DNL Marketo Measure] - Productdocumentatie
title: Een veld Aangepaste omzettingsbedrag gebruiken
exl-id: 517ea4f9-aa83-48d0-8ce7-003f4a907430
feature: Custom Revenue Amount
source-git-commit: 560ca558ae9ef4d2ef4da57eb9bfa672ed00e0fc
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 0%

---

# Een veld Aangepaste omzettingsbedrag gebruiken {#using-a-custom-revenue-amount-field}

Standaard halen Aanraakpunten voor koperkenmerk de opportunity Amount uit een van de volgende twee velden:

* Bedrag (standaard SFDC)
* [!DNL Marketo Measure] Opportuniteitsbedrag (aangepast)

Als u een gebied van het Bedrag van de douane op uw Kansen gebruikt, zullen wij een werkschema moeten vormen om de Ontvangsten van het Aanraakpunt van de Koper te berekenen. Hiervoor is meer kennis van [!DNL Salesforce], kan dit dus hulp vereisen van uw SFDC-beheerder.

Om te beginnen hebben we de volgende informatie nodig:

* API Naam van uw veld Bedrag

Vanaf hier beginnen we de workflow te maken.

## De workflow maken in Salesforce Lightning {#create-the-workflow-in-salesforce-lightning}

De volgende stappen gelden voor gebruikers van Salesforce Lightning. Als u Salesforce Classic nog steeds gebruikt, worden deze stappen [worden hieronder vermeld](#create-the-workflow-in-salesforce-classic).

1. Typ in Setup &quot;Stroom&quot; in het vak Snel zoeken en selecteer **[!UICONTROL Flows]** om Flow Builder te starten. Klik in het rechterdeelvenster op **[!UICONTROL New Flow]** knop.

   ![](assets/using-a-custom-revenue-amount-field-1.png)

1. Selecteren **[!UICONTROL Record-Triggered Flow]** en klik op **[!UICONTROL Create]** rechtsonder.

   ![](assets/using-a-custom-revenue-amount-field-2.png)

1. Selecteer het object Opportunity in het venster Start configureren. Van de [!UICONTROL Configure Trigger] sectie, selecteert u **[!UICONTROL A record is created or updated]**.

   ![](assets/using-a-custom-revenue-amount-field-3.png)

1. In het gedeelte Invoervoorwaarden instellen, onder [!UICONTROL Condition Requirements], selecteert u **[!UICONTROL Custom Condition Logic Is Met]**.
   * Selecteer in het zoekveld het veld Aangepast bedrag.
   * De operator instellen als **Is null** en de waarde als **[!UICONTROL False]**.
   * De evaluatiecriteria instellen op **[!UICONTROL Every time a record is updated and meets the condition requirements]**.

   ![](assets/using-a-custom-revenue-amount-field-4.png)

1. Selecteer onder de sectie &quot;De stroom optimaliseren voor&quot; de optie **[!UICONTROL Fast Field Updates]**. Klikken **[!UICONTROL Done]** rechtsonder.

   ![](assets/using-a-custom-revenue-amount-field-5.png)

1. Als u het element wilt toevoegen, klikt u op de plusknop (+) en selecteert u **[!UICONTROL Update Triggering Record]**.

   ![](assets/using-a-custom-revenue-amount-field-6.png)

1. Voer het volgende in het venster Nieuwe updateverslagen in:

   * Voer een label in. De API-naam wordt automatisch gegenereerd
   * Onder &quot;Hoe te om Verslagen te vinden om bij te werken en hun Waarden te plaatsen,&quot;uitgezocht **[!UICONTROL Use the opportunity record that triggered the flow]**.
   * In het veld &quot;[!UICONTROL Set Filter Conditions]&quot;, selecteert u **[!UICONTROL Always Update Record]** als voorwaarde voor het bijwerken van een record.
   * In &quot;[!UICONTROL Set Field Values for the Campaign Record],&quot; in het veld selecteert u het bedrag en de waarde voor Marketo Measure Opportunity. Selecteer vervolgens het veld Aangepast bedrag.
   * Klik op **[!UICONTROL Done]**.

   ![](assets/using-a-custom-revenue-amount-field-7.png)

1. Klik op **[!UICONTROL Save]**. Er wordt een pop-up weergegeven. Typ &quot;Flow Label&quot; in het venster Save the Flow (de naam van de Flow-API wordt automatisch gegenereerd). Klikken **[!UICONTROL Save]** opnieuw.

   ![](assets/using-a-custom-revenue-amount-field-8.png)

1. Klik op de knop **[!UICONTROL Activate]** om de flow te activeren.

   ![](assets/using-a-custom-revenue-amount-field-9.png)

## De workflow maken in Salesforce Classic {#create-the-workflow-in-salesforce-classic}

De volgende stappen gelden voor gebruikers van Salesforce Classic. Als u op Salesforce Lightning hebt overgegaan, die stappen [kan hierboven worden gevonden](#create-the-workflow-in-salesforce-lightning).

1. Ga naar **[!UICONTROL Setup]** > **[!UICONTROL Create]** > **[!UICONTROL Workflow & Approvals]** > **[!UICONTROL Workflow Rules]**.

   ![](assets/using-a-custom-revenue-amount-field-10.png)

1. Selecteren **[!UICONTROL New Rule]**, stelt u het object in als &quot;Opportunity&quot; en klikt u op **[!UICONTROL Next]**.

   ![](assets/using-a-custom-revenue-amount-field-11.png)

   ![](assets/using-a-custom-revenue-amount-field-12.png)

1. Configureer de workflow. De regelnaam instellen als &quot;Bijwerken&quot; [!DNL Marketo Measure] Opportuniteitsbedrag.&quot; Stel de evaluatiecriteria in op &quot;Gemaakt en telkens wanneer het wordt bewerkt.&quot; Voor de Criteria van de Regel, selecteer uw gebied van het Bedrag van de Douane en selecteer de Exploitant [!UICONTROL as "Not Equal To"] en laat het veld Waarde leeg.

   ![](assets/using-a-custom-revenue-amount-field-13.png)

1. Voeg een workflowactie toe. Deze keuzelijst instellen op &quot;[!UICONTROL New Field Update].&quot;
   ![](assets/using-a-custom-revenue-amount-field-14.png)

1. Hier kunt u veldgegevens invullen. In het veld Naam raden we u aan deze naam te gebruiken: &quot;[!DNL Marketo Measure] Hoeveelheid opp.&quot; De &quot;Unieke Naam&quot; wordt automatisch ingevuld op basis van het veld &quot;Naam&quot;. Selecteer in de keuzelijst &quot;Veld bijwerken&quot; de optie &quot;[!DNL Marketo Measure] Opportuniteitsbedrag.&quot; Nadat u het veld hebt geselecteerd, selecteert u het vak &quot;Workflowregels opnieuw toepassen na wijziging van veld&quot;. Selecteer in het vak &quot;Nieuwe veldwaarde opgeven&quot; de optie &quot;Een formule gebruiken om de nieuwe waarde in te stellen.&quot; Laat in het lege vak de API-naam van het veld Aangepast bedrag vallen. Klik op **[!UICONTROL Save]**.

   ![](assets/using-a-custom-revenue-amount-field-15.png)

1. U wordt teruggebracht naar een roll-up pagina voor uw werkschema, zeker om &quot;te activeren&quot;en u zult goed zijn om te gaan. Klik op **[!UICONTROL Edit]** naast uw nieuwe workflow en klik vervolgens op **[!UICONTROL Activate]**.

   Zodra u deze stappen hebt voltooid, zullen de kansen moeten worden bijgewerkt om het werkschema teweeg te brengen om de nieuwe waarde van te hebben [!UICONTROL custom opportunity] veld.

   Dit kan worden verwezenlijkt door uw kansen door de Lader van Gegevens binnen SFDC in werking te stellen. Meer informatie over het gebruik van Data Loader vindt u in [dit artikel](/help/advanced-marketo-measure-features/custom-revenue-amount/using-data-loader-to-update-marketo-measure-custom-amount-field.md).

Als er onderweg vragen zijn, aarzel dan niet contact op te nemen met het accountteam van de Adobe (uw accountmanager) of [[!DNL Marketo] Ondersteuning](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
