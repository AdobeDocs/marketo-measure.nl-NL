---
unique-page-id: 18874610
description: De Campagnes van de dynamiek en de Marketing Lijsten -  [!DNL Marketo Measure]
title: Dynamische campagnes en marketinglijsten
exl-id: 7b3d4032-5edf-489d-b86b-1e2a5755b258
feature: Microsoft Dynamics
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 0%

---

# Dynamische campagnes en marketinglijsten {#dynamics-campaigns-and-marketing-lists}

>[!NOTE]
>
>Dit artikel behandelt een verouderd proces. Wij moedigen gebruikers aan om het [ nieuwe, verbeterde in-app proces ](/help/channel-tracking-and-setup/offline-channels/custom-campaign-sync.md){target="_blank"} te gebruiken.

## Campagnes {#campaigns}

De Campagnes van de dynamiek zijn goed voor het volgen van off-line marketing activiteit en het opnemen van hen in de omni-kanaalreis. De campagnes moeten op Leads of Contacten betrekking hebben en kunnen of tot de Campagne door of de Reacties van de Campagne of de Lijsten van de Marketing rollen.

## Campagnereacties {#campaign-responses}

Wanneer de Leads of de Contacten rechtstreeks aan een Campagne worden toegevoegd, zijn zij ingegaan als verslag van de Reactie van de Campagne.

![](assets/1.png)

## Aanraakpunten inschakelen {#enable-touchpoints}

Om deze verslagen in touchpoint reis te omvatten, zijn er een paar opties voor de types van de Reacties van de Campagne aan synchronisatie. Voor het verslag van de Campagne, zou er een douanegebied van de geïnstalleerde oplossing geëtiketteerd, &quot;[!UICONTROL Enable Buyer Touchpoints] moeten zijn.&quot; Als dit niet wordt weergegeven, moet het veld worden toegevoegd via de formuliereditor.

![](assets/2.png)

U kunt selecteren om alle verslagen op te nemen die een Reactie van de Campagne in de Campagne hebben, of slechts die met een Reactie van &quot;Geïnteresseerde,&quot;of door gebrek, kunt u de Reacties van de Campagne bij allen niet omvatten. U kunt het veld leeg laten of expliciet uitsluiten.

[!DNL Marketo Measure] biedt geen ondersteuning voor aangepaste reactiewaarden.

![](assets/3.png)

Dit zijn de reactiewaarden van de voorraad voor de Campagne Reactie:

![](assets/4.png)

Gebaseerd op uw selectie, zijn deze verslagen nu verkiesbaar voor aanraakpunten in de reis van de Lood, van het Contact, of van de Kans. Als ze hiervoor in aanmerking komen, verschijnt er op de reis een aanraakpunt met de titel &quot;Dynamics Campaign&quot;.

Een reden dat een reactie van de Campagne niet kan verschijnen is omdat een Eerste Aanraking en/of Aanraking van de Lood reeds activiteit voor de Lood/het Contact was geregistreerd en de eigenschap &quot;PostLC&quot;gehandicapt is of zijn maximumaantal aanraakpunten heeft bereikt.

## Aanraakpuntdatum {#touchpoint-date}

De aanraakpuntdatum voor een campagne bevindt zich gewoonlijk op de datum waarop de campagnereactie aan de campagne is toegevoegd. Het kan worden met voeten getreden als het douanegebied van de geïnstalleerde oplossing geëtiketteerd, &quot;Datum van Buyer Touchpoint,&quot;bevolkt is. Als dit niet wordt weergegeven, moet het veld worden toegevoegd via de formuliereditor.

Dit veld wordt veel gebruikt voor gebeurtenissen waarbij een lijst met badge-scans van een gebeurtenis wordt toegevoegd aan de CRM-dagen nadat de gebeurtenis heeft plaatsgevonden, zodat de gebruiker de Buyer Touchpoint-datum kan wijzigen van het moment waarop de gebeurtenis heeft plaatsgevonden.

![](assets/5.png)

