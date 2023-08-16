---
unique-page-id: 18874588
description: Aangepaste campagnecorrectie - [!DNL Marketo Measure] - Productdocumentatie
title: Aangepaste synchronisatie van campagnes
exl-id: 66f0e4e3-c1b6-443e-8ffa-06b67862b855
feature: Channels
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 0%

---

# Aangepaste synchronisatie van campagnes {#custom-campaign-sync}

Vandaag, met geïnstalleerd [!DNL Marketo Measure] -pakket, kunt u aangeven welke campagnes moeten worden opgenomen als een geschikt aanraakpunt. Er zijn meerdere obstakels. Wanneer de [!DNL Marketo Measure] wordt geïnstalleerd in CRM, kan het tijd vergen om door uw veiligheidsteam worden goedgekeurd. Bovendien is er een gebrek aan flexibiliteit in het gebruiken van één enkele picklist op het voorwerp van de Campagne. Met deze nieuwe functie hoeft u geen pakket te installeren om de records voor Campagne en Campagne-leden te gaan gebruiken. De regels kunnen worden gebouwd om precies te bepalen welke verslagen kunnen worden gebouwd om precies te bepalen welke verslagen in aanmerking komen.

## Vereisten {#requirements}

* Campagne synchroniseren is beschikbaar in alle lagen
* Als u gegevens wilt importeren, moet u uw CRM nog steeds koppelen aan uw [!DNL Marketo Measure] account

## Hoe het werkt {#how-it-works}

1. Met AccountAdmin-machtigingen kunt u naar **[!UICONTROL Settings]** > **[!UICONTROL Campaigns]** en raadpleegt u de gebruikersinterface van Campagneleden synchroniseren.
1. Klik op de knop **+** pictogram om een regel te beginnen maken.

   ![](assets/1-1.png)

1. U kunt een regel maken op basis van [!UICONTROL Campaign] of [!UICONTROL Campaign Member] velden. Vul de rest van de regel in met de operator en de waarde die we moeten valideren. In het onderstaande voorbeeld zoeken we op naam naar een specifieke campagne.

   ![](assets/2-1.png)

   >[!NOTE]
   >
   >Formulervelden kunnen niet worden gebruikt binnen uw regels en worden niet weergegeven in de keuzelijst. Omdat formules op de achtergrond berekenen en een record niet wijzigen, [!DNL Marketo Measure] kan niet ontdekken of een verslag een regel past of niet.

1. Kies de aanraakpuntdatum. De lijst met mogelijke datums wordt weergegeven nadat u een accolade hebt ingevoerd `{` - selecteert u vervolgens de datum die u wilt toepassen op alle aanraakpunten die met de regel zijn gemaakt.

   ![](assets/3-1.png)

   >[!NOTE]
   >
   >Als u de regels van de Synchronisatie van de Campagne van de Douane gebruikt, [!DNL Marketo Measure] Hiermee worden de updates die u hebt gemaakt met de knop Aanraakdatum bulkupdate niet gelezen.

1. Klik op het vinkje en voeg desgewenst aanvullende regels voor extra campagnes toe.

   ![](assets/4-1.png)

   >[!NOTE]
   >
   >Nu de regels naast de synchronisatie van CRM worden bepaald, zullen de regels die worden verklaard natuurlijk beginnen in conflict te komen. Als u ervoor kiest om beide aangepaste Campagne Sync te blijven gebruiken _en_ Het Type van Synchronisatie van CRM, is het kritiek om regels tot stand te brengen zodat worden uw Types van Synchronisatie van CRM niet genegeerd.

   ![](assets/5-1.png)

   >[!NOTE]
   >
   >Als u overweegt de gebruiker uiteindelijk te stoppen [!UICONTROL CRM Sync Type], is het ideaal om regels te maken die niet verwijzen naar het &quot;Type synchroniseren&quot;, maar _nog steeds_ de huidige CRM-aanraakpunten onderhouden. Op die manier werken de regels nog steeds als/wanneer die omschakeling plaatsvindt.

Hier is een voorbeeld van hoe dat eruit zou zien, zodat geen bestaande aanraakpunten van CRM worden verloren:

## Validatie {#validation}

U kunt de aanraakpunten voor kopers en de aanraakpunten voor koperkenmerken in de campagne eenvoudig controleren om te controleren of de regels correct werken. Hier is een BBT die [!DNL Marketo Measure] gemaakt met de juiste dynamische aanraakpuntdatum, gehaald uit de campagne. Het veld Gemaakt op datum staat in de afbeelding eronder.

![](assets/6-1.png)

## Testen {#testing}

1. De functie Campagne synchroniseren wordt geleverd met een testfunctie, zodat u kunt controleren of de regels die u hebt gemaakt, ook daadwerkelijk voldoen aan de criteria voor campagnes. Begin door te klikken op de knop [!UICONTROL Test] knop. De regels moeten eerst worden opgeslagen voordat u kunt beginnen met testen.

   ![](assets/7-1.png)

   Een pop-up zal verschijnen waar u een Identiteitskaart van de Campagne (of 15 of 18 karakters van CRM) aan test kunt ingaan. Het punt moet identiteitskaart van de Campagne van CRM ingaan die u aan synchronisatie probeerde om het met de regel te verzekeren u creeerde.

   ![](assets/8-1.png)

1. Nadat u op [!UICONTROL Test]U ziet dan de naam van de campagne en het aantal campagneleden dat in aanmerking komt voor aanraakpunten. Hieronder ziet u een tabel met alle regels die overeenkomen met uw campagne-id. Alleen de overeenkomsten worden weergegeven.

   ![](assets/9.png)

1. U kunt ook op het aantal leden klikken om een lijst weer te geven van de leads en contactpersonen en hun id&#39;s die deel uitmaken van de geschiktheid voor de campagneregel. Dit is slechts een steekproefreeks en zal tot 50 tonen zodat u een idee kunt krijgen van welke verslagen kwalificeren.

   ![](assets/10.png)
