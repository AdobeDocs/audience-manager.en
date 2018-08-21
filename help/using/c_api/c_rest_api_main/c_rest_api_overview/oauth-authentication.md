---
description: The Audience Manager REST API follows OAuth 2.0 standards for token authentication and renewal.
seo-description: The Audience Manager REST API follows OAuth 2.0 standards for token authentication and renewal.
seo-title: OAuth Authentication
solution: Audience Manager
title: OAuth Authentication
uuid: bf37d017-d56c-427b-87cd-adff09ebd3e7
index: y
internal: n
snippet: y
translate: y
---

# OAuth Authentication

Contents: 


<ul class="simplelist"> 
 <li> <a href="../../../c_api/c_rest_api_main/c_rest_api_overview/oauth-authentication.md#section_E8C9602AFAAC45D782D72E8ED7F5EFB1" format="dita" scope="local"> Password Authentication Workflow </a> </li> 
 <li> <a href="../../../c_api/c_rest_api_main/c_rest_api_overview/oauth-authentication.md#section_6671766BA28A4EADB5925F56267B343E" format="dita" scope="local"> Refresh Token </a> </li> 
 <li> <a href="../../../c_api/c_rest_api_main/c_rest_api_overview/oauth-authentication.md#section_315C16DF045C4E73B81426CD98EA730B" format="dita" scope="local"> Authorization Code and Implicit Authentication </a> </li> 
</ul>



## Password Authentication Workflow {#section_E8C9602AFAAC45D782D72E8ED7F5EFB1}

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
   <td colname="col2"> <p>Contact your Partner Solutions manager. They will provide you with an API client ID and secret. The ID and secret authenticate you to the API. <p>Note:  If you'd like to receive a refresh token, specify that when you request API access. </p></p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <b>Request the Token</b> </td> 
   <td colname="col2"> <p>Pass in a token request with your preferred JSON client. When you build the request: 
     <ul id="ul_D34AF5AAF8C94148823A33EE1340CECC"> 
      <li id="li_DC7A0B98B1824BF996CD85B822F9B6A6">Use a <span class="codeph"> POST </span> method to call <span class="codeph"> https://api.demdex.com/oauth/token </span>. </li> 
      <li id="li_07DBC364F32748D4A8471A849C321A0A">Convert your client ID and secret to a base-64 encoded string. Separate the ID and secret with a colon during the conversion process. For example, the credentials <span class="codeph"> testId </span>: <span class="codeph"> testSecret </span> convert to <span class="codeph"> dGVzdElkOnRlc3RTZWNyZXQ= </span>. </li> 
      <li id="li_F525D6C394D74246AF68C9F5496174D1">Pass in the HTTP headers <span class="codeph"> Authorization:Basic <span class="varname"> &amp;lt;base-64 clientID:clientSecret&amp;gt; </span> </span> and <span class="codeph"> Content-Type: application/x-www-form-urlencoded </span>. For example, your header could look like this: 
       <codeblock>
         Authorization:&nbsp;Basic&nbsp;dGVzdElkOnRlc3RTZWNyZXQ= 
        Content-Type:&nbsp;application/x-www-form-urlencoded 
       </codeblock></li> 
      <li id="li_3A638183F3C343759642EB405E5AEF1B">Set up the request body as follows: 
       <codeblock>
         grant_type=password&amp;username= 
        <span class="varname"> &amp;lt;your&amp;nbsp;AudienceManager&amp;nbsp;user&amp;nbsp;name&amp;gt;&amp;amp; </span> 
        password= 
        <span class="varname"> &amp;lt;your&amp;nbsp;AudienceManager&amp;nbsp;password&amp;gt; </span> 
       </codeblock></li> 
     </ul></p> </td> 
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
     </codeblock></p> <p>The <span class="codeph"> "expires_in" </span> key represents the number of seconds until the access token expires. As best practice, use short expiration times to limit exposure if the token is ever exposed. </p> </td> 
  </tr> 
 </tbody> 
</table>


## Refresh Token {#section_6671766BA28A4EADB5925F56267B343E}

Refresh tokens renew API access after the original token expires. If requested, the response JSON in the password workflow includes a refresh token. If you don't receive a refresh token, create a new one through the password authentication process. 

You can also use a refresh token to generate a new token before the existing access token expires. 

If your access token has expired, you receive a ` 401 Status Code` and the following header in the response: 

` WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"` 

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
      <li id="li_06CFB45DA2C84859ADE6591218E413F1">Pass in the HTTP headers <span class="codeph"> Authorization:Basic <span class="varname"> &amp;lt;base-64 clientID:clientSecret&amp;gt; </span> </span> and <span class="codeph"> Content-Type: application/x-www-form-urlencoded </span>. For example, your header could look like this: 
       <codeblock>
         Authorization:&nbsp;Basic&nbsp;dGVzdElkOnRlc3RTZWNyZXQ= 
        Content-Type:&nbsp;application/x-www-form-urlencoded 
       </codeblock></li> 
      <li id="li_14595B35956D4876BE8661BB7FFC0839">In the request body, specify the <span class="codeph"> grant_type:refresh_token </span> and pass in the refresh token you received in your previous access request. The request should look like this: 
       <codeblock>
         grant_type=refresh_token&amp;amp;refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e 
       </codeblock></li> 
     </ul></p> </td> 
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
     </codeblock></p> </td> 
  </tr> 
 </tbody> 
</table>


## Authorization Code and Implicit Authentication {#section_315C16DF045C4E73B81426CD98EA730B}

The Audience Manager REST API supports authorization code and implicit authentication. To use these access methods, your users need to log in to ` https://api.demdex.com/oauth/authorize` to get access and refresh tokens. 
>[!MORE_LIKE_THIS]
>
>* [ Make Authenticated API Requests ](c_oauth_call_methods.md#concept_1A4B53C4554C4B0396499997EECCBDB9)
>* [  ](http://oauth.net/2/)
>* [  ](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)
