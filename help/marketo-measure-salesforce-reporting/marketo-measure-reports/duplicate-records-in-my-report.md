---
unique-page-id: 18874634
description: Records dupliceren in Mijn rapport - [!DNL Marketo Measure]
title: Records dupliceren in Mijn rapport
exl-id: 4ee42371-5b67-4c69-9b49-3249f33614d0
feature: Reporting
source-git-commit: b84909fbb34a1d8f739ebeea3400ef8816e17d32
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# Records dupliceren in Mijn rapport {#duplicate-records-in-my-report}

>[!NOTE]
>
>Mogelijk ziet u instructies die &quot;[!DNL Marketo Measure]&quot; in de documentatie, maar nog steeds &quot;[!DNL Bizible]&quot; in uw CRM. We werken eraan dat dit wordt bijgewerkt en de herbranding wordt binnenkort weerspiegeld in uw CRM.

Terwijl u in de [!DNL Marketo Measure] Rapporten in [!DNL Salesforce], kun je beginnen naar dubbele records in je rapporten te zoeken. U zult dit gevoel waarschijnlijk ervaren wanneer u een beoordeling uitvoert [!DNL Marketo Measure] out-of-the-box rapporten.

Wanneer u rapporteert met het object Aanraakpunten koper of het object Aanraakpunt koperkenmerk, is het belangrijk om te begrijpen dat u niet langer rapporteert over het aantal leads, contactpersonen of mogelijkheden, maar dat u ook rapporteert over het aantal aanraakpunten voor kopers of aanraakpunten voor koperkenmerken die aan deze standaardobjecten zijn gekoppeld (leads, contactpersonen, mogelijkheden).

Neem het volgende rapport als voorbeeld:

Dit is een **Contacten met de Aanraakpunten van de Koper** verslag. Nogmaals, dit betekent dat we kijken naar het aantal aanraakpunten dat gekoppeld is aan een individueel contact.

![](assets/1.gif)

Zoals je ziet, lijken er drie James Williams-contacten in het verslag te zitten, en daarom denk je misschien: &quot;duplicaten!&quot;

Dit verslag toont echter het aantal aanraakpunten met James. In het rapport ziet u dat James een individuele FT (First Touch), een individuele LC, Form (Lead Creation Touch) en een PostLC-aanraakpunt heeft (een formulierverzending die plaatsvindt na het LC-aanraakpunt).

Als u het &quot;aantal contacten&quot;wilt begrijpen kunt u de gebieden &quot;Telling - Eerste Aanraking&quot;, &quot;Telling-Lood Aanraking&quot;of &quot;Telling-U-Vormde&quot;gebruiken om te begrijpen hoeveel contacten marketing interactie hebben gehad.

>[!MORELIKETHIS]
>
>[[!DNL Marketo Measure] Tutorials: SFDC-rapporten voor aandelen](https://experienceleague.adobe.com/en/docs/marketo-measure-learn/tutorials/onboarding/marketo-measure-102/stock-salesforce-reports){target="_blank"}
