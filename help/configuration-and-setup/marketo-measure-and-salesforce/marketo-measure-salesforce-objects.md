---
unique-page-id: 18874582
description: "[!DNL Marketo Measure] Salesforce-objecten - [!DNL Marketo Measure] - Productdocumentatie"
title: "[!DNL Marketo Measure] Salesforce-objecten"
exl-id: d5d6f334-6531-40fa-b043-75b49d8f43d5
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '935'
ht-degree: 0%

---

# [!DNL Marketo Measure] Salesforce-objecten {#marketo-measure-salesforce-objects}

>[!NOTE]
>
>Mogelijk ziet u instructies die &quot;[!DNL Marketo Measure]&quot; in onze documentatie, maar zie nog &quot;Bizible&quot;in uw CRM. We werken eraan dat dit wordt bijgewerkt en de herbranding wordt binnenkort weerspiegeld in uw CRM.

Wanneer [!DNL Marketo Measure] is geïnstalleerd in [!DNL Salesforce] (SFDC), meerdere aangepaste [!DNL Marketo Measure] Objecten worden toegevoegd. Dit artikel bevat een uitleg van verschillende van deze aangepaste [!DNL Marketo Measure] Objecten. Sommige objecten die [!DNL Marketo Measure] toevoegen aan [!DNL Salesforce] zijn:

