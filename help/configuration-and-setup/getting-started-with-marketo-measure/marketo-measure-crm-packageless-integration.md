---
unique-page-id: 37356027
description: '[!DNL Marketo Measure] CRM Packageless Integration -  [!DNL Marketo Measure]'
title: '[!DNL Marketo Measure] CRM Packageless Integration'
exl-id: a4f31d82-63ec-4bb2-bc8b-d3495e61af4f
feature: Integration
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 0%

---

# [!DNL Marketo Measure] CRM Packageless Integration {#marketo-measure-crm-packageless-integration}

Niet alle marketingteams willen (of hebben toegang) marketingrapporten uitvoeren vanuit de CRM, of dit nu komt door beperkte toegang, CRM-eigendom, langere tijd tot waarde of juridische implicaties. Als u het pad van [!DNL Marketo Measure] Snel starten omlaag gaat, hebt u de mogelijkheid om [!DNL Marketo Measure] effectief te implementeren en uit te voeren, waarbij u zo weinig mogelijk afhankelijk bent van de CRM.

## Standaard [!DNL Marketo Measure] installeren {#standard-marketo-measure-installation}

Via de standaardinstallatie van [!DNL Marketo Measure] moet u een [!DNL Salesforce] pakket of een [!DNL Microsoft Dynamics] beheerde oplossing installeren. De installatie bevat aangepaste objecten/entiteiten en aangepaste velden die aan de CRM worden toegevoegd en waarnaar [!DNL Marketo Measure] vervolgens gegevens kan schrijven.

Een pakketloze integratie met [!DNL Marketo Measure] is bedoeld voor klanten die geen aangepaste objecten/entiteiten of aangepaste velden in uw CRM willen maken. Het is ook een goede optie voor klanten die een externe Data Warehouse gebruiken.

## Machtigingen {#permissions}

Voor een [!DNL Marketo Measure] CRM-pakketloze integratie is nog steeds toegang vereist tot standaard CRM-objecten, zoals leads en contactpersonen. Het wordt aanbevolen dat een specifieke gebruiker als de verbonden gebruiker fungeert, aangezien deze over de juiste toegangsrechten voor gegevens beschikt.

Om ervoor te zorgen dat alle gegevens behoorlijk van uw CRM trekken, vereisen wij de volgende veiligheid en toegankelijkheidsmontages: Bekijk Alle Gegevens voor het Profiel van de specifieke gebruiker. Deze rechtenset geeft [!DNL Marketo Measure] de toegang die nodig is om gegevens van standaardobjecten te downloaden. Deze rechtenset bevindt zich op profielniveau.

## Uw identiteitsprovider en gegevensverbindingen instellen {#setup-your-identity-provider-and-data-connections}

Sla in de onderstaande handleidingen de stappen over om het [!DNL Salesforce] -pakket of de [!DNL Microsoft Dynamics] Beheerde oplossing te installeren en volg alleen de machtigingen en integratie-instructies.

[!DNL Salesforce] klanten klik [ hier ](/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-salesforce-package-installation-and-set-up.md).

[!DNL Microsoft Dynamics] klanten klik [ hier ](/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/microsoft-dynamics-crm-installation-guide.md).

Nadat u deze stappen voltooit, zou de integratie operationeel moeten zijn. Als u in om het even welke kwesties loopt, contacteer uw [!DNL Marketo Measure] vertegenwoordiger of [ Steun van Marketo ](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.

>[!NOTE]
>
>Als u begint met de [!DNL Marketo Measure] CRM-pakketloze integratie, kunt u het Salesforce-pakket of Microsoft Dynamics Managed Solution later installeren.
