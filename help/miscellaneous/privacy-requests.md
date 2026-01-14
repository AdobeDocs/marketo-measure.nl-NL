---
description: Richtlijnen voor privacyverzoeken voor Marketo Measure-gebruikers
title: Privacyverzoeken
exl-id: 883e475f-9868-412a-b505-230556f38484
feature: APIs, Tracking
source-git-commit: 0299ef68139df574bd1571a749baf1380a84319b
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 0%

---


# Privacyverzoeken {#privacy-requests}

Dit document biedt een overzicht van het beheer van individuele privacyverzoeken voor gegevens die u naar [!DNL Marketo Measure] kunt verzenden via de [!DNL Privacy Service] interface en de **[!DNL Privacy Service]API** .

U kunt afzonderlijke aanvragen voor toegang tot en verwijdering van consumentengegevens uit [!DNL Marketo Measure] op twee manieren verzenden:

* Door [[!DNL Privacy Service]  UI &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html?lang=nl-NL){target="_blank"}.
* Via de **[!DNL Privacy Service]API** . Zie hier de documentatie [&#x200B; &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=nl-NL){target="_blank"} en API verwijzing [&#x200B; &#x200B;](https://developer.adobe.com/experience-platform-apis/references/privacy-service/){target="_blank"}.

[&#x200B; Privacy Service &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=nl-NL){target="_blank"} steunt twee soorten verzoeken: gegevenstoegang en gegevensschrapping.

Zie hoe u verzoeken van de Toegang en van de Schrapping kunt tot stand brengen.

## Vereiste instelling voor het verzenden van aanvragen voor Marketo Measure {#required-setup-to-send-requests-for-marketo-measure}

Als u aanvragen wilt indienen voor toegang tot gegevens en gegevens wilt verwijderen voor [!DNL Marketo Measure] , moet u:

1. Vermeld het volgende:

   a. IMS Org ID

   b. E-mailadres van de persoon aan wie u wilt optreden

   Een IMS-organisatie-id is een alfanumerieke tekenreeks van 24 tekens die wordt toegevoegd met @AdobeOrg. Als uw marketingteam of interne Adobe-systeembeheerder de IMS Org-id van uw organisatie niet kent, neemt u contact op met de klantenservice van Adobe op gdprsupport@adobe.com. U hebt de IMS Org ID nodig om aanvragen in te dienen bij de Privacy API.

1. In [!DNL Privacy Service] kunt u aanvragen voor toegang en verwijderen indienen bij [!DNL Marketo Measure] en de status van bestaande aanvragen controleren.

## Vereiste veldwaarden in [!DNL Marketo Measure] JSON-aanvragen {#required-field-values-in-marketo-measure-json-requests}

&quot;companyContext&quot;:

* &quot;namespace&quot;: **imsOrgID**
* &quot;value&quot;: `<Your IMS Org ID Value>`

&quot;gebruikers&quot;:

* &quot;action&quot;: either [!UICONTROL access] or delete
* &quot;userIDs&quot;:
   * &quot;namespace&quot;: e-mail
   * &quot;type&quot;: standaard
   * &quot;value&quot;: `<Data Subject's Email Address>`

&quot;include&quot;:

* **marketoMeasuring** (dat het product van Adobe is dat op het verzoek van toepassing is)

&quot;verordening&quot;:

* **gdpr**, **ccpa**, **pdpa**, **lgpd_bra**, of **nzpa_nzl** (dat de privacyverordening is die op het verzoek van toepassing is)

## Voorbeeld één: GDPR-aanvraag verwijderen {#gdpr-delete-request}

JSON-aanvraag

```json
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

```json
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

```json
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

```json
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
