---
unique-page-id: 18874795
description: Toevoegen [!DNL Marketo Measure] Script - [!DNL Marketo Measure]
title: Toevoegen [!DNL Marketo Measure] Script
exl-id: f8773037-04d7-4308-ba04-440e9b990d92
feature: Tracking
source-git-commit: 9e672d0c568ee0b889461bb8ba6fc6333edf31ce
workflow-type: tm+mt
source-wordcount: '1282'
ht-degree: 0%

---

# Toevoegen [!DNL Marketo Measure] Script {#adding-marketo-measure-script}

[!DNL Marketo Measure] JavaScript die u wilt bijhouden door [!DNL Marketo Measure] moeten zo snel mogelijk aan alle wegeigenschappen worden toegevoegd. Zodra JavaScript is geïmplementeerd, [!DNL Marketo Measure] begint uw digitale gegevens te verzamelen. Dit artikel schetst de methodes om op te stellen [!DNL Marketo Measure] JavaScript en aanvullende overwegingen.

>[!NOTE]
>
>Zorg ervoor dat je [alle relevante domeinen in de [!DNL Adobe Admin Console]](/help/marketo-measure-and-adobe/domain-management.md){target="_blank"} naast de implementatie van de [!DNL Marketo Measure] JavaScript.

Aan de slag met [!DNL Marketo Measure], er zijn twee manieren waarop u de [!DNL Marketo Measure] JavaScript naar uw website:

* Hard coderen
* Tag Management Systems

## Hard coderen {#hard-coding}

Als beste praktijken, adviseren wij sterk hardcoding [!DNL Marketo Measure] JavaScript naar uw wegeigenschappen. Als u het script hard wilt coderen, moet u het script plaatsen vóór het sluiten `</head>` op elke pagina van uw site.

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

De JavaScript-code in de `<head>` van uw pagina&#39;s ervoor zorgt dat [!DNL Marketo Measure] eerst wordt het script geladen en de informatie over de verwijzing wordt niet overgeslagen. De [!DNL Marketo Measure] JavaScript wordt asynchroon geladen. Als de hardcodering is ingeschakeld, moet de JavaScript-code handmatig worden toegevoegd aan Marketing Automation.

>[!TIP]
>
>Leer hoe u ervoor kunt zorgen dat het script [GDPR-conform](/help/security-and-compliance/compliance-related-resources/ensuring-consent-for-gdpr-in-marketo-measure-js.md){target="_blank"}.

## Tag Management Systems {#tag-management-systems}

Indien toevoegen [!DNL Marketo Measure] JavaScript via hardcodering is niet mogelijk. U kunt ook het volgende toevoegen: [!DNL Marketo Measure] script dat gebruikmaakt van een Tag Management-systeem, zoals [!DNL Google Tag Manager] (GTM) of Tealium.

Tagbeheersystemen gebruiken om te implementeren [!DNL Marketo Measure] JS kan in een potentieel gegevensverlies van 5-10% als gevolg van de tijdvertraging van de manuscriptlading resulteren. In wezen geldt dat als het gereedschap voor tagbeheer niet snel genoeg wordt geladen, [!DNL Marketo Measure] JS kan ook niet snel genoeg laden en kan de informatie van de eerste referentie verliezen.

Een gemeenschappelijke praktijk is op te stellen [!DNL Marketo Measure] JS via een hulpmiddel voor tagbeheer totdat timing/resource beter is om over te schakelen naar hardcodering.

Toevoegen [!DNL Marketo Measure] scriptbewerkingen uit te voeren met behulp van een oplossing voor tagbeheer, moet u een tag maken en hierin onze JavaScript-code toevoegen. Pas dit label toe op alle pagina&#39;s op uw website die u wilt bijhouden.

[!DNL Marketo Measure] Het wordt aangeraden dat de tag wordt geactiveerd in de paginaweergave. Ook, is het best om te geven [!DNL Marketo Measure] de hoogste prioriteit in de vuurorde en zorg ervoor dat er geen synchrone manuscripten vóór [!DNL Marketo Measure] -tags toepassen om de hoogste gegevenskwaliteit te garanderen.

Meer informatie is mogelijk [hier gevonden](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-via-google-tag-manager.md){target="_blank"}.

## Aanvullende overwegingen {#additional-considerations}

