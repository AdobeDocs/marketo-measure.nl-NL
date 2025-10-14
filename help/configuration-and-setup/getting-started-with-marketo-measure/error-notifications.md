---
description: Foutmeldingen - [!DNL Marketo Measure]
title: Foutmeldingen
feature: Fundamentals
exl-id: ed07eed6-ddeb-4856-a1ac-ea3d571283f6
source-git-commit: 20f886a0c6f448956ad2fda2d21a25f8d9a5a6af
workflow-type: tm+mt
source-wordcount: '1692'
ht-degree: 0%

---

# Foutmeldingen {#error-notifications}

Hieronder volgt een lijst met fouten die u kunt ontvangen via meldingen in de app of e-mail. Als u om het even welk van deze ontvangt, volg de respectieve het oplossen van problemenstappen. Neem contact op met [Marketo-ondersteuning](https://nation.marketo.com/t5/support/ct-p/Support).

Het volledige kennisgevingsbericht weergeven in [!DNL Marketo Measure], klikt u op **Alles weergeven** onder aan het tabblad Meldingen.

![](assets/error-notifications-1.png)

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
      <td>Raadpleeg de volgende documentatie bij Salesforce op <a href="https://help.salesforce.com/s/articleView?language=en_US&id=sf.branded_apps_commun_api_permset.htm&type=5">API-toegang inschakelen</a>.</td>
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
           <img src="assets/error-notifications-2.png">
          </p>
      </td>
    </tr>
    <tr>
      <td>CANNOT_EXECUTE_FLOW_TRIGGER</td>
      <td>Er is een fout opgetreden tijdens de Crm-export: CANNOT_EXECUTE_FLOW_TRIGGER : Type entiteit 'Contact' Geef uw Salesforce-beheerder deze gegevens.
De limiet is overschreden. U of uw organisatie heeft de maximumlimiet voor deze functie overschreden. Fout-id: 123456</td>
      <td>De record kan niet worden opgeslagen omdat deze niet voldoet aan een triggerstroomregel die is ingesteld op de Salesforce org.</td>
      <td>Bekijk de volledige details van het meldingsbericht en bekijk de flowtriggers in de Salesforce org.
Salesforce-documentatie over stroomtriggers <a href="https://admin.salesforce.com/blog/2023/what-is-a-record-triggered-flow#:~:text=A%20record%2Dtriggered%20flow%20allows,is%20created%20and%2For%20updated">hier te vinden</a>.
      </td>
    </tr>
    <tr>
      <td>CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY</td>
      <td>Fout opgetreden tijdens Crm-export: CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY : Type entiteit 'Lead': CRM ErrorCode: CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY, CRM ErrorMessage: System.LimitException: Apex CPU time limit expired, RecordId: 0123456
      <p>
      Fout opgetreden tijdens Crm Export: CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY : Type entiteit 'Account': CRM ErrorCode: CANNOT_INSERT_UPDATE_ACTIVATE_ENTITY, CRM ErrorMessage: entiteitstype kan niet worden bijgewerkt: Account, RecordId: 0123456</td>
      <td>Triggers voorkomen het bijwerken of invoegen van een object.
      <p>
      OF
      <p>
      Ontbrekende machtigingen voor het object.</td>
      <td>Controleer de triggercode waardoor het invoegen/bijwerken mislukt. Raadpleeg de volgende documentatie bij Salesforce voor meer informatie over triggers:
        <ul>
          <li><a href="https://help.salesforce.com/s/articleView?id=sf.code_manage_triggers.htm&type=5">Apex-triggers</a>
          </li>
          <li><a href="https://admin.salesforce.com/blog/2023/what-is-a-record-triggered-flow#:~:text=A%20record%2Dtriggered%20flow%20allows,is%20created%20and%2For%20updated">Stroom triggers</a>
          </li>
        </ul>
        <p>
        Alle benodigde machtigingen aan de <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Marketo Measure-gebruiker</a>.
      </td>
    </tr>
    <tr>
      <td>DUPLICATES_DETECTED</td>
      <td>Er is een fout opgetreden tijdens de Crm-export: DUPLICATES_DETECTED : Type entiteit 'Contact': CRM ErrorCode: DUPLICATES_DETECTED, CRM ErrorMessage: U maakt een gedupliceerde record. We raden u aan een bestaande record te gebruiken., RecordId: 0123456</td>
      <td>De record die wordt geïmporteerd in de Salesforce Org bestaat al.</td>
      <td><a href="https://help.salesforce.com/s/articleView?id=000390009&type=1">De instelling Regel dupliceren uitschakelen</a> om duplicaten toe te staan.
          <p>
          De specifieke Marketo Measure-gebruiker uitsluiten van <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">aangepaste validatieregels</a>.</td>
    </tr>
    <tr>
      <td>DUPLICATE_VALUE</td>
      <td>Fout opgetreden tijdens Crm Export: DUPLICATE_VALUE : Type entiteit 'Lead': CRM ErrorCode: DUPLICATE_VALUE, CRM ErrorMessage: duplicate value found: Email_Unique__c duplicates value on record with id: 123, RecordId: 456</td>
      <td>In het veld dat wordt geïmporteerd in de Salesforce Org zijn geen dubbele waarden toegestaan.</td>
      <td>Schakel het selectievakje <a href="https://help.salesforce.com/s/articleView?id=000390009&type=1">"Uniek selectievakje"</a> in Salesforce.
          <p>
          De specifieke Marketo Measure-gebruiker uitsluiten van <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">aangepaste validatieregels</a>.</td>
    </tr>
    <tr>
      <td>ENTITY_IS_LOCKED</td>
      <td>Fout opgetreden tijdens Crm-export: ENTITY_IS_LOCKED : Type entiteit 'Account': CRM ErrorCode: ENTITY_IS_LOCKED, CRM ErrorMessage: This record is locked. Neem contact op met uw beheerder als u het bestand wilt bewerken. Voer RecordId uit: 0123456</td>
      <td>Wanneer een record zich in een goedkeuringsproces bevindt en een gebruiker die niet de huidige fiatteur of systeembeheerder is, probeert de record te bewerken.</td>
      <td>
        <ul>
          <li>Los het goedkeuringsproces in behandeling voor die record op de Salesforce org op.</li>
          <li>De specifieke Marketo Measure-gebruiker uitsluiten van <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">aangepaste validatieregels</a>.
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>FIELD_FILTER_VALIDATION_EXCEPTION</td>
      <td>Fout opgetreden tijdens Crm-export: FIELD_FILTER_VALIDATION_EXCEPTION: Type entiteit 'Lead': CRM ErrorCode: FIELD_FILTER_VALIDATION_EXCEPTION, Field(s): User__C, CRM ErrorMessage: Value does not exist or not match filter criteria. Selecteer een gebruiker met de rol "Account Executive, Inside Sales"; RecordId: 0123456</td>
      <td>Gewijzigde record voldoet niet meer aan opzoekfilters die op het object zijn gedefinieerd.</td>
      <td>Controleren op filters op het object dat Marketo Measure probeert te wijzigen. Zie <a href="https://help.salesforce.com/s/articleView?id=000384756&type=1">dit Salesforce-artikel</a> om te leren controleren op filters op een object.</td>
    </tr>
    <tr>
      <td>FIELD_INTEGRITY_EXCEPTION</td>
      <td>Er is een fout opgetreden tijdens de Crm-export: FIELD_INTEGRITY_EXCEPTION : Type entiteit 'Lead': CRM ErrorCode: FIELD_INTEGRITY_EXCEPTION, Field(s): Land, CRM ErrorMessage: Er is een probleem met dit land, ook al lijkt het er goed uit. Selecteer een land/gebied in de lijst met geldige landen.: Land, recordId: 0123456</td>
      <td>Het verwachte type record komt niet overeen.</td>
      <td>Het meest voorkomende geval hiervan is dat de in de Salesforce Org vastgestelde naamgevingsnormen voor landen/landen niet worden nageleefd, omdat de velden Staat/Land zijn gestandaardiseerd om alleen bepaalde keuzelijstwaarden te accepteren. U kunt dit probleem oplossen door:
        <ul>
          <li>Werk de record bij volgens de geaccepteerde waarden van de organisatie voor dat veld. Neem contact op met uw SFDC-beheerder om de lijst met toegestane waarden op te halen.</li>
          <li><a href="https://help.salesforce.com/s/articleView?id=sf.admin_state_country_picklist_enable.htm&type=5">Frame/land-picklists uitschakelen</a>.
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>INACTIVE_OWNER_OR_USER</td>
      <td>Fout opgetreden tijdens Crm-export: INACTIVE_OWNER_OR_USER: Type entiteit 'Contact': CRM ErrorCode: INACTIVE_OWNER_OR_USER, CRM-foutmelding: bewerking uitgevoerd met niet-actieve gebruiker [1234] als eigenaar van contact, RecordId: 0123456</td>
      <td>Marketo Measure beschikt niet over de machtiging "Records bijwerken met inactieve eigenaars".</td>
      <td>Marketo Measure de opdracht "<a href="https://help.salesforce.com/s/articleView?id=000386699&type=1">Records bijwerken met inactieve eigenaars</a>" toestemming.</td>
    </tr>
    <tr>
      <td>INSUFFICIENT_ACCESS_OR_READONLY</td>
      <td>Fout opgetreden tijdens Crm-export: INSUFFICIENT_ACCESS_OR_READONLY : Type entiteit 'Account': CRM ErrorCode: INSUFFICIENT_ACCESS_OR_READONLY, CRM ErrorMessage: onvoldoende toegangsrechten voor object-id: [123], RecordId: 456</td>
      <td>Marketo Measure heeft geen machtigingen voor een object/veld of het object is alleen-lezen.</td>
      <td>Raadpleeg het volgende: <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">Artikel Experience League</a> voor richtlijnen over de machtigingen die Marketo Measure vereist.</td>
    </tr>
    <tr>
      <td>INVALID_ADOBE_ANALYTICS_CONFIGURATION</td>
      <td>Er is een fout opgetreden tijdens het exporteren van Adobe Analytics: INVALID_ADOBE_ANALYTICS_CONFIGURATION: Fout: Uploaden niet toegestaan. Bevestig het gegevensbronschema alvorens te uploaden. DataSource-id:1234</td>
      <td>De Adobe Analytics-integratie is niet correct geconfigureerd.</td>
      <td>Raadpleeg de volgende Help-artikelen voor een correcte configuratie:
        <ul>
          <li>
            <a href="/help/marketo-measure-and-adobe/marketo-measure-integrations-with-adobe-analytics.md">Marketo Measure-integratie met Adobe Analytics</a>
          </li>
          <li>
            <a href="https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html?lang=nl-NL">Een bron voor klantkenmerken maken en het gegevensbestand uploaden</a>
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
      <td>In het bronsysteem dat in de kennisgeving is aangegeven (Advertentie, Crm, Marketo), wordt gegarandeerd dat de aan de record gekoppelde valuta een ondersteunde en geldige valuta heeft. Ondersteunde valuta's zijn afgeleid van ISO-valutanormen.</td>
    </tr>
    <tr>
      <td>MISSING_BIZIBLE_CUSTOM_FIELDS_PERMISSIONS</td>
      <td>Fout opgetreden tijdens Crm-export: MISSING_BIZIBLE_CUSTOM_FIELDS_PERMISSIONS : Type entiteit 'Campaign': CRM-foutcode: INVALID_FIELD_FOR_INSERT_UPDATE, Veld(en): bizible2__UniqueId__c, CRM-foutbericht: Kan geen velden maken/bijwerken: bizible2_UniqueId_UniqueId_C Id__c. Controleer de beveiligingsinstellingen van dit veld en controleer of het gelezen/geschreven is voor uw profiel of rechtenset.</td>
      <td>Marketo Measure heeft geen machtigingen voor kwetsbare velden.</td>
      <td>We hebben lees- en schrijfmachtigingen nodig voor alle velden die vooraf zijn ingesteld op "bizible2__". Een volledige lijst van deze velden is te vinden <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">in dit artikel</a>.</td>
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
      <td>MISSING_RECORD_OBJECT_PERMISSIONS</td>
      <td>Fout opgetreden tijdens Crm-export: MISSING_RECORD_OBJECT_PERMISSIONS : Type entiteit 'bizible2__Bizible_Touchpoint__c': CRM-foutcode: INSUFFICIENT_ACCESS_ON_CROSS_REFERENCE_ENTITY, Veld(en): Account, CRM-foutbericht: onvoldoende toegangsrechten voor kruisverwijzing: 01 23456</td>
      <td>Marketo Measure heeft geen machtigingen.</td>
      <td>Er zijn verschillende redenen voor deze fout die specifiek zijn voor de Salesforce org. Hieronder volgen enkele veelvoorkomende stappen voor het oplossen van problemen die het probleem kunnen oplossen:
        <ul>
          <li>Alle machtigingen controleren die voor elke instantie vereist zijn <a href="/help/configuration-and-setup/marketo-measure-and-salesforce/how-marketo-measure-and-salesforce-interact.md">object en veld</a>.</li>
          <li>De specifieke Marketo Measure-gebruiker uitsluiten van <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">aangepaste validatieregels</a>.</li>
          <li>Grant Marketo Measure "<a href="https://developer.salesforce.com/docs/atlas.en-us.securityImplGuide.meta/securityImplGuide/users_profiles_view_all_mod_all.htm">Alles wijzigen</a>" bevoegdheden.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>NULL_EMPTY_CURRENCY_ISO_CODE</td>
      <td>
        <p>
          Er is een fout opgetreden tijdens het importeren van Crm: NULL_EMPTY_CURRENCY_ISO_CODE: ISO-code van valuta is NULL of Leeg wanneer MultiCurrency is ingeschakeld voor RecordId 1234
      </td>
      <td>Valuta moet een ondersteunde ISO-valutacode zijn.</td>
      <td>In het bronsysteem dat in de kennisgeving is aangegeven (Advertentie, Crm, Marketo), wordt gegarandeerd dat de aan de record gekoppelde valuta een ondersteunde en geldige valuta heeft. Ondersteunde valuta's zijn afgeleid van ISO-valutanormen.</td>
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
      <td>RECORD_NONCOMPLIANT_WITH_VALIDATION_RULES</td>
      <td>Fout opgetreden tijdens Crm-export: RECORD_NONCOMPLIANT_WITH_VALIDATION_RULES: Type entiteit 'Lead': CRM ErrorCode: FIELD_CUSTOM_VALIDATION_EXCEPTION, Field(s): Lead_Status_Reason__c, CRM ErrorMessage: You must select the Lead Status Reason, RecordId: 01234 56</td>
      <td>De record die wordt bijgewerkt, voldoet niet aan een validatieregel die is ingesteld op de Salesforce org.</td>
      <td>De specifieke Marketo Measure-gebruiker uitsluiten van <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">aangepaste validatieregels</a>.
      <p>
      Werk uw <a href="https://help.salesforce.com/s/articleView?id=sf.fields_about_field_validation.htm&type=5">validatieregels</a>.</td>
    </tr>
    <tr>
      <td>RESTRICT_PICKLIST_VALUES_ENABLED</td>
      <td>Er is een fout opgetreden tijdens de Crm-export: RESTRICT_PICKLIST_VALUES_ENABLED : Type entiteit 'Campaign': CRM ErrorCode: INVALID_OR_NULL_FOR_RESTRICTED_PICKLIST, Field(s): Areas_of_Interest__c, CRM ErrorMessage: ongeldige waarde voor veld met beperkte keuzelijst: Onbekend</td>
      <td>Wanneer 'De keuzelijst beperken tot de waarden die zijn gedefinieerd in de waardenset' is ingeschakeld in de instelling van het veld keuzelijst of wanneer de waarde die in het veld wordt ingevoegd niet beschikbaar is in het recordtype van het object.</td>
      <td>Schakel de instelling voor de beperkt picklist in de Salesforce Org uit.
          <p>
          De specifieke Marketo Measure-gebruiker uitsluiten van <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">aangepaste validatieregels</a>.
      </td>
    </tr>
    <tr>
      <td>REQUIRED_FIELD_MISSING</td>
      <td>Fout opgetreden tijdens Crm-export: MISSING_REQUIRED_FIELD : Type entiteit 'Lead': CRM ErrorCode: REQUIRED_FIELD_MISSING, Field(s): Product_Type__c, CRM ErrorMessage: Required fields are missing: [Product_Type__c], RecordId: 0123456</td>
      <td>Wanneer een validatieregel velden op objecten vereist.</td>
      <td>De specifieke Marketo Measure-gebruiker uitsluiten van <a href="https://trailhead.salesforce.com/content/learn/modules/validation-rules/bypass-your-validation-rules">aangepaste validatieregels</a>.
      </td>
    </tr>
    <tr>
      <td>UNKNOWN_EXCEPTION</td>
      <td>Fout opgetreden tijdens Crm-export: UNKNOWN_EXCEPTION: Type entiteit 'Contact': CRM ErrorCode: UNKNOWN_EXCEPTION, CRM ErrorMessage: Portal users cannot own partner accounts, RecordId: 0123456</td>
      <td>Er is een niet-afgehandelde uitzondering opgetreden in Salesforce.</td>
      <td>Als het probleem zich blijft voordoen, meldt u een kwestie met Salesforce en kopieert u de numerieke waarden in het foutbericht.</td>
    </tr>
    <tr>
      <td>UNSUPPORTED_CRM_PACKAGE_VERSION</td>
      <td>Er is een fout opgetreden tijdens het importeren van CRM: UNSUPPORTED_CRM_PACKAGE_VERSION: uw crm-pakket bijwerken</td>
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