* [Aanraakpunt koper](#touchpoint)
* [Aanraakpunt koperkenmerk](#attribution)
* [[!DNL Marketo Measure] Persoon](#person)
* [[!DNL Marketo Measure] A/B-tests](#ab)
* [[!DNL Marketo Measure] Gebeurtenissen](#events)

Aanraakpunten die zijn vastgelegd door de dingen die u wilt bijhouden, schrijven naar de aangepaste objecten die zijn gemaakt door de installatie van de [!DNL Bizible Salesforce] pakket.

[!DNL Marketo Measure] Objecten hebben betrekking op specifieke norm [!DNL Salesforce] Objecten. Op deze manier kunt u rapporteren over [!DNL Marketo Measure] en [!DNL Salesforce] Objecten bij elkaar. In de onderstaande tabel wordt aangegeven welke [!DNL Salesforce] Object [!DNL Marketo Measure] Object heeft betrekking op.

![](assets/1-1.png)

## Aanraakpunt koper {#buyer-touchpoint}

De [!UICONTROL Buyer Touchpoint] (BT) Object vertelt het marketingverhaal van een individu. Het bevat alle gegevens met betrekking tot de marketingaanraakpunten die door Leads en Contacten worden gegenereerd. In het BT ziet u informatie over het marketingkanaal waar het aanraakpunt vandaan komt of over welke Ad Campaign die de desbetreffende lead/contactpersoon naar uw website heeft geleid.

Het object BT is op de pagina&#39;s Leads en Contacten als een **Verwante lijst** (zie onderstaande afbeelding).

![](assets/2-1.png)

In de lijst Verwante koppelingen worden alle aanraakpunten weergegeven die bij de lead of contactpersoon horen. Binnen de lijst zijn aangepaste [!DNL Marketo Measure] Velden die nadere gegevens over elk aanraakpunt bevatten. Als u op het nummer van de contactpersoon voor kopers klikt, gaat u naar de pagina Details aanraakpunt voor kopers, die nog meer informatie bevat over het aanraakpunt, zoals de eerste webpagina die tijdens die websessie is bezocht (**landingspagina**).

## Aanraakpunt koperkenmerk {#buyer-attribution-touchpoint}

De [!UICONTROL Buyer Attribution Touchpoint] Object vertelt het verhaal van de marketinginteracties van uw contactpersonen met betrekking tot een opportuniteit. De interface geeft de *toewijzing* gegevens met betrekking tot de marketingaanraakpunten. Met dit object kunt u zien hoeveel inkomstenkrediet wordt toegewezen aan elk marketingaanraakpunt. Het type toewijzingsmodel dat u gebruikt, bepaalt het percentage aan aanraakpunten toegewezen inkomsten.

Aanraakpunten voor koperkenmerken (BBT&#39;s) worden pas gecreëerd wanneer een opportunity wordt gecreëerd die betrekking heeft op contactpersonen die BT-gegevens (Buyer Touchpoint) hebben. BBT&#39;s worden niet gemaakt zonder opportuniteit. Zodra de Opportunity is gemaakt, gebruikt het BBT-object de [!DNL Salesforce] *Hoeveelheid* veld op de Opportunity om te begrijpen hoeveel omzet aan de aanraakpunten moet worden toegewezen.

A **werkstroom** moet worden gemaakt als u een [aangepast bedrag, veld](/help/advanced-marketo-measure-features/custom-revenue-amount/using-a-custom-revenue-amount-field.md) om opbrengsten op het Voorwerp van de Opportunity te tonen. [!DNL Marketo Measure] kan de informatie in de velden Aangepast bedrag niet lezen en kan bijgevolg geen gegevens over inkomstentoewijzing op de aanraakpunten invullen. In deze workflow wordt gebruikgemaakt van de **[!DNL Marketo Measure]Aantal kansen** Veld, een van de [!DNL Marketo Measure] aangepaste velden, om de opbrengstwaarde van het veld Aangepast bedrag toe te wijzen aan het veld Opportunity Amount.

![](assets/3-1.png)

Het BBT-object is zichtbaar op het tabblad [!UICONTROL Opportunity], [!UICONTROL Contact], en [!UICONTROL Account] Object als een verwante lijst. In deze lijst worden alle aanraakpunten weergegeven met de toewijzingsgegevens die bij een opportunity horen. Als u op de ID Aanraakpunt voor koperkenmerk klikt, gaat u naar de pagina Details aanraakpunt voor koperkenmerken. Hier kunt u specifiekere toewijzingsgegevens en informatie bekijken over waar het aanraakpunt vandaan komt (vergelijkbaar met wat er wordt geleverd met het object Aanraakpunt koper).

## [!DNL Marketo Measure] Persoon {#marketo-measure-person}

De [!DNL Marketo Measure] Persoonsobject koppelt de objecten Lead en Contact. Uit de doos, verstrekt Salesforce niet de optie om rapporten tot stand te brengen gebruikend het Lood en voorwerp van het Contact in het zelfde rapport. Door het object Lead en Contact te koppelen, [!DNL Marketo Measure] Met Persoon kunt u in hetzelfde rapport over beide objecten rapporteren. Dit is vooral handig wanneer een lead is omgezet in een contactpersoon. Op een [!DNL Marketo Measure] Persoonsrecord dat u ziet, wordt weergegeven met een zoekopdracht naar de bijbehorende lijst met leads en/of contactpersonen, een verwante lijst met de aan de persoon gekoppelde aanraakpunten en de persoon-id (dit is altijd het e-mailadres van de lead/contactpersoon). Aangezien [!DNL Marketo Measure] Persoon heeft betrekking op het object Lead &amp; Contact, er zal nooit een [!DNL Marketo Measure] Persoonsrecord die is gekoppeld aan een aanraakpunt voor koperkenmerken. Hieronder ziet u een voorbeeld van een [!DNL Marketo Measure] Persoonsregistratie in Salesforce:

![](assets/4.png)

## [!DNL Marketo Measure] A/B-test {#marketo-measure-a-b-test}

Als u A/B tests door [!DNL Optimizely] of VWO (Visuele Optimizer van het Web), kunt u die rekeningen met uw verbinden [!DNL Marketo Measure] account om de A/B-testgegevens in Salesforce weer te geven. De [!DNL Marketo Measure] Met een A/B-testobject kunt u in feite A/B-testgegevens van Optimizely/VWO nemen en de gegevens koppelen aan Leads en Contacten.

![](assets/5.png)

De [!DNL Marketo Measure] A/B-testobject wordt weergegeven als een verwante lijst in [!UICONTROL Leads], [!UICONTROL Contacts] en [!UICONTROL Opportunity] pagina&#39;s. De lijst bevat alle experimenten en variaties die u doorloopt via Optimizely of VWO. U kunt de experimenten/variaties bekijken als ze betrekking hebben op specifieke leads en contactpersonen.

## [!DNL Marketo Measure] Gebeurtenissen {#marketo-measure-events}

De [!DNL Marketo Measure] Met Events Object kunt u specifieke gebeurtenissen bijhouden die op uw website plaatsvinden. Als u specifieke gebeurtenissen op uw website wilt bijhouden, moet u naast de [!DNL Marketo Measure] JavaScript. De vastgelegde informatie wordt weergegeven in het [!DNL Marketo Measure] Lijst met verwante objecten, die u kunt vinden op het tabblad [!UICONTROL Leads], [!UICONTROL Contacts] en [!UICONTROL Opportunity] pagina&#39;s. De [!DNL Marketo Measure] Object Events *niet* koppelen aan toewijzingsgegevens. Het doel van dit object is om te zien of mensen specifieke handelingen op uw website uitvoeren.

## [!DNL Marketo Measure] Velden {#marketo-measure-fields}

Gegevens vastgelegd door de [!DNL Marketo Measure] JavaScript wordt in de aangepaste versie geplaatst [!DNL Marketo Measure] Velden binnen onze [!DNL Marketo Measure] Objecten. Bepaalde velden zijn alleen beschikbaar op bepaalde objecten. Voor een verklarende woordenlijst van alle [!DNL Marketo Measure] velden, alstublieft [klik hier](/help/introduction-to-marketo-measure/overview-resources/glossary-of-marketo-measure-fields.md). Voor een visualisatie waarvan [!DNL Marketo Measure] Object elk [!DNL Marketo Measure] Veld heeft betrekking op [klik hier](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-object-and-field-taxonomy.md).

## [!DNL Marketo Measure] Rapporten en dashboards {#marketo-measure-reports-and-dashboards}

De [!DNL Marketo Measure] Rapporten en dashboards die aan uw worden toegevoegd [!DNL Salesforce] biedt u mogelijkheden voor out-of-the-box rapportage en gegevensvisualisatie. Deze zijn fundamenteel [!DNL Marketo Measure] rapporten zodat u snel aanraakpuntgegevens kunt ordenen, analyseren en begrijpen.
