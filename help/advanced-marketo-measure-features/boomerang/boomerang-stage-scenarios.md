---
unique-page-id: 18874692
description: Boemerang Stage Scenarios - [!DNL Marketo Measure] - Productdocumentatie
title: Boomerang Stage Scenarios
exl-id: 150db070-eef5-4741-845c-775ab4034ead
source-git-commit: 01be819ccee1b3079b15a748480e9dacf6adb488
workflow-type: tm+mt
source-wordcount: '1707'
ht-degree: 0%

---

# Boomerang Stage Scenarios {#boomerang-stage-scenarios}

>[!AVAILABILITY]
>
>De Boomerang-functie wordt alleen ingeschakeld voor Tier 3-klanten. Neem contact op met het Adobe-accountteam (uw accountmanager) als u een hogere accountlaag wilt aanvragen.

Hieronder staan enkele voorbeelden van Boomerang Stage-scenario&#39;s om te begrijpen hoe [!DNL Marketo Measure] in elke situatie aanraakpunten creëren.

## Scenario&#39;s voor één lead {#single-lead-scenarios}

**Scenario 1: Standaard Boomerang-aanraakpunten voor een lead**

Dit is het eenvoudigste Boommeren-scenario. De bovenste regel (met het label Lead 1) geeft de individuele route van Leads weer en de manier waarop hun aanraakpunten in de Lead-record worden weergegeven. De onderste regel (Opportunity genoemd) geeft aan hoe de aanraakpunten van de Leads worden vertaald naar de Opportunity. De voortgang van de aanraakpunten wordt in chronologische volgorde van links naar rechts uitgelegd.

In dit scenario heeft een klant ervoor gekozen om hun **MQL** en **SQL** trappen bijgehouden met Boommeren. Elke boemerang-aanraakpunt positie zal worden geëtiketteerd met het stadium en het aantal waarin het voorkomt (MQL-01, SQL-01, MQL-02.. enz.). Het laatste boemerang-aanraakpunt voor dat werkgebied heeft ook &quot;Last&quot; in de aanraakpuntpositie.

Lood 1 wordt dan omgezet in een Contact met een Kans, die als OC aanraking wordt beschouwd.

![](assets/1-1.png)

**Scenario 2: Boomerang Touchpoints AND Custom Stage for a Lead**

In dit scenario heeft een klant ervoor gekozen alleen de **SQL-stadium** met boemerang-aanraakpunten. MQL- en SAL-fasen worden nog steeds gevolgd, maar met de [!DNL Marketo Measure] Functie Aangepast werkgebied.

![](assets/2-1.png)

U ziet dat de positie van het MQL-aanraakpunt niet met een getal is aangeduid. De reden hiervoor is dat deze optie niet is geselecteerd om te worden bijgehouden met Boomerang-aanraakpunten. Bij het maken van aanraakpunten voor fasen die zijn opgenomen in het aangepaste model, maar die niet worden bijgehouden met Boomerang, [!DNL Marketo Measure] zal het laatste exemplaar uit dat stadium nemen.

In het geval van de SAL-fase: [!DNL Marketo Measure] negeert de eerste twee exemplaren van dit werkgebied. [!DNL Marketo Measure] maakt alleen een SAL-aanraakpunt voor de _last_ voorkomen. In het bovenstaande voorbeeld gebeurt dit vlak voor het aanraakpunt voor OC.

Het SQL-werkgebied wordt bijgehouden met Boomerang-aanraakpunten en er zijn drie aanraakpunten gemaakt en dienovereenkomstig gelabeld.

Lood 1 wordt dan omgezet in een Contact met een Kans, die als OC aanraking wordt beschouwd.

**Scenario 3: Wanneer Leads een werkgebied niet bereiken of overslaan**

In dit scenario worden dezelfde criteria gehanteerd als in scenario 2. Een klant heeft ervoor gekozen het SQL-werkgebied alleen bij te houden met boemerang-aanraakpunten. MQL en SAL worden nog steeds bijgehouden, maar met de [!DNL Marketo Measure] Functie Aangepast werkgebied.

![](assets/3.png)

In dit scenario gaat de lead nooit over naar het SAL-stadium. Het zet in een Contact om alvorens het SAL stadium bereikt, hoofdzakelijk &quot;overslaat&quot;het SAL stadium. In deze situatie [!DNL Marketo Measure] zal veronderstellen dat SAL met OC aanraakpunt voorkomt, en zowel zal de positie van SAL als van OC op het zelfde aanraakpunt verschijnen.

Lood 1 wordt dan omgezet in een Contact met een Kans, die als OC aanraking wordt beschouwd.

## Scenario&#39;s met meerdere leads {#scenarios-with-multiple-leads}

De volgende scenario&#39;s zijn waar de Stages van Boommeren ingewikkelder kunnen worden, aangezien wij bekijken hoe de veelvoudige Loodsen de reis van de Kans kunnen beïnvloeden.

