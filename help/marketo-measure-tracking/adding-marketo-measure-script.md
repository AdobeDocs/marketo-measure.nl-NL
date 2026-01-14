---
description: Het toevoegen van  [!DNL Marketo Measure]  begeleiding van het Manuscript voor de gebruikers van Marketo Measure
title: Toevoegend  [!DNL Marketo Measure]  Manuscript
exl-id: f8773037-04d7-4308-ba04-440e9b990d92
feature: Tracking
hidefromtoc: true
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '1287'
ht-degree: 0%

---

# [!DNL Marketo Measure] Script toevoegen {#adding-marketo-measure-script}

[!DNL Marketo Measure] JavaScript die u wilt laten volgen door [!DNL Marketo Measure] , moet zo snel mogelijk aan alle wegeigenschappen worden toegevoegd. Zodra de JavaScript is geïmplementeerd, begint [!DNL Marketo Measure] met het verzamelen van uw digitale gegevens. In dit artikel worden de methoden voor het implementeren van [!DNL Marketo Measure] JavaScript en aanvullende overwegingen beschreven.

>[!NOTE]
>
>Zorg ervoor u [ alle aangewezen domeinen in  [!DNL Adobe Admin Console]](/help/marketo-measure-and-adobe/domain-management.md){target="_blank"} naast het opstellen van [!DNL Marketo Measure] JavaScript hebt geclaimd.

Wanneer u aan de slag gaat met [!DNL Marketo Measure] , kunt u de [!DNL Marketo Measure] JavaScript op twee manieren aan uw website toevoegen:

* Hard coderen
* Tag Management Systems

## Hard coderen {#hard-coding}

We raden u ten zeerste aan [!DNL Marketo Measure] JavaScript hardcoding toe te passen op uw wegeigenschappen. Als u het script wilt coderen, moet u het script vóór het sluiten van `</head>` op elke pagina van uw site plaatsen.

`<script type="text/javascript" src="https://cdn.bizible.com/scripts/bizible.js" async=""></script>`

Door de JavaScript te coderen in de `<head>` van uw pagina&#39;s, zorgt u ervoor dat het [!DNL Marketo Measure] -script eerst wordt geladen en dat de verwijzingsgegevens niet worden overgeslagen. De [!DNL Marketo Measure] JavaScript wordt asynchroon geladen. Als de hardcoding aanwezig is, moet de JavaScript handmatig worden toegevoegd aan Marketing Automation.

>[!TIP]
>
>Leer hoe u ervoor kunt zorgen dat uw script compatibel is met GDPR.

## Tag Management Systems {#tag-management-systems}

Als het toevoegen van [!DNL Marketo Measure] JavaScript via hardcoding niet mogelijk is, kunt u het script van [!DNL Marketo Measure] ook toevoegen met behulp van een Tag Management-systeem zoals [!DNL Google Tag Manager] (GTM) of Tealium.

Als u [!DNL Marketo Measure] JS implementeert met tagbeheersystemen, kan dit leiden tot een mogelijk gegevensverlies van 5-10% als gevolg van vertraging bij het laden van scripts. Als het gereedschap voor tagbeheer niet snel genoeg wordt geladen, kan [!DNL Marketo Measure] JS ook niet snel genoeg laden en kan de informatie over de eerste referentie verloren gaan.

Vaak wordt [!DNL Marketo Measure] JS geïmplementeerd via een tagbeheerprogramma totdat timing/resourcing beter is om over te schakelen naar hardcodering.

Als u [!DNL Marketo Measure] -script wilt toevoegen via een oplossing voor tagbeheer, moet u een tag maken en de JavaScript daarin toevoegen. Pas dit label toe op alle pagina&#39;s op uw website die u wilt bijhouden.

[!DNL Marketo Measure] raadt aan dat de tag in de paginaweergave wordt geactiveerd. Bovendien kunt u [!DNL Marketo Measure] het beste de hoogste prioriteit geven in de volgorde waarin de gegevens worden gemaakt en ervoor zorgen dat er geen synchrone scripts staan voor de tag [!DNL Marketo Measure] om de hoogste gegevenskwaliteit te garanderen.

Meer informatie kan [ hier ](/help/marketo-measure-tracking/adding-marketo-measure-script-via-google-tag-manager.md){target="_blank"} worden gevonden.

## Aanvullende overwegingen {#additional-considerations}

