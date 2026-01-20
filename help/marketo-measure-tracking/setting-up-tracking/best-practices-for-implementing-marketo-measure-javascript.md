---
description: Beste praktijken voor het Uitvoeren van  [!DNL Marketo Measure]  JavaScript -  [!DNL Marketo Measure]
title: Beste praktijken voor het Uitvoeren van  [!DNL Marketo Measure]  JavaScript
exl-id: 0359ad27-81e8-4902-a23a-49a5646a44d0
feature: Tracking
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 0%

---

# Aanbevolen procedures voor het implementeren van [!DNL Marketo Measure] JavaScript {#best-practices-for-implementing-marketo-measure-javascript}

## Overzicht {#overview}

De JavaScript van [!DNL Marketo Measure] volgt de digitale marketinginteracties van uw webbezoekers en is van wezenlijk belang voor de mogelijkheid van [!DNL Marketo Measure] om online aanraakpuntgegevens te maken. Als de [!DNL Marketo Measure] JavaScript correct en volledig wordt geïmplementeerd op uw gehele site of sites, zorgt u ervoor dat de verzamelde sessiegegevens nauwkeurige aanraakpuntgegevens opleveren.

Inconsistenties in de implementatie van de [!DNL Marketo Measure] JavaScript veroorzaken onderbrekingen in de sessiegegevens, wat kan resulteren in het volgende:

* Onjuiste kanaaltoewijzing
* Verlies van brongegevens
* Hoge niveaus van onjuist direct verkeer
* Inconsistente rapportage

[!DNL Marketo Measure] JavaScript is een essentieel onderdeel van uw [!DNL Marketo Measure] -account en een sleutel tot succes!

## Beste praktijken {#best-practice}

Houd rekening met de volgende aanbevolen procedures als het gaat om het implementeren en beheren van uw [!DNL Marketo Measure] JavaScript.

* Bevestig dat al uw domeinen worden vermeld in uw [!DNL Marketo Measure] -account
   * Neem contact op met de ondersteuning als u problemen hebt met uw domeinen
* JavaScript implementeren op ALLE pagina&#39;s.
   * Als JavaScript alleen op bepaalde pagina&#39;s wordt geplaatst, worden de sessiegegevens verbroken, wat tot onjuiste [!DNL Marketo Measure] -gegevens leidt
* Voeg voor een formulier op uw site waarvan u geen aanraakpunten wilt maken het script voor uitsluiten van [!DNL Marketo Measure] toe
   * Met dit uitsluitingsscript wordt ervoor gezorgd dat de sessiegegevens van [!DNL Marketo Measure] niet worden onderbroken en dat de brongegevens op hun plaats blijven
      * Voorbeelden van algemene formulieren die moeten worden onderdrukt zijn:
         * Aanmeldingsgegevens klant
         * Formulieren Wachtwoord vergeten
         * Formulieren afmelden
         * Formulieren voor carrièreaanvragen
* Lees de gedeelten &quot;Aanvullende overwegingen&quot; en &quot;Forms om extra aandacht te besteden aan&quot; van de Scriptbron [!DNL Marketo Measure] die hieronder worden vermeld, om te controleren op scenario&#39;s die speciale afhandeling vereisen

## Aanbevolen werkwijzen voor onderhoud {#best-practice-for-maintenance}

Hoewel de instelling van de JavaScript van [!DNL Marketo Measure] wordt behandeld tijdens de eerste implementatie, kunnen wijzigingen in uw site of het team dat deze beheert, leiden tot onderbrekingen in het bijhouden van [!DNL Marketo Measure] . We raden u aan te bevestigen dat de [!DNL Marketo Measure] JavaScript één keer per jaar correct en volledig wordt geïmplementeerd. Als uw organisatie bovendien over documentatie van wijzigingsprotocollen voor de website beschikt, controleert u of er een gedeelte is waarin wordt uitgelegd dat [!DNL Marketo Measure] JavaScript moet worden behouden of toegevoegd aan alle nieuwe pagina&#39;s.

Andere redenen die een herziening van de JavaScript-instellingen kunnen activeren, zijn onder meer...

* Omzet in uw marketingteam
* Wijzigingen en updates in de sitestructuur
* Sitemigratie
* Wijzigingen in uw domein
* Verwerving van andere ondernemingen en hun westeigenschappen
