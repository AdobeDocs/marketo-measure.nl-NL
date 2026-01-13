---
description: '[!DNL Marketo Engage] Integratie van programma''s -  [!DNL Marketo Measure]'
title: '[!DNL Marketo Engage] Integratie van programma''s'
exl-id: c26087e3-d821-4fe7-bacd-eeaa1530a4b0
feature: Integration
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '1375'
ht-degree: 0%

---


# [!DNL Marketo Engage] Integratie van programma&#39;s {#marketo-engage-programs-integration}

Via de [!DNL Marketo Measure] integratie met [!DNL Marketo Engage] -programma&#39;s kunnen onze klanten aanraakpunten maken voor het bijhouden van toewijzingen via de Marketo-programmamakers. Dankzij deze mogelijkheid kunnen marketers hun lidmaatschap van programma&#39;s bijhouden vanaf e-mail- of betrokkenheidsprogramma&#39;s die anders niet door de javascript van [!DNL Marketo Measure] worden gezien en die binnen de attributietraject moeten worden gemeten.

## Beschikbaarheid {#availability}

Alle lagen.

## Vereisten {#requirements}

* Production Marketo-instantie
* Production Salesforce of Microsoft Dynamics-instantie
* Alle betaalde [!DNL Marketo Measure] -abonnementen
* Marketo People Sync Enabled ([!DNL Marketo Measure] Instellingen)
* Marketo-programma&#39;s ingeschakeld ([!DNL Marketo Measure] Instellingen)

## Instellen {#setup}

**Regels**

