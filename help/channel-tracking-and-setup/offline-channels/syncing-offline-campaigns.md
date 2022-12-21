---
unique-page-id: 18874600
description: Offlinecampagnes synchroniseren - [!DNL Marketo Measure] - Productdocumentatie
title: Offlinecampagnes synchroniseren
exl-id: a6f9e217-ff6e-474d-9f14-c6f6238c9e84
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 0%

---

# Offlinecampagnes synchroniseren {#syncing-offline-campaigns}

Het kan moeilijk zijn om offline campagnes nauwkeurig te volgen en te begrijpen hoe zij met uw digitale marketing inspanningen vergelijken. [!DNL Marketo Measure] kunt u aanraakpunten bijhouden en koppelen aan uw offlinecampagnes in [!DNL Salesforce], zelfs in situaties waarin [!DNL Salesforce] de campagne wordt pas een paar weken na de gebeurtenis gemaakt.

## Voordat u gaat synchroniseren {#before-you-sync}

Hier volgen enkele tips voor een efficiënt synchronisatieproces:

* Offlinecampagnes hebben betrekking op marketinginteracties die niet online plaatsvinden. Dit zijn onder andere marketingkanalen zoals gebeurtenissen, webinars en winkels. Neem alleen offlinemarketingcampagnes op.
* Als u campagnes wilt opnemen die online activiteiten hebben bijgehouden voordat u de software installeerde [!DNL Marketo Measure], dient u de einddatum van het aanraakpunt in te stellen als de datum waarop uw JavaScript-code op uw site is geïmplementeerd.
* Het is handig om de [!DNL Marketo Measure] op de pagina Offlinekanalen wordt geopend, zodat u gemakkelijk de verschillende typen campagnes kunt identificeren en kunt zien in welk marketingkanaal de aanraakpunten worden opgenomen.

* Controleer alles voordat u op &quot;[!UICONTROL Save]&quot; button!

## Aanraakpunt datum bulkupdate {#bulk-update-touchpoint-date}

In [!DNL Salesforce]In het veld Aanmaakdatum in het object Campagne-lidobject wordt de datum vermeld waarop het Campagne-lid aan de campagne is toegevoegd. Voor een vloeiend synchronisatieproces moet het veld Datum aanraakpunt koper dezelfde datum hebben als de datum in het object Lid van Salesforce-campagne. Deze stap wordt uitgevoerd met &quot;[!UICONTROL Bulk Update Touchpoint Date button],&quot; _voor_ u selecteert de [!UICONTROL picklist] in het veld Aanraakpunten koper inschakelen.

Waarom is dit belangrijk? Stel je voor dat je bedrijf een poot heeft gesponsord op een conferentie in januari. Tijdens de conferentie hebben 100 personen belangstelling getoond voor uw product en hun contactgegevens verstrekt om e-mailupdates te ontvangen. Drie weken later creëerde je eindelijk een campagne in [!DNL Salesforce] de resultaten van de conferentie te volgen .

Uw uploaddatum zou drie weken later zijn dan de conferentiedatum. Als u dit verschil wilt corrigeren, [!UICONTROL Bulk Update Touchpoint Date] kan worden gebruikt om de aangewezen datum te plaatsen. De knop wordt afgebeeld in de onderstaande afbeelding.

![](assets/1-3.png)

In dit geval wordt de uploaddatum drie weken later ingevuld. Deze stap moet worden uitgevoerd voordat u &quot;[!UICONTROL Enable Buyer Touchpoints]&quot;.

Samenvattend, als u de [!UICONTROL Bulk Update Touchpoint Date] en wijzigt u de datum van het aanraakpunt in de datum van de gebeurtenis, [!DNL Marketo Measure] Hiermee worden aanraakpunten gegenereerd voor de datum waarop de gebeurtenis plaatsvindt, niet voor de datum waarop de gebeurtenis is geüpload.

U kunt ook de datums voor alle leden van de campagne bijwerken op een bestaande campagne. Zorg er daarbij voor dat de datum van het aanraakpunt de datum van de interactie van het lid is. Klik gewoon op de datum waarop de koper van de Bulk Update Touchpoint Date wordt weergegeven, filtert u de lijst met de leden van de campagne naar wens en in &quot;[!UICONTROL Select Date]&quot; boven de lijst met leden van de campagne voegt u dezelfde datum toe als de datum waarop de gebeurtenis heeft plaatsgevonden.

>[!CAUTION]
>
>Zorg ervoor dat u de datum van het aanraakpunt bijwerkt _voor_ u schakelt aanraakpunten in voor alle leden van de campagne.

![](assets/2-3.png)

## Een campagne maken en aanraakpunten voor kopers synchroniseren {#how-to-create-a-campaign-and-sync-buyer-touchpoints}

Een campagne maken in [!DNL Salesforce], navigeert u naar de [!UICONTROL Campaigns] tab en selecteer &#39;[!UICONTROL New]&#39; zoals weergegeven in de onderstaande afbeelding. Afhankelijk van uw [!DNL Salesforce] Als u wilt instellen, moet u mogelijk campagnes toevoegen aan de bovenste balk door op de plusknop (+) te klikken.

![](assets/3-3.png)

Wanneer u deze campagne maakt, klikt u op de knop &quot;[!UICONTROL Enable Buyer Touchpoints]&quot; en selecteer een van de volgende opties in de keuzelijst:

![](assets/4-3.png)

* **Inclusief alle leden van de campagne**
   * Deze optie schakelt [!DNL Marketo Measure] om een aanraakpunt toe te wijzen aan elk campagnetelid.

* **Inclusief leden van de campagne &quot;Responded&quot;.**
   * Met deze optie past u aanraakpunten toe op leden van de campagne met de status &quot;Reageerd&quot;.

* **Sluit alle leden van de campagne uit.**
   * Met deze optie worden geen aanraakpunten toegewezen aan leden van de campagne en wordt een vlag gebruikt die aangeeft dat de campagne bewust is uitgesloten van [!DNL Marketo Measure]. Als u ooit een campagne synchroniseert met Aanraakpunten voor kopers bij een ongeluk, kunt u de status wijzigen in &quot;Alle campagneleden uitsluiten&quot; en worden de aanraakpunten verwijderd.

Nadat een van deze selecties is gekozen, [!DNL Marketo Measure] wijst elk campagnerelid zo nodig een aanraakpunt toe. De lead of contactpersoon die aan de campagne is toegevoegd _moet_ beschikken over een e-mailadres dat aan hun record is gekoppeld om [!DNL Marketo Measure] om een aanraakpunt te maken. Zonder e-mailadres [!DNL Marketo Measure] geen aanraakpunt toewijzen aan het lid van de campagne.

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] Universiteit: Offlinekanalen toewijzen](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c630eca34d9f0367662b77f)
>
>[[!DNL Marketo Measure] Universiteit: Campagneobjectvelden](https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c63007334d9f0367662b758)
