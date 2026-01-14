---
description: Best practices voor het instellen van UTM-parameterrichtlijnen voor Marketo Measure-gebruikers
title: Aanbevolen procedures voor het instellen van UTM-parameters
exl-id: 56019f41-b6ba-48c1-9bef-2a5f56d2d5f4
feature: UTM Parameters
hidefromtoc: true
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 0%

---

# Aanbevolen procedures voor het instellen van UTM-parameters {#best-practices-for-setting-up-utm-parameters}

UTM-parameters zijn ideaal om uw marketinggegevens te segmenteren en te verwerken. [!DNL Marketo Measure] gebruikt en legt alle UTM-parameters vast om velden in Salesforce en de [!DNL Marketo Measure] -app te vullen. Met deze informatie, kunt u een korrelig inzicht krijgen in waar uw lood, kansen, en gesloten/gewonnen overeenkomsten van komen.

U kunt de [&#x200B; Bouwer van Google URL &#x200B;](https://support.google.com/analytics/answer/1033867?hl=en){target="_blank"} gebruiken aan opstelling uw parameters UTM en hen toevoegen aan uw verbindingen binnen uw marketing inspanningen. Gebruik dit [&#x200B; Spreadsheet van Google &#x200B;](https://docs.google.com/spreadsheets/d/1QCIr1WUJQHE68cA4VTks2XE7nxuryaUymCEy_23-Oew/edit#gid=0){target="_blank"} als u een gemakkelijkere manier wilt om al uw verbindingen te volgen UTM.

## Waarden op hoog niveau voor elke parameter {#high-level-values-for-each-parameter}

**utm_medium**: Dit gebied brengt aan het gebied van Medium in kaart. Gebruik utm_medium om het kanaal op hoog niveau aan te geven.

Bijvoorbeeld [!UICONTROL Social], CPC, email, web, organisch

Gebruik dit veld niet om het subkanaal uit te roepen.

**utm_source**: Dit gebied brengt aan het gebied van Touchpoint Source in kaart. Gebruik utm_source om het subkanaal te definiëren waarvan de lead afkomstig is.

Bijvoorbeeld Facebook, Twitter, Linkedin, Drip_email, Email_blast, nieuwsbrief.

Houd het eenvoudig. Gebruik deze parameter niet om typen advertenties aan te duiden, zoals opnieuw richten of sponsoren. Voeg geen utm_source = homepage, webdirect, website toe. Deze gegevens worden automatisch door [!DNL Marketo Measure] ingevuld.

**utm_campagne**: Dit gebied brengt aan de Naam van de Campagne van de Add in kaart. Gebruik utm_campagne om de titel van de campagne aan te duiden zoals deze in het advertentieplatform bestaat, of zoals deze intern wordt genoemd.

Dit is ook een goede parameter om Geolocation, het netwerktype van de Advertentie aan te duiden (vertoning v. onderzoek), etc.

U wordt aangeraden onderstrepingstekens te gebruiken in plaats van spaties en het gebruik van leestekens te vermijden. Hierdoor wordt de kans op coderingsfouten bij het lezen van de parameters verkleind.

AU_Idea_for_an_App_50k

**utm_content**: Dit brengt aan de Inhoud van de Advertentie in kaart. Gebruik Titel toevoegen in de parameter utm_content. Als het een afbeeldingsadvertentie is, gebruikt u een titel en neemt u de afmetingen van de advertentie op.

Bijvoorbeeld, [ en titel ] 200x400px

**utm_term**: Dit brengt aan de Tekst van het Sleutelwoord in kaart. Gebruik deze parameter om het trefwoord aan te duiden dat betrekking heeft op het afvuren van de advertentie.

Laat deze parameter leeg als er geen trefwoord is voor de advertentie.

IPhone App Ideas, bijvoorbeeld

**houd het eenvoudig en beknopt. Dubbele inspanningen, termijnen, en kanalen niet.**

Wij stellen de UTM-hiërarchie als volgt voor:

Medium > [!UICONTROL Source] > [!UICONTROL Campaign] > [!UICONTROL Content/Term]

Als bijvoorbeeld een [!UICONTROL display] -advertentie op Facebook wordt geplaatst, raden we het volgende aan:

`fakewebsite.com/?utm_medium=social&utm_source=facebook&utm_campaign=Display_campaign_ID&utm_content=content_of_campaign`

Let op: termen/kanalen worden niet gedupliceerd en in dit geval wordt utm_term niet gebruikt.

Als er om het even welke vragen zijn, bereik uit aan het Team van de Rekening van Adobe (uw Manager van de Rekening) of [&#x200B; Steun van Marketo &#x200B;](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