## Marketinglijsten {#marketing-lists}

Marketing List is een andere manier om leads of contactpersonen op te nemen in een marketingreis. Marketinglijsten zijn uniek voor een groep leads of contactpersonen. Dit betekent dat de gebruiker moet bepalen of de lijst een set leads of een set contactpersonen is.

[!DNL Marketo Measure] ondersteunt alleen statische marketinglijsten. Dynamische marketinglijsten worden niet ondersteund omdat de verwerking vereist dat we de Gewijzigde datum van een record inchecken, maar omdat een dynamische lijst vaak wordt gewijzigd, is er geen Gewijzigde datum waarop [!DNL Marketo Measure] moet worden gecontroleerd. Dit zou een constante download van de volledige gegevensreeks door de dag vereisen.

![](assets/6.png)

De bovenstaande schermafbeelding is een marketinglijst voor leads. Marketinglijsten zijn gekoppeld aan campagnes en kunnen worden gekoppeld aan meerdere campagnes. Tenzij u slechts één Marketing List voor één Campagne creeert, adviseert [!DNL Marketo Measure] niet dat de klanten de Lijsten van de Marketing gebruiken om hun Campagnes te volgen. Het is onwaarschijnlijk dat dezelfde exacte lijst van leads/contactpersonen in aanmerking komt voor aanraakpunten in meerdere campagnes.

## Aanraakpunten inschakelen {#enable-touchpoints-1}

Om een Lijst van de Marketing voor touchpoints toe te laten, is er een afzonderlijke het plaatsen op het verslag van de Campagne geëtiketteerd, &quot;[!UICONTROL Sync Marketing Lists],&quot;wat een eenvoudige ja/neen schakelaar is. Als dit niet wordt weergegeven, moet het veld worden toegevoegd via de formuliereditor. Terwijl op het verslag van de Campagne, kunt u zien welke Lijsten van de Marketing met de Campagne verwant zijn zodat u weet hoeveel Lijsten u toelaat.

![](assets/7.png)

## Aanraakpuntdatum {#touchpoint-date-1}

De Datum van het Aanraakpunt voor een Lijst van de Marketing is typisch ListMember gecreeerd datum, zodat de datum dat de Lood of het Contact aan de Lijst van de Marketing werd toegevoegd. Het kan worden met voeten getreden als het douanegebied van de geïnstalleerde oplossing geëtiketteerd, &quot;Datum van Buyer Touchpoint,&quot;bevolkt is. Als dit niet wordt weergegeven, moet het veld worden toegevoegd via de formuliereditor.

![](assets/8.png)

## Kanaaltoewijzing {#channel-mapping}

De Campagnes van de dynamiek worden vastgezet in uw douanegerichte Kanalen van de Marketing gebruikend het gebied van het Type van Campagne. Deze kunnen in uw het menu van Aanpassingen van de Dynamiek worden veranderd.

De waarden in het menu Type campagne worden in de [!DNL Marketo Measure] -toepassing opgehaald. **[!UICONTROL My Account]** > **[!UICONTROL Settings]** > **[!UICONTROL Offline Channels]** .

Voor elk Type van Campagne, kan het aan een combinatie van het Kanaal en Subchannel worden in kaart gebracht zodat elk aanraakpunt dat uit de Campagne voortkomt het correcte in kaart gebrachte Kanaal en Subchannel zal hebben.

![](assets/9.png)

![](assets/10.png)

## Synchronisatiedatum campagne {#campaign-sync-date}

Dit is niet beschikbaar voor klanten van Dynamics

## Veelgestelde vragen {#faq}

**kunnen wij aanraakpunten op de Verkoop van Lijsten of slechts campagnes in Dynamiek toelaten?**

U kunt een Lijst van de Marketing toelaten maar het moet met een Campagne worden verwant omdat de optie om een Lijst van de Marketing te synchroniseren op de Campagne leeft.

**kunnen wij de Reacties van de Campagne EN de Marketing lijsten op een Campagne gebruiken?**

Ja.