1. Navigeer naar **[!UICONTROL My Account]** > **[!UICONTROL Settings]** > **[!UICONTROL Programs]** om regels voor Marketo-programma&#39;s in te stellen. Klik op het pictogram **+** om de eerste regel te maken.

   ![&#x200B; pagina van de montages van Programma&#39;s in de rekening van Marketo Measure &#x200B;](assets/one.png)

   ![&#x200B; creeer nieuwe regeldialoog met toevoegen knoop &#x200B;](assets/two.png)

1. U kunt desgewenst een naam voor de regel instellen als u deze beter kunt bijhouden. u zult eerst het gebied selecteren om uw regel van de lijst van het Programma en de gebieden van het Lidmaatschap van het Programma te bepalen. Ga door met het bouwen van de regel door de operator en de verwachte waarde te selecteren.

   ![&#x200B; Bouwer van de Regel met de dropdown van de gebiedsselectie en exploitant opties &#x200B;](assets/three.png)

1. Voeg een andere instructie in hetzelfde vak toe om de criteria &quot;en&quot; in de regel in te stellen of klik op het pictogram + buiten het vak om de instructie &quot;of&quot; in te stellen.

   ![&#x200B; Bouwer van de Regel die veelvoudige voorwaarden met en/of logische opties toont &#x200B;](assets/four.png)

1. Kies welke datum- of datum-/tijdveld moet worden gebruikt voor toewijzing aan de datum van het aanraakpunt. Als u de lijst met waarden die beschikbaar zijn in Marketo wilt weergeven, voert u een accolade `{` in en geeft u de beschikbare velden weer.

   ![&#x200B; het gebiedstoewijzing van de Datum met autocomplete dropdown tonen beschikbare gebieden &#x200B;](assets/five.png)

   >[!NOTE]
   >Als uw regel de Datum van de Activiteit, of de datum wilt vangen dat een Lid van het Programma een bepaalde status bereikte, zult u [!DNL Marketo Engage] de Integratie van Activiteiten willen gebruiken en opstelling een regel voor het &quot;Status van de Verandering in de activiteitstype van de Progressie&quot;.

   ![&#x200B; Voltooide regelconfiguratie die gebiedstoewijzingen en voorwaarden tonen &#x200B;](assets/six.png)

De voltooide regel moet er ongeveer als volgt uitzien:

## Testen {#test}

Nadat u sommige regels hebt gecreeerd, kunt u het willen uittesten om te verifiëren dat uw verklaring uw Programma&#39;s aanpast.

1. Als u een test wilt uitvoeren, klikt u op de knop **[!UICONTROL TEST]** zoals hieronder wordt weergegeven.

   ![&#x200B; knoop van de Test in interface van programmalijnen &#x200B;](assets/seven.png)

1. Er wordt een modaal model weergegeven waar u de programma-id vanuit Marketo kunt invoeren.

   ![&#x200B; de modale dialoog van de Test met de inputgebied van identiteitskaart van het Programma &#x200B;](assets/eight.png)

   Nadat u de id hebt ingevoerd en op de knop [!UICONTROL Test] hebt geklikt, controleert de regelengine elke regel en of het programma aan een van de regels voldoet. In het onderstaande voorbeeld ziet u dat Program 1002, genaamd [!DNL Marketo Measure] Ebook, vijf programmaleden heeft en in aanmerking komt vanwege de regel die wordt weergegeven.

   De regels worden uitgevoerd op steekproefgrootte van 5000 leden. Als uw programma meer dan 5000 leden bevat, is het mogelijk dat wij niet de verenigbaarheid van alle leden controleren. Met dit gereedschap kunt u eenvoudig controleren of de regels correct zijn opgebouwd.

   ![&#x200B; de resultaten van de Test die aangepast programma met lidtelling tonen &#x200B;](assets/nine.png)

   Klik op Lidmaatschap om een lijst weer te geven met Marketo People Ids die in aanmerking komen voor het programma.

   ![&#x200B; Lijst van in aanmerking komende Marketo Mensen IDs van testresultaten &#x200B;](assets/ten.png)

## Kanaaltoewijzing {#channel-mapping}

In de lijst met Marketo Program Channels wilt u de waarden toewijzen aan de aangepaste [!DNL Marketo Measure] marketingkanalen die u hebt gemaakt in Instellingen. Alle aanraakpunten die door deze programma&#39;s worden gegenereerd, nemen de Kanaal- en Subkanaalnamen over die u hier selecteert.

1. Navigeer eerst naar **[!UICONTROL My Account]** > **[!UICONTROL Settings]** > **[!UICONTROL Offline Channels]** .

1. Bovenaan hebt u de optie om een toewijzing te maken aan uw CRM-cameratypen, en onderaan ziet u de opties voor uw Marketo-programmakanalen.

1. Selecteer eerst het kanaal dat aan de waarde zou moeten in kaart brengen, dan naar keuze Subchannel. Als u klaar bent, klikt u op **[!UICONTROL Save]** onderaan.

   ![&#x200B; Off-line montages van Kanalen die de toewijzingsopties van het Kanaal van het Programma van Marketo tonen &#x200B;](assets/eleven.png)

## Programmakosten {#program-costs}

Via de gegevensimport van Marketo-programma&#39;s worden de kosten automatisch gedownload van de kosten van de periode en worden de gerapporteerde kosten in Marketo over de toegewezen maand verdeeld. Als bijvoorbeeld $1000 wordt gerapporteerd voor januari 2021, wordt $1000 gesplitst over 31 dagen. De kosten vindt u in [!DNL Marketo Measure Discover] .

>[!NOTE]
>
>Marketo Measure ondersteunt slechts één prijsvermelding voor de periode per maand. Om ervoor te zorgen dat alle kosten worden ingevoerd, telt u de totale maandelijkse kosten samen in één keer. Meerdere Periode-kosten voor dezelfde maand worden niet ondersteund.

## Hoe het werkt {#how-it-works}

**Toewijzingen van het Gebied**

<table>
 <colgroup>
  <col>
  <col>
 </colgroup>
 <tbody>
  <tr>
   <th>biz_ad_campagnes</th>
   <th>Marketo</th>
  </tr>
  <tr>
   <td>ID</td>
   <td>id</td>
  </tr>
  <tr>
   <td>IS_DELETED</td>
   <td>(controleer of Programma nog steeds bestaat via API)</td>
  </tr>
  <tr>
   <td><p>NAAM</p></td>
   <td>name</td>
  </tr>
 </tbody>
</table>

| biz_campagne_members | Marketo |
|---|---|
| ID | &quot;MarketoProgramMembership&quot;_ProgramId_Lead-id |
| MODIFIED_DATE | updatedAt |
| CREATED_DATE | membershipDate |
| LEAD_ID | Id (lijstlidmaatschap) |
| LEAD_EMAIL | E-mail (lidmaatschap lijst) |
| STATUS | progressionStatus |
| HAS_RESPONDED | hitStatus |
| CAMPAIGN_NAME | programName |
| CAMPAIGN_ID | programId |
| CAMPAIGN_TYPE | kanaal |

## Cookie-toewijzing {#cookie-mapping}

Dankzij de [!DNL Marketo Measure] -integratie met Marketo wordt de [!DNL Marketo Measure] cookie-id nu ook toegewezen en gesynchroniseerd met de [!DNL Marketo Munchkin Id] . Zo kunt u de tussenruimte dichten en de anonieme eerste aanraking toewijzen aan een websessie in plaats van zowel de FT- als de LC-aanraking toe te wijzen aan een Marketo-activiteit. Stel je dit scenario voor:

Mark klikt op een [!DNL Facebook] advertentie en landt op wayneenterprises.com waar hij gekookt wordt met [!DNL Marketo Measure] Id 123 en [!DNL Marketo Munchkin Id] 456. Er vindt geen formuliervulling plaats.

Het Wayne Enterprises Marketing-team stuurt een e-mailexplosie naar specifieke beoogde leads, waaronder `mark@email.com` .

`mark@email.com` ontvangt het e-mailbericht en klikt en landt op wayneenterprises.com. Dit wordt een `mark@email.com's` tweede bezoek aan `wayneenterprise.com` met dezelfde cookie-id, maar er is geen formuliervulling. In [!DNL Marketo Measure] zijn ze dus nog steeds een anonieme bezoeker.

Het Wayne Enterprises Marketing-team maakt een Marketo Activity-regel om aanraakpunten te genereren voor een activity type &quot;Click Email&quot;.

De implementatie van vandaag zou één enkel aanraakpunt van FT en van LC voor `mark@email.com` van de Activiteit van Marketo van het &quot;Klik E-mail&quot;activiteitstype tot stand brengen.

Met deze functie voor het toewijzen van cookies gaat de FT terug en wordt de [!DNL Facebook] -advertentie gecrediteerd en wordt de LC gecrediteerd voor de e-mail.

>[!NOTE]
>Met het gedrag van de koekjesafbeelding, kunt u sommige aanraakpunten vinden LC die van een Webbezoek komen. Het is mogelijk dat een lead in Marketo verschijnt zonder bijbehorende activiteit, en dat [!DNL Marketo Measure] die lead heeft gedownload, de bijbehorende cookies heeft gevonden en deze vervolgens naar de meest recente websessie heeft getraceerd, zelfs als er geen formulieractiviteit was die de lead heeft gemaakt.

## Veelgestelde vragen {#faq}

**Hoe plaats ik de Datum van het Aanraakpunt om de progressiedatum te zijn, of datum dat de statusverandering met mijn Lid van het Programma gebeurde?**

Als uw regel de Datum van de Activiteit, of de datum wilt vangen dat een Lid van het Programma een bepaalde status bereikte, zult u [!DNL Marketo Engage] de Integratie van Activiteiten willen gebruiken en opstelling een regel voor het &quot;Status van de Verandering in de activiteitstype van de Progressie&quot;. Anders stelt de [!DNL Marketo Engage] Integratie van Programma&#39;s slechts de Datum van het Lidmaatschap ter beschikking, die de eerste datum is die de Persoon van Marketo in het Programma bracht, zelfs als er veelvoudige statussen zijn.

**kan ik een picklist van datumopties voor de Datum van het Aanraakpunt krijgen?**

Als u het automatisch aanvullen wilt activeren, begint u met het invoeren van een accolade `{` in het tekstveld, worden de beschikbare velden weergegeven.

**als ik de regels van het Programma van Marketo creeer en ook de regels van de Campagne van CRM heeft, zullen zij tweemaal tellen?**

Het hangt van uw regeldefinitie af, maar misschien, ja. u zult uw regelreeks willen evalueren zodat u geen regels hebt die een Programma en een Campagne behandelen omdat wij niet voor gelijkaardige lidmaatschappen zullen dedupliceren of ontdekken. Een mogelijke oplossing is om uw regels voor campagnes over te brengen naar Programma&#39;s als u wilt dat Marketo uw enige bron van waarheid is, en vervolgens de regels voor campagnes te verwijderen. Een andere optie is om de criteria &quot;CreatedOn&quot;of &quot;CreatedDate&quot;in uw regels toe te voegen zodat de regels vóór een bepaalde datum de regels en de regels van de Campagne na een bepaalde datum zullen gebruiken de regels van het Programma. Er zijn veel problemen, maar er zal enige planning en coördinatie nodig zijn.

**Zijn de Beschikbare Gebieden van de Aangepast van het Lidmaatschap van Marketo van het Programma beschikbaar om te bepalen?**

Vanwege technische beperkingen kunnen we momenteel geen ondersteuning bieden voor aangepaste velden voor programmalidmaatschap. Zodra deze velden beschikbaar zijn via extra Marketo API&#39;s, worden ze voor u toegankelijk en zichtbaar.

**Hoe weet ik of om Programma&#39;s of Activiteiten te gebruiken?**

De integratie van programma&#39;s [!DNL Marketo Engage] is een eenvoudige manier om aanraakpunten te genereren op basis van het feit of een persoon al dan niet lid is van een programma. Als u in het bepalen van een regel geinteresseerd bent die op de tijd wordt gebaseerd een Persoon in een bepaalde status van het Programma verandert, zal de [!DNL Marketo Engage] Integratie van Activiteiten de opstelling zijn u zult willen, specifiek het &quot;Status van de Verandering in de Voortgang&quot;activiteitstype.
