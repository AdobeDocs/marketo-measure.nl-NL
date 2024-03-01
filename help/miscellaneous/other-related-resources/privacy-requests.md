---
description: Privacyverzoeken - [!DNL Marketo Measure]
title: Privacyverzoeken
exl-id: 883e475f-9868-412a-b505-230556f38484
feature: APIs, Tracking
source-git-commit: 915e9c5a968ffd9de713b4308cadb91768613fc5
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 0%

---

# Privacyverzoeken {#privacy-requests}

Dit document biedt een overzicht van het beheer van individuele privacyverzoeken voor gegevens die u kunt verzenden naar [!DNL Marketo Measure] via de [!DNL Privacy Service] UI en de **[!DNL Privacy Service]API**.

U kunt individuele verzoeken indienen om tot consumentengegevens toegang te hebben en te schrappen [!DNL Marketo Measure] op twee manieren :

* Via de [[!DNL Privacy Service] UI](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html){target="_blank"}.
* Via de **[!DNL Privacy Service]API**. Zie de documentatie [hier](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html){target="_blank"} and the API reference [here](https://developer.adobe.com/experience-platform-apis/references/privacy-service/){target="_blank"}.

De [Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html){target="_blank"} ondersteunt twee soorten verzoeken: toegang tot gegevens en verwijdering van gegevens.

Zie hoe u verzoeken van de Toegang en van de Schrapping kunt tot stand brengen.

## Vereiste installatie voor het verzenden van aanvragen voor Marketo Measure {#required-setup-to-send-requests-for-marketo-measure}

Om tot Gegevens van de Toegang en van de Schrapping te verzoeken voor [!DNL Marketo Measure], moet u:

1. Vermeld het volgende:

   a. IMS Org ID

   b. E-mailadres van de persoon aan wie u wilt optreden

   Een IMS-organisatie-id is een alfanumerieke tekenreeks van 24 tekens die wordt toegevoegd met @AdobeOrg. Als uw marketingteam of de beheerder van het interne Adobe-systeem de IMS Org-id van uw organisatie niet kent, neemt u contact op met de klantenservice van de Adobe op gdprsupport@adobe.com. U hebt de IMS Org ID nodig om aanvragen in te dienen bij de Privacy API.

1. In [!DNL Privacy Service], kunt u verzoeken om toegang en om verwijdering verzenden naar [!DNL Marketo Measure]en controleert u de status van bestaande verzoeken.

## Vereiste veldwaarden in [!DNL Marketo Measure] JSON-verzoeken {#required-field-values-in-marketo-measure-json-requests}

&quot;companyContext&quot;:

* &quot;namespace&quot;: **imsOrgID**
* &quot;waarde&quot;: `<Your IMS Org ID Value>`

&quot;gebruikers&quot;:

* &quot;actie&quot;: [!UICONTROL access] of verwijderen
* &quot;userIDs&quot;:
   * &quot;namespace&quot;: e-mail
   * &quot;type&quot;: standaard
   * &quot;waarde&quot;: `<Data Subject's Email Address>`

&quot;include&quot;:

* **marketoMeas** (dit is het Adobe product dat van toepassing is op het verzoek)

&quot;verordening&quot;:

* **gdpr**, **ccpa**, **pdpa**, **lgpd_bra**, of **nzpa_nzl** (dit is de privacyverordening die van toepassing is op het verzoek)

## Voorbeeld één: GDPR-aanvraag verwijderen {#gdpr-delete-request}

JSON-aanvraag

```text
{
  "companyContexts": [
    {
      "namespace": "imsOrgID",
      "value": "1231659F56A68A8B7F000101@AdobeOrg"
    }
  ],
  "users": [
    {
      "action": [
        "delete"
      ],
      "userIDs": [
        {
          "namespace": "email",
          "type": "standard",
          "value": "john.doe@adobe.com"
        }
      ]
    }
  ],
  "include": [
    "marketoMeasure"
  ],
  "regulation": "gdpr",
}
```

JSON-reactie

```text
{
  "requestId": "16331241037112570RX-245",
  "totalRecords": 1,
  "jobs": [
    {
      "jobId": "997b01e3-9568-402c-904b-b4e60a437875",
      "customer": {
        "user": {
          "action": [
            "delete"
          ],
          "userIDs": [
            {
              "namespace": "email",
              "value": "john.doe@adobe.com",
              "type": "standard",
              "namespaceId": 6,
              "isDeletedClientSide": false
            }
          ]
        }
      }
    }
  ]
}
```

## Voorbeeld twee: CCPA-verzoek om toegang {#ccpa-access-request}

JSON-aanvraag

```text
{
  "companyContexts": [
    {
      "namespace": "imsOrgID",
      "value": "1231659F56A68A8B7F000101@AdobeOrg"
    }
  ],
  "users": [
    {
      "action": [
        "access"
      ],
      "userIDs": [
        {
          "namespace": "email",
          "type": "standard",
          "value": "john.doe@adobe.com"
        }
      ]
    }
  ],
  "include": [
    "marketoMeasure"
  ],
  "regulation": "ccpa",
}
```

JSON-reactie

```text
{
  "requestId": "16329573462631890RX-207",
  "totalRecords": 1,
  "jobs": [
    {
      "jobId": "3115e42d-011b-47ab-a2b0-ed4356af4d3e",
      "customer": {
        "user": {
          "action": [
            "access"
          ],
          "userIDs": [
            {
              "namespace": "email",
              "value": "john.doe@adobe.com",
              "type": "standard",
              "namespaceId": 6,
              "isDeletedClientSide": false
            }
          ]
        }
      }
    }
  ]
}
```
