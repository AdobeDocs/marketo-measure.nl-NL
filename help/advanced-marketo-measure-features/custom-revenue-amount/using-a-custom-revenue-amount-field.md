---
unique-page-id: 18874793
description: Met een veld Aangepaste inkomstenbedrag - [!DNL Marketo Measure] - Productdocumentatie
title: Een veld Aangepaste inkomstenbedrag gebruiken
exl-id: 517ea4f9-aa83-48d0-8ce7-003f4a907430
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 0%

---

# Een veld Aangepaste inkomstenbedrag gebruiken {#using-a-custom-revenue-amount-field}

Standaard halen Aanraakpunten voor koperkenmerk de opportunity Amount uit een van de volgende twee velden:

* Bedrag (standaard SFDC)
* [!DNL Marketo Measure] Opportuniteitsbedrag (aangepast)

Als u een gebied van het Bedrag van de douane op uw Kansen gebruikt, zullen wij een werkschema moeten vormen om de Ontvangsten van het Aanraakpunt van de Koper te berekenen. Hiervoor is meer kennis van [!DNL Salesforce], kan dit dus hulp vereisen van uw SFDC-beheerder.

Om te beginnen hebben we de volgende informatie nodig:

* API Naam van uw veld Bedrag

Vanaf hier beginnen we de workflow te maken.

1. Ga naar **[!UICONTROL Setup]** > **[!UICONTROL Create]** > **[!UICONTROL Workflow & Approvals]** > **[!UICONTROL Workflow Rules]**.

   ![](assets/1.jpg)

1. Selecteren **[!UICONTROL New Rule]**, stelt u het object in als &quot;Opportunity&quot; en klikt u op **[!UICONTROL Next]**.

   ![](assets/2.jpg)

   ![](assets/3.jpg)

1. Configureer de workflow. De regelnaam instellen als &quot;Bijwerken&quot; [!DNL Marketo Measure] Opportuniteitsbedrag.&quot; Stel de evaluatiecriteria in op &quot;Gemaakt en telkens wanneer het wordt bewerkt.&quot; Voor de Criteria van de Regel, selecteer uw gebied van het Bedrag van de Douane en selecteer de Exploitant [!UICONTROL as "Not Equal To"] en laat het veld Waarde leeg.

   ![](assets/4.jpg)

1. Voeg een workflowactie toe. Deze keuzelijst instellen op &quot;[!UICONTROL New Field Update].&quot;

   ![](assets/5.jpg)

1. Hier kunt u veldgegevens invullen. In het veld Naam raden we u aan deze naam te gebruiken: &quot;[!DNL Marketo Measure] Hoeveelheid opp.&quot; De &quot;Unieke Naam&quot; wordt automatisch ingevuld op basis van het veld &quot;Naam&quot;. Selecteer in de keuzelijst &quot;Bij te werken veld&quot; de optie &quot;[!DNL Marketo Measure] Opportuniteitsbedrag.&quot; Nadat u het veld hebt geselecteerd, selecteert u het vak &quot;Workflowregels opnieuw toepassen na wijziging van veld&quot;. Selecteer in het vak &quot;Nieuwe veldwaarde opgeven&quot; de optie &quot;Een formule gebruiken om de nieuwe waarde in te stellen.&quot; Laat in het lege vak de API-naam van het veld Aangepast bedrag vallen. Klik op **[!UICONTROL Save]**.

   ![](assets/6.png)

1. U wordt teruggebracht naar een roll-up pagina voor uw werkschema, zeker om &quot;te activeren&quot;en u zult goed zijn om te gaan. Klik op **Bewerken** naast uw nieuwe workflow en klik vervolgens op **Activeren**.

   Zodra u deze stappen hebt voltooid, zullen de kansen moeten worden bijgewerkt om het werkschema teweeg te brengen om de nieuwe waarde van te hebben [!UICONTROL custom opportunity] veld.

   Dit kan worden verwezenlijkt door uw kansen door de Lader van Gegevens binnen SFDC in werking te stellen. Meer informatie over het gebruik van Data Loader vindt u in [dit artikel](/help/advanced-marketo-measure-features/custom-revenue-amount/using-data-loader-to-update-marketo-measure-custom-amount-field.md).

Als er onderweg vragen zijn, aarzel dan niet om contact op te nemen met uw Customer Success Manager of [[!DNL Marketo] Ondersteuning](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
