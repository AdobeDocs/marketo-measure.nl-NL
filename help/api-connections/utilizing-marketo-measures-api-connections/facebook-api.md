---
unique-page-id: 18874680
description: "[!DNL Facebook] API - [!DNL Marketo Measure] - Productdocumentatie"
title: "[!DNL Facebook] API"
exl-id: d6d18545-baae-4103-b0a6-c3de681ec833
feature: APIs, Integration, UTM Parameters
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 0%

---

# [!DNL Facebook] API {#facebook-api}

## Inleiding {#introduction}

Vergelijkbaar met onze Advertentiewoorden &amp; [!DNL Bing Ads] integratie, onze [!DNL Facebook] integratie omvat twee fundamentele acties :

* Alle tags automatisch labelen [!DNL Facebook] Toevoegen met een [!DNL Marketo Measure] parameter (_bf)
* Download- en kostengegevens over alle actieve Facebook-advertenties

## Hoe te om te vormen [!DNL Facebook] Integratie {#how-to-configure-the-facebook-integration}

Wat de installatie betreft, moeten er zeven stappen worden uitgevoerd binnen de [!DNL Marketo Measure] app.

1. Navigeren naar [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} en aanmelden.
1. Onder Mijn account selecteren **[!UICONTROL Settings]**.
1. Onder Integratie selecteren **[!UICONTROL Connections]**.
1. Selecteren **[!UICONTROL Set Up New Ads Connection]** en wordt er een pop-up weergegeven. Selecteren **[!UICONTROL Facebook]** en meld u aan met uw Facebook-gebruikersgegevens.

   >[!NOTE]
   >
   >De persoon die de [!DNL Facebook Ads] account moet een beheerder zijn binnen de [!DNL Facebook Ads] account.

1. Eenmaal [!DNL Marketo Measure] is verbonden met uw Facebook-account, klikt u op het potloodpictogram naast de account.
1. Verplaats in deze weergave de optie Automatisch labelen? schakelen naar &#39;Ja&#39;. Schakel vervolgens het selectievakje in in het dialoogvenster [!UICONTROL Learn More] om akkoord te gaan met de voorwaarden. Zorg ervoor dat de [!UICONTROL Auto-tagging] toggle is nog steeds ingesteld op &#39;[!UICONTROL Yes]&quot;.

## De account verbinden {#connecting-the-account}

![](assets/1.gif)

## Automatisch labelen inschakelen {#enabling-autotagging}

>[!NOTE]
>
>Als u automatische labeling inschakelt, stellen we de omzetgeschiedenis en het sociale bewijs van alle advertenties die we labelen opnieuw in. We raden u aan [deze gegevens exporteren als CSV](https://www.facebook.com/business/help/205067636197240) voordat u automatische labeling inschakelt.

![](assets/2-2.png)

Zodra u de integratie hebt toegelaten, [!DNL Marketo Measure] worden kosten op advertentieniveau gedownload naar de [!DNL Marketo Measure Marketing ROI] Dashboard.

De integratie werkt alleen correct als u automatische labeling hebt ingeschakeld voor uw [!DNL Facebook] account. Hierdoor kan ons systeem een _bf-parameter toevoegen aan alle advertentiekoppelingen. Dit proces zal de nieuwe parameter bovenop andere het volgen parameters toevoegen u reeds aan uw hebt toegevoegd [!DNL Facebook] advertenties.

![](assets/3.gif)

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
   <td><p>[[!DNL Facebook] Id advertentieset]</p></td> 
  </tr> 
  <tr> 
   <td><p>Naam advertentiegroep</p></td> 
   <td><p>[[!DNL Facebook] Naam advertentieset]</p></td> 
  </tr> 
  <tr> 
   <td><p>Aanraakpuntbron</p></td> 
   <td><p>"[!DNL Facebook]", of [utm_source] indien opgegeven</p></td> 
  </tr> 
  <tr> 
   <td><p>Normaal</p></td> 
   <td><p>"Sociaal" of [utm_medium] indien verstrekt</p></td> 
  </tr> 
  <tr> 
   <td><p>Advertentiecode, of Creative_Unique_Id (Data Warehouse)</p></td> 
   <td><p>[aangepaste id gegenereerd door utm_content]</p></td> 
  </tr> 
  <tr> 
   <td><p>Inhoud toevoegen of Creative_Name (Data Warehouse)</p></td> 
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
   <td><p>AD_Provider (Data Warehouse)</p></td> 
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

**V: Wat [!DNL Facebook] Advertenties worden ondersteund door [!DNL Marketo Measure]?**

A: Carrousel, enkele afbeelding. Op dit moment geen video, presentatie of verzameling.

**V: Wat is sociaal bewijs?**

A: Sociale proefdrukken is zichtbare betrokkenheid, zoals zoals bijvoorbeeld klikken, opmerkingen en shares.

**Q: Wat gebeurt er als [!DNL Marketo Measure] -tags toevoegen aan de advertentie?**

A: [!DNL Facebook] staat bewerken van advertenties niet toe [!DNL Marketo Measure] moet creatief schrappen, dat de Bestemming URL bevat, en dan de advertentie met de nieuwe parameters opnieuw creëren.

**Q: Waarom doet [!DNL Marketo Measure] alles bijwerken [!DNL Facebook] Advertenties?**

A: De [!DNL Marketo Measure] Alle advertenties moeten worden gecodeerd als ze opnieuw worden geactiveerd.

**V: Welke toestemming heeft de verbonden gebruiker nodig?**

A: advertenties_beheer, e-mail

**V: Hoe lang duurt het om uitgavengegevens te importeren?**

A: 1 uur

**V: Hoe lang duurt het om gegevens te importeren?**

A: 4 uur
