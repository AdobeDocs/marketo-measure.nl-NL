---
description: '[!DNL Facebook] API -  [!DNL Marketo Measure]'
title: '[!DNL Facebook] API'
exl-id: d6d18545-baae-4103-b0a6-c3de681ec833
feature: APIs, Integration, UTM Parameters
hidefromtoc: true
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 1%

---

# [!DNL Facebook] API {#facebook-api}

## Inleiding {#introduction}

Net als bij onze integratie van Advertentiewoorden en -[!DNL Bing Ads] doet onze [!DNL Facebook] -integratie twee fundamentele acties:

* Automatisch alle [!DNL Facebook] Advertenties labelen met een [!DNL Marketo Measure] -parameter (_bf)
* Informatie over alle actieve Facebook-advertenties downloaden en kosten besparen

## De [!DNL Facebook] integratie configureren {#how-to-configure-the-facebook-integration}

Voor de installatie moeten er zeven stappen worden uitgevoerd in de app [!DNL Marketo Measure] .

1. Navigeer aan [ experience.adobe.com/marketo-measure ](https://experience.adobe.com/marketo-measure){target="_blank"} en login.
1. Selecteer onder Mijn account **[!UICONTROL Settings]** .
1. Selecteer onder Integraties **[!UICONTROL Connections]** .
1. Selecteer **[!UICONTROL Set Up New Ads Connection]** en er verschijnt een pop-up. Selecteer **[!UICONTROL Facebook]** en meld u aan met uw Facebook-referenties.

   >[!NOTE]
   >
   >De persoon die de [!DNL Facebook Ads] -account aansluit, moet een beheerder zijn binnen de [!DNL Facebook Ads] -account.

1. Zodra [!DNL Marketo Measure] is verbonden met uw Facebook-account, klikt u op het potloodpictogram naast de account.
1. Verplaats in deze weergave de optie Automatisch labelen? schakelen naar &#39;Ja&#39;. Schakel vervolgens het selectievakje in de sectie [!UICONTROL Learn More] in om akkoord te gaan met de voorwaarden. Zorg ervoor de [!UICONTROL Auto-tagging] knevel nog aan &quot;[!UICONTROL Yes]&quot;wordt geplaatst.

## De account verbinden {#connecting-the-account}

![](assets/utilizing-connections-2.gif)

## Automatisch labelen inschakelen {#enabling-autotagging}

>[!NOTE]
>
>Als u automatische labeling inschakelt, stellen we de omzetgeschiedenis en het sociale bewijs van alle advertenties die we labelen opnieuw in. Wij adviseren hoogst [ het uitvoeren van deze gegevens als CSV ](https://www.facebook.com/business/help/205067636197240) alvorens u auto-etiketteren toelaat.

![](assets/bizible-guide-1.png)

Zodra u de integratie hebt ingeschakeld, begint [!DNL Marketo Measure] met het downloaden van ad-level kosten naar het [!DNL Marketo Measure Marketing ROI] -dashboard.

De integratie werkt alleen correct als u automatische labeling voor uw [!DNL Facebook] -account inschakelt. Hierdoor kan ons systeem een _bf-parameter toevoegen aan alle advertentiekoppelingen. Tijdens dit proces wordt de nieuwe parameter toegevoegd boven op andere trackingparameters die u al hebt toegevoegd aan uw [!DNL Facebook] -advertenties.

![](assets/five-five-1.png)

## Veldtoewijzing {#field-mapping}

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th><p><strong>Aanraakpuntveld</strong></p></th> 
   <th><p><strong>Waarde</strong></p></th> 
  </tr> 
  <tr> 
   <td><p>Campagne-id toevoegen</p></td> 
   <td><p>[[!DNL Facebook] Campagne-id]</p></td> 
  </tr> 
  <tr> 
   <td><p>Naam advertentiecampagne </p></td> 
   <td><p>[[!DNL Facebook] Campagnenaam], of [utm_campagne] indien opgegeven</p></td> 
  </tr> 
  <tr> 
   <td><p>Groep-id toevoegen</p></td> 
   <td><p>[[!DNL Facebook] Id van advertentieset]</p></td> 
  </tr> 
  <tr> 
   <td><p>Naam advertentiegroep</p></td> 
   <td><p>[[!DNL Facebook] Naam van advertentieset]</p></td> 
  </tr> 
  <tr> 
   <td><p>Aanraakpunt Source</p></td> 
   <td><p>"[!DNL Facebook]", of [utm_source] indien opgegeven</p></td> 
  </tr> 
  <tr> 
   <td><p>Medium</p></td> 
   <td><p>"Sociaal" of [utm_medium] indien verstrekt</p></td> 
  </tr> 
  <tr> 
   <td><p>Advertentiecode, of Creative_Unique_Id (Data Warehouse)</p></td> 
   <td><p>[aangepaste id gegenereerd door utm_content]</p></td> 
  </tr> 
  <tr> 
   <td><p>Inhoud toevoegen, of Creative_Name (Data Warehouse)</p></td> 
   <td><p>[utm_content] indien opgegeven</p></td> 
  </tr> 
  <tr> 
   <td><p>Trefwoordtekst of Trefwoord_naam (Data Warehouse)</p></td> 
   <td><p>[utm_term] indien opgegeven</p></td> 
  </tr> 
  <tr> 
   <td><p>ad_unique_id (Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook] Advertentie-id]</p></td> 
  </tr> 
  <tr> 
   <td><p>Advertentie_Naam (Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook] Advertentienaam]</p></td> 
  </tr> 
  <tr> 
   <td><p>Trefwoord_Unique_Id (Data Warehouse)</p></td> 
   <td><p>[aangepaste id gegenereerd op basis van utm_term]</p></td> 
  </tr> 
  <tr> 
   <td><p>Advertentieleverancier (Data Warehouse)</p></td> 
   <td><p>"[!DNL Facebook]"</p></td> 
  </tr> 
  <tr> 
   <td><p>Account_Unique_ID (Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook] Rekeningnummer]</p></td> 
  </tr> 
  <tr> 
   <td><p>Account_Name (Data Warehouse)</p></td> 
   <td><p>[[!DNL Facebook] Accountnaam]</p></td> 
  </tr> 
 </tbody> 
</table>

## Veelgestelde vragen {#faq}

**Q: Welke [!DNL Facebook] Advertenties door [!DNL Marketo Measure] worden gesteund?**

A: Carrousel, enkele afbeelding. Op dit moment geen video, presentatie of verzameling.

**Q: Wat is sociaal bewijs?**

A: Sociale proefdrukken is zichtbare betrokkenheid, zoals zoals bijvoorbeeld klikken, opmerkingen en shares.

**Q: Wat gebeurt wanneer [!DNL Marketo Measure] markeringen Advertentie?**

A: [!DNL Facebook] staat niet toe dat advertenties worden bewerkt, zodat [!DNL Marketo Measure] de creatieve inhoud moet verwijderen, die de doel-URL bevat, en de advertentie vervolgens opnieuw moet maken met de nieuwe parameters.

**Q: Waarom [!DNL Marketo Measure] werkt alle [!DNL Facebook] Advertenties bij?**

A: Het proces [!DNL Marketo Measure] bestaat uit het labelen van alle advertenties voor het geval deze opnieuw worden geactiveerd.

**Q: Welke toestemming vereist de verbonden gebruiker?**

A: advertenties_beheer, e-mail

**Q: Hoe lang kan het duren om uitgavengegevens in te voeren?**

A: 1 uur

**Q: Hoe lang kan het aan invoer en gegevens vergen?**

A: 4 uur