De bovenste regel (met het label Lead 1 in blauw) geeft de individuele route van Leads aan en geeft aan hoe hun aanraakpunten in de Lead-record worden weergegeven. Hetzelfde geldt voor lood 2 (roze) en lood 3 (oranje). In de onderste regel (Opportunity genoemd) wordt weergegeven hoe de aanraakpunten van deze leads zich vertalen naar de Opportunity. De voortgang van de aanraakpunten wordt in chronologische volgorde van links naar rechts uitgelegd.

**Scenario 1:[!UICONTROL Three Leads with Opportunity]**

In dit scenario heeft een klant ervoor gekozen om de **MQL** en **SAL-fasen** met boemerang-aanraakpunten. Het SQL-werkgebied wordt bijgehouden in de standaard aangepaste stadia.

![](assets/4.png)

De FT- en LC-aanraakpunten op de Opportunity zijn afkomstig uit Lead 1 (blauw), omdat ze optraden vóór de FT en LC van Lead 2 (roze). Het LC-aanraakpunt voor lead 2 wordt weergegeven als aanraakpunt voor een formulier op de opportunity.

De MQL-01 (laatste) van lead 2 wordt de eerste MQL op de opportuniteit. De MQL-01 van Lood 1 zal niet als aanraakpunt op de Kans verschijnen omdat Lood 2 MQL eerst voorkwam. Nochtans, zullen leiden 1 MQL-02 en MQL-03 op de Kans verschijnen.

Let op: het SQL-werkgebied wordt bijgehouden met aangepaste stadia en niet met boemerangfasen. Hoewel het SQL-werkgebied drie keer voorkomt tussen regel 1 en regel 2, wordt alleen de laatste SQL-instantie opgenomen als aanraakpunt op de opportunity.

Het SAL-01 (laatste) aanraakpunt van Lood 1 wordt overgedragen als aanraakpunt op de Opportunity. Lood 1 wordt dan omgezet in een Contact met een Kans, die als OC aanraking wordt beschouwd. Aanraakpunt SAL-01 (laatste) van lead 2 wordt gemaakt als aanraakpunt omdat de overgang in dit werkgebied heeft plaatsgevonden _na_ de OC-aanraking.

Hoofd 3&#39;s FT, LC en MQL, SQL, SAL touchpoints (oranje) voorkwamen allen na OC touchpoint op de Opportunity. Deze aanraakpunten worden opgenomen in de Opportunity, maar worden beschouwd als &quot;middelste aanraakpunten&quot;.

Wanneer lood 2 en 3 in Contacten wordt omgezet, [!DNL Marketo Measure] zal geen ander aanraakpunt voor OC creëren omdat er slechts één opportuniteitsaanmaakfase kan zijn.

**Scenario 2 -[!UICONTROL Three Leads with Opportunity]**

In dit scenario heeft een klant ervoor gekozen om de **MQL**, **SQL**, en **SAL** stadia met boemerang-aanraakpunten.

Alle aanraakpunten van regel 1 worden bij de gelegenheid opgenomen, van FT tot SAL-01 (Laatste). Het LC-aanraakpunt van lead 2 wordt opgenomen als een aanraakpunt op formulier tussen de aanraakpunten LC en MQL-01 op de opportunity.

![](assets/5.png)

De MQL-01 (laatste) van Lood 2 is uiteindelijk het MQL-04 (laatste) aanraakpunt op de Opportunity. Omdat in dit scenario wordt gekeken naar de trajecten van meerdere leads binnen één opportunity, kunnen de plaatsing en nummering van de touchpoints van de Leads veranderen wanneer ze worden vertaald als aanraakpunten op de Opportunity. Op dezelfde manier wordt SQL-01 (Laatste) van Lood 2 SQL-04 (Laatste) op de Opp. Lood 2 SAL-01 (Laatste) wordt ook SAL-02 van de Kans (Laatste).

Ook, merk op dat er slechts 2 SAL touchpoints inbegrepen op de Kans zijn. [!DNL Marketo Measure] zal niet proberen aanraakpunten voor werkgebiedovergangen te forceren/maken als deze zich nog niet hebben voorgedaan.

De touchpoint-reis van lead 3 begint net voordat de OC-aanraking plaatsvindt, maar lang nadat Lead 1 en Lead 2 hun FT en LC-aanraking hadden. In dit geval worden FT en LC van lead 3 weergegeven als een aanraakpunt voor formulieren op de Opportunity. Lood 1 wordt dan omgezet in een Contact met een Kans, die als OC aanraking wordt beschouwd.

De aanrakingen MQL, SQL, en SAL van lood 3 komen allen tezelfdertijd voor, na de OC aanraking. Aangezien zij na OC aanraakpunt voorkwamen, zal dit aanraakpunt als Vorm/Midden Aanraking op de Kans eerder dan een Boemerang faseovergang verschijnen.

**Scenario 2a - Web Visit Boomerang Touchpoints**

In dit scenario heeft een klant ervoor gekozen om de **MQL**, **SQL**, en **SAL** stadia met boemerang-aanraakpunten. Dit scenario is vrijwel identiek aan het bovenstaande, met enkele uitzonderingen.

![](assets/6.png)

