---
unique-page-id: 18874582
description: '[!DNL Marketo Measure] Salesforce-objecten -  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] Salesforce-objecten'
exl-id: d5d6f334-6531-40fa-b043-75b49d8f43d5
feature: Salesforce
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '924'
ht-degree: 0%

---

# [!DNL Marketo Measure] Salesforce-objecten {#marketo-measure-salesforce-objects}

>[!NOTE]
>
>U kunt instructies zien die &quot;[!DNL Marketo Measure]&quot;in de documentatie specificeren, maar nog zie &quot;Bizible&quot;in uw CRM. We werken eraan dat dit wordt bijgewerkt en de herbranding wordt binnenkort weerspiegeld in uw CRM.

Wanneer [!DNL Marketo Measure] is geïnstalleerd in [!DNL Salesforce] (SFDC), worden verschillende aangepaste [!DNL Marketo Measure] -objecten toegevoegd. In dit artikel wordt een uitleg gegeven van verschillende van deze aangepaste [!DNL Marketo Measure] objecten. Sommige objecten die [!DNL Marketo Measure] toevoegt aan [!DNL Salesforce] zijn:

* [Buyer Touchpoint](#touchpoint)
* [Buyer Attribution Touchpoint](#attribution)
* [[!DNL Marketo Measure] Persoon](#person)
* [[!DNL Marketo Measure] A/B-tests](#ab)
* [[!DNL Marketo Measure] Gebeurtenissen](#events)

Aanraakpunten die zijn vastgelegd door de dingen die u wilt bijhouden, schrijven naar de aangepaste objecten die zijn gemaakt door de installatie van het [!DNL Bizible Salesforce] -pakket.

[!DNL Marketo Measure] Objecten hebben betrekking op specifieke standaard [!DNL Salesforce] -objecten. Op deze manier kunt u [!DNL Marketo Measure] en [!DNL Salesforce] -objecten samen rapporteren. In de onderstaande tabel wordt aangegeven op welk [!DNL Salesforce] -object het [!DNL Marketo Measure] -object betrekking heeft.

![](assets/1-1.png)

## Buyer Touchpoint {#buyer-touchpoint}

Met het object [!UICONTROL Buyer Touchpoint] (BT) wordt het marketingverhaal van een individu verteld. Het bevat alle gegevens met betrekking tot de marketingaanraakpunten die door Leads en Contacten worden gegenereerd. Op de BT wordt informatie weergegeven over het marketingkanaal waar het aanraakpunt vandaan kwam of over de advertentiecampagne die die bepaalde lead/contactpersoon naar uw website heeft gebracht.

Het Voorwerp van BT is zichtbaar op de Pagina&#39;s van Leads en van Contacten als a **Verwante Lijst** (zie hieronder beeld).

![](assets/2-1.png)

In de lijst Verwante BT worden alle aanraakpunten weergegeven die bij de lead of contactpersoon horen. In de lijst staan aangepaste [!DNL Marketo Measure] velden die meer informatie over elk aanraakpunt bevatten. Het klikken op het aantal van identiteitskaart van Buyer Touchpoint zal u aan de pagina van het Detail van Buyer Touchpoint leiden, die zelfs meer details over touchpoint, als de eerste Web-pagina het Lood/Contact tijdens die Webzitting (**landende pagina**) verstrekt.

## Buyer Attribution Touchpoint {#buyer-attribution-touchpoint}

Het [!UICONTROL Buyer Attribution Touchpoint] -object vertelt het verhaal van de marketinginteracties van uw contactpersonen met betrekking tot een opportuniteit. Het toont de *attributie* gegevens met betrekking tot marketing touchpoints. Met dit object kunt u zien hoeveel inkomstenkrediet wordt toegewezen aan elk marketingaanraakpunt. Het type toewijzingsmodel dat u gebruikt, bepaalt het percentage aan aanraakpunten toegewezen inkomsten.

Aanraakpunten voor koperkenmerken (BBT&#39;s) worden pas gecreëerd wanneer een Opportunity is gemaakt die betrekking heeft op contactpersonen die gegevens van Buyer Touchpoint (BT) bevatten. BBT&#39;s worden niet gemaakt zonder opportuniteit. Zodra de Kans is gecreeerd, zal het Voorwerp van BAT het [!DNL Salesforce] *2} gebied van het Bedrag {op de Kans gebruiken om te begrijpen hoeveel opbrengst aan attributen aan touchpoints.*

A **werkschema** moet worden gecreeerd als u het gebied van het Bedrag van de a [ douane ](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md) gebruikt om opbrengst op het Voorwerp van de Kans te tonen. [!DNL Marketo Measure] kan de informatie niet lezen die in de velden Aangepast bedrag wordt weergegeven en kan daarom de toewijzingsgegevens van de inkomsten niet vullen op de aanraakpunten. Deze werkstroom zal het **[!DNL Marketo Measure]Gebied van het Bedrag van de Kans**, één van [!DNL Marketo Measure] douanevelden gebruiken, om de opbrengstwaarde van het gebied van het Bedrag van de douane aan het gebied van het Bedrag van de Kans in kaart te brengen.

![](assets/3-1.png)

Het object BAT is op het object [!UICONTROL Opportunity] , [!UICONTROL Contact] en [!UICONTROL Account] zichtbaar als een verwante lijst. In deze lijst worden alle aanraakpunten weergegeven met de toewijzingsgegevens die bij een opportunity horen. Als u op de Buyer Attribution Touchpoint-id klikt, gaat u naar de Buyer Attribution Touchpoint-detailpagina. Hier kunt u specifiekere toewijzingsgegevens en informatie zien over waar het aanraakpunt vandaan komt (vergelijkbaar met wat er van het Buyer Touchpoint-object wordt aangeboden).

## [!DNL Marketo Measure] Persoon {#marketo-measure-person}

Met het [!DNL Marketo Measure] object Person worden de objecten Lead en Contact aan elkaar gekoppeld. Salesforce beschikt niet over de optie om rapporten te maken met behulp van het object Lead en Contact in hetzelfde rapport. Door met betrekking tot het Lood en Voorwerp van het Contact te werken, staat de [!DNL Marketo Measure] Persoon u toe om over beide Voorwerpen binnen het zelfde rapport te melden. Dit is vooral handig wanneer een lead is omgezet in een contactpersoon. Op een [!DNL Marketo Measure] Personen-record wordt een zoekopdracht weergegeven naar de bijbehorende lijst met leads en/of contactpersonen, een verwante lijst met de aan de persoon gekoppelde aanraakpunten en de persoon-id (dit is altijd het e-mailadres van de lead/contactpersoon). Aangezien de persoon van [!DNL Marketo Measure] betrekking heeft op het object Lead &amp; Contact, is er nooit een [!DNL Marketo Measure] Person-record die is gekoppeld aan een Buyer Attribution Touchpoint. Hieronder ziet u een voorbeeld van een [!DNL Marketo Measure] Person-record in Salesforce:

![](assets/4.png)

## [!DNL Marketo Measure] A/B-test {#marketo-measure-a-b-test}

Als u A/B tests door [!DNL Optimizely] of (Visuele Optimizer van het Web) in werking stelt, kunt u die rekeningen met uw [!DNL Marketo Measure] rekening verbinden om A/B testgegevens binnen Salesforce te bekijken. Met het [!DNL Marketo Measure] A/B-testobject kunt u in feite A/B-testgegevens van Optimizely/VWO nemen en de gegevens koppelen aan Leads en Contacten.

![](assets/5.png)

Het [!DNL Marketo Measure] A/B-testobject wordt op de pagina&#39;s [!UICONTROL Leads] , [!UICONTROL Contacts] en [!UICONTROL Opportunity] weergegeven als een verwante lijst. De lijst bevat alle experimenten en variaties die u doorloopt via Optimizely of VWO. U kunt de experimenten/variaties bekijken zoals deze betrekking hebben op specifieke leads en contactpersonen.

## [!DNL Marketo Measure] Gebeurtenissen {#marketo-measure-events}

Met het gebeurtenisobject [!DNL Marketo Measure] kunt u specifieke gebeurtenissen bijhouden die op uw website plaatsvinden. Als u specifieke gebeurtenissen op uw website wilt bijhouden, moet er naast [!DNL Marketo Measure] JavaScript ook een aangepaste code aan uw pagina&#39;s worden toegevoegd. De vastgelegde informatie wordt weergegeven in de [!DNL Marketo Measure] Objectgerelateerde lijst, die u kunt vinden op de pagina&#39;s [!UICONTROL Leads] , [!UICONTROL Contacts] en [!UICONTROL Opportunity] . Het [!DNL Marketo Measure] Voorwerp van Gebeurtenissen *bindt niet* aan attributiegegevens. Het doel van dit object is om te zien of mensen specifieke handelingen op uw website uitvoeren.

## [!DNL Marketo Measure] Velden {#marketo-measure-fields}

Gegevens die zijn vastgelegd door de [!DNL Marketo Measure] JavaScript, worden geduwd in de aangepaste [!DNL Marketo Measure] -velden binnen de [!DNL Marketo Measure] -objecten. Bepaalde velden zijn alleen beschikbaar op bepaalde objecten. U kunt de [ verklarende woordenlijst van [[!DNL Marketo Measure] gebieden] ](/help/introduction-to-marketo-measure/overview-resources/glossary-of-marketo-measure-fields.md) en a [ visualisatie van de verwante  [!DNL Marketo Measure]  Voorwerpen ](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-object-and-field-taxonomy.md) herzien.

## [!DNL Marketo Measure] Rapporten en dashboards {#marketo-measure-reports-and-dashboards}

De [!DNL Marketo Measure] rapporten en dashboards die aan uw [!DNL Salesforce] worden toegevoegd voorzien u van uit-van-de-doos rapportering en gegevensvisualiseringsmogelijkheden. Dit zijn eenvoudige [!DNL Marketo Measure] -rapporten waarmee u snel aanraakpuntgegevens kunt ordenen, analyseren en begrijpen.
