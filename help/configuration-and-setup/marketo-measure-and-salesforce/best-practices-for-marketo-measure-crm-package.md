---
description: De beste praktijken voor  [!DNL Marketo Measure]  Pakket van CRM -  [!DNL Marketo Measure]
title: Beste praktijken voor  [!DNL Marketo Measure]  het Pakket van CRM
exl-id: 97ce0ff3-8aa5-4789-9ee0-25d68c001def
feature: Salesforce
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 0%

---

# Aanbevolen procedures voor het [!DNL Marketo Measure] CRM-pakket {#best-practices-for-marketo-measure-crm-package}

>[!NOTE]
>
>U kunt instructies zien die &quot;[!DNL Marketo Measure]&quot;in de documentatie specificeren, maar nog zie &quot;Bizible&quot;in uw CRM. Dat wordt bijgewerkt en de herbranding zal spoedig in uw CRM worden weerspiegeld.

## Overzicht {#overview}

[!DNL Marketo Measure] integreert met zowel [!DNL Salesforce] als [!DNL Microsoft Dynamics] , dit document richt zich op de [!DNL Marketo Measure] aanbevolen procedures voor de CRM-pakketten die zijn ontworpen voor [!DNL Salesforce] .

Tijdens de implementatie zouden de twee volgende pakketten in uw [!DNL Salesforce] -instantie zijn geïnstalleerd.

Basispakket: dit is het basispakket dat aangepaste objecten en velden bevat. Het wordt aanbevolen om alle gebruikers te installeren in Production.
Dashboard Extension Package: dit is ons Dashboard Extension Package, dat drie vooraf gebouwde dashboards bevat. We raden u aan om de installatie in Production voor alle gebruikers uit te voeren. Dit is optioneel, maar we moedigen klanten aan te installeren.

Met deze pakketten hebben [!DNL Marketo Measure] -gebruikers eenvoudig toegang tot aanraakpuntgegevens via hun [!DNL Salesforce] -instantie. Als u bevestigt dat u deze pakketten correct hebt geconfigureerd, moet u controleren of de paginalay-outs, machtigingssets, rapporten en dashboards naar verwachting aan uw [!DNL Marketo Measure] -gebruikers worden getoond.

## Beste praktijken {#best-practice}

Houd bij het implementeren en beheren van het [!DNL Marketo Measure] [!DNL Salesforce] -pakket rekening met de volgende aanbevolen procedures.

* Controleer of elk vereist teamlid toegang heeft tot de rapportmappen van [!DNL Marketo Measure] . Er moeten 1-3 [!DNL Marketo Measure] mappen zijn (deze worden hieronder uitgelegd). Om toegang te openen, moet de persoon die de pakketten installeerde de rapportomslagen met de aangewezen gebruikers of de rollen delen.
   * **de Rapporten van Buyer Touchpoint** - beschikbaar aan iedereen
   * **[!DNL Marketo Measure]Op account gebaseerde marketingrapporten** - rapporten worden alleen ingevuld bij klanten van niveau 2 en hoger
   * **de Dashboards van Buyer Touchpoint** - beschikbaar aan iedereen, hoewel dit pakket facultatief is.

## Aanbevolen werkwijzen voor onderhoud {#best-practice-for-maintenance}

Terwijl de opstelling van uw Pakket van CRM tijdens aanvankelijke implementatie wordt behandeld, adviseert men dat u de opstelling van uw pakket van CRM eens per jaar herziet. Deze revisie bevestigt dat alle paginalay-outs correct zijn ingesteld en dat alle relevante teamleden toegang hebben tot [!DNL Marketo Measure] -rapporten en -dashboards.

Andere redenen daarvoor kunnen aanleiding geven tot een herziening...

* Toevoeging van nieuwe teamleden
* Updates van uw [!DNL Salesforce] paginalay-outs
* Migratie voor [!DNL Salesforce] Klassiek naar lichter maken
* Upgrades naar uw [!DNL Marketo Measure] contract
* Controleer of u de meest recente versie van het pakket met aanraakpunten voor kopers hebt geïnstalleerd in [!DNL Salesforce]

>[!NOTE]
>
>Als u het exporteren van gegevens naar Salesforce uitschakelt, worden bestaande gegevens niet verwijderd. Om het te verwijderen, volg de stappen in [&#x200B; dit Salesforce hulpartikel &#x200B;](https://help.salesforce.com/s/articleView?language=en_US&id=sf.c360_a_delete_data_stream_records.htm&type=5){target="_blank"}.

>[!MORELIKETHIS]
>
>* [&#x200B; Update Buyer Touchpoint Package &#x200B;](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-salesforce-package-installation-and-set-up.md)
>* [[!DNL Marketo Measure]  Reeksen van de Toestemming &#x200B;](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-permission-sets.md)
>* [&#x200B; het Delen van de Omslag van Rapporten en van Dashboards &#x200B;](https://help.salesforce.com/s/articleView?language=en_US&id=analytics_share_folder.htm&type=0)
>* [&#x200B; verbind Marketo Measure met Salesforce &#x200B;](/help/configuration-and-setup/marketo-measure-and-salesforce/connect-marketo-measure-to-salesforce.md)
