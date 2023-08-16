---
unique-page-id: 18874614
description: Leads met rapport met aanraakpunten voor kopers - [!DNL Marketo Measure] - Productdocumentatie
title: Leads met rapport met aanraakpunten voor kopers
exl-id: 0376abb0-5eed-41bb-ab4f-3c204ab437df
feature: Touchpoints, Reporting
source-git-commit: a2a7657e8377fd5c556d38f6eb815e39d2b8d15e
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 0%

---

# Leads met rapport met aanraakpunten voor kopers {#leads-with-buyer-touchpoints-report}

>[!NOTE]
>
>Mogelijk ziet u instructies die &quot;[!DNL Marketo Measure]&quot; in onze documentatie , maar nog steeds &quot;[!DNL Bizible]&quot; in uw CRM. We werken eraan dat dit wordt bijgewerkt en de herbranding wordt binnenkort weerspiegeld in uw CRM.

U hebt veel rapportagemogelijkheden binnen handbereik als het gaat om [!DNL Marketo Measure], maar er zijn een aantal extra rapporttypes wij adviseren bouw. Meer informatie over het maken van een inclusief leadtype met kopersaanraakpunten vindt u hieronder.

1. Navigeer naar de instellingsoptie binnen [!DNL Salesforce]. Vouw van daaruit de groep &quot;Maken&quot; uit en selecteer **[!UICONTROL Report Types]**.

   ![](assets/1.jpg)

1. Selecteren **[!UICONTROL New Custom Report Type]**.

   ![](assets/2.jpg)

1. Stel het primaire object in als &#39;Leads&#39; en binnen de invoer &#39;Label voor rapporttype&#39; als &#39;Leads met aanraakpunten voor kopers - inclusief&#39;. Sla het rapport op in de categorie &quot;Leads&quot; en wijzig de implementatiestatus in **[!UICONTROL Deployed]**. Selecteer vervolgens **[!UICONTROL Next]**.

   ![](assets/3.jpg)

1. Selecteer voor de objectrelaties de optie **[!DNL Marketo Measure]Personen** als het secundaire object. Selecteer de relatie A tot B als &quot;Elk A-record moet minstens één verwant B-record hebben.&quot; Vervolgens brengt u het object &quot;Aanraakpunt koper&quot; aan en selecteert u dezelfde relatie tussen de objecten B en C.

   ![](assets/4.jpg)

1. Sla enkele rapporten op en maak deze.
