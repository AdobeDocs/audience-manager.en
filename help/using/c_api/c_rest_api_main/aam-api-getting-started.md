---
description: Information about general requirements, authentication, optional query parameters, request URLs, and other references.
seo-description: Information about general requirements, authentication, optional query parameters, request URLs, and other references.
seo-title: Getting Started with REST APIs
solution: Audience Manager
title: Getting Started with REST APIs
uuid: 64dc1971-23ed-4a83-8c4d-65c26dbffb4c
index: y
internal: n
snippet: y
translate: y
---

# Getting Started with REST APIs

Information about general requirements, authentication, optional query parameters, request URLs, and other references.

## Getting Started with REST APIs {#concept_2745BC64D5BD43A49DA6020E42280863}

Information about general requirements, authentication, optional query parameters, request URLs, and other references.




<!-- c_rest_api_overview.xml -->

## API Requirements and Recommendations {#concept_A7FAC9443CF34974A873E6B787616421}

Things you must and should do when working with the Audience Manager APIs.


## Requirements {#section_42B2E4780AD440C58A25ED0FBC50B78A}




<!-- aam-api-requirements.xml -->
Note the following when working with [ [!DNL Audience Manager] API ](https://bank.demdex.com/portal/swagger/index.html#/) code: 

* **Request parameters:** All request parameters are required unless specified otherwise.
* **JSON content type:** Specify `content-type: application/json` *and* `accept: application/json` in your code.
* **Requests and responses:** Send requests as a properly formatted JSON object. [!DNL Audience Manager] responds with JSON formatted data. Server responses can contain requested data, a status code, or both.
* **Access:** Your [!DNL Audience Manager] consultant will provide you with a client ID and key that lets you make API requests.
* **Documentation and code samples:** Text in *italics* represents a variable that you provide or pass in when making or receiving API data. Replace *italicised* text with your own code, parameters, or other required information.



## Recommendations: Create a Generic API User {#section_F520E4C007904BB78EC694E5A9A46E0A}



We recommend you create a separate, technical user account for working with the Audience Manager APIs. This is a generic account that is not tied to or associated with a specific user in your organization. This type of API user account helps you accomplish 2 things: 

* Identify what service is calling the API (e.g., calls from your apps that use our APIs or from other tools that make API requests).
* Provide uninterrupted access to the APIs. An account tied to a specific person may be deleted when they leave your company. This will prevent you from working with the available API code. A generic account that's not tied to a particular employee helps you avoid this problem.




As an example or use case for this type of account, let's say you want to change a lot of segments at once with the [Bulk Management Tools](../../reference/bulk-management-tools/bulk-management-tools.md#concept_8D6CB301643C482F994938F6484B390C). Well, to do this, your user account needs API access. Rather than add permissions to a specific user, create a non-specific, API user account that has the appropriate credentials, key, and secret to make API calls. This is also useful if you develop your own applications that use the [!DNL Audience Manager] APIs. 


Work with your [!DNL Audience Manager] consultant to set up a generic, API-only user account. 

## OAuth Authentication {#concept_426EEF5C102049B08C8ECF90FCB41796}

The Audience Manager REST API follows OAuth 2.0 standards for token authentication and renewal. The sections below describe how to authenticate and start working with the APIs.


## Password Authentication Workflow {#section_E8C9602AFAAC45D782D72E8ED7F5EFB1}




<!-- oath-authentication.xml -->
Password authentication secure access our REST API. The following table outlines the workflow for password authentication from a JSON client in your browser.



>[!TIP]
>
>Encrypt access and refresh tokens if you store them in a database.





<table id="table_BC7346F48EA74541A43A8157A7EC7346"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Process Step </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <b>Request API Access</b> </td> 
   <td colname="col2"> <p>Contact your Partner Solutions manager. They will provide you with an API client ID and secret. The ID and secret authenticate you to the API. <p>Note:  If you'd like to receive a refresh token, specify that when you request API access. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Request the Token</b> </td> 
   <td colname="col2"> <p>Pass in a token request with your preferred JSON client. When you build the request: 
     <ul id="ul_D34AF5AAF8C94148823A33EE1340CECC"> 
      <li id="li_DC7A0B98B1824BF996CD85B822F9B6A6">Use a <span class="codeph"> POST </span> method to call <span class="codeph"> https://api.demdex.com/oauth/token </span>. </li> 
      <li id="li_07DBC364F32748D4A8471A849C321A0A">Convert your client ID and secret to a base-64 encoded string. Separate the ID and secret with a colon during the conversion process. For example, the credentials <span class="codeph"> testId </span>: <span class="codeph"> testSecret </span> convert to <span class="codeph"> dGVzdElkOnRlc3RTZWNyZXQ= </span>. </li> 
      <li id="li_F525D6C394D74246AF68C9F5496174D1">Pass in the HTTP headers <span class="codeph"> Authorization:Basic <span class="varname"> &lt;base-64 clientID:clientSecret&gt; </span> </span> and <span class="codeph"> Content-Type: application/x-www-form-urlencoded </span>. For example, your header could look like this: 
       <codeblock>
         Authorization:&nbsp;Basic&nbsp;dGVzdElkOnRlc3RTZWNyZXQ= 
        Content-Type:&nbsp;application/x-www-form-urlencoded 
       </codeblock> </li> 
      <li id="li_3A638183F3C343759642EB405E5AEF1B">Set up the request body as follows: 
       <codeblock>
         grant_type=password&amp;username= 
        <span class="varname"> &lt;your&amp;nbsp;AudienceManager&amp;nbsp;user&amp;nbsp;name&gt;&amp; </span> 
        password= 
        <span class="varname"> &lt;your&amp;nbsp;AudienceManager&amp;nbsp;password&gt; </span> 
       </codeblock> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Receive the Token</b> </td> 
   <td colname="col2"> <p>The JSON response contains your access token. The response should look like this: 
     <codeblock>
       { 
      &nbsp;&nbsp;&nbsp;&nbsp;"access_token":&nbsp;"28fed402-eafd-456c-9341-ac753f25bbbc", 
      &nbsp;&nbsp;&nbsp;&nbsp;"token_type":&nbsp;"bearer", 
      &nbsp;&nbsp;&nbsp;&nbsp;"refresh_token":&nbsp;"b27122c0-b0c7-4b39-a71b-1547a3b3b88e", 
      &nbsp;&nbsp;&nbsp;&nbsp;"expires_in":&nbsp;21922, 
      &nbsp;&nbsp;&nbsp;&nbsp;"scope":&nbsp;"read&nbsp;write" 
      } 
     </codeblock> </p> <p>The <span class="codeph"> "expires_in" </span> key represents the number of seconds until the access token expires. As best practice, use short expiration times to limit exposure if the token is ever exposed. </p> </td> 
  </tr> 
 </tbody> 
</table>


## Refresh Token {#section_6671766BA28A4EADB5925F56267B343E}



Refresh tokens renew API access after the original token expires. If requested, the response JSON in the password workflow includes a refresh token. If you don't receive a refresh token, create a new one through the password authentication process. 


You can also use a refresh token to generate a new token before the existing access token expires. 


If your access token has expired, you receive a `401 Status Code` and the following header in the response: 


`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"` 


The following table outlines the workflow for using a refresh token to create a new access token from a JSON client in your browser. 




<table id="table_875413EA6F124BBD831194D785A774DB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Process Step </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <b>Request the New Token</b> </td> 
   <td colname="col2"> <p>Pass in a refresh token request with your preferred JSON client. When you build the request: 
     <ul id="ul_49608127094F42A69886A66B85F87B0E"> 
      <li id="li_0244743C33DB4BB7A3AB19064C22B44E">Use a <span class="codeph"> POST </span> method to call <span class="codeph"> https://api.demdex.com/oauth/token </span>. </li> 
      <li id="li_88BC61A4393542D3B3B7FB25156B1FB3">Convert your client ID and secret to a base-64 encoded string. Separate the ID and secret with a colon during the conversion process. For example, the credentials <span class="codeph"> testId </span>: <span class="codeph"> testSecret </span> convert to <span class="codeph"> dGVzdElkOnRlc3RTZWNyZXQ= </span>. </li> 
      <li id="li_06CFB45DA2C84859ADE6591218E413F1">Pass in the HTTP headers <span class="codeph"> Authorization:Basic <span class="varname"> &lt;base-64 clientID:clientSecret&gt; </span> </span> and <span class="codeph"> Content-Type: application/x-www-form-urlencoded </span>. For example, your header could look like this: 
       <codeblock>
         Authorization:&nbsp;Basic&nbsp;dGVzdElkOnRlc3RTZWNyZXQ= 
        Content-Type:&nbsp;application/x-www-form-urlencoded 
       </codeblock> </li> 
      <li id="li_14595B35956D4876BE8661BB7FFC0839">In the request body, specify the <span class="codeph"> grant_type:refresh_token </span> and pass in the refresh token you received in your previous access request. The request should look like this: 
       <codeblock>
         grant_type=refresh_token&amp;refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e 
       </codeblock> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Receive the New Token</b> </td> 
   <td colname="col2"> <p>The JSON response contains your new access token. The response should look like this: 
     <codeblock>
       { 
      &nbsp;&nbsp;&nbsp;&nbsp;"access_token":&nbsp;"4fdfc261-2ffc-4fb7-8dbd-64221714c45f", 
      &nbsp;&nbsp;&nbsp;&nbsp;"token_type":&nbsp;"bearer", 
      &nbsp;&nbsp;&nbsp;&nbsp;"refresh_token":&nbsp;"295fa487-1825-4caa-a715-80b81ac17dae", 
      &nbsp;&nbsp;&nbsp;&nbsp;"expires_in":&nbsp;21922, 
      &nbsp;&nbsp;&nbsp;&nbsp;"scope":&nbsp;"read&nbsp;write" 
      } 
     </codeblock> </p> </td> 
  </tr> 
 </tbody> 
</table>


## Authorization Code and Implicit Authentication {#section_315C16DF045C4E73B81426CD98EA730B}



The Audience Manager REST API supports authorization code and implicit authentication. To use these access methods, your users need to log in to `https://api.demdex.com/oauth/authorize` to get access and refresh tokens. 
>[!MORE_LIKE_THIS]
>
>* [OAuth 2.0](http://oauth.net/2/)
>* [OAuth 2 Simplified](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

## Make Authenticated API Requests {#concept_1A4B53C4554C4B0396499997EECCBDB9}

Requirements for calling API methods after you receive an authentication token.




<!-- c_oauth_call_methods.xml -->
To make calls against the available API methods:

* In the HTTP header, set **** ` Authorization: Bearer *`<token>`*`.
* Call the required API method.


>[!MORE_LIKE_THIS]
>
>* [OAuth Authentication](aam-api-getting-started.md#concept_426EEF5C102049B08C8ECF90FCB41796)

## Optional API Query Parameters {#concept_BB1E73AE736F4F54830E6CAF28089608}

Set the optional parameters available to methods that return all properties for an object.




<!-- c_rest_api_optional.xml -->
You can use these optional parameters with API methods that return*all* properties for an object. Set these options in the request string when passing that query in to the API. 

<table id="table_B05A8EE22C9A4C72B84A8479E1AB7D0A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> page </span> </td> 
   <td colname="col2"> Returns results by page number. Numbering starts at 0. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> pageSize </span> </td> 
   <td colname="col2"> Sets the number of response results returned by the request (10 is default). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> sortBy </span> </td> 
   <td colname="col2"> Sorts and returns results according to the specified JSON property. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> descending </span> </td> 
   <td colname="col2"> Sorts and returns results in descending order. Ascending is default. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> search </span> </td> 
   <td colname="col2"> Returns results based on the specified string you want to use as a search parameter. For example, let's say you want to find results for all models that have the word "Test" in any of the value fields for that item. Your sample request could look like this: <p> <span class="codeph"> GET https://api.demdex.com/v1/models/?search=Test </span>. </p> <p>You can search on any value returned by a "get all" method. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> folderId </span> </td> 
   <td colname="col2"> Returns all the IDs for traits inside the specified folder. Not available to all methods. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> permissions </span> </td> 
   <td colname="col2"> <p>Returns a list of segments based on the specified permission. <span class="codeph"> READ </span> is default. Permissions include: 
     <ul id="ul_389EA328C64448F0BC76E80E13CAB406"> 
      <li id="li_339A737BC71646699AA337A2243CF992"> <span class="codeph"> READ </span>: Return and view information about a segment. </li> 
      <li id="li_18EF54637F6849D1A72EEE9FB60E3E5F"> <span class="codeph"> WRITE </span>: Use <span class="codeph"> PUT </span> to update a segment. </li> 
      <li id="li_8903069EC759441FACBA2C2922A02CA2"> <span class="codeph"> CREATE </span>: Use <span class="codeph"> POST </span> to create a segment. </li> 
      <li id="li_50F95EE7A08D469F97A555E4AEF7F1EE"> <span class="codeph"> DELETE </span>: Delete a segment. Requires access to underlying traits, if any. For example, you'll need rights to delete the traits that belong to a segment if you want to remove it. </li> 
     </ul> </p> <p>Specify multiple permissions with separate key-value pairs. For example, to return a list of segments with <span class="codeph"> READ </span> and <span class="codeph"> WRITE </span> permissions only, pass in <span class="codeph"> "permissions":"READ", "permissions":"WRITE" </span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> includePermissions </span> </td> 
   <td colname="col2"> <p>(Boolean) Set to <span class="codeph"> true </span> to return your permissions for the segment. Default is <span class="codeph"> false </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>



**A Note About Page Options** 


When page information *is not* specified, the request returns plain JSON results in an array. If page information *is* specified, then the returned list is wrapped in a JSON object that contains information about the total result and current page. Your sample request using page options could look similar to this: 
```
GET https://api.demdex.com/v1/models/?page=1&pageSize=2&search=Test
```

## API URLs {#reference_B6E2ECCB46834DF597BBAE3BEBD7BE4D}

URLs for requests, staging and production environments, and versions.





<!-- r_rest_urls.xml -->


## Request URLS {#section_2DBA5BD10E8B4E0DBD51BD36055C5013}

The following table lists the request URLs used to pass in API requests, by method.

<table id="table_C174E7230F6F4D55AC6515FBDBDD265B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API Methods </th> 
   <th colname="col2" class="entry"> Request URL </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <b>Algorithmic Modeling</b> </td> 
   <td colname="col2"> <span class="codeph"> https://api.demdex.com/v1/models/ </span> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Data Source</b> </td> 
   <td colname="col2"> <span class="codeph"> https://api.demdex.com/v1/datasources/ </span> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Derived Signals</b> </td> 
   <td colname="col2"> <span class="codeph"> https://api.demdex.com/v1/signals/derived/ </span> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Destinations</b> </td> 
   <td colname="col2"> <span class="codeph"> https://api.demdex.com/v1/destinations/ </span> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Domains</b> </td> 
   <td colname="col2"> <span class="codeph"> https://api.demdex.com/v1/partner-sites/ </span> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Folders</b> </td> 
   <td colname="col2"> 
    <ul id="ul_DF2B28E0D85340398D6E00B0BBC2B9B4"> 
     <li id="li_271CAE6807EB4428A77C26F60EFE813D">Traits: <span class="codeph"> https://api.demdex.com/v1/folders/traits </span>/ </li> 
     <li id="li_B3CE481EAA7B4E1E9DD7857A9E5BF297">Segments: <span class="codeph"> https://api.demdex.com/v1/folders/segments </span>/ </li> 
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Schema</b> </td> 
   <td colname="col2"> <span class="codeph"> https://api.demdex.com/v1/schemas/ </span> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Segments</b> </td> 
   <td colname="col2"> <span class="codeph"> https://api.demdex.com/v1/segments/ </span> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Traits</b> </td> 
   <td colname="col2"> <span class="codeph"> https://api.demdex.com/v1/traits/ </span> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Trait Types</b> </td> 
   <td colname="col2"> <span class="codeph"> https://api.demdex.com/v1/customer-trait-types </span> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b> Taxonomy</b> </td> 
   <td colname="col2"> <span class="codeph"> https://api.demdex.com/v1/taxonomies/0/ </span> </td> 
  </tr> 
 </tbody> 
</table>


## Environments {#section_5B33F1445F9C49C896C4E9240B5F0CCD}



The [!DNL Audience Manager] APIs provide access to different working environments. These environments help you test code against separate databases without affecting live, production data. The following table lists the available API environments and corresponding resource hostnames. 

|  Environment  | Hostname  |
|---|---|
|  **Production** | `https://api.demdex.com/...`  |
|  **Beta** | `https://api-beta.demdex.com/...`  |




>[!NOTE]
>
>The Audience Manager beta environment is a smaller-scale, standalone version of the production environment. All the data that you want to test must be entered and collected in this environment.


## Versions {#section_473AE7014EE949E7AD868AB357452673}



New versions of these APIs are released on a regular schedule. A new release increments the API version number. The version number is referenced in the request URL as `v<version number>` as shown in the following example: 


`https:// <host>/v1/...` 

## Response Codes Defined {#reference_2AC89154A26E49A48E0DDD8DA520757F}

HTTP status codes and response text returned by the Audience Manager REST API.


>
>

><!-- r_api_http_response_codes.xml -->

>
>
>|  Response code ID  | Response text  | Definition  |
>|---|---|---|
>|  200  | OK  | The request processed successfully. Will return expected content or data if required.  |
>|  201  | Created  | The resource was created. Returns for `PUT` and `POST` requests.  |
>|  204  | No Content  | The resource has been deleted. The response body will be blank.  |
>|  400  | Bad Request  | The server did not understand the request. Usually due to malformed syntax. Check your request and try again.  |
>|  403  | Forbidden  | You do not have access to the resource.  |
>|  404  | Not Found  | The resource could not be found for the specified path.  |
>|  409  | Conflict  | The request could not be completed due to a conflict with the state of the resource.  |
>|  500  | Server Error  | The server encountered an unexpected error that prevented it from fulfilling the request.  |

