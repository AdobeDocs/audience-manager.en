---
description: A general overview of how Audience Manager performs an asynchronous batch data exchange with a third-party vendor.
seo-description: A general overview of how Audience Manager performs an asynchronous batch data exchange with a third-party vendor.
seo-title: Batch Data Transfer Process Described
solution: Audience Manager
title: Batch Data Transfer Process Described
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
feature: Inbound Data Transfers
exl-id: e02dcc9a-4010-4c01-bd6b-ad04b8029f18
TQID: https://experienceleague.adobe.com/HXA9Ql-ulLQ8itnnGnwMuk82nFRZnrFYaOGniGNDgn8
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
    internal-label: Implementation
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
    internal-label: Data integration
---
# Batch Data Transfer Process Described {#batch-data-transfer-process-described}

A general overview of how [!DNL Audience Manager] performs an asynchronous batch data exchange with a third-party vendor.

## Batch Data Integration

<!-- c_async.xml -->

The batch data integration process saves visitor information on our servers and synchronizes that material with data sent by a provider at regular intervals. The asynchronous data transfer process is useful when:

* Immediate data transfers are not required.
* Collecting data to build a large pool of segmented users.
* You want to reduce data discrepancies and `HTTP` calls from the browser.

![](assets/s2s_70.png)

## Data Integration Steps

1. A user visits a customer site.
1. [!DNL Audience Manager] and the third-party data provider assign the visitor a unique ID (usually with a cookie).
1. [!DNL Audience Manager] calls the third-party data provider to match visitor IDs.
1. A scheduled request, usually on a daily interval, exchanges visitor segment data between [!DNL Audience Manager] and your third-party data provider.
1. Whenever an inbound [!UICONTROL Server-to-Server] file is processed, a receipt is sent via email to partner solutions and, if configured, to the partner. For more information, see [Sample Message to Partners after Inbound Processing](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).
