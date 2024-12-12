---
unique-page-id: 18874646
description: Verschil tussen aanraakpunten voor kopers en kenmerkaanraakpunten voor kopers -  [!DNL Marketo Measure]
title: Verschil tussen aanraakpunten voor kopers en aanraakpunten voor koperkenmerken
exl-id: 19109271-7b59-44c0-b1ff-e3b0bba9f5ce
feature: Touchpoints
source-git-commit: bdc32fdfe24d57fd7770654f1238896c7b59acf6
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 0%

---

# Verschil tussen aanraakpunten voor kopers en aanraakpunten voor koperkenmerken {#difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints}

Leer wat een Buyer Touchpoint (BT) en Buyer Attribution Touchpoint (BAT) bepaalt, de verschillen tussen twee, en antwoord vaak gestelde vragen.

Het belangrijkste onderscheid tussen aanraakpunten voor kopers en aanraakpunten voor koperkenmerken is hun relatie met objecten voor [!DNL Salesforce] . BT hebben betrekking op de objecten Lead, Contact en Case, maar niet op het object Opportunity. Dat betekent dat er nooit inkomsten zijn verbonden aan de aanraakpunten van kopers.

Terwijl het Buyer Attribution Touchpoint-object gerelateerd is aan de contact-, account- en opportuniteitsobjecten, maar niet aan het hoofdobject; de aanraakpunten voor koperkenmerken zijn niet gekoppeld aan leads. In het BAT Object ziet u inkomsten die zijn gekoppeld aan specifieke marketinginteracties.

Verschil tussen BT en BAT:

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td>Buyer Touchpoint (BT)</td> 
   <td>Buyer Attribution Touchpoint (BAT)</td> 
  </tr> 
  <tr> 
   <td> 
    <ul> 
     <li>Heeft betrekking op de objecten Lead, Contact en Case</li> 
     <li>Heeft geen betrekking op het object Opportunity</li> 
     <li>Opbrengsten zijn niet gekoppeld aan een Buyer Touchpoint</li> 
    </ul></td> 
   <td> 
    <ul> 
     <li>Heeft betrekking op de contact-, account- en opportunity-objecten</li> 
     <li>Heeft geen betrekking op het object Lead</li> 
     <li>Aangezien een Buyer Attribution Touchpoint aan een Kans wordt geassocieerd, hebben alle BAT aan hen verbonden inkomsten</li> 
    </ul></td> 
  </tr> 
 </tbody> 
</table>

## Veelgestelde vragen {#faq}

**wanneer wordt een Buyer Touchpoint een Buyer Attribution Touchpoint?**

Een BT wordt een BAT zodra dit BT aan een Contact wordt geassocieerd dat een bijbehorende Kans heeft. Een belangrijk ding om te begrijpen is dat één specifieke marketing interactie een BT en BAT kan zijn.

**kan een Buyer Touchpoint een Positie van het Aanraakpunt van de Aanmaak van de Kans (OC) hebben?**

Een Buyer Touchpoint heeft alleen een aanraakpunt met de positie First Touch (FT), Lead Creation (LC) of Form submission (intermediaire aanraakpunten). Aangezien BT niet met Kansen verwant zijn, is het niet mogelijk voor een BT om een Positie van het Aanraakpunt van Kans te hebben creatie of Gesloten.

**hoe worden de gegevens van Buyer Touchpoint gebruikt?**

Doorgaans gebruiken klanten Buyer Touchpoint-gegevens om Top van de trechter en het midden van de treindienst te begrijpen. Betekenis dat [!DNL Marketo Measure] -gebruikers weten wie formulieren verzendt, wie zijn site bekijkt, welk blogbericht goed presteert, wat AdWords en welke drijfveer tot conversie leidt, enzovoort. Buyer Touchpoint-gegevens zijn ideaal voor inzicht in de betrokkenheid van uw leads en contactpersonen.

**wat kijkt een Buyer Touchpoint als in Salesforce?**

Hier is een schermafbeelding van een BT in [!DNL Salesforce] :

![](assets/buyer-touchpoints-and-buyer-attribution-touchpoints-1.png){width="600" zoomable="yes"}

**wat kijkt een Buyer Attribution Touchpoint als in Salesforce?**

Hier is een schermafbeelding van een BAT in [!DNL Salesforce] :

![](assets/buyer-touchpoints-and-buyer-attribution-touchpoints-2.png){width="600" zoomable="yes"}
