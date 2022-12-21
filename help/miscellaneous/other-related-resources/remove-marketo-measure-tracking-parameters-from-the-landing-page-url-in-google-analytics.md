---
unique-page-id: 18874736
description: Verwijderen [!DNL Marketo Measure] Parameters bijhouden van de URL van de bestemmingspagina in Google Analytics - [!DNL Marketo Measure] - Productdocumentatie
title: Verwijderen [!DNL Marketo Measure] Parameters bijhouden op basis van de URL van de bestemmingspagina in Google Analytics
exl-id: ec81ba4a-bb10-49fd-b62e-5a1bc9e1a023
source-git-commit: 09ffdbb0b1baeed870a3145268997e63a3707c97
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 0%

---

# Verwijderen [!DNL Marketo Measure] Parameters bijhouden op basis van de URL van de bestemmingspagina in Google Analytics {#remove-marketo-measure-tracking-parameters-from-the-landing-page-url-in-google-analytics}

Soms wanneer u bestemmingspagina&#39;s weergeeft in [!DNL Google Analytics], wilt u volgparameters verwijderen uit de URL&#39;s. Anders splitsen ze in afzonderlijke rijen.

Gelukkig is dit een makkelijke oplossing.

1. In [!DNL Google Analytics], ga naar [!UICONTROL Admin] >[!UICONTROL View Settings] >[!UICONTROL Exclude URL Query Parameters].
1. Typ &quot;_bt,_bk,_bm,_bn,_bg&quot; in het vak (minus de aanhalingstekens).
1. Omlaag schuiven en klikken **[!UICONTROL Save]**.

   Houd er rekening mee dat [!DNL Google Analytics] gegevens worden niet opnieuw verwerkt. Deze wijziging wordt daarom alleen weerspiegeld in een volgende stap en uw gegevens uit het verleden worden nog steeds weergegeven met de parameters bt, bk en bm.
