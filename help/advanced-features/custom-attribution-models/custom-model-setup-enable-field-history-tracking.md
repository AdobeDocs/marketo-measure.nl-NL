---
description: Aangepaste modelinstelling - Richtlijnen voor het bijhouden van veldgeschiedenis inschakelen voor Marketo Measure-gebruikers
title: Aangepaste modelinstelling - Enable Field History Tracking
exl-id: 70328e67-051b-4864-891b-b251e49859c2
feature: Custom Models
hidefromtoc: true
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 0%

---

# Aangepaste modelinstelling: Enable Field History Tracking {#custom-model-setup-enable-field-history-tracking}

## Waarom en wanneer om het Volgen van de Geschiedenis van het Gebied toe te laten {#why-and-when-to-enable-field-history-tracking}

Als u besluit om een douanegebied als stadium in uw model van de douaneattributie te omvatten, moet het volgen van de gebiedsgeschiedenis **** voor dit gebied worden toegelaten. Door het bijhouden van de veldgeschiedenis in te schakelen, kan [!DNL Salesforce] elke keer dat het aangepaste veld wordt bewerkt, bijhouden door een record te maken in de tabel Historie bijhouden. [!DNL Marketo Measure] kan die tabel downloaden en deze informatie gebruiken om de tijd en de dag te meten waarop een &quot;overgang&quot; heeft plaatsgevonden. Zonder het bijhouden van de veldgeschiedenis kan [!DNL Marketo Measure] geen wijzigingen bijhouden die betrekking hebben op dit veld.

Als alleen [!UICONTROL Lead Status] - of Opportunity-fasen worden gebruikt in het aangepaste model, hoeft u het bijhouden van veldgeschiedenis niet in te schakelen, omdat dit automatisch wordt bijgehouden als een overgang in het werkgebied.

Volg onderstaande instructies om het bijhouden van veldgeschiedenis in te schakelen.

## Enable Field History Tracking {#enable-field-history-tracking}

>[!NOTE]
>
>U moet een systeembeheerder zijn om deze wijzigingen aan te brengen in de velden op het object Lead/Contact/Opportunity.

1. Ga naar het object waar het aangepaste veld zich bevindt en klik op de knop **[!UICONTROL Set History Tracking]** .

   ![](assets/custom-models-1.png)

1. Selecteer de velden waarop u wijzigingen wilt bijhouden.

   ![](assets/custom-models-10.png)

[!DNL Marketo Measure] kan een record alleen opnieuw importeren als het ziet dat de record onlangs is gewijzigd. Formulervelden wijzigen technisch geen record wanneer deze verandert omdat de berekening op de achtergrond wordt uitgevoerd. Wij hebben kwesties gezien waar een regel wordt overgeslagen omdat [!DNL Marketo Measure] niet de verslagverandering zag, zodat wordt het geadviseerd om **geen formules in regeldefinities** te gebruiken. U kunt een tekstveld maken en een workflow gebruiken om dat veld te vullen met de juiste waarde of berekening wanneer de record wordt bewerkt of aan de criteria voldoet. Dit vereist dat alle verslagen worden uitgegeven zodat kan het werkschema met terugwerkende kracht aan oude verslagen werken.
