---
unique-page-id: 18874604
description: Aangepaste segmentatie - [!DNL Marketo Measure]
title: Aangepaste segmentatie
exl-id: c20a2add-250e-45ff-97a6-1b1c03351b6a
feature: Segmentation
source-git-commit: e1ad563aac12ceb6bea6c28621ebd1cb7ec0a923
workflow-type: tm+mt
source-wordcount: '733'
ht-degree: 0%

---

# Aangepaste segmentatie {#custom-segmentation}

De segmenten verstrekken de capaciteit om gegevens in te filtreren [!DNL Marketo Measure] ROI-dashboard om verder te gaan met een specifieke gegevensset. Een segment kan bijvoorbeeld worden gedefinieerd op basis van het geografische gebied of een classificatiesysteem.

**Waarom aangepaste segmentatie?**

Met Aangepaste segmentatie kunt u aanraakpunten filteren op categorieën (filternaam) en regels (filterwaarden). Klanten met Tier 1 krijgen één segment, Tiers 2 en hoger krijgen tien. Afhankelijk van het object waarnaar uw ROI-streepje verwijst (Lood of Contact), kunt u segmenten maken op basis van de velden op het object Lood/Contact. Bovendien kunt u segmenten maken op basis van alle velden die worden gevonden op het Opportunity-object.

**Wanneer is de functie Aangepaste segmentatie nuttig?**

De Segmentatie van de douane kan worden gebruikt om gegevens voor een bepaald verslagtype te zien. Als u de filterlogica eenmaal hebt toegewezen, kunt u deze weergeven in het dialoogvenster [!DNL Marketo Measure] De mening van de Waterval van de Dvraag van het dashboard - de zelfde gegevens u in uw CRM zou zien.

**Hoe kan ik het opzetten?**

>[!NOTE]
>
>Bij het bijwerken van segmentregels worden historische gegevens opnieuw verwerkt.

Stap 1 - Bepaal welke informatie u wilt zien.

Voordat u deze functie gebruikt, moet u uitzoeken op welke aanraakpuntinformatie u wilt filteren. Vergeet niet de exacte waarden in uw CRM te gebruiken voor uw recordtypen. De opstelling zal touchpoints van de bovenkant aan de bodem van de marketing trechter filtreren.

Stap 2 - Meld u aan en zoek de [!UICONTROL Segments] gebruiken.

* Ga naar [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} en aanmelden
* Onder de [!UICONTROL My Account] tab, selecteert u [!UICONTROL Settings]
* Selecteren [!UICONTROL Segments] van de opties op de zijbalk naar links, onder de optie [!UICONTROL Reporting] sectie

Stap 3 - begrijp de componenten.

* Met deze legenda krijgt u inzicht in de verschillende pictogrammen op deze pagina

![](assets/1.png)

Stap 4 - voeg de Regels van de Filter toe.

* Voer eerst de naam van de categorie in. [!UICONTROL Business Type] is een voorbeeld. Klik op het vinkje als u klaar bent. U moet een categorienaam invoeren voordat u segmenten kunt toevoegen
* Klik op het plusteken om een segment toe te voegen
* Voer een segmentnaam in. Bijvoorbeeld, kon u één segment voor Nieuwe Onderneming, Partners, Vernieuwen, of Upsell hebben

![](assets/2.png)

* Klik op het plusteken om de velden voor regelinvoer weer te geven. Met de opties in de keuzelijst Veld worden velden rechtstreeks van uw CRM opgehaald

![](assets/3.png)

>[!NOTE]
>
>Formulervelden kunnen niet worden gebruikt binnen uw regels en worden niet weergegeven in de keuzelijst. Omdat formules op de achtergrond berekenen en een record niet wijzigen, [!DNL Marketo Measure] kan niet ontdekken of een verslag een regel past of niet.

* De [!UICONTROL Value] is geen vervolgkeuzelijst en de waarde ervan moet handmatig worden ingevoerd. Controleer de waarden in uw Salesforce org
* Herhaal dit proces voor de het segmentregels van Opportunity
* De categorie &quot;Overige&quot; is een standaardsegment dat ongedefinieerde aanraakpunten vastlegt. U kunt de naam van het standaardsegment wijzigen
* Klik op het pictogram van de prullenbak om een hele categorie of een afzonderlijke regel binnen een categorie te verwijderen. Of klik op het potloodpictogram om de categorie of regel te bewerken
* Je hebt een &#39;[!UICONTROL Save]&quot; en een knop &quot;Opslaan en verwerken&quot;. Met de knop Opslaan kunt u uw werk en wijzigingen in de loop van de tijd opslaan. Gebruik de knop Opslaan en verwerken alleen als u ervoor hebt gezorgd dat:

   * Uw toewijzing is correct
   * U hebt alle segmenten toegevoegd die u wilt bijhouden in een categorie
   * De knop Opslaan en verwerken activeert [!DNL Marketo Measure] om al uw aanraakpunten te synchroniseren en de nieuwe gegevens toe te passen die u hebt toegevoegd. Dit proces duurt zeven dagen en de regels kunnen tijdens deze periode niet worden gewijzigd

**_Aanvullende opmerkingen:_**

Als de regels niet opstelling voor zowel Leads/Contacten als Kansen zijn, zult u slechts een gedeelte van uw gegevens zien. Om uit te werken, als u niet opstelling de regels van Kansen, zult u slechts lood/contactgegevens zonder de Kansen verbonden aan het zien. Het zelfde is waar als u opstelling geen regels voor lood/Contacten-u slechts Kansen zonder de bijbehorende Leads/Contacten zult zien.

Als u klaar bent, klikt u op [!UICONTROL Save] eerst, controleer alles tweemaal en klik dan [!UICONTROL Save and Process]. Vergeet niet dat u uw instellingen zeven dagen na het opslaan en verwerken niet kunt bewerken, omdat [!DNL Marketo Measure] maakt uw gegevens tijdens deze tijd opnieuw op.

Als u een Marketo Measure Ultimate-klant bent en uw standaarddashboard-object als contactpersoon hebt ingesteld, gebruikt u de onderstaande twee velden niet die specifiek zijn voor Lead ([Meer informatie](/help/marketo-measure-ultimate/data-integrity-requirement.md){target="_blank"}).

* b2b.personStatus
* b2b.isConverted

**Hoe kan ik de gegenereerde rapporten opslaan?**

U kunt de gegenereerde rapporten niet rechtstreeks in de gebruikersinterface opslaan. Maar [!DNL Marketo Measure] Hiermee slaat u de segmentnamen op in de URL, zodat u een record van elk rapport kunt bijhouden door een bladwijzer van de pagina te maken.