[!DNL Marketo Measure] JavaScript is op domein-gebaseerd zodat kan het automatisch om het even welke subdomeinen behandelen zolang JavaScript op de pagina&#39;s is en het worteldomein het zelfde als het domein is dat wordt gebruikt om de rekening van Marketo Measure tot stand te brengen.

Als u echter afzonderlijke of internationale domeinen gebruikt, moet u ervoor zorgen dat uw [!DNL Marketo Measure] Consultant kent het. De domeinen moeten manueel aan uw rekening op worden toegevoegd [!DNL Marketo Measure] einde zodat [!DNL Marketo Measure] weet hoe u de gegevens van de aanvullende domeinen aan uw account kunt koppelen. U kunt dus elk afzonderlijk/internationaal domein naar uw [!DNL Marketo Measure] Consultant.

Als u om het even welke derdepagina&#39;s gebruikt, heb een gesprek over uw gebruiksgeval met uw [!DNL Marketo Measure] Consultant. In het algemeen wilt u weten of u een aangepaste versie van [!DNL Marketo Measure] JavaScript om deze pagina&#39;s zo nodig bij te houden. Als dit niet mogelijk is, wordt het volgen via CRM Campaign touchpoints onderzocht met uw [!DNL Marketo Measure] Consultant.

Hebt u formulieren die NIET mogen worden bijgehouden door [!DNL Marketo Measure] aangezien zij niet noodzakelijk voor attributie (bijvoorbeeld, unsubscribe vormen, klantenlogins, etc.) zinvol maken? Zo ja, dan wilt u de uitsluitingscode toevoegen [in dit artikel](/help/marketo-measure-tracking/setting-up-tracking/excluding-marketo-measure-from-specific-forms.md){target="_blank"} naar elk formulier

Hebt u onveilige pagina&#39;s? U moet ze zo beveiligen dat ze door een beveiligde/niet-beveiligde pagina worden verbroken tijdens de volgende sessie.

Ben zeker om een gesprek met uw Webteam te hebben zodat weten zij [!DNL Marketo Measure] JavaScript moet zich altijd op de juiste wegeigenschappen bevinden. Als er nieuwe pagina&#39;s/formulieren/sites worden geïntroduceerd, zorg dan voor implementatie [!DNL Marketo Measure] JavaScript maakt deel uit van het protocol.

Indien een [!DNL Web Application Firewall (WAF)] de waarschuwing wordt geactiveerd tijdens het instellen van JavaScript, kunnen gebruikers die WAF-regel uitschakelen of de cookies lijsten van gewenste personen, zoals in het volgende voorbeeld:

![](assets/adding-marketo-measure-script-1.png)

## Forms om extra aandacht te besteden aan {#forms-to-pay-extra-attention-to}

**Meerdere formulieren verzenden**

* Probleem: als u meerdere gekoppelde formulieren hebt als onderdeel van één formulier voor verzending, is het mogelijk dat het eerste formulier een aanraakpunt genereert, zelfs als het volledige formulier niet wordt verzonden.
* Oplossing: u moet een van de formulieren forceren om de gebruiker aan te melden [!DNL Marketo Measure] gebaseerd op caching gegevens en bespreken verlaten praktijken. In het algemeen [rapportgebruikerscode](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-to-different-form-providers/ajax-form-handling.md){target="_blank"} kan hiervoor een oplossing bieden.

**Accountaanmelding (niet gemaakt)**

* Probleem: [!DNL Marketo Measure] Het verdient aanbeveling geen aanraakpunten te maken voor logins van volgende accounts, aangezien deze het attributieartikel verwateren.
* Oplossing: voeg Code uitsluiten toe aan het aanmeldingsformulier voor account/klant/partner.

>[!NOTE]
>
>We raden u aan een aanraakpunt te maken voor het maken van een account of proefversie.

**Downloaden van middelen**

* Uitgave: als uw activa worden afgesloten, [!DNL Marketo Measure] Hiermee worden downloads als formuliervullingen bijgehouden. Als uw activa niet worden behandeld, zijn er beperkingen aan wat wij kunnen melden zonder aanpassing.
* Oplossing: Gate het middel als u het wilt worden gevolgd door [!DNL Marketo Measure] JavaScript. Als dit geen optie is en u nog van een aanraakpunt voor het zou houden, denk in plaats daarvan het synchroniseren van een Campagne van CRM.

**iFrames**

