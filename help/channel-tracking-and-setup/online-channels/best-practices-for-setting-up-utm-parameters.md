---
unique-page-id: 18874732
description: Aanbevolen procedures voor het instellen van UTM-parameters - [!DNL Marketo Measure] - Productdocumentatie
title: Aanbevolen procedures voor het instellen van UTM-parameters
exl-id: 56019f41-b6ba-48c1-9bef-2a5f56d2d5f4
source-git-commit: 02f686645e942089df92800d8d14c76215ae558f
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 0%

---

# Aanbevolen procedures voor het instellen van UTM-parameters {#best-practices-for-setting-up-utm-parameters}

UTM-parameters zijn ideaal om uw marketinggegevens te segmenteren en te verwerken. [!DNL Marketo Measure] gebruikt en legt alle UTM-parameters vast om velden in Salesforce en de [!DNL Marketo Measure] app. Met deze informatie, zult u een korrelig inzicht in kunnen krijgen waar uw lood, kansen, en gesloten/gewonnen overeenkomsten van komen.

U kunt de [Google URL Builder](https://support.google.com/analytics/answer/1033867?hl=en){target="_blank"} to set up your UTM parameters and add them to your links within your marketing efforts. Use this [Google Spreadsheet](https://docs.google.com/spreadsheets/d/1QCIr1WUJQHE68cA4VTks2XE7nxuryaUymCEy_23-Oew/edit#gid=0){target="_blank"} als u een gemakkelijkere manier wilt om spoor van al uw verbindingen van UTM te houden.

## Waarden op hoog niveau voor elke parameter {#high-level-values-for-each-parameter}

**utm_medium**: Dit veld wordt toegewezen aan het veld Normaal. Gebruik utm_medium om het kanaal op hoog niveau aan te geven.

bijv.: [!UICONTROL Social], CPC, e-mail, web, organisch

Gebruik dit veld niet om het subkanaal uit te roepen.

**utm_source**: Dit veld wordt toegewezen aan het veld Aanraakpuntbron. Gebruik utm_source om het subkanaal te definiëren waarvan de lead afkomstig is.

bijv.: Facebook, Twitter, Linkedin, Drip_email, Email_blast, nieuwsbrief.

Houd het eenvoudig. Gebruik deze parameter niet voor het aangeven van het type advertentie, zoals voor opnieuw toewijzen, sponsoren, enzovoort. Voeg geen utm_source = homepage, webdirect, website toe. [!DNL Marketo Measure] Deze gegevens worden automatisch voor u ingevuld.

**utm_campagne**: Dit veld verwijst naar de naam van de advertentiecampagne. Gebruik utm_campagne om de titel van de campagne aan te duiden zoals deze in het advertentieplatform bestaat, of zoals deze intern wordt genoemd.

Dit is ook een goede parameter om Geolocation, het netwerktype van de Advertentie aan te duiden (vertoning v. onderzoek), etc.

We raden u aan onderstrepingstekens te gebruiken in plaats van spaties, en leestekens te gebruiken. Hierdoor wordt de kans op coderingsfouten bij het lezen van de parameters verkleind.

bijv.: AU_Idea_for_an_App_50k

**utm_content**: Dit is toegewezen aan Advertentie-inhoud. Gebruik Titel toevoegen in de parameter utm_content. Als het een afbeeldingsadvertentie is, gebruikt u een titel en neemt u de afmetingen van de advertentie op.

bijv.: [advertentitel] 200 x 400 px

**utm_term**: Dit is toegewezen aan trefwoordtekst. Gebruik deze parameter om het trefwoord aan te duiden dat betrekking heeft op het afvuren van de advertentie.

Laat deze parameter leeg als er geen trefwoord is voor de advertentie.

bijv.: iPhone App Ideas

**Houd het eenvoudig en beknopt. U mag inspanningen, termen en kanalen niet dupliceren.**

Wij stellen de UTM-hiërarchie als volgt voor:

Normaal > [!UICONTROL Source] > [!UICONTROL Campaign] > [!UICONTROL Content/Term]

bijv.: Indien een [!UICONTROL display] advertentie die op Facebook is geplaatst, raden we het volgende aan:

fakewebsite.com/

?utm_medium=social

&amp;utm_source=facebook

&amp;utm_campagne=Display_campagne_ID

&amp;utm_content=content_of_campagne

Let op: termen/kanalen worden niet gedupliceerd en in dit geval wordt utm_term niet gebruikt.

Als er vragen zijn, kunt u contact opnemen met uw Customer Success Manager of [Marketo-ondersteuning](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
