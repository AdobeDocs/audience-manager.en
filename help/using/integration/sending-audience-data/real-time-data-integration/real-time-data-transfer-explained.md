---
description: A general overview of how Audience Manager performs real-time data transfers with a third-party content provider.
seo-description: A general overview of how Audience Manager performs real-time data transfers with a third-party content provider.
seo-title: Real-Time Data Transfer Process Described
solution: Audience Manager
title: Real-Time Data Transfer Process Described
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: Inbound Data Transfers
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
    internal-label: Integrations
subfeature_v2:
  - id: a03b8192-8410-479f-a326-4cddf10757f6
    internal-label: Inbound data transfers
---

# Real-Time Data Transfer Process Described{#real-time-data-transfer-process-described}

A general overview of how Audience Manager performs real-time data transfers with a third-party content provider.

<!-- real-time-data-transfer-explained.xml -->

## Real-Time Data Transfers

Real-time data transfers send and receive segment IDs as a user visits or takes action on your site. Typically, synchronous data transfers are useful when you need to qualify or segment users right away, as they navigate through your inventory.

## Data Integration Steps

The real-time data integration process works as follows:

1. A user visits a customer's site that contains Audience Manager code.
1. Audience Manager loads an iframe and makes a call to our [!UICONTROL Data Collection Server] ( [!DNL DCS]).
1. The [!DNL DCS] calls the third-party server (in real time) to check if the vendor has any segment information about the user.
1. The content provider returns segment information about that user to Audience Manager.
1. Audience Manager receives this segment information and makes it available for targeting and building new traits and segments.

![](assets/rt_reduce70.png)