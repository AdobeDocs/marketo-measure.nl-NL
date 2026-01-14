---
description: Richtlijnen voor aangepaste segmentatie voor Marketo Measure-gebruikers
title: Aangepaste segmentatie
exl-id: c20a2add-250e-45ff-97a6-1b1c03351b6a
feature: Segmentation
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 0%

---

# Aangepaste segmentatie {#custom-segmentation}

Met segmenten kunt u gegevens filteren in het [!DNL Marketo Measure] ROI-dashboard om verder te gaan met een specifieke gegevensset. Een segment kan bijvoorbeeld worden gedefinieerd op basis van het geografische gebied of een classificatiesysteem.

**waarom de Segmentatie van de Douane?**

Met Aangepaste segmentatie kunt u aanraakpunten filteren op categorieën (filternaam) en regels (filterwaarden). Klanten met Tier 1 krijgen één segment, Tiers 2 en hoger krijgen tien. Afhankelijk van het object waarnaar uw ROI-streepje verwijst (Lood of Contact), kunt u segmenten maken op basis van de velden op het object Lood/Contact. Bovendien kunt u segmenten maken op basis van alle velden die worden gevonden op het Opportunity-object.

**wanneer is de eigenschap van de Segmentatie van de Douane nuttig?**

De Segmentatie van de douane kan worden gebruikt om gegevens voor een bepaald verslagtype te zien. Zodra u de filterlogica in kaart brengt, zou u in de vraagWatervalweergave van het [!DNL Marketo Measure] dashboard moeten kunnen zien - de zelfde gegevens u in uw CRM zou zien.

**hoe ik opstelling het?**

>[!NOTE]
>
>Bij het bijwerken van segmentregels worden historische gegevens opnieuw verwerkt.

Stap 1 - Bepaal welke informatie u wilt zien.

Voordat u deze functie gebruikt, moet u uitzoeken op welke aanraakpuntinformatie u wilt filteren. Vergeet niet de exacte waarden in uw CRM te gebruiken voor uw recordtypen. De setup filtert aanraakpunten van boven naar beneden in de funnel voor marketingdoeleinden.

Stap 2 - Meld u aan en zoek de functie [!UICONTROL Segments] .

* Ga naar [&#x200B; experience.adobe.com/marketo-measure &#x200B;](https://experience.adobe.com/marketo-measure){target="_blank"} en login
* Selecteer onder de tab [!UICONTROL My Account] de optie [!UICONTROL Settings]
* Selecteer [!UICONTROL Segments] in de opties op de zijbalk links, onder de sectie [!UICONTROL Reporting] .

Stap 3 - begrijp de componenten.

* Met deze legenda krijgt u inzicht in de verschillende pictogrammen op deze pagina

![&#x200B; Gebruik deze legenda om de diverse pictogrammen te begrijpen die op deze pagina worden gevonden &#x200B;](assets/custom-segmentation-1.png)

Stap 4 - voeg de Regels van de Filter toe.

* Voer eerst de naam van de categorie in. [!UICONTROL Business Type] is een voorbeeld. Klik op het vinkje als u klaar bent. U moet een categorienaam invoeren voordat u segmenten kunt toevoegen
* Klik op het plusteken om een segment toe te voegen
* Voer een segmentnaam in. Bijvoorbeeld, kon u één segment voor Nieuwe Onderneming, Partners, Vernieuwen, of Upsell hebben

![&#x200B; ga een naam van het Segment in. Bijvoorbeeld, kon u één segment voor &#x200B;](assets/custom-segmentation-2.png) hebben

* Klik op het plusteken om de velden voor regelinvoer weer te geven. Met de opties in de keuzelijst Veld worden velden rechtstreeks van uw CRM opgehaald

![&#x200B; klik het plus pictogram om de gebieden van de regelinput te openbaren. De opties &#x200B;](assets/custom-segmentation-3.png)

>[!NOTE]
>
>Formulervelden kunnen niet worden gebruikt binnen uw regels en worden niet weergegeven in de keuzelijst. Omdat formules op de achtergrond berekenen en een record niet wijzigen, kan [!DNL Marketo Measure] niet bepalen of een record op een regel past of niet.

* De optie [!UICONTROL Value] is geen vervolgkeuzelijst en de waarde ervan moet handmatig worden ingevoerd. Controleer de waarden op je Salesforce org
* Herhaal dit proces voor de het segmentregels van Opportunity
* De categorie &quot;Overige&quot; is een standaardsegment dat ongedefinieerde aanraakpunten vastlegt. U kunt de naam van het standaardsegment wijzigen
* Klik op het pictogram van de prullenbak om een hele categorie of een afzonderlijke regel binnen een categorie te verwijderen. Of klik op het potloodpictogram om de categorie of regel te bewerken
* Bericht dat u &quot;[!UICONTROL Save]&quot;knoop en &quot;sparen en Proces&quot;knoop hebt. Met de knop Opslaan kunt u uw werk en wijzigingen in de loop van de tijd opslaan. Gebruik de knop Opslaan en verwerken alleen als u ervoor hebt gezorgd dat:

   * Uw toewijzing is correct
   * U hebt alle segmenten toegevoegd die u wilt bijhouden in een categorie
   * Met de knop Opslaan en verwerken activeert u [!DNL Marketo Measure] alle aanraakpunten te synchroniseren en de nieuwe gegevens toe te passen die u hebt toegevoegd. Dit proces duurt zeven dagen en de regels kunnen tijdens deze periode niet worden gewijzigd

**_Aanvullende notities:_**

Als de regels niet opstelling voor zowel Leads/Contacten als Kansen zijn, zult u slechts een gedeelte van uw gegevens zien. Om uit te werken, als u niet opstelling de regels van Kansen, zult u slechts lood/contactgegevens zonder de Kansen verbonden aan het zien. Het zelfde is waar als u opstelling geen regels voor lood/Contacten-u slechts Kansen zonder de bijbehorende Leads/Contacten zult zien.

Wanneer u klaar bent, klikt u eerst op [!UICONTROL Save] , dubbelklikt u op alles en klikt u vervolgens op [!UICONTROL Save and Process] . U kunt de instellingen zeven dagen na het opslaan en verwerken niet bewerken, omdat [!DNL Marketo Measure] de gegevens tijdens deze periode opnieuw opmaakt.

Als u een klant van Marketo Measure Ultimate bent en uw StandaardVoorwerp Dashboard als Contact hebt geplaatst, gebruik niet de hieronder twee gebieden specifiek voor Lood ([&#x200B; leert meer &#x200B;](/help/data-integrity-requirement.md){target="_blank"}).

* b2b.personStatus
* b2b.isConverted

**hoe ik sparen de geproduceerde rapporten?**

U kunt de gegenereerde rapporten niet rechtstreeks in de gebruikersinterface opslaan. [!DNL Marketo Measure] slaat de segmentnamen echter op in de URL, zodat u een record van elk rapport kunt bijhouden door een bladwijzer van de pagina te maken.
