---
description: Aanbevolen procedures voor [!DNL Marketo Measure] CRM-pakket - [!DNL Marketo Measure]
title: Aanbevolen procedures voor [!DNL Marketo Measure] CRM-pakket
exl-id: 97ce0ff3-8aa5-4789-9ee0-25d68c001def
feature: Salesforce
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 0%

---

# Aanbevolen procedures voor [!DNL Marketo Measure] CRM-pakket {#best-practices-for-marketo-measure-crm-package}

>[!NOTE]
>
>Mogelijk ziet u instructies die &quot;[!DNL Marketo Measure]&quot; in de documentatie, maar zie nog steeds &quot;Bizible&quot; in uw CRM. Dat wordt bijgewerkt en de herbranding zal spoedig in uw CRM worden weerspiegeld.

## Overzicht {#overview}

[!DNL Marketo Measure] integreert met beide [!DNL Salesforce] en [!DNL Microsoft Dynamics], wordt in dit document de nadruk gelegd op [!DNL Marketo Measure] beste praktijken voor de pakketten CRM die voor worden ontworpen [!DNL Salesforce].

Tijdens de implementatie zouden de twee volgende pakketten in uw [!DNL Salesforce] -instantie.

Basispakket: dit is het basispakket dat aangepaste objecten en velden bevat. Het wordt aanbevolen om alle gebruikers te installeren in Production.
Dashboard Extension Package: dit is ons Dashboard Extension Package, dat drie vooraf gebouwde dashboards bevat. We raden u aan om de installatie in Production voor alle gebruikers uit te voeren. Dit is optioneel, maar we moedigen klanten aan te installeren.

Deze pakketten maken uw [!DNL Marketo Measure] gebruikers eenvoudig toegang krijgen tot aanraakpuntgegevens in hun [!DNL Salesforce] -instantie. Bevestigen dat u deze pakketten correct hebt geconfigureerd, is essentieel om te controleren of paginalay-outs, machtigingssets, rapporten en dashboards aan uw [!DNL Marketo Measure] gebruikers zoals verwacht.

## Beste praktijken {#best-practice}

Wanneer het uitvoeren van en het leiden van uw [!DNL Marketo Measure] [!DNL Salesforce] Houd rekening met de volgende aanbevolen procedures:

* Bevestig dat elk noodzakelijk teamlid toegang heeft tot [!DNL Marketo Measure] rapportmappen. Er moet 1-3 zijn [!DNL Marketo Measure] mappen (deze worden hieronder uitgelegd). Om toegang te openen, moet de persoon die de pakketten installeerde de rapportomslagen met de aangewezen gebruikers of de rollen delen.
   * **Aanraakpuntrapporten van koper** - voor iedereen beschikbaar
   * **[!DNL Marketo Measure]Marketingsrapporten op basis van account** - de rapporten worden alleen ingevuld bij klanten van Tier 2 en hoger
   * **Aanraakpuntdashboards van koper** - beschikbaar voor iedereen, hoewel dit pakket facultatief is.

## Aanbevolen werkwijzen voor onderhoud {#best-practice-for-maintenance}

Terwijl de opstelling van uw Pakket van CRM tijdens aanvankelijke implementatie wordt behandeld, adviseert men dat u de opstelling van uw pakket van CRM eens per jaar herziet. Deze revisie bevestigt dat alle paginalay-outs correct zijn ingesteld en dat alle relevante teamleden toegang hebben tot [!DNL Marketo Measure] rapporten en dashboards.

Andere redenen daarvoor kunnen aanleiding geven tot een herziening...

* Toevoeging van nieuwe teamleden
* Updates voor uw [!DNL Salesforce] paginalay-outs
* Migratie voor [!DNL Salesforce] Klassiek naar lichter maken
* Upgrades naar uw [!DNL Marketo Measure] contract
* Controleer of u de meest recente versie van het pakket met aanraakpunten voor kopers hebt geïnstalleerd in [!DNL Salesforce]

>[!NOTE]
>
>Wanneer u het exporteren van gegevens van Marketo Measure naar Salesforce uitschakelt, worden bestaande gegevens niet verwijderd. Volg de stappen in om het bestand te verwijderen [dit Help-artikel voor Salesforce](https://help.salesforce.com/s/articleView?language=en_US&id=sf.c360_a_delete_data_stream_records.htm&type=5){target="_blank"}.

>[!MORELIKETHIS]
>
>* [Aanraakpuntpakket voor koper bijwerken](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-salesforce-package-installation-and-set-up.md)
>* [[!DNL Marketo Measure] Machtigingssets](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md)
>* [Map Rapporten en dashboards delen](https://help.salesforce.com/s/articleView?language=en_US&id=analytics_share_folder.htm&type=0)
>* [Marketo Measure verbinden met Salesforce](/help/configuration-and-setup/marketo-measure-and-salesforce/connect-marketo-measure-to-salesforce.md)
