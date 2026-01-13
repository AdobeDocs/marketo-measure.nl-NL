---
description: Offlinecampagnes synchroniseren -  [!DNL Marketo Measure]
title: Offlinecampagnes synchroniseren
exl-id: a6f9e217-ff6e-474d-9f14-c6f6238c9e84
feature: Channels
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 0%

---


# Offlinecampagnes synchroniseren {#syncing-offline-campaigns}

Het kan moeilijk zijn om offline campagnes nauwkeurig te volgen en te begrijpen hoe zij met uw digitale marketing inspanningen vergelijken. Met [!DNL Marketo Measure] kunt u aanraakpunten bijhouden en koppelen aan uw offlinecampagnes in [!DNL Salesforce] , zelfs in situaties waarin een [!DNL Salesforce] -campagne pas enkele weken na de gebeurtenis wordt gemaakt.

>[!NOTE]
>Dit artikel behandelt een verouderd proces. Wij moedigen gebruikers aan om het [&#x200B; nieuwe, verbeterde in-app proces &#x200B;](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"} te gebruiken.

## Voordat u gaat synchroniseren {#before-you-sync}

Hier volgen enkele tips voor een efficiënt synchronisatieproces:

* Offlinecampagnes hebben betrekking op marketinginteracties die niet online plaatsvinden. Dit zijn onder andere marketingkanalen zoals gebeurtenissen, webinars en winkels. Neem alleen offlinemarketingcampagnes op.
* Als u campagnes wilt opnemen die online activiteiten hebben bijgehouden voordat u [!DNL Marketo Measure] installeerde, moet u de Einddatum van het aanraakpunt instellen als de datum waarop onze JavaScript op uw site is geïmplementeerd.
* Het is handig om de app [!DNL Marketo Measure] open te houden op de pagina Offlinekanalen, zodat u gemakkelijk de verschillende typen campagnes kunt identificeren en ook kunt zien in welk marketingkanaal de aanraakpunten worden opgenomen.

* Controleer alles voordat u op de knop &quot;[!UICONTROL Save]&quot; klikt.

## Aanraakpunt datum bulkupdate {#bulk-update-touchpoint-date}

In [!DNL Salesforce], merkt het Gemaakt gebied van de Datum op het Voorwerp van het Lid van de Campagne de datum aan het campagnelid werd toegevoegd. Voor een vloeiende synchronisatie moet het datumveld Buyer Touchpoint dezelfde datum hebben als de datum in het Object Campagne-lid van Salesforce. Deze stap wordt uitgevoerd gebruikend &quot;[!UICONTROL Bulk Update Touchpoint Date button],&quot;_vóór_ u selecteert de [!UICONTROL picklist] optie op het Enable gebied van Aanraakpunten van de Koper.

Waarom is dit belangrijk? Stel je voor dat je bedrijf een poot heeft gesponsord op een conferentie in januari. Op de conferentie gaven 100 personen blijk van belangstelling voor uw product en verstrekten hun contactgegevens om e-mailupdates te ontvangen. Drie weken later maakte u eindelijk een campagne in [!DNL Salesforce] om de resultaten van de conferentie te volgen.

Uw uploaddatum zou drie weken later zijn dan de conferentiedatum. U kunt dit verschil corrigeren door op de knop [!UICONTROL Bulk Update Touchpoint Date] de juiste datum in te stellen. De knop wordt afgebeeld in de onderstaande afbeelding.

![&#x200B; 3 &#x200B;](assets/1-3.png)

In dit geval wordt de uploaddatum drie weken later ingevuld. Deze stap zou vóór het plaatsen van het &quot;[!UICONTROL Enable Buyer Touchpoints]&quot;gebied moeten worden gedaan.

Samenvattend, als u de [!UICONTROL Bulk Update Touchpoint Date] knoop gebruikt en de datum van het Aanraakpunt in de datum van de gebeurtenis verandert, zal [!DNL Marketo Measure] Aanraakpunten voor de daadwerkelijke datum van de gebeurtenis-niet de datum van het uploaden produceren.

U kunt ook de datums voor alle leden van de campagne bijwerken op een bestaande campagne. Zorg er daarbij voor dat de datum van het aanraakpunt de datum van de interactie van het lid is. Klik de Datum van Buyer Touchpoint van de Update van het Bulk, filter de lijst van campagnegeleden zoals aangewezen, en in de &quot;[!UICONTROL Select Date]&quot;optie boven de lijst van campagneleden, voeg de zelfde datum toe zoals de datum de gebeurtenis plaatsvond.

>[!CAUTION]
>Zorg ervoor u de datum van het Aanraakpunt _vóór_ bijwerkt u aanraakpunten voor alle campagnegeleden toelaat.

![&#x200B; 3 &#x200B;](assets/2-3.png)

## Een campagne maken en aanraakpunten voor kopers synchroniseren {#how-to-create-a-campaign-and-sync-buyer-touchpoints}

Om een Campagne in [!DNL Salesforce] tot stand te brengen, navigeer aan het [!UICONTROL Campaigns] lusje en selecteer &quot;[!UICONTROL New]&quot;zoals aangetoond in het hieronder beeld. Afhankelijk van de instelling van [!DNL Salesforce] moet u mogelijk campagnes toevoegen aan de bovenste balk door op de plusknop (+) te klikken.

![&#x200B; 3 &#x200B;](assets/3-3.png)

Wanneer u deze campagne creeert, klik het &quot;[!UICONTROL Enable Buyer Touchpoints]&quot;gebied en selecteer één van de volgende opties van picklist:

![&#x200B; 3 &#x200B;](assets/4-3.png)

* **omvat alle campagneleden**
   * Met deze optie kan in [!DNL Marketo Measure] een aanraakpunt worden toegewezen aan elk lid van de campagne.

* **omvat &quot;Responded&quot;campagnegeleden.**
   * Met deze optie past u aanraakpunten toe op leden van de campagne met de status &quot;Reageerd&quot;.

* **sluit alle campagnereden uit.**
   * Met deze optie worden aanraakpunten niet toegewezen aan leden van de campagne en wordt een vlag gebruikt die aangeeft dat de campagne bewust is uitgesloten van [!DNL Marketo Measure] . Als u ooit een campagne synchroniseert met Aanraakpunten voor kopers bij een ongeluk, kunt u de status wijzigen in &quot;Alle campagneleden uitsluiten&quot; en worden de aanraakpunten verwijderd.

Nadat u een van deze selecties hebt gekozen, wijst [!DNL Marketo Measure] aan elk campagnetelid indien van toepassing een aanraakpunt toe. De Lood of het Contact dat aan de campagne _wordt toegevoegd moet_ een e-mailadres hebben verbonden aan hun verslag opdat [!DNL Marketo Measure] om een touchpoint tot stand te brengen. Zonder een e-mailadres wijst [!DNL Marketo Measure] geen aanraakpunt toe aan het lid van de campagne.

>[!MORELIKETHIS]
>[[!DNL Marketo Measure]  Leerprogramma&#39;s: Het in kaart brengen van Off-line Kanalen &#x200B;](https://experienceleague.adobe.com/nl/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-salesforce/mapping-offline-channels){target="_blank"}
>[[!DNL Marketo Measure] Zelfstudies: Objectvelden voor campagne uitlijnen &#x200B;](https://experienceleague.adobe.com/nl/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-salesforce/campaign-object-fields){target="_blank"}
