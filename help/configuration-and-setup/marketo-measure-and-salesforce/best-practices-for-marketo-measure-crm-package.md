---
description: Aanbevolen procedures voor [!DNL Marketo Measure] CRM-pakket - [!DNL Marketo Measure] - Productdocumentatie
title: Aanbevolen procedures voor [!DNL Marketo Measure] CRM-pakket
exl-id: 97ce0ff3-8aa5-4789-9ee0-25d68c001def
source-git-commit: 00268f49ff6e5dfc105fa7ea21837375eae49647
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---

# Aanbevolen procedures voor [!DNL Marketo Measure] CRM-pakket {#best-practices-for-marketo-measure-crm-package}

>[!NOTE]
>
>Mogelijk ziet u instructies die &quot;[!DNL Marketo Measure]&quot; in onze documentatie, maar zie nog &quot;Bizible&quot;in uw CRM. We werken eraan dat dit wordt bijgewerkt en de herbranding wordt binnenkort weerspiegeld in uw CRM.

## Overzicht {#overview}

[!DNL Marketo Measure] integreert met beide [!DNL Salesforce] en [!DNL Microsoft Dynamics], richt dit document zich op de [!DNL Marketo Measure] beste praktijken voor de pakketten CRM die voor worden ontworpen [!DNL Salesforce].

Tijdens de implementatie zouden de twee volgende pakketten in uw [!DNL Salesforce] -instantie.

Basispakket: Dit is ons basispakket dat onze aangepaste objecten en velden bevat. We raden u aan om de installatie in Production voor alle gebruikers uit te voeren.
Extensiepakket dashboard: Dit is ons Dashboard Extension Package, dat 3 vooraf gebouwde dashboards bevat. We raden u aan om de installatie in Production voor alle gebruikers uit te voeren. Dit is optioneel, maar we moedigen klanten aan te installeren.

Deze pakketten maken uw [!DNL Marketo Measure] gebruikers eenvoudig toegang krijgen tot aanraakpuntgegevens in hun [!DNL Salesforce] -instantie. Als u bevestigt dat u deze pakketten correct hebt geconfigureerd, moet u controleren of de paginalay-outs, machtigingssets en rapporten en dashboards aan uw [!DNL Marketo Measure] gebruikers zoals verwacht.

## Beste praktijken {#best-practice}

Wanneer het over het uitvoeren van en het leiden van uw [!DNL Marketo Measure] [!DNL Salesforce] Houd bij het verpakken rekening met de volgende aanbevolen procedures.

* Bevestig elk noodzakelijk teamlid toegang tot heeft [!DNL Marketo Measure] rapportmappen. Er moet 1-3 zijn [!DNL Marketo Measure] mappen (deze worden hieronder uitgelegd). Om toegang te openen, moet de persoon die het pakket of de pakketten installeerde de rapportomslagen met de aangewezen gebruikers of de rollen delen.
   * **Aanraakpuntrapporten koper** - voor iedereen beschikbaar
   * **[!DNL Marketo Measure]Marketingsrapporten op basis van account** - de rapporten worden alleen ingevuld bij klanten van Tier 2 en hoger
   * **Aanraakpuntdashboards van koper** - beschikbaar voor iedereen, hoewel dit pakket facultatief is.

## Best Practice for Maintenance {#best-practice-for-maintenance}

Terwijl de opstelling van uw Pakket van CRM tijdens aanvankelijke implementatie wordt behandeld, adviseren wij dat u de opstelling van uw pakket van CRM eens per jaar herziet. Deze revisie zal bevestigen dat alle paginalay-outs correct opstelling zijn en dat alle aangewezen teamleden toegang hebben tot [!DNL Marketo Measure] rapporten en dashboards.

Andere redenen daarvoor kunnen aanleiding geven tot een herziening...

* Toevoeging van nieuwe teamleden
* Updates voor u [!DNL Salesforce] paginalay-outs
* Migratie voor [!DNL Salesforce] Klassiek naar lichter maken
* Upgrades naar uw [!DNL Marketo Measure] contract
* Controleer of de meest recente versie van ons pakket met aanraakpunten voor kopers is geïnstalleerd in [!DNL Salesforce]

>[!NOTE]
>
>Wanneer u het exporteren van gegevens van Marketo Measure naar Salesforce uitschakelt, worden bestaande gegevens niet verwijderd. Volg de stappen in [dit Help-artikel voor Salesforce](https://help.salesforce.com/s/articleView?id=sf.c360_a_delete_data_stream_records.htm&amp;type=5){target="_blank"}.

>[!MORELIKETHIS]
>
>* [Aanraakpuntpakket voor koper bijwerken](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-salesforce-package-installation-and-set-up.md)
>* [[!DNL Marketo Measure] Machtigingssets](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md)
>* [Map Rapporten en dashboards delen](https://help.salesforce.com/articleView?id=analytics_share_folder.htm&amp;type=0)
>* [Marketo Measure verbinden met Salesforce](/help/configuration-and-setup/marketo-measure-and-salesforce/connect-marketo-measure-to-salesforce.md)

