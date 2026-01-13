---
description: Kosten CRM-campagne
title: Kosten CRM-campagne
exl-id: d967cabe-b9f1-4ea1-a81b-e4484c703ecf
feature: Spend Management
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '1194'
ht-degree: 0%

---


# Kosten CRM-campagne {#crm-campaign-costs}

De meeste [!DNL Marketo Measure] klanten gebruiken CRM-campagnes om offline marketingactiviteiten bij te houden. Marktdeelnemers die deze campagnes gebruiken, controleren ook de kosten binnen de BCR. Deze functie maakt het voor marketers gemakkelijker door [!DNL Marketo Measure] toe te staan die kosten te lezen en toe te passen op de gerapporteerde marketinguitgaven binnen [!DNL Marketo Measure] . Tot op heden, hebben de klanten kosten voor elke campagne per maand manueel moeten ingaan, maar met de noodzakelijke informatie die aan [!DNL Marketo Measure] wordt verstrekt, kunnen de gebruikers dit proces automatiseren zodat kunnen de marketers meer tijd doorbrengen die hun uitgaven en ROI analyseren.

## Beschikbaarheid {#availability}

Deze functie is beschikbaar voor alle klanten van [!DNL Salesforce] en van de Dynamica.

## Hoe het werkt {#how-it-works}

[!DNL Marketo Measure] zoekt eerst naar campagnes die &quot;toegelaten&quot;voor aanraakpunten zijn, zodat is er of een passende regel van de Synchronisatie van de Campagne die werd gecreeerd, of de Enable Aanraakpunten van de Koper waarde &quot;omvat Alle Campagne Leden&quot;of omvat &quot;Geënquêteerde&quot;Campagneleden.&quot; Daarnaast moet [!DNL Marketo Measure] de juiste waarden importeren en weten hoe de kosten moeten worden verdeeld. Daarom moeten de volgende velden een waarde bevatten:

**[!DNL Salesforce]**: `ActualCost` , `StartDate` , `EndDate`

**[!DNL Microsoft Dynamics]**: `totalactualcost` , `actualstart` , `actualend`

Als in een van de drie velden een waarde ontbreekt, importeert [!DNL Marketo Measure] de kosten niet. U kunt dit verbeteren door het verslag van de Campagne in CRM bij te werken. Kosten worden niet geïmporteerd als deze is ingesteld op $0, omdat [!DNL Salesforce] de lege waarde en $0 gelijk behandelt.

[!DNL Marketo Measure] bepaalt de verdeling van een campagne over maanden door de begin- en einddatum van de campagne te gebruiken om het bedrag gelijkmatig per dag te verdelen.

![ voorbeeld van de de campagnekostendistributie van CRM door maand ](assets/1.jpg)

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

Veel marketers kiezen ervoor marketinguitgaven te melden voor CRM-campagnes die geen aanraakpunten hebben gegenereerd of die geen campagneleden hebben voor het bijhouden van hun uitgaven. Zolang de drie velden zijn ingevuld (startdatum, einddatum, kosten) en de campagne is ingeschakeld voor aanraakpunten, trekt [!DNL Marketo Measure] die kosten in, zelfs als er geen aanraakpunten aan zijn gekoppeld.

Dit zou voor het volgen van uitgaven aan overtollige Marketingkosten of hulpmiddelen kunnen nuttig zijn om dat omhoog in uw berekeningen van het ROI te rollen.

## Marketo Program Sync {#marketo-program-sync}

Als u de Programma&#39;s van Marketo in CRM als Campagnes brengt, zorg ervoor u de de kaartopstelling van de Kosten van het Begin, van het Eind, en van de Periode aan de vereiste gebieden van CRM hebt. Aangezien het veld Aanraakpunten koper inschakelen niet in kaart is gebracht, moet u deze campagnes toch inschakelen zodat de kosten kunnen worden opgevangen.

## Bewerking van de kosten {#editing-the-costs}

Als een campagne eenmaal is geïmporteerd vanuit de CRM, wordt deze op dezelfde manier behandeld als een API-advertentieprovider en wordt deze niet weergegeven in de CSV om wijzigingen in de kosten aan te brengen.

Elke wijziging van de kosten of de verdeling moet plaatsvinden in de BCR, zodat we op één enkel waarheidspunt kunnen wijzen.

