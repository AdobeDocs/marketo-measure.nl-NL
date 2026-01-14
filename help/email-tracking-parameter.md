---
description: Richtlijnen voor het bijhouden van parameters voor Marketo Measure-gebruikers
title: Parameter voor bijhouden van e-mail
exl-id: e2cfd59e-ce4a-4cbb-b64a-828d1db7410f
feature: Tracking
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 0%

---

# Parameter voor bijhouden van e-mail {#email-tracking-parameter}

Met de parameter voor het bijhouden van e-mail van [!DNL Marketo Measure] kunnen marketers klikken op e-mail behandelen als verzonden formulieren, zodat er aanraakpunten voor deze handelingen worden gegenereerd. Zonder een parameter voor het bijhouden van e-mailberichten te gebruiken, worden doorklikbewerkingen van een e-mail alleen behandeld als &quot;webbezoeken&quot; totdat de gebruiker daadwerkelijk verbinding maakt met de site via een formulierverzending of een webchat.

## Gebruiksscenario’s  {#use-cases}

**Webinar Registratie**: Het team van de Marketing verzendt een e-mailuitnodiging met één enkele knoop om voor een webinar te registreren. Omdat het e-mailbericht al over de gegevens van de persoon beschikt, registreert deze persoon met één klik automatisch. De landingspagina bevat de parameter voor het bijhouden van e-mailberichten, zodat [!DNL Marketo Measure] het e-mailadres kan vastleggen en de doorklikken kan behandelen als een formuliervulling, die een aanraakpunt genereert.

**Download van de Inhoud**: Het team van de Marketing van de Inhoud wil een recent eBook bevorderen dat zij met een directe downloadverbinding van e-mail hebben gepubliceerd. Wanneer de e-mailsjabloon is gemaakt, bevat de pagina voor downloadbevestiging de parameter voor het bijhouden van e-mailberichten, zodat [!DNL Marketo Measure] het e-mailadres kan vastleggen wanneer ze doorklikken. Zonder dat u een formulier op de site hoeft in te vullen, kan [!DNL Marketo Measure] een aanraakpunt genereren voor het downloaden van de inhoud. Dit komt omdat de e-mail ze op de bevestigingspagina heeft geland met de parameter voor het bijhouden van e-mail.

## Hoe het werkt {#how-it-works}

Wanneer een bezoeker op uw site arriveert, verwacht [!DNL Marketo Measure] een bestemmingspagina te vinden met een e-mailadres of [!DNL Salesforce] Id, zodat we dat bezoek kunnen koppelen aan een &quot;formulierverzending&quot; en een aanraakpunt voor die activiteit kunnen genereren.

Als klant maakt u een e-mailsjabloon zoals u dat normaal zou doen. Zodra het tijd is om in de landende pagina voor de actie toe te voegen die u wilt volgen, moet u of het teken, of veranderlijke markering, of macro bepalen dat uw platform van de Automatisering van de Marketing goedkeurt om de waarde voor elk individu dynamisch te tonen.

Marketo Measure accepteert de volgende waarden: E-mailadres, Salesforce Lead-id of Salesforce-contactpersoon.

## Voorbeelden van tags {#tag-examples}

| Marketingautomatisering | Token/Tag/macro | Voorbeeld | Ondersteunend materiaal |
| --- | --- | --- | --- |
| Marketo | {{lead.Email Address}} | <https://engage.marketo.com/rs/460-TDH-945/images/BZ-B2B-Marketing-Attribution-101-ebook.pdf?mailId={{lead.EmailAddress}}> | [&#x200B; Tokens overzicht &#x200B;](https://experienceleague.adobe.com/docs/marketo/using/product-docs/demand-generation/landing-pages/personalizing-landing-pages/tokens-overview.html?lang=nl-NL) |
| Pardot | %%email% of %%user_crm_id% | <https://engage.marketo.com/rs/460-TDH-945/images/BZ-B2B-Marketing-Attribution-101-ebook.pdf?mailId=%%email%%> | [&#x200B; Pardot veranderlijke de markeringsverwijzing &#x200B;](https://help.salesforce.com/s/articleView?language=en_US&id=pardot_variable_tags_reference.htm&type=5) |
| Hubspot | (ingevoegd via de Editor) | nvt | [&#x200B; HubSpot personaliseert inhoud &#x200B;](https://knowledge.hubspot.com/website-pages/personalize-your-content) |
| Act-On | (ingevoegd via Message Composer) | nvt | [&#x200B; handeling-op personaliseer e-mailinhoud &#x200B;](https://connect.act-on.com/hc/en-us/articles/360033436074-How-to-Personalize-Email-Content-with-CRM-Data) |

Tot slot moet u binnen [!DNL Marketo Measure] de parameter tracking opgeven, zodat [!DNL Marketo Measure] de waarde van de e-mail of id kan vinden. Het gebrek is &quot;mailId&quot;zoals aangetoond in de bovenstaande voorbeelden en het hieronder opgenomen scherm. Voer de waarde in uw instellingen in [!DNL Marketo Measure] in en klik op **[!UICONTROL Save]** .

![&#x200B; en tenslotte, binnen Marketo Measure, moet u de volgende parameter specificeren &#x200B;](assets/marketo-engage-activities-01.png)
