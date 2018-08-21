---
description: Returns search terms used to reach the current page.
seo-description: Returns search terms used to reach the current page.
seo-title: getSearchReferrer
solution: Audience Manager
title: getSearchReferrer
uuid: 5aed46a6-e1f1-461d-ac6e-5e050b5bec4b
index: y
internal: n
snippet: y
translate: y
---

# getSearchReferrer


>**Purpose of getSearchReferrer** 

>In DIL, ` getSearchReferrer` returns search results (names and key words) used to reach your site. You can pass in specific search terms to this function or let it search the supported search engines (AOL, Ask, Bing, Google, and Yahoo) against ` document.referrer` by default. 
>**Function signature:**` DIL.tools.getSearchReferrer(uri, initConfig)`**Function Parameters** 

>` getSearchReferrer` accepts: >
>* *` {string}`*: *(Optional)* A string containing the search URL (uses ` document.referrer` if undefined).
>* *` {object}`**(Optional)* An object containing the configuration for the ` hostPattern`, ` queryParam`, or ` queryPattern`.


>And returns: >
>* *` {object}`*: An object that contains valid names and keywords.


>**Examples** 

>|  Search Type  | Description  | Code Sample  |
>|---|---|---|
>|  **Default Search** | Returns keyword search terms used by the AOL, Ask, Bing, Google, and Yahoo search engines.  | >
>```
>var results = DIL.tools.getSearchReferrer();
>```
>|
>|  **Pass in a Custom URL** | Returns the search referrer based on a custom URL.  | >
>```
>var results = 
>DIL.tools.getSearchReferrer("http://www.ehow.com/ 
>search.aspx?q=adobe+rules");
>```
>|
>|  **Match URL Hostname with a Custom Regex** | Pass in a custom regex to match the host name of the referring URL.  | >
>```
>var results = 
>DIL.tools.getSearchReferrer("http://www.ehow.com/ 
>search.aspx?q=adobe+rules",{ 
>   hostPattern:/ehow\./, 
>   queryParam:"p" 
>});
>```
>|
>|  **Match Search Patterns with a Custom Regex** | Pass in a custom regex to perform a custom search.  | >
>```
>var results = 
>DIL.tools.getSearchReferrer("http://www.ehow.com/ 
>search.aspx?q=adobe+rules,{ 
>   hostPattern:/ehow\./, 
>   search_pattern:/[&\?]p=([^&]+/ 
>});
>```
>|

