---
unique-page-id: 18874795
description: Toevoegen [!DNL Marketo Measure] Script - [!DNL Marketo Measure] - Productdocumentatie
title: Toevoegen [!DNL Marketo Measure] Script
exl-id: f8773037-04d7-4308-ba04-440e9b990d92
source-git-commit: 82cc8269bfdb26b6acf039d0ce0e06564f5e2612
workflow-type: tm+mt
source-wordcount: '1319'
ht-degree: 0%

---

# Toevoegen [!DNL Marketo Measure] Script {#adding-marketo-measure-script}

[!DNL Marketo Measure] JavaScript die u wilt bijhouden door [!DNL Marketo Measure] moeten zo snel mogelijk aan alle wegeigenschappen worden toegevoegd. Zodra JavaScript is geïmplementeerd, [!DNL Marketo Measure] begint uw digitale gegevens te verzamelen. Dit artikel schetst de methodes om op te stellen [!DNL Marketo Measure] JavaScript en aanvullende overwegingen waarmee rekening moet worden gehouden.

>[!NOTE]
>
>Zorg ervoor dat je [alle relevante domeinen in de [!DNL Adobe Admin Console]](/help/marketo-measure-and-adobe/domain-management.md){target=&quot;_blank&quot;} naast de implementatie van de [!DNL Marketo Measure] JavaScript.

Aan de slag met [!DNL Marketo Measure], er zijn twee manieren waarop u de [!DNL Marketo Measure] JavaScript naar uw website:

* Hard coderen
* Tag Management Systems

## Hard coderen {#hard-coding}

Als beste praktijken, adviseren wij sterk hardcoding [!DNL Marketo Measure] JavaScript naar uw wegeigenschappen. Als u het script hard wilt coderen, moet u het script plaatsen vóór het sluiten `</head>` op elke pagina van uw site.

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

De JavaScript-code in de `<head>` van uw pagina&#39;s ervoor zorgt dat [!DNL Marketo Measure] script wordt eerst geladen en verwijzingsinformatie wordt niet overgeslagen. De [!DNL Marketo Measure] JavaScript wordt asynchroon geladen. Als de hardcodering is ingeschakeld, moet de JavaScript-code handmatig worden toegevoegd aan Marketing Automation.

>[!TIP]
>
>Leer hoe u ervoor kunt zorgen dat het script [GDPR-compatibel](/help/security-and-compliance/compliance-related-resources/ensuring-consent-for-gdpr-in-marketo-measure-js.md){target=&quot;_blank&quot;}.

## Tag Management Systems {#tag-management-systems}

Indien toevoegen [!DNL Marketo Measure] JavaScript via hardcodering is niet mogelijk. U kunt ook het volgende toevoegen: [!DNL Marketo Measure] een script gebruiken dat gebruikmaakt van een Tag Management-systeem, zoals [!DNL Google Tag Manager] (GTM) of Tealium.

Houd er rekening mee dat u tagbeheersystemen gebruikt om te implementeren [!DNL Marketo Measure] JS kan in een potentieel gegevensverlies van 5-10% als gevolg van de tijdvertraging van de manuscriptlading resulteren. In wezen geldt dat als het gereedschap voor tagbeheer niet snel genoeg wordt geladen, [!DNL Marketo Measure] JS kan ook niet snel genoeg laden en kan de informatie van de eerste referentie verliezen.

Een gemeenschappelijke praktijk is op te stellen [!DNL Marketo Measure] JS via een hulpmiddel voor tagbeheer totdat timing/resource beter is om over te schakelen naar hardcodering.

Toevoegen [!DNL Marketo Measure] via een oplossing voor tagbeheer een nieuwe tag maken en hierin onze JavaScript toevoegen. Pas dit label toe op alle pagina&#39;s op uw website die u wilt bijhouden.

[!DNL Marketo Measure] Het wordt aanbevolen dat de tag wordt geactiveerd in elke paginaweergave. Bovendien is het beter om [!DNL Marketo Measure] de hoogste prioriteit in de vuurorde en zorg ervoor er geen synchrone manuscripten vóór [!DNL Marketo Measure] -tags toepassen om de hoogste gegevenskwaliteit te garanderen.

Meer informatie is mogelijk [hier gevonden](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-via-google-tag-manager.md){target=&quot;_blank&quot;}.

## Aanvullende overwegingen {#additional-considerations}

