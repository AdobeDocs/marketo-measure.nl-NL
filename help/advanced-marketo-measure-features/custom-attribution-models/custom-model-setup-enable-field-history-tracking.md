---
unique-page-id: 18874777
description: Aangepaste modelinstelling - Enable Field History Tracking - [!DNL Marketo Measure] - Productdocumentatie
title: Aangepaste modelinstelling - Enable Field History Tracking
exl-id: 70328e67-051b-4864-891b-b251e49859c2
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 0%

---

# Aangepaste modelinstelling: Enable Field History Tracking {#custom-model-setup-enable-field-history-tracking}

## Waarom en wanneer om het Volgen van de Geschiedenis van het Gebied toe te laten {#why-and-when-to-enable-field-history-tracking}

Als u besluit een aangepast veld als een werkgebied op te nemen in het aangepaste toewijzingsmodel, wordt de historie van het veld gevolgd **moet worden ingeschakeld** voor dit veld. Het bijhouden van de veldgeschiedenis wordt ingeschakeld [!DNL Salesforce] als u wilt bijhouden wanneer het aangepaste veld wordt bewerkt, maakt u een record in de tabel Historie bijhouden. [!DNL Marketo Measure] U kunt die tabel downloaden en deze informatie gebruiken om de tijd en de dag te meten waarop een &quot;overgang&quot; heeft plaatsgevonden. Zonder bijhouden van veldgeschiedenis, [!DNL Marketo Measure] kan de wijzigingen met betrekking tot dit veld niet bijhouden.

Alleen [!UICONTROL Lead Status] Of Opportunity-fasen worden gebruikt in het aangepaste model, het is niet nodig om het bijhouden van veldgeschiedenis in te schakelen, omdat dit automatisch wordt bijgehouden als een werkgebiedovergang.

Volg onderstaande instructies om het bijhouden van veldgeschiedenis in te schakelen.

## Enable Field History Tracking {#enable-field-history-tracking}

>[!NOTE]
>
>U moet een systeembeheerder zijn om deze wijzigingen aan te brengen in de velden op het object Lead/Contact/Opportunity.

1. Ga naar het object waar het aangepaste veld zich bevindt en klik op de knop **[!UICONTROL Set History Tracking]** knop.

   ![](assets/1.png)

1. Selecteer de velden waarop u wijzigingen wilt bijhouden.

   ![](assets/2.png)

[!DNL Marketo Measure] kan een record alleen opnieuw importeren als het ziet dat de record onlangs is gewijzigd. Formulervelden wijzigen technisch geen record wanneer deze verandert omdat de berekening op de achtergrond wordt uitgevoerd. We hebben problemen gezien waarbij een regel wordt overgeslagen omdat [!DNL Marketo Measure] heeft de recordwijziging niet gezien, dus wordt aangeraden **geen gebruik van formuleringsgebieden in regeldefinities**. U kunt een tekstveld maken en een workflow gebruiken om dat veld te vullen met de juiste waarde of berekening wanneer de record wordt bewerkt of aan de criteria voldoet. Dit vereist dat alle verslagen worden uitgegeven zodat kan het werkschema met terugwerkende kracht aan oude verslagen werken.
