---
unique-page-id: 18874704
description: veelgestelde vragen over activiteitenkenmerken - [!DNL Marketo Measure] - Productdocumentatie
title: Veelgestelde vragen over activiteitenkenmerk
exl-id: 6272024f-b6ae-4aa7-ba92-c9f183549614
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '780'
ht-degree: 0%

---

# Veelgestelde vragen over activiteitenkenmerk {#activities-attribution-faq}

De [!DNL Marketo Measure] Met functionaliteit voor activiteiten kunnen we al uw activiteitenrecords importeren en aanraakpunten voor deze activiteiten genereren, zodat deze activiteiten een toewijzingkrediet krijgen. Het meest gebruikelijke gebruiksgeval is het volgen van Activiteiten van het team van de Verkoop, aangezien zij algemeen een verslag van telefoongesprekken of e-mails zullen tot stand brengen die naar vooruitzichten worden verzonden. Andere unieke dingen die kunnen worden bijgehouden, zijn inhoudsinteracties zoals het downloaden van elementen of videoweergaven.

**Hoe is dit anders dan offline campagnes?**

Het grootste verschil is dat campagnes slechts één aanraakpunt kunnen bieden, omdat campagnes slechts één campagnelid toestaan voor elke leider of contactpersoon. Dat betekent u terugkomende gebeurtenissen zoals uitgaande vraag of demo&#39;s of webinar aanwezigen kunt niet volgen, tenzij u individuele Campagnes voor elke groepering creeert. Met activiteiten kunt u elke gebeurtenis meten.

**Is er een verschil tussen Taak, Gebeurtenissen, en Activiteiten?**

Het object Activity fungeert als paraplu, of bovenliggend element, voor de objecten Task en Event. De activiteiten hebben hoofdzakelijk betrekking op zowel Taken als Gebeurtenissen. Taken worden doorgaans gebruikt om snel eenmalige items op te nemen, zoals een telefoongesprek of een e-mail. Gebeurtenissen worden doorgaans gebruikt voor dingen die een begin- of einddatum kunnen hebben, zoals vergaderingen of conferenties.

**Als ik een lead of contactpersoon met dezelfde terugkerende taak heb, zoals een e-mail of oproep, zal ik dan de aanraakpunten voor kopers voor al deze taken bekijken?**

Ja. Er zal een 1:1 verhouding tussen uw gesynchroniseerde Activiteiten en gecreeerd Aanraakpunten zijn.

**Hoe weet ik welke records ertoe zullen leiden dat er aanraakpunten worden gemaakt?**

Een goede suggestie is om eerst uw filters in te stellen met behulp van het object Activity in uw CRM. Gebaseerd op de filterregels, die u een goed idee zullen geven over hoeveel verslagen onder die criteria vallen, dan kunt u het verfijnen zoals nodig. Dit wordt niet vereist, maar een nuttige manier voor gebruikers om te begrijpen hoeveel Activiteiten Touchpoints zullen worden gecreeerd zodra de regels van de Activiteiten opstelling zijn.

**Wat is de [!DNL Marketo Measure] Naam campagne?**

Aangezien deze activiteiten zullen leiden tot een aanraakpunt, [!DNL Marketo Measure] moet weten tot welk kanaal en subkanaal zij behoren. Voor elke regel, zult u moeten verstrekken a [!DNL Marketo Measure] Naam campagne. Zodra dat wordt gecreeerd, kunt u Online Kanalen CSV gebruiken om in kaart te brengen dat [!DNL Marketo Measure] Campagnenaam aan zijn aangewezen Kanaal. De [!DNL Marketo Measure] De naam van de campagne wordt ook weergegeven op het aanraakpunt zelf in het dialoogvenster [!UICONTROL Ad Campaign Name] veld.

**Welke andere aanraakpuntvelden zijn gevuld?**

| **Aanraakpuntveld** | **Waarde** |
|---|---|
| Lead/contactpersoon | Alle activiteiten hebben betrekking op een lead of contactpersoon |
| Campagne | Kanaal.Subkanaal [[!DNL Marketo Measure]] |
| Aanraakpuntbron | CRM-activiteit |
| Normaal | Activity.Type |
| Type aanraakpunt | Activity.Type |
| Naam advertentiecampagne | [!DNL Marketo Measure] Campagnenaam |
| Inhoud toevoegen | Activiteitenonderwerp |
| Advertentie-id | Externe id activiteit |
| Aanraakpuntdatum | [aangepaste - set in apps] |

**Wat als ik een verschillende regel voor elke Verkoper moet creëren? Moet ik een andere [!DNL Marketo Measure] Campagnes voor elk?**

Nee, dat doe je niet. We introduceerden een concept van &#39;Dynamic Campaign Names&#39;. Hierdoor kunt u (een deel van) de [!DNL Marketo Measure] Campagnenaam die een &quot;vervangingsparameter&quot;gebruikt die een gebied van het voorwerp van de Activiteit van verwijzingen voorziet. Als u bijvoorbeeld een [!DNL Marketo Measure] De Naam van de campagne getiteld &quot;Uitgaande Vraag&quot;maar u wilt de Verkoop aan het eind zijn, neemt u de het gebiedsnaam van CRM en roept [!DNL Marketo Measure] De naam van de campagne &quot;Uitgaande Vraag {AssignedTo}&quot;of &quot;Uitgaande Vraag {CreatedBy}.&quot;

**Hoe kan ik Activiteiten instellen in het dialoogvenster [!DNL Marketo Measure] app?**

Richtingen op hoe te om Activites binnen te vormen [!UICONTROL Marketo] De maatstoepassing vindt u in het dialoogvenster [!DNL Marketo Measure] Activiteiten ondersteunen artikel.

**Wat betekenen de verschillende operatoren?**

* is gelijk aan: exacte overeenkomst met de waarde (ook bekend als: sociaal)
* bevat: de tekst staat in het midden ( ook bekend als : &#42;sociaal&#42;)
* begint met: de waarde begint met de tekst (aka: sociaal&#42;)
* eindigt met: de waarde eindigt met de tekst (alias: &#42;sociaal)
* komt overeen met alle: U kunt meerdere waarden toevoegen die door komma&#39;s van elkaar worden gescheiden. Indien [!UICONTROL starts with], [!UICONTROL ends with], of bevat operatoren die moeten worden toegepast, wordt het jokerteken gebruikt (&#42;)
* groter dan: gebruikt voor numerieke velden of datum-/tijdvelden
* kleiner dan: gebruikt voor numerieke velden of datum-/tijdvelden

**Welk kanaal zullen deze activiteiten bestrijken?**

Zodra de regel Activiteit, en zijn overeenkomstige [!DNL Marketo Measure] De Naam van de campagne, wordt gecreeerd u de Online definities van Kanalen zult gebruiken om die Campagnes onder het correcte Kanaal van de Marketing te plaatsen. [!DNL Marketo Measure] heeft de capaciteit om Kanalen te bepalen gebruikend niet alleen middel en bron, maar ook campagne.

In het voorbeeld hierboven, om de &quot;Uitgaande Vraag {Toegewezen aan}&quot;campagne aan het kanaal BDR toe te wijzen, zult u een rij in uw Online Kanalen CSV voor het kanaal BDR met een campagnedefinitie van &quot;Uitgaande Vraag willen opnemen&#42;&quot; - de asterisk wijst op een vervangingswaarde, zodat zullen alle campagnes die met &quot;Uitgaande Vraag&quot;beginnen onder het kanaal BDR vallen, eerder dan het moeten een afzonderlijke rij voor elke campagnenaam tot stand brengen.
