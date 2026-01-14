---
description: Richtlijnen voor het verwijderen van aanraakpunten en het onderdrukken van aanraakpunten voor Marketo Measure-gebruikers
title: Aanraakpunt verwijderen en onderdrukking aanraakpunt
exl-id: 201af648-6525-4a80-a7e5-3cbeeb1670b6
feature: Touchpoints
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 0%

---

# Aanraakpunt verwijderen en onderdrukking aanraakpunt {#touchpoint-removal-and-touchpoint-suppression}

Leer hoe u aanraakpunten die voldoen aan specifieke criteria, verwijdert of onderdrukt in uw CRM. Dit kan handig zijn om gegevensruimte vrij te maken als u [!DNL Salesforce] beperkingen voor gegevensopslag hebt.

Er is één belangrijk verschil tussen de regels voor het verwijderen van aanraakpunten en de regels voor het onderdrukken van aanraakpunten:

* Verwijderen van aanraakpunt - [!DNL Marketo Measure] verwijdert alle aanraakpunten uit uw CRM die aan de criteria van de regel voldoen. De gegevens _kunnen_ binnen het [!DNL Marketo Measure] Dashboard van ROI worden gemeld, maar niet meer in CRM.
* Aanraakpuntonderdrukking - vergelijkbaar met het verwijderen van aanraakpunten, maar de gegevens kunnen NIET worden gerapporteerd op het ROI-dashboard.

Voordat u aan de slag gaat met het maken van Touchpoint-verwijderings-/suppressieregels, is het verstandig om uw implementatieplan te delen met uw team voor marketing- en verkoopbewerkingen. U moet al weten welke typen of waarden u wilt verwijderen. Enkele gangbare gebruiksgevallen zijn:

* Aanraakpunten verwijderen uit gesloten, verloren kansen
* Aanraakpunten verwijderen uit zeer oude leads
* Aanraakpunten verwijderen uit ongekwalificeerde leads

Zodra de regels zijn opgeslagen, zal [!DNL Marketo Measure] het toewijzingsmodel opschonen en opnieuw verdelen. Dit betekent de mijlpalen en de posities zullen veranderen, en de attributie van uw kanaal zal veranderen! Hierdoor worden uw gegevens gewijzigd. Neem contact op met uw succesmanager als u hulp nodig hebt.

`1)` Er zijn twee secties voor instellingen voor verwijderen/onderdrukken. U kunt de optie instellen voor aanraakpunten voor kopers (leads en contactpersonen) of Aanraakpunten voor koperkenmerken (contactpersonen, opportunity en accounts).

Begin met het toevoegen van een regel en het selecteren van het Gebied dat uw criteria zal bepalen.

Maak een keuze in een lijst met operatoren die betrekking hebben op de volgende reeks waarden die u in de volgende kolom toevoegt.

![](assets/touchpoint-settings-10.png)

>[!TIP]
>
>Als u meerdere waarden in een veld wilt toevoegen, gebruikt u de operator &quot;Komt overeen met een&quot; met komma&#39;s die elke waarde scheiden.

>[!TIP]
>
>Als u een lege of NULL-waarde in een veld wilt verwerken, laat u het vak [!UICONTROL Value] leeg. Hierbij wordt rekening gehouden met scenario&#39;s zoals het evalueren tegen een aanraakpunt zonder URL van formulier.

>[!NOTE]
>
>Formulervelden kunnen niet worden gebruikt binnen uw regels en worden niet weergegeven in de keuzelijst. Omdat formules op de achtergrond berekenen en een record niet wijzigen, kan [!DNL Marketo Measure] niet bepalen of een record op een regel past of niet.

`2)` Voeg regels binnen dezelfde groep toe om de logica AND in uw instructie te gebruiken.
U kunt ook nieuwe instructies buiten de groep toevoegen om de logica &quot;OR&quot; in uw instructie te gebruiken.

![](assets/touchpoint-settings-11.png)

`3)` Als uw regels complex worden en u groepen opnieuw moet maken en kleine wijzigingen in elke instructie moet aanbrengen, gebruikt u de optie [!UICONTROL Clone] om de regels eenvoudiger te maken.

![](assets/touchpoint-settings-6.png)

Als je een fout maakt, maak je dan geen zorgen. U kunt ook afzonderlijke rijen van uw instructie of volledige groepen verwijderen.

![](assets/touchpoint-settings-7.png)

`4)` Stel regels in voor de aanraakpunten voor koperkenmerken als u deze op beide objecten wilt toepassen. Met onze flexibiliteit kunt u regels instellen voor één object of beide objecten en deze voor beide instellen als deze van toepassing zijn.

![](assets/touchpoint-settings-8.png)

Om te voltooien, [!UICONTROL Save and Process] uw regels. Als u veel wijzigingen aanbrengt, moet u uw wijzigingen onderweg opslaan. [!DNL Marketo Measure] verwijdert uw aanraakpunten pas wanneer u klikt
[!UICONTROL **sparen en Proces**].

| **Exploitant** | **Geval van het Gebruik** |
|---|---|
| Is gelijk aan | Enkele waarde - exact overeenkomend |
| Bevat | Enkele waarde - bevat waarde |
| Komt overeen met alles | Meerdere waarden - Exacte overeenkomst |
| Komt overeen met alle items (bevat) | Veelvoudige waarden - &#42; waarde &#42;, &#42; waarde, &#42; waarde &#42; |

Voor klanten die Dynamiek gebruiken die de regels van de Verdrukking van de opstelling willen die van Status en/of Statecode worden gebaseerd, vereisen wij het volgende formatteren wanneer vestiging de regel: `[Object].Statecode` is gelijk of niet gelijk aan `[Status Value]`. Bijvoorbeeld, als Statecode binnen Dynamiek &quot;1&quot;op een Contact leest, en de Status &quot;Inactief&quot;leest, en u al dergelijke Contacten wilde onderdrukken, zou het volgende formaat voor uw regel van de Onderdrukking onjuist zijn: Contact.Statecode is gelijk aan 1. In plaats daarvan, zou u het volgende formaat willen gebruiken - aangezien Statecode en Status als paar werken, [!DNL Marketo Measure] de waarde van Status in ons het vragen leest: Contact.Statecode is gelijk aan Inactief.
