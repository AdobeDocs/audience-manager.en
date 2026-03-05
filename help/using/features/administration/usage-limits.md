---
description: Audience Manager sets a maximum limit on the number of traits, segments, destinations, and algorithmic models that you can create for an account. Limits apply to these items whether created in the user interface or programmatically through API methods. Usage limits help protect Audience Manager from automated processes that may attempt to compromise our APIs or user interface.
seo-description: Audience Manager sets a maximum limit on the number of traits, segments, destinations, and algorithmic models that you can create for an account. Limits apply to these items whether created in the user interface or programmatically through API methods. Usage limits help protect Audience Manager from automated processes that may attempt to compromise our APIs or user interface.
seo-title: Usage Limits
solution: Audience Manager
title: Usage Limits
keywords: ID mapping, ID mappings, cookie mappings
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
feature: Usage and Billing
exl-id: 8d29e231-d369-44ad-8e89-e6a4c83175f2
TQID: https://experienceleague.adobe.com/hyvYo82mjW-ZK5zn5nVzeQNavwIYTnd8LsjpNjiHofs
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
    internal-label: Implementation
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
    internal-label: APIs and SDKs
  - id: c814092e-2730-45e8-a12d-e084529f52cb
    internal-label: Destinations
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
    internal-label: Administration
subfeature_v2:
  - id: d12f0729-c5e9-4a4a-bb39-687f9ab4a97c
    internal-label: Usage and billing
  - id: d3dfac44-e20d-492d-a806-0f4a4a495901
    internal-label: Support
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
    internal-label: Overview
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Usage Limits {#usage-limits}

Audience Manager sets a maximum limit on the number of traits, segments, destinations, and algorithmic models that you can create for an account. Limits apply to these items whether created in the user interface or programmatically through [!DNL API] methods. Usage limits help protect Audience Manager from automated processes that may attempt to compromise our [!DNL API]s or user interface.

## ID Mapping Limits {#id-mapping-limits}

The table below lists the [ID mapping](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) limits for device IDs. Once an ID reaches any of the limits below, Audience Manager adds new ID mappings based on a FIFO (first in, first out) logic, by removing the oldest stored ID mapping, and adding the new one. Refer to [Index of IDs](../../reference/ids-in-aam.md) in Audience Manager for details on the IDs supported by Audience Manager.

|ID Mapping | Maximum Limit |
|-----------|-------------- |
|Device Advertising ID ([DAID](../../reference/ids-in-aam.md)) to Cross-device ID ([DPUUID](../../reference/ids-in-aam.md)) | 100 Device Advertising IDs ([DAID](../../reference/ids-in-aam.md)) to 1 Cross-device ID ([DPUUID](../../reference/ids-in-aam.md)) |
|Cross-device ID ([DPUUID](../../reference/ids-in-aam.md)) to Device Advertising ID ([DAID](../../reference/ids-in-aam.md)) | 10 Cross-device IDs ([DPUUID](../../reference/ids-in-aam.md)) to 1 Device Advertising ID ([DAID](../../reference/ids-in-aam.md)), per each [DPID](../../reference/ids-in-aam.md) |
|Cookie/browser ID to cookie/browser ID | 1000 cookie/browser  IDs to 1 cookie/browser ID |

## Item Limits {#item-limits}

The tables list the current limits by item type. You cannot create new traits, segments, destinations, or [!UICONTROL Algorithmic Models] if you reach a specific limit for one of these items. If you do reach a limit, you must delete an older item before you can create a new one.

### Trait Limits

| Trait Type    | Maximum Limit   |
| -------------------------- | ------------------------------------- |
| Total Traits               | 100,000   |
| Total Trait Qualifications | 150,000. For more information on trait qualification, see Trait Qualification Limit in [Trait Qualifications Reference](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit). |
| Algorithmic                | 50       |
| Rule Based                 | 100,000  |
| Onboarded                  | 100,000  |
| Folder Traits              | 2,000    |

### Segment Limits

| Segment Type   | Maximum Limit |
| -------------- | ------------- |
| Total Segments | 20,000        |

### Destination Limits

| Destination Type   | Maximum Limit |
| ------------------ | ------------- |
| Total Destinations | 1,000         |
| Cookie             | 1,000         |
| URL                | 1,000         |
| S2S                | 100           |
| Adobe Analytics    | 10            |

### Algorithmic Model Limits

| Item  | Maximum Limit |
| -------- | ----- |
| Active [!UICONTROL Look-Alike Models]  | 20. Audience Manager only counts *active* algorithmic models against the limit.|
| [!UICONTROL Look-Alike Models] maximum audience size | 25,000,000.  Note that this limit cannot be increased. You can decrease audience sizes by selecting fewer data sources for the model or by selecting a shorter look-back window. |
| Maximum number of excluded traits for a [!UICONTROL Look-Alike Model] | 500. See [Trait Exclusion in Algorithmic Modeling](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md). |
|Maximum [!UICONTROL Predictive Audiences Models]|10|
|Maximum number of baseline personas for [!UICONTROL Predictive Audiences Models]|50|

### Folder Limits

| Item | Maximum Limit|
| ------------- | ------------------ |
| Trait Folders | 2,000.  Your folder structure can be maximum 5 levels deep. |

### Derived Signals Limits

| Item            | Maximum Limit |
| --------------- | ------------- |
| Derived Signals | 50,000.       |

### Company User Accounts Limit

| Item  | Maximum Limit |
| ----------- | ------------- |
| Maximum number of user accounts for a company | 1,000.  |

## Monitor Usage {#monitor-usage}

You can see usage and limits for your account by going to **[!UICONTROL Administration > Limits]**. Access requires administrator permissions.

![usage limits image](assets/usage-limits.png)

## Increase Item Limits {#increase-item-limits}

The default limits listed here should provide enough capacity for your business needs. If your organization consistently reaches these limits, contact your account representative to discuss an increase.
