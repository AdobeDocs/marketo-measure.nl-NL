---
description: Aanbevolen procedures voor onlinekanalen - [!DNL Marketo Measure]
title: Aanbevolen procedures voor onlinekanalen
exl-id: 766cb01c-98b3-492d-bb35-e0a78b76333a
feature: Channels
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 0%

---

# Aanbevolen procedures voor onlinekanalen {#best-practices-for-online-channels}

## Overzicht {#overview}

Om nauwkeurig te zijn [!DNL Marketo Measure] uw marketingkanalen moeten correct zijn ingesteld. In het veld Marketing channel wordt de groep marketingactiviteiten weergegeven die op het hoogste niveau door een aanraakpunt kan worden gebruikt (bijvoorbeeld Betaald zoeken, Direct, Sociaal, enzovoort).

Het instellen van uw marketingkanalen kent twee aspecten: online en offline. Dit document is gericht op de [!DNL Marketo Measure] aanbevelingen voor best practices voor het instellen en onderhouden van uw onlinekanalen.

De online regels van het Kanaal zijn de richtlijnen voor hoe [!DNL Marketo Measure] wijst uw digitale aanraakpunten toe, dat wil zeggen, alle aanraakpunten die via de [!DNL Marketo Measure] JS op uw site. Als deze regels niet volledig zijn of niet correct zijn geordend, kunnen aanraakpunten worden toegewezen aan het onjuiste kanaal, waardoor de nauwkeurigheid van de rapportage afneemt. Als u ervoor zorgt dat uw regels voor online kanalen correct en up-to-date zijn, weet u zeker dat uw digitale gegevens worden toegewezen aan het juiste kanaal en de juiste subkanalen in uw [!DNL Marketo Measure] Rapportage.

## Beste praktijken {#best-practice}

Ongeacht of u uw regels voor het eerst instelt of alleen controleert of ze correct zijn, houd dan rekening met de volgende aanbevolen procedures.

Neem wat tijd om na te denken over de organisatie van uw marketingcampagnes en hoe deze passen in de [!DNL Marketo Measure] kader. Bepaal welke kanalen en Subkanalen in uw Online Kanalen zouden moeten worden vertegenwoordigd en welke campagnes, parameters UTM, of verwijzende websites die kanalen van elkaar onderscheiden.

Denk aan de volgende zaken:

* Alle digitale kanalen en subkanalen moeten met minstens één regel worden vertegenwoordigd
   * Als het kanaal geen personen naar uw site stuurt, is het geen online kanaal
* U hebt meerdere regels nodig voor één kanaal/subkanaal
   * Meerdere regels kunnen worden beschouwd als &quot;een breder net casting&quot; om ervoor te zorgen dat elk aanraakpunt correct wordt toegewezen. Vaak kunnen parameters verkeerd worden toegevoegd of volledig worden gemist, daarom is het hebben van veelvoudige regels om een kanaal/subchannel te vangen een goed idee om afbeeldingsnauwkeurigheid te verzekeren.
* [!DNL Marketo Measure] logica geeft voorrang aan touchpoint mapping in aflopende volgorde, te beginnen met de bovenste rij van het spreadsheet en deze omlaag te maken
   * [!DNL Marketo Measure] leest elke regel (rij), zoekend waar en eerst passend. Het aanraakpunt wordt vervolgens toegewezen aan dat kanaal/subkanaal
   * Sorteer het vel niet in alfabetische volgorde, omdat dit de logische regels aantast.
* Handhaaf de gehaakte regels, bewerk of voeg niet aan de gehaakte regels toe (voorbeeld; [Advertentievoorden zoekopdracht] of [Facebook Paid] )
   * Deze zijn uit de doos [!DNL Marketo Measure] regels met ingebouwde logica, die gebonden zijn aan de [!DNL Marketo Measure] integratie. Geef deze regels hoogste prioriteit voor die kanaal/subkanaalsectie om ervoor te zorgen [!DNL Marketo Measure] de integratie kan werken zoals zij is ontworpen .
* Nadat het bestand is geüpload, kunt u de regels gedurende zeven dagen niet meer wijzigen
   * [!DNL Marketo Measure] gebruikt deze tijd om de aanraakpunten te verwerken en bij te werken. Controleer daarom de regels voordat u gaat uploaden.

## Aanbevolen werkwijzen voor onderhoud {#best-practice-for-maintenace}

Nadat de online regels van het Kanaal worden bewaard en verwerkt, werken zij onophoudelijk om uw digitale touchpoints te sluiten. Nochtans veroorzaken bepaalde veranderingen of scenario&#39;s u uw Online opstelling van het Kanaal wilt herzien. [!DNL Marketo Measure] raadt u aan om uw regels voor online kanalen eens in de zes maanden te herzien. Dit zorgt ervoor dat uw [!DNL Marketo Measure] gegevens worden uitgelijnd met uw interne definities van onlinekanalen/subkanalen en uw gebruik van UTM&#39;s.

Andere items die uw team ertoe kunnen aanzetten online kanaalonderhoud uit te voeren, zijn onder andere...

* Nieuw digitaal kanaal/subkanaal gestart
* UTM-parameters worden bijgewerkt of gewijzigd
* Wijzigingen in de kanaalorganisatie of naamgevingsconventies
* Omzet in uw marketingteam

Als uw team onlangs één van bovengenoemde ervaring heeft [!DNL Marketo Measure] raadt u aan de regels voor online kanalen te herzien en de juiste wijzigingen aan te brengen.

>[!MORELIKETHIS]
>
>* [Online kanaalinstelling](/help/channel-tracking-and-setup/online-channels/online-custom-channel-setup.md)
>* [UTM-parameters](/help/channel-tracking-and-setup/online-channels/utm-parameters.md)
>* [Marketingkanaal en Subkanaal](/help/channel-tracking-and-setup/online-channels/marketing-channels-and-subchannels.md)
>* [Beste praktijken UTM](/help/channel-tracking-and-setup/online-channels/best-practices-for-setting-up-utm-parameters.md)
