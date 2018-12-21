---
description: A general overview of how Audience Manager performs real-time data transfers with a third-party content provider.
seo-description: A general overview of how Audience Manager performs real-time data transfers with a third-party content provider.
seo-title: Real-Time Data Transfer Process Described
solution: Audience Manager
title: Real-Time Data Transfer Process Described
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
---

# Real-Time Data Transfer Process Described{#real-time-data-transfer-process-described}

A general overview of how Audience Manager performs real-time data transfers with a third-party content provider.

<!-- 

real-time-data-transfer-explained.xml

 -->

## Real-Time Data Transfers

Real-time data transfers send and receive segment IDs as a user visits or takes action on your site. Typically, synchronous data transfers are useful when you need to qualify or segment users right away, as they navigate through your inventory.

## Data Integration Steps

The real-time data integration process works as follows:

1. A user visits a customer's site that contains Audience Manager code. 
1. Audience Manager loads an iframe and makes a call to our [!UICONTROL Data Collection Server] ( [!UICONTROL DCS]). 

1. The [!UICONTROL DCS] calls the third-party server (in real time) to check if the vendor has any segment information about the user. 
1. The content provider returns segment information about that user to Audience Manager. 
1. Audience Manager receives this segment information and makes it available for targeting and building new traits and segments.

![](assets/rt_reduce70.png)

