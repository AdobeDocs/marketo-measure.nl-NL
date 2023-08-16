---
unique-page-id: 42762648
description: Documentatie van het dashboard van de Reis van de Cohort - [!DNL Marketo Measure] - Productdocumentatie
title: Documentatie van Cohort Reisdashboard
exl-id: b139f720-86ae-4f6d-9dfc-cc67b4186f88
feature: Reporting
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 0%

---

# Documentatie van Cohort Reisdashboard {#cohort-journey-dashboard-documentation}

Met de dashboards Cohort Impact en Funnel kunnen Marketers de voortgang van een startcohortfase voor een geselecteerd tijdframe bekijken en de conversiesnelheid meten.

Het belangrijkste verschil is hoe we elke entiteit tellen van de cohortfase.

* Cohort Funnel: het resultaat van elke fase is rechtstreeks afgeleid van de vorige fase.

   * Alleen records die na de ingestelde begintijd van de cohort door elke fase naar beneden zijn gegaan, worden geteld.

![](assets/cohort-journey-dashboard-documentation-1.png)

* Cohorteffect: het resultaat van elke fase is afgeleid van de cohortfase, niet van de voorafgaande fase.

   * Alle records in elk werkgebied worden meegeteld zolang ze na de ingestelde begintijd van het cohort zijn gemaakt. Dit dashboard zal natuurlijk meer records hebben dan het dashboard van de Trechter, omdat we bekijken hoe de entiteiten beïnvloed werden vanuit de cohortfase, niet alleen de beweging door de trechter.

![](assets/cohort-journey-dashboard-documentation-2.png)

Elk dashboard heeft twee tegels:

* Cohort Revenue: De totale opportuniteit komt voort uit alle mogelijkheden in de fase van de transacties van de Cohort Reistiel.
* Cohort Journey: De overgang naar elke fase van de reis vanaf het begin van de cohortfase voor een geselecteerd tijdkader.

>[!NOTE]
>
>Op alle Discover-dashboards kan slechts één persoonlijk object, Lead of Contact, worden gerapporteerd. Deze is ingesteld in [!UICONTROL Settings] > [!UICONTROL Reporting] > [!UICONTROL Attribution Settings] > [!UICONTROL Default Dashboard Object].

De dashboards steunen de volgende filters:

* Cohortwerkgebied: selecteer het beginstadium van het cohort. De verslagen in alle volgende stadia worden geëvolueerd van de verslagen in het cohortstadium.
* Datumbereik van kleur: selecteer het tijdkader voor het geselecteerde codewerkgebied. Samen met Cohort Stage definieert het de eerste gegevensset.
* Afsnijddatum: selecteer de datum waarop de recordprogressie in alle volgende fasen moet plaatsvinden. Wordt standaard ingesteld op vandaag. Dit geldt voor alle stadia behalve het cohortstadium.
* Kanaal: filtert de records via kanalen. Een record is gekoppeld aan een kanaal als een van de aanraakpunten aan het kanaal is gekoppeld.
* Subkanaal: filter de records op subkanalen. Een record is gekoppeld aan een subkanaal als een van de aanraakpunten ervan is gekoppeld aan het subkanaal.
* Campagne: filter de records door campagnes. Een record is gekoppeld aan een campagne als een van de aanraakpunten aan de campagne is gekoppeld.
* Bron campagne: filter de verslagen door campagnebronnen. Voorbeelden van campagnebronnen zijn [!DNL Adwords], [!DNL BingAds], [!DNL Facebook], [!DNL LinkedIn], enz. Een record wordt gekoppeld aan een campagnebron als een van de aanraakpunten aan de campagnebron is gekoppeld.
* Segmentfilters: filtert de records op aangepaste segmenten. Een record is gekoppeld aan een segment als een van de aanraakpunten ervan aan het segment is gekoppeld.

Voor alle filters wordt de logica &quot;AND&quot; gebruikt.

>[!NOTE]
>
>Segmentfilters zijn alleen van toepassing op LC-werkgebied en erna. Als Cohort Stage onbekend of bekend is en een van de segmentfilters een waarde heeft, retourneert het dashboard geen resultaten.

De stadia omvatten Onbekend, Bekend, LC, geselecteerde stadia van de Trechter in Open Lood/ContactStages (Montages > CRM > de Afbeelding van het Stadium), OC, geselecteerde stadia van de Trechter in de Stages van de Kanaal van de Open (Montages > CRM > de Afbeelding van het Stadium), en Overeenkomsten (Gesloten Kansen van de Won).

>[!NOTE]
>
>Het aantal records voor een reisfase, gedefinieerd als een ander stadium dan het cohortstadium, omvat alle nieuwe records die betrekking hebben op de cohortrecords en die worden gemaakt na de begindatum van het geselecteerde tijdkader en vóór de afkapdatum. Dit is afgeleid oorzakelijk.

U kunt vanaf elke balk omlaag boren om de records voor elk werkgebied weer te geven.

* Voor Onbekend worden anonieme bezoekersgegevens weergegeven.
* Voor Bekende, toont het bekende bezoekersdetails.
* Voor de fasen LC en Open Lead/Contact worden de gegevens van de Lead/van het Contact weergegeven.
* Voor OC, Open stadia van de Kans, en Overeenkomsten, toont het de details van de Kans.
