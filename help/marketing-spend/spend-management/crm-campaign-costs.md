---
unique-page-id: 18874688
description: Kosten van CRM-campagne - [!DNL Marketo Measure]
title: Kosten CRM-campagne
exl-id: d967cabe-b9f1-4ea1-a81b-e4484c703ecf
feature: Spend Management
source-git-commit: 1a274c83814f4d729053bb36548ee544b973dff5
workflow-type: tm+mt
source-wordcount: '1187'
ht-degree: 0%

---

# Kosten CRM-campagne {#crm-campaign-costs}

Meeste [!DNL Marketo Measure] klanten gebruiken CRM-campagnes om offline marketingactiviteiten te volgen. Marktdeelnemers die deze campagnes gebruiken, controleren ook de kosten binnen de BCR. Met deze functie wordt het op de markt eenvoudiger om [!DNL Marketo Measure] deze kosten te lezen en toe te passen op de gerapporteerde marketinguitgaven binnen [!DNL Marketo Measure]. Tot op heden moesten klanten de kosten voor elke campagne per maand manueel invoeren, maar met de noodzakelijke informatie verstrekt aan[!DNL Marketo Measure]kunnen gebruikers dit proces automatiseren, zodat marketers meer tijd kunnen besteden aan het analyseren van hun uitgaven en investeringsrendement.

## Beschikbaarheid {#availability}

Deze functie is beschikbaar voor alle [!DNL Salesforce] en Dynamics-klanten.

## Hoe het werkt {#how-it-works}

[!DNL Marketo Measure] zoekt eerst naar campagnes die &quot;toegelaten&quot;voor aanraakpunten zijn, zodat is er of een passende regel van de Synchronisatie van de Campagne die werd gecreeerd, of de Enable aanraakpunten van de Koper is waarde &quot;omvat Alle Campagne Leden&quot;of &quot;omvat &quot;Ontvangen&quot;Campagneleden.&quot;omvat Daarnaast [!DNL Marketo Measure] moeten de juiste waarden importeren en weten hoe de kosten moeten worden verdeeld. Daarom moeten de volgende velden een waarde bevatten:

**[!DNL Salesforce]**: `ActualCost`, `StartDate`, `EndDate`

**[!DNL Microsoft Dynamics]**: `totalactualcost`, `actualstart`, `actualend`

Als in een van de drie velden een waarde ontbreekt, [!DNL Marketo Measure] zal de kosten niet invoeren. U kunt dit verbeteren door het verslag van de Campagne in CRM bij te werken. Kosten worden niet geïmporteerd als deze is ingesteld op $0 omdat [!DNL Salesforce] behandelt leeg en $0 als het zelfde.

Voor [!DNL Marketo Measure] om de verdeling van een campagne over de maanden te bepalen , wordt de begin - en einddatum van de campagne gebruikt om het bedrag gelijkmatig per dag te verdelen .

![](assets/1.jpg)

In dit voorbeeld duurt een campagne 109 dagen, dus met een totale kosten van $18.000, komt de uitgave per dag aan ~$165.14.

Op basis van het aantal dagen per maand krijgen we deze maandelijkse totalen, zoals u in de tabel kunt zien:

Juli 2018: ($18.000/109) x 31 = $5.119.27

aug 2018: ($18,000/109) x 31 = $5,119,27

Sept 2018: ($18,000/109) x 30 = $4,954.13

okt 2018: ($ 18.000/109) x 17 = $ 2.807,34

## Historische gerapporteerde uitgave {#historical-reported-spend}

Als u uitgaven voor Campagnes bent ingegaan die in het verleden zijn gevolgd en aan een Campagne van CRM in kaart zijn gebracht, treedt het geen van de kosten met voeten u hebt ingegaan. Als de zelfde campagne in CRM wordt gewijzigd, negeert het het en geeft prioriteit aan de veranderingen u eerder in CSV uploadt had aangebracht.

Als u verkiest dat wij de kosten van de Campagne van CRM van nu op nemen, verander de waarde in CSV in $0 die de ingang schrapt. De volgende keer dat de taken worden uitgevoerd om de kosten te importeren, worden eerder bewerkte rapporten opgehaald.

## Campagnes zonder aanraakpunten {#campaigns-with-no-touchpoints}

Veel marketers kiezen ervoor marketinguitgaven te melden voor CRM-campagnes die geen aanraakpunten hebben gegenereerd of die geen campagneleden hebben voor het bijhouden van hun uitgaven. Zolang de drie velden zijn ingevuld (startdatum, einddatum, kosten) en de campagne is ingeschakeld voor aanraakpunten, [!DNL Marketo Measure] trekt die kosten binnen, zelfs als geen aanraakpunten verbonden aan het.

Dit zou voor het volgen van uitgaven aan overtollige Marketingkosten of hulpmiddelen kunnen nuttig zijn om dat omhoog in uw berekeningen van het ROI te rollen.

## Marketo Program Sync {#marketo-program-sync}

