---
description: Server-to-server (S2S) APIs provide code and methods that let you send and receive DCS user data and work with this information in your own systems or applications.
seo-description: Server-to-server (S2S) APIs provide code and methods that let you send and receive DCS user data and work with this information in your own systems or applications.
seo-title: DCS APIs for Server-to-Server Data Transfers
solution: Audience Manager
title: DCS APIs for Server-to-Server Data Transfers
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
index: y
internal: n
snippet: y
---

# DCS APIs for Server-to-Server Data Transfers{#dcs-apis-for-server-to-server-data-transfers}

Server-to-server (S2S) APIs provide code and methods that let you send and receive DCS user data and work with this information in your own systems or applications.

## Common Use Cases {#section_76B12DEC71604E978F7CF6DD9D979F79}

[!UICONTROL Server-to-server] transfers can help you customize landing pages or other interactions based on visitor interests. Some common use cases include:

* On-site personalization: Tailor a visitor’s experience on your site by dynamically adding relevant content and calls to action based on the segments they belong to. 
* Improve customer service: Import [!DNL Audience Manager] segments into a CRM or other system through a server-to-server data transfer. This data can provide call service or on-line chat operators with relevant, personalized information about a customer.

## Requirements: User IDs and Regional Server Names {#section_0AEA56B3B3EA4AD1A461804E936A03FE}

The [!UICONTROL DCS] API requires user IDs and region IDs to validate and make data requests.

* The user ID is required because you need to associate data with a particular visitor. 
* The region ID is required to tie calls back to a server name and because user data is stored in data centers that are geographically closest to site visitors.

## Getting Started {#section_E4349EFAE12B45AC921A9DC6552B02CB}

Currently, this guide covers how to:

* Get the user and region IDs from the [!UICONTROL DCS] files you may already receive as an [!DNL Audience Manager] customer. 

* Get the user and region IDs if you use the [!DNL Visitor ID Service]. 
* Make calls to the [!UICONTROL DCS] after you have the user and region ID.

We'll add new methods as they become available. Refer to the following sections to get started. 

>[!MORE_LIKE_THIS]
>
>* [DCS API Reference](../../../c-api/dcs-intro/dcs-api-reference/dcs-api-reference.md#concept_DCDCAF1BB264442A86A2C007AD4BF366)
