---
description: Activiteiten Algemene richtlijnen voor veelgestelde vragen voor Marketo Measure-gebruikers
title: Veelgestelde vragen over activiteitenkenmerk
exl-id: 6272024f-b6ae-4aa7-ba92-c9f183549614
feature: Attribution
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '744'
ht-degree: 0%

---

# Veelgestelde vragen over activiteitenkenmerk {#activities-attribution-faq}

[!DNL Marketo Measure] Met Activiteiten importeert u al uw activiteitsgegevens en genereert u aanraakpunten voor deze Activiteiten, zodat deze Activiteiten toewijzingskredieten krijgen. Het meest gebruikelijke gebruik is het volgen van Activiteiten van het team van de Verkoop, aangezien zij algemeen een verslag van telefoongesprekken of e-mails tot stand brengen die naar vooruitzichten worden verzonden. Andere unieke dingen die kunnen worden bijgehouden, zijn inhoudsinteracties zoals het downloaden van elementen of videoweergaven.

**hoe is dit verschillend van Off-line Campagnes?**

Het grootste verschil is dat campagnes slechts één aanraakpunt kunnen bieden, omdat campagnes slechts één campagnelid toestaan voor elke leider of contactpersoon. Dat betekent u terugkomende gebeurtenissen zoals uitgaande vraag of demo&#39;s of webinar aanwezigen kunt niet volgen, tenzij u individuele Campagnes voor elke groepering creeert. Met activiteiten kunt u elke gebeurtenis meten.

**is er een verschil tussen Taak, Gebeurtenissen, en Activiteiten?**

Het object Activity fungeert als paraplu, of bovenliggend element, voor de objecten Task en Event. De activiteiten betreffen hoofdzakelijk zowel Taken als Gebeurtenissen. Taken worden doorgaans gebruikt om snel eenmalige items op te nemen, zoals een telefoongesprek of een e-mailbericht. Gebeurtenissen worden doorgaans gebruikt voor dingen die een begin- of einddatum kunnen hebben, zoals vergaderingen of conferenties.

**als ik een Lood of Contact met de zelfde terugkomende Taak heb, zal ik de Touchpoints van de Koper voor elk van die zien?**

Ja. Er is een 1 :1 verhouding tussen uw gesynchroniseerde Activiteiten en gecreeerde Aanraakpunten.

**hoe ik weet welke verslagen in Touchpoints resulteren die worden gecreeerd?**

Een goede suggestie is om eerst uw filters in te stellen met behulp van het object Activity in uw CRM. Gebaseerd op de filterregels, geeft dit u een goed idee over hoeveel verslagen onder die criteria vallen, dan kunt u het verfijnen zoals nodig. Dit is niet nodig, maar een nuttige manier voor gebruikers om te begrijpen hoeveel Activiteiten Touchpoints zullen worden gecreeerd zodra de Activiteitenregels zijn opgezet.

**wat is de [!DNL Marketo Measure] Naam van de Campagne?**

Aangezien deze activiteiten resulteren in een aanraakpunt, moet [!DNL Marketo Measure] weten tot welk kanaal en subkanaal ze behoren. Voor elke regel moet u een [!DNL Marketo Measure] campagnenaam opgeven. Nadat dat wordt gecreeerd, gebruik online CSV van Kanalen om die [!DNL Marketo Measure] Naam van de Campagne aan zijn aangewezen Kanaal in kaart te brengen. De naam van de campagne [!DNL Marketo Measure] wordt ook weergegeven op het aanraakpunt zelf in het veld [!UICONTROL Ad Campaign Name] .

**Welke andere gebieden van het Aanraakpunt worden bevolkt?**

| **Gebied van het Aanraakpunt** | **Waarde** |
|---|---|
| Lead/contactpersoon | Alle activiteiten hebben betrekking op een lead of contactpersoon |
| Campaign | Kanaal.Subkanaal [[!DNL Marketo Measure]] |
| Aanraakpunt Source | CRM-activiteit |
| Medium | Activity.Type |
| Type aanraakpunt | Activity.Type |
| Naam advertentiecampagne | [!DNL Marketo Measure] Campagnenaam |
| Inhoud toevoegen | Activiteitenonderwerp |
| Advertentie-id | Externe id activiteit |
| Aanraakpuntdatum | [ douane - reeks in apps ] |

**wat als ik een verschillende regel voor elke Vertegenwoordiger moet tot stand brengen? Moet ik verschillende [!DNL Marketo Measure] Campagne voor elk creëren?**

Nee, dat doe je niet. Met &#39;Dynamische campagnemenamen&#39; kunt u een deel (of alles) van de naam van de [!DNL Marketo Measure] -campagne invullen met een &#39;vervangingsparameter&#39; die verwijst naar een veld van het object Activity. Bijvoorbeeld, als u een [!DNL Marketo Measure] Naam van de Campagne &quot;Uitgaande Vraag&quot;hebt maar u de Verkoper aan het eind wilt zijn, neem de het gebiedsnaam van CRM en roep [!DNL Marketo Measure] de Naam van de Campagne &quot;Uitgaande Vraag {AssignedTo}&quot;of &quot;Uitgaande Vraag {CreatedBy}.&quot;

**hoe stel ik Activiteiten in [!DNL Marketo Measure] app?**

Informatie over het configureren van activiteiten in de [!UICONTROL Marketo] Meetlat-app vindt u in het [!DNL Marketo Measure] Ondersteuning voor activiteiten-artikel.

**wat betekenen de verschillende exploitanten?**

* is gelijk aan: exact overeenkomend met de waarde (ook bekend als: social)
* bevat: de tekst is in het midden (alias: &#42; sociaal &#42;)
* begint met: de waarde begint met de tekst (ook bekend als: social&#42;)
* eindigt met: de waarde eindigt met de tekst (ook bekend als: &#42; social)
* komt overeen met een willekeurige waarde: er kunnen meerdere waarden worden toegevoegd die door komma&#39;s van elkaar worden gescheiden. Als [!UICONTROL starts with] , [!UICONTROL ends with], of bevat operatoren moeten worden toegepast, gebruikt u het jokerteken (&#42;)
* groter dan: wordt gebruikt voor numerieke velden of datum-/tijdvelden
* kleiner dan: gebruikt voor numerieke velden of datum-/tijdvelden

**Welk Kanaal deze Activiteiten onder gaan?**

Wanneer de regel Activiteit en zijn overeenkomstige [!DNL Marketo Measure] Naam van de Campagne worden gecreeerd, gebruik de Online definities van Kanalen om die Campagnes onder het correcte Kanaal van de Marketing te plaatsen. Met [!DNL Marketo Measure] kunt u kanalen definiëren met behulp van niet alleen medium en bron, maar ook campagne.

In het voorbeeld hierboven, om de &quot;Uitgaande Vraag {Assigned To}&quot;campagne aan het kanaal toe te wijzen BDR, neem een rij in uw Online Kanalen CSV voor het kanaal BDR met een campagnedefinitie van &quot;Uitgaande Vraag &#42;&quot;op - de asterisk wijst een vervangingswaarde aan, zodat zullen alle campagnes die met &quot;Uitgaande Vraag&quot;beginnen onder het kanaal BDR vallen, eerder dan het moeten een afzonderlijke rij voor elke campagnaam tot stand brengen.