Alle aanraakpunten van regel 1 worden bij de gelegenheid opgenomen, van FT tot SAL-01 (Laatste). Het LC-aanraakpunt van lead 2 wordt opgenomen als een aanraakpunt op formulier tussen de aanraakpunten LC en MQL-01 op de opportunity.

Hoofd 2&#39;s MQL-01 (Laatste) (Webbezoek) zullen niet als aanraakpunt op Opp worden gecreeerd. Dit is omdat dit aanraakpunt een webbezoek was dat plaatsvond na de laatste keer dat het SQL-werkgebied werd weergegeven en de Opportunity niet vooruit helpt.

Het werkgebied van lead 1 verandert in SAL en wordt vervolgens omgezet in een contactpersoon met een opportunity. in dit geval worden de SAL-01 (laatste) en de OC-positie gecombineerd in hetzelfde aanraakpunt.

De FT,LC-aanraking van lead 3 wordt gemaakt als een aanraakpunt voor formulieren op de Opp. Alleen handelingen voor het invullen van formulieren worden gemaakt als aanraakpunten na de OC-aanraking. Daarom worden de overgangen in het werkgebied SQL-01 (Laatste) en SAL-01 (Laatste) voor regel twee niet gemaakt als aanraakpunten, omdat deze aanraakpunten webbezoeken waren.

De MQL-, SQL- en SAL-aanraakpunten van lead 3 worden als aanraakpunt opgenomen omdat dit een handeling voor het invullen van formulieren was.

**Scenario 3 - Boomerang Attribution Weighting**

In dit scenario heeft een klant ervoor gekozen om de **MQL**, **SQL**, en **SAL** stadia met boemerang-aanraakpunten.

![](assets/7.png)

De FT- en LC-aanraakpunten op de Opportunity zijn afkomstig uit Lead 1 (blauw), omdat ze optraden vóór de FT en LC van Lead 2 (roze). Het LC-aanraakpunt voor lead 2 wordt weergegeven als aanraakpunt voor een formulier op de opportunity.

De MQL-01 (laatste) van lead 2 wordt de eerste MQL op de opportuniteit. De MQL-01 van Lood 1 zal niet als aanraakpunt op de Kans verschijnen omdat Lood 2 MQL eerst voorkwam.

SQL-01 (laatste) van lead 2 wordt SQL-01 bij de Opportunity. SQL-01 op lood 1 zal niet als aanraakpunt op de kans verschijnen omdat SQL-01 op lood 2 eerst gebeurde.

Merk op dat Lood 1 boemerangs tussen MQL en SQL een paar keer alvorens definitief het SAL stadium te bereiken. SQL-01, MQL-02, SQL-02, MQL-03, SQL-03 _niet_ als aanraakpunten aan de gelegenheid worden toegevoegd omdat deze faseovergangen niet helpen om de kans op de reis vooruit te helpen.

Het SAL-01 (Laatste) aanraakpunt van Lood 1 zal het volgende aanraakpunt zijn dat op de Opp moet worden opgenomen. Lood 1 zet dan in een contact met een kans om, creërend OC touchpoint.

Hoofd 3&#39;s FT en LC, en het aanraakpunt MQL, SQL en SAL, zullen als vormaanrakingen op de Kans verschijnen.

SQL-01 (laatste)-aanraakpunt van lead 2 wordt niet opgenomen als aanraakpunt op de opp omdat dit na het aanraakpunt voor OC is opgetreden. Bovendien is de SQL-werkgebiedovergang van lead 2 opgetreden _na de laatste SAL-faseovergang_ en helpt niet de opportuniteitsreis vooruit te helpen.

## Opportunity-scenario&#39;s {#opportunity-scenarios}

**Scenario 1 - Contacten met Opportunity en Boommeren het Volgen**

In dit scenario heeft een klant ervoor gekozen om de **Overgangen in de fase van demo- en onderhandeling** op de **Contact**. Elk boemerangstadium kan maximaal twee aanraakpunten ontvangen. Het verschil tussen werkgebiedovergangen bij een contactpersoon en werkgebiedovergangen bij een lead is dat overgangen in het contactgebied kunnen worden weergegeven als Boomerang-aanraakpunten bij de opportunity _na_ het aanraakpunt van de OC. Dit geldt niet voor overgangen in het werkgebied die zich voordoen op de lead, aangezien deze als touchpoint Form worden weergegeven.

![](assets/8.png)

In dit voorbeeld worden de overgangen in de Stage van de Demo en de Onderhandeling van Contact 1 opgenomen als Demo-01- en onderhandelingsaanraakpunten op de Opportunity. De overgang van het demodium van contact 2 komt voor _na_ Contact 1 s, en verschijnt als (Laatste) aanraakpunt demo-02 op de Kans.

Merk op dat er geen tweede overgang naar de onderhandelingsfase is; De Kans springt onmiddellijk van demo-02 (Laatste) bewegingen aan Close Won. In dit geval: [!DNL Marketo Measure] De overgang naar onderhandelingen met het &quot;Closed Won&quot;-aanraakpunt.
