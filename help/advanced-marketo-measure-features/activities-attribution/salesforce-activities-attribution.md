---
unique-page-id: 18874708
description: Toewijzing Salesforce-activiteiten - [!DNL Marketo Measure] - Productdocumentatie
title: Toewijzing Salesforce-activiteiten
exl-id: 1dc6f15b-2a45-4ed3-9fa3-5267366d1f45
feature: Attribution, Salesforce
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 0%

---

# Toewijzing Salesforce-activiteiten {#salesforce-activities-attribution}

De [!DNL Marketo Measure] De integratie van de Activiteiten van Salesforce zal in specifieke taak en Gebeurtenis verslagen in uw attributiemodel brengen. Begin met het volgen van zaken zoals verkoop e-mails of telefoongesprekken die geen behoorlijk krediet ontvingen. Om uw activiteitenregel te vormen, zult u moeten gaan [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"}. Ga van daar naar de **[!UICONTROL Settings]** en klik op de knop **[!UICONTROL Activities]** tab.

Je staat op het punt je verkoopteam erg gelukkig te maken! Laten we u een korte zelfstudie geven.

![](assets/1.png)

Om te beginnen introduceren we een nieuw concept, genaamd een [!DNL Marketo Measure] Campagne. Voor elke regel die u definieert, gaat u de records in een [!DNL Marketo Measure] Campagne die u kunt noemen. Voeg zo nodig meerdere campagnes toe. Stel je voor dat je de effectiviteit van een campagne voor uitgaande verkoop naast een campagne voor betaalde media meet!

Je gaat dit gebruiken [!DNL Marketo Measure] Campagnenaam om ons te vertellen aan welk kanaal het zou moeten worden in kaart gebracht. Als u nog aan Uitgaande Verkoop denkt, misschien zouden alle Uitgaande campagnes van de Verkoop in een kanaal BDR moeten zitten.

Bekend maken met deze hiërarchie:

* Kanaal
   * Subkanaal
      * Campagne
      * Campagne
   * Subkanaal
      * Campagne

>[!TIP]
>
>Als u een unieke Campagne voor elke Verkoper bijvoorbeeld wilt plaatsen, gebruik onze dynamische vervangingsparameters om in te vullen [!DNL Marketo Measure] Naam campagne. In hetzelfde voorbeeld kunt u `"Outbound Sales - {AssignedTo}"` en we zullen het veranderen in zoiets `"Outbound Sales - Jill"` of `"Outbound Sales - Jack."` U hebt geen idee hoeveel tijd we u hebben bespaard!

![](assets/2.png)

Eenmaal uw [!DNL Marketo Measure] De Naam van de campagne wordt geplaatst, is het tijd aan opstelling uw regels van de Activiteit.

De regels fungeren als een filter om ons te vertellen welke records in aanmerking komen voor toekenning. Stel u voor een rapport in uw CRM creeert gebruikend gelijkaardige logica om dat rapport te produceren. U hebt de flexibiliteit om een combinatie van instructies en/of instructies en diverse operatoren zoals overeenkomsten met andere, bevat, begint met, eindigt met, is gelijk aan, enz. te gebruiken. Definieer &quot;en&quot;-instructies in een regel- of laaginstructie buiten het vak in een vak.

![](assets/3.png)

>[!NOTE]
>
>Formulervelden kunnen niet worden gebruikt binnen uw regels en worden niet weergegeven in de keuzelijst. Omdat formules op de achtergrond berekenen en een record niet wijzigen, [!DNL Marketo Measure] kan niet ontdekken of een verslag een regel past of niet.
>
>Gebruik correcte waarden voor id-velden zoals CrmEvent.CreatedById. [!DNL Salesforce IDs] zijn 18 tekens lang (bijvoorbeeld 0054H000007WmrfQAC).

Tot slot kiezen we een van de datum- of datum-/tijdvelden die je wilt gebruiken als Aanraakdatum koper. Standaard- en aangepaste velden kunnen worden geselecteerd.

>[!TIP]
>
>Met uw pakketinstallatie, [!DNL Marketo Measure] neemt een aangepast veld Aanraakpunt koper op in de activiteitenrecord. Als u een dynamische datum wilt gebruiken, zoals de datum waarop een status verandert, is het mogelijk om een CRM-workflow te gebruiken om de &quot;Aanraakdatum koper&quot; in te stellen en vervolgens de Aanraakdatum koper hier in deze stap te selecteren.

![](assets/4.png)

Vergeet niet verschillende regels voor Taken of Gebeurtenissen in te stellen. Je moet weten welk object je verkoopteam gebruikt om hun activiteiten vast te leggen.

![](assets/5.png)

U zult waarschijnlijk deze nieuwe touchpoints in hun aangewezen willen plaatsen [Marketingkanaal](https://experience.adobe.com/#/marketo-measure/MyAccount/Business?busView=false&amp;id=10#/!/MyAccount/Business/Account.Settings.SettingsHome?tab=Channels.Online%20 Kanalen){target="_blank"}. U kunt dat doen door het Kanaal met zijn nieuwe afbeelding van de Campagne te bepalen die u enkel creeerde. Misschien zult u een nieuwe rij voor het kanaal BDR creëren waar de Campagne met Uitgaand begint.

>[!TIP]
>
>Gebruik bij het toevoegen van een kanaaldefinitie jokertekenwaarden, een eenvoudigere manier om operatoren als:
>
>begint met ( Uitgaand&#42; )
>
>contains ( &#42;Uitgaand&#42; )
>
>eindigt met ( &#42;Uitgaand )
>
>Geen wilde kaart betekent in feite &quot;is gelijk aan&quot;, dus gebruik ze zo nodig.

| **Operator** | **Hoofdletters gebruiken** |
|---|---|
| Is gelijk aan | Enkele waarde - exact overeenkomend |
| Bevat | Enkele waarde - bevat waarde |
| Komt overeen met alles | Meerdere waarden - Exacte overeenkomst |
| Komt overeen met alle items (bevat) | Meerdere waarden - &#42;value&#42;, &#42;waarde, &#42;value&#42; |

![](assets/6.png)

En last but not least, hebt u de optie om kosten voor uw nieuwe kanalen in te voeren. Ons [Uploaden marketinguitgaven](https://experience.adobe.com/#/marketo-measure/MyAccount/Business?busView=false&amp;id=10#/!/MyAccount/Business/Account.Settings.SettingsHome?tab=Reporting.Marketing%20Spend){target="_blank"} staat u toe om uw uitgaven op het niveau van het Kanaal, Subchannel, of het niveau van de Campagne in te gaan. Met uw nieuwe [!DNL Marketo Measure] Campagnes, kunt u die verwante kosten per maand toevoegen, dan ROI voor elke Campagne zien!

![](assets/7.png)

>[!MORELIKETHIS]
>
>[Veelgestelde vragen over activiteitskenmerk](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)
