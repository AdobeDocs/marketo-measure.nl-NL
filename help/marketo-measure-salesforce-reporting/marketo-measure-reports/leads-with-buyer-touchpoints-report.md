---
description: Leads met rapport met aanraakpunten voor kopers -  [!DNL Marketo Measure]
title: Leads met rapport met aanraakpunten voor kopers
exl-id: 0376abb0-5eed-41bb-ab4f-3c204ab437df
feature: Touchpoints, Reporting
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 0%

---


# Leads met rapport met aanraakpunten voor kopers {#leads-with-buyer-touchpoints-report}

>[!NOTE]
>U kunt instructies zien die &quot;[!DNL Marketo Measure]&quot;in de documentatie specificeren, maar nog zie &quot;[!DNL Bizible]&quot;in uw CRM. We werken eraan dat dit wordt bijgewerkt en de herbranding wordt binnenkort weerspiegeld in uw CRM.

Uit de doos hebt u vele rapporteringsmogelijkheden bij uw vingertoppen wanneer het over [!DNL Marketo Measure] komt, maar er zijn sommige extra rapporttypes wij adviseren bouw. Meer informatie over het maken van een inclusief leadtype met kopersaanraakpunten vindt u hieronder.

1. Navigeer binnen [!DNL Salesforce] naar de instellingsoptie. Vouw vervolgens de groep Maken uit en selecteer **[!UICONTROL Report Types]** .

   ![&#x200B; de pagina van de Types van Rapport van Salesforce die Leads met de opstelling van Aanraakpunten van de Koper toont &#x200B;](assets/1.jpg)

1. Selecteer **[!UICONTROL New Custom Report Type]**.

   ![&#x200B; Nieuwe tovenaar van het Type van Rapport van de Douane in Salesforce &#x200B;](assets/2.jpg)

1. Stel het primaire object in als &#39;Leads&#39; en binnen de invoer &#39;Label voor rapporttype&#39; als &#39;Leads met aanraakpunten voor kopers - inclusief&#39;. Sla het rapport op in de categorie &quot;Leads&quot; en wijzig de implementatiestatus in **[!UICONTROL Deployed]** . Selecteer vervolgens **[!UICONTROL Next]** .

   ![&#x200B; het type van Rapport details met Leads als primair voorwerp &#x200B;](assets/3.jpg)

1. Voor de objecten verhoudingen, selecteer het **[!DNL Marketo Measure]voorwerp van Personen** als secundair voorwerp. Selecteer de relatie A tot B als &quot;Elk A-record moet minstens één verwant B-record hebben.&quot; Daarna koppelt u het object &quot;Buyer Touchpoint&quot; en selecteert u dezelfde relatie tussen de objecten B en C.

   ![&#x200B; de relatieselectie van Objecten met inbegrip van de Personen van Marketo Measure en de Aanraakpunten van de Koper &#x200B;](assets/4.jpg)

1. Sla enkele rapporten op en maak deze.
