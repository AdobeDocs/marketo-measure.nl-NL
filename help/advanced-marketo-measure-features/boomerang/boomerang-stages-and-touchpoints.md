---
unique-page-id: 18874558
description: Boommeren en aanraakpunten - [!DNL Marketo Measure] - Productdocumentatie
title: Boomerang Stages en Touchpoints
exl-id: e58169a3-3637-4878-8a0e-1920d873ff52
feature: Boomerang, Touchpoints
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 0%

---

# Boomerang Stages en Touchpoints {#boomerang-stages-and-touchpoints}

>[!AVAILABILITY]
>
>De Boomerang-functie wordt alleen ingeschakeld voor Tier 3-klanten. Neem contact op met het Adobe-accountteam (uw accountmanager) als u een hogere accountlaag wilt aanvragen.

[!DNL Marketo Measure] heeft onze functie Boomerang Stage uitgebracht! De functie van het Stadium van Boemerang werd gecreeerd om grotere zicht in de reis van de klant te verstrekken voor [!DNL Marketo Measure] klanten met lange verkoopcycli. Met deze functie kunnen marketers aanraakpunten maken voor alle werkgebiedovergangen die zich voordoen tijdens de Opportunity-reis, bijvoorbeeld wanneer een contactpersoon MQL&#39;s, vervolgens naar SAL gaat en vervolgens terugkeert naar het MQL-werkgebied. Wanneer de contacten &quot;het stadium van MQL&quot;of &quot;re-MQL&#39;s&quot;opnieuw ingaan, beschouwen wij MQL als een boemerang stadium. Het Boemerang-werkgebied functioneert naast [!DNL Marketo Measure] Aangepaste stadia.

## Wat doet deze functie? {#what-this-feature-does}

* Creeert een &quot;boemerang&quot;aanraakpunt voor alle stadium overgangen die in een reis van een opportuniteit voorkomen
* Tracks herkent overgangen tussen aangepaste werkruimten (bijv. wanneer een contactpersoon-MQL&#39;s naar SAL gaat en vervolgens teruggaat naar het MQL-werkgebied)
* Hiermee kunt u opgeven hoeveel en welke set werkgebiedovergangen u in de opportunity wilt opnemen (bijvoorbeeld De eerste 10 MQLs OF de laatste 5 MQLs)
* Als u een gebruiker van het Model van de Douane bent, kunt u de attributieweging en percentagekrediet bepalen u aan elk van deze stadia (b.v. wilt toewijzen. het toewijzingsgewicht toewijzen aan het eerste of laatste MQL-exemplaar, of de toewijzingsweging gelijkmatig verdelen over alle voorvallen)

>[!NOTE]
>
>[Instructies voor het instellen van Boomerang-fasen](/help/advanced-marketo-measure-features/boomerang/setting-up-boomerang-stages.md).

## Hoe ziet Boommeren en aanraakpunten eruit in uw CRM {#what-boomerang-stages-and-touchpoints-look-like-in-your-crm}

Zonder Boomerang-stappen (de &quot;voor&quot;) ziet u alleen het meest recente MQL- of meest recente SQL-aanraakpunt dat is gekoppeld aan een lijst met leads/contactpersonen.

![](assets/1.png)

Met de Stages en aanraakpunten van Boemerang ziet u aanraakpunten die voor elke overgang van het werkgebied optreden. De naamgevingsconventie voor deze boemerang-aanraakpunten is als volgt:

**[Werkgebiednaam]-00.**

In het onderstaande voorbeeld wordt deze [!DNL Marketo Measure] MQL en SQL zijn opgenomen in hun boemerang-fasen en hebben ervoor gekozen om 2 boemerang-aanraakpunten per werkgebied weer te geven.

![](assets/2.png)

**MQL-01** Dit is de eerste overgang in het MQL-werkgebied.

De numerieke waarde in de positie van het aanraakpunt geeft de volgorde aan waarin de overgang van het werkgebied heeft plaatsgevonden. Het laatste boemerang-aanraakpunt wordt als volgt gestempeld:

MQL-02 **(Laatste)**

## Hoe Boomerang-fasen uw bestaande gegevens wijzigen {#how-boomerang-stages-change-your-existing-data}

Boomerang Stages zal gevolgen hebben voor:

**Attributie via kanaal**

* Sinds [!DNL Boomerang Stages] Er worden meer aanraakpunten gemaakt. Hierdoor wordt de verdeling van de toewijzing over de aanraakpunten in de gegevens gewijzigd. Dit kan ertoe leiden dat de inkomstenwaarden tussen de afzetkanalen verschuiven. Houd hiermee rekening voordat u de [!DNL Boomerang stages]of neem contact op met uw accountmanager voor meer informatie.

**Alle rapporten die &#39;equals gebruiken [Positie aanraakpunt]&quot;**

* De stadia van Boemerang zullen nieuwe aanraakpuntposities aan uw gegevens introduceren. [!DNL Marketo Measure] wijzigt de opmaak van de positie van het aanraakpunt zodat deze het voorkomen van het werkgebied bevat, zoals &quot;MQL-01&quot; of &quot;MQL-05 (Laatste)&quot;. In dit voorbeeld beïnvloedt Boomerang Stages alle rapporten die gebruikmaken van &quot;Touchpoint Position is equal to MQL.&quot; Als u deze rapporten wilt aanpassen, gebruikt het filter in plaats daarvan de operator &quot;contains&quot;.

## Veelgestelde vragen {#faq}

**Hoeveel boemerang-stadia kan ik in mijn attributiemodel opnemen?**

U kunt maximaal 15 fasen selecteren.

**V: Hoeveel &quot;boemerang&quot;-aanraakpunten kan ik per stadium hebben?**

U kunt maximaal 10 boemerang-aanraakpunten per werkgebied selecteren.

**V: Waarom zijn we beperkt tot 10 boemerangs per stadium?**

[!DNL Marketo Measure] het aantal fasen moet worden beperkt om de verwerkingstijden onder controle te houden. Als u ervoor kiest om alle 15 Boomerang-stappen in uw attributiemodel en 10 boemerang-aanraakpunten per werkgebied op te nemen, hebt u mogelijk meer dan 150 aanraakpunten per regel/contactrecord.

**V: Ik heb Data Warehouse. Heb ik alle gegevens of is het Boemerang Stages-plafond ook op mij van toepassing?**

Het maximum geldt voor Data Warehouse en BCR vanwege de verwerkingsbeperkingen die [!DNL Marketo Measure] heeft bestaan. De Data Warehouse zal ook de limiet van 10 aanraakpunten per fase zien.

**Q: Wat is het voordeel om Stages Boomerang met Aangepaste Modellering te gebruiken?**

Gebruiken [!UICONTROL Boomerang] Met Fases met aangepaste modellering kunt u toewijzingsweging toewijzen aan [!UICONTROL Boomerang] touchpoints, die inkomstenkrediet aan deze fasen zullen toekennen.

Zonder aangepaste modellen [!DNL Marketo Measure] voor elke boemerang- en werkgebiedovergang aanraakpunten creëren, maar aan deze aanraakpunten geen toeslagen toekennen. De enige boemerang-aanraakpunten die attribuutcredits zullen ontvangen, zijn aanraakpunten voor verzending. Zonder aangepast model [!DNL Boomerang] aanraakpunten worden als hetzelfde beschouwd als een &quot;middelste aanraking&quot; en krijgen dienovereenkomstig toeschrijvingen.
