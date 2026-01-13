---
description: Boomerang Stage Scenarios -  [!DNL Marketo Measure]
title: Boomerang Stage Scenarios
exl-id: 150db070-eef5-4741-845c-775ab4034ead
feature: Boomerang
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '1876'
ht-degree: 0%

---


# Boomerang Stage Scenarios {#boomerang-stage-scenarios}

>[!AVAILABILITY]
>De functie Boomerang is alleen ingeschakeld voor klanten van Tier 2 en 3. Neem contact op met het Adobe-accountteam (uw accountmanager) als u een hogere accountlaag wilt aanvragen.

Hieronder volgen een paar voorbeelden van Boomerang-werkgebiedscenario&#39;s om te begrijpen hoe [!DNL Marketo Measure] aanraakpunten in elke situatie maakt.

## Scenario&#39;s voor één lead {#single-lead-scenarios}

**Scenario 1: Standaard Boomerang Touchpoints voor een Lood**

Dit is het eenvoudigste Boommeren-scenario. De bovenste regel (met het label Lead 1) geeft de individuele route van Leads weer en de manier waarop hun aanraakpunten in de Lead-record worden weergegeven. De onderste regel (Opportunity genoemd) geeft aan hoe de aanraakpunten van de Leads worden vertaald naar de Opportunity. De voortgang van aanraakpunten wordt in chronologische volgorde van links naar rechts uitgelegd.

In dit scenario, heeft een klant ervoor gekozen om hun **MQL** en **SQL** stadia te hebben die met Boommeren worden gevolgd. Elke boemerang-aanraakpunt positie wordt geëtiketteerd met het stadium en het aantal waarin het voorkomt (MQL-01, SQL-01, MQL-02). Het laatste boemerang-aanraakpunt voor dat werkgebied heeft &quot;(Laatste)&quot; in de positie van het aanraakpunt.

Lood 1 wordt dan omgezet in een Contact met een Kans, die als OC aanraking wordt beschouwd.

