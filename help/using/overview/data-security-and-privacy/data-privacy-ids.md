---
description: This document covers the types of Audience Manager IDs that you can use in data privacy requests.
seo-description: This document covers the types of Audience Manager IDs that you can use in data privacy requests.
seo-title: Audience Manager Identifiers (IDs)
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, AAM ID
title: Audience Manager Identifiers (IDs)
---

# Audience Manager Identifiers (IDs) {#aam-ids}

When submitting data privacy requests to Adobe Audience Manager, you must include one of the identifiers (IDs) listed below. You can find more information on the ID formats in our [Index of Audience Manager IDs](../../reference/ids-in-aam.md).

## Adobe Audience Manager Unique User ID

* **User ID**: `aam_uuid`
* **Definition**: Adobe Audience Manager Unique User ID
* **Namespace ID**: 0

**JSON Example**:

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

>[!NOTE]
>
>You can also use the [!DNL CORE] namespace.

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

## Adobe Experience Cloud ID

* **User ID**: `mid`
* **Definition**: [!DNL Adobe Experience Cloud ID], formerly known as [!DNL Visitor ID] or [!DNL Marketing Cloud ID]
* **Namespace ID**: 4

>[!NOTE]
>
>You can also use the [!DNL ECID] namespace. See the second [!DNL JSON] example.

**JSON Example**:

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

## Customer ID

**User ID**: `cid`

**Definition**: Customer ID, such as a cookie you set for anonymous site visitors or a [!DNL CRM] ID from an offline system or a hashed username.

**Namespace ID**: Customer-specific. Please find it from your Audience Manager instance.

**JSON Example**:

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"1234567",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-1234567"
      },
      {
        "namespace": "1234567",
        "type": "namespaceId",
        "value": "another-unique-user-id-for-datasource-1234567"
      },
      {
        "namespace":"54321",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-54321"
      }
    ]
  }
  ```

## Mobile advertising ID

**User ID**: `d_cid`

**Definition**: Mobile advertising IDs.

**Namespace ID**:

* [!DNL IDFA:] 20915
* [!DNL GAID:] 20914

See [Global Data Sources](../../features/global-data-sources.md) for more details.

>[!IMPORTANT]
>
> If you are using the Mobile [!DNL SDK], then you should also send the Experience Cloud ID (`MID`) along with mobile advertising IDs for complete Access and Delete responses.

**JSON Example**:

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"20914",
        "type": "namespaceId",
        "value": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2"
      },
      {
        "namespace":"20915",
        "type": "namespaceId",
        "value": "AEBE52E7-03EE-455A-B3C4-E57283966239"
      }
    ]
  }
]
```

## Integration code

**User ID**: `d_cid_ic`

**Definition**: An integration code for the data source. This can be used instead of data source ID / namespace ID in the [!DNL API] request to [!DNL Adobe Experience Cloud Privacy Core Service].

**Namespace ID**: Not applicable

**JSON Example**:

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "loyaltyCard",
        "type": "integrationCode",
        "value": "272023537812"
      },
      {
        "namespace":"offlineCampaign",
        "type": "integrationCode",
        "value": "9546673332"
      }
    ]
  }
]
```
