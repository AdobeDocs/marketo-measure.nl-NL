---
unique-page-id: 18874688
description: Kosten van CRM-campagne - [!DNL Marketo Measure] - Productdocumentatie
title: Kosten CRM-campagne
exl-id: d967cabe-b9f1-4ea1-a81b-e4484c703ecf
feature: Spend Management
source-git-commit: 8ac315e7c4110d14811e77ef0586bd663ea1f8ab
workflow-type: tm+mt
source-wordcount: '1228'
ht-degree: 0%

---

# Kosten CRM-campagne {#crm-campaign-costs}

Meeste [!DNL Marketo Measure] klanten gebruiken CRM-campagnes om offline marketingactiviteiten te volgen. Marketers die deze campagnes gebruiken, zullen ook kosten binnen CRM controleren, zodat maakt deze eigenschap het op marketers gemakkelijker door toe te staan [!DNL Marketo Measure] deze kosten te lezen en toe te passen op de gerapporteerde marketinguitgaven binnen [!DNL Marketo Measure]. Tot op heden moesten klanten de kosten voor elke campagne per maand manueel invoeren, maar met de noodzakelijke informatie die aan ons werd verstrekt, [!DNL Marketo Measure] kan dit proces automatiseren zodat marketers meer tijd kunnen besteden aan het analyseren van hun uitgaven en investeringsrendement.

## Beschikbaarheid {#availability}

Deze functie is beschikbaar voor alle [!DNL Salesforce] en Dynamics-klanten.

## Hoe het werkt {#how-it-works}

[!DNL Marketo Measure] zoekt eerst naar campagnes die &quot;toegelaten&quot;voor aanraakpunten zijn, zodat is er of een passende regel van de Synchronisatie van de Campagne die werd gecreeerd, of de Enable aanraakpunten van de Koper is waarde &quot;omvat Alle Campagne Leden&quot;of &quot;omvat &quot;Ontvangen&quot;Campagneleden.&quot;omvat Daarnaast [!DNL Marketo Measure] moeten de juiste waarden importeren en weten hoe de kosten moeten worden verdeeld. Daarom moeten de volgende velden een waarde bevatten:

**[!DNL Salesforce]**: ActualCost, StartDate, EndDate

**[!DNL Microsoft Dynamics]**: totale actualcost, actualstart, actualend

Als in een van de drie velden een waarde ontbreekt, [!DNL Marketo Measure] zal de kosten niet invoeren. U kunt dit verbeteren door het verslag van de Campagne in CRM bij te werken. Ook belangrijk om op te merken dat wij de kosten niet zullen invoeren als het uitdrukkelijk aan $0 wordt geplaatst omdat [!DNL Salesforce] behandelt leeg en $0 als het zelfde.

Om [!DNL Marketo Measure] om de verdeling van een campagne over maanden te bepalen , gebruiken wij de begin - en einddatum van de campagne en verdelen wij het bedrag gelijkmatig per dag .

![](assets/1.jpg)

In dit voorbeeld hebben we een campagne die 109 dagen duurt, dus met een totale kostprijs van $18.000, komt de uitgave per dag op ~$165,14.

Op basis van het aantal dagen per maand krijgen we deze maandelijkse totalen, zoals u in de tabel kunt zien:

Juli 2018: ($18.000/109) x 31 = $5.119.27

aug 2018: ($18,000/109) x 31 = $5,119,27

Sept 2018: ($18,000/109) x 30 = $4,954.13

okt 2018: ($ 18.000/109) x 17 = $ 2.807,34

## Historische gerapporteerde uitgave {#historical-reported-spend}

Maak je geen zorgen! Als u uitgaven voor Campagnes bent ingegaan die wij in het verleden hebben gevolgd die aan een Campagne van CRM in kaart werden gebracht, zullen wij geen van de kosten met voeten treden u hebt ingegaan. Als de zelfde campagne in CRM wordt gewijzigd, zullen wij het nog negeren en prioriteit geven aan de veranderingen u eerder in CSV uploadde had aangebracht.

Als u verkiest dat wij de kosten van de Campagne van CRM bewegend vooruit nemen, kunt u de waarde in CSV in $0 veranderen die de ingang zal vernietigen. De volgende keer dat we onze taken uitvoeren om de kosten in te voeren, zullen we zoeken naar records die eerder zijn bewerkt en dat vervolgens weer terugbrengen.

## Campagnes zonder aanraakpunten {#campaigns-with-no-touchpoints}

Vele marketers verkiezen om marketing uitgaven aan de Campagnes van CRM te melden die toevallig om het even welke aanraakpunten produceerden, of bewust geen leden van de Campagne voor het volgen van uitgaven hebben. Zolang de drie velden zijn ingevuld (startdatum, einddatum, kosten) en de campagne is ingeschakeld voor aanraakpunten, [!DNL Marketo Measure] zal die kosten nog steeds doorberekenen, ongeacht of er wel of geen aanraakpunten aan verbonden zijn.

Dit zou voor het volgen van uitgaven aan overtollige Marketingkosten of hulpmiddelen kunnen nuttig zijn om dat omhoog in uw berekeningen van het ROI te rollen.

