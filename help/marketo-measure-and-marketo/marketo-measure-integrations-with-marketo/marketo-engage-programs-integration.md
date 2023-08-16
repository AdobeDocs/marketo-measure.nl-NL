---
unique-page-id: 42762729
description: "[!DNL Marketo Engage] Integratie van programma's - [!DNL Marketo Measure] - Productdocumentatie"
title: "[!DNL Marketo Engage] Programmaintegratie"
exl-id: c26087e3-d821-4fe7-bacd-eeaa1530a4b0
feature: Integration
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '1247'
ht-degree: 0%

---

# [!DNL Marketo Engage] Integratie van programma&#39;s {#marketo-engage-programs-integration}

Via de [!DNL Marketo Measure] integratie met [!DNL Marketo Engage] Met programma&#39;s kunnen onze klanten aanraakpunten maken voor het bijhouden van toewijzingen via de Marketo-programmamakers. Met deze functie kunnen marketers hun lidmaatschap van programma&#39;s bijhouden via e-mail- of serviceprogramma&#39;s die anders niet door de [!DNL Marketo Measure] javascript en moet worden gemeten binnen de attributietraject.

## Beschikbaarheid {#availability}

Alle lagen.

## Vereisten {#requirements}

* Production Marketo-instantie
* Production Salesforce of Microsoft Dynamics-instantie
* Betaald [!DNL Marketo Measure] abonnement
* Marketo People Sync Enabled ([!DNL Marketo Measure] Instellingen)
* Marketo-programma&#39;s ingeschakeld ([!DNL Marketo Measure] Instellingen)

## Instellen {#setup}

**Regels**

1. Als u regels voor Marketo-programma&#39;s wilt instellen, navigeert u naar **[!UICONTROL My Account]** > **[!UICONTROL Settings]** > **[!UICONTROL Programs]**. Klik op de knop **+** pictogram om te beginnen met het maken van uw eerste regel.

   ![](assets/one.png)

   ![](assets/two.png)

1. U kunt desgewenst een naam voor de regel instellen als u deze beter kunt bijhouden. U zult eerst het gebied selecteren om uw regel van de lijst van de gebieden van het Programma en van het Lidmaatschap van het Programma te bepalen. Ga door met het bouwen van de regel door de operator en de verwachte waarde te selecteren.

   ![](assets/three.png)

1. Voeg een andere instructie in hetzelfde vak toe om de criteria &quot;en&quot; in de regel in te stellen of klik op het pictogram + buiten het vak om de instructie &quot;of&quot; in te stellen.

   ![](assets/four.png)

1. Kies welke datum- of datum-/tijdveld moet worden gebruikt voor toewijzing aan de datum van het aanraakpunt. Voer een accolade in om de lijst met beschikbare waarden in Marketo weer te geven `{` en we geven de beschikbare velden weer.

   ![](assets/five.png)

   >[!NOTE]
   >
   >Als uw regel de Datum van de Activiteit, of de datum wilt vangen dat een Lid van het Programma een bepaalde status bereikte, zult u willen gebruiken [!DNL Marketo Engage] De Integratie van activiteiten en opstelling een regel voor het &quot;Status van de Verandering in de activiteitstype van de Progressie&quot;.

   ![](assets/six.png)

De voltooide regel moet er ongeveer als volgt uitzien:

## Testen {#test}

Nadat u sommige regels hebt gecreeerd, kunt u het willen uittesten om te verifiëren dat uw verklaring uw Programma&#39;s aanpast.

1. Als u een test wilt uitvoeren, klikt u op de knop **[!UICONTROL TEST]** zoals hieronder weergegeven.

   ![](assets/seven.png)

1. Er wordt een modaal model weergegeven waar u de programma-id vanuit Marketo kunt invoeren.

   ![](assets/eight.png)

   Nadat u de id hebt ingevoerd en op de knop [!UICONTROL Test] knoop, zal onze regelingsmotor door elke regel gaan en bepalen of het Programma om het even welke regels past of niet. In het onderstaande voorbeeld ziet u dat Program 1002, genaamd [!DNL Marketo Measure] Ebook, heeft 5 Leden van het Programma en komt in aanmerking wegens de regel die wordt getoond.

   De regels worden uitgevoerd op steekproefgrootte van 5000 leden. Als uw programma meer dan 5000 leden bevat, is het mogelijk dat wij niet de verenigbaarheid van alle leden controleren. Met dit gereedschap kunt u eenvoudig controleren of de regels correct zijn opgebouwd.

   ![](assets/nine.png)

   Klik op Lid Tellen om een lijst met Marketo People Ids weer te geven die in aanmerking komen voor het programma.

   ![](assets/ten.png)

## Kanaaltoewijzing {#channel-mapping}

Van de lijst van de Kanalen van het Programma van Marketo, zult u de waarden aan in kaart willen brengen [!DNL Marketo Measure] aangepaste marketingkanalen die u hebt gemaakt in Instellingen. Alle aanraakpunten die door deze programma&#39;s worden gegenereerd, nemen de Kanaal- en Subkanaalnamen over die u hier selecteert.

1. Starten door te navigeren naar **[!UICONTROL My Account]** > **[!UICONTROL Settings]** > **[!UICONTROL Offline Channels]**.

1. Bovenaan, zult u de optie hebben om aan uw Types van Campagne van CRM in kaart te brengen, dan onderaan, zult u de opties voor uw Kanalen van het Programma van Marketo zien.

1. Selecteer eerst het kanaal dat aan de waarde zou moeten in kaart brengen, dan naar keuze Subchannel. Als u klaar bent, klikt u **[!UICONTROL Save]** onderaan.

   ![](assets/eleven.png)

