---
description: Overzicht van integratierechten - [!DNL Marketo Measure]
title: Overzicht van integratierechten
feature: APIs, Integration
exl-id: c45598fe-0c33-459a-9fde-de7f6906bd0c
source-git-commit: 666812e8bf095170d611cd694b5d0ac5151d8fdd
workflow-type: tm+mt
source-wordcount: '1286'
ht-degree: 1%

---

# Overzicht van integratierechten {#integration-permissions-overview}

In deze handleiding worden de benodigde machtigingen beschreven voor naadloze integratie met Marketo Measure, zodat elke integratie effectief en probleemloos werkt.

<table>
<thead>
  <tr>
    <th style="width:10%">Integratie</th>
    <th style="width:25%">Gegevenstype
    <li>Interactiegegevens web</li>
    <li>B2B-systeemgegevens</li>
    <li>Platformgegevens toevoegen</li></th>
    <th style="width:25%">Wat we bijhouden</th>
    <th style="width:40%">Machtigingsvereisten</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Salesforce</td>
    <td>B2B-systeemgegevens    
</td>
    <td>Marketo Measure volgt:
    <p>
    <li>Account</li>
    <li>Campaign</li>
    <li>CampaignMember</li>
    <li>Contact</li>
    <li>CurrencyConversionRange</li>
    <li>CurrencyStatus</li>
    <li>Gebeurtenissen</li>
    <li>FieldHistory (lead, contact en opportunity)</li>
    <li>Lood</li>
    <li>Kans</li>
    <li>OpportunityContactRole</li>
    <li>OpportunityHistory</li>
    <li>Taken</li>
<p>
Aanraakpunten en andere gegevens worden in aangepaste, bizible velden geschreven op account, campagne, CampaignMember, case, contact, lead en opportunity.</td>
    <td><b> Salesforce Verbonden (vereiste) Vergunning van de Gebruiker </b>
    <p>
    <b> de Toestemming van de Beheerder van Marketo Measure die voor Specifieke Gebruiker wordt geplaatst:</b> staat SFDC admin toe om verrichtingen CRUD op markt uit te voeren om voorwerpen te meten.
    <br>
    <b> Mening en geef Omgezette Reeks van de Toestemming van Leads uit:</b> dit staat Marketo Measure toe om lood te versieren nadat zij in contacten zijn omgezet.
    <br>
    <b> de Checkbox van de Gebruiker van de Marketing van Salesforce:</b> checkbox van de Gebruiker van de Marketing staat gebruikers toe om campagnes tot stand te brengen en de Tovenaars van de Invoer van de Campagne te gebruiken.
    <br>
    <b> StandaardGebruiker van Marketo Measure:</b> geeft een gebruiker de capaciteit om verslagen van de voorwerpen van Marketo Measure te lezen.
    <p>
    <b> Salesforce Standaard de Toestemmingen van het Gebied </b>
    <br>
    <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md"> Salesforce standaardobjecten en toegang </a>
    <p>
    <b> de Toestemmingen van het Gebied van de Douane van Salesforce </b>
    <br>
    Wij verstrekken eigenschapmontages om de gebieden van de douaneverkoop te houden die de klanten kunnen gebruiken. Als deze eigenschapmontages dan worden bepaald hebben wij LEZEN toegang tot elk van de verkoopkrachtgebieden nodig die in het eigenschapplaatsen worden bewaard (b.v., als de het plaatsen waarde van CustomLeadSourceField aan "LeadSource__c"gelijk is dan vereisen wij LEZEN toegang tot dit gebied).
    </td>
  </tr>
  <tr>
    <td>Dynamiek</td>
    <td>B2B-systeemgegevens</td>
    <td>Marketo Measure volgt:
    <p>
    <li>Account
<li>ActivityParty
<li>ActivityPointer
<li>Campaign
<li>CampaignItem (CampaignList in ons systeem)
<li>CampaignResponse (CampaignMember in ons systeem)
<li>Contact
<li>Lood
<li>Lijst (MarketingList in ons systeem)
<li>ListMember (MarketingListMember in ons systeem)
<li>Kans
<li>Organisatie
<li>TransactionCurrency (CurrencyConversionRange en CurrencyStatus in ons systeem)
<li>Benoeming, CampaignActivity, E-mail, Fax, IncidentResolution, Letter, PhoneCall, RecurringAppointmentMaster, ServiceAppointment, Task
<li>bizible2_bizible_abtest
<li>bizible2_bizible_attribution_touchpoint
<li>bizible2_bizible_event
<li>bizible2_bizible_history
<li>bizible2_bizible_touchpoint
<p>
Aanraakpunten die zijn gemaakt en andere gegevens worden geschreven naar aangepaste bizible-velden op account, campagne, CampagneResponse, Contact, Lead, List, Opportunity en PhoneCall</td>
    <td><b> de Toestemmingen van de Gebruiker van Marketo Measure </b>
