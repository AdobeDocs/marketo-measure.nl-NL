---
unique-page-id: 18874614
description: Leads met rapport met aanraakpunten voor kopers -  [!DNL Marketo Measure]
title: Leads met rapport met aanraakpunten voor kopers
exl-id: 0376abb0-5eed-41bb-ab4f-3c204ab437df
feature: Touchpoints, Reporting
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 0%

---

# Leads met rapport met aanraakpunten voor kopers {#leads-with-buyer-touchpoints-report}

>[!NOTE]
>
>U kunt instructies zien die &quot;[!DNL Marketo Measure]&quot;in de documentatie specificeren, maar nog zie &quot;[!DNL Bizible]&quot;in uw CRM. We werken eraan dat dit wordt bijgewerkt en de herbranding wordt binnenkort weerspiegeld in uw CRM.

Uit de doos hebt u vele rapporteringsmogelijkheden bij uw vingertoppen wanneer het over [!DNL Marketo Measure] komt, maar er zijn sommige extra rapporttypes wij adviseren bouw. Meer informatie over het maken van een inclusief leadtype met kopersaanraakpunten vindt u hieronder.

1. Navigeer binnen [!DNL Salesforce] naar de instellingsoptie. Vouw vervolgens de groep Maken uit en selecteer **[!UICONTROL Report Types]** .

   ![](assets/1.jpg)

1. Selecteer **[!UICONTROL New Custom Report Type]**.

   ![](assets/2.jpg)

1. Stel het primaire object in als &#39;Leads&#39; en binnen de invoer &#39;Label voor rapporttype&#39; als &#39;Leads met aanraakpunten voor kopers - inclusief&#39;. Sla het rapport op in de categorie &quot;Leads&quot; en wijzig de implementatiestatus in **[!UICONTROL Deployed]** . Selecteer vervolgens **[!UICONTROL Next]** .

   ![](assets/3.jpg)

1. Voor de objecten verhoudingen, selecteer het **[!DNL Marketo Measure]voorwerp van Personen** als secundair voorwerp. Selecteer de relatie A tot B als &quot;Elk A-record moet minstens één verwant B-record hebben.&quot; Daarna koppelt u het object &quot;Buyer Touchpoint&quot; en selecteert u dezelfde relatie tussen de objecten B en C.

   ![](assets/4.jpg)

1. Sla enkele rapporten op en maak deze.
