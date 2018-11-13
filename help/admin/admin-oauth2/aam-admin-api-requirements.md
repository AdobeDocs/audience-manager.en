---
description: Things you should encourage your clients to be aware of when they're working with the Audience Manager APIs.
seo-description: Things you should encourage your clients to be aware of when they're working with the Audience Manager APIs.
seo-title: API Requirements and Recommendations
title: API Requirements and Recommendations
uuid: eba9cf92-f0c8-4394-8532-0de9a2e7b103
index: y
internal: n
snippet: y
---

# API Requirements and Recommendations{#api-requirements-and-recommendations}

Things you should encourage your clients to be aware of when they're working with the Audience Manager APIs.

## Requirements {#section_42B2E4780AD440C58A25ED0FBC50B78A}

Note the following when working with [!DNL Audience Manager] API code:

* **Request parameters:** All request parameters are required unless specified otherwise. 
* **JSON content type:** Specify `content-type: application/json` *and* `accept: application/json` in your code. 

* **Requests and responses:** Send requests as a properly formatted [!DNL JSON] object. [!DNL Audience Manager] responds with [!DNL JSON] formatted data. Server responses can contain requested data, a status code, or both. 

* **Access:** Your [!DNL Audience Manager] consultant will provide you with a client ID and key that lets you make API requests. 

* **Documentation and code samples:** Text in *italics* represents a variable that you provide or pass in when making or receiving API data. Replace *italicised* text with your own code, parameters, or other required information.

## Recommendations: Create a Generic API User {#section_F520E4C007904BB78EC694E5A9A46E0A}

We recommend creating a separate, technical user account for working with the Audience Manager APIs. This is a generic account that is not tied to or associated with a specific user in your client's organization. This type of API user account helps accomplish 2 things:

* Identify what service is calling the API (e.g., calls from a client app that use our APIs or from making bulk changes) 
* Provide uninterrupted access to the APIs. An account tied to a specific employee may be deleted when they leave company. This will prevent your customers from working with the available API code. A generic account that's not tied to a particular employee helps avoid this problem.

As an example or use case for this type of account, let's say your customers want to change a lot of segments at once with the [Bulk Management Tools](https://marketing.adobe.com/resources/help/en_US/aam/c_bulk.html). Well, to do this, they need API access. Rather than add permissions to a specific user, create a non-specific, API user account that has the appropriate credentials, key, and secret to make API calls. This is also useful if client's develop their own applications that use the [!DNL Audience Manager] APIs. 
