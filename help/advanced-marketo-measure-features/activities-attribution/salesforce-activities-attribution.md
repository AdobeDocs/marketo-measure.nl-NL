---
unique-page-id: 18874708
description: Kenmerk Salesforce-activiteiten - [!DNL Marketo Measure]
title: Kenmerk Salesforce-activiteiten
exl-id: 1dc6f15b-2a45-4ed3-9fa3-5267366d1f45
feature: Attribution, Salesforce
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 0%

---

# Kenmerk Salesforce-activiteiten {#salesforce-activities-attribution}

De integratie van [!DNL Marketo Measure] Salesforce-activiteiten maakt specifieke taak- en gebeurtenisrecords in uw toewijzingsmodel. Begin met het volgen van zaken zoals verkoope-mails of telefoongesprekken die geen creditering kregen. Om uw activiteitenregel te vormen, ga [ experience.adobe.com/marketo-measure ](https://experience.adobe.com/marketo-measure){target="_blank"}. Ga vervolgens naar de tab **[!UICONTROL Settings]** en klik op de tab **[!UICONTROL Activities]** .

![](assets/1.png)

>[!AVAILABILITY]
>
>Deze functie is alleen beschikbaar voor klanten van Tier 2. Neem contact op met het Adobe-accountteam (uw accountmanager) als u een hogere accountlaag wilt aanvragen.

Om te beginnen introduceren we een nieuw concept: een [!DNL Marketo Measure] campagne. Voor elke regel die u definieert, gaat u de records vastzetten in een [!DNL Marketo Measure] -campagne die u een naam kunt geven. Voeg zo nodig meerdere campagnes toe. Stel je voor dat je de effectiviteit van een campagne voor uitgaande verkoop naast een campagne voor betaalde media meet!

U gaat deze [!DNL Marketo Measure] Campagnenaam gebruiken om ons te vertellen aan welk kanaal het zou moeten worden in kaart gebracht. Als u nog aan Uitgaande Verkoop overweegt, misschien zouden alle Uitgaande campagnes van de Verkoop in een kanaal BDR moeten zitten.

Bekend maken met deze hiërarchie:

* Kanaal
   * Subkanaal
      * Campaign
      * Campaign
   * Subkanaal
      * Campaign

>[!TIP]
>
>Als u bijvoorbeeld een unieke campagne voor elke vertegenwoordiger wilt instellen, gebruikt u dynamische vervangingsparameters om de [!DNL Marketo Measure] naam van de campagne in te vullen. In hetzelfde voorbeeld kunt u `"Outbound Sales - {AssignedTo}"` invoeren en wijzigen in iets als `"Outbound Sales - Jill"` of `"Outbound Sales - Jack."`

![](assets/2.png)

Zodra uw [!DNL Marketo Measure] Naam van de Campagne wordt geplaatst, is het tijd aan opstelling uw regels van de Activiteit.

De regels fungeren als een filter om ons te vertellen welke records in aanmerking komen voor toekenning. Stel u een rapport in uw CRM creeert gebruikend gelijkaardige logica om dat rapport te produceren. U hebt de flexibiliteit om een combinatie van instructies en/of instructies en verschillende operatoren zoals `matches any` , `contains` , `starts with` , `ends with` en `is equal to` te gebruiken. Definieer `and` -instructies binnen een regel- of laaginstructies in een vak `or` buiten het vak.

![](assets/3.png)

>[!NOTE]
>
>Formulervelden kunnen niet worden gebruikt binnen uw regels en worden niet weergegeven in de keuzelijst. Omdat formules op de achtergrond berekenen en een record niet wijzigen, kan [!DNL Marketo Measure] niet bepalen of een record op een regel past of niet.
>
>Gebruik correcte waarden voor id-velden zoals CrmEvent.CreatedById. [!DNL Salesforce IDs] zijn 18 tekens lang (0054H000007WmrfQAC).

Kies ten slotte een van de datum- of datum-/tijdvelden die u wilt gebruiken als Buyer Touchpoint-datum. Standaard- en aangepaste velden kunnen worden geselecteerd.

>[!TIP]
>
>Bij de pakketinstallatie neemt [!DNL Marketo Measure] een aangepast Buyer Touchpoint-datumveld op in de activiteitenrecord. Als u een dynamische datum wilt gebruiken, zoals de datum waarop een status verandert, is het mogelijk om een CRM-workflow te gebruiken om de &quot;Buyer Touchpoint Date&quot; in te stellen en vervolgens de Buyer Touchpoint Date hier in deze stap te selecteren.

![](assets/4.png)

Vergeet niet verschillende regels voor Taken of Gebeurtenissen in te stellen. Je moet weten welk object je verkoopteam gebruikt om hun activiteiten vast te leggen.

![](assets/5.png)

U zult waarschijnlijk deze nieuwe aanraakpunten in hun aangewezen [ het In de handel brengen Kanaal ](https://experience.adobe.com/#/marketo-measure/MyAccount/Business?busView=false&id=10#/!/MyAccount/Business/Account.Settings.SettingsHome?tab=Channels.Online%20 Kanalen){target="_blank"} willen plaatsen. Doe dat door het Kanaal met zijn nieuwe afbeelding van de Campagne te bepalen die enkel werd gecreeerd.

>[!TIP]
>
>Gebruik bij het toevoegen van een kanaaldefinitie jokertekenwaarden, een eenvoudigere manier om operatoren als:
>
>begint met ( Uitgaand &#42; )
>
>bevat ( &#42; Uitgaand &#42;)
>
>eindigt met ( &#42; Uitgaand)
>
>Geen wilde kaart betekent in feite &quot;is gelijk aan&quot;, dus gebruik ze zo nodig.

| **Exploitant** | **Geval van het Gebruik** |
|---|---|
| Is gelijk aan | Enkele waarde - exact overeenkomend |
| Bevat | Enkele waarde - bevat waarde |
| Komt overeen met alles | Meerdere waarden - Exacte overeenkomst |
| Komt overeen met alle items (bevat) | Veelvoudige waarden - &#42; waarde &#42;, &#42; waarde, &#42; waarde &#42; |

![](assets/6.png)

En last but not least, hebt u de optie om kosten voor uw nieuwe kanalen in te voeren. De [ Marketing besteedt uploadt ](https://experience.adobe.com/#/marketo-measure/MyAccount/Business?busView=false&id=10#/!/MyAccount/Business/Account.Settings.SettingsHome?tab=Reporting.Marketing%20Spend){target="_blank"} staat u toe om uw uitgaven op het niveau van het Kanaal, Subchannel niveau, of het niveau van de Campagne in te gaan. Met uw nieuwe [!DNL Marketo Measure] Campagnes, kunt u die verwante kosten per maand toevoegen, dan het ROI voor elke Campagne zien!

![](assets/7.png)

>[!MORELIKETHIS]
>
>[ Veelgestelde vragen van de Attributie van de Activiteit ](/help/advanced-marketo-measure-features/activities-attribution/activities-attribution-faq.md)