## Veelgestelde vragen {#faq}

**ik heb een verandering in mijn campagne aangebracht - wanneer zou ik moeten verwachten om de veranderingen in de lijst van de Uitgaven van de Marketing of in mijn rapportering te zien?**

3-4 uur

**ik heb de begindatum, de einddatum, en de gevulde kosten maar waarom worden mijn kosten nog niet getoond in [!DNL Marketo Measure]?**

Controleer of u de waarde &quot;Buyer Touchpoint inschakelen&quot; hebt ingesteld op &quot;Alle campagneleden opnemen&quot; of op zijn minst &quot;Alle leden van campagne opnemen die zijn gereageerd&quot;, of dat u een aangepaste regel voor campagnecorrectie hebt gemaakt die deze campagne omvat. Als u dit hebt bevestigd en nog niet de Campagne ziet, reik uit naar [ Steun van Marketo ](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} zodat kunnen wij controleren dat uw Campagnes behoorlijk invoeren.

**ik moet de distributie van mijn Campagne veranderen zodat ik het in bepaalde maanden kan zwaarder wegen. Hoe doe ik dat?**

De verdeling van de kosten is uitsluitend gebaseerd op een gelijkmatige verdeling van de begindatum tot de einddatum. Helaas, kunnen wij het niet veranderen zodat uw kosten een verschillend gewicht naast de vastgestelde data hebben. U kunt dit controleren door de begin en einddatum van uw campagne aan te passen aangezien elke dag in de maandkwestie van belang is.

**ik heb kosten opstelling op mijn Ouderlijke Campagne - hoe worden de Kindercampagnes toegewezen de kosten van de Ouderlijke Campagne?**

De manier waarop de kosten in beslag worden genomen, zal rechtstreeks afkomstig zijn van één campagne, ongeacht de relatie tussen moeder en kind. We raden aan om de kosten op de Kindercampagnes te zetten, samen met de data van de campagne, dan de Ouder te gebruiken als de paraplu-campagne waar de Ouderlijke Campagne niet geschikt zou worden gemaakt voor aanraakpunten.

**Hoe verander ik de kosten voor een maand in [!DNL Marketo Measure]?**

Omdat wij op CRM als enige bron van waarheid vertrouwen, moeten alle veranderingen in CRM worden aangebracht. Nadat de campagne door [!DNL Marketo Measure] is geïmporteerd, kunnen de Campagnewaarden niet meer worden bewerkt in [!DNL Marketo Measure] of in het CSV-bestand.

**in welk scenario zou een Campagne in de lijst van de Uitgaven van de Marketing verschijnen, dan niet meer?**

We blijven vereisen dat alle drie de sleutelvelden een waarde hebben: Begindatum, Einddatum en Kosten. Ons standaardgedrag is dat we alleen campagnes importeren met een waarde groter dan $0. In het ideale geval importeren we campagnes met expliciet $0 en importeren we geen campagnes die leeg blijven, maar de Salesforce API importeert ze allebei als $0, ongeacht de waarde. Als de waarde voor Buyer Touchpoint inschakelen verandert van Alles opnemen of Alles opnemen in antwoord, worden bovendien de campagne en de kosten verwijderd uit de tabel met marketinguitgaven.

**Welke kosten zouden prioriteit nemen als een rij reeds van CRM werd gedownload en ik een andere rij in CSV met zelfde campagneId inging?**

Hoewel u het bestand mogelijk met succes kunt uploaden, gebruikt [!DNL Marketo Measure] die rij niet omdat er al een campagne-id is met dezelfde waarde die automatisch uit de integratie is gehaald.

**hoe u zou voorstellen wij het kosten van onze Digitale Campagnes brengen die wij opstelling in CRM?**

Omdat in [!DNL Marketo Measure] javascript al webactiviteiten van uw site worden bijgehouden, raden we u aan geen campagnes te synchroniseren die Campagneleden volgen op webformulieren of andere activiteiten op de site, omdat hierdoor de aanrakingen dubbel worden geteld. Daarom kunt u de CSV-uploadoptie in marketinguitgaven blijven gebruiken om die online/digitale kosten bij te houden als we nog niet zijn geïntegreerd met dat platform (dat wil zeggen, Twitter, Adroll).