Als u de Programma&#39;s van Marketo in CRM als Campagnes brengt, zorg ervoor u de de kaartopstelling van de Kosten van het Begin, van het Eind, en van de Periode aan de vereiste gebieden van CRM hebt. Aangezien het veld Aanraakpunten koper inschakelen niet in kaart is gebracht, moet u deze campagnes toch inschakelen zodat de kosten kunnen worden opgevangen.

## Bewerking van de kosten {#editing-the-costs}

Als een campagne eenmaal is geïmporteerd vanuit de CRM, wordt deze op dezelfde manier behandeld als een API-advertentieprovider en wordt deze niet weergegeven in de CSV om wijzigingen in de kosten aan te brengen.

Elke wijziging van de kosten of de verdeling moet plaatsvinden in de BCR, zodat we op één enkel waarheidspunt kunnen wijzen.

## Veelgestelde vragen {#faq}

**Ik heb een wijziging aangebracht in mijn campagne - wanneer zou ik de veranderingen in de lijst van de Uitgaven van de Marketing of in mijn rapportering moeten verwachten?**

3-4 uur

**Ik heb de begindatum, einddatum en kosten ingevuld, maar waarom komen mijn kosten nog steeds niet voor [!DNL Marketo Measure]?**

Controleer of u de waarde Enable Buyer Touchpoint hebt ingesteld op &quot;Include All Campaign Member&quot; of op zijn minst op &quot;Include Reponded Campaign members&quot; of dat u een aangepaste regel Campagne Sync met deze campagne hebt gemaakt. Als u dit hebt bevestigd en de Campagne nog steeds niet ziet, kunt u contact opnemen met [Marketo-ondersteuning](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} zodat kunnen wij controleren dat uw campagnes behoorlijk invoeren.

**Ik moet de verdeling van mijn campagne wijzigen zodat ik deze in bepaalde maanden zwaarder kan wegen. Hoe doe ik dat?**

De verdeling van de kosten is uitsluitend gebaseerd op een gelijkmatige verdeling van de begindatum tot de einddatum. Helaas, kunnen wij het niet veranderen zodat uw kosten een verschillend gewicht naast de vastgestelde data hebben. U kunt dit controleren door de begin en einddatum van uw campagne aan te passen aangezien elke dag in de maandkwestie van belang is.

**Ik heb kosten voor mijn bovenliggende campagne - hoe krijgen de kindercampagnes de kosten van de bovenliggende campagne toegewezen?**

De manier waarop de kosten in beslag worden genomen, zal rechtstreeks afkomstig zijn van één campagne, ongeacht de relatie tussen moeder en kind. We raden aan om de kosten op de Kindercampagnes te zetten, samen met de data van de campagne, dan de Ouder te gebruiken als de paraplu-campagne waar de Ouderlijke Campagne niet geschikt zou worden gemaakt voor aanraakpunten.

**Hoe verander ik de kosten voor een maand in [!DNL Marketo Measure]?**

Omdat wij op CRM als enige bron van waarheid vertrouwen, moeten alle veranderingen in CRM worden aangebracht. Nadat de campagne is geïmporteerd door [!DNL Marketo Measure], kunnen de Campagnewaarden niet worden bewerkt in [!DNL Marketo Measure] of in het CSV-bestand.

**In welk scenario zou een Campagne in de Lijst van de Uitgaven van de Marketing verschijnen, dan niet meer verschijnen?**

We blijven vereisen dat alle drie de sleutelvelden een waarde hebben: Begindatum, Einddatum en Kosten. Ons standaardgedrag is dat we alleen campagnes importeren met een waarde groter dan $0. In het ideale geval zouden we campagnes importeren waar expliciet $0 is en geen campagnes die leeg blijven importeren, maar de Salesforce-API importeert beide als $0, ongeacht de waarde. Bovendien verwijderen we de campagne en de kosten uit de tabel marketinguitgaven als de waarde van het aanraakpunt voor kopers inschakelen verandert van &quot;Alles opnemen&quot; of &quot;Alles opnemen en reageren&quot; in &quot;Alles uitsluiten&quot;.

**Welke kosten zouden prioriteit nemen als een rij reeds van CRM werd gedownload en ik een andere rij in CSV met zelfde campagneId inging?**

Hoewel u het bestand mogelijk met succes kunt uploaden, [!DNL Marketo Measure] zal die rij niet gebruiken omdat wij reeds een campagne-ID met de zelfde waarde hebben die automatisch uit de integratie werd getrokken.

**Hoe zou u suggereren dat we het kosten van onze digitale campagnes die we hebben opgezet in de CRM?**

Omdat ons [!DNL Marketo Measure] JavaScript volgt de webactiviteiten van uw site al. We raden u aan campagnes die leden van de campagne volgen op webformulieren of andere activiteiten op de site niet te synchroniseren, omdat hierdoor de aanrakingen dubbel worden geteld. Daarom kunt u de CSV-uploadoptie in marketinguitgaven blijven gebruiken om die online/digitale kosten bij te houden als we nog niet zijn geïntegreerd met dat platform (Twitter, Adroll).
