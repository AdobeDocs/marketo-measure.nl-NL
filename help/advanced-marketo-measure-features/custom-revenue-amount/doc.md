---
description: Met een veld Aangepaste inkomstenbedrag - [!DNL Marketo Measure] - Productdocumentatie
title: Een veld Aangepaste omzettingsbedrag gebruiken
hide: true
hidefromtoc: true
feature: Custom Revenue Amount
source-git-commit: 2d2fe74998abd853f6592c5e65edfe2ce39d7ce6
workflow-type: tm+mt
source-wordcount: '656'
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

1. Typ in Setup &quot;Stroom&quot; in het vak Snel zoeken en selecteer **Stromen** om Flow Builder te starten. Klik in het rechterdeelvenster op **Nieuwe stroom** knop.

   ![](assets/using-a-custom-revenue-amount-field-1.png)

1. Selecteren **Opnamegerichte stroom** en klik op de knop **Maken** aan de rechteronderkant.

   ![](assets/using-a-custom-revenue-amount-field-2.png)

1. Selecteer het object Opportunity in het venster Start configureren. Selecteer in het gedeelte Trigger configureren de optie **Een record wordt gemaakt of bijgewerkt**.

   ![](assets/using-a-custom-revenue-amount-field-3.png)

1. Selecteer in het gedeelte Invoervoorwaarden instellen onder Voorwaardevereisten de optie **Aan Custom Condition Logic is voldaan**.
   * Selecteer in het zoekveld het veld Aangepast bedrag.
   * De operator instellen als **Is null** en de waarde als **Onwaar**.
   * De evaluatiecriteria instellen op **Telkens wanneer een record wordt bijgewerkt en aan de voorwaardenvereisten voldoet**.

   ![](assets/using-a-custom-revenue-amount-field-4.png)

1. Selecteer onder de sectie &quot;De stroom optimaliseren voor&quot; de optie **Snelle veldupdates**. Klikken **Gereed**.

   ![](assets/using-a-custom-revenue-amount-field-5.png)

1. Als u het element wilt toevoegen, klikt u op de plusknop (+) en selecteert u **Trigingrecord bijwerken**.

   ![](assets/using-a-custom-revenue-amount-field-6.png)

1. Voer het volgende in het venster Nieuwe updateverslagen in:

   * Voer een label in. De API-naam wordt automatisch gegenereerd
   * Onder &quot;Hoe te om Verslagen te vinden om bij te werken en hun Waarden te plaatsen,&quot;uitgezocht **Gebruik de opportunityrecord die de flow heeft geactiveerd**.
   * Selecteer in de sectie &#39;Filtervoorwaarden instellen&#39; de optie **Record altijd bijwerken** als voorwaarde voor het bijwerken van een record.
   * Selecteer in het veld &quot;Veldwaarden instellen voor Campagnerecord&quot; de optie Hoeveelheid Marketo Measure-opportuniteit en geef een waarde op voor het veld Aangepast bedrag.
   * Klikken **Gereed**.

   ![](assets/using-a-custom-revenue-amount-field-7.png)

1. Klikken **Opslaan**. Er wordt een pop-up weergegeven. Typ &quot;Flow Label&quot; in het venster Save the Flow (de naam van de Flow-API wordt automatisch gegenereerd). Klikken **Opslaan** opnieuw.

   ![](assets/using-a-custom-revenue-amount-field-8.png)

1. Klik op de knop **Activeren** om de flow te activeren.

   ![](assets/using-a-custom-revenue-amount-field-9.png)

## De workflow maken in Salesforce Classic {#create-the-workflow-in-salesforce-classic}

De volgende stappen gelden voor gebruikers van Salesforce Classic. Als u op Salesforce Lightning hebt overgegaan, die stappen [kan hierboven worden gevonden](#create-the-workflow-in-salesforce-lightning).

1. Ga naar **[!UICONTROL Setup]** > **[!UICONTROL Create]** > **[!UICONTROL Workflow & Approvals]** > **[!UICONTROL Workflow Rules]**.

   ![](assets/1.jpg)

1. Selecteren **[!UICONTROL New Rule]**, stelt u het object in als &quot;Opportunity&quot; en klikt u op **[!UICONTROL Next]**.

   ![](assets/2.jpg)

   ![](assets/3.jpg)

1. Configureer de workflow. De regelnaam instellen als &quot;Bijwerken&quot; [!DNL Marketo Measure] Opportuniteitsbedrag.&quot; Stel de evaluatiecriteria in op &quot;Gemaakt en telkens wanneer het wordt bewerkt.&quot; Voor de Criteria van de Regel, selecteer uw gebied van het Bedrag van de Douane en selecteer de Exploitant [!UICONTROL as "Not Equal To"] en laat het veld Waarde leeg.

   ![](assets/4.jpg)

1. Voeg een workflowactie toe. Deze keuzelijst instellen op &quot;[!UICONTROL New Field Update].&quot;
   ![](assets/5.jpg)

1. Hier kunt u veldgegevens invullen. In het veld Naam raden we u aan deze naam te gebruiken: &quot;[!DNL Marketo Measure] Hoeveelheid opp.&quot; De &quot;Unieke Naam&quot; wordt automatisch ingevuld op basis van het veld &quot;Naam&quot;. Selecteer in de keuzelijst &quot;Veld bijwerken&quot; de optie &quot;[!DNL Marketo Measure] Opportuniteitsbedrag.&quot; Nadat u het veld hebt geselecteerd, selecteert u het vak &quot;Workflowregels opnieuw toepassen na wijziging van veld&quot;. Selecteer in het vak &quot;Nieuwe veldwaarde opgeven&quot; de optie &quot;Een formule gebruiken om de nieuwe waarde in te stellen.&quot; Laat in het lege vak de API-naam van het veld Aangepast bedrag vallen. Klik op **[!UICONTROL Save]**.

   ![](assets/6.png)

1. U wordt teruggebracht naar een roll-up pagina voor uw werkschema, zeker om &quot;te activeren&quot;en u zult goed zijn om te gaan. Klik op **Bewerken** naast uw nieuwe workflow en klik vervolgens op **Activeren**.

   Zodra u deze stappen hebt voltooid, zullen de kansen moeten worden bijgewerkt om het werkschema teweeg te brengen om de nieuwe waarde van te hebben [!UICONTROL custom opportunity] veld.

   Dit kan worden verwezenlijkt door uw kansen door de Lader van Gegevens binnen SFDC in werking te stellen. Meer informatie over het gebruik van Data Loader vindt u in [dit artikel](/help/advanced-marketo-measure-features/custom-revenue-amount/using-data-loader-to-update-marketo-measure-custom-amount-field.md).

Als er onderweg vragen zijn, aarzel dan niet contact op te nemen met het accountteam van de Adobe (uw accountmanager) of [[!DNL Marketo] Ondersteuning](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
