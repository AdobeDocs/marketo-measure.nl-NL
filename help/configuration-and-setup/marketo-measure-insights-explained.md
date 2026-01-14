---
description: '[!DNL Marketo Measure] Uitgelichte inzichten -  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] Uitgelichte inzichten'
exl-id: d479a15f-4c92-4302-8ce8-6487645012e1
feature: Reporting
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 0%

---

# [!DNL Marketo Measure] Uitgelichte inzichten {#marketo-measure-insights-explained}

Leer meer over de weergave [!DNL Marketo Measure] Inzichten in [!DNL Salesforce] , inclusief wat de verschillende pictogrammen vertegenwoordigen en hoe u de functie kunt gebruiken. Deze functie is vooral handig voor het bekijken van de eerste 20 sessies van een lead, contactpersoon of account.

Zodra iemand door de [!DNL Marketo Measure] JavaScript wordt bijgehouden en een formulier op uw website invult, wordt de persoon een lead in uw systeem en worden de digitale marketinggegevens ervan verzonden naar uw Salesforce (SFDC) org. Wanneer dit gebeurt, worden de gegevens van het aanraakpunt weergegeven die zijn ingevuld in de sectie [!DNL Marketo Measure] Inzichten van lead (een Canvas-app) op de objecten Lead/Contact/Opportunity/Account.

Eerst zie je in het midden van je inzichten het aantal sessies dat de persoon op je website heeft gehad. U kunt door deze zittingen scrollen en navigeren bij wil.

![ eerst, ziet u in het middelste deel van uw inzichten, het aantal ](assets/marketo-app-1.png)

U kunt de roll-up van al uw zittingen bekijken als u &quot;allen&quot;in het midden-hogere deel van uw inzichten klikt. Daar begrijpt u de data van de afzonderlijke sessies, welk kanaal of bron deze bestuurde, en een reeks pictogrammen die meer informatie specificeren.

Het eerste wat je ziet, zijn de FT- of LC-pictogrammen. Deze vertegenwoordigen de aanraakpuntpositie van de weergegeven sessies. Met name FT staat voor First Touch en LC standaard voor Lead Creation. U kunt meerdere sessies hebben, maar slechts één aanraakpunt kan de FT of LC zijn. U zult nooit veelvoudige FTs of LCs vinden verbonden aan één persoon.

De pictogrammen die er als papier uitzien, geven aan dat er een paginaweergave is opgetreden binnen de sessie. Het is waarschijnlijk dat elke sessie dit pictogram bevat.

![ de pictogrammen die als document kijken wijzen erop dat een paginamening ](assets/marketo-app-2.png) gebeurde

Het pictogram dat er als een bekeraar uitziet, geeft aan dat er een A/B-testexperiment is uitgevoerd. We integreren nu met Optimizely en VWO. Met deze integratie kunnen we het experiment en de variatie die de gebruiker op zijn specifieke sessie zag, kracht bijzetten.

![ het pictogram dat als een bekersignalen kijkt dat een test A/B ](assets/marketo-app-3.png)

Als u op een specifieke sessie klikt (u doet dit door op de werkelijke datum van de sessie of in het bovenste middelste deel van de gegroepeerde sessies te klikken), kunt u de sessiedetails bekijken. In elke sessie kunt u alle specifieke pagina&#39;s zien die de gebruiker op datum en tijd heeft besteld.

![ als u om het even welke specifieke zitting klikt (u kunt dit doen door ](assets/marketo-app-4.png) te klikken

Aan de rechterkant van elke sessie kunt u meer granulaire marketinggegevens zien die de velden [!DNL Marketo Measure] in uw SFDC verdringen. In dit voorbeeld ziet u Advertentiegroep, Advertentie Inhoud, Campagne, Sleutelwoord, Medium. U kunt ook omlaag schuiven om meer [!DNL Marketo Measure] gegevens te zien die we verschaffen.

Ten slotte kunt u, zodra iemand een groot aantal sessies heeft, bepaalde filters gebruiken binnen [!UICONTROL Insights] om te zoeken naar specifieke onderdelen van de betrokkenheid op uw site. U kunt bijvoorbeeld filteren op [!UICONTROL Touchpoint Position] .

U kunt ook zoeken op Paginaweergaven, AB Tests of Forms.
