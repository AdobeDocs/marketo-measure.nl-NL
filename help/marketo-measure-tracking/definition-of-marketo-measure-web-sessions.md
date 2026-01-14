---
description: Definitie van  [!DNL Marketo Measure]  de richtlijnen van de Zittingen van het Web voor de gebruikers van Marketo Measure
title: Definitie van  [!DNL Marketo Measure]  zittingen van het Web
exl-id: ddf4f19d-2024-413a-b0ae-4efd468c24de
feature: Tracking
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 0%

---

# Definitie van [!DNL Marketo Measure] websessies {#definition-of-marketo-measure-web-sessions}

Leer hoe [!DNL Marketo Measure] websessies definieert.

A **Webzitting** verwijst naar de interactie van een individu met uw website tijdens een bepaalde hoeveelheid tijd. De sessie begint wanneer een gebruiker op uw website landt.

Haley bezoekt bijvoorbeeld adobe.com. Haar bezoek aan de site begint een sessie. Wanneer Haley de site verlaat, door het tabblad/de webbrowser te sluiten of weg van de site te navigeren, wordt de sessie beëindigd.

Eén gebruiker kan niet meerdere sessies tegelijk openen. Als Haley [!DNL adobe.com] op tien aparte tabbladen opent, is er slechts één sessie gemaakt met betrekking tot haar bezoek aan de website.

## Hoe definieert [!DNL Marketo Measure] een nieuwe sessie? {#how-does-marketo-measure-define-a-new-session}

Er zijn een paar dingen die bepalen wanneer een zitting beëindigt, en wanneer een nieuwe zitting begint. De twee belangrijkste manieren waarop [!DNL Marketo Measure] -sessies kunnen worden beëindigd, zijn:

* **Op tijd-gebaseerde afloop**
* **op kanaal-gebaseerde afloop**

## Vervaldatum op basis van tijd {#time-based-expiration}

**hoe lang een zitting het laatst?**

[!DNL Marketo Measure] -sessies eindigen na 30 minuten inactiviteit op de website. Bijvoorbeeld:

Wanneer Haley adobe.com bezoekt, wordt een sessie gestart. Ze verkent de website een paar minuten en stapt weg van haar computer, maar laat de website open. Na 30 minuten inactiviteit eindigt de sessie.

Momenteel beschouwt [!DNL Marketo Measure] paginanavigatie en formulierverzendingen alleen als activiteit. Schuiven door de webpagina of het boven een element op de pagina plaatsen wordt niet als activiteit beschouwd. Dus als Haley een bezoek brengt aan adobe.com om een blogbericht te lezen, en haar één uur nodig heeft om te lezen, eindigt haar websessie nog steeds na 30 minuten, zelfs als ze door de inhoud op de pagina scrolt.

## Vervaldatum op basis van kanalen {#channel-based-expiration}

[!DNL Marketo Measure] begint altijd een nieuwe sessie wanneer een gebruiker via een ander digitaal marketingkanaal of een externe website naar uw website komt. Dit omvat het volgende:

* Een verwijzingswebsite
* Sociale kanalen ([!DNL Facebook], [!DNL LinkedIn], enzovoort)
* Betaalde of organische zoekkanalen ([!DNL Google/Bing])

**Verwijzing Websites en Sociale Kanalen**

Telkens wanneer een bezoeker via een verwijzende website of een sociaal kanaal naar uw website komt, wordt een nieuwe sessie gestart.

Als Haley zich op LinkedIn bevindt, klikt u op een [!DNL Marketo Measure] -bericht en wordt deze omgeleid naar de Adobe-website. Vervolgens ziet Haley tijdens het schuiven door [!DNL Facebook] nog een [!DNL Marketo Measure] -bericht. Wanneer ze op dit bericht klikt en naar de Adobe-site wordt omgeleid, wordt de eerste websessie die betrekking heeft op [!DNL LinkedIn] beëindigd en wordt een nieuwe sessie gestart die betrekking heeft op [!DNL Facebook] .

**Betaalde of Organic Kanalen van het Onderzoek**

Nieuwe sessies beginnen op elk moment dat een gebruiker via betaalde of organische zoekkanalen naar uw site komt. Als Haley naar de Adobe-website komt via een zoekopdracht op basis van biologische gegevens en vervolgens onmiddellijk uw website bezoekt via een betaalde advertentie op Google, worden er twee aparte sessies gemaakt.

**Direct Verkeer van het Web**

Als een bezoeker naar uw website komt door de URL van uw website in de adresbalk te typen, wordt niet altijd een nieuwe sessie gestart.

Als Haley&#39;s eerste websessie begint als resultaat van een bezoek van een verwijzingssite, een sociaal kanaal of een betaald/biologisch zoekkanaal en vervolgens de site bezoekt via web direct, wordt er geen nieuwe sessie gestart.

_Nochtans_, als de eerste Webzitting van Haley van Web Direct voortkwam, en dan bezoekt zij de website via _een externe/verwijzingsplaats_, beëindigt de eerste zitting en een nieuwe zitting wordt geopend met betrekking tot de externe/verwijzingsplaats.

## Google Analytics-sessies {#google-analytics-sessions}

Er zijn enkele overeenkomsten met de manier waarop sessies door [!DNL Marketo Measure] en Google Analytics worden gedefinieerd. Voor meer informatie over hoe Google Analytics zittingen bepaalt, bezoek: [&#x200B; https://support.google.com/analytics/answer/2731565?hl=en &#x200B;](https://support.google.com/analytics/answer/2731565?hl=en){target="_blank"}
