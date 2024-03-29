---
unique-page-id: 18874732
description: Aanbevolen procedures voor het instellen van UTM-parameters - [!DNL Marketo Measure]
title: Aanbevolen procedures voor het instellen van UTM-parameters
exl-id: 56019f41-b6ba-48c1-9bef-2a5f56d2d5f4
feature: UTM Parameters
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 0%

---

# Aanbevolen procedures voor het instellen van UTM-parameters {#best-practices-for-setting-up-utm-parameters}

UTM-parameters zijn ideaal om uw marketinggegevens te segmenteren en te verwerken. [!DNL Marketo Measure] gebruikt en legt alle UTM-parameters vast om velden in Salesforce en de [!DNL Marketo Measure] app. Met deze informatie, kunt u een korrelig inzicht krijgen in waar uw lood, kansen, en gesloten/gewonnen overeenkomsten van komen.

U kunt de [Google URL Builder](https://support.google.com/analytics/answer/1033867?hl=en){target="_blank"} to set up your UTM parameters and add them to your links within your marketing efforts. Use this [Google Spreadsheet](https://docs.google.com/spreadsheets/d/1QCIr1WUJQHE68cA4VTks2XE7nxuryaUymCEy_23-Oew/edit#gid=0){target="_blank"} als u een eenvoudigere manier wilt om al uw UTM-koppelingen bij te houden.

## Waarden op hoog niveau voor elke parameter {#high-level-values-for-each-parameter}

**utm_medium**: Dit veld wordt toegewezen aan het veld Normaal. Gebruik utm_medium om het kanaal op hoog niveau aan te geven.

Bijvoorbeeld: [!UICONTROL Social], CPC, e-mail, web, organisch

Gebruik dit veld niet om het subkanaal uit te roepen.

**utm_source**: Dit veld wordt toegewezen aan het veld Aanraakpuntbron. Gebruik utm_source om het subkanaal te definiëren waarvan de lead afkomstig is.

Bijvoorbeeld Facebook, Twitter, Linkedin, Drip_email, Email_blast, nieuwsbrief.

Houd het eenvoudig. Gebruik deze parameter niet om typen advertenties aan te duiden, zoals opnieuw richten of sponsoren. Voeg geen utm_source = homepage, webdirect, website toe. [!DNL Marketo Measure] Deze gegevens worden automatisch voor u ingevuld.

**utm_campagne**: Dit veld verwijst naar de naam van de advertentiecampagne. Gebruik utm_campagne om de titel van de campagne aan te duiden zoals deze in het advertentieplatform bestaat, of zoals deze intern wordt genoemd.

Dit is ook een goede parameter om Geolocation, het netwerktype van de Advertentie aan te duiden (vertoning v. onderzoek), etc.

U wordt aangeraden onderstrepingstekens te gebruiken in plaats van spaties en het gebruik van leestekens te vermijden. Hierdoor wordt de kans op coderingsfouten bij het lezen van de parameters verkleind.

AU_Idea_for_an_App_50k

**utm_content**: Dit is toegewezen aan Inhoud toevoegen. Gebruik Titel toevoegen in de parameter utm_content. Als het een afbeeldingsadvertentie is, gebruikt u een titel en neemt u de afmetingen van de advertentie op.

Bijvoorbeeld: [advertentietak] 200 x 400 px

**utm_term**: Dit is toegewezen aan Trefwoordtekst. Gebruik deze parameter om het trefwoord aan te duiden dat betrekking heeft op het afvuren van de advertentie.

Laat deze parameter leeg als er geen trefwoord is voor de advertentie.

IPhone App Ideas, bijvoorbeeld

**Houd het eenvoudig en beknopt. U mag inspanningen, termen en kanalen niet dupliceren.**

Wij stellen de UTM-hiërarchie als volgt voor:

Normaal > [!UICONTROL Source] > [!UICONTROL Campaign] > [!UICONTROL Content/Term]

Als een [!UICONTROL display] advertentie die op Facebook is geplaatst, raden we het volgende aan:

fakewebsite.com/

?utm_medium=social

&amp;utm_source=facebook

&amp;utm_campagne=Display_campagne_ID

&amp;utm_content=content_of_campagne

Let op: termen/kanalen worden niet gedupliceerd en in dit geval wordt utm_term niet gebruikt.

Neem contact op met het accountteam van de Adobe (uw accountmanager) of [Marketo-ondersteuning](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
