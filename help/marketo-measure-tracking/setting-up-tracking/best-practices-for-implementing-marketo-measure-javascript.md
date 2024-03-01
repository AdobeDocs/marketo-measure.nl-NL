---
description: Beste praktijken voor het Uitvoeren [!DNL Marketo Measure] JavaScript - [!DNL Marketo Measure]
title: Beste praktijken voor het Uitvoeren [!DNL Marketo Measure] JavaScript
exl-id: 0359ad27-81e8-4902-a23a-49a5646a44d0
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 0%

---

# Beste praktijken voor het Uitvoeren [!DNL Marketo Measure] JavaScript {#best-practices-for-implementing-marketo-measure-javascript}

## Overzicht {#overview}

De [!DNL Marketo Measure] JavaScript houdt de digitale marketinginteracties van uw webbezoekers bij en is van wezenlijk belang voor de [!DNL Marketo Measure] de mogelijkheid om online aanraakpuntgegevens te maken. De [!DNL Marketo Measure] JavaScript wordt correct en volledig geïmplementeerd op de volledige site of sites, zodat de verzamelde sessiegegevens nauwkeurige aanraakpuntgegevens opleveren.

Inconsistenties bij de invoering van de [!DNL Marketo Measure] JavaScript zal onderbrekingen in de zittingsgegevens veroorzaken die in het volgende kunnen resulteren:

* Onjuiste kanaaltoewijzing
* Verlies van brongegevens
* Hoge niveaus van onjuist direct verkeer
* Inconsistente rapportage

[!DNL Marketo Measure] JavaScript is een essentieel onderdeel van uw [!DNL Marketo Measure] account en sleutel tot succes!

## Beste praktijken {#best-practice}

Wanneer het over het uitvoeren van en het leiden van uw [!DNL Marketo Measure] Houd rekening met de volgende aanbevolen procedures in JavaScript.

* Bevestig dat al uw domeinen in uw [!DNL Marketo Measure] account
   * Neem contact op met de ondersteuning als u problemen hebt met uw domeinen
* JavaScript implementeren op ALLE pagina&#39;s.
   * Als JavaScript alleen op bepaalde pagina&#39;s wordt geplaatst, worden de sessiegegevens verbroken, wat tot onjuiste gegevens leidt [!DNL Marketo Measure] data
* Voor een formulier op uw site waarvan u geen aanraakpunten wilt maken, voegt u het volgende toe: [!DNL Marketo Measure] Script uitsluiten
   * Met dit script voor uitsluitingen wordt ervoor gezorgd dat de [!DNL Marketo Measure] sessiegegevens worden niet verstoord en de brongegevens blijven staan
      * Voorbeelden van algemene formulieren die moeten worden onderdrukt zijn:
         * Aanmeldingsgegevens klant
         * Formulieren Wachtwoord vergeten
         * Formulieren afmelden
         * Formulieren voor carrièreaanvragen
* Lees de secties &quot;Aanvullende overwegingen&quot; en &quot;Forms om extra aandacht te besteden aan&quot; van het toevoegen [!DNL Marketo Measure] Scriptbron hieronder vermeld om te controleren op scenario&#39;s die speciale afhandeling nodig kunnen hebben

## Aanbevolen werkwijzen voor onderhoud {#best-practice-for-maintenance}

Tijdens de installatie van de [!DNL Marketo Measure] JavaScript wordt behandeld tijdens de eerste implementatie, wijzigingen in uw site of het team dat deze beheert, kunnen leiden tot storingen in [!DNL Marketo Measure] bijhouden. We raden u aan de [!DNL Marketo Measure] JavaScript wordt één keer per jaar correct en volledig geïmplementeerd. Als uw organisatie bovendien een type documentatie van het veranderingsprotocol voor de website heeft, zorg ervoor dat er een gedeelte is waarin wordt uitgelegd dat [!DNL Marketo Measure] JavaScript moet behouden blijven of worden toegevoegd aan alle nieuwe pagina&#39;s.

Andere redenen die kunnen leiden tot een revisie van uw JavaScript-instellingen zijn onder andere..

* Omzet in uw marketingteam
* Wijzigingen en updates in de sitestructuur
* Sitemigratie
* Wijzigingen in uw domein
* Verwerving van andere ondernemingen en hun westeigenschappen
