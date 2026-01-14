---
description: '''[!DNL Marketo Measure] Vereiste voor Ultimate-gegevensintegriteit - [!DNL Marketo Measure]'''
title: '[!DNL Marketo Measure] Vereiste voor Ultimate-gegevensintegriteit'
feature: Integration, Tracking, Attribution
exl-id: 8ad001d0-e9fe-46f5-b808-d6203a55a229
source-git-commit: fcd8e276c85669ddf12bd7404fb12d3e99b2642a
workflow-type: tm+mt
source-wordcount: '1610'
ht-degree: 7%

---


# [!DNL Marketo Measure] Vereiste voor Ultimate-gegevensintegriteit {#marketo-measure-ultimate-data-integrity-requirement}

[!DNL Marketo Measure] valideert de binnenkomende AEP-gegevenssets om ervoor te zorgen dat de gegevens toereikend en consistent zijn voor toewijzing. Als niet wordt voldaan aan de gegevensintegriteitsvereiste, wordt de gegevensset afgewezen door het [!DNL Marketo Measure] -systeem. Dit artikel detailleert de vereiste van de gegevensintegriteit, verstrekt vraagvoorbeelden voor gegevensinspectie, en adviseert een oplossing voor vereiste gebieden met een ongeldige waarde.

## Object Entiteit {#entity-object}

