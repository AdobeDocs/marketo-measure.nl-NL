---
unique-page-id: 27656737
description: Marketingbestedingen rapporteren - [!DNL Marketo Measure]
title: Marketingbestedingen rapporteren
exl-id: 46b0f81c-acd1-47a5-bf75-6a943edb9009
feature: Reporting, Spend Management
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 0%

---

# Marketingbestedingen rapporteren {#report-marketing-spend}

## Tabel met marketinguitgaven {#marketing-spend-table}

De lijst van de Uitgaven van de Marketing zal nu een nieuwe kolom bevatten om de munt voor elk Kanaal, Subkanaal, en rij van de Campagne te tonen. Deze nieuwe kolom zal voor alle klanten tonen, zelfs als zij geen Veelvoudige Toegelaten Valuta&#39;s hebben.

De tabel zal nu een combinatie van verschillende valuta&#39;s bevatten. Raadpleeg het dashboard marketinguitgaven als u de som van kanalen, subkanalen of campagnes in één valuta moet ophalen.

## Kosten uploaden {#upload-costs}

Wanneer een gebruiker het kostenbestand downloadt, bevat het bestand ook een nieuwe kolom met de valuta voor elke rij. De enige acceptabele valuta&#39;s zijn de valuta&#39;s die in de CRM zijn ingesteld en opgeslagen. U moet weten wat de afgekorte code van drie letters is voor uw valuta (USD, CAD, JPY, EUR) en wanneer een bestand wordt geüpload met een niet-herkende valuta, mislukt het uploaden van het bestand.

## Kosten van de integratie van hulpmiddelen {#costs-from-ad-integrations}

Wanneer [!DNL Marketo Measure] Hiermee importeert u de kosten van verbonden platforms zoals AdWords, Bing, Facebook of Doubleclick. Ook gebruiken we de gerapporteerde valuta. De valuta wordt naast Kanaal, Subkanaal en Campagne weergegeven wanneer deze worden weergegeven in de tabel marketinguitgaven.

Als de valuta van de advertentieprovider niet overeenkomt met een valuta die van de CRM is gehaald, wordt mogelijk een fout met &quot;Gemengde valuta&#39;s&quot; weergegeven in [!DNL Marketo Measure Discover] omdat we die valuta niet konden omrekenen. Om dit te bevestigen, moet uw Admin van CRM een omzetting voor de onbekende munt toevoegen.

## Migreren naar geconverteerde marketinguitgaven {#migrate-to-converted-marketing-spend}

Omdat onze marketinguitgaven historisch slechts in één valuta (USD) zijn gedaan, is er een kleine hoeveelheid werk nodig om alle gemelde uitgaven aan de nieuwe valuta te veranderen. Zelfs als Meerdere valuta&#39;s niet zijn ingeschakeld voor uw account, als u één andere bedrijfsvaluta dan USD hebt, kunt u deze migratie uitvoeren.

1. Het huidige uitgavenbestand downloaden naar een CSV
1. De valutakolom wordt weergegeven als &quot;[!UICONTROL USD]&quot; als de veronderstelde valuta. U kunt ofwel handmatig alle instanties van &quot;[!UICONTROL USD]&quot; of gebruik Zoeken+vervangen om alle &quot;[!UICONTROL USD]&quot; exemplaren naar uw eigen bedrijfsvaluta, zoals &quot;[!UICONTROL EUR]&quot; of &quot;[!UICONTROL GBP]&quot; bijvoorbeeld.
1. Sla het bestand op en upload het opnieuw naar [!DNL Marketo Measure].
1. Alle gerapporteerde kosten worden nu weergegeven als de nieuwe valuta.