* Probleem: iFrames functioneren in feite als pagina&#39;s binnen pagina&#39;s.
* Oplossing: De [!DNL Marketo Measure] JS moet rechtstreeks in de iFrame-header worden geïmplementeerd, zodat we het formulier correct kunnen koppelen.

**Lichtbakken**

* Lichtbakken zijn doorgaans pop-ups die iFrames bevatten
* Oplossing: de [!DNL Marketo Measure] JS moet worden opgesteld binnen de kopbal van dat ontvangen iFrame.

**Meerdere formulieren op een pagina**

* Probleem: als er meerdere formulieren op een pagina worden gehost, kunt u mogelijk niet zien welk specifiek formulier is ingevuld met de [!DNL Marketo Measure] Formulier-URL.
* Oplossing: als u moet weten welk formulier is ingevuld, kunt u zoeken naar dynamische URL-hashing instellen met uw webteam.

**Forms georganiseerd in `<div>` format**

* Probleem: [!DNL Marketo Measure] JS heeft moeite met het herkennen van formulieren die zijn georganiseerd in `<div>` opmaak zodat aangepaste code nodig kan zijn.
* Oplossing: deze [rapportgebruikerssjablonen](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-to-different-form-providers/ajax-form-handling.md){target="_blank"} kan door uw team van Webontwikkeling worden gebruikt om de vereiste code toe te voegen.

**Chat**

* Probleem: als u een chatprovider gebruikt, is mogelijk speciale afhandeling vereist.
* Oplossing: [!DNL Marketo Measure] integreert met Drift, Olark, Livechat, LivePerson en SnapEngage. Alle andere platforms moeten worden gevolgd door CRM-campagnelidmaatschap.

**Tweede domein**

* Probleem: [!DNL Marketo Measure] JavaScript is domeinspecifiek, dus er moeten extra stappen worden uitgevoerd voor afzonderlijke of internationale domeinen. [!DNL Marketo Measure] JS kan subdomeinen op het zelfde worteldomein behandelen.
* Oplossing: als u veelvoudige worteldomeinen bezit, die u door zou willen worden gevolgd [!DNL Marketo Measure] zorg ervoor dat u JS toevoegt aan de domeinen EN uw [!DNL Marketo Measure] De consultant weet welke domeinen handmatig aan uw [!DNL Marketo Measure] account.

## Testen [!DNL Marketo Measure] JavaScript {#testing-marketo-measure-javascript}

Uw [!DNL Marketo Measure] Consultant helpt u bij het testen van de website om te controleren of [!DNL Marketo Measure] JavaScript is aanwezig op alle pagina&#39;s. Een deel van deze test is het indienen van een paar formuliervullingen met duidelijk aangegeven testdetails om ervoor te zorgen dat het volgen correct terugkeert.

Uw [!DNL Marketo Measure] Consultant is waarschijnlijk niet zo vertrouwd met uw website als uw webteam. Daarom is het erg belangrijk dat uw webteam of ander geschikt team de website grondig controleert, vooral als er complexe formulieren in gebruik zijn zoals de hierboven vermelde. Uw team zal er uiteindelijk voor verantwoordelijk zijn dat alle benodigde wegeigenschappen correct worden bijgehouden, maar als u weet welke complexe formulieren of situaties er zijn, kunt u [!DNL Marketo Measure] Consultant voor assistentie bij het testen.

Voer de volgende stappen uit om een formulier zelf te testen:

1. Gebruik altijd een incognitobrowser of wis de cache tussen elke test voor het verzenden van formulieren EN gebruik telkens een ander e-mailadres.

   a. De beste manier is om een nep-e-mail te gebruiken die iets bevat dat aangeeft dat het een test en het tijdstip van de dag is. Bijvoorbeeld: testing830am@test.com.

1. Registreer de URL van de pagina die u het formulier verzendt en het e-mailadres dat u gebruikt.

1. Zoek de record die is gemaakt in uw CRM (lead of contact) voor het verzenden van het formulier en controleer of een aanraakpunt op de juiste wijze is gemaakt.

   a. U kunt een [!DNL Marketo Measure] voorraadrapport zoals Leads met aanraakpunten voor kopers of bekijk de pagina-indeling Lead/Contact als u uw paginalay-outs wilt bijwerken met [!DNL Marketo Measure] details.

   b. Dit kan enige tijd duren voordat de gegevens worden verwerkt.
