---
description: Disassembles a Uniform Resource Identifier (URI) into its constituent components  hash, host, href, pathname, protocol, search, and uriParams.
seo-description: Disassembles a Uniform Resource Identifier (URI) into its constituent components  hash, host, href, pathname, protocol, search, and uriParams.
seo-title: decomposeURI
solution: Audience Manager
title: decomposeURI
uuid: 5d3e71f6-d661-4b6c-b499-91df13654b61
index: y
internal: n
snippet: y
translate: y
---

# decomposeURI


>Function signature: ` DIL.tools.decomposeURI`

>**Function Parameters** 

>` decomposeURI` accepts: >
>* *` uri {string}`*: *(Optional)* A string containing the URI. Defaults to ` document.location.href` if not specified.


>And returns: >
>* *` {object}`*: An object that contains valid names and keywords.


>**Sample Code** >
>```
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