![&#x200B; Loodreisdiagram dat MQL en SQL boemerang touchpoints met chronologische progressie aan Kans toont &#x200B;](assets/1-1.png)

**Scenario 2: Boomerang Touchpoints EN de Staven van de Douane voor een Lood**

In dit scenario, heeft een klant ervoor gekozen slechts om het **SQL stadium** met boemerang te volgen aanraakpunten. De fasen MQL en SAL worden nog steeds bijgehouden, maar met de functie Aangepast werkgebied van [!DNL Marketo Measure] .

![&#x200B; Loodreis die SQL boemerang touchpoints met MQL en SAL toont die als douanestadia worden gevolgd &#x200B;](assets/2-1.png)

U ziet dat de positie van het MQL-aanraakpunt niet met een getal is aangeduid. De reden hiervoor is dat deze optie niet is geselecteerd om te worden bijgehouden met Boomerang-aanraakpunten. Wanneer u aanraakpunten maakt voor stadia die zijn opgenomen in het aangepaste model, maar niet worden bijgehouden met Boommeren, neemt [!DNL Marketo Measure] de laatste instantie van dat werkgebied.

Voor het SAL-werkgebied negeert [!DNL Marketo Measure] de eerste twee instanties van dit werkgebied. [!DNL Marketo Measure] leidt slechts tot een SAL touchpoint voor het _laatste_ voorkomen. In het bovenstaande voorbeeld gebeurt dit vlak voor het aanraakpunt voor OC.

Het SQL-werkgebied wordt bijgehouden met Boomerang-aanraakpunten en er zijn drie aanraakpunten gemaakt en dienovereenkomstig gelabeld.

Lood 1 wordt dan omgezet in een Contact met een Kans, die als OC aanraking wordt beschouwd.

**Scenario 3: Wanneer leiden niet bereiken/overslaan een stadium**

In dit scenario worden dezelfde criteria gehanteerd als in scenario 2. Een klant heeft ervoor gekozen het SQL-werkgebied alleen bij te houden met boemerang-aanraakpunten. MQL en SAL worden nog steeds bijgehouden, maar met de functie Aangepast werkgebied van [!DNL Marketo Measure] .

![&#x200B; de reis die van het lood het overgeslagen stadium van SAL met SAL en OC posities toont die in zelfde touchpoint worden gecombineerd &#x200B;](assets/3.png)

In dit scenario gaat de lead nooit over naar het SAL-stadium. Het zet in een Contact om alvorens het SAL stadium bereikt, hoofdzakelijk &quot;overslaat&quot;het SAL stadium. In deze situatie, veronderstelt [!DNL Marketo Measure] dat SAL met OC aanraakpunt voorkomt, en zowel zal de positie van SAL als van OC op het zelfde aanraakpunt verschijnen.

Lood 1 wordt dan omgezet in een Contact met een Kans, die als OC aanraking wordt beschouwd.

## Scenario&#39;s met meerdere leads {#scenarios-with-multiple-leads}

De volgende scenario&#39;s zijn waar de Stages van Boommeren ingewikkelder kunnen worden, aangezien wij bekijken hoe de veelvoudige Loodsen de reis van de Kans kunnen beïnvloeden.

De bovenste regel (met het label Lead 1 in blauw) geeft de individuele route van Leads aan en geeft aan hoe hun aanraakpunten in de Lead-record worden weergegeven. Hetzelfde geldt voor lood 2 (roze) en lood 3 (oranje). In de onderste regel (Opportunity genoemd) wordt weergegeven hoe de aanraakpunten van deze leads zich vertalen naar de Opportunity. De voortgang van aanraakpunten wordt in chronologische volgorde van links naar rechts uitgelegd.

**Scenario 1:[!UICONTROL Three Leads with Opportunity]**

In dit scenario, heeft een klant verkiezen om de **MQL** en **stadia van de VAL** met boemerang te volgen aanraakpunten. Het SQL-werkgebied wordt bijgehouden in de standaard aangepaste stadia.

![&#x200B; Drie loodreisdiagram die MQL en SAL boemerang touchpoints tonen die aan Kans &#x200B;](assets/4.png) vertalen

De FT- en LC-aanraakpunten op de Opportunity zijn afkomstig van Lead 1 (blauw), omdat ze optraden vóór de FT en LC van Lead 2 (roze). Het LC-aanraakpunt voor lead 2 wordt weergegeven als aanraakpunt voor een formulier op de opportunity.

De MQL-01 (laatste) van lead 2 wordt de eerste MQL op de opportuniteit. De MQL-01 van Lood 1 zal niet als aanraakpunt op de Kans verschijnen omdat Lood 2 MQL eerst voorkwam. Nochtans, zullen leiden 1 MQL-02 en MQL-03 op de Kans verschijnen.

Het SQL-werkgebied wordt bijgehouden met aangepaste stadia en niet met boemerangfasen. Hoewel het SQL-werkgebied drie keer voorkomt tussen regel 1 en regel 2, wordt alleen de laatste SQL-instantie opgenomen als aanraakpunt op de opportunity.

Het SAL-01 (laatste) aanraakpunt van Lood 1 wordt overgedragen als aanraakpunt op de Opportunity. Lood 1 wordt dan omgezet in een Contact met een Kans, die als OC aanraking wordt beschouwd. Lood 2 (laatste) zal aanraakpunt SAL-01 niet als aanraakpunt worden gecreeerd omdat deze werkgebiedovergang _na_ de OC aanraking voorkwam.

Hoofd 3&#39;s FT, LC en MQL, SQL, SAL touchpoints (oranje) voorkwamen allen na OC touchpoint op de Opportunity. Deze aanraakpunten worden opgenomen in de Opportunity, maar worden beschouwd als &#39;middelste aanraakpunten&#39;.

Als lead 2 en 3 worden omgezet in contact, maakt [!DNL Marketo Measure] geen ander OC-aanraakpunt omdat er maar één aanmaakfase voor de mogelijkheid kan zijn.

**Scenario 2 -[!UICONTROL Three Leads with Opportunity]**

In dit scenario, heeft een klant ervoor gekozen om **MQL**, **SQL**, en **SAL** stadia met boemerang te volgen aanraakpunten.

Alle aanraakpunten van Lead 1 worden bij de gelegenheid opgenomen, van FT tot SAL-01 (Laatste). Het LC-aanraakpunt van lead 2 wordt opgenomen als een aanraakpunt op formulier tussen de aanraakpunten LC en MQL-01 op de opportunity.

![&#x200B; Drie belangrijke reis die MQL, SQL, en SAL boemerang touchpoints met positie nummering op Kans &#x200B;](assets/5.png) tonen

De MQL-01 (laatste) van Lood 2 is uiteindelijk het MQL-04 (laatste) aanraakpunt op de Opportunity. Omdat in dit scenario wordt gekeken naar de trajecten van meerdere leads binnen één opportunity, kunnen de plaatsing en nummering van de touchpoints van de Leads veranderen wanneer ze worden vertaald als aanraakpunten op de Opportunity. Op dezelfde manier wordt SQL-01 (Laatste) van Lood 2 SQL-04 (Laatste) op de Opp. Lood 2 SAL-01 (Laatste) wordt ook SAL-02 van de Kans (Laatste).

Er zijn slechts twee SAL-aanraakpunten opgenomen op de Opportunity. [!DNL Marketo Measure] probeert geen aanraakpunten voor werkgebiedovergangen te forceren/maken als deze niet zijn opgetreden.

De touchpoint-reis van lead 3 begint net voordat de OC-aanraking plaatsvindt, maar lang nadat Lead 1 en Lead 2 hun FT en LC-aanraking hadden. In dit geval worden FT en LC van lead 3 weergegeven als een aanraakpunt voor formulieren op de Opportunity. Lood 1 wordt dan omgezet in een Contact met een Kans, die als OC aanraking wordt beschouwd.

De aanrakingen MQL, SQL, en SAL van lood 3 komen allen tezelfdertijd voor, na de OC aanraking. Aangezien ze zich na het aanraakpunt OC hebben voorgedaan, wordt dit aanraakpunt weergegeven als een Form/Middle Touch op Opportunity in in plaats van als een Boomerang-werkgebiedovergang.

**Scenario 2a - het Bezoek van het Web Boemerang Touchpoints**

In dit scenario, heeft een klant ervoor gekozen om **MQL**, **SQL**, en **SAL** stadia met boemerang te volgen aanraakpunten. Dit scenario is vrijwel identiek aan het bovenstaande scenario, met enkele uitzonderingen.

![&#x200B; Drie belangrijke reis die van het Webbezoek boemerang touchpoints tonen die van Kans worden uitgesloten wanneer voorkomen na SQL stadium &#x200B;](assets/6.png)

Alle aanraakpunten van regel 1 worden bij de gelegenheid opgenomen, van FT tot SAL-01 (Laatste). Het LC-aanraakpunt van lead 2 wordt opgenomen als een aanraakpunt op formulier tussen de aanraakpunten LC en MQL-01 op de opportunity.

Hoofd 2&#39;s MQL-01 (Laatste) (Webbezoek) zullen niet als aanraakpunt op Opp worden gecreeerd. Dit is omdat dit aanraakpunt een webbezoek was dat plaatsvond na de laatste keer dat het SQL-werkgebied werd weergegeven en de Opportunity niet vooruit helpt.

Het werkgebied van lead 1 verandert in SAL en wordt vervolgens omgezet in een contactpersoon met een opportunity. In dit geval worden de posities SAL-01 (Last) en OC gecombineerd in hetzelfde aanraakpunt.

De FT,LC-aanraking van lead 3 wordt gemaakt als een aanraakpunt voor formulieren op de Opp. Alleen handelingen voor het invullen van formulieren worden gemaakt als aanraakpunten na de OC-aanraking. Daarom worden de overgangen in het werkgebied SQL-01 (Laatste) en SAL-01 (Laatste) voor regel twee niet gemaakt als aanraakpunten, omdat deze aanraakpunten webbezoeken waren.

De MQL-, SQL- en SAL-touches van lead 3 worden als aanraakpunt opgenomen omdat dit een handeling was voor het invullen van formulieren.

**Scenario 3 - Boomerang het Weighting van de Attributie**

In dit scenario, heeft een klant ervoor gekozen om **MQL**, **SQL**, en **SAL** stadia met boemerang te volgen aanraakpunten.

![&#x200B; Drie belangrijke reis die boemerang attributieweging met veelvoudige werkgebiedovergangen toont &#x200B;](assets/7.png)

De FT- en LC-aanraakpunten op de Opportunity zijn afkomstig van Lead 1 (blauw), omdat ze optraden vóór de FT en LC van Lead 2 (roze). Het LC-aanraakpunt voor lead 2 wordt weergegeven als een aanraakpunt voor een formulier op de opportunity.

De MQL-01 (laatste) van Lood 2 wordt de eerste MQL op de Kans. De MQL-01 van Lood 1 zal niet als aanraakpunt op de Kans verschijnen omdat Lood 2 MQL eerst voorkwam.

SQL-01 (laatste) van lead 2 wordt SQL-01 op de opportunity. SQL-01 op lood 1 zal niet als aanraakpunt op de kans verschijnen omdat SQL-01 op lood 2 eerst gebeurde.

Merk op dat Lood 1 boemerangs tussen MQL en SQL een paar keer alvorens definitief het SAL stadium te bereiken. SQL-01, MQL-02, SQL-02, MQL-03, SQL-03 _zal niet_ als aanraakpunten op de kans worden omvat omdat deze werkgebiedovergangen niet helpen in het drijven van de kans vooruit in de reis.

Het aanraakpunt SAL-01 (laatste) van lead 1 is het volgende aanraakpunt dat op de opp moet worden opgenomen. Lood 1 zet dan in een contact met een kans om, creërend OC touchpoint.

De FT en LC van lood 3, en de aanraakpunten MQL, SQL en SAL verschijnen als vormaanrakingen op de Kans.

SQL-01 (laatste)-aanraakpunt van lead 2 wordt niet opgenomen als aanraakpunt op de opp omdat dit na het aanraakpunt voor OC is opgetreden. Ook, kwam SQL van lood 2 het werkgebiedovergang voor _na de definitieve het werkgebiedovergang van SAL_, en helpt niet de opportuniteitstraject vooruit drijven.

## Opportunity-scenario&#39;s {#opportunity-scenarios}

**Scenario 1 - Contacten met het Volgen van Opportunity en Boommeren**

In dit scenario, heeft een klant ervoor gekozen om de **overgangen van het Stadium van de Demo en van de Onderhandeling** op het **Contact** te volgen. Elk boemerangstadium kan maximaal twee aanraakpunten ontvangen. Het verschil tussen werkgebiedovergangen op een Contact tegenover werkgebiedovergangen op een Lood is dat de overgangen van het werkgebied van het Contact als aanraakpunten Boommeren op de Kans _na_ OC kunnen verschijnen aanraakpunt. Dit geldt niet voor werkgebiedovergangen die zich op de lead voordoen, aangezien deze als touchpoint Formulier worden weergegeven.

![&#x200B; de reis die van het contact de van de Demo en van de Onderhandeling boemerang touchpoints tonen na OC touchpoint op Opportunity &#x200B;](assets/8.png) verschijnen

In dit voorbeeld worden de overgangen in de Stage van de Demo en de Onderhandeling van Contact 1 opgenomen als Demo-01- en onderhandelingsaanraakpunten op de Opportunity. De overgang van het werkgebied van de Demo van contact 2 komt voor _na_ Contact 1&#39;s, en verschijnt als (Laatste) aanraakpunt demo-02 op de Kans.

Er is geen tweede overgang naar de onderhandelingsfase; de opportuniteit springt onmiddellijk van demo-02 (laatste) stappen naar Close Won. In dit geval neemt [!DNL Marketo Measure] de onderhandelingstransactie met het aanraakpunt van de Gesloten Won op.