[!DNL Marketo Measure] JavaScript is op domein-gebaseerd zodat kan het automatisch om het even welke subdomeinen behandelen zolang JavaScript op de pagina&#39;s is en het worteldomein het zelfde als het domein is dat wordt gebruikt om de rekening van de Meetlat van Marketo tot stand te brengen.

Als u echter afzonderlijke of internationale domeinen gebruikt, moet u ervoor zorgen dat uw [!DNL Marketo Measure] Consultant kent het. Het domein of de domeinen moeten handmatig aan uw account worden toegevoegd op het tabblad [!DNL Marketo Measure] zodat [!DNL Marketo Measure] weet hoe u de gegevens van de aanvullende domeinen aan uw account kunt koppelen. Stuur dus afzonderlijke/internationale domeinen naar uw [!DNL Marketo Measure] Consultant.

Als u om het even welke derdepagina&#39;s gebruikt, heb een gesprek over uw gebruiksgeval met uw [!DNL Marketo Measure] Consultant. In het algemeen wilt u weten of u een aangepaste versie van [!DNL Marketo Measure] JavaScript om deze pagina&#39;s zo nodig bij te houden. Als dit niet mogelijk is, zal het volgen via CRM Campaign touchpoints met uw worden onderzocht [!DNL Marketo Measure] Consultant.

Hebt u formulieren die NIET mogen worden bijgehouden door [!DNL Marketo Measure] aangezien zij niet noodzakelijk voor attributie (b.v. unsubscribe vormen, klantenlogins, enz.) zinvol zijn? Als zo, zult u de uitsluitingscode willen toevoegen [in dit artikel](/help/marketo-measure-tracking/setting-up-tracking/excluding-marketo-measure-from-specific-forms.md){target=&quot;_blank&quot;} aan elk formulier

Hebt u onveilige pagina&#39;s? Als dat het geval is, zult u ze willen beveiligen, aangezien navigatie tussen een beveiligde/niet-beveiligde pagina de volgende sessie zal verbreken.

Ben zeker om een gesprek met uw Webteam te hebben zodat weten zij [!DNL Marketo Measure] JavaScript moet zich altijd op de juiste wegeigenschappen bevinden. Als er nieuwe pagina&#39;s/formulieren/sites worden geïntroduceerd, zorg dan voor implementatie [!DNL Marketo Measure] JavaScript maakt deel uit van het protocol.

Indien een [!DNL Web Application Firewall (WAF)] de waarschuwing wordt geactiveerd tijdens het instellen van JavaScript, kunnen gebruikers die WAF-regel uitschakelen of de cookies toestaan en weergeven, zoals in het volgende voorbeeld:

![](assets/adding-marketo-measure-script-1.png)

## Forms om extra aandacht te besteden aan {#forms-to-pay-extra-attention-to}

**Meerdere formulieren verzenden**

* Probleem: Als u meerdere gekoppelde formulieren hebt als onderdeel van één verzonden formulier, is het mogelijk dat het eerste formulier een aanraakpunt genereert, zelfs als het volledige formulier niet wordt verzonden.
* Oplossing: U moet een van de formulieren forceren om de gebruiker aan te melden [!DNL Marketo Measure] gebaseerd op caching gegevens en bespreken verlaten praktijken. In het algemeen [rapportgebruikerscode](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-to-different-form-providers/ajax-form-handling.md){target=&quot;_blank&quot;} kan dit oplossen.

**Accountaanmelding (niet gemaakt)**

* Probleem: [!DNL Marketo Measure] Het verdient aanbeveling geen aanraakpunten te maken voor logins van volgende accounts, aangezien deze het attributieartikel verwateren.
* Oplossing: Voeg Code uitsluiten toe aan het aanmeldingsformulier voor account/klant/partner.

>[!NOTE]
>
>We raden u aan een aanraakpunt te maken voor het maken van een account of proefversie.

**Downloaden van middelen**

* Probleem: Als uw elementen zijn gecodeerd, [!DNL Marketo Measure] Hiermee worden downloads als formuliervullingen bijgehouden. Als uw activa niet worden behandeld, zijn er beperkingen aan wat wij kunnen melden zonder aanpassing.
* Oplossing: Het element ophalen als u het wilt laten volgen door [!DNL Marketo Measure] JavaScript. Als dit geen optie is en u nog van een aanraakpunt voor het zou houden, denk in plaats daarvan het synchroniseren van een Campagne van CRM.

**iFrames**

