---
description: Information about general requirements, authentication, optional query parameters, request URLs, and other references.
seo-description: Information about general requirements, authentication, optional query parameters, request URLs, and other references.
seo-title: Getting Started with REST APIs
solution: Audience Manager
title: Getting Started with REST APIs
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
---

# Getting Started with REST APIs {#getting-started-with-rest-apis}

Information about general requirements, authentication, optional query parameters, request URLs, and other references.

<!-- c_rest_api_overview.xml -->

## [!DNL API] Requirements and Recommendations {#concept_A7FAC9443CF34974A873E6B787616421}

Things you must and should do when working with the Audience Manager [!DNL API]s.

## Requirements {#section_42B2E4780AD440C58A25ED0FBC50B78A}

<!-- aam-api-requirements.xml -->

Note the following when working with [Audience Manager API](https://bank.demdex.com/portal/swagger/index.html#/) code:

* **Request parameters:** All request parameters are required unless specified otherwise.
* **[!DNL JSON] content type:** Specify `content-type: application/json` *and* `accept: application/json` in your code.

* **Requests and responses:** Send requests as a properly formatted [!DNL JSON] object. [!DNL Audience Manager] responds with [!DNL JSON] formatted data. Server responses can contain requested data, a status code, or both.

* **Access:** Your [!DNL Audience Manager] consultant will provide you with a client ID and key that lets you make [!DNL API] requests.

* **Documentation and code samples:** Text in *italics* represents a variable that you provide or pass in when making or receiving [!DNL API] data. Replace *italicised* text with your own code, parameters, or other required information.

## Recommendations: Create a Generic API User {#section_F520E4C007904BB78EC694E5A9A46E0A}

We recommend you create a separate, technical user account for working with the Audience Manager [!DNL API]s. This is a generic account that is not tied to or associated with a specific user in your organization. This type of [!DNL API] user account helps you accomplish 2 things:

* Identify what service is calling the [!DNL API] (e.g., calls from your apps that use our [!DNL API]s or from other tools that make [!DNL API] requests).
* Provide uninterrupted access to the [!DNL API]s. An account tied to a specific person may be deleted when they leave your company. This will prevent you from working with the available [!DNL API] code. A generic account that's not tied to a particular employee helps you avoid this problem.

As an example or use case for this type of account, let's say you want to change a lot of segments at once with the [Bulk Management Tools](../../reference/bulk-management-tools/bulk-management-intro.md). Well, to do this, your user account needs [!DNL API] access. Rather than add permissions to a specific user, create a non-specific, [!DNL API] user account that has the appropriate credentials, key, and secret to make [!DNL API] calls. This is also useful if you develop your own applications that use the Audience Manager [!DNL API]s.

Work with your Audience Manager consultant to set up a generic, [!DNL API]-only user account.

## [!DNL OAuth] Authentication {#concept_426EEF5C102049B08C8ECF90FCB41796}

The Audience Manager [!UICONTROL REST API] follows [!DNL OAuth 2.0] standards for token authentication and renewal. The sections below describe how to authenticate and start working with the [!DNL API]s.

## Password Authentication Workflow {#section_E8C9602AFAAC45D782D72E8ED7F5EFB1}

<!-- oath-authentication.xml -->

Password authentication secure access our [!DNL REST API]. The steps below outline the workflow for password authentication from a [!DNL JSON] client in your browser.

>[!TIP]
>
>Encrypt access and refresh tokens if you store them in a database.

### Step 1: Request API Access

Contact your Partner Solutions manager. They will provide you with an [!DNL API] client ID and secret. The ID and secret authenticate you to the [!DNL API].

Note: If you'd like to receive a refresh token, specify that when you request [!DNL API] access.

### Step 2: Request the Token

Pass in a token request with your preferred [!DNL JSON] client. When you build the request:

* Use a `POST` method to call `https://api.demdex.com/oauth/token`.
* Convert your client ID and secret to a base-64 encoded string. Separate the ID and secret with a colon during the conversion process. For example, the credentials `testId : testSecret` convert to `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Pass in the [!DNL HTTP] headers `Authorization:Basic <base-64 clientID:clientSecret>` and `Content-Type: application/x-www-form-urlencoded` . For example, your header could look like this: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Set up the request body as follows:
  <br/> `grant\_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

### Step 3: Receive the Token

The [!DNL JSON] response contains your access token. The response should look like this:

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

The "expires\_in" key represents the number of seconds until the access token expires. As best practice, use short expiration times to limit exposure if the token is ever exposed.

## Refresh Token {#section_6671766BA28A4EADB5925F56267B343E}

Refresh tokens renew [!DNL API] access after the original token expires. If requested, the response [!DNL JSON] in the password workflow includes a refresh token. If you don't receive a refresh token, create a new one through the password authentication process.

You can also use a refresh token to generate a new token before the existing access token expires.

If your access token has expired, you receive a `401 Status Code` and the following header in the response:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

The following steps outline the workflow for using a refresh token to create a new access token from a [!DNL JSON] client in your browser.

### Step 1: Request the New Token

Pass in a refresh token request with your preferred [!DNL JSON] client. When you build the request:

* Use a `POST` method to call `https://api.demdex.com/oauth/token`.
* Convert your client ID and secret to a base-64 encoded string. Separate the ID and secret with a colon during the conversion process. For example, the credentials `testId : testSecret` convert to `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Pass in the HTTP headers `Authorization:Basic <base-64 clientID:clientSecret>` and `Content-Type: application/x-www-form-urlencoded`. For example, your header could look like this: <br/> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/> `Content-Type: application/x-www-form-urlencoded`
* In the request body, specify the `grant\_type:refresh\_token` and pass in the refresh token you received in your previous access request. The request should look like this: <br/> `grant\_type=refresh\_token&refresh\_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

### Step 2: Receive the New Token

The [!DNL JSON] response contains your new access token. The response should look like this:

```json
{
    "access_token": "4fdfc261-2ffc-4fb7-8dbd-64221714c45f",
    "token_type": "bearer",
    "refresh_token": "295fa487-1825-4caa-a715-80b81ac17dae",
    "expires_in": 21922,
    "scope": "read write"
}
```

## Authorization Code and Implicit Authentication {#section_315C16DF045C4E73B81426CD98EA730B}

The Audience Manager [!UICONTROL REST API] supports authorization code and implicit authentication. To use these access methods, your users need to log in to `https://api.demdex.com/oauth/authorize` to get access and refresh tokens.

>[!MORE_LIKE_THIS]
>
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2 Simplified](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

## Make Authenticated API Requests {#concept_1A4B53C4554C4B0396499997EECCBDB9}

Requirements for calling [!DNL API] methods after you receive an authentication token.

<!-- c_oauth_call_methods.xml -->

To make calls against the available [!DNL API] methods:

* In the `HTTP` header, set `Authorization: Bearer <token>`.
* Call the required [!DNL API] method.

>[!MORE_LIKE_THIS]
>
>* [OAuth Authentication](../../api/rest-api-main/aam-api-getting-started.md#concept_426EEF5C102049B08C8ECF90FCB41796)

## Optional API Query Parameters {#concept_BB1E73AE736F4F54830E6CAF28089608}

Set the optional parameters available to methods that return all properties for an object.

<!-- c_rest_api_optional.xml -->

You can use these optional parameters with [!DNL API] methods that return *all* properties for an object. Set these options in the request string when passing that query in to the [!DNL API].

| Parameter | Description |
|--- |--- |
|page|Returns results by page number. Numbering starts at 0.|
|pageSize|Sets the number of response results returned by the request (10 is default).|
|sortBy|Sorts and returns results according to the specified [!DNL JSON] property.|
|descending|Sorts and returns results in descending order. Ascending is default.|
|search|Returns results based on the specified string you want to use as a search parameter. For example, let's say you want to find results for all models that have the word "Test" in any of the value fields for that item. Your sample request could look like this:   `GET https://api.demdex.com/v1/models/?search=Test`.  You can search on any value returned by a "get all" method.|
|folderId|Returns all the IDs for traits inside the specified folder. Not available to all methods.|
|permissions|Returns a list of segments based on the specified permission.  READ  is default. Permissions include:<ul><li>`READ` : Return and view information about a segment.</li><li>`WRITE` : Use  `PUT`  to update a segment.</li><li>`CREATE` : Use  `POST`  to create a segment.</li><li>`DELETE` : Delete a segment. Requires access to underlying traits, if any. For example, you'll need rights to delete the traits that belong to a segment if you want to remove it.</li></ul><br>Specify multiple permissions with separate key-value pairs. For example, to return a list of segments with  `READ`  and  `WRITE`  permissions only, pass in  `"permissions":"READ"`, `"permissions":"WRITE"` .|
|includePermissions|(Boolean) Set to  true  to return your permissions for the segment. Default is  false.|

### A Note About Page Options

When page information *is not* specified, the request returns plain [!DNL JSON] results in an array. If page information *is* specified, then the returned list is wrapped in a [!DNL JSON] object that contains information about the total result and current page. Your sample request using page options could look similar to this:

```
GET https://api.demdex.com/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API] URLs {#reference_B6E2ECCB46834DF597BBAE3BEBD7BE4D}

[!DNL URLs] for requests, staging and production environments, and versions.

<!-- r_rest_urls.xml -->

## Request URLs {#section_2DBA5BD10E8B4E0DBD51BD36055C5013}

The following table lists the request URLs used to pass in [!DNL API] requests, by method.

| [!DNL API] Methods | Request [!DNL URL] |
|--- |--- |
|Algorithmic Modeling|`https://api.demdex.com/v1/models/`|
|Data Source|`https://api.demdex.com/v1/datasources/`|
|Derived Signals|`https://api.demdex.com/v1/signals/derived/`|
|Destinations|`https://api.demdex.com/v1/destinations/`|
|Domains|`https://api.demdex.com/v1/partner-sites/`|
|Folders|Traits:  `https://api.demdex.com/v1/folders/traits /`<br>Segments:  `https://api.demdex.com/v1/folders/segments /`|
|Schema|`https://api.demdex.com/v1/schemas/`|
|Segments|`https://api.demdex.com/v1/segments/`|
|Traits|`https://api.demdex.com/v1/traits/`|
|Trait Types|`https://api.demdex.com/v1/customer-trait-types`|
|Taxonomy|`https://api.demdex.com/v1/taxonomies/0/`|

## Environments {#section_5B33F1445F9C49C896C4E9240B5F0CCD}

The [!DNL Audience Manager] [!DNL API]s provide access to different working environments. These environments help you test code against separate databases without affecting live, production data. The following table lists the available [!DNL API] environments and corresponding resource hostnames.

|  Environment  | Hostname  |
|---|---|
|  **Production** | `https://api.demdex.com/...`  |
|  **Beta** | `https://api-beta.demdex.com/...`  |

>[!NOTE]
>
>The Audience Manager beta environment is a smaller-scale, standalone version of the production environment. All the data that you want to test must be entered and collected in this environment.

## Versions {#section_473AE7014EE949E7AD868AB357452673}

New versions of these [!DNL API]s are released on a regular schedule. A new release increments the [!DNL API] version number. The version number is referenced in the request URL as `v<version number>` as shown in the following example:

`https://<host>/v1/...`

## Response Codes Defined {#reference_2AC89154A26E49A48E0DDD8DA520757F}

`HTTP` status codes and response text returned by the Audience Manager [!UICONTROL REST API].

<!-- r_api_http_response_codes.xml -->

|  Response code ID  | Response text  | Definition  |
|---|---|---|
|  200  | OK  | The request processed successfully. Will return expected content or data if required.  |
|  201  | Created  | The resource was created. Returns for `PUT` and `POST` requests.  |
|  204  | No Content  | The resource has been deleted. The response body will be blank.  |
|  400  | Bad Request  | The server did not understand the request. Usually due to malformed syntax. Check your request and try again.  |
|  403  | Forbidden  | You do not have access to the resource.  |
|  404  | Not Found  | The resource could not be found for the specified path.  |
|  409  | Conflict  | The request could not be completed due to a conflict with the state of the resource.  |
|  500  | Server Error  | The server encountered an unexpected error that prevented it from fulfilling the request.  |