<br>
We raden u aan een speciale Marketo Measure-gebruiker in Dynamics te maken, zodat we gegevens kunnen exporteren en importeren om problemen met andere gebruikers in uw CRM te voorkomen. Neem nota van de gebruikersbenaming en het wachtwoord evenals het eindpunt URL aangezien dit zal worden gebruikt wanneer het creëren van de rekening van Marketo Measure.
<p>
<b> Rollen van de Veiligheid </b>
<br>
Als uw organisatie Dynamische veiligheidsrollen gebruikt, zorg ervoor de verbonden gebruiker, of de specifieke Gebruiker van Marketo Measure voldoende lees-schrijf toestemmingen aan de vereiste entiteiten heeft.
<br>
Beveiligingsrollen bevinden zich hier: Instellingen &gt; Beveiliging &gt; Beveiligingsrollen
<br>
Voor aangepaste Marketo Measure-entiteiten hebben we volledige machtigingen voor al onze entiteiten nodig.
<p>
<b> de StandaardToestemmingen van het Gebied van de Dynamiek 0} {
</b>
<br> het Schema van de Dynamica van Marketo Measure <a href="/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/marketo-measure-dynamics-schema.md"></a>
<p>
<b> de Toestemmingen van het Gebied van de Douane van 0} Dynamiek
</b>
Wij hebben LEZEN toegang voor om het even welk gebied op de Leiding of entiteit van het Contact nodig die de klant voor de regels van de Montages van de Douane wil gebruiken onderdrukken/verwijderen Touchpoint.
<br>
<br>
Wij hebben LEZEN toegang voor om het even welk gebied op de LEIDING of entiteit van de Kans nodig die de klant voor de regels van het Segment of de Afbeelding van het Stadium wil gebruiken.
<br>
Wij hebben LEZEN toegang voor om het even welk gebied op de Campagne, CampaignResponse, en de entiteiten van de Lijst nodig die de klant voor het Syncen Campagne/MarketingList leden wil gebruiken.
</td>
  </tr>
  <tr>
    <td>Facebook</td>
    <td>Platformgegevens toevoegen</td>
    <td>We integreren met Facebook in:
<p>
<li>Klantenadvertenties importeren</li>
<li>Klantenadvertenties importeren</li>
<li>Clientadvertenties bijwerken door URL-parameters toe te voegen</li>
<p>
Marketo Measure volgt accounts, campagnes, advertentiegroepen, advertenties, filter-id's en URL's.</td>
    <td><li>De machtiging ads_management is vereist voor het maken van campagnes, het beheren van advertenties of het ophalen van Advertentiemetriek.</li>
