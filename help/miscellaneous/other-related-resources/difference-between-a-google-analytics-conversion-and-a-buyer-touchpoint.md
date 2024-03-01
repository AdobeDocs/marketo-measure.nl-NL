---
unique-page-id: 18874648
description: Verschil tussen een conversie van Googles Analytics en een aanraakpunt voor kopers - [!DNL Marketo Measure]
title: Verschil tussen een conversie van Googles Analytics en een aanraakpunt voor kopers
exl-id: d09d963c-3207-467c-852a-d1edd49511fa
feature: Touchpoints
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 0%

---

# Verschil tussen een conversie van Googles Analytics en een aanraakpunt voor kopers {#difference-between-a-google-analytics-conversion-and-a-buyer-touchpoint}

Meer informatie over [!DNL Google Analytics (GA)] doel is en hoe het van een Aanraakpunt van de Koper onderscheidt.

**Wat zijn conversies van Googles Analytics?**

[!UICONTROL Google Analytics] conversies worden volledig bepaald door de manier waarop een markeerteken of een webontwikkelaar &#39;doel&#39; codeert voor een bepaalde website. Doelen zouden volgens Google kunnen worden beschouwd als &quot;het maken van een aankoop (voor een site van e-commerce), het voltooien van een gameniveau (voor een mobiele game-app), of het indienen van een contactformulier (voor een marketing- of lead generation-site).&quot; Meestal zien marketers doelen/conversies als iemand die een informatieve vorm invult.

Nochtans, kunnen de doelstellingen niet worden gecodeerd om zeer specifiek gedrag te beheren. In plaats daarvan zijn er Goal Types die een webontwikkelaar kan configureren. Hieronder volgen enkele voorbeelden:

<table> 
 <colgroup> 
  <col> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <td><strong>Type doel</strong></td> 
   <td><p><strong>Beschrijving</strong></p></td> 
   <td><strong>Voorbeeld</strong></td> 
  </tr> 
  <tr> 
   <td><p>Doel</p></td> 
   <td>Een specifieke locatie wordt geladen</td> 
   <td><em>Hartelijk dank voor uw registratie!</em> webpagina of toepassingsscherm</td> 
  </tr> 
  <tr> 
   <td>Duur</td> 
   <td>Sessies die een bepaalde hoeveelheid tijd of langer duren</td> 
   <td>10 minuten of langer besteed aan een ondersteuningssite</td> 
  </tr> 
  <tr> 
   <td>Pagina's/rasters per sessie</td> 
   <td>Een gebruiker bekijkt een specifiek aantal pagina's of schermen</td> 
   <td>Er zijn 5 pagina's of schermen geladen</td> 
  </tr> 
  <tr> 
   <td>Gebeurtenis</td> 
   <td>Een actie die is gedefinieerd als een gebeurtenis, wordt geactiveerd</td> 
   <td>Sociale aanbeveling, video afspelen en klikken</td> 
  </tr> 
 </tbody> 
</table>

De meeste marketeers vormen hun omzettingen als &quot;Doeldoelstellingen,&quot;betekenend dat zij gewoonlijk een danku pagina na een vorm creëren om dat een formele omzetting in overweging te nemen.

Dit betekent dat Google weergaven van je pagina als een conversie beschouwt. Vanuit het oogpunt van de Google Analytics is dit een realisatie waar de meeste marketeers het mee eens zijn.

Aanraakpunten voor kopers functioneren echter heel anders.

**Hoe verschillen de aanraakpunten van de koper?**

[!DNL Marketo Measure] JavaScript houdt sessiegegevens en formulierverzendingen bij op alle vormen van een bepaalde site. Er is geen behoefte aan codedoelstellingen van a [!DNL Marketo Measure] standpunt. Dit proces is automatisch. Voor het indienen van formulieren: [!DNL Marketo Measure] Hiermee wordt een formulierinvulling gerapporteerd telkens wanneer een anonieme gebruiker informatievelden invult op een bepaald formulier en ook op de knop Formulier verzenden klikt. [!DNL Marketo Measure] heeft geen pagina voor bedankt nodig om de formulierverzending op te nemen.

[!DNL Marketo Measure] wordt een aanraakpunt voor formulieren gemaakt wanneer:

* Een lood/contact dat aan die omzettingen wordt geassocieerd verschijnt in uw CRM.
* De [!DNL Marketo Measure] JS is aanwezig op de webpagina&#39;s die het formulier bevatten.
* Een formulier wordt binnen 30 minuten ingediend.

[!DNL Marketo Measure] zal de Analytische omzettingen van de Bestemming van Google negeren wanneer:

* Een bot verzendt formulieren op een website (deze bots maken het meestal niet tot de CRM van een klant).
* Een gebruiker verzendt meer formulieren nadat het formulier voor het eerst is verzonden. [!DNL Marketo Measure] alleen de eerste conversie vanaf die sessie uitvoeren.
* De gebruiker klikt meerdere keren op het verzenden van het formulier. [!DNL Marketo Measure] alleen de eerste formulierverzending in overweging nemen.
* De gebruiker laadt de pagina Hartelijk dank meerdere keren opnieuw.
* De gebruiker gebruikt alle gereedschappen voor het blokkeren van advertenties.

Zoals u ziet, zijn er fundamentele verschillen tussen wat GA en [!DNL Marketo Measure] een conversie als zodanig beschouwen. Daarom is het zeer waarschijnlijk dat het aantal conversies en het aantal aanraakpunten van formulieren zullen verschillen.
