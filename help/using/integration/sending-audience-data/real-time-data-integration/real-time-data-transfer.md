---
description: The real-time inbound data ingestion process uses a series of HTTP requests from a user's browser to pass in data to Audience Manager.
seo-description: The real-time inbound data ingestion process uses a series of HTTP requests from a user's browser to pass in data to Audience Manager.
seo-title: Real-Time Inbound Data Ingestion
solution: Audience Manager
title: Real-Time Inbound Data Ingestion
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
feature: Inbound Data Transfers
exl-id: d243c74c-3a29-4dbf-a4c7-43ea526a9d7b
TQID: https://experienceleague.adobe.com/ps6Iks-zvDnIIEagSND0LEnW18K6odtuwIJOsBfp2v0
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
    internal-label: Implementation
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
---
# Real-Time Inbound Data Ingestion {#real-time-inbound-data-ingestion}

The real-time inbound data ingestion process uses a series of `HTTP` requests from a user's browser to pass in data to Audience Manager.

<!-- c_rt_inbound_real_time.xml -->

Inbound data should be formatted as key-value pairs called signals. Typically, each signal is mapped to a segment created or managed through the user interface or [!DNL API].

## URL String Parameters and Syntax {#url-string-syntax}

The [!DNL URL] for an inbound data transfer should contain the variables described below. Remember to [create traits](../../../features/traits/create-onboarded-rule-based-traits.md) and a [folder structure](../../../features/traits/trait-storage.md#create-trait-storage-folder) in the [!DNL Audience Manager] UI before setting up real-time data transfers.

>[!NOTE]
>
>Replace italicized content with actual parameter values.

|  Parameter  | Description  |
|---|---|
| `<KEY>`  | A unique identifier in a key-value pair (e.g., gender, color, price).  |
| `<VAL>`  | A variable that belongs to the data set defined by the key (e.g., gender=male, color=green, price=100)  |

### URL Syntax

During a real-time inbound data ingestion process, a properly formatted [!DNL URL] string uses the following syntax:

```

https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC

```
