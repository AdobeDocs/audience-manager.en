---
description: Things you must and should do when working with the Audience Manager APIs.
seo-description: Things you must and should do when working with the Audience Manager APIs.
seo-title: API Requirements and Recommendations
solution: Audience Manager
title: API Requirements and Recommendations
uuid: bb952546-f0f1-45dd-88ef-278999589e0f
index: y
internal: n
snippet: y
translate: y
---

# API Requirements and Recommendations


## Requirements {#section_42B2E4780AD440C58A25ED0FBC50B78A}

Note the following when working with [ [!DNL  Audience Manager] API](https://bank.demdex.com/portal/swagger/index.html#/) code: 

* **Request parameters:** All request parameters are required unless specified otherwise.
* **JSON content type:** Specify ` content-type: application/json` *and* ` accept: application/json` in your code.
* **Requests and responses:** Send requests as a properly formatted JSON object. [!DNL  Audience Manager] responds with JSON formatted data. Server responses can contain requested data, a status code, or both.
* **Access:** Your [!DNL  Audience Manager] consultant will provide you with a client ID and key that lets you make API requests.
* **Documentation and code samples:** Text in *italics* represents a variable that you provide or pass in when making or receiving API data. Replace *italicised* text with your own code, parameters, or other required information.

## Recommendations: Create a Generic API User {#section_F520E4C007904BB78EC694E5A9A46E0A}

We recommend you create a separate, technical user account for working with the Audience Manager APIs. This is a generic account that is not tied to or associated with a specific user in your organization. This type of API user account helps you accomplish 2 things: 

* Identify what service is calling the API (e.g., calls from your apps that use our APIs or from other tools that make API requests).
* Provide uninterrupted access to the APIs. An account tied to a specific person may be deleted when they leave your company. This will prevent you from working with the available API code. A generic account that's not tied to a particular employee helps you avoid this problem.
As an example or use case for this type of account, let's say you want to change a lot of segments at once with the [ Bulk Management Tools](../../../c_reference/c_bulk/c_bulk.md#concept_8D6CB301643C482F994938F6484B390C). Well, to do this, your user account needs API access. Rather than add permissions to a specific user, create a non-specific, API user account that has the appropriate credentials, key, and secret to make API calls. This is also useful if you develop your own applications that use the [!DNL  Audience Manager] APIs. 

Work with your [!DNL  Audience Manager] consultant to set up a generic, API-only user account. 
