---
description: '''[!DNL Salesforce] Pakketconsolidatie -  [!DNL Marketo Measure]'''
title: '[!DNL Salesforce] Pakketconsolidatie'
exl-id: ae559f5f-91bf-4504-9d5a-af47f95ca01f
feature: Salesforce
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 0%

---

# [!DNL Salesforce] Pakketconsolidatie {#salesforce-package-consolidation}

Om de gebruikerservaring te verbeteren en het gebruik te vereenvoudigen, worden bestaande pakketten gecompileerd in één, uitvoerig pakket.

## Pakketverlaging {#package-retirement}

Als gevolg van deze consolidatie zullen de huidige pakketten V1, V2_EXT, V2_Security en alle rapportagepakketten na augustus 2023 worden ingetrokken. Als u het V2-pakket al hebt geïnstalleerd, moet u het bijwerken naar de nieuwe geconsolideerde versie.

## Nieuw geconsolideerd pakket {#new-consolidated-package}

Het nieuwe geconsolideerde V2-pakket bevat alle functies en functies van de vorige pakketten, waardoor de gebruiker een betere ervaring krijgt. Dit bijgewerkte pakket maakt efficiëntere marketing en verkoopprestaties het volgen mogelijk en biedt meer inzicht in het gedrag van klanten.

Er zijn twee nieuwe gebieden om uw rapporteringsmogelijkheden te verbeteren:

* form_name: Nu beschikbaar in BT/BAT-objecten, kunnen gebruikers in dit veld rapporten maken op basis van formuliernamen.
* user_touchpoint_id: Dit gebied laat gebruikers toe om rapporten met unieke gebruikers te creëren aanraakpunt tellingen (`bizible2__User_Touchpoint_V2__c` in Salesforce).

## Ondersteuning en overgang {#support-and-transition}

Het [ team van de Steun ](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} is beschikbaar om het even welke vragen te beantwoorden en met het verzekeren van een vlotte overgang aan het nieuwe geconsolideerde pakket bij te wonen.

## Vereiste handelingen {#retired-actions}

* Als u het V2-pakket al hebt geïnstalleerd, moet u het bijwerken naar de nieuwe geconsolideerde versie.
* Als u rapporten of dashboards van om het even welk pakket van de Rapportering hebt, kunt u hen gemakkelijk zonder enige vereiste wijzigingen ontspannen, aangezien alle gebieden in het geconsolideerde pakket bestaan.
* Als u rapporten hebt die gebieden in het V2_EXT pakket gebruiken, kunt u hen in het geconsolideerde pakket door de hieronder stappen opnieuw creëren:
   * Alle gegevens in V2_EXT-velden zijn beschikbaar in Touchpoint-velden. U kunt dus uw rapporten wijzigen om gegevens op te halen uit corresponderende V2-aanraakpuntvelden door een filter toe te voegen op de positie van het aanraakpunt.
   * Voorbeeldrapport waarin alle leads worden opgehaald met Ad Content FT die &quot;Outreach&quot;-tekst bevat.
      * V2_EXT-query:
         * bizible2_ext__Ad_Content_FT__c contains Outreach

![](assets/bizible-full-1.png)

* Overeenkomende query in het geconsolideerde pakket:
   * bizible2__Touchpoint_Position__c bevat FT AND
   * bizible2__Ad_Content__c bevat Outreach

![](assets/bizible-taxonomy-1.png)

## Veelgestelde vragen {#faq}

**zal het geconsolideerde pakket conflicten met gebieden in mijn bestaand pakket hebben?**

U hoeft het pakket niet te verwijderen voordat u het geconsolideerde pakket installeert. Er treden geen conflicten op in velden omdat deze zich in een andere naamruimte bevinden.

**Hoe kan ik backfill de gegevens van mijn huidige pakketten?**

U kunt een kaartje [ met Steun ](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} voor het terugvullen en het opwerken van gegevens van BT/BAT dossier om identiteitskaart van het Aanraakpunt en de gebieden van identiteitskaart van de Vorm in te vullen.

**zullen de gebieden in V1 en V2_EXT pakketten in het geconsolideerde pakket beschikbaar zijn?**

Ja. Het geconsolideerde pakket bevat dezelfde velden in V1 met verdere uitsplitsingen naar objecten en V2_EXT-velden via aanraakpuntvelden.

**kan rapporten die V2_EXT gebieden gebruiken in het geconsolideerde pakket worden opnieuw gecreeerd?**

Ja. Volg de stappen in de [ Vereiste sectie van Acties ](#retired-actions).
