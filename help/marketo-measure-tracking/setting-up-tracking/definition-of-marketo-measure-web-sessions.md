---
unique-page-id: 18874564
description: Definitie van  [!DNL Marketo Measure]  zittingen van het Web -  [!DNL Marketo Measure]
title: Definitie van  [!DNL Marketo Measure]  zittingen van het Web
exl-id: ddf4f19d-2024-413a-b0ae-4efd468c24de
feature: Tracking
source-git-commit: 9a5e267b4b268d067fbbe89a00a4da96752a44db
workflow-type: tm+mt
source-wordcount: '807'
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

### Verouderd gedrag {#legacy-behavior}

**hoe lang een zitting het laatst?**

[!UICONTROL Marketo Measure] -sessies eindigen na 30 minuten inactiviteit op de website. Bijvoorbeeld:

Wanneer Haley adobe.com bezoekt, wordt een sessie gestart. Ze verkent de website een paar minuten en stapt weg van haar computer, maar laat de website open. Na 30 minuten inactiviteit eindigt de sessie.

Momenteel beschouwt [!UICONTROL Marketo Measure] paginanavigatie en formulierverzendingen alleen als activiteit. Schuiven door de webpagina of het boven een element op de pagina plaatsen wordt niet als activiteit beschouwd. Dus als Haley een bezoek brengt aan adobe.com om een blogbericht te lezen, en haar één uur nodig heeft om te lezen, eindigt haar websessie nog steeds na 30 minuten, zelfs als ze door de inhoud op de pagina scrolt.

### Nieuw gedrag {#new-behavior}

Voor nieuwe gebruikers is dit het standaardgedrag.

De bestaande gebruikers kunnen het nieuwe gedrag goedkeuren door de knevel onder **Montages** aan te zetten > **de Attributie van de Knoop** > **Kanaal van de Zitting Overdracht**. Zodra geactiveerd, kan deze instelling niet worden omgekeerd.

Wanneer een nieuwe sessie wordt gemaakt na 30 minuten inactiviteit, wordt het kanaal van de vorige sessie overgedragen als de nieuwe sessie binnen zeven dagen start. Deze overdracht geldt alleen voor rechtstreekse bezoeken (geen referentie of interne referentie). Als de inactiviteit meer dan zeven dagen duurt, wordt het kanaal voor de nieuwe sessie standaard ingesteld op Direct/Overige. Als Haley bijvoorbeeld landingpage.com uit Google bezoekt, meer dan 30 minuten inactief is en binnen zeven dagen terugkeert, behoudt de nieuwe sessie het Google-kanaal. Als dezelfde gebruiker de pagina echter via een ander kanaal terugkeert, wordt het niet-directe kanaal niet overschreven door het vorige Google-kanaal.

Alleen het kanaal wordt overgedragen, met uitzondering van de details van de campagne of de referentie. De reden hiervoor is dat de kanaalclassificatie wordt afgehandeld door Marketo Measure, terwijl andere gegevenspunten afzonderlijk worden verzameld.

**sociaal Sign-In**

Wanneer een bezoeker gebruikmaakt van aanmelden via een sociaal netwerk via Google, Microsoft of Apple, wordt de sessie samengevoegd tot één doorlopende sessie. Als een bezoeker bijvoorbeeld op een pagina uit LinkedIn landt, een Google sociale aanmelding voltooit en een pagina voor bedankt bereikt, telt deze allemaal als één sessie. Zonder de overdrachtschakelaar van het sessiekanaal aan te schakelen, zou het sociale inloggen afzonderlijke sessies maken die aan de externe referentie zijn toe te schrijven.

## Vervaldatum op basis van kanalen {#channel-based-expiration}

[!DNL Marketo Measure] begint altijd een nieuwe sessie wanneer een gebruiker via een ander digitaal marketingkanaal of een externe website naar uw website komt. Dit omvat het volgende:

* Een verwijzingswebsite
* Sociale kanalen ([!DNL Facebook], [!DNL LinkedIn], enzovoort)
* Betaalde of organische zoekkanalen ([!DNL Google/Bing])

**Verwijzing Websites en Sociale Kanalen**

Telkens wanneer een bezoeker via een verwijzende website of een sociaal kanaal naar uw website komt, wordt een nieuwe sessie gestart.

Zeg dat Haley op LinkedIn is, klikt op een [!DNL Marketo Measure] -bericht en wordt omgeleid naar de website van de Adobe. Vervolgens ziet Haley tijdens het schuiven door [!DNL Facebook] nog een [!DNL Marketo Measure] -bericht. Wanneer ze op dit bericht klikt en naar de site van de Adobe wordt omgeleid, wordt de eerste websessie die betrekking heeft op [!DNL LinkedIn] beëindigd en wordt een nieuwe sessie gestart die betrekking heeft op [!DNL Facebook] .

**Betaalde of Organic Kanalen van het Onderzoek**

Nieuwe sessies beginnen op elk moment dat een gebruiker via betaalde of organische zoekkanalen naar uw site komt. Als Haley naar de website van de Adobe komt door middel van organische zoekopdrachten en vervolgens onmiddellijk uw website bezoekt via een betaalde advertentie op Google, worden er twee aparte sessies gemaakt.

**Direct Verkeer van het Web**

Als een bezoeker naar uw website komt door de URL van uw website in de adresbalk te typen, wordt niet altijd een nieuwe sessie gestart.

Als Haley&#39;s eerste websessie begint als resultaat van een bezoek van een verwijzingssite, een sociaal kanaal of een betaald/biologisch zoekkanaal en vervolgens de site bezoekt via web direct, wordt er geen nieuwe sessie gestart.

_Nochtans_, als de eerste Webzitting van Haley van Web Direct voortkwam, en dan bezoekt zij de website via _een externe/verwijzingsplaats_, beëindigt de eerste zitting en een nieuwe zitting wordt geopend met betrekking tot de externe/verwijzingsplaats.

## Googles Analytics sessies {#google-analytics-sessions}

Er zijn enkele overeenkomsten met de manier waarop sessies worden gedefinieerd in [!DNL Marketo Measure] en Googles Analytics. Voor meer informatie over hoe de Googles Analytics zittingen bepalen, bezoek: [ https://support.google.com/analytics/answer/2731565?hl=en ](https://support.google.com/analytics/answer/2731565?hl=en){target="_blank"} 
