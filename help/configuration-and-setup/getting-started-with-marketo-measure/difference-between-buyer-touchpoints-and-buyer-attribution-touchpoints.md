---
unique-page-id: 18874646
description: Verschil tussen aanraakpunten voor kopers en kenmerkaanraakpunten voor kopers - [!DNL Marketo Measure] - Productdocumentatie
title: Verschil tussen aanraakpunten voor kopers en aanraakpunten voor koperkenmerken
exl-id: 19109271-7b59-44c0-b1ff-e3b0bba9f5ce
source-git-commit: b59c79236d3e324e8c8b07c5a6d68bd8176fc8a9
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 0%

---

# Verschil tussen aanraakpunten voor kopers en aanraakpunten voor koperkenmerken {#difference-between-buyer-touchpoints-and-buyer-attribution-touchpoints}

Leer wat een Aanraakpunt voor kopers (BT) en een Aanraakpunt voor koperkenmerken (BAT) bepaalt, de verschillen tussen beide, en beantwoord veelgestelde vragen.

Het belangrijkste onderscheid tussen aanraakpunten voor kopers en aanraakpunten voor kopers is hun relatie met [!DNL Salesforce] Objecten. BT&#39;s hebben betrekking op de objecten Lead, Contact en Case, maar niet op het object Opportunity. Dat betekent dat er nooit inkomsten zullen zijn die aan de aanraakpunten van de koper zijn gekoppeld.

Terwijl het object Aanraakpunt voor koperkenmerk gerelateerd is aan de objecten Contact, Account en Opportunity, maar niet aan het object Lead. Dit betekent dat er nooit aanraakpunten voor koperkenmerken zijn gekoppeld aan leads. In het BBT-object ziet u inkomsten die zijn gekoppeld aan specifieke marketinginteracties.

Verschil tussen BT en BBT:

<table> 
 <colgroup> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td>Aanraakpunt koper (BT)</td> 
   <td>Aanraakpunt voor koperkenmerk (BBT)</td> 
  </tr> 
  <tr> 
   <td> 
    <ul> 
     <li>Heeft betrekking op de objecten Lead, Contact en Case</li> 
     <li>Heeft geen betrekking op het object Opportunity</li> 
     <li>Ontvangsten zijn niet gekoppeld aan een aanraakpunt voor kopers</li> 
    </ul></td> 
   <td> 
    <ul> 
     <li>Heeft betrekking op de contact-, account- en opportunity-objecten</li> 
     <li>Heeft geen betrekking op het object Lead</li> 
     <li>Aangezien een aanraakpunt voor koperkenmerken is gekoppeld aan een opportunity, zijn aan alle BBT's inkomsten gekoppeld</li> 
    </ul></td> 
  </tr> 
 </tbody> 
</table>

## Veelgestelde vragen {#faq}

**Wanneer wordt een aanraakpunt voor kopers een aanraakpunt voor koperkenmerken?**

Een BT wordt een BBT zodra dit BT wordt geassocieerd met een Contact dat een bijbehorende Kans heeft. Een zeer belangrijk ding om te begrijpen is dat één specifieke marketing interactie BT en BBT kan zijn.

**Kan een aanraakpunt voor kopers beschikken over een aanraakpunt positie van Opportunity Creation (OC)?**

Een aanraakpunt voor kopers heeft alleen een aanraakpunt met de positie First Touch (FT), Lead Creation (LC) of Formulier verzenden (tussenliggende aanraakpunten). Aangezien BTs niet met Kansen verwant is het niet mogelijk voor BT om een Positie van het Aanraakpunt van Kans te hebben creeert of gesloten.

**Hoe wordt gebruikgemaakt van aanraakpuntgegevens voor kopers?**

Klanten gebruiken doorgaans gegevens van het aanraakpunt voor kopers om de top van de trechter en het midden van de treindienst te begrijpen. Betekenis [!DNL Marketo Measure] gebruikers weten wie formulieren verzendt, wie hun site bekijkt, welk blogbericht goed presteert, wat AdWords en welke drijfveer tot conversie leidt, enz. Gegevens van aanraakpunten voor kopers zijn ideaal voor het begrijpen van de betrokkenheid van uw leads en contactpersonen.

**Hoe ziet een aanraakpunt voor kopers eruit in Salesforce?**

Hier is een screenshot van een BT in [!DNL Salesforce]:

![](assets/1.png)

**Hoe ziet een aanraakpunt voor koperkenmerken eruit in Salesforce?**

Hier is een screenshot van een BBT in [!DNL Salesforce]:

![](assets/2.png)
