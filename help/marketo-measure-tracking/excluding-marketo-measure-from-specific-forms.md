---
description: Exclusief  [!DNL Marketo Measure]  van de Specifieke begeleiding van Forms voor de gebruikers van Marketo Measure
title: Exclusief  [!DNL Marketo Measure]  van Specifieke Forms
exl-id: ce39a3b2-2ac6-4385-b6d1-3c36b51c03fa
feature: Tracking
hidefromtoc: true
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 0%

---

# [!DNL Marketo Measure] uitsluiten van specifieke Forms {#excluding-marketo-measure-from-specific-forms}

[!DNL Marketo Measure] voegt standaard een bijlage toe aan alle formulieren op uw site. Niet alle ingevulde formulieren moeten echter noodzakelijkerwijs worden bijgehouden of in een toewijzingsmodel worden opgenomen. Dit komt omdat niet alle formuliervullingen als &quot;goed&quot; worden beschouwd. Een voorbeeld hiervan is het afmelden van een pagina/formulier. Bovendien worden aanmeldingsformulieren meestal niet bijgehouden, omdat dit het toewijzingsmodel zou verwateren.

## Procedure voor het toevoegen van code [!DNL Marketo Measure] -exclude:  {#how-to-add-marketo-measure-exclude-code}

Als u wilt voorkomen dat [!DNL Marketo Measure] specifieke formulieren bijhoudt, voegt u &quot;[!DNL Bizible-Exclude]&quot; toe als een &#39;klasse&#39; in uw formulier. De code ziet er als volgt uit:

`<form id="myForm" action="/Home/TestPage" method="POST" class="Bizible-Exclude">`
