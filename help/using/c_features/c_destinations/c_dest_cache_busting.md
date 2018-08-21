---
description: The %rnd% and %timestamp% macros insert unique values into a URL string to prevent browser caching.
seo-description: The %rnd% and %timestamp% macros insert unique values into a URL string to prevent browser caching.
seo-title: Cache Busting with Destination Macros
solution: Audience Manager
title: Cache Busting with Destination Macros
uuid: 92bffb35-2167-4ed7-b300-c2cf2d3c7a1e
index: y
internal: n
snippet: y
translate: y
---

# Cache Busting with Destination Macros


## Cache Busting with %rnd% and %timestamp% {#section_4A1CBFBCB1F74E55BB3A8345E5174332}

Browsers cache (save) save frequently requested content in memory. When a page loads, saved content serves from the cache rather than from a remote server. This process helps maintain efficient download times because data serves locally rather than from another location. However, because caching does not require a server call, it can skew reporting by artificially lowering the number of unique requests. 

Cache busting prevents browsers from saving and reusing content. This technique uses code that inserts a random number or time stamp into a URL string, which makes it look unique to the browser. As a result, each HTTP call is counted as a separate request to the server. Forcing a new server call for each request helps maintain reporting accuracy and reduce discrepancies. Audience Manager provides two macros for cache busting: 


* ` %rnd%`: Inserts a random number into a URL.
* ` %timestamp%`: Inserts the Unix date/time into a URL.


## Comparing %rnd% and %timestamp% {#section_DA7D8DD8FCB74C259C621121C50BF0FB}

Both macros prevent caching, but ` %rnd%` may be more efficient. For example, with ` %timestamp%`, if several users view a page simultaneously they'll get the same date/time value. As a result, the URL is not unique and multiple calls are counted only once. However, ` %rnd%` generates a unique numeric value for each call (even when users see the same page simultaneously). This means the URL string contains different values and is counted as unique. 
>[!MORE_LIKE_THIS]
>
>* [ Destination Macros Defined ](destination-macros.md#reference_B2F4AE643702440D879EFFE4A3FAAEDB)
