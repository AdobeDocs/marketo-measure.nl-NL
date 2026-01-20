---
unique-page-id: 18874562
description: PostLC Touchpoints en Lead Engagement - Marketo Measure - Productdocumentatie
title: PostLC-aanraakpunten en Lead Engagement
exl-id: 3ee5c571-195e-46c7-b150-fedcbc3614cb
feature: Touchpoints
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 0%

---

# PostLC-aanraakpunten en Lead Engagement {#postlc-touchpoints-and-lead-engagement}

[!DNL Marketo Measure] Post-Lead Creation (PostLC)-aanraakpunten zijn beschikbaar voor klanten die gebruikmaken van multitouch-attributiemodellen (W-Shape en hoger). Wanneer een lead of contactpersoon terugkeert naar uw website en door blijft gaan met het invullen van formulieren, worden deze formulierverzendingen geregistreerd als PostLC-aanraakpunten. Met deze aanraakpunten kunt u zien welke inhoud de Leads ertoe brengt om lang na de eerste conversie door te gaan met uw site. PostLC-aanraakpunten delen toewijzingskrediet met alle intermediaire aanraakpunten binnen een Opportunity; 10% toewijzingskrediet wordt toegewezen aan intermediaire aanraakpunten en wordt gelijkelijk verdeeld over alle aanraakpunten.

![](assets/1.png)

U kunt het aantal PostLC-aanraakpunten aanpassen dat wordt weergegeven in [!DNL SFDC] . Doorgaans raden we u aan maximaal vijf PostLC-aanraakpunten in te drukken. Elk aanraakpunt neemt 1 kB in beslag [!DNL SFDC] .

>[!NOTE]
>
>Aan het einde van dit artikel vindt u instructies voor het aanpassen van de PostLC-aanraakpuntinstellingen.

PostLC-aanraakpunten zijn dynamisch. Aangezien een lead of contactpersoon PostLC-formulieren blijft verzenden, werkt [!DNL Marketo Measure] de PostLC-aanraakpunten in uw CRM bij om hun meest recente formulierverzendingen weer te geven. Specifiek, als u een grens van 5 aanraakpunten PostLC hebt geplaatst, [!DNL Marketo Measure] duw altijd vijf _meest recente_ aanraakpunten aan uw CRM.  In dit voorbeeld heeft dit account de PostLC-limiet ingesteld op vier aanraakpunten. Deze lead heeft al het maximum aantal PostLC-aanraakpunten bereikt dat deze in uw CRM kan hebben. De laatste PostLC touch was op 6-2-2018. Als deze persoon de volgende dag een ander formulier invult, verwijdert [!DNL Marketo Measure] het eerste PostLC-aanraakpunt van 11-9-2017 om het laatste aanraakpunt toe te voegen van 2-7-2018.

![](assets/2.png)

>[!NOTE]
>
>[!DNL Marketo Measure] werkt alleen PostLC-aanraakpunten op de lead of contactpersoon bij en werkt geen PostLC-aanknopingspunten voor toewijzingen bij op een opportunity. Alle relevante PostLC-aanraakpunten op een contactpersoon worden opgenomen in de opportunity.

## PostLC-aanraakpuntinstellingen wijzigen {#how-to-change-postlc-touchpoint-settings}

Volg onderstaande instructies om de PostLC-aanraakpuntinstellingen voor uw leads of contactpersonen aan te passen.

**Leads**

1. Login aan uw [!DNL Marketo Measure] rekening in [ experience.adobe.com/marketo-measure ](https://experience.adobe.com/marketo-measure){target="_blank"} en ga naar [!UICONTROL Settings].

1. Selecteer **[!UICONTROL Leads]** onder CRM.

1. Voer het aantal PostLC-aanraakpunten in dat u op uw leads wilt drukken en klik op **[!UICONTROL Save]** .

   ![](assets/3.png)

**Contacten**

1. Login aan uw [!DNL Marketo Measure] rekening in [ experience.adobe.com/marketo-measure ](https://experience.adobe.com/marketo-measure){target="_blank"} en ga naar [!UICONTROL Settings].

1. Selecteer **[!UICONTROL Contacts]** onder CRM.

1. Voer het aantal postLC-aanraakpunten in dat u op uw contactpersonen wilt toepassen en klik op **[!UICONTROL Save]** .

   ![](assets/4.png)
