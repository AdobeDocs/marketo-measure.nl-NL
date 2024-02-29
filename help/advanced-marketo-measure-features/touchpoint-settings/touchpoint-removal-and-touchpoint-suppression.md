---
unique-page-id: 18874710
description: Aanraakpunt verwijderen en onderdrukking aanraakpunt - [!DNL Marketo Measure] - Productdocumentatie
title: Aanraakpunt verwijderen en onderdrukking aanraakpunt
exl-id: 201af648-6525-4a80-a7e5-3cbeeb1670b6
feature: Touchpoints
source-git-commit: cc786cb3af08fa36af91ef22f4dba3072c9617eb
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 0%

---

# Aanraakpunt verwijderen en onderdrukking aanraakpunt {#touchpoint-removal-and-touchpoint-suppression}

Leer hoe u aanraakpunten die voldoen aan specifieke criteria, verwijdert of onderdrukt in uw CRM. Dit kan nuttig zijn voor het vrijmaken van gegevensruimte als u [!DNL Salesforce] maximale gegevensopslag.

Er is één belangrijk verschil tussen de regels voor het verwijderen van aanraakpunten en de regels voor het onderdrukken van aanraakpunten:

* Aanraakpunt verwijderen - [!DNL Marketo Measure] verwijdert alle aanraakpunten uit uw CRM die aan de criteria van de regel voldoen. De gegevens _kan_ binnen de [!DNL Marketo Measure] ROI Dashboard, maar niet meer in CRM.
* Aanraakpuntonderdrukking - vergelijkbaar met het verwijderen van aanraakpunten, maar de gegevens kunnen NIET worden gerapporteerd op het ROI-dashboard.

Voordat u aan de slag gaat met het maken van Touchpoint-verwijderings-/suppressieregels, is het verstandig om uw implementatieplan te delen met uw team voor marketing- en verkoopbewerkingen. U moet al weten welke typen of waarden u wilt verwijderen. Enkele gangbare gebruiksgevallen zijn:

* Aanraakpunten verwijderen uit gesloten, verloren kansen
* Aanraakpunten verwijderen uit zeer oude leads
* Aanraakpunten verwijderen uit ongekwalificeerde leads

Zodra de regels zijn opgeslagen, [!DNL Marketo Measure] zal uw attributiemodel opschonen en opnieuw verdelen. Dit betekent de mijlpalen en de posities zullen veranderen, en de attributie van uw kanaal zal veranderen! Hierdoor worden uw gegevens gewijzigd. Neem contact op met uw succesmanager als u hulp nodig hebt.

`1)` Er zijn twee gedeelten voor instellingen voor verwijderen/onderdrukken. U kunt de optie instellen voor aanraakpunten voor kopers (leads en contactpersonen) of Aanraakpunten voor koperkenmerken (contactpersonen, opportunity en accounts).

Begin met het toevoegen van een regel en het selecteren van het Gebied dat uw criteria zal bepalen.

Maak een keuze in een lijst met operatoren die betrekking hebben op de volgende reeks waarden die u in de volgende kolom toevoegt.

![](assets/1-1.png)

>[!TIP]
>
>Als u meerdere waarden in een veld wilt toevoegen, gebruikt u de operator &quot;Komt overeen met een&quot; met komma&#39;s die elke waarde scheiden.

>[!TIP]
>
>Als u een lege of NULL-waarde in een veld wilt verwerken, laat u gewoon de instelling [!UICONTROL Value] leeg. Hierbij wordt rekening gehouden met scenario&#39;s zoals het evalueren tegen een aanraakpunt zonder URL van formulier.

>[!NOTE]
>
>Formulervelden kunnen niet worden gebruikt binnen uw regels en worden niet weergegeven in de keuzelijst. Omdat formules op de achtergrond berekenen en een record niet wijzigen, [!DNL Marketo Measure] kan niet ontdekken of een verslag een regel past of niet.

`2)` Voeg regels binnen de zelfde groep toe om &quot;EN&quot;logica in uw verklaring te gebruiken.
U kunt ook nieuwe instructies buiten de groep toevoegen om de logica &quot;OR&quot; in uw instructie te gebruiken.

![](assets/2.png)

`3)` Als uw regels complex worden en u groepen moet opnieuw maken en kleine wijzigingen in elke instructie aanbrengen, gebruikt u de opdracht [!UICONTROL Clone] om de zaken eenvoudiger te maken.

![](assets/3.png)

Als je een fout maakt, maak je dan geen zorgen. U kunt ook afzonderlijke rijen van uw instructie of volledige groepen verwijderen.

![](assets/4.png)

`4)` Stel regels in voor de aanraakpunten voor koperkenmerken als u deze op beide objecten wilt toepassen. Met onze flexibiliteit kunt u regels instellen voor één object of beide objecten en deze voor beide instellen als deze van toepassing zijn.

![](assets/5.png)

Tot slot: [!UICONTROL Save and Process] uw regels. Als u veel wijzigingen aanbrengt, moet u uw wijzigingen onderweg opslaan. [!DNL Marketo Measure] begint pas echt met het verwijderen van uw aanraakpunten wanneer u op de knop **Opslaan en verwerken** knop.

| **Operator** | **Hoofdletters gebruiken** |
|---|---|
| Is gelijk aan | Enkele waarde - exact overeenkomend |
| Bevat | Enkele waarde - bevat waarde |
| Komt overeen met alles | Meerdere waarden - Exacte overeenkomst |
| Komt overeen met alle items (bevat) | Meerdere waarden - &#42;value&#42;, &#42;waarde, &#42;value&#42; |

Voor klanten die Dynamiek gebruiken die aan de regels van de Opperkking van opstelling willen die van Status en/of Statecode worden gebaseerd, vereisen wij het volgende formatteren wanneer vestiging de regel: `[Object].Statecode` is gelijk aan/niet gelijk aan `[Status Value]`. Bijvoorbeeld, als Statecode binnen Dynamiek &quot;1&quot;op een Contact leest, en de Status &quot;Inactief&quot;leest, en u al dergelijke Contacten wilde onderdrukken, zou het volgende formaat voor uw regel van de Onderdrukking onjuist zijn: Contact.Statecode is gelijk aan 1. In plaats daarvan, zou u het volgende formaat willen gebruiken - aangezien Statecode en Status als paar werken, [!DNL Marketo Measure] leest de waarde van Status in ons het vragen: Contact.Statecode is gelijk aan Inactief.
