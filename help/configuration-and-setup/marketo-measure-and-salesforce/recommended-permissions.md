---
description: Geadviseerde  [!DNL Salesforce]  Toestemmingen voor  [!DNL Marketo Measure]  Verbonden Gebruiker -  [!DNL Marketo Measure]
title: Geadviseerde  [!DNL Salesforce]  Toestemmingen voor  [!DNL Marketo Measure]  Verbonden Gebruiker
exl-id: b74aa28b-4a7b-42d1-8df0-d1ae0ff1f338
feature: Salesforce
source-git-commit: c6090ce0c3ac60cd68b1057c369ce0b3b20aeeee
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 0%

---


# Aanbevolen [!DNL Salesforce] machtigingen voor [!DNL Marketo Measure] verbonden gebruiker {#recommended-salesforce-permissions-for-marketo-measure-connected-user}

[!DNL Marketo Measure] verzendt en ontvangt gegevens via een verbonden [!DNL Salesforce] -gebruiker in de [!DNL Marketo Measure] -app.

Als u aanraakpuntgegevens naar uw [!DNL Salesforce] -instantie wilt verzenden, moet de verbonden gebruiker toegang hebben tot [!DNL Marketo Measure] aangepaste objecten (Buyer Touchpoint en Buyer Attribution Touchpoint) en tot standaard [!DNL Salesforce] -objecten zoals Leads en Contacten. Zie [[!DNL Marketo Measure]  in Salesforce ](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md).

[!DNL Salesforce] Beheerderslicenties kunnen fungeren als de verbonden gebruiker, omdat deze standaard vaak over de benodigde gegevensrechten beschikt. Uw team kan er echter de voorkeur aan geven een integratiegebruiker of een toegewijde [!DNL Salesforce] -gebruikerslicentie te gebruiken om de impact van [!DNL Marketo Measure] op uw instantie te volgen.

We raden de volgende machtigingen aan om ervoor te zorgen dat [!DNL Marketo Measure] -gegevens correct worden verzonden:

* [!DNL Marketo Measure] Beheerdermachtigingen ingesteld voor specifieke gebruiker

Met de beheerde rechtenset kan een SFDC-beheerder records maken, lezen, schrijven, verwijderen uit [!DNL Marketo Measure] -objecten.

* Toestemmingsset voor omgezette leads weergeven en bewerken

Hierdoor kan [!DNL Marketo Measure] leads decoreren nadat deze zijn omgezet in contactpersonen. Als deze rechtenset niet is ingeschakeld, kunnen er belangrijke hiaten in het bijhouden van gegevens zijn. U kunt meer informatie in [[!DNL Salesforce Trailblazer]  gemeenschap ](https://help.salesforce.com/s/articleView?language=en_US&id=leads_view_edit_converted.htm&type=5) vinden.

* [!DNL Salesforce] Selectievakje voor marketinggebruiker

Met het selectievakje [!UICONTROL Marketing User] kan de gebruiker campagnes maken en de wizard Campagne importeren gebruiken. Als deze optie niet is geselecteerd, kan de gebruiker alleen campagnes en geavanceerde campagneopstelling weergeven, de Campagnegeschiedenis voor één enkele lead of contactpersoon bewerken en campagnerapporten uitvoeren. [!DNL Marketo Measure] moet het campagneobject kunnen lezen en schrijven.

**Extra het Oplossen van problemen**

Als er in [!DNL Marketo Measure] nog steeds problemen optreden bij het lezen of schrijven van gegevens, kan het nuttig zijn het volgende te onderzoeken:

* Toegang tot [!DNL Salesforce] wachtrijen

Als de toegewezen gebruiker geen toegang heeft tot leads in wachtrijen, kan de gebruiker de leads niet wijzigen met [!DNL Marketo Measure] -gegevens. U kunt dit bereiken door een rol in de hiërarchie te hebben die toegang tot rijen of individueel het verlenen van gebruikerstoegang toestaat.

* Beveiliging en toegankelijkheid op veldniveau

De veiligheid van het gebiedsniveau en gebiedstoegankelijkheid zijn verwant maar hebben sommige zeer belangrijke verschillen. De Veiligheid van het Niveau van het gebied bepaalt gebiedszicht voor een bepaald profiel terwijl de Toegankelijkheid van het Gebied bepaalt of een gebied op de veiligheid van het gebiedsniveau en de configuratie van de paginalay-out editable is. Met de machtigingssets van het pakket [!DNL Marketo Measure] ontvangt u de benodigde beveiligingsinstellingen voor veldobjecten. Soms moet de verbonden gebruiker de [!DNL Marketo Measure] -velden op de paginalay-outs hebben om de juiste toegankelijkheid van de velden te hebben. Met [!DNL Marketo Measure] -velden in de layout kunnen de [!DNL Marketo Measure] -gegevens worden toegewezen aan [!DNL Salesforce] . Dit is afhankelijk van uw specifieke [!DNL Salesforce] -omgeving.

De [!DNL Salesforce] van elke organisatie heeft individuele behoeften maar wij voorzien u van onze vereisten om de [!DNL Marketo Measure] toegangsbehoeften met uw veiligheidsprotocollen in evenwicht te brengen. Aarzel niet om uit te reiken aan [[!DNL Marketo Support] ](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
