---
description: Describes methods in the DIL.tools namespace. These utility functions help you perform specific tasks.
seo-description: Describes methods in the DIL.tools namespace. These utility functions help you perform specific tasks.
seo-title: DIL Tools
solution: Audience Manager
title: DIL Tools
uuid: 2bc62ce2-16bd-4e80-b493-c816ba643b59
feature: DIL Implementation
exl-id: 1f52eb95-8287-4dd0-b933-00de6926a797
TQID: https://experienceleague.adobe.com/W3xzJ172rBhQ9Flqs5towA5pE3-nJHpwnJ1jd1mXIyo
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
    internal-label: Implementation
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
    internal-label: Integrations
subfeature_v2:
  - id: d7e573ad-4eda-46ec-90c4-239e75362af9
    internal-label: DIL implementation
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
    internal-label: Data integration
---
# DIL Tools

>[!WARNING]
>
>Beginning in July 2023, Adobe has discontinued the development of the [!DNL Data Integration Library (DIL)] and the [!DNL DIL] extension.
>
>Existing customers can continue using their [!DNL DIL] implementation. However, Adobe will not be developing [!DNL DIL] beyond this point. Customers are encouraged to evaluate [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) for their long term data collection strategy.
>
>Customers looking to implement new data collection integrations after July 2023 should use [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) instead.

Describes methods in the `DIL.tools` namespace. These utility functions help you perform specific tasks.

<!-- 

c_dil_functions.xml

 -->

## getSearchReferrer

Returns search terms used to reach the current page.

<!-- 

r_dil_get_search_referrer.xml

 -->

### Purpose of `getSearchReferrer`

In DIL, `getSearchReferrer` returns search results (names and key words) used to reach your site. You can pass in specific search terms to this function or let it search the supported search engines ( [!DNL AOL], [!DNL Ask], [!DNL Bing], [!DNL Google], and [!DNL Yahoo]) against `document.referrer` by default. 

### Function signature

Function signature: `DIL.tools.getSearchReferrer(uri, initConfig)`

### Function Parameters

`getSearchReferrer` accepts:

* *`{string}`*: *(Optional)* A string containing the search URL (uses `document.referrer` if undefined). 
* *`{object}`*: *(Optional)* An object containing the configuration for the `hostPattern`, `queryParam`, or `queryPattern`.

And returns:

* `{object}` An object that contains valid names and keywords.

### Examples

<table id="table_D035276601EC428295E4D619F05BB8D0"> 
 <thead> 
  <tr> 
   <th> Search Type </th> 
   <th> Description </th> 
   <th> Code Sample </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Default Search</td> 
   <td> Returns keyword search terms used by the AOL, Ask, Bing, Google, and Yahoo search engines. </td> 
   <td>
      <code>var&amp;nbsp;results&amp;nbsp;=&amp;nbsp;DIL.tools.getSearchReferrer();</code> 
  </td>
  </tr> 
  <tr> 
   <td>Pass in a Custom URL</td> 
   <td>Returns the search referrer based on a custom URL.</td> 
   <td> 
  <code>
        var&nbsp;results&nbsp;= 
        DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules");
  </code>
</td> 
  </tr> 
  <tr> 
   <td> <b>Match URL Hostname with a Custom Regex</b></td> 
   <td> Pass in a custom regex to match the host name of the referring URL. </td> 
   <td> 
  <code>
      var results = 
        DIL.tools.getSearchReferrer("https://www.ehow.com/
      search.aspx?q=adobe+rules",{ 
      &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
      &nbsp;&nbsp;&nbsp;queryParam:"p" 
      }); 
  </code>
  </td></tr> 
  <tr> 
   <td> <b>Match Search Patterns with a Custom Regex</b> </td> 
   <td> Pass in a custom regex to perform a custom search. </td> 
   <td> 
    <code>
      var&nbsp;results&nbsp;= 
      DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules,
      {
        &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
        &nbsp;&nbsp;&nbsp;search_pattern:/[&amp;\?]p=([^&amp;]+/ 
      });
    </code>
   </td> 
  </tr> 
 </tbody> 
</table>

## decomposeURI

Disassembles a Uniform Resource Identifier ( [!DNL URI]) into its constituent components: `hash`, `host`, `href`, `pathname`, `protocol`, `search`, and `[!DNL uriParams]`.

<!-- 

r_dil_decompose.xml

 -->

Function signature: `DIL.tools.decomposeURI`

### Function Parameters

`decomposeURI` accepts:

* *`uri {string}`*: *(Optional)* A string containing the URI. Defaults to `document.location.href` if not specified.

And returns:

* *`{object}`*: An object that contains valid names and keywords.

### Sample Code


```javascript
var uriData = DIL.tools.decomposeURI('https://www.adobe.com/?arg1=123&arg2=456#am'); 
{ 
  hash : "#am", 
  host : "www.adobe.com", 
  hostname : "www.adobe.com", 
  href : "https://www.adobe.com/?arg1=123&arg2=456#am", 
  pathname : "", 
  protocol : "https:", 
  search : "?arg1=123&arg2=456", 
  uriParams : { 
    arg1 : "123", 
    arg2 : "456" 
  } 
}
```

## getMetaTags

Searches for specific content defined in the meta tags on a Web page and returns that data in an object.

<!-- 

r_dil_get_metatags.xml

 -->

### Function signature

Function signature: `DIL.tools.getMetaTags( 1 or more parameters)`

### Function Parameters

`getMetaTags` accepts one or more name parameters (string type) to search for. It returns an object composed of key-value pairs.

### Sample Code

<pre class="javascript"><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>', '<i>keywords</i>',  '<i>description</i>'), 'c_').submit();
</code></pre>

<pre><code>
var dataLib = DIL.create({ 
     partner: <i>`partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>','<i>keywords</i>', '<i>description</i>'), 'c_').submit();
</code></pre>
