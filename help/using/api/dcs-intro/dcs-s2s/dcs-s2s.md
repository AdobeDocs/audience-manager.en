---
description: Server-to-server (S2S) APIs provide code and methods that let you send and receive DCS user data and work with this information in your own systems or applications.
seo-description: Server-to-server (S2S) APIs provide code and methods that let you send and receive DCS user data and work with this information in your own systems or applications.
seo-title: DCS APIs for Server-to-Server Data Transfers
solution: Audience Manager
title: DCS APIs for Server-to-Server Data Transfers
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
---

# [!UICONTROL DCS API]s for [!UICONTROL Server-to-Server] Data Transfers{#dcs-apis-for-server-to-server-data-transfers}

Server-to-server ([!UICONTROL S2S]) [!DNL API]s provide code and methods that let you send and receive [!UICONTROL DCS] user data and work with this information in your own systems or applications.

## Common Use Cases {#common-use-cases}

[!UICONTROL Server-to-server] transfers can help you customize landing pages or other interactions based on visitor interests. Some common use cases include:

* On-site personalization: Tailor a visitor’s experience on your site by dynamically adding relevant content and calls to action based on the segments they belong to.
* Improve customer service: Import [!DNL Audience Manager] segments into a [!DNL CRM] or other system through a server-to-server data transfer. This data can provide call service or on-line chat operators with relevant, personalized information about a customer.

## Requirements: User IDs and Regional Server Names {#requirements}

The [!UICONTROL DCS API] requires user IDs and region IDs to validate and make data requests.

* The user ID is required because you need to associate data with a particular visitor.
* The region ID is required to tie calls back to a server name and because user data is stored in data centers that are geographically closest to site visitors.

## Getting Started {#getting-started}

Currently, this guide covers how to:

* Get the user and region IDs from the [!UICONTROL DCS] files you may already receive as an [!DNL Audience Manager] customer.

* Get the user and region IDs if you use the [!DNL Visitor ID Service].
* Make calls to the [!UICONTROL DCS] after you have the user and region ID.

We'll add new methods as they become available. Refer to the following sections to get started.

* [Get User IDs and Regions From a DCS Response](dcs-aam-ids.md)
* [Get User IDs and Regions Through the Experience Cloud ID...](dcs-mcid-ids.md)
* [Making Server-to-Server DCS API Calls](dcs-s2s-calls.md)

>[!MORE_LIKE_THIS]
>
>* [DCS API Reference](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)
