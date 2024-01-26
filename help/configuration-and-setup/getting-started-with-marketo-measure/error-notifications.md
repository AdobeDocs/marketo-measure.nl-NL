---
description: Foutmeldingen - [!DNL Marketo Measure] - Productdocumentatie
title: Foutmeldingen
feature: Fundamentals
source-git-commit: b7aea1e0789b2f4f3fd4b250c0f66595618317bb
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 0%

---

# Foutmeldingen {#error-notifications}

Hieronder volgt een lijst met fouten die u kunt ontvangen via meldingen in de app of e-mail. Als u een van deze reacties ontvangt, volgt u de desbetreffende stappen voor het oplossen van problemen. Neem contact op met [Marketo-ondersteuning](https://nation.marketo.com/t5/support/ct-p/Support).

<table>
  <tbody>
    <tr>
      <th style="width:31%">Foutcode</th>
      <th style="width:23%">Voorbeeld van melding</th>
      <th style="width:23%">Beschrijving</th>
      <th style="width:23%">Stappen voor probleemoplossing</th>
    </tr>
    <tr>
      <td>API_DISABLED</td>
      <td>Er is een fout opgetreden tijdens het importeren van CRM: API_DISABLED: API-aanroepen zijn uitgeschakeld voor deze gebruiker</td>
      <td>De API-machtiging is uitgeschakeld voor de Marketo Measure-gebruiker.</td>
      <td>Raadpleeg de volgende documentatie bij Salesforce op <a href="https://help.salesforce.com/s/articleView?id=sf.branded_apps_commun_api_permset.htm&amp;type=5">API-toegang inschakelen</a>.</td>
    </tr>
    <tr>
      <td>API_LIMIT_EXCEEDED</td>
      <td>Er is een fout opgetreden tijdens de Crm-export: PI_LIMIT_EXCEEDED</td>
      <td>De API-limiet van de CRM is overschreden (24 uur).</td>
      <td>Raadpleeg de volgende documentatie voor uw CRM voor hulp bij het aanpassen van API-krediettoewijzingen:</p>
          <ul>
            <li><a href="https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/data-entities/service-protection-monitoring">Dynamiek</a>
            </li>
            <li><a href="https://developer.salesforce.com/docs/atlas.en-us.salesforce_app_limits_cheatsheet.meta/salesforce_app_limits_cheatsheet/salesforce_app_limits_platform_api.htm">Salesforce</a>
            </li>
          </ul>
          <p>U kunt de CRM-credits die Marketo Measure gebruikt ook aanpassen door de volgende stappen uit te voeren:</p>
          <ul>
            <li>Navigeren naar <b>Instellingen</b> &gt; <b>CRM</b> &gt; <b>Algemeen</b></li>
            <li>De API-limiet voor dagelijkse CRM bijwerken<br/>
              <ul>
                <li><b>Opmerking: de standaardwaarde is 100.000</b></li>
              </ul>
            </li>
          </ul>
          <p>
           <img src="assets/error-notifications-1.png">
          </p>
      </td>
    </tr>
    <tr>
      <td>INVALID_ADOBE_ANALYTICS_CONFIGURATION</td>
      <td>Er is een fout opgetreden tijdens het exporteren van AdobeAnalytics: INVALID_ADOBE_ANALYTICS_CONFIGURATION: Fout: Uploaden niet toegestaan. Bevestig het schema van de gegevensbron voordat u het uploadt. DataSource-id:1234</td>
      <td>De Adobe Analytics-integratie is niet correct geconfigureerd.</td>
      <td>Raadpleeg de volgende Help-artikelen voor een correcte configuratie:
        <ul>
          <li>
            <a href="/help/marketo-measure-and-adobe/marketo-measure-integrations-with-adobe-analytics.md">Marketo Measure-integratie met Adobe Analytics</a>
          </li>
          <li>
            <a href="https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html">Een bron voor klantkenmerken maken en het gegevensbestand uploaden</a>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>INVALID_CURRENCY_ISO_CODE</td>
      <td>Er is een fout opgetreden tijdens het importeren van de advertentie: INVALID_CURRENCY_ISO_CODE: Valuta XXX wordt niet ondersteund door Marketo Measure.
      <p>
      Er is een fout opgetreden tijdens het importeren van de advertentie: INVALID_CURRENCY_ISO_CODE: Valuta XXX op account voor 1234 wordt niet ondersteund door Marketo Measure.</td>
      <td>Er is een niet-ondersteunde valuta aangetroffen.</td>
      <td>In het bronsysteem dat in de kennisgeving is aangegeven (Advertentie, Crm, Marketo), zorgt u ervoor dat de aan de record gekoppelde valuta een ondersteunde en geldige valuta heeft. Ondersteunde valuta's zijn afgeleid van ISO-valutanormen.</td>
    </tr>
    <tr>
      <td>MISSING_CONVERTED_LEAD_PERMISSION</td>
      <td>Fout opgetreden tijdens Crm-export: MISSING_CONVERTED_LEAD_PERMISSION</td>
      <td>Marketo Measure beschikt niet over de machtiging Omgezette leads weergeven/bewerken</td>
      <td>Raadpleeg het volgende Experience League voor hulp bij het inschakelen van deze machtiging in uw CRM<br/>
          <a href="/help/marketo-measure-salesforce-reporting/additional-functionality/enabling-the-permission-to-edit-converted-leads.md">Toestaan dat de machtiging voor het bewerken van omgezette leads wordt verleend</a></td>
    </tr>
    <tr>
      <td>MISSING_FIELD_READ_PERMISSION</td>
      <td>Fout opgetreden tijdens Crm-import: MISSING_FIELD_READ_PERMISSION : Type entiteit 'Event': INVALID_FIELD:<br/>
    SystemModstamp,isDelette,WhoId,bizible2__Bizible_Touchpoint_Date__c</td>
      <td>Marketo Measure heeft geen leesmachtigingen voor een vereist veld.</td>
      <td>Raadpleeg de volgende Help-artikelen voor richtlijnen over de machtigingen die Marketo Measure vereist:
        <ul>
          <li><a href="/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/marketo-measure-dynamics-schema.md">Dynamiek</a>
          </li>
          <li><a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Salesforce</a>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>MISSING_ISREPLICATEABLE_PERMISSION</td>
      <td>Er is een fout opgetreden tijdens het importeren van CRM: MISSING_ISREPLICATEABLE_PERMISSION: Er ontbreekt een IsReplicate-machtiging voor campagne</td>
      <td>Deze machtiging is vereist voor Salesforce-objecten, zodat we uw Marketo Measure en Salesforce synchroon kunnen houden.</td>
      <td>Neem contact op met de ondersteuning van Salesforce voor hulp en stel de reproduceerbare machtigingen voor objecten in.</td>
    </tr>
    <tr>
      <td>MISSING_OBJECT_READ_PERMISSION</td>
      <td>Fout opgetreden tijdens Crm-import: MISSING_OBJECT_READ_PERMISSION: campagne van het type entiteit': CRM-foutcode: MISSING_PERMISSION</td>
      <td>Marketo Measure heeft geen leesmachtigingen voor een vereist object.</td>
      <td rowspan="2">Raadpleeg de volgende Help-artikelen voor richtlijnen over de machtigingen die Marketo Measure vereist:
          <ul>
            <li><a href="/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/marketo-measure-dynamics-schema.md">Dynamiek</a>
            </li>
            <li><a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Salesforce</a>
            </li>
          </ul>
      </td>
    </tr>
    <tr>
      <td>MISSING_OBJECT_WRITE_PERMISSION</td>
      <td>Fout opgetreden tijdens Crm-export: MISSING_OBJECT_WRITE_PERMISSION : Type entiteit 'bizible2_Bizible_Attribution_Touchpoint': CRM ErrorCode: MISSING_PERMISSION</td>
      <td>Marketo Measure beschikt niet over schrijfmachtigingen voor een vereist object.</td>
    </tr>
    <tr>
      <td>NULL_EMPTY_CURRENCY_ISO_CODE</td>
      <td>
        <p>
          Er is een fout opgetreden tijdens het importeren van Crm: NULL_EMPTY_CURRENCY_ISO_CODE: ISO-code van valuta is NULL of Leeg wanneer MultiCurrency is ingeschakeld voor RecordId 1234
      </td>
      <td>Valuta moet een ondersteunde ISO-valutacode zijn.</td>
      <td>In het bronsysteem dat in de kennisgeving is aangegeven (Advertentie, Crm, Marketo), zorgt u ervoor dat de aan de record gekoppelde valuta een ondersteunde en geldige valuta heeft. Ondersteunde valuta's zijn afgeleid van ISO-valutanormen.</td>
    </tr>
    <tr>
      <td>OPERATION_TOO_LARGE</td>
      <td>Er is een fout opgetreden tijdens het importeren van CRM: OPERATION_TOO_LARGE: We hebben de machtiging 'Alle gegevens weergeven' nodig om activiteiten met succes te kunnen controleren.</td>
      <td>De montages van CRM staan Marketo Measure niet toe om een grote genoeg reeks gegevens te vragen</td>
      <td>Toestaan dat Marketo Measure de machtiging Alle gegevens weergeven heeft voor het opgegeven object.
      <p>
      Meer informatie over de machtiging Alle gegevens weergeven <a href="https://developer.salesforce.com/docs/atlas.en-us.securityImplGuide.meta/securityImplGuide/users_profiles_view_all_mod_all.htm">hier te vinden</a>.</td>
    </tr>
    <tr>
      <td>UNSUPPORTED_CRM_PACKAGE_VERSION</td>
      <td>Er is een fout opgetreden tijdens het importeren van CRM: UNSUPPORTED_CRM_PACKAGE_VERSION: werk het crm-pakket bij</td>
      <td>Het huidige gevonden pakket wordt niet meer ondersteund.</td>
      <td>Voer een upgrade uit op uw pakket naar de meest recente versie:
        <ul>
          <li><a href="/help/configuration-and-setup/marketo-measure-and-salesforce/best-practices-for-marketo-measure-crm-package.md">Aanbevolen procedures</a>
          </li>
          <li><a href="/help/marketo-measure-and-dynamics/getting-started-with-marketo-measure-and-dynamics/microsoft-dynamics-crm-installation-guide.md">Dynamiek</a>
          </li>
          <li><a href="/help/configuration-and-setup/marketo-measure-and-salesforce/marketo-measure-salesforce-package-installation-and-set-up.md">Salesforce</a>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>
