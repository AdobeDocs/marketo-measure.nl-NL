---
unique-page-id: 18874684
description: Datums voor campagnesynchronisatie -  [!DNL Marketo Measure]
title: Synchronisatiedata voor campagne
exl-id: 66ce9948-9297-47ef-8b16-0ac45c5664fc
feature: Channels
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 0%

---

# Synchronisatiedata voor campagne {#campaign-sync-dates}

Leer wat de functie Datums synchroniseren van de Campagne doet, en bied enkele gebruiksgevallen voor deze functie aan.

>[!NOTE]
>
>Dit artikel behandelt een verouderd proces. Wij moedigen gebruikers aan om het [ nieuwe, verbeterde in-app proces ](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"} te gebruiken.

**[!DNL Marketo Measure]Vereist pakket: 6.9 of hoger**

Deze functie bestaat uit twee eenvoudige datumvelden in het [!DNL Salesforce] Campagneobject:

* Begindatum aanraakpunt
* Einddatum aanraakpunt

Wanneer Aanraakpunten voor kopers zijn ingeschakeld voor een bepaalde campagne, kunt u met de synchronisatiedatums voor campagnes de parameters Aanraakpunt datum instellen voor de afzonderlijke campagne. Als u dus een einddatum van het aanraakpunt van 1 maart 2017 toevoegt, maakt [!DNL Marketo Measure] alleen aanraakpunten op campagneleden die vóór die datum aan de campagne zijn toegevoegd. [!DNL Marketo Measure] maakt geen aanraakpunten voor campagsleden die na 1 maart 2017 zijn toegevoegd.

![](assets/1.gif)

En als u een aanraakpunt Begindatum toevoegt aan een campagne (bijvoorbeeld 1 januari 2017), maakt [!DNL Marketo Measure] geen aanraakpunten op campagneleden die vóór 1 januari 2017 zijn toegevoegd aan de campagne. U hoeft geen Begindatum van een aanraakpunt toe te voegen als u een Einddatum van een aanraakpunt en vice versa toevoegt.

## Gebruik hoofdletters {#use-cases}

**terug-vult Aanraakpunten**

Er kunnen tijden zijn wanneer een marketing team het toevoegen van parameters van utm aan een bepaalde marketing inspanning kan missen. Met de synchronisatiedatums voor campagnes kunt u (als u SFDC-campagnes gebruikt voor online inspanningen) een aantal gemiste gegevens terugvullen. Laten we zeggen dat u een e-mailcampagne uitvoert die op 1 mei is gestart, maar dat uw team tot 15 mei geen parameters heeft toegevoegd aan die e-mailcampagne. Als u e-mailconversies bijhoudt via een SFDC-campagne, kunt u een Einddatum van aanraakpunt van 15 mei voor die campagne instellen en aanraakpunten inschakelen voor &#39;Responded&#39;-leden van de campagne. Met deze actie maakt [!DNL Marketo Measure] aanraakpunten voor al deze reacties tot 15 mei.

**Retroactive de Aanraakpunten van het Lidmaatschap van de Campagne**

Als u een nieuwe [!DNL Marketo Measure] klant bent, bent u wellicht geïnteresseerd in het doorgeven van enkele marketinggegevens die u via SFDC Campaigns hebt bijgehouden. Als u echter aanraakpunten wilt inschakelen voor uw online SFDC-campagnes, kunt u het probleem van de attributie van dubbeltelling oplossen, aangezien [!DNL Marketo Measure] automatisch aanraakpunten maakt voor uw online marketingactiviteiten. Als u wilt voorkomen dat gegevens dubbel worden geteld, kunt u Einddatums van aanraakpunten gebruiken om een limiet in te stellen voor de aanraakpuntdatums die door [!DNL Marketo Measure] in de SFDC-campagne zijn gemaakt. Als u bijvoorbeeld retroactieve conversies wilt toevoegen voor een sociale campagne die u hebt bijgehouden in SFDC, maar u begrijpt dat u de [!DNL Marketo Measure] JavaScript (die online aanraakpunten maakt) op 1 juli hebt toegevoegd, kunt u de campagne voor sociale SFDC bewerken met een aanraakpunteinddatum die gelijk is aan 1 juli en Aanraakpunten voor die campagne inschakelen.

Er kunnen vele andere gebruiksgevallen zijn voor de Einddata van het Aanraakpunt. Als u hulp het uitzoeken van een specifieke situatie nodig hebt, aarzel niet om uit te reiken aan [ de Steun van Marketo ](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
