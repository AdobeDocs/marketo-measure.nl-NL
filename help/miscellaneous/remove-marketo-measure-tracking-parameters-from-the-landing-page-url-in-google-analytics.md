---
description: Verwijder  [!DNL Marketo Measure]  het Volgen Parameters van de Openende Pagina URL in Google Analytics
title: Verwijder  [!DNL Marketo Measure]  het Volgen Parameters van de Openende Pagina URL in Google Analytics
exl-id: ec81ba4a-bb10-49fd-b62e-5a1bc9e1a023
feature: Tracking
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 0%

---


# [!DNL Marketo Measure] Trackingparameters verwijderen uit de URL van de bestemmingspagina in Google Analytics {#remove-marketo-measure-tracking-parameters-from-the-landing-page-url-in-google-analytics}

Wanneer u bestemmingspagina&#39;s weergeeft in [!DNL Google Analytics] , wilt u soms traceerparameters verwijderen uit de URL&#39;s. Anders splitsen ze in afzonderlijke rijen.

Gelukkig is dit een makkelijke oplossing.

1. Ga in [!DNL Google Analytics] naar [!UICONTROL Admin] > [!UICONTROL View Settings] > [!UICONTROL Exclude URL Query Parameters].
1. Typ &quot;_bt,_bk,_bm,_bn,_bg&quot; in het vak (minus de aanhalingstekens).
1. Schuif omlaag en klik op **[!UICONTROL Save]** .

   Houd er rekening mee dat [!DNL Google Analytics] geen gegevens opnieuw verwerkt. Deze wijziging wordt daarom alleen weerspiegeld in een volgende stap en uw gegevens uit het verleden worden nog steeds weergegeven met de parameters bt, bk en bm.
