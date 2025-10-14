---
unique-page-id: 37356030
description: Parameter voor bijhouden van e-mail - [!DNL Marketo Measure]
title: Parameter voor bijhouden van e-mail
exl-id: e2cfd59e-ce4a-4cbb-b64a-828d1db7410f
feature: Tracking
source-git-commit: 4787f765348da71bc149c997470ce678ba498772
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 0%

---

# Parameter voor bijhouden van e-mail {#email-tracking-parameter}

De [!DNL Marketo Measure] Met Parameter voor e-mailbeheer kunnen marketers klikken op e-mail als verzonden formulieren behandelen, zodat er aanraakpunten voor deze handelingen worden gegenereerd. Zonder een parameter voor het bijhouden van e-mailberichten te gebruiken, worden doorklikbewerkingen van een e-mail alleen behandeld als &quot;webbezoeken&quot; totdat de gebruiker daadwerkelijk verbinding maakt met de site via een formulierverzending of een webchat.

## Gevallen gebruiken  {#use-cases}

**Webinar-registratie**: Het marketingteam stuurt een e-mailuitnodiging met één knop om zich te registreren voor een webinar. Omdat het e-mailbericht al over de gegevens van de persoon beschikt, registreert deze persoon met één klik automatisch. De landingspagina bevat de parameter voor het bijhouden van e-mailberichten, zodat ze door de bevestigingspagina klikken en op de bevestigingspagina landen. [!DNL Marketo Measure] U kunt het e-mailadres vastleggen en de doorklikken als een invulling van het formulier behandelen, waardoor een aanraakpunt wordt gegenereerd.

**Inhoud downloaden**: Het team voor het op de markt brengen van inhoud wil een recent eBook promoten die zij via een e-mail hebben gepubliceerd met een directe downloadkoppeling. Wanneer de e-mailsjabloon is gemaakt, bevat de pagina voor downloadbevestiging de parameter voor het bijhouden van e-mailberichten, zodat wanneer deze klikken, [!DNL Marketo Measure] kan het e-mailadres vastleggen. Zonder een formulier op de site in te vullen, [!DNL Marketo Measure] kan een aanraakpunt genereren voor het downloaden van de inhoud. Dit komt omdat de e-mail ze op de bevestigingspagina heeft geland met de parameter voor het bijhouden van e-mail.

## Hoe het werkt {#how-it-works}

Wanneer een bezoeker op uw site aankomt, [!DNL Marketo Measure] verwacht een bestemmingspagina met of een e-mailadres of [!DNL Salesforce] Id zodat we dat bezoek kunnen koppelen aan een &quot;formulierverzending&quot; en een aanraakpunt voor die activiteit kunnen genereren.

Als klant maakt u een e-mailsjabloon zoals u dat normaal zou doen. Zodra het tijd is om in de landende pagina voor de actie toe te voegen die u wilt volgen, moet u of het teken, of veranderlijke markering, of macro bepalen dat uw platform van de Automatisering van de Marketing goedkeurt om de waarde voor elk individu dynamisch te tonen.

Marketo Measure accepteert de volgende waarden: E-mailadres, Salesforce Lead-id of Salesforce-contactpersoon.

## Voorbeelden van tags {#tag-examples}

<table> 
 <colgroup> 
  <col> 
  <col> 
  <col> 
  <col> 
 </colgroup> 
 <tbody> 
  <tr> 
   <th><p>Marketingautomatisering</p></th> 
   <th><p>Token/Tag/macro </p></th> 
   <th><p>Voorbeeld</p></th> 
   <th><p>Ondersteunend materiaal</p></th> 
  </tr> 
  <tr> 
   <td><p>Marketo</p></td> 
   <td><p>{{lead.Email Address}} </p></td> 
   <td><p>https://engage.marketo.com/rs/460-TDH-945/images/BZ-B2B-Marketing-Attribution-101-ebook.pdf?mailId={{lead.EmailAddress}}</p></td> 
   <td><p>https://experienceleague.adobe.com/docs/marketo/using/product-docs/demand-generation/landing-pages/personalizing-landing-pages/tokens-overview.html?lang=nl-NL</p></td> 
  </tr> 
  <tr> 
   <td><p>Pardot</p></td> 
   <td><p>%%email% </p><p>of</p><p>%%user_crm_id%%</p></td> 
   <td><p>https://engage.marketo.com/rs/460-TDH-945/images/BZ-B2B-Marketing-Attribution-101-ebook.pdf?mailId=%%email%%</p></td> 
   <td><p>https://help.salesforce.com/s/articleView?language=en_US&id=pardot_variable_tags_reference.htm&type=5</p></td> 
  </tr> 
  <tr> 
   <td><p>Hubspot</p></td> 
   <td><p>(ingevoegd via de Editor)</p></td> 
   <td><p>nvt</p></td> 
   <td><p>https://knowledge.hubspot.com/website-pages/personalize-your-content</p></td> 
  </tr> 
  <tr> 
   <td><p>Act-On</p></td> 
   <td><p>(ingevoegd via Message Composer)</p></td> 
   <td><p>nvt</p></td> 
   <td><p>https://connect.act-on.com/hc/en-us/articles/360033436074-How-to-Personalize-Email-Content-with-CRM-Data</p></td> 
  </tr> 
 </tbody> 
</table>

En ten slotte, binnen [!DNL Marketo Measure]moet u de parameter tracking opgeven, zodat [!DNL Marketo Measure] U kunt de waarde van de e-mail of ID vinden. Het gebrek is &quot;mailId&quot;zoals aangetoond in de bovenstaande voorbeelden en het hieronder opgenomen scherm. Geef de waarde op in uw instellingen in [!DNL Marketo Measure]en klik vervolgens op **[!UICONTROL Save]**.

![](assets/one.png)
