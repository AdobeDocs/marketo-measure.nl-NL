---
unique-page-id: 18874775
description: Veelgestelde vragen over het leermodel voor machines - [!DNL Marketo Measure]
title: Veelgestelde vragen over het leermodel voor machines
exl-id: 2fc142b2-8ac4-4c48-a8f1-398e29ccfe97
feature: Custom Models
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 0%

---

# Veelgestelde vragen over het leermodel voor machines {#machine-learning-model-faq}

De [!DNL Marketo Measure] Het leermodel van de machine gebruikt uw aanraakpuntgegevens om te berekenen hoeveel attributieweging aan elk stadium zou moeten worden toegewezen. Dit wordt bepaald door hoe belangrijk elke fase was in het sluiten van de rijafspraken.

Wat vertellen de toewijzingspercentages van het Machine Learning Model me over elk stadium?

De toewijzingspercentages van elke fase weerspiegelen de potentiële impact van uw marketinginspanningen. Een hoger percentage betekent dat het in de handel brengen de beweging van de trechter op dat punt rechtstreeks kan beïnvloeden. Een lager toewijzingspercentage betekent dat de stadia voor uw team minder belangrijk zijn om te controleren.

Hoe wordt het leermodel van de Machine berekend?

[!DNL Marketo Measure] berekent het belang van elke aangepaste fase met behulp van de aanraakpuntgegevens van uw account. De criteria om het belang van elke fase te bepalen zijn:

* Model Accuracy: Als we een voorspellend model bouwen met de aanraakpuntgegevens om te voorspellen of we uiteindelijk een deal zullen winnen, hoe nauwkeurig zal het model zijn? Hogere voorspellende nauwkeurigheid betekent dat de details van dit stadium meer correleren met of een overeenkomst zal sluiten
* Conversietarief: als Leads of Opportunity in dit stadium in een hoog tempo naar de volgende fase converteren, geeft dit aan dat de marketingactiviteiten die in dit stadium hebben plaatsgevonden, niet erg belangrijk waren. Omgekeerd kan, als een bepaalde fase in een laag tempo naar de volgende fase wordt omgeschakeld, dit erop wijzen dat de marketingactiviteiten die in deze fase hebben plaatsgevonden, van invloed waren op het sturen van de conversie.
* Uniquisitiegewicht aanraakpunt: als een werkgebied optreedt als een stand-alone overgang, wat betekent dat er geen andere werkgebiedovergangen zijn die tegelijkertijd hebben plaatsgevonden, kan dit werkgebied een hoger toewijzingsgewicht krijgen. Wanneer daarentegen een aanraakpunt voor een werkgebied wordt gedeeld met andere stadia (het aanraakpunt deelt bijvoorbeeld de fasen First Touch, Lead Conversion en Opportunity Conversion), kan dit werkgebied een lagere toewijzingsweging krijgen.

Het uiteindelijke gewicht van een aangepaste fase wordt als volgt berekend:

**_Model Percentage = Model Accuracy x Conversion Rate x Touchpoint Uniqueness Weight_**

Uiteindelijk worden alle aangepaste werkgebiedgewichten genormaliseerd en omgezet in %, zoals hieronder wordt weergegeven.

Waarom zie ik geen aantallen in de het Leren van de Machine kolom?

Wanneer het aangepaste kenmerkingsmodel is ingeschakeld voor uw account, duurt het meestal 3 tot 7 dagen voordat ons model deze nummers uitvoert en bouwt, op basis van uw historische gegevens.

Hoe vaak wordt het leermodel van de Machine bijgewerkt?

We voeren het model om de zeven dagen opnieuw uit.

Waarom stelt het model altijd Midden-aanrakingen in op 10%?

Het toewijzen van 10% toewijzingskrediet aan Middle Touches is een standaardinstelling voor al onze attributiemodellen.

Wanneer moet ik mijn attributiedistributie wijzigen?

Neem contact op met uw accountmanager om de gevolgen van het wijzigen van de toewijzingspercentages te bespreken, en welke stappen u wilt opnemen in uw aangepaste model. Elk [!DNL Salesforce] en het verkoopproces is uniek, en wij willen ervoor zorgen dat uw douanemodel correct wordt gemodelleerd.

Dit gezegd hebbende, hebben wij enkele algemene tendensen over onze klanten geïdentificeerd:

Eén trend die we hebben opgemerkt, is dat het niet altijd nuttig is om meer stadia in je model op te nemen. Wanneer klanten bijvoorbeeld meerdere opportuniteitsfasen hebben toegevoegd aan de onderkant van de trechter, krijgen deze fasen meestal een zeer laag toewijzingspercentage. Lage percentagewaarden wijzen op een hoge omzettingssnelheid, wat typisch betekent dat deze stadia niet zo nadelig zijn bij het drijven van overeenkomsten om te sluiten. Sommige klanten besluiten uiteindelijk om deze stadia niet in de trechter op te nemen. Als u besluit een werkgebied te verwijderen uit het toewijzingsmodel, worden de percentages opnieuw berekend en verdeeld.

We hebben ook gemerkt dat er een hoge conversiesnelheid is van &#39;Lead Creation&#39; naar &#39;Marketing Qualified phase&#39; (gekwalificeerd voor marketing). Hierdoor kan de toewijzingscoëfficiënt voor het stadium &#39;Marketing Qualified&#39; lager zijn. Afhankelijk van uw bedrijfs en verkoopcyclus, kan het nuttig zijn om dit stadium uit het douanemodel te verwijderen.

Houd er rekening mee dat als u marketingactiviteiten wilt bijhouden via een specifieke overgangsfase, maar u niet wilt dat dit stadium toekent aan creditering, u dit stadium in uw model kunt opnemen en een toewijzingkrediet van 0% aan dat stadium wilt toewijzen.
