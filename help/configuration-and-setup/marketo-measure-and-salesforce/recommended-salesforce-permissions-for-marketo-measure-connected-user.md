---
unique-page-id: 18874696
description: Aanbevolen [!DNL Salesforce] Rechten voor [!DNL Marketo Measure] Verbonden gebruiker - [!DNL Marketo Measure]
title: Aanbevolen [!DNL Salesforce] Rechten voor [!DNL Marketo Measure] Verbonden gebruiker
exl-id: b74aa28b-4a7b-42d1-8df0-d1ae0ff1f338
feature: Salesforce
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 0%

---

# Aanbevolen [!DNL Salesforce] Rechten voor [!DNL Marketo Measure] Verbonden gebruiker {#recommended-salesforce-permissions-for-marketo-measure-connected-user}

[!DNL Marketo Measure] verzendt en ontvangt gegevens door verbonden [!DNL Salesforce] binnen de [!DNL Marketo Measure] app.

Om aanraakpuntgegevens naar uw [!DNL Salesforce] -instantie, moet de verbonden gebruiker toegang hebben tot [!DNL Marketo Measure] aangepaste objecten (aanraakpunt koper en aanraakpunt koper) en standaard [!DNL Salesforce] objecten zoals regelafstand en contactpersonen. Zie [[!DNL Marketo Measure] in Salesforce](/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md).

[!DNL Salesforce] Beheerdersgebruikerslicenties kunnen fungeren als de verbonden gebruiker, omdat deze standaard vaak over de benodigde gegevensrechten beschikt. Uw team kan echter de voorkeur geven aan een integratiegebruiker of een toegewijde [!DNL Salesforce] gebruikerslicentie om de impact van [!DNL Marketo Measure] op uw exemplaar.

We raden de volgende machtigingen aan om ervoor te zorgen dat [!DNL Marketo Measure] de gegevens vloeien correct:

* [!DNL Marketo Measure] Beheerdersmachtigingen ingesteld voor specifieke gebruiker

De beheerde rechtenset geeft een SFDC-beheerder de mogelijkheid om records te maken, lezen, schrijven, verwijderen uit [!DNL Marketo Measure] objecten.

* Toestemmingsset voor omgezette leads weergeven en bewerken

Dit maakt [!DNL Marketo Measure] om leidingen te versieren nadat ze zijn omgezet in contacten. Als deze rechtenset niet is ingeschakeld, kunnen er belangrijke hiaten in het bijhouden van gegevens zijn. Meer informatie vindt u in [[!DNL Salesforce Trailblazer] gemeenschap](https://help.salesforce.com/s/articleView?language=en_US&amp;id=leads_view_edit_converted.htm&amp;type=5).

* [!DNL Salesforce] Selectievakje voor marketinggebruiker

De [!UICONTROL Marketing User] Met het selectievakje kan de gebruiker campagnes maken en de wizard Campagne importeren gebruiken. Als deze optie niet is geselecteerd, kan de gebruiker alleen campagnes en geavanceerde campagneopstelling weergeven, de Campagnegeschiedenis voor één enkele lead of contactpersoon bewerken en campagnerapporten uitvoeren. [!DNL Marketo Measure] moet het campagneobject kunnen lezen en schrijven.

**Extra probleemoplossing**

Indien [!DNL Marketo Measure] Er zijn nog steeds problemen met het lezen of schrijven van gegevens. Het kan handig zijn het volgende te onderzoeken:

* Toegang tot [!DNL Salesforce] Queues

Als de specifieke gebruiker geen toegang tot lood in rijen heeft, dan kan het niet de lood wijzigen met [!DNL Marketo Measure] gegevens. U kunt dit bereiken door een rol in de hiërarchie te hebben die toegang tot rijen of individueel het verlenen van gebruikerstoegang toestaat.

* Beveiliging en toegankelijkheid op veldniveau

De veiligheid van het gebiedsniveau en gebiedstoegankelijkheid zijn verwant maar hebben sommige zeer belangrijke verschillen. De Veiligheid van het Niveau van het gebied bepaalt gebiedszicht voor een bepaald profiel terwijl de Toegankelijkheid van het Gebied bepaalt of een gebied op de veiligheid van het gebiedsniveau en de configuratie van de paginalay-out editable is. Met de [!DNL Marketo Measure] de de toestemmingsreeksen van het pakket u de noodzakelijke de veiligheidsmontages van het veldobject ontvangt. Soms moet de verbonden gebruiker, om de juiste veldtoegankelijkheid te hebben, over de [!DNL Marketo Measure] velden op de paginalay-outs. [!DNL Marketo Measure] de velden in de lay-out zijn geschikt voor de [!DNL Marketo Measure] gegevens die moeten worden toegewezen [!DNL Salesforce]. Dit hangt van uw bepaald af [!DNL Salesforce] milieu.

Elke organisatie [!DNL Salesforce] heeft individuele behoeften, maar wij stellen u van onze vereisten in evenwicht [!DNL Marketo Measure] hebt toegang nodig met uw beveiligingsprotocollen. Niet aarzelen om naar [[!DNL Marketo Support]](https://nation.marketo.com/t5/support/ct-p/Support){target="_blank"}.
