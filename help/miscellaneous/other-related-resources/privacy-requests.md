---
description: Privacyverzoeken - [!DNL Marketo Measure] - Productdocumentatie
title: Privacyverzoeken
exl-id: 883e475f-9868-412a-b505-230556f38484
source-git-commit: 09ffdbb0b1baeed870a3145268997e63a3707c97
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 0%

---

# Privacyverzoeken {#privacy-requests}

Dit document biedt een overzicht van het beheer van individuele privacyverzoeken voor gegevens die u kunt verzenden naar [!DNL Marketo Measure] via de [!DNL Privacy Service] UI en de **[!DNL Privacy Service]API**.

U kunt individuele verzoeken indienen om tot consumentengegevens toegang te hebben en te schrappen van [!DNL Marketo Measure] op twee manieren :

* Via de [[!DNL Privacy Service] UI](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html){target=&quot;_blank&quot;}.
* Via de **[!DNL Privacy Service]API**. Zie de documentatie [hier](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html){target=&quot;_blank&quot;} en de API-referentie [hier](https://developer.adobe.com/experience-platform-apis/references/privacy-service/){target=&quot;_blank&quot;}.

De [Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html){target=&quot;_blank&quot;} ondersteunt twee typen aanvragen: gegevenstoegang en gegevensverwijdering.

Zie hoe u verzoeken van de Toegang en van de Schrapping kunt tot stand brengen.

## Vereiste installatie voor het verzenden van aanvragen voor Marketo-maatregel {#required-setup-to-send-requests-for-marketo-measure}

Om tot Gegevens van de Toegang en van de Schrapping te verzoeken voor [!DNL Marketo Measure]moet u:

1. Vermeld het volgende:

   a. IMS Org ID

   b. E-mailadres van de persoon aan wie u wilt optreden

   Een IMS-organisatie-id is een alfanumerieke tekenreeks van 24 tekens die wordt toegevoegd met @AdobeOrg. Als uw marketingteam of interne beheerder van het Adobe-systeem de IMS Org-id van uw organisatie niet kent, neemt u contact op met de klantenservice van Adobe op gdprsupport@adobe.com. U hebt de IMS Org ID nodig om aanvragen in te dienen bij de Privacy API.

1. In [!DNL Privacy Service], kunt u verzoeken om toegang en om verwijdering verzenden naar [!DNL Marketo Measure]en controleert u de status van bestaande verzoeken.

## Vereiste veldwaarden in [!DNL Marketo Measure] JSON-verzoeken {#required-field-values-in-marketo-measure-json-requests}

&quot;companyContext&quot;:

* &quot;namespace&quot;: **imsOrgID**
* &quot;waarde&quot;: `<Your IMS Org ID Value>`

&quot;gebruikers&quot;:

* &quot;actie&quot;: ofwel [!UICONTROL access] of verwijderen
* &quot;userIDs&quot;:
   * &quot;namespace&quot;: email
   * &quot;type&quot;: standaard
   * &quot;waarde&quot;: `<Data Subject's Email Address>`

&quot;include&quot;:

* **marketoMeetlat** (dit is het product van de Adobe dat op het verzoek van toepassing is)

&quot;verordening&quot;:

* **gdpr**, **ccpa**, **pdpa**, **lgpd_bra**, of **nzpa_nzl** (dit is de privacyverordening die van toepassing is op het verzoek)

## Voorbeeld één: GDPR-verzoek verwijderen {#gdpr-delete-request}

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
