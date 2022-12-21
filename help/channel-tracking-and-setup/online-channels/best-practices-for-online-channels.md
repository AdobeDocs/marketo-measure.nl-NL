---
description: Aanbevolen procedures voor onlinekanalen - [!DNL Marketo Measure] - Productdocumentatie
title: Aanbevolen procedures voor onlinekanalen
exl-id: 766cb01c-98b3-492d-bb35-e0a78b76333a
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 0%

---

# Aanbevolen procedures voor onlinekanalen {#best-practices-for-online-channels}

## Overzicht {#overview}

Om nauwkeurig te zijn [!DNL Marketo Measure] de marketingkanalen moeten correct zijn ingesteld. In het veld marketingkanaal wordt de groep marketingactiviteiten weergegeven die op het hoogste niveau door een aanraakpunt kan worden uitgevoerd (bijvoorbeeld Betaald zoeken, Direct, Sociaal, enz.).

Het instellen van uw marketingkanalen kent twee aspecten: online en offline. In dit document wordt de nadruk gelegd op de [!DNL Marketo Measure] aanbevelingen voor best practices voor het instellen en onderhouden van uw onlinekanalen.

De online regels van het Kanaal zijn de richtlijnen voor hoe [!DNL Marketo Measure] wijst uw digitale aanraakpunten toe, d.w.z. alle aanraakpunten die via de [!DNL Marketo Measure] JS op uw site. Als deze regels niet volledig zijn of niet correct zijn geordend, kunnen aanraakpunten worden toegewezen aan het onjuiste kanaal, waardoor de nauwkeurigheid van de rapportage afneemt. Als u ervoor zorgt dat uw regels voor online kanalen correct en up-to-date zijn, weet u zeker dat uw digitale gegevens worden toegewezen aan het juiste kanaal en de juiste subkanalen in uw [!DNL Marketo Measure] Rapportage.

## Beste praktijken {#best-practice}

Of u opstelling uw regels voor het eerst of enkel het herzien hen aan controle voor nauwkeurigheid bent, houd de volgende beste praktijken in mening.

Neem wat tijd om na te denken over de organisatie van uw marketingcampagnes en hoe deze passen in de [!DNL Marketo Measure] kader. Bepaal welke kanalen en Subkanalen in uw Online Kanalen evenals welke campagnes, parameters UTM, of verwijzende websites zouden moeten worden vertegenwoordigd die kanalen van elkaar onderscheiden.

Denk aan de volgende zaken:

* Alle digitale kanalen en subkanalen moeten met minstens één regel worden vertegenwoordigd
   * Als het kanaal geen personen naar uw site stuurt, is het geen online kanaal
* Het is oké om veelvoudige regels voor één kanaal/subchannel te hebben
   * Meerdere regels kunnen worden beschouwd als &quot;een breder net casting&quot; om ervoor te zorgen dat elk aanraakpunt correct wordt toegewezen. Vaak kunnen parameters verkeerd worden toegevoegd of volledig worden gemist, daarom is het hebben van veelvoudige regels om een kanaal/subchannel te vangen een goed idee om afbeeldingsnauwkeurigheid te verzekeren.
* [!DNL Marketo Measure] logica geeft voorrang aan touchpoint mapping in aflopende volgorde, te beginnen met de bovenste rij van het spreadsheet en deze omlaag te maken
   * [!DNL Marketo Measure] leest elke regel (rij), zoekend waar en eerst passend. Het aanraakpunt wordt vervolgens toegewezen aan dat kanaal/subkanaal
   * Sorteer het blad niet in alfabetische volgorde, omdat dit de logische regels verstoort.
* Handhaaf de gehaakte regels, bewerk of voeg niet aan de gehaakte regels toe (voorbeeld; [Advertentievoorden zoekopdracht] of [Facebook Paid] )
   * Deze zijn uit de doos [!DNL Marketo Measure] regels die zijn ingebouwd in logica, die gekoppeld zijn aan de [!DNL Marketo Measure] integratie. Geef deze regels hoogste prioriteit voor die kanaal/subkanaalsectie om ervoor te zorgen dat de [!DNL Marketo Measure] de integratie kan werken zoals zij is ontworpen .
* Nadat het bestand is geüpload, kunt u de regels gedurende zeven dagen niet meer wijzigen
   * [!DNL Marketo Measure] gebruikt deze tijd om de aanraakpunten te verwerken en bij te werken. Controleer daarom de regels voordat u gaat uploaden.

## Aanbevolen werkwijzen voor onderhoud {#best-practice-for-maintenace}

Nadat u de online kanaalregels hebt opgeslagen en verwerkt, kunt u de digitale aanraakpunten continu sluiten. Nochtans veroorzaken bepaalde veranderingen of scenario&#39;s u uw Online opstelling van het Kanaal wilt herzien. [!DNL Marketo Measure] raadt u aan om uw regels voor online kanalen eens in de zes maanden te herzien. Zo zorgt u ervoor dat uw [!DNL Marketo Measure] gegevens worden uitgelijnd met uw interne definities van onlinekanalen/subkanalen en uw gebruik van UTM&#39;s.

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

