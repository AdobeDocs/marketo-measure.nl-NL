---
unique-page-id: 18874783
description: Exclusief [!DNL Marketo Measure] uit specifiek Forms - [!DNL Marketo Measure]
title: Exclusief [!DNL Marketo Measure] van Specifieke Forms
exl-id: ce39a3b2-2ac6-4385-b6d1-3c36b51c03fa
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 0%

---

# Exclusief [!DNL Marketo Measure] van Specifieke Forms {#excluding-marketo-measure-from-specific-forms}

Standaard, [!DNL Marketo Measure] voegt toe aan alle formulieren op uw site. Niet alle ingevulde formulieren moeten echter noodzakelijkerwijs worden bijgehouden of in een toewijzingsmodel worden opgenomen. Dit komt omdat niet alle formuliervullingen als &quot;goed&quot; worden beschouwd. Een voorbeeld hiervan is het afmelden van een pagina/formulier. Bovendien worden aanmeldingsformulieren meestal niet bijgehouden, omdat dit het toewijzingsmodel zou verwateren.

## Toevoegen [!DNL Marketo Measure]-exclude Code:  {#how-to-add-marketo-measure-exclude-code}

voorkomen [!DNL Marketo Measure] van het bijhouden van specifieke formulieren, voegt u eenvoudig &quot;[!DNL Bizible-Exclude]&quot; als een &#39;klasse&#39; op uw formulier. De code ziet er als volgt uit:

`<form id="myForm" action="/Home/TestPage" method="POST" class="Bizible-Exclude">`