[!DNL Marketo Measure] JavaScript is op domein gebaseerd zodat het automatisch subdomeinen kan behandelen zolang JavaScript op de pagina&#39;s is en het worteldomein het domein is dat wordt gebruikt om de rekening van Marketo Measure tot stand te brengen.

Als u echter afzonderlijke of internationale domeinen gebruikt, moet u dit aan uw [!DNL Marketo Measure] Consultant laten weten. De domeinen moeten handmatig aan uw account worden toegevoegd aan het [!DNL Marketo Measure] -einde, zodat [!DNL Marketo Measure] weet dat de gegevens van de aanvullende domeinen aan uw account moeten worden gekoppeld. Stuur dus elk afzonderlijk/internationaal domein naar uw [!DNL Marketo Measure] Consultant.

Als u pagina&#39;s van derden gebruikt, voert u een gesprek over uw gebruikskwestie met uw [!DNL Marketo Measure] Consultant. Over het algemeen wilt u weten of u een aangepaste versie van [!DNL Marketo Measure] JavaScript kunt toevoegen om deze pagina&#39;s indien nodig bij te houden. Als dit niet mogelijk is, wordt het volgen via CRM Campaign-aanraakpunten besproken met uw [!DNL Marketo Measure] Consultant.

Hebt u formulieren die NIET door [!DNL Marketo Measure] moeten worden bijgehouden omdat ze niet noodzakelijkerwijs zinvol zijn voor toewijzing (bijvoorbeeld het afmelden van formulieren, het aanmelden van klanten, enzovoort)? Als zo, zult u de uitsluitingscode [ in dit artikel ](/help/marketo-measure-tracking/excluding-marketo-measure-from-specific-forms.md){target="_blank"} aan elke vorm willen toevoegen

Hebt u onveilige pagina&#39;s? U moet ze zo beveiligen dat ze door een beveiligde/niet-beveiligde pagina worden verbroken tijdens de volgende sessie.

Zorg ervoor dat u een gesprek hebt met uw webteam, zodat ze weten dat [!DNL Marketo Measure] JavaScript altijd op de juiste wegeigenschappen moet staan. Als er nieuwe pagina&#39;s/formulieren/sites worden geïntroduceerd, moet u ervoor zorgen dat [!DNL Marketo Measure] JavaScript deel uitmaakt van het protocol.

Als een [!DNL Web Application Firewall (WAF)] -waarschuwing wordt geactiveerd tijdens het instellen van de JavaScript, kunnen gebruikers de WAF-regel uitschakelen of de cookies lijsten van gewenste personen, zoals in het volgende voorbeeld:

![](assets/adding-script-1.png)

## Forms om extra aandacht te besteden aan {#forms-to-pay-extra-attention-to}

**Multiform voorlegging**

* Probleem: als u meerdere gekoppelde formulieren hebt als onderdeel van één formulier voor verzending, is het mogelijk dat het eerste formulier een aanraakpunt genereert, zelfs als het volledige formulier niet wordt verzonden.
* Oplossing: u moet een van de formulieren forceren om de gebruiker aan [!DNL Marketo Measure] te melden op basis van gegevens in de cache en om praktijken voor het verlaten van de server te bespreken. Over het algemeen, [ kan de code van de rapportgebruiker ](/help/marketo-measure-tracking/ajax-form-handling.md){target="_blank"} voor dit oplossen.

**login van de Rekening (niet verwezenlijking)**

* Probleem: [!DNL Marketo Measure] raadt u aan geen aanraakpunten te maken voor volgende aanmeldingen van accounts, aangezien deze het toewijzingsartikel doorgaans verwateren.
* Oplossing: voeg Code uitsluiten toe aan het aanmeldingsformulier voor account/klant/partner.

>[!NOTE]
>
>We raden u aan een aanraakpunt te maken voor het maken van een account of proefversie.

**Download van activa**

* Probleem: als uw elementen zijn gecodeerd, houdt [!DNL Marketo Measure] downloads bij als formuliervullingen. Als uw activa niet worden behandeld, zijn er beperkingen aan wat wij kunnen melden zonder aanpassing.
* Oplossing: haal het element op als u het wilt laten volgen door [!DNL Marketo Measure] JavaScript. Als dit geen optie is en u nog van een aanraakpunt voor het zou houden, denk in plaats daarvan het synchroniseren van een Campagne van CRM.

**iFrames**

