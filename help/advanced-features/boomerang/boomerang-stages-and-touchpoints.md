---
description: Boomerang-fasen en aanraakpunten voor Marketo Measure-gebruikers
title: Boomerang Stages en Touchpoints
exl-id: e58169a3-3637-4878-8a0e-1920d873ff52
feature: Boomerang, Touchpoints
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 0%

---

# Boomerang Stages en Touchpoints {#boomerang-stages-and-touchpoints}

>[!AVAILABILITY]
>
>De functie Boomerang is alleen ingeschakeld voor klanten van Tier 2 en 3. Neem contact op met het Adobe-accountteam (uw accountmanager) als u een hogere accountlaag wilt aanvragen.

[!DNL Marketo Measure] heeft de functie Boemerang Stage uitgebracht! De functie van het Stadium van Boemerang werd gecreeerd om grotere zicht in de reis van de klant voor [!DNL Marketo Measure] klanten met lange verkoopcycli te verstrekken. Met deze functie kunnen marketers aanraakpunten maken voor alle werkgebiedovergangen die zich tijdens de Opportunity-reis voordoen, zoals wanneer een contactpersoon MQL&#39;s, vervolgens naar SAL gaat en vervolgens terugkeert naar het MQL-werkgebied. Wanneer contacten &quot;het stadium van MQL&quot;of &quot;re-MQL&#39;s&quot;opnieuw ingaan, wordt MQL beschouwd als een boemerangstadium. De functie voor het werkgebied van Boomerang werkt naast de [!DNL Marketo Measure] Aangepaste werkfasen.

## Wat doet deze functie? {#what-this-feature-does}

* Creeert een &quot;boemerang&quot;aanraakpunt voor alle stadium overgangen die in een reis van een opportuniteit voorkomen
* Tracks herkent overgangen tussen aangepaste werkruimten (bijv. wanneer een contactpersoon-MQL&#39;s naar SAL gaat en vervolgens teruggaat naar het MQL-werkgebied)
* Hiermee kunt u opgeven hoeveel en welke set werkgebiedovergangen u in de opportunity wilt opnemen (bijvoorbeeld De eerste 10 MQLs OF de laatste 5 MQLs)
* Als u een gebruiker van het Model van de Douane bent, kunt u de attributieweging en percentagekrediet bepalen u aan elk van deze stadia (b.v. wilt toewijzen. toewijzingsgewicht toewijzen aan het eerste of laatste MQL-exemplaar, of toewijzingsgewicht gelijkmatig verdelen over alle voorvallen)

>[!NOTE]
>
>[ Instructies op hoe te opstelling Boommeren Stages ](/help/advanced-features/boomerang/setting-up-boomerang-stages.md).

## Hoe ziet Boommeren en aanraakpunten eruit in uw CRM {#what-boomerang-stages-and-touchpoints-look-like-in-your-crm}

Zonder Boomerang-stappen (de &quot;voor&quot;) ziet u alleen het meest recente MQL- of meest recente SQL-aanraakpunt dat is gekoppeld aan een lijst met leads/contactpersonen.

![](assets/boomerang-boomerang-18.png)

Met de Stages en aanraakpunten van Boemerang ziet u aanraakpunten die voor elke overgang van het werkgebied voorkomen. De naamgevingsconventie voor deze boemerang-aanraakpunten is:

**[Naam van het Stadium ] - 00.**

In het onderstaande voorbeeld heeft deze [!DNL Marketo Measure] -account MQL en SQL in hun boemerangfasen opgenomen en ervoor gekozen om 2 boemerang-aanraakpunten per werkgebied weer te geven.

![](assets/boomerang-boomerang-19.png)

**MQL-01** is de eerste MQL stadium overgang.

De numerieke waarde in de positie van het aanraakpunt geeft de volgorde aan waarin de overgang van het werkgebied plaatsvond. Het laatste boemerang-aanraakpunt wordt als volgt gestempeld:

MQL-02 **(Laatste)**

## Hoe Boomerang-fasen uw bestaande gegevens wijzigen {#how-boomerang-stages-change-your-existing-data}

Botsing met Boomerang-stadia:

**Attributie door kanaal**

* Aangezien [!DNL Boomerang Stages] meer aanraakpunten maakt, verandert de manier waarop de toewijzing wordt verdeeld over de aanraakpunten die momenteel in de gegevens voorkomen. Dit kan er dus toe leiden dat de inkomstenwaarden tussen de afzetkanalen verschuiven. Houd hier rekening mee voordat u [!DNL Boomerang stages] implementeert of neem contact op met uw accountmanager voor meer informatie.

**om het even welke rapporten die &quot;gelijke [ Positie van het Aanraakpunt ] gebruiken&quot;**

* De stadia van Boemerang introduceren nieuwe aanraakpuntposities aan uw gegevens. [!DNL Marketo Measure] wijzigt de opmaak van de positie van het aanraakpunt zodat deze de instantie van het werkgebied bevat, zoals &quot;MQL-01&quot; of &quot;MQL-05 (Laatste).&quot; Met dit voorbeeld beïnvloedt Boomerang Stages om het even welke rapporten die &quot;Positie van het Aanraakpunt gelijk aan MQL.&quot;gebruiken Als u deze rapporten wilt aanpassen, gebruikt het filter in plaats daarvan de operator &quot;contains&quot;.

## Veelgestelde vragen {#faq}

**hoeveel boemerang stadia kan ik in mijn attributiemodel omvatten?**

U kunt maximaal 15 fasen selecteren.

**Q: Hoeveel &quot;boemerang&quot;aanraakpunten kan ik per stadium hebben?**

U kunt maximaal tien boemerang-aanraakpunten per werkgebied selecteren.

**Q: Waarom is er een tien boemerangs grens per stadium?**

[!DNL Marketo Measure] moet een limiet instellen voor het aantal stappen om de verwerkingstijd onder controle te houden. Als u ervoor kiest om alle 15 Boomerang-stappen in uw attributiemodel en 10 boemerang-aanraakpunten per werkgebied op te nemen, hebt u mogelijk meer dan 150 aanraakpunten per regel/contactrecord.

**Q: Ik heb Data Warehouse. Krijg ik alle gegevens of is het Boemerang-plafond van Stages ook op me van toepassing?**

De limiet geldt voor Data Warehouse en CRM&#39;s vanwege de verwerkingsbeperkingen die [!DNL Marketo Measure] heeft ingesteld. Data Warehouse zal ook de limiet van tien aanraakpunten per fase zien.

**Q: Wat is het voordeel om Stages Boomerang met de Modellering van de Douane te gebruiken?**

Met [!UICONTROL Boomerang] Stage&#39;s met aangepaste modellering kunt u toewijzingsweging toewijzen aan [!UICONTROL Boomerang] touchpoints, die inkomstenkrediet aan deze fasen toewijzen.

Zonder aangepaste modellering maakt [!DNL Marketo Measure] aanraakpunten voor elke boemerang- en werkgebiedovergang, maar kent het geen attributietekort toe aan deze aanraakpunten. De enige boemerang-aanraakpunten die toewijzingskredieten ontvangen, zijn afkomstig van aanspreekpunten voor verzending. Zonder aangepast model worden aanraakpunten van [!DNL Boomerang] beschouwd als hetzelfde als een &#39;middenaanraking&#39; en krijgen ze dienovereenkomstig bijschriftkredieten.
