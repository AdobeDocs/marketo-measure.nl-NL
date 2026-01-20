---
description: Beste praktijken voor Online Kanalen -  [!DNL Marketo Measure]
title: Aanbevolen procedures voor onlinekanalen
exl-id: 766cb01c-98b3-492d-bb35-e0a78b76333a
feature: Channels
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 0%

---

# Aanbevolen procedures voor onlinekanalen {#best-practices-for-online-channels}

## Overzicht {#overview}

Uw marketingkanalen moeten correct zijn ingesteld om een nauwkeurige [!DNL Marketo Measure] -rapportage te kunnen krijgen. In het veld Marketing channel wordt de groep marketingactiviteiten weergegeven die op het hoogste niveau door een aanraakpunt kan worden gebruikt (bijvoorbeeld Betaald zoeken, Direct, Sociaal, enzovoort).

Het instellen van uw marketingkanalen kent twee aspecten: online en offline. Dit document is gericht op de [!DNL Marketo Measure] aanbevelingen voor best practices voor het instellen en onderhouden van uw onlinekanalen.

De regels van het Onlinekanaal zijn de richtlijnen voor hoe [!DNL Marketo Measure] uw digitale aanraakpunten in kaart brengt, namelijk om het even welke aanraakpunten die via [!DNL Marketo Measure] JS op uw plaats worden gevolgd en gecreeerd. Als deze regels niet volledig zijn of niet correct zijn geordend, kunnen aanraakpunten worden toegewezen aan het onjuiste kanaal, waardoor de nauwkeurigheid van de rapportage afneemt. Als u ervoor zorgt dat de regels voor het online kanaal correct en up-to-date zijn, weet u zeker dat uw digitale gegevens worden toegewezen aan het juiste kanaal en de juiste subkanalen in de [!DNL Marketo Measure] Reporting.

## Beste praktijken {#best-practice}

Ongeacht of u uw regels voor het eerst instelt of alleen controleert of ze correct zijn, houd dan rekening met de volgende aanbevolen procedures.

Neem wat tijd om na te denken over de organisatie van uw marketingcampagnes en hoe deze passen in het [!DNL Marketo Measure] -framework. Bepaal welke kanalen en Subkanalen in uw Online Kanalen zouden moeten worden vertegenwoordigd en welke campagnes, parameters UTM, of verwijzende websites die kanalen van elkaar onderscheiden.

Denk aan de volgende zaken:

* Alle digitale kanalen en subkanalen moeten met minstens één regel worden vertegenwoordigd
   * Als het kanaal geen personen naar uw site stuurt, is het geen online kanaal
* U hebt meerdere regels nodig voor één kanaal/subkanaal
   * Meerdere regels kunnen worden beschouwd als &quot;een breder net casting&quot; om ervoor te zorgen dat elk aanraakpunt correct wordt toegewezen. Vaak kunnen parameters verkeerd worden toegevoegd of volledig worden gemist, daarom is het hebben van veelvoudige regels om een kanaal/subchannel te vangen een goed idee om afbeeldingsnauwkeurigheid te verzekeren.
* Met [!DNL Marketo Measure] krijgt de toewijzing van aanraakpunten prioriteit in aflopende volgorde, te beginnen met de bovenste rij van het spreadsheet en vervolgens de volgende stap omlaag te maken
   * [!DNL Marketo Measure] leest elke regel (rij), zoekend waar en eerste pas. Het aanraakpunt wordt vervolgens toegewezen aan dat kanaal/subkanaal
   * Sorteer het vel niet in alfabetische volgorde, omdat dit de logische regels aantast.
* Handhaaf de gehaakte regels, geef of voeg niet aan de gehaakte regels uit (voorbeeld; [ AdWords Betaalde Onderzoek ] of [ Betaalde Facebook ])
   * Deze regels staan buiten de box [!DNL Marketo Measure] -regels met ingebouwde logica, die aan de [!DNL Marketo Measure] -integratie zijn gekoppeld. Geef deze regels de hoogste prioriteit voor dat kanaal/subkanaalgedeelte om ervoor te zorgen dat [!DNL Marketo Measure] -integraties naar behoren kunnen werken.
* Nadat het bestand is geüpload, kunt u de regels gedurende zeven dagen niet meer wijzigen
   * [!DNL Marketo Measure] gebruikt deze tijd om de aanraakpunten te verwerken en bij te werken. Controleer daarom de regels voordat u gaat uploaden.

## Aanbevolen werkwijzen voor onderhoud {#best-practice-for-maintenace}

Nadat de online regels van het Kanaal worden bewaard en verwerkt, werken zij onophoudelijk om uw digitale touchpoints te sluiten. Nochtans veroorzaken bepaalde veranderingen of scenario&#39;s u uw Online opstelling van het Kanaal wilt herzien. [!DNL Marketo Measure] raadt u aan om uw regels voor online kanalen eens in de zes maanden te controleren. Zo zorgt u ervoor dat uw [!DNL Marketo Measure] -gegevens zijn afgestemd op uw interne definities van online kanalen/subkanalen en uw gebruik van UTM&#39;s.

Andere items die uw team ertoe kunnen aanzetten online kanaalonderhoud uit te voeren, zijn onder andere...

* Nieuw digitaal kanaal/subkanaal gestart
* UTM-parameters worden bijgewerkt of gewijzigd
* Wijzigingen in de kanaalorganisatie of naamgevingsconventies
* Omzet in uw marketingteam

Als een van de bovenstaande problemen zich onlangs in uw team heeft voorgedaan, raadt [!DNL Marketo Measure] u aan de regels voor online kanalen te herzien en de juiste wijzigingen aan te brengen.

>[!MORELIKETHIS]
>
>* [&#x200B; Online Opstelling van het Kanaal &#x200B;](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
>* [&#x200B; parameters UTM &#x200B;](/help/channel-tracking-and-setup/online-channels/utm-parameters.md)
>* [&#x200B; het Marketing Kanaal en Subchannel &#x200B;](/help/channel-tracking-and-setup/online-channels/marketing-channels-and-subchannels.md)
>* [&#x200B; Beste praktijken UTM &#x200B;](/help/channel-tracking-and-setup/online-channels/best-practices-for-setting-up-utm-parameters.md)
