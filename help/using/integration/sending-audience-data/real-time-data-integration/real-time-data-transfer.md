---
description: The real-time inbound data ingestion process uses a series of HTTP requests from a user's browser to pass in data to Audience Manager.
seo-description: The real-time inbound data ingestion process uses a series of HTTP requests from a user's browser to pass in data to Audience Manager.
seo-title: Real-Time Inbound Data Ingestion
solution: Audience Manager
title: Real-Time Inbound Data Ingestion
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
---

# Real-Time Inbound Data Ingestion {#real-time-inbound-data-ingestion}

The real-time inbound data ingestion process uses a series of `HTTP` requests from a user's browser to pass in data to Audience Manager.

<!-- c_rt_inbound_real_time.xml -->

Inbound data should be formatted as key-value pairs called signals. Typically, each signal is mapped to a segment created or managed through the user interface or [!DNL API].

## [!DNL URL] String Parameters and Syntax {#section_B804B3485D61445BB3908870EF7C60BF}

The [!DNL URL] for an inbound data transfer should contain the variables described below. Remember to [create traits](../../../features/traits/create-onboarded-rule-based-traits.md#concept_98DD94EF9AA24422BA17B8D0760542DF) and a [folder structure](../../../features/traits/trait-storage.md#create-trait-storage-folder) in the [!DNL Audience Manager] UI before setting up real-time data transfers.

>[!NOTE]
>
>Replace italicized content with actual parameter values.

|  Parameter  | Description  |
|---|---|
| `<KEY>`  | A unique identifier in a key-value pair (e.g., gender, color, price).  |
| `<VAL>`  | A variable that belongs to the data set defined by the key (e.g., gender=male, color=green, price=100)  |

### [!DNL URL] Syntax

During a real-time inbound data ingestion process, a properly formatted [!DNL URL] string uses the following syntax:

```

https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC

```