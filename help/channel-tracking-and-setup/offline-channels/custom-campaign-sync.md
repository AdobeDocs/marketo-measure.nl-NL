---
description: Aangepaste richtlijnen voor het synchroniseren van campagnes voor Marketo Measure-gebruikers
title: Aangepaste synchronisatie van campagnes
exl-id: 66f0e4e3-c1b6-443e-8ffa-06b67862b855
feature: Channels
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 0%

---

# Aangepaste synchronisatie van campagnes {#custom-campaign-sync}

Vandaag kunt u met het geïnstalleerde [!DNL Marketo Measure] -pakket aangeven welke campagnes moeten worden opgenomen als een geschikt aanraakpunt. Er zijn meerdere obstakels. Nadat het [!DNL Marketo Measure] -pakket in de CRM-service is geïnstalleerd, kan het enige tijd duren voordat het door uw beveiligingsteam is goedgekeurd. Bovendien is er een gebrek aan flexibiliteit in het gebruiken van één enkele picklist op het voorwerp van de Campagne. Met deze nieuwe functie hoeft u geen pakket te installeren om de records voor Campagne en Campagne-leden te gaan gebruiken. De regels kunnen worden gebouwd om precies te bepalen welke verslagen kunnen worden gebouwd om precies te bepalen welke verslagen in aanmerking komen.

## Vereisten {#requirements}

* Campagne synchroniseren is beschikbaar in alle lagen
* Als u gegevens wilt importeren, moet u uw CRM nog steeds verbinden met uw [!DNL Marketo Measure] -account

## Hoe het werkt {#how-it-works}

1. Met AccountAdmin-machtigingen kunt u naar **[!UICONTROL Settings]** > **[!UICONTROL Campaigns]** navigeren en de gebruikersinterface van Campagneleden synchroniseren weergeven.
1. Klik op het pictogram **+** om een regel te maken.

   ![](assets/offline-channels-1.png)

1. U kunt een regel maken in [!UICONTROL Campaign] - of [!UICONTROL Campaign Member] -velden. Vul de rest van de regel in met de operator en de waarde die we moeten valideren. In het onderstaande voorbeeld zoeken we op naam naar een specifieke campagne.

   ![](assets/offline-channels-10.jpg)

   >[!NOTE]
   >
   >Formulervelden kunnen niet worden gebruikt binnen uw regels en worden niet weergegeven in de keuzelijst. Omdat formules op de achtergrond berekenen en een record niet wijzigen, kan [!DNL Marketo Measure] niet bepalen of een record op een regel past of niet.

1. Kies de aanraakpuntdatum. De lijst met mogelijke datums wordt weergegeven nadat u een accolade hebt ingevoerd `{` . Vervolgens kunt u de datum selecteren die u wilt toepassen op alle aanraakpunten die met de regel zijn gemaakt.

   ![](assets/offline-channels-11.png)

   >[!NOTE]
   >
   >Als u de regels van de Synchronisatie van de Campagne van de Douane gebruikt, [!DNL Marketo Measure] zal om het even welke updates niet lezen u gebruikend de Bulk knoop van de Datum van het Aanraakpunt van de Update hebt gemaakt.

1. Klik op het vinkje en voeg desgewenst aanvullende regels voor extra campagnes toe.

   ![](assets/offline-channels-12.png)

   >[!NOTE]
   >
   >Nu de regels naast de synchronisatie van CRM worden bepaald, zullen de regels die worden verklaard natuurlijk beginnen in conflict te komen. Als het verkiezen om zowel de synchronisatie van de douanecampagne te blijven gebruiken _als_ het Type van Synchronisatie van CRM, is het kritiek om regels tot stand te brengen zodat worden uw Types van Synchronisatie van CRM niet genegeerd.

   ![](assets/offline-channels-13.png)

   >[!NOTE]
   >
   >Als u overweegt uiteindelijk het tegenhouden van de gebruiker van [!UICONTROL CRM Sync Type], is het ideaal om regels tot stand te brengen die niet het &quot;Type van Synchronisatie&quot;maar _nog_ verwijzen handhaaft de huidige Aanraakpunten van CRM. Op die manier werken de regels nog steeds als/wanneer die omschakeling plaatsvindt.

Hier is een voorbeeld van hoe dat eruit zou zien, zodat geen bestaande aanraakpunten van CRM worden verloren:

## Validatie {#validation}

U kunt eenvoudig de aanraakpunten voor kopers en de Buyer Attribution Touchpoint-records in de campagne controleren om te controleren of de regels correct werken. Hier is een BAT die [!DNL Marketo Measure] heeft gemaakt met de juiste dynamische aanraakpuntdatum, opgehaald uit de campagne. Het veld Gemaakt op datum staat in de afbeelding eronder.

![](assets/offline-channels-14.png)

## Testen {#testing}

1. De functie Campagne synchroniseren wordt geleverd met een testfunctie, zodat u kunt controleren of de regels die u hebt gemaakt, ook daadwerkelijk voldoen aan de criteria voor campagnes. Klik eerst op de knop [!UICONTROL Test] . De regels moeten eerst worden opgeslagen voordat u kunt beginnen met testen.

   ![](assets/offline-channels-15.jpg)

   Een pop-up zal verschijnen waar u een Identiteitskaart van de Campagne (of 15 of 18 karakters van CRM) aan test kunt ingaan. Het punt moet identiteitskaart van de Campagne van CRM ingaan die u aan synchronisatie probeerde om het met de regel te verzekeren u creeerde.

   ![](assets/offline-channels-16.png)

1. Nadat u op [!UICONTROL Test] hebt geklikt, ziet u de naam van de campagne en het aantal campagneleden dat in aanmerking komt voor aanraakpunten. Hieronder ziet u een tabel met alle regels die overeenkomen met uw campagne-id. Alleen de overeenkomsten worden weergegeven.

   ![](assets/offline-channels-17.png)

1. U kunt ook op het aantal leden klikken om een lijst weer te geven met de leads en contactpersonen en hun id&#39;s die deel uitmaken van de geschiktheid voor de campagneregel. Dit is slechts een steekproefreeks en zal tot 50 tonen zodat u een idee kunt krijgen van welke verslagen kwalificeren.

   ![](assets/offline-channels-18.jpg)