* Probleem: iFrames functioneren in feite als pagina&#39;s binnen pagina&#39;s.
* Oplossing: De [!DNL Marketo Measure] JS moet direct binnen de iFrame kopbal worden opgesteld voor ons om aan de vorm correct vast te maken.

**Lichtbakken**

* Lichtbakken zijn doorgaans pop-ups die iFrames bevatten
* Oplossing: de [!DNL Marketo Measure] JS moet worden opgesteld binnen de kopbal van dat ontvangen iFrame.

**Meerdere formulieren op een pagina**

* Probleem: Als er meerdere formulieren op een pagina worden gehost, kunt u mogelijk niet zien welk specifiek formulier is ingevuld met de [!DNL Marketo Measure] Formulier-URL.
* Oplossing: Als u wilt weten welk formulier is ingevuld, kunt u het beste dynamische URL-hashing instellen met uw webteam.

**Forms georganiseerd in `<div>` format**

* Probleem: [!DNL Marketo Measure] JS heeft moeite met het herkennen van formulieren die zijn georganiseerd in `<div>` opmaak zodat aangepaste code nodig kan zijn.
* Oplossing: Deze [rapportgebruikerssjablonen](/help/marketo-measure-tracking/setting-up-tracking/adding-marketo-measure-script-to-different-form-providers/ajax-form-handling.md){target=&quot;_blank&quot;} kan door uw webontwikkelingsteam worden gebruikt om de benodigde code toe te voegen.

**Chat**

* Probleem: Als u een chatprovider gebruikt, is speciale afhandeling mogelijk vereist.
* Oplossing: [!DNL Marketo Measure] integreert met Drift, Olark, Livechat, LivePerson en SnapEngage. Alle andere platforms moeten worden gevolgd door CRM-campagnelidmaatschap.

**Tweede domein**

* Probleem: [!DNL Marketo Measure] JavaScript is domeinspecifiek, dus voor afzonderlijke of internationale domeinen moeten extra stappen worden gezet. Let op: [!DNL Marketo Measure] JS kan subdomeinen op het zelfde worteldomein behandelen.
* Oplossing: Als u meerdere hoofddomeinen hebt, wilt u dat deze worden bijgehouden [!DNL Marketo Measure] moet JS toevoegen aan de domeinen EN uw [!DNL Marketo Measure] De consultant weet welke domeinen handmatig aan uw [!DNL Marketo Measure] account.

## Testen [!DNL Marketo Measure] JavaScript {#testing-marketo-measure-javascript}

Uw [!DNL Marketo Measure] Consultant helpt u bij het testen van de website om te controleren of [!DNL Marketo Measure] JavaScript is aanwezig op alle pagina&#39;s. Een deel van deze test zal een paar vormvullingen met duidelijk aangegeven testdetails voorleggen om ervoor te zorgen dat het volgen behoorlijk terugkeert.

Uw [!DNL Marketo Measure] Consultant is waarschijnlijk niet zo vertrouwd met uw website als uw webteam. Daarom is het erg belangrijk dat uw webteam of ander geschikt team de website grondig controleert, vooral als er complexe formulieren in gebruik zijn zoals de hierboven vermelde. Uw team zal er uiteindelijk voor verantwoordelijk zijn dat alle benodigde wegeigenschappen correct worden bijgehouden, maar als u weet welke complexe formulieren of situaties er zijn, kunt u [!DNL Marketo Measure] Consultant voor assistentie bij het testen.

Voer de volgende stappen uit om een formulier zelf te testen:

1. Gebruik altijd een incognitobrowser of wis de cache tussen elke test voor het verzenden van formulieren EN gebruik telkens een ander e-mailadres.

   a. Een beste manier is om een nep-e-mail te gebruiken die iets bevat dat aangeeft dat het een test en het tijdstip van de dag is. Bijvoorbeeld: testing830am@test.com.

1. Neem de URL op van de pagina die u het formulier en het gebruikte e-mailbericht verzendt.

1. Zoek de record die is gemaakt in uw CRM (lead of contact) voor het verzenden van het formulier en controleer of een aanraakpunt op de juiste wijze is gemaakt.

   a. U kunt een [!DNL Marketo Measure] voorraadrapport zoals Leads met aanraakpunten voor kopers of bekijk de pagina-indeling Lead/Contact als u uw paginalay-outs wilt bijwerken met [!DNL Marketo Measure] details.

   b. Dit kan enige tijd duren voordat de gegevens zijn verwerkt.
