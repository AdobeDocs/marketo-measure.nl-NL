---
unique-page-id: 18874704
description: veelgestelde vragen over activiteitenkenmerken - [!DNL Marketo Measure]
title: Veelgestelde vragen over activiteitenkenmerk
exl-id: 6272024f-b6ae-4aa7-ba92-c9f183549614
feature: Attribution
source-git-commit: 741ab20845de2f3bcde589291d7446a5b4f877d8
workflow-type: tm+mt
source-wordcount: '744'
ht-degree: 0%

---

# Veelgestelde vragen over activiteitenkenmerk {#activities-attribution-faq}

[!DNL Marketo Measure] Met Activiteiten importeert u al uw activiteitenoverzichten en genereert u aanraakpunten voor deze activiteiten, zodat deze activiteiten een toewijzingskrediet krijgen. Het meest gebruikelijke gebruik is het volgen van Activiteiten van het team van de Verkoop, aangezien zij algemeen een verslag van telefoongesprekken of e-mails tot stand brengen die naar vooruitzichten worden verzonden. Andere unieke dingen die kunnen worden bijgehouden, zijn inhoudsinteracties zoals het downloaden van elementen of videoweergaven.

**Hoe is dit anders dan offline campagnes?**

Het grootste verschil is dat campagnes slechts één aanraakpunt kunnen bieden, omdat campagnes slechts één campagnelid toestaan voor elke leider of contactpersoon. Dat betekent u terugkomende gebeurtenissen zoals uitgaande vraag of demo&#39;s of webinar aanwezigen kunt niet volgen, tenzij u individuele Campagnes voor elke groepering creeert. Met activiteiten kunt u elke gebeurtenis meten.

**Is er een verschil tussen Taak, Gebeurtenissen, en Activiteiten?**

Het object Activity fungeert als paraplu, of bovenliggend element, voor de objecten Task en Event. De activiteiten betreffen hoofdzakelijk zowel Taken als Gebeurtenissen. Taken worden doorgaans gebruikt om snel eenmalige items op te nemen, zoals een telefoongesprek of een e-mailbericht. Gebeurtenissen worden doorgaans gebruikt voor dingen die een begin- of einddatum kunnen hebben, zoals vergaderingen of conferenties.

**Als ik een lead of contactpersoon met dezelfde terugkerende taak heb, zal ik dan de aanraakpunten voor kopers voor al deze aanspreekpunten zien?**

Ja. Er bestaat een 1:1-relatie tussen uw gesynchroniseerde activiteiten en gemaakte aanraakpunten.

**Hoe weet ik welke records ertoe leiden dat aanraakpunten worden gemaakt?**

Een goede suggestie is om eerst uw filters in te stellen met behulp van het object Activity in uw CRM. Gebaseerd op de filterregels, geeft dit u een goed idee over hoeveel verslagen onder die criteria vallen, dan kunt u het verfijnen zoals nodig. Dit is niet nodig, maar een nuttige manier voor gebruikers om te begrijpen hoeveel Activiteiten Touchpoints zullen worden gecreeerd zodra de Activiteitenregels zijn opgezet.

**Wat is de [!DNL Marketo Measure] Naam campagne?**

Aangezien deze activiteiten resulteren in een aanraakpunt, [!DNL Marketo Measure] moet weten tot welk kanaal en subkanaal zij behoren. Voor elke regel moet u een [!DNL Marketo Measure] Naam campagne. Nadat dat wordt gecreeerd, gebruik online CSV van Kanalen om in kaart te brengen dat [!DNL Marketo Measure] Campagnenaam aan zijn aangewezen Kanaal. De [!DNL Marketo Measure] De naam van de campagne verschijnt ook op het Aanraakpunt zelf binnen [!UICONTROL Ad Campaign Name] veld.

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

**Wat als ik een verschillende regel voor elke Verkoper moet creëren? Moet ik een andere functie maken [!DNL Marketo Measure] Campagne voor elk?**

Nee, dat doe je niet. Met de optie Dynamische campagnemenamen kunt u (een deel van) de [!DNL Marketo Measure] Campagnenaam die een &quot;vervangingsparameter&quot;gebruikt die een gebied van het voorwerp van de Activiteit van verwijzingen voorziet. Als u bijvoorbeeld een [!DNL Marketo Measure] De Naam van de campagne getiteld &quot;Uitgaande Vraag&quot;maar u wilt de Verkoop aan het eind zijn, neemt de het gebiedsnaam van CRM en roept [!DNL Marketo Measure] De naam van de campagne &quot;Uitgaande Vraag {AssignedTo}&quot; of &quot;Uitgaande Vraag {CreatedBy}.&quot;

**Hoe kan ik Activiteiten instellen in het dialoogvenster [!DNL Marketo Measure] app?**

Richtingen voor het configureren van activiteiten binnen de [!UICONTROL Marketo] De maatstoepassing vindt u in het dialoogvenster [!DNL Marketo Measure] Activiteiten ondersteunen artikel.

**Wat betekenen de verschillende operatoren?**

* is gelijk aan: exact overeenkomend met de waarde (ook bekend als: social)
* bevat : de tekst staat in het midden ( ook bekend als : &#42;sociaal&#42;)
* begint met: de waarde begint met de tekst (ook bekend als: social&#42;)
* eindigt met: de waarde eindigt met de tekst (alias: &#42;sociaal)
* komt overeen met een willekeurige waarde: er kunnen meerdere waarden worden toegevoegd die door komma&#39;s van elkaar worden gescheiden. Indien [!UICONTROL starts with], [!UICONTROL ends with], of bevat operatoren moet worden toegepast, gebruikt u het jokerteken (&#42;)
* groter dan: wordt gebruikt voor numerieke velden of datum-/tijdvelden
* kleiner dan: gebruikt voor numerieke velden of datum-/tijdvelden

**Welk kanaal vallen deze activiteiten onder?**

Wanneer de regel Activiteit en zijn overeenkomstige [!DNL Marketo Measure] De Naam van de campagne wordt gecreeerd, gebruik de Online definities van Kanalen om die Campagnes onder het correcte Kanaal van de Marketing te plaatsen. [!DNL Marketo Measure] U kunt kanalen definiëren met niet alleen medium en bron, maar ook campagne.

In het voorbeeld hierboven, om de &quot;Uitgaande Vraag {Toegewezen aan}&quot;campagne aan het kanaal BDR toe te wijzen, neem een rij in uw Online Kanalen CSV voor het kanaal BDR met een campagnedefinitie van &quot;Uitgaande Vraag op&#42;&quot; - de asterisk wijst op een vervangingswaarde, zodat zullen alle campagnes die met &quot;Uitgaande Vraag&quot;beginnen onder het kanaal BDR vallen, eerder dan het moeten een afzonderlijke rij voor elke campagnenaam tot stand brengen.
