---
unique-page-id: 18874562
description: PostLC Touchpoints en Lead Engagement - Marketo Measure - Productdocumentatie
title: PostLC-aanraakpunten en Lead Engagement
exl-id: 3ee5c571-195e-46c7-b150-fedcbc3614cb
feature: Touchpoints
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 0%

---

# PostLC-aanraakpunten en Lead Engagement {#postlc-touchpoints-and-lead-engagement}

[!DNL Marketo Measure] Post-Lead Creation (PostLC)-aanraakpunten zijn beschikbaar voor klanten die gebruikmaken van multitouch-attributiemodellen (W-Shape en hoger). Wanneer een lead of contactpersoon terugkeert naar uw website en door blijft gaan met het invullen van formulieren, worden deze formulierverzendingen geregistreerd als PostLC-aanraakpunten. Met deze aanraakpunten kunt u zien welke inhoud de Leads ertoe brengt om lang na de eerste conversie door te gaan met uw site. PostLC-aanraakpunten delen toewijzingskrediet met alle intermediaire aanraakpunten binnen een Opportunity; 10% toewijzingskrediet wordt toegewezen aan intermediaire aanraakpunten en wordt gelijkelijk verdeeld over alle aanraakpunten.

![](assets/1.png)

U kunt het aantal PostLC-aanraakpunten aanpassen dat wordt weergegeven in [!DNL SFDC]. Meestal raden we u aan om maximaal vijf PostLC-aanraakpunten te verplaatsen. Elk aanraakpunt neemt 1 kB in beslag [!DNL SFDC].

>[!NOTE]
>
>Aan het einde van dit artikel vindt u instructies voor het aanpassen van de PostLC-aanraakpuntinstellingen.

PostLC-aanraakpunten zijn dynamisch. Als leider of contactpersoon blijven PostLC-formulieren verzenden, [!DNL Marketo Measure] Hiermee werkt u de PostLC-aanraakpunten in uw CRM bij en toont u de meest recente formulierverzendingen. Specifiek, als u een grens van 5 aanraakpunten PostLC hebt geplaatst, [!DNL Marketo Measure] Druk altijd op de 5 _meest recent_ touchpoints to your CRM.  In dit voorbeeld heeft dit account de PostLC-limiet ingesteld op vier aanraakpunten. Deze lead heeft al het maximum aantal PostLC-aanraakpunten bereikt dat deze in uw CRM kan hebben. De laatste PostLC touch was op 6-2-2018. Indien deze persoon de volgende dag een ander formulier invult, [!DNL Marketo Measure] het eerste PostLC-aanraakpunt van 11-9-2017 wordt verwijderd om het laatste aanraakpunt van 2-7-2018 toe te voegen.

![](assets/2.png)

>[!NOTE]
>
>[!DNL Marketo Measure] Hiermee werkt u alleen de PostLC-aanraakpunten op de lead of contactpersoon bij en worden de PostLC-aanknopingspunten voor toewijzingen niet bijgewerkt op een opportunity. Alle relevante PostLC-aanraakpunten op een contactpersoon worden opgenomen in de opportunity.

## PostLC-aanraakpuntinstellingen wijzigen {#how-to-change-postlc-touchpoint-settings}

Volg onderstaande instructies om de PostLC-aanraakpuntinstellingen voor uw leads of contactpersonen aan te passen.

**Leads**

1. Aanmelden bij uw [!DNL Marketo Measure] account op [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} en ga naar [!UICONTROL Settings].

1. Selecteer onder CRM **[!UICONTROL Leads]**.

1. Voer het aantal PostLC-aanraakpunten in dat u op uw leads wilt drukken en klik op **[!UICONTROL Save]**.

   ![](assets/3.png)

**Contactpersonen**

1. Aanmelden bij uw [!DNL Marketo Measure] account op [experience.adobe.com/marketo-measure](https://experience.adobe.com/marketo-measure){target="_blank"} en ga naar [!UICONTROL Settings].

1. Selecteer onder CRM **[!UICONTROL Contacts]**.

1. Voer het aantal postLC-aanraakpunten in dat u op uw contactpersonen wilt toepassen en klik op **[!UICONTROL Save]**.

   ![](assets/4.png)