<li>De e-mailmachtiging is vereist om gebruikers toe te staan zich aan te melden bij Facebook.</li>
<p>
<b> Scopes </b>
<br>
<a href="https://developers.facebook.com/docs/permissions/reference/ads_management/"> ads_management </a>
<br>
<li>Maak programmatisch campagnes, beheer advertenties en haal metriek op.</li>
<li>Stel hulpmiddelen voor advertentiebeheer samen die innovatieve oplossingen en gedifferentieerde waarde voor adverteerders bieden.</li>
<br>
<br>
<a href="https://developers.facebook.com/docs/permissions/reference/email"> e-mail </a>
<br>
<li>Communiceren met mensen en ze laten zich aanmelden bij uw app met het e-mailadres dat is gekoppeld aan hun Facebook-profiel.</li></td>
  </tr>
  <tr>
    <td>LinkedIn</td>
    <td>Platformgegevens toevoegen
    <p>
    B2B-systeemgegevens (lead Gen-formuliergegevens, inclusief formulieren en inzendingen, die zijn gecategoriseerd als CRM-activiteit).</td>
    <td>Marketo Measure volgt LinkedIn-advertenties, Creative, kostengegevens en lead Gen Forms en reacties. Op basis van geïmporteerde gegevens kunnen we LinkedIn-aanraakpunten genereren en reacties op leads koppelen aan klanten.</td>
    <td><li>Voor Marketo Measure is de rol Campagnebeheer of Accountmanager vereist om kostengegevens te downloaden. (Toepassingsgebied, rij 1)</li>
    <br>
    <li>Super Admin (Page Admin Role, Scopes row 2) of Lead Gen Forms Manager (Paid Media Admin Role, Scopes row 3) is vereist voor Marketo Measure om toegang te krijgen tot de gegevens van het loodgen-formulier</li>
    <br>
    <li>Super Admin (de Rol van het Admin van de Pagina, Scopes rij 2) of Gesponsorde Poster van de Inhoud (Betaalde Rol van Media Admin, Scopes row 3) wordt vereist voor Marketo Measure om auto het etiketteren te manipuleren</li>
    <p>
    <b> Scopes </b>
    <br>
    <a href="https://www.linkedin.com/campaignmanager/accounts"> de gebruikersrol van de opstelling in portaal (vereist login aan LinkedIn rekening) </a> - <a href="https://www.linkedin.com/help/lms/answer/a425731/user-roles-and-functions-in-campaign-manager"> het Overzicht van Rollen van de Gebruiker </a>: De rol van de gebruiker, mening en beheert gebruikerstoestemming, wijs rollen zoals rekeningsmanager of campagnemanager toe
    <p>
    <a href="https://www.linkedin.com/help/linkedin/answer/a570172/add-or-remove-admins-on-your-showcase-page?lang=en"> de Rol van Admin van de Pagina van de opstelling - <a href="https://www.linkedin.com/help/linkedin/answer/a541981/linkedin-page-admin-roles-overview"> Definities van de Rol van Admin van de Pagina </a>: De rol van Admin van de pagina, op de gewenste admin pagina
    <p>
    <a href="https://www.linkedin.com/help/linkedin/answer/a570172/add-or-remove-admins-on-your-showcase-page?lang=en"> Opstelling de Betaalde Rol van Media Admin (zoek Betaalde Media Admin) - <a href="https://www.linkedin.com/help/linkedin/answer/a554540"> Betaalde Definities van Media Admin </a>: Betaalde Rollen van Media Admin</td>
  </tr>
  <tr>
    <td>DoubleClick</td>
    <td>Platformgegevens toevoegen</td>
    <td>Marketo Measure volgt accounts, adverteerders, campagnes, (aangepaste) bestemmingspagina's, advertenties, Creative Sites, Placements en Sites.</td>
    <td><li>Het primaire e-mailadres van de Google-account van de gebruiker is vereist</li>
<li>De toestemmingen van de Manager van de campagne die worden vereist om tot Manager 360 van de Campagne rekening toegang te hebben</li>
<ul>
<li>Dubbelklikadvertenties weergeven en beheren</li>
<li>Weergave- en campagnes voor het beheren van Double Click Campaign Manager</li>
<p>
    <b> Scopes </b>
    <br>
    <a href="https://www.googleapis.com/auth/userinfo.email"> https://www.googleapis.com/auth/userinfo.email </a>: Zie uw primaire e-mailadres van de Rekening van Google
    <p>
     <a href="https://www.googleapis.com/auth/dfareporting"> https://www.googleapis.com/auth/dfareporting </a>: Mening en beheer DoubleClick voor Advertisers- rapporten
    <p>
     <a href="https://www.googleapis.com/auth/dfatrafficking"> https://www.googleapis.com/auth/dfatrafficking </a>: Bekijk en beheer uw de vertonings en campagnes van de Manager van de Campagne van de Campagne van DoubleClick (DCM)</td>
  </tr>
  <tr>
    <td>AdWords</td>
    <td>Platformgegevens toevoegen</td>
    <td>We integreren met Advertentie-woorden in:
<p>
<li>Klantenadvertenties importeren</li>
<li>Klantenadvertenties importeren</li>
<li>Clientadvertenties bijwerken door URL-parameters toe te voegen/URL-trackingsjablonen bij te werken</li>
<p>
Marketo Measure volgt campagnes, ad-hocgroepen, Creative Cloud, Site Links en Trefwoorden.</td>
    <td><li>Het primaire e-mailadres van de Google-account van de gebruiker is vereist</li>
