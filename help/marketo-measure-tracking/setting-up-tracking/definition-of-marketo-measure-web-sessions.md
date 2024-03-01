---
unique-page-id: 18874564
description: Definitie van [!DNL Marketo Measure] Websessies - [!DNL Marketo Measure]
title: Definitie van [!DNL Marketo Measure] Websessies
exl-id: ddf4f19d-2024-413a-b0ae-4efd468c24de
feature: Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 0%

---

# Definitie van [!DNL Marketo Measure] Websessies {#definition-of-marketo-measure-web-sessions}

Meer informatie [!DNL Marketo Measure] definieert websessies.

A **websessie** verwijst naar de interactie van een individu met uw website gedurende een bepaalde periode. De sessie begint wanneer een gebruiker op uw website landt.

Haley bezoekt bijvoorbeeld adobe.com. Haar bezoek aan de site begint een sessie. Wanneer Haley de site verlaat, door het tabblad/de webbrowser te sluiten of weg van de site te navigeren, wordt de sessie beëindigd.

Eén gebruiker kan niet meerdere sessies tegelijk openen. Als Haley wordt geopend [!DNL adobe.com] op 10 aparte tabbladen is slechts één sessie gemaakt voor haar bezoek aan de website .

## Hoe werkt [!DNL Marketo Measure] een nieuwe sessie definiëren? {#how-does-marketo-measure-define-a-new-session}

Er zijn een paar dingen die bepalen wanneer een zitting beëindigt, en wanneer een nieuwe zitting begint. De twee belangrijkste manieren [!DNL Marketo Measure] sessies kunnen worden beëindigd:

* **Vervaldatum gebaseerd op tijd**
* **Vervaldatum op basis van kanalen**

## Vervaldatum op basis van tijd {#time-based-expiration}

**Hoe lang duurt een sessie?**

[!DNL Marketo Measure] de sessies eindigen na 30 minuten inactiviteit op de website . Bijvoorbeeld:

Wanneer Haley adobe.com bezoekt, wordt een sessie gestart. Ze verkent de website een paar minuten en stapt weg van haar computer, maar laat de website open. Na 30 minuten inactiviteit wordt de sessie beëindigd.

Momenteel [!DNL Marketo Measure] beschouwt paginanavigatie en formulierverzendingen alleen als activiteit. Schuiven door de webpagina of het boven een element op de pagina plaatsen wordt niet als activiteit beschouwd. Dus als Haley een bezoek brengt aan adobe.com om een blogbericht te lezen, en haar één uur nodig heeft om te lezen, eindigt haar websessie nog steeds na 30 minuten, zelfs als ze door de inhoud op de pagina scrolt.

## Vervaldatum op basis van kanalen {#channel-based-expiration}

[!DNL Marketo Measure] wordt een nieuwe sessie gestart wanneer een gebruiker via een ander digitaal marketingkanaal of een externe website naar uw website komt. Dit omvat:

* Een verwijzingswebsite
* Sociale kanalen ([!DNL Facebook], [!DNL LinkedIn], enz.)
* Betaalde of organische zoekkanalen ([!DNL Google/Bing])

**Referral-websites en sociale kanalen**

Elke keer dat een bezoeker via een verwijzende website of een sociaal kanaal naar uw website komt, wordt een nieuwe sessie gestart.

Zeg dat Haley op LinkedIn is, klikt op een [!DNL Marketo Measure] post en wordt omgeleid naar de website van de Adobe. Daarna, terwijl u doorbladert [!DNL Facebook], Haley ziet er een [!DNL Marketo Measure] post. Wanneer ze op dit bericht klikt en naar de site van de Adobe wordt omgeleid, veroorzaakt dit de eerste websessie die betrekking heeft op [!DNL LinkedIn] om te beëindigen, en een nieuwe zitting met betrekking tot [!DNL Facebook] begint.

**Betaalde of organische zoekkanalen**

Nieuwe sessies beginnen telkens wanneer een gebruiker via betaalde of organische zoekkanalen naar uw site komt. Als Haley naar de website van de Adobe komt door middel van organische zoekopdrachten en vervolgens onmiddellijk uw website bezoekt via een betaalde advertentie op Google, worden er twee aparte sessies gemaakt.

**Web Direct Traffic**

Als een bezoeker naar uw website komt door de URL van uw website in de adresbalk te typen, wordt niet altijd een nieuwe sessie gestart.

Als Haley&#39;s eerste websessie begint als resultaat van een bezoek van een verwijzingssite, een sociaal kanaal of een betaald/biologisch zoekkanaal en vervolgens de site bezoekt via web direct, wordt er geen nieuwe sessie gestart.

_Echter_, als Haley&#39;s eerste websessie voortkwam uit Web Direct, en dan bezoekt ze de website via _een externe/verwijzingslocatie_, eindigt de eerste sessie en wordt een nieuwe sessie geopend met betrekking tot de externe site/verwijzingssite.

## Googles Analytics sessies {#google-analytics-sessions}

Er zijn enkele overeenkomsten met hoe [!DNL Marketo Measure] en Googles Analytics definiëren sessies. Ga voor meer informatie over hoe Googles Analytics sessies definiëren naar: [https://support.google.com/analytics/answer/2731565?hl=en](http://support.google.com/analytics/answer/2731565?hl=en){target="_blank"}
