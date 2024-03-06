---
unique-page-id: 18874684
description: Synchronisatiedata voor campagne - [!DNL Marketo Measure]
title: Synchronisatiedata voor campagne
exl-id: 66ce9948-9297-47ef-8b16-0ac45c5664fc
feature: Channels
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 0%

---

# Synchronisatiedata voor campagne {#campaign-sync-dates}

Leer wat de functie Datums synchroniseren van de Campagne doet, en bied enkele gebruiksgevallen voor deze functie aan.

>[!NOTE]
>
>Dit artikel behandelt een verouderd proces. We raden gebruikers aan de [nieuw, verbeterd proces in de app](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"}.

**[!DNL Marketo Measure]Vereiste verpakking: 6.9 of hoger**

Deze functie bestaat uit twee eenvoudige datumvelden op de [!DNL Salesforce] Campagneobject:

* Begindatum aanraakpunt
* Einddatum aanraakpunt

Wanneer Aanraakpunten voor kopers zijn ingeschakeld voor een bepaalde campagne, kunt u met de synchronisatiedatums voor campagnes de parameters Aanraakpunt datum instellen voor de afzonderlijke campagne. Dus als je een Touchpoint-einddatum van 1 maart 2017 toevoegt, dan [!DNL Marketo Measure] alleen aanraakpunten maken op campagneleden die vóór die datum aan de campagne zijn toegevoegd. [!DNL Marketo Measure] geen aanraakpunten maken voor leden van de campagne die na 1 maart 2017 zijn toegevoegd.

![](assets/1.gif)

Op dezelfde manier als u een Datum van het Begin van het Aanraakpunt op een Campagne (te zeggen Januari 1, 2017) moest toevoegen, toen [!DNL Marketo Measure] Hiermee worden geen aanraakpunten gemaakt voor campagneleden die vóór 1 januari 2017 aan de campagne zijn toegevoegd. U hoeft geen Begindatum van een aanraakpunt toe te voegen als u een Einddatum van een aanraakpunt en vice versa toevoegt.

## Gebruik hoofdletters {#use-cases}

**Aanraakpunten met achtervulling**

Er kunnen tijden zijn wanneer een marketing team het toevoegen van parameters van utm aan een bepaalde marketing inspanning kan missen. De Datums van de Synchronisatie van de campagne zullen u toestaan om (als u campagnes SFDC voor online inspanningen gebruikt) terug te vullen sommige gemiste gegevens. Laten we zeggen dat u een e-mailcampagne uitvoert die op 1 mei is gestart, maar dat uw team tot 15 mei geen parameters heeft toegevoegd aan die e-mailcampagne. Als u e-mailconversies bijhoudt via een SFDC-campagne, kunt u een einddatum van aanraakpunt van 15 mei voor die campagne instellen en aanraakpunten inschakelen voor &#39;Responded&#39;-leden van de campagne. Deze actie zal [!DNL Marketo Measure] om aanraakpunten te maken voor al deze reacties tot 15 mei.

**Retroactive Campagne Membership Touchpoints**

Als u een nieuwe [!DNL Marketo Measure] klant, wilt u wellicht bepaalde marketinggegevens die u via SFDC Campaigns hebt bijgehouden, beschikbaar stellen. Als u echter de aanraakpunten naar uw online SFDC-campagnes wilt inschakelen, kunt u de kwestie van de attributie van dubbeltelling doorlopen, aangezien [!DNL Marketo Measure] maakt automatisch aanraakpunten voor uw online marketingactiviteiten. Als u dubbeltellende gegevens wilt voorkomen, kunt u Einddatums van aanraakpunten gebruiken om een limiet in te stellen voor de aanraakpuntdatums die worden gemaakt door [!DNL Marketo Measure] over de SFDC-campagne. Als voorbeeld, als u retroactieve omzettingen voor een Sociale Campagne wilde toevoegen hebt u in SFDC gevolgd, maar u begrijpt dat u hebt toegevoegd [!DNL Marketo Measure] JavaScript (dat online aanraakpunten maakt) maakt op 1 juli, kunt u de campagne Sociale SFDC bewerken met een einddatum van aanraakpunten die gelijk is aan 1 juli en Aanraakpunten voor kopers inschakelen voor die campagne.

Er kunnen vele andere gebruiksgevallen zijn voor de Einddata van het Aanraakpunt. Als u hulp nodig hebt bij het ontdekken van een specifieke situatie, aarzel dan niet om naar [Marketo-ondersteuning](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] Universiteit: Campagne en Campagne lidvelden](https://learn.bizible.com/2-bizible-customization/137720https://universityonline.marketo.com/courses/bizible-fundamentals-channel-management/#/page/5c63007334d9f0367662b758)