* Probleem: iFrames functioneren in feite als pagina&#39;s binnen pagina&#39;s.
* Oplossing: de JS van [!DNL Marketo Measure] moet direct binnen de iFrame- kopbal voor ons worden opgesteld om aan de vorm correct vast te maken.

**Lichtbakken**

* Lichtbakken zijn doorgaans pop-ups die iFrames bevatten
* Oplossing: de [!DNL Marketo Measure] JS moet worden geïmplementeerd in de header van dat gehoste iFrame.

**Veelvoudige vormen op een pagina**

* Probleem: als er meerdere formulieren op een pagina worden gehost, kunt u mogelijk niet zien welk specifiek formulier is ingevuld met het veld [!DNL Marketo Measure] Formulier-URL.
* Oplossing: als u moet weten welk formulier is ingevuld, kunt u zoeken naar dynamische URL-hashing instellen met uw webteam.

**Forms die in `<div>` formaat** wordt georganiseerd

* Probleem: [!DNL Marketo Measure] JS heeft moeite formulieren te herkennen in `<div>` -indeling, zodat aangepaste code nodig kan zijn.
* Oplossing: Deze [ malplaatjes van de rapportgebruiker ](/help/marketo-measure-tracking/ajax-form-handling.md){target="_blank"} kunnen door uw Web Dev team worden gebruikt om de vereiste code toe te voegen.

**Praatje**

* Probleem: als u een chatprovider gebruikt, is mogelijk speciale afhandeling vereist.
* Oplossing: [!DNL Marketo Measure] kan worden geïntegreerd met Drift, Olark, Livechat, LivePerson en SnapEngage. Alle andere platforms moeten worden gevolgd door CRM-campagnelidmaatschap.

**Tweede Domein**

* Probleem: [!DNL Marketo Measure] JavaScript is domeinspecifiek, dus er moeten extra stappen worden uitgevoerd voor afzonderlijke of internationale domeinen. [!DNL Marketo Measure] JS kan subdomeinen op hetzelfde hoofddomein afhandelen.
* Oplossing: als u meerdere hoofddomeinen hebt, moet u [!DNL Marketo Measure] controleren of u JS aan de domeinen wilt toevoegen EN moet u uw [!DNL Marketo Measure] Consultant laten weten welke domeinen handmatig aan uw [!DNL Marketo Measure] -account moeten worden gekoppeld.

## Testen [!DNL Marketo Measure] JavaScript {#testing-marketo-measure-javascript}

Uw [!DNL Marketo Measure] Consultant helpt u de website te testen om te controleren of [!DNL Marketo Measure] JavaScript op alle pagina&#39;s aanwezig is. Een deel van deze test is het indienen van een paar formuliervullingen met duidelijk aangegeven testdetails om ervoor te zorgen dat het volgen correct terugkeert.

Uw [!DNL Marketo Measure] Consultant is echter waarschijnlijk niet zo vertrouwd met uw website als uw webteam. Daarom is het erg belangrijk dat uw webteam of ander geschikt team de website grondig controleert, vooral als er complexe formulieren in gebruik zijn zoals de hierboven vermelde. Uw team zal er uiteindelijk voor verantwoordelijk zijn dat alle benodigde wegeigenschappen correct worden bijgehouden, maar als u weet welke complexe formulieren of situaties er zijn, kunt u uw [!DNL Marketo Measure] -consultant om hulp vragen bij het testen.

Voer de volgende stappen uit om een formulier zelf te testen:

1. Gebruik altijd een incognitobrowser of wis de cache tussen elke test voor het verzenden van formulieren EN gebruik telkens een ander e-mailadres.

   a. De beste manier is om een nep-e-mail te gebruiken die iets bevat dat aangeeft dat het een test en het tijdstip van de dag is. Bijvoorbeeld: testing830am@test.com.

1. Registreer de URL van de pagina die u het formulier verzendt en het e-mailadres dat u gebruikt.

1. Zoek de record die is gemaakt in uw CRM (lead of contact) voor het verzenden van het formulier en controleer of een aanraakpunt op de juiste wijze is gemaakt.

   a. U kunt een [!DNL Marketo Measure] voorraadrapport gebruiken, zoals Leads met aanraakpunten voor kopers, of de pagina-indeling Lead/Contactpersoon bekijken als u ervoor kiest de paginalay-outs bij te werken met [!DNL Marketo Measure] -gegevens.

   b. Dit kan enige tijd duren voordat de gegevens worden verwerkt.
