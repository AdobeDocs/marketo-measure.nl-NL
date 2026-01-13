---
description: Verschil tussen een Google Analytics-conversie en een Buyer Touchpoint
title: Verschil tussen een Google Analytics-conversie en een Buyer Touchpoint
exl-id: d09d963c-3207-467c-852a-d1edd49511fa
feature: Touchpoints
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 0%

---


# Verschil tussen een Google Analytics-conversie en een Buyer Touchpoint {#difference-between-a-google-analytics-conversion-and-a-buyer-touchpoint}

Leer wat een [!DNL Google Analytics (GA)] doel is en hoe het van een Buyer Touchpoint onderscheidt.

**wat zijn de Omzettingen van de Analyse van Google?**

[!UICONTROL Google Analytics] conversies worden bepaald door de manier waarop een markator of webontwikkelaar &#39;doel&#39;-voltooiing op een bepaalde website codeert. Doelen zouden volgens Google kunnen worden beschouwd als &quot;het maken van een aankoop (voor een e-commercesite), het voltooien van een gameniveau (voor een mobiele gaming app), of het indienen van een contactinformatieformulier (voor een marketing- of hoofdproductiesite).&quot; Meestal zien marketers doelen/conversies als iemand die een informatieve vorm invult.

Nochtans, kunnen de doelstellingen niet worden gecodeerd om specifiek gedrag te beheren. In plaats daarvan zijn er Goal Types die een webontwikkelaar kan configureren. Hieronder volgen enkele voorbeelden:

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
   <td><p>Bestemming</p></td>
   <td>Een specifieke locatie wordt geladen</td>
   <td><em> Dank u voor het registreren!</em> webpagina of toepassingsscherm</td>
  </tr>
  <tr>
   <td>Duur</td>
   <td>Sessies die een bepaalde hoeveelheid tijd of langer duren</td>
   <td>10 minuten of langer besteed aan een ondersteuningssite</td>
  </tr>
  <tr>
   <td>Pagina's/Screens per sessie</td>
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

Dit betekent dat Google de weergave van je pagina Bedankt als een conversie beschouwt. Vanuit Google Analytics-standpunt is dit een realisatie waar de meeste marketeers mee in overeenstemming zijn.

Aanraakpunten voor kopers functioneren echter anders.

**hoe verschillen de Aanraakpunten van de Koper?**

[!DNL Marketo Measure] JavaScript houdt de sessiegegevens en formulierverzendingen bij voor alle vormen van een bepaalde site. Het is niet nodig om doelen te coderen vanuit een [!DNL Marketo Measure] -standpunt. Dit proces is automatisch. Voor het verzenden van formulieren rapporteert [!DNL Marketo Measure] elke keer dat een anonieme gebruiker informatievelden invult op een bepaald formulier en ook op de verzendknop klikt. [!DNL Marketo Measure] heeft geen pagina voor bedankt nodig om de formulierverzending op te nemen.

[!DNL Marketo Measure] maakt een aanraakpunt voor een formulier wanneer:

* Een lood/contact dat aan die omzettingen wordt geassocieerd verschijnt in uw CRM.
* De JS van [!DNL Marketo Measure] is aanwezig op de webpagina&#39;s die het formulier bevatten.
* Een formulier wordt binnen 30 minuten ingediend.

[!DNL Marketo Measure] negeert Google Analytic-omzettingen van bestemming wanneer:

* Een bot verzendt formulieren op een website (deze bots maken het meestal niet tot de CRM van een klant).
* Een gebruiker verzendt meer formulieren nadat het formulier voor het eerst is verzonden. [!DNL Marketo Measure] voert alleen de eerste conversie van die sessie uit.
* De gebruiker klikt meerdere keren op het verzenden van het formulier. [!DNL Marketo Measure] houdt alleen rekening met de eerste formulierverzending.
* De gebruiker laadt de pagina Hartelijk dank meerdere keren opnieuw.
* De gebruiker gebruikt alle gereedschappen voor het blokkeren van advertenties.

Zoals u kunt zien, zijn er fundamentele verschillen tussen wat GA en [!DNL Marketo Measure] een omzetting als te beschouwen. Het is daarom waarschijnlijk dat het aantal conversies en het aantal aanraakpunten van formulieren verschillen.
