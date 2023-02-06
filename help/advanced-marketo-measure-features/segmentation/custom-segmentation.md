---
unique-page-id: 18874604
description: Aangepaste segmentatie - [!DNL Marketo Measure] - Productdocumentatie
title: Aangepaste segmentatie
exl-id: c20a2add-250e-45ff-97a6-1b1c03351b6a
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 0%

---

# Aangepaste segmentatie {#custom-segmentation}

De segmenten verstrekken de capaciteit om gegevens in te filtreren [!DNL Marketo Measure] ROI-dashboard om verder te gaan met een specifieke gegevensset. Een segment kan bijvoorbeeld worden gedefinieerd op basis van het geografische gebied of een classificatiesysteem.

**Waarom aangepaste segmentatie?**

Met de functie Aangepaste segmentatie kunt u aanraakpunten filteren op één categorie en op maximaal vijf segmenten. Afhankelijk van het object waarnaar uw ROI-streepje verwijst (Lood of Contact), kunt u segmenten maken op basis van de velden op het object Lood/Contact. Ook, zult u segmenten kunnen tot stand brengen die op om het even welke gebieden worden gebaseerd die op het Voorwerp van de Opportunity worden gevonden.

**Wanneer is de functie Aangepaste segmentatie nuttig?**

De Segmentatie van de douane kan worden gebruikt om gegevens voor een bepaald verslagtype te zien. Als u de filterlogica eenmaal hebt toegewezen, kunt u deze in het dialoogvenster [!DNL Marketo Measure] De mening van de Waterval van de Dvraag van het dashboard - de zelfde gegevens u in uw CRM zou zien.

**Hoe kan ik het opzetten?**

Stap 1 - Bepaal welke informatie u wilt zien.

Voordat u deze functie gebruikt, moet u uitzoeken op welke aanraakpuntinformatie u wilt filteren. Vergeet niet de exacte waarden in uw CRM te gebruiken voor uw recordtypen. De opstelling zal touchpoints van de bovenkant aan de bodem van de marketing trechter filtreren.

Stap 2 - Login en bepaal de plaats van de eigenschap van Segmenten.

* Ga naar [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} en aanmelden
* Onder de [!UICONTROL My Account] tab, selecteert u [!UICONTROL Settings]
* Selecteren [!UICONTROL Segments] van de opties op de zijbalk naar links, onder de optie [!UICONTROL Reporting] sectie

Stap 3 - begrijp de componenten.

* Met deze legenda krijgt u inzicht in de verschillende pictogrammen op deze pagina

![](assets/1.png)

Stap 4 - voeg de Regels van de Filter toe.

* Voer eerst de categorienaam in. Business Type is een voorbeeld. Klik op het vinkje als u klaar bent. U moet een categorienaam invoeren voordat u segmenten kunt toevoegen
* Klik op het plusteken om een segment toe te voegen
* Voer een segmentnaam in. Bijvoorbeeld, kon u één segment voor Nieuwe Onderneming, Partners, Vernieuwen, of Upsell hebben

![](assets/2.png)

* Klik op het plusteken om de velden voor regelinvoer weer te geven. Met de opties in de keuzelijst Veld worden velden rechtstreeks van uw CRM opgehaald

![](assets/3.png)

>[!NOTE]
>
>Formulervelden kunnen niet worden gebruikt binnen uw regels en worden niet weergegeven in de keuzelijst. Omdat formules op de achtergrond berekenen en een record niet wijzigen, [!DNL Marketo Measure] kan niet ontdekken of een verslag een regel past of niet.

* De optie Waarde is geen vervolgkeuzelijst en de waarde ervan moet handmatig worden ingevoerd. Controleer de waarden in uw Salesforce org
* Herhaal dit proces voor de het segmentregels van Opportunity
* De categorie &quot;Overige&quot; is een standaardsegment dat ongedefinieerde aanraakpunten vastlegt. U kunt de naam van het standaardsegment wijzigen
* Klik op het pictogram van de prullenbak om een hele categorie of een afzonderlijke regel binnen een categorie te verwijderen. U kunt ook op het potloodpictogram klikken om de categorie of regel te bewerken
* U ziet dat u een knop &quot;Opslaan&quot; en &quot;Opslaan en verwerken&quot; hebt. Met de knop Opslaan kunt u uw werk en wijzigingen in de loop van de tijd opslaan. Gebruik de knop Opslaan en verwerken alleen als u ervoor hebt gezorgd dat:

   * Uw toewijzing is correct
   * U hebt alle segmenten toegevoegd die u wilt bijhouden in een categorie
   * De knop Opslaan en verwerken activeert [!DNL Marketo Measure] om al uw aanraakpunten te synchroniseren en de nieuwe gegevens toe te passen die u hebt toegevoegd. Dit proces duurt zeven dagen en de regels kunnen tijdens deze periode niet worden gewijzigd

**_Aanvullende opmerkingen:_**

Als de regels niet opstelling voor zowel Leads/Contacten als Kansen zijn, zult u slechts een gedeelte van uw gegevens zien. Om uit te werken, als u niet opstelling de regels van Kansen, zult u slechts lood/contactgegevens zonder de Kansen verbonden aan het zien. Het zelfde is waar als u opstelling geen regels voor lood/Contacten-u slechts Kansen zonder de bijbehorende Leads/Contacten zult zien.

Als u klaar bent, klikt u op [!UICONTROL Save] eerst, controleer alles tweemaal en klik dan [!UICONTROL Save and Process]. Houd er rekening mee dat u de instellingen zeven dagen lang niet kunt bewerken wanneer u het bestand opslaat en verwerkt, zoals [!DNL Marketo Measure] maakt uw gegevens tijdens deze tijd opnieuw op.

**Hoe kan ik de gegenereerde rapporten opslaan?**

U kunt de gegenereerde rapporten niet rechtstreeks in de gebruikersinterface opslaan. Maar [!DNL Marketo Measure] Hiermee slaat u de segmentnamen op in de URL, zodat u een record van elk rapport kunt bijhouden door een bladwijzer van de pagina te maken.