## Marketo Program Sync {#marketo-program-sync}

Als u de Programma&#39;s van Marketo in CRM als Campagnes brengt, zult u willen verzekeren u de Datum van het Begin, de Datum van het Eind, en de Toerekening van de Kosten van de Periode opstelling aan de vereiste gebieden van CRM hebt. Aangezien het veld Aanraakpunten koper inschakelen niet in kaart is gebracht, moet u deze campagnes nog steeds inschakelen zodat we weten dat we de kosten voor hen moeten opbrengen.

## Bewerking van de kosten {#editing-the-costs}

Als een campagne eenmaal is geïmporteerd vanuit de CRM, wordt deze op dezelfde manier behandeld als een API-advertentieprovider en wordt deze niet weergegeven in de CSV om wijzigingen in de kosten aan te brengen.

Elke wijziging van de kosten of de verdeling moet plaatsvinden in de BCR, zodat we op één enkel waarheidspunt kunnen wijzen.

## Veelgestelde vragen {#faq}

**Ik heb een wijziging aangebracht in mijn campagne - wanneer zou ik de veranderingen in de lijst van de Uitgaven van de Marketing of in mijn rapportering moeten verwachten?**

3-4 uur

**Ik heb de begindatum, einddatum en kosten ingevuld, maar waarom komen mijn kosten nog steeds niet voor [!DNL Marketo Measure]?**

Controleer of u de waarde Enable Buyer Touchpoint hebt ingesteld op &quot;Include All Campaign Member&quot; of op zijn minst &quot;Include Reponded&quot; Campagneleden, of of u een aangepaste regel Campagne Sync hebt gemaakt die deze campagne omvat. Als u dit hebt bevestigd en de campagne nog steeds niet ziet, kunt u contact opnemen met [Marketo-ondersteuning](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"} zodat kunnen wij controleren dat uw campagnes behoorlijk invoeren.

**Ik moet de verdeling van mijn campagne veranderen zodat ik het in bepaalde maanden zwaarder kan wegen. Hoe doe ik dat?**

De verdeling van de kosten is uitsluitend gebaseerd op een gelijkmatige verdeling van de begindatum tot de einddatum. Helaas, kunnen wij het niet veranderen zodat uw kosten een verschillend gewicht naast de vastgestelde data hebben. U kunt dit controleren door de begin en einddatum van uw campagne aan te passen aangezien elke dag in de maandkwestie van belang is.

**Ik heb kosten in verband met mijn bovenliggende campagne - hoe krijgen de kindercampagnes de kosten van de bovenliggende campagne toegewezen?**

De manier waarop de kosten in beslag worden genomen, zal rechtstreeks afkomstig zijn van één campagne, ongeacht de relatie tussen moeder en kind. We raden aan om de kosten op de Kindercampagnes te zetten, samen met de data van de campagne, dan de Ouder te gebruiken als de paraplu-campagne waar de Ouderlijke Campagne niet geschikt zou worden gemaakt voor aanraakpunten.

**Hoe verander ik de kosten voor een maand in [!DNL Marketo Measure]?**

Omdat wij op CRM als enige bron van waarheid vertrouwen, moeten alle veranderingen in CRM worden aangebracht. Nadat de campagne is geïmporteerd door [!DNL Marketo Measure], kunnen de Campagnewaarden niet worden bewerkt in [!DNL Marketo Measure] of in het CSV-bestand.

**In welk scenario zou een Campagne in de Lijst van de Uitgaven van de Marketing verschijnen, dan niet meer verschijnen?**

We blijven vereisen dat alle drie de sleutelvelden een waarde hebben: Begindatum, Einddatum en Kosten. Ons standaardgedrag is dat we alleen campagnes importeren met een waarde groter dan $0. In het ideale geval zouden we campagnes importeren waar expliciet $0 is en geen campagnes die leeg blijven importeren, maar de Salesforce-API importeert beide als $0, ongeacht de waarde. Als de waarde van het aanraakpunt voor kopers inschakelen verandert van Alles opnemen of Inclusief &#39;Alle geantwoord&#39; in Alles uitsluiten, worden bovendien de campagne en de kosten verwijderd uit de tabel met marketinguitgaven.

**Welke kosten zouden prioriteit nemen als een rij reeds van CRM werd gedownload en ik een andere rij in CSV met zelfde campagneId inging?**

Hoewel u het bestand mogelijk met succes kunt uploaden, [!DNL Marketo Measure] zal die rij niet gebruiken omdat wij reeds een campagne-ID met de zelfde waarde hebben die automatisch uit de integratie werd getrokken.

**Hoe zou u suggereren dat we het kosten van onze digitale campagnes die we hebben opgezet in de CRM?**

Omdat ons [!DNL Marketo Measure] JavaScript volgt de webactiviteiten van uw site al. We raden u aan campagnes die leden van de campagne volgen op webformulieren of andere activiteiten op de site niet te synchroniseren, omdat hierdoor de aanrakingen dubbel worden geteld. Daarom kunt u de CSV-uploadoptie in marketinguitgaven blijven gebruiken om die online/digitale kosten bij te houden als we nog niet met dat platform zijn geïntegreerd (Twitter, Adroll).
