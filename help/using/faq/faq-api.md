---
description: Common API questions and issues.
seo-description: Common API questions and issues.
seo-title: API FAQ
solution: Audience Manager
title: API FAQ
uuid: 8222ebf0-b50e-4f48-8021-dbfca2828b7c
feature: API
exl-id: 9a51220e-3f53-4911-876b-16e968d44d0f
---
# API FAQ{#api-faq}

Common API questions and issues.

<!-- 

faq_api.xml

 -->

The [REST API](../api/rest-api-main/rest-api-main.md) documentation contains details about specific methods and code samples.

<br>&nbsp;

**Why does [!UICONTROL DIL] make event calls with [!UICONTROL GET] and [!UICONTROL POST] methods?**

[!UICONTROL DIL] passes data to [!DNL Audience Manager] with a `GET` or `POST` method based on the length of the query string of the event call. This behavior is built in to `GET` and `POST` methods by default. It is not specific to [!DNL Audience Manager].

* [!UICONTROL DIL] makes event calls with `GET` when a URL contains 2048 characters or less. A `GET` event call includes data in the URL as query string parameters, which are passed in as key-value pairs.

* [!UICONTROL DIL] makes event calls with `POST` when a URL contains more than 2048 characters. A `POST` event call includes data in the body of the request. [!UICONTROL DIL] puts data into key-value pairs and passes information as form data rather than in the URL query string.

Although each method passes data in a different way, this does not affect functionality. For example, with either method, [!DNL Audience Manager] still sends data to destinations, ID syncs works normally, and you can create traits from data signals.  

<br>&nbsp;

**What do the [!UICONTROL REST API]s allow me to do?**

The [!UICONTROL REST API]s let you work programmatically with most [!DNL Audience Manager] features and functions that are available in the user interface.  

<br>&nbsp;

**How do I obtain a [!UICONTROL REST API] client ID and secret?**

Contact your Partner Solutions representative to obtain [!DNL API] access credentials. Our APIs use [OAuth 2.0](https://oauth.net/2/) standards for token authentication, authorization, and renewal. See [OAuth Authentication](../api/rest-api-main/aam-api-getting-started.md#oauth) for more information.