<p>
    <b> Scopes </b>
    <br>
    <a href="https://www.googleapis.com/auth/userinfo.email"> https://www.googleapis.com/auth/userinfo.email </a>: Zie uw primaire e-mailadres van de Rekening van Google</td>
  </tr>
  <tr>
    <td>Bing</td>
    <td>Platformgegevens toevoegen</td>
    <td>Marketo Measure volgt accounts, campagnes, advertentiegroepen, creatieve projecten en trefwoorden.</td>
    <td><li>De gebruiker moet "off-line toegang"via hun Rekening van Microsoft verlenen (wat Marketo Measure toegang tot de Gebruiker van het Eind verleent - gebruikerInfo zelfs wanneer niet het programma geopend). Zie <a href="https://learn.microsoft.com/en-us/deployoffice/overview-extended-offline-access"> Microsoft pagina </a> op hoe te om dit te doen.</li>
<p>
    <b> Scopes </b>
    <br>
    <a href="https://learn.microsoft.com/en-us/deployoffice/overview-extended-offline-access"> https://learn.microsoft.com/en-us/deployoffice/overview-extended-offline-access </a>: handhaaf toegang tot gegevens u het toegang tot toestemming hebt verleend.</td>
  </tr>
  <tr>
    <td>Marketo Engage</td>
    <td>B2B-systeemgegevens</td>
    <td>Dankzij de Marketo-integratie kan Marketo Measure Marketo-activiteiten, -mensen, -programma's en -programmamakers verzamelen. Bovendien, volgt Marketo Measure de koekjes van Marketo (Munchkin IDs) voor het verbinden van het Webactiviteiten van Marketo met Marketo Measure loodtouchpoints, <a href="/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/marketo-engage-programs-integration.md#cookie-mapping"> zoals hier beschreven </a>:
    <p>
    <i> als resultaat van de integratie van Marketo Measure met Marketo, wordt Marketo Measure Cookie ID nu in kaart gebracht en gesynchroniseerd met Marketo Munchkin Id. Dit helpt de hiaat te sluiten om de anonieme eerste aanraking aan een Webzitting eerder dan het toeschrijven van zowel FT als LC aan een Activiteit van Marketo toe te schrijven.</i>
    </td>
    <td>De klant moet een speciale Marketo Engage API-gebruiker maken en de referenties aan Marketo Measure leveren. Er is geen configuratie met extra machtigingen vereist. <a href="/help/marketo-measure-and-marketo/marketo-measure-integrations-with-marketo/set-up-marketo-connection.md#configuring-the-integration"> leer meer </a>.</td>
  </tr>
  <tr>
    <td>Adobe Analytics</td>
    <td>B2B-systeemgegevens</td>
    <td>Dankzij de integratie van B2B-klantkenmerken kunnen wederzijdse gebruikers van Marketo Measure en Adobe Analytics hun Adobe Analytics-gebruikersprofielen verrijken met waardevolle metagegevens die zijn afgeleid van de Marketo Measure-toewijzingsengine en via de synchronisatiefunctie met CRM's (Microsoft Dynamics en Salesforce). <a href="/help/marketo-measure-and-adobe/marketo-measure-integrations-with-adobe-analytics.md"> leer meer </a>.</td>
    <td>De klant moet Marketo Measure een alias-id en FTP-serverreferenties verstrekken op een locatie waar de gegevens naar de instantie Analytics worden geüpload.
    <p>
    Neem nota van de volgende informatie, aangezien u het voor enkele recentere stappen in het proces zult nodig hebben:
    <p>
    <li>De alias-id. Dit kan elke gewenste waarde zijn. We raden 'marketeasure_id' aan</li>
    <li>De hostnaam en referenties van de FTP-server (gebruikersnaam en wachtwoord)</li>
    <p>
    <a href="/help/marketo-measure-and-adobe/marketo-measure-integrations-with-adobe-analytics.md#configuring-the-integration">Meer informatie</a></td>
  </tr>
  <tr>
    <td>Bizible Javascript</td>
    <td></td>
    <td><a href="/help/marketo-measure-tracking/setting-up-tracking/data-collected-by-javascript.md"> Welke gegevens bizible.js verzamelt </a>.</td>
    <td></td>
  </tr>
</tbody>
</table>

>[!MORELIKETHIS]
>
>[ Meldingen van de Fout ](/help/configuration-and-setup/getting-started-with-marketo-measure/error-notifications.md){target="_blank"}
