---
description: secureDataCollection is a boolean parameter that controls how DIL makes calls to the Data Collection Servers (DCS) and Akamai.
seo-description: secureDataCollection is a boolean parameter that controls how DIL makes calls to the Data Collection Servers (DCS) and Akamai.
seo-title: secureDataCollection
solution: Audience Manager
title: secureDataCollection
uuid: 76e128c0-af27-457f-9934-85b869aca9f2
index: y
internal: n
snippet: y
translate: y
---

# secureDataCollection


* When ` secureDataCollection= true` (default), DIL always makes secure, HTTPS calls.
* When ` secureDataCollection= false`, DIL makes either HTTP or HTTPS calls by following the security protocol set by the page.

>[!IMPORTANT]
>
>Set ` secureDataCollection= false` if you use visitorAPI.js and DIL on the same page. See the code sample below. 




```
jsvar dilInstance = DIL.create({ 
     ... 
     secureDataCollection: false 
});
```

>[!MORE_LIKE_THIS]
>
>* [ DIL create ](r_dil_create.md#reference_F87131F6C1CC4ECCA064B24B91710FD4)
