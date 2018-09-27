---
description: Describes methods in the DIL.tools namespace. These utility functions help you perform specific tasks.
seo-description: Describes methods in the DIL.tools namespace. These utility functions help you perform specific tasks.
seo-title: DIL Tools
solution: Audience Manager
title: DIL Tools
uuid: 2b8131ef-3fa2-4265-bf58-909737fa3d18
index: y
internal: n
snippet: y
translate: y
---

# DIL Tools

Describes methods in the DIL.tools namespace. These utility functions help you perform specific tasks.

## <codeph> getSearchReferrer </codeph> {#reference_1658BF0239D24C87811BA963E4DB0FB8}

Returns search terms used to reach the current page. 
<draft-comment otherprops="merge">
  r_dil_get_search_referrer.xml 
</draft-comment>


>
>
>**Purpose of `getSearchReferrer`** 
>
>
>In DIL, `getSearchReferrer` returns search results (names and key words) used to reach your site. You can pass in specific search terms to this function or let it search the supported search engines ( [!DNL AOL], [!DNL Ask], [!DNL Bing], [!DNL Google], and [!DNL Yahoo]) against `document.referrer` by default. 
>**Function signature:**`DIL.tools.getSearchReferrer(uri, initConfig)`>
>
>**Function Parameters** 
>
>
>`getSearchReferrer` accepts: >
>* *`{string}`*: *(Optional)* A string containing the search URL (uses `document.referrer` if undefined).>
>* *`{object}`**(Optional)* An object containing the configuration for the `hostPattern`, `queryParam`, or `queryPattern`.>
>
>

>
>
>And returns: >
>* *`{object}`*: An object that contains valid names and keywords.>
>
>

>
>
>**Examples** 
>
>
>|  Search Type  | Description  | Code Sample  |
>|---|---|---|
>|  **Default Search** | Returns keyword search terms used by the [!DNL AOL], [!DNL Ask], [!DNL Bing], [!DNL Google], and [!DNL Yahoo] search engines.  | >
>```>
>var results = DIL.tools.getSearchReferrer();
>```
>|
>|  **Pass in a Custom URL** | Returns the search referrer based on a custom URL.  | >
>```>
>var results = 
>DIL.tools.getSearchReferrer("http://www.ehow.com/ 
>search.aspx?q=adobe+rules");
>```
>|
>|  **Match URL Hostname with a Custom Regex** | Pass in a custom regex to match the host name of the referring URL.  | >
>```>
>var results = 
>DIL.tools.getSearchReferrer("http://www.ehow.com/ 
>search.aspx?q=adobe+rules",{ 
>   hostPattern:/ehow\./, 
>   queryParam:"p" 
>});
>```
>|
>|  **Match Search Patterns with a Custom Regex** | Pass in a custom regex to perform a custom search.  | >
>```>
>var results = 
>DIL.tools.getSearchReferrer("http://www.ehow.com/ 
>search.aspx?q=adobe+rules,{ 
>   hostPattern:/ehow\./, 
>   search_pattern:/[&\?]p=([^&]+/ 
>});
>```
>|

## <codeph> decomposeURI </codeph> {#reference_222B85A7E6E34722B67212C7C080FE5F}

Disassembles a Uniform Resource Identifier ( 
<keyword>
  URI 
</keyword>) into its constituent components: hash, host, href, pathname, protocol, search, and 
<keyword>
  uriParams 
</keyword>. 
<draft-comment otherprops="merge">
  r_dil_decompose.xml 
</draft-comment>


>
>
>Function signature: `DIL.tools.decomposeURI` 
>
>
>**Function Parameters** 
>
>
>`decomposeURI` accepts: >
>* *`uri {string}`*: *(Optional)* A string containing the URI. Defaults to `document.location.href` if not specified.>
>
>

>
>
>And returns: >
>* *`{object}`*: An object that contains valid names and keywords.>
>
>

>
>
>**Sample Code** >
>```>
>var uriData = DIL.tools.decomposeURI('http://www.adobe.com/?arg1=123&arg2=456#am'); 
>  
>{ 
>  hash : "#am", 
>  host : "www.adobe.com", 
>  hostname : "www.adobe.com", 
>  href : "http://www.adobe.com/?arg1=123&arg2=456#am", 
>  pathname : "", 
>  protocol : "http:", 
>  search : "?arg1=123&arg2=456", 
>  uriParams : { 
>    arg1 : "123", 
>    arg2 : "456" 
>  } 
>}
>```

## <codeph> getMetaTags </codeph> {#reference_411CD926DD6E45F599581DB5D19C4B30}

Searches for specific content defined in the meta tags on a Web page and returns that data in an object. 
<draft-comment otherprops="merge">
  r_dil_get_metatags.xml 
</draft-comment>


>
>
>**Function signature:** `DIL.tools.getMetaTags( 1 or more parameters)` 
>
>
>**Function Parameters** 
>
>
>`getMetaTags` accepts one or more name parameters (string type) to search for. It returns an object composed of key-value pairs. 
>
>
>**Sample Code** >
>```>
>var dataLib = DIL.create({ 
>     partner: ' 
<i>partnerName'</i>, 
>     containerNSID:  
<i>containerNSID</i> 
>}); 
> 
>dataLib.api.signals(DIL.tools.getMetaTags(' 
<i>application</i>', ' 
<i>keywords</i>', 
>' 
<i>description</i>'), 'c_').submit();
>```