<table style="table-layout:auto">
  <tr>
    <th>XDM-klasse</th>
    <th>XDM-veldgroep</th>
    <th>XDM-pad</th>
    <th>XDM-type</th>
    <th>Source-veld voor gegevens</th>
    <th>Vereist?</th>
    <th>Notities</th>
  </tr>
  <tbody>
    <tr>
      <td colspan="7"><strong> Rekening </strong> (Rekening voor Salesforce, Bedrijf en/of Benoemde Rekening voor Marketo)</td>
    </tr>
    <tr>
      <td rowspan="6">XDM Business Account</td>
      <td></td>
      <td>accountKey.sourceKey</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld: 123@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceID</td>
      <td>string</td>
      <td>ID</td>
      <td>Ja</td>
      <td>Bijvoorbeeld - 123</td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceInstanceID</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld - 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceType</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld - Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>date-time</td>
      <td>CreatedDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>date-time</td>
      <td>ModifiedDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>XDM-bedrijfsaccountgegevens</td>
      <td>accountName</td>
      <td>string</td>
      <td>Naam</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td colspan="7"><strong> Campagne </strong> (Campagne voor Salesforce, Programma voor Marketo)</td>
    </tr>
    <tr>
      <td rowspan="8">XDM Business Campaign</td>
      <td></td>
      <td>campaignKey.sourceKey</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld: 55555@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceID</td>
      <td>string</td>
      <td>ID</td>
      <td>Ja</td>
      <td>Bijvoorbeeld - 55555</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceInstanceID</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld - 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceType</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld - Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>date-time</td>
      <td>CreatedDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>date-time</td>
      <td>ModifiedDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>campagneName</td>
      <td>string</td>
      <td>Naam</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>campagneType</td>
      <td>string</td>
      <td>CampaignType</td>
      <td>Nee</td>
      <td>Voor kanaaltoewijzing</td>
    </tr>
    <tr>
      <td></td>
      <td rowspan="5">XDM Business Campaign - details</td>
      <td>channelName</td>
      <td>string</td>
      <td>ChannelName</td>
      <td>Nee</td>
      <td>Voor kanaaltoewijzing</td>
    </tr>
    <tr>
      <td></td>
      <td>campagneStartDate</td>
      <td>date-time</td>
      <td>StartDate</td>
      <td>Nee</td>
      <td>Voor campagnekosten</td>
    </tr>
    <tr>
      <td></td>
      <td>campagneEndDate</td>
      <td>date-time</td>
      <td>EndDate</td>
      <td>Nee</td>
      <td>Voor campagnekosten</td>
    </tr>
    <tr>
      <td></td>
      <td>actualCost.amount</td>
      <td>getal</td>
      <td>Kosten</td>
      <td>Nee</td>
      <td>Voor campagnekosten</td>
    </tr>
    <tr>
      <td></td>
      <td>actualCost.currencyCode</td>
      <td>
        <p>string</p>
        <p>^[A-Z]{3}$</p>
      </td>
      <td>CurrencyIsoCode</td>
      <td>Nee</td>
      <td>Voor campagnekosten</td>
    </tr>
    <tr>
      <td colspan="7"><strong> Lid van de Campagne </strong> (Lid van de Campagne voor Salesforce, Lidmaatschappen van het Programma voor Marketo)</td>
    </tr>
    <tr>
      <td rowspan="14">XDM Business Campaign-leden</td>
      <td></td>
      <td>campaignMemberKey.sourceKey</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld: 987654321@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignMemberKey.sourceID</td>
      <td>string</td>
      <td>ID</td>
      <td>Ja</td>
      <td>Bijvoorbeeld - 987654321</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignMemberKey.sourceInstanceID</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld - 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignMemberKey.sourceType</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld - Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>date-time</td>
      <td>CreatedDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>date-time</td>
      <td>ModifiedDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceKey</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld: 333@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceID</td>
      <td>string</td>
      <td>ID lead of contactpersoon</td>
      <td>Ja</td>
      <td>
        <p>Bijvoorbeeld - 333, afhankelijk van de gegevensbronlijst, is dit of Lood identiteitskaart of identiteitskaart van het Contact</p>
        <p>Externe sleutel naar lead of contact</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceInstanceID</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld - 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceType</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld - Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceKey</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld: 55555@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceID</td>
      <td>string</td>
      <td>Campagne-id</td>
      <td>Ja</td>
      <td>
        <p>Bijvoorbeeld - 55555.</p>
        <p>Externe sleutel voor campagne</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceInstanceID</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld - 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>campaignKey.sourceType</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld - Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td rowspan="4">XDM Business Campagne Member Details</td>
      <td>b2b.personType</td>
      <td>string</td>
      <td>"Lead" of "Contact"</td>
      <td>Ja</td>
      <td>Afhankelijk van de gegevensbronlijst, zou dit aan of "Lood"of "Contact"moeten worden geplaatst. We raden u aan deze instelling in te stellen op "Contact" voor de meeste gevallen</td>
    </tr>
    <tr>
      <td></td>
      <td>memberStatus</td>
      <td>string</td>
      <td>Status</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>hasResponded</td>
      <td>boolean</td>
      <td>HasResponded</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>firstRespondedDate</td>
      <td>date-time</td>
      <td>FirstRespondedDate</td>
      <td>Nee</td>
      <td></td>
    </tr>
    <tr>
      <td colspan="7"><strong> Persoon </strong> (Contact of Lood voor Salesforce, Personen voor Marketo)</td>
    </tr>
    <tr>
      <td>Afzonderlijk XDM-profiel</td>
      <td rowspan="11">XDM Business Person - Gegevens</td>
      <td>b2b.personKey.sourceKey</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld: 333@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.personKey.sourceID</td>
      <td>string</td>
      <td>ID</td>
      <td>Ja</td>
      <td>Bijvoorbeeld - 333, afhankelijk van de gegevensbronlijst, is dit of Lood identiteitskaart of identiteitskaart van het Contact</td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.personKey.sourceInstanceID</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld - 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.personKey.sourceType</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld - Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>workEmail.address</td>
      <td>
        <p>string</p>
        <p>email</p>
      </td>
      <td>E-mail</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.personStatus</td>
      <td>string</td>
      <td>Status</td>
      <td><b><i>Alleen voor Lead personType</i></b></td>
      <td>Alleen vereist als b2b.personType "Lead" is</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>date-time</td>
      <td>CreatedDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>date-time</td>
      <td>ModifiedDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.isConverted</td>
      <td>boolean</td>
      <td>IsConverted</td>
      <td><b><i>Alleen voor Lead personType</i></b></td>
      <td>Alleen vereist als b2b.personType "Lead" is</td>
    </tr>
    <tr>
      <td></td>
      <td>b2b.personType</td>
      <td>string</td>
      <td>"Lead" of "Contact"</td>
      <td>Ja</td>
      <td>Afhankelijk van de gegevensbronlijst, zou dit aan of "Lood"of "Contact"moeten worden geplaatst. We raden u aan deze instelling in te stellen op "Contact" voor de meeste gevallen</td>
    </tr>
    <tr>
      <td></td>
      <td>extendedWorkDetails.jobTitle</td>
      <td>string</td>
      <td></td>
      <td>Nee</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td rowspan="4">XDM Business Person-componenten</td>
      <td>personComponents.sourceAccountKey.sourceKey</td>
      <td>string</td>
      <td></td>
      <td>Nee</td>
      <td>
        <p>Bijvoorbeeld: 123@999-abc-888.Marketo.</p>
        <p>De set van sourceAccountKey-velden is alleen "vereist" voor echte contactrecords, gedefinieerd als persoonrecords die zijn gekoppeld aan account. Als deze waarde ontbreekt, wordt de gegevensset niet geweigerd, maar zijn de toewijzingsresultaten uitgeschakeld.</p>
        <p>personComponents is een array, maar Marketo Measure neemt alleen het eerste element personComponents[0]</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>personComponents.sourceAccountKey.sourceID</td>
      <td>string</td>
      <td>Account-id</td>
      <td>Nee</td>
      <td>
        <p>bijv. - 123.</p>
        <p>Externe sleutel naar account</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>personComponents.sourceAccountKey.sourceInstanceID</td>
      <td>string</td>
      <td></td>
      <td>Nee</td>
      <td>bijv. - 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>personComponents.sourceAccountKey.sourceType</td>
      <td>string</td>
      <td></td>
      <td>Nee</td>
      <td>Bijvoorbeeld - Marketo</td>
    </tr>
    <tr>
      <td colspan="7"><strong> Kans </strong> (Kans voor Salesforce, Kansen voor Marketo)</td>
    </tr>
    <tr>
      <td rowspan="13">XDM Business Opportunity</td>
      <td></td>
      <td>opportunityKey.sourceKey</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>bijv. - 77777@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceID</td>
      <td>string</td>
      <td>ID</td>
      <td>Ja</td>
      <td>Bijvoorbeeld - 77777</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceInstanceID</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld - 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceType</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld - Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>date-time</td>
      <td>CreatedDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>date-time</td>
      <td>ModifiedDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceKey</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>bijv. - 123@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceID</td>
      <td>string</td>
      <td>Account-id</td>
      <td>Ja</td>
      <td>
        <p>bijv. - 123.</p>
        <p>Externe sleutel naar account</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceInstanceID</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld - 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>accountKey.sourceType</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld - Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityName</td>
      <td>string</td>
      <td>Naam</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityStage</td>
      <td>string</td>
      <td>Werkgebied</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityType</td>
      <td>string</td>
      <td></td>
      <td>Nee</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td rowspan="5">XDM Business Opportunity-gegevens</td>
      <td>isWon</td>
      <td>boolean</td>
      <td>IsWon</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>isClosed</td>
      <td>boolean</td>
      <td>IsClosed</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>expectedCloseDate</td>
      <td>date</td>
      <td>CloseDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityAmount.amount</td>
      <td>getal</td>
      <td>Hoeveelheid</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityAmount.currencyCode</td>
      <td>
        <p>string</p>
        <p>^[A-Z]{3}$</p>
      </td>
      <td>CurrencyIsoCode</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td colspan="7"><strong>Functie contactpersoon voor opportunity (alleen vereist als u Opportunity Contact Rol wilt gebruiken als inkoopgroep voor toewijzing)</strong></td>
    </tr>
    <tr>
      <td rowspan="16">XDM Business Opportunity Person Relatie</td>
      <td></td>
      <td>personKey.sourceKey</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>bijv. - 333@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceID</td>
      <td>string</td>
      <td>Contactpersoon-id</td>
      <td>Ja</td>
      <td>
        <p>bijv. - 333.</p>
        <p>Externe sleutel voor contact</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceInstanceID</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld - 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>personKey.sourceType</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld - Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>isPrimary</td>
      <td>boolean</td>
      <td>IsPrimary</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceKey</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>bijv. - 77777@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceID</td>
      <td>string</td>
      <td>Opportunity-id</td>
      <td>Ja</td>
      <td>
        <p>bijv. - 7777.</p>
        <p>Buitenlandse sleutel naar opportunity</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceInstanceID</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld - 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityKey.sourceType</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld - Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityPersonKey.sourceKey</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>bijv. - 222222@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityPersonKey.sourceID</td>
      <td>string</td>
      <td>ID</td>
      <td>Ja</td>
      <td>bijv. - 222222</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityPersonKey.sourceInstanceID</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld - 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td>opportunityPersonKey.sourceType</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld - Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>personRole</td>
      <td>string</td>
      <td>Functie</td>
      <td>Nee</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>date-time</td>
      <td>CreatedDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>date-time</td>
      <td>ModifiedDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td colspan="7"><strong>Conversiesnelheid (alleen vereist als u meerdere valuta's gebruikt; slechts één gegevensset met conversiesnelheden kan op Marketo Measure worden geactiveerd)</strong></td>
    </tr>
    <tr>
      <td rowspan="7">Conversie</td>
      <td></td>
      <td>extSourceSystemAudit.externalKey.sourceKey</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>bijv. - 8888@0x012345.Salesforce</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.externalKey.sourceId</td>
      <td>string</td>
      <td>ID</td>
      <td>Ja</td>
      <td>bijv. - 8888</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.externalKey.sourceInstanceId</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld - 0x012345</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.externalKey.sourceType</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld - Salesforce</td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.createdDate</td>
      <td>date-time</td>
      <td>CreatedDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>extSourceSystemAudit.lastUpdatedDate</td>
      <td>date-time</td>
      <td>ModifiedDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>isDelette</td>
      <td>boolean</td>
      <td></td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td rowspan="5">Details valutaomrekeningskoers</td>
      <td>conversionRate</td>
      <td>getal</td>
      <td>ConversionRate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>endDate</td>
      <td>date</td>
      <td>NextStartDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>startDate</td>
      <td>date</td>
      <td>StartDate</td>
      <td>Ja</td>
      <td></td>
    </tr>
    <tr>
      <td></td>
      <td>sourceISOCode</td>
      <td>string</td>
      <td>ISOCode</td>
      <td>Ja</td>
      <td>Bijvoorbeeld EUR</td>
    </tr>
    <tr>
      <td></td>
      <td>targetISOCode</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>De standaardvalutacode die in Marketo Measure is ingesteld, bijvoorbeeld USD</td>
    </tr>
  </tbody>
</table>

## Gegevensvereisten voor valutaomrekening {#currency-conversion-data-requirements}

**StandaardValuta**: In Marketo Measure, worden alle opbrengst en kosten omgezet in een standaardmunt bij het melden van tijd. Er moet één record zijn met dezelfde datumdekking voor de doelvaluta zelf (bv. USD tot USD) met een omrekeningskoers van 1.

**Tarieven van de Omzetting**: Elk (bronmunt, doelmunt) paar kan veelvoudige omzettingspercentages voor verschillende datumperiodes hebben. De tarieven moeten het volledige tijdsbereik van 0001-01-01 tot 9999-12-31 bestrijken, zoals bepaald door het Salesforce DatedConversionRate-object.

**de Waaier van de Datum**:

* Geen overlappende datumbereiken binnen een vastgestelde (bronvaluta, doelvaluta) koers (bv. 2023-01-01 tot 2023-02-01 en 2023-01-01 tot 2024-01-01).
* Geen tussenruimten tussen datumbereiken. De begindatum is inclusief en de einddatum is exclusief.

## ExperienceEvent {#experienceevent}

<table style="table-layout:auto">
  <tr>
    <th>XDM-klasse</th>
    <th>XDM-veldgroep</th>
    <th>XDM-pad</th>
    <th>XDM-type</th>
    <th>Source-veld voor gegevens</th>
    <th>Vereist?</th>
    <th>Notities</th>
  </tr>
  <tbody>
    <tr>
      <td colspan="7"><strong>Activiteit</strong></td>
    </tr>
    <tr>
      <td rowspan="3">XDM ExperienceEvent</td>
      <td></td>
      <td>_id</td>
      <td>string</td>
      <td>ID</td>
      <td>Ja</td>
      <td>Ja</td>
    </tr>
    <tr>
      <td></td>
      <td>eventType</td>
      <td>string</td>
      <td>ActivityType</td>
      <td>Ja</td>
      <td>Ja</td>
    </tr>
    <tr>
      <td></td>
      <td>tijdstempel</td>
      <td>date-time</td>
      <td>Datum activiteit</td>
      <td>Ja</td>
      <td>Ja</td>
    </tr>
    <tr>
      <td></td>
      <td>Persoon-id</td>
      <td>personKey.sourceKey</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld: 333@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>personKey.sourceID</td>
      <td>string</td>
      <td>ID lead of contactpersoon</td>
      <td>Ja</td>
      <td>
        <p>Bijvoorbeeld - 333, afhankelijk van de gegevensbronlijst, is dit of Lood identiteitskaart of identiteitskaart van het Contact</p>
        <p>Externe sleutel naar lead of contact</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>personKey.sourceInstanceID</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld - 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>personKey.sourceType</td>
      <td>string</td>
      <td></td>
      <td>Ja</td>
      <td>Bijvoorbeeld - Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>Toevoegen aan campagne</td>
      <td>leadOperation.addToCampaign.campaignKey.sourceKey</td>
      <td>string</td>
      <td></td>
      <td>Ja, alleen voor het type leadOperation.addToCampaign</td>
      <td>Bijvoorbeeld: 55555@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.addToCampaign.campaignKey.sourceId</td>
      <td>string</td>
      <td>Campagne-id</td>
      <td>Ja, alleen voor het type leadOperation.addToCampaign</td>
      <td>
        <p>Bijvoorbeeld - 55555.</p>
        <p>Externe sleutel voor campagne</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.addToCampaign.campaignKey.sourceInstanceId</td>
      <td>string</td>
      <td></td>
      <td>Ja, alleen voor het type leadOperation.addToCampaign</td>
      <td>Bijvoorbeeld - 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.addToCampaign.campaignKey.sourceType</td>
      <td>string</td>
      <td></td>
      <td>Ja, alleen voor het type leadOperation.addToCampaign</td>
      <td>Bijvoorbeeld - Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td>Status in gewijzigde campagnevoortgang</td>
      <td>leadOperation.campaignProgression.campaignKey.sourceKey</td>
      <td>string</td>
      <td></td>
      <td>Ja, alleen voor het type leadOperation.campagneProgression</td>
      <td>Bijvoorbeeld: 55555@999-abc-888.Marketo</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.campaignProgression.campaignKey.sourceId</td>
      <td>string</td>
      <td>Campagne-id</td>
      <td>Ja, alleen voor het type leadOperation.campagneProgression</td>
      <td>
        <p>Bijvoorbeeld - 55555.</p>
        <p>Externe sleutel voor campagne</p>
      </td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.campaignProgression.campaignKey.sourceInstanceId</td>
      <td>string</td>
      <td></td>
      <td>Ja, alleen voor het type leadOperation.campagneProgression</td>
      <td>Bijvoorbeeld - 999-abc-888</td>
    </tr>
    <tr>
      <td></td>
      <td></td>
      <td>leadOperation.campaignProgression.campaignKey.sourceType</td>
      <td>string</td>
      <td></td>
      <td>Ja, alleen voor het type leadOperation.campagneProgression</td>
      <td>Bijvoorbeeld - Marketo</td>
    </tr>
  </tbody>
</table>

## Ondersteund ExperienceEvent-type {#experienceevent-type-supported}

<table style="table-layout:auto">
  <tr>
    <th>Type gebeurtenis</th>
    <th>XDM-gebeurtenistype</th>
    <th>Beschrijving</th>
  </tr>
  <tbody>
    <tr>
      <td>Nieuwe lead</td>
      <td>leadOperation.newLead</td>
      <td>Gebruiken om de aanmaak en details van een nieuwe marketinglead vast te leggen</td>
    </tr>
    <tr>
      <td>Regelafstand omzetten</td>
      <td>leadOperation.convertLead</td>
      <td>Gebruik wanneer een marketing lood in een verkoop-gekwalificeerde contact wordt omgezet dat aan een verkoopgebruiker wordt toegewezen</td>
    </tr>
    <tr>
      <td>Interessant moment</td>
      <td>leadOperation.interestingMoment</td>
      <td>Gebruik voor het bijhouden van activiteiten van hoge kwaliteit door potentiële klanten</td>
    </tr>
    <tr>
      <td>Formulier invullen</td>
      <td>web.formFilledOut</td>
      <td>Gebruik deze optie om details vast te leggen wanneer iemand een formulier op een webpagina invult</td>
    </tr>
    <tr>
      <td>E-mailadres opzeggen</td>
      <td>directMarketing.emailUnsubscribed</td>
      <td>Gebruiken om details vast te leggen wanneer een persoon zich afmeldt bij een e-mail</td>
    </tr>
    <tr>
      <td>E-mail openen</td>
      <td>directMarketing.emailOpened</td>
      <td>Gebruik deze optie om details vast te leggen wanneer iemand een marketingmail opent</td>
    </tr>
    <tr>
      <td>Klik op E-mail</td>
      <td>directMarketing.emailClicked</td>
      <td>Gebruiken om details vast te leggen wanneer iemand op een koppeling in een marketingmail klikt</td>
    </tr>
    <tr>
      <td>Status wijzigen in Progressie</td>
      <td>leadOperation.statusInCampaignProgressionChanged</td>
      <td>Gebruiken om details vast te leggen wanneer de status van een lead in een campagne verandert</td>
    </tr>
    <tr>
      <td>Toevoegen aan betrokkenheidsprogramma (toevoegen aan cursus)</td>
      <td>leadOperation.addToCampaign</td>
      <td>Hiermee voegt u een persoon toe aan de specifieke campagne.</td>
    </tr>
  </tbody>
</table>

Gebruik het gebeurtenistype &quot;Interesting Moment&quot; voor gebeurtenistypen die niet in de bovenstaande tabel worden ondersteund. Voeg een aangepast veld toe om het subtype &quot;Interesting Moment&quot; aan te geven.

## Zoekvoorbeelden voor gegevenscontrole {#query-examples-for-data-inspection}

Hieronder volgt een lijst met queryvoorbeelden voor het inspecteren van ingesloten gegevenssets in het gegevensmeer van AEP. Om hen tegen uw datasets te gebruiken, vervang de lijstnaam in de vraagvoorbeelden hieronder met uw daadwerkelijke naam van de datasetlijst.

We verwachten dat alle tellingen 0 zijn.

Voor personType-veld verwachten we alleen &#39;Lead&#39;- of &#39;Contact&#39;-waarden en er is geen null-waarde.

Voor alle persoonlijke gegevens van de contactpersoon verwachten we dat er een buitenlandse sleutel voor de account is.

Voor persoonrecords met de naam &quot;Lead&quot; bestaat een vreemde sleutel voor de account niet en is deze niet vereist. Als u ervoor kiest om persoonlijke gegevens van &quot;lead&quot; in te voeren als &quot;contact&quot; met de persoon (aanbevolen), is een buitenlandse sleutel van de account niet vereist.

### XDM Business Account {#xdm-business-account}

```sql
select 'account source id', count(*) from salesforce_account where accountKey.sourceId is null
union all
select 'account source type', count(*) from salesforce_account where accountKey.sourceType is null
union all
select 'account source instance id', count(*) from salesforce_account where accountKey.sourceInstanceId is null
union all
select 'account source key', count(*) from salesforce_account where accountKey.sourceKey is null
union all
select 'account name', count(*) from salesforce_account where accountName is null
union all
select 'created date', count(*) from salesforce_account where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_account where extSourceSystemAudit.lastUpdatedDate is null;
```

### XDM Business Campaign {#xdm-business-campaign}

```sql
select 'campaign source id', count(*) from salesforce_campaign where campaignKey.sourceId is null
union all
select 'campaign source type', count(*) from salesforce_campaign where campaignKey.sourceType is null
union all
select 'campaign source instance id', count(*) from salesforce_campaign where campaignKey.sourceInstanceId is null
union all
select 'campaign source key', count(*) from salesforce_campaign where campaignKey.sourceKey is null
union all
select 'campaign name', count(*) from salesforce_campaign where campaignName is null
union all
select 'created date', count(*) from salesforce_campaign where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_campaign where extSourceSystemAudit.lastUpdatedDate is null;
```

### XDM Business Campaign-lid {#xdm-business-campaign-member}

```sql
select 'campaign member source id', count(*) from salesforce_campaign_member where campaignMemberKey.sourceId is null
union all
select 'campaign member source type', count(*) from salesforce_campaign_member where campaignMemberKey.sourceType is null
union all
select 'campaign member source instance id', count(*) from salesforce_campaign_member where campaignMemberKey.sourceInstanceId is null
union all
select 'campaign member source key', count(*) from salesforce_campaign_member where campaignMemberKey.sourceKey is null
union all
select 'campaign source id', count(*) from salesforce_campaign_member where campaignKey.sourceId is null
union all
select 'campaign source type', count(*) from salesforce_campaign_member where campaignKey.sourceType is null
union all
select 'campaign source instance id', count(*) from salesforce_campaign_member where campaignKey.sourceInstanceId is null
union all
select 'campaign source key', count(*) from salesforce_campaign_member where campaignKey.sourceKey is null
union all
select 'person source id', count(*) from salesforce_campaign_member where personKey.sourceId is null
union all
select 'person source type', count(*) from salesforce_campaign_member where personKey.sourceType is null
union all
select 'person source instance id', count(*) from salesforce_campaign_member where personKey.sourceInstanceId is null
union all
select 'person source key', count(*) from salesforce_campaign_member where personKey.sourceKey is null
union all
select distinct 'person type', b2b.personType from salesforce_campaign_member
union all
select 'member status', count(*) from salesforce_campaign_member where memberStatus is null
union all
select 'has responded', count(*) from salesforce_campaign_member where hasResponded is null
union all
select 'created date', count(*) from salesforce_campaign_member where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_campaign_member where extSourceSystemAudit.lastUpdatedDate is null;
```

### XDM Business Person {#xdm-business-person}

```sql
select 'person source id', count(*) from marketo_person where b2b.personKey.sourceId is null
union all
select 'person source type', count(*) from marketo_person where b2b.personKey.sourceType is null
union all
select 'person source instance id', count(*) from marketo_person where b2b.personKey.sourceInstanceId is null
union all
select 'person source key', count(*) from marketo_person where b2b.personKey.sourceKey is null
union all
select 'email', count(*) from marketo_person where workEmail.address is null
union all
select 'Lead - person status', count(*) from marketo_person where b2b.personType = 'Lead' and b2b.personStatus is null
union all
select 'Lead - is converted', count(*) from marketo_person where b2b.personType = 'Lead' and b2b.isConverted is null
union all
select distinct 'person type', b2b.personType from marketo_person
union all
select 'created date', count(*) from marketo_person where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from marketo_person where extSourceSystemAudit.lastUpdatedDate is null;
```

```sql
select 'person source id', count(*) from salesforce_contact where b2b.personKey.sourceId is null
union all
select 'person source type', count(*) from salesforce_contact where b2b.personKey.sourceType is null
union all
select 'person source instance id', count(*) from salesforce_contact where b2b.personKey.sourceInstanceId is null
union all
select 'person source key', count(*) from salesforce_contact where b2b.personKey.sourceKey is null
union all
select 'email', count(*) from salesforce_contact where workEmail.address is null
union all
select 'Lead - person status', count(*) from salesforce_contact where b2b.personType = 'Lead' and b2b.personStatus is null
union all
select 'Lead - is converted', count(*) from salesforce_contact where b2b.personType = 'Lead' and b2b.isConverted is null
union all
select distinct 'person type', b2b.personType from salesforce_contact
union all
select 'account source id', count(*) from salesforce_contact where b2b.personType = 'Contact' and personComponents[0].sourceAccountKey.sourceId is null
union all
select 'account source type', count(*) from salesforce_contact where b2b.personType = 'Contact' and personComponents[0].sourceAccountKey.sourceType is null
union all
select 'account source instance id', count(*) from salesforce_contact where b2b.personType = 'Contact' and personComponents[0].sourceAccountKey.sourceInstanceId is null
union all
select 'account source key', count(*) from salesforce_contact where b2b.personType = 'Contact' and personComponents[0].sourceAccountKey.sourceKey is null
union all
select 'created date', count(*) from salesforce_contact where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_contact where extSourceSystemAudit.lastUpdatedDate is null;
```

### XDM Business Opportunity {#xdm-business-opportunity}

```sql
select 'opportunity source id', count(*) from salesforce_opportunity where opportunityKey.sourceId is null
union all
select 'opportunity source type', count(*) from salesforce_opportunity where opportunityKey.sourceType is null
union all
select 'opportunity source instance id', count(*) from salesforce_opportunity where opportunityKey.sourceInstanceId is null
union all
select 'opportunity source key', count(*) from salesforce_opportunity where opportunityKey.sourceKey is null
union all
select 'account source id', count(*) from salesforce_opportunity where accountKey.sourceId is null
union all
select 'account source type', count(*) from salesforce_opportunity where accountKey.sourceType is null
union all
select 'account source instance id', count(*) from salesforce_opportunity where accountKey.sourceInstanceId is null
union all
select 'account source key', count(*) from salesforce_opportunity where accountKey.sourceKey is null
union all
select 'opportunity name', count(*) from salesforce_opportunity where opportunityName is null
union all
select 'opportunity stage', count(*) from salesforce_opportunity where opportunityStage is null
union all
select 'is won', count(*) from salesforce_opportunity where isWon is null
union all
select 'is closed', count(*) from salesforce_opportunity where isClosed is null
union all
select 'expected close date', count(*) from salesforce_opportunity where expectedCloseDate is null
union all
select 'opportunity amount', count(*) from salesforce_opportunity where opportunityAmount.amount is null
union all
select 'currency code', count(*) from salesforce_opportunity where opportunityAmount.currencyCode is null
union all
select 'created date', count(*) from salesforce_opportunity where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from salesforce_opportunity where extSourceSystemAudit.lastUpdatedDate is null;
```

### XDM ExperienceEvent {#xdm-experienceevent}

```sql
select 'id', count(*) from marketo_activity where _id is null
union all
select 'event type', count(*) from marketo_activity where eventType is null
union all
select 'timestamp', count(*) from marketo_activity where timestamp is null
union all
select 'person source id', count(*) from marketo_activity where personKey.sourceId is null
union all
select 'person source type', count(*) from marketo_activity where personKey.sourceType is null
union all
select 'person source instance id', count(*) from marketo_activity where personKey.sourceInstanceId is null
union all
select 'person source key', count(*) from marketo_activity where personKey.sourceKey is null
union all
select 'addToCampaign campaign id', count(*) from marketo_activity where eventType = 'leadOperation.addToCampaign' and leadOperation.addToCampaign.campaignKey.sourceId is null
union all
select 'addToCampaign campaign type', count(*) from marketo_activity where eventType = 'leadOperation.addToCampaign' and leadOperation.addToCampaign.campaignKey.sourceType is null
union all
select 'addToCampaign campaign instance id', count(*) from marketo_activity where eventType = 'leadOperation.addToCampaign' and leadOperation.addToCampaign.campaignKey.sourceInstanceId is null
union all
select 'addToCampaign campaign key', count(*) from marketo_activity where eventType = 'leadOperation.addToCampaign' and leadOperation.addToCampaign.campaignKey.sourceKey is null
union all
select 'statusInCampaignProgressionChanged campaign id', count(*) from marketo_activity where eventType = 'leadOperation.statusInCampaignProgressionChanged' and leadOperation.campaignProgression.campaignKey.sourceId is null
union all
select 'statusInCampaignProgressionChanged campaign type', count(*) from marketo_activity where eventType = 'leadOperation.statusInCampaignProgressionChanged' and leadOperation.campaignProgression.campaignKey.sourceType is null
union all
select 'statusInCampaignProgressionChanged campaign instance id', count(*) from marketo_activity where eventType = 'leadOperation.statusInCampaignProgressionChanged' and leadOperation.campaignProgression.campaignKey.sourceInstanceId is null
union all
select 'statusInCampaignProgressionChanged campaign key', count(*) from marketo_activity where eventType = 'leadOperation.statusInCampaignProgressionChanged' and leadOperation.campaignProgression.campaignKey.sourceKey is null;
```

```sql
select 'id', count(*) from salesforce_task where _id is null
union all
select 'event type', count(*) from salesforce_task where eventType is null
union all
select 'timestamp', count(*) from salesforce_task where timestamp is null
union all
select 'person source id', count(*) from salesforce_task where personKey.sourceId is null
union all
select 'person source type', count(*) from salesforce_task where personKey.sourceType is null
union all
select 'person source instance id', count(*) from salesforce_task where personKey.sourceInstanceId is null
union all
select 'person source key', count(*) from salesforce_task where personKey.sourceKey is null;
```

### Conversie {#conversion}

```sql
select 'conversion rate', count(*) from currency_conversion_rate where conversionRate is null
union all
select 'end date', count(*) from currency_conversion_rate where endDate is null
union all
select 'start date', count(*) from currency_conversion_rate where startDate is null
union all
select 'source ISO Code', count(*) from currency_conversion_rate where sourceISOCode is null
union all
select 'target ISO Code', count(*) from currency_conversion_rate where targetISOCode is null
union all
select 'source id', count(*) from currency_conversion_rate where extSourceSystemAudit.externalKey.sourceId is null
union all
select 'source type', count(*) from currency_conversion_rate where extSourceSystemAudit.externalKey.sourceType is null
union all
select 'source instance id', count(*) from currency_conversion_rate where extSourceSystemAudit.externalKey.sourceInstanceId is null
union all
select 'source key', count(*) from currency_conversion_rate where extSourceSystemAudit.externalKey.sourceKey is null
union all
select 'created date', count(*) from currency_conversion_rate where extSourceSystemAudit.createdDate is null
union all
select 'last updated date', count(*) from currency_conversion_rate where extSourceSystemAudit.lastUpdatedDate is null;
```

## Aanbevolen Oplossing voor Vereiste Gebieden met een ONGELDIGE Waarde {#recommended-solution-for-required-fields-with-a-null-value}

Wij adviseren gebruikend een berekend gebied in gebiedstoewijzing om het gebied aan een niet-ONGELDIGE waarde in gebreke te blijven. Hieronder volgen twee voorbeelden:

* Als `opportunityName` van sommige opportunityrecords null is, maakt en gebruikt u het volgende berekende veld in veldtoewijzing
   * `iif(name != null && trim(name) != "", name, "Unknown")`

* Als `leadOperation.campaignProgression.campaignID` van sommige ervaringsgebeurtenisrecords null is, maakt en gebruikt u het volgende berekende veld in veldtoewijzing
   * `iif(leadOperation.campaignProgression.campaignID != null && leadOperation.campaignProgression.campaignID != "" , to_object("sourceType", "Marketo", "sourceInstanceID", "123-abc-321", "sourceID", leadOperation.campaignProgression.campaignID, "sourceKey", concat(leadOperation.campaignProgression.campaignID,"@123-abc-321.Marketo")), iif(eventType == "leadOperation.statusInCampaignProgressionChanged", to_object("sourceType", "Marketo", "sourceInstanceID", "123-abc-321", "sourceID", "Unknown", "sourceKey", "Unknown@123-abc-321.Marketo"), null))`