## Programmakosten {#program-costs}

Via de gegevensimport van Marketo-programma&#39;s worden de kosten automatisch gedownload van de kosten van de periode en worden de gerapporteerde kosten in Marketo over de toegewezen maand verdeeld. Als bijvoorbeeld $1000 wordt gerapporteerd voor januari 2021, wordt $1000 gesplitst over 31 dagen. De kosten zijn te vinden in [!DNL Marketo Measure Discover].

## Hoe het werkt {#how-it-works}

**Veldtoewijzingen**

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

Als gevolg van de [!DNL Marketo Measure] de integratie met Marketo [!DNL Marketo Measure] De cookie-id is nu ook toegewezen en gesynchroniseerd met de [!DNL Marketo Munchkin Id]. Zo kunt u de tussenruimte dichten en de anonieme eerste aanraking toewijzen aan een websessie in plaats van zowel de FT- als de LC-aanraking toe te wijzen aan een Marketo-activiteit. Stel je dit scenario voor:

Markeren klikt op een [!DNL Facebook] en landt op wayneenterprises.com waar hij gekookt wordt [!DNL Marketo Measure] ID 123 en [!DNL Marketo Munchkin Id] 456. Er vindt geen formuliervulling plaats.

Het Wayne Enterprises Marketing-team stuurt een e-mailoverzicht naar specifieke beoogde leads, waarbij een van hen `mark@email.com`.

`mark@email.com` ontvangt de e-mail en klikt en landt op wayneenterprises.com. Dit wordt `mark@email.com's` tweede bezoek aan `wayneenterprise.com` met dezelfde cookie-id, maar er was geen formuliervulling, dus om [!DNL Marketo Measure], zij zijn nog steeds een anonieme bezoeker.

Het Wayne Enterprises Marketing-team maakt een Marketo Activity-regel om aanraakpunten te genereren voor een activity type &quot;Click Email&quot;.

De implementatie van vandaag zou één enkel FT en LC aanraakpunt voor creëren `mark@email.com` van de Activiteit van Marketo van het type van &quot;klikE-mail&quot;activiteit.

Met deze functie voor het toewijzen van cookies gaat de FT terug en wordt deze gecrediteerd aan de [!DNL Facebook] en de LC worden gecrediteerd voor de e-mail.

>[!NOTE]
>
>Met het gedrag van de koekjesafbeelding, kunt u sommige aanraakpunten vinden LC die van een Webbezoek komen. Het is mogelijk dat er een lead verscheen in Marketo zonder enige bijbehorende activiteit, dan [!DNL Marketo Measure] Deze lead is gedownload, er zijn overeenkomende cookies in opgenomen en vervolgens naar de meest recente websessie geleid, zelfs als de lead niet via een formulieractiviteit is gemaakt.

## Veelgestelde vragen {#faq}

**Hoe stel ik de aanraakpuntdatum in op de progressiedatum, of de datum waarop de statuswijziging is gebeurd met mijn programmalid?**

Als uw regel de Datum van de Activiteit, of de datum wilt vangen dat een Lid van het Programma een bepaalde status bereikte, zult u willen gebruiken [!DNL Marketo Engage] De Integratie van activiteiten en opstelling een regel voor het &quot;Status van de Verandering in de activiteitstype van de Progressie&quot;. Anders wordt de [!DNL Marketo Engage] Programs Integration stelt alleen de Membership Date beschikbaar, de eerste datum waarop de Marketo Person in het Programma is opgenomen, zelfs als er meerdere statussen zijn.

**Kan ik een keuzelijst met datumopties voor het aanraakpunt Date krijgen?**

Als u het automatisch aanvullen wilt activeren, begint u met het invoeren van een accolade. `{` in het tekstveld worden de beschikbare velden weergegeven.

**Als ik regels van het Marketo-programma stel en ook regels voor CRM-campagne heb, tellen ze dan twee keer?**

Het hangt van uw regeldefinitie af, maar misschien, ja. U zult uw regelreeks willen evalueren zodat u geen regels hebt die een Programma en een Campagne behandelen omdat wij niet voor gelijkaardige lidmaatschappen zullen dedupliceren of ontdekken. Een mogelijke oplossing is om uw regels voor campagnes over te brengen naar Programma&#39;s als u wilt dat Marketo uw enige bron van waarheid is, en vervolgens de regels voor campagnes te verwijderen. Een andere optie is om de criteria &quot;CreatedOn&quot;of &quot;CreatedDate&quot;in uw regels toe te voegen zodat de regels vóór een bepaalde datum de regels en de regels van de Campagne na een bepaalde datum zullen gebruiken de regels van het Programma. Er zijn veel problemen, maar er zal enige planning en coördinatie nodig zijn.

**Zijn aangepaste velden voor Marketo-lidmaatschap beschikbaar om te definiëren?**

Vanwege technische beperkingen kunnen we momenteel geen ondersteuning bieden voor aangepaste velden voor programmalidmaatschap. Zodra deze velden beschikbaar zijn via extra Marketo API&#39;s, worden ze voor u toegankelijk en zichtbaar.

**Hoe weet ik of ik Programma&#39;s of Activiteiten moet gebruiken?**

De [!DNL Marketo Engage] De Integratie van programma&#39;s is een eenvoudige manier om aanraakpunten te produceren die op worden gebaseerd of een Persoon een programmalid van een programma is of niet. Als u in het bepalen van een regel geinteresseerd bent die op de tijd wordt gebaseerd een Persoon in een bepaalde status van het Programma verandert, [!DNL Marketo Engage] De Integratie van activiteiten zal de opstelling zijn u, specifiek het &quot;Status van de Verandering in de activiteitstype van de Progressie&quot;wilt.
