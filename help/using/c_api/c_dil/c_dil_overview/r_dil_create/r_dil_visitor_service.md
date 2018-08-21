---
description: Defines the properties used by the visitorService variable. This variable is part of the DIL.create method.
seo-description: Defines the properties used by the visitorService variable. This variable is part of the DIL.create method.
seo-title: visitorService Properties
solution: Audience Manager
title: visitorService Properties
uuid: 4e02ec8c-07be-425d-a697-ede5cdbbcf01
index: y
internal: n
snippet: y
translate: y
---

# visitorService Properties


>` visitorService` has the following properties: 



>|  Name  | Type  | Description  |
>|---|---|---|
>|  ` namespace`  | String  | Required. Represents The Experience Cloud Org ID. This is needed for Experience Cloud Core Service functionality. Same parameter used to instantiate the Visitor ID functionality.  |

>**Code Sample:** 

>
>```
>var vDil = DIL.create({ 
>    partner: 'demofirst', 
>    visitorService: { 
>        namespace: "INSERT-MCORG-ID-HERE" 
>    } 
>});
>```

>[!MORE_LIKE_THIS]
>
>* [  ](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-implementation-guides.html)
