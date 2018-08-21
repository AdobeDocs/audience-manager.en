---
description: Adds custom query parameters that are not explicitly defined by the data collection server to a pending request.
seo-description: Adds custom query parameters that are not explicitly defined by the data collection server to a pending request.
seo-title: customQueryParams
solution: Audience Manager
title: customQueryParams
uuid: 407ba943-9387-4c78-b238-93c675899946
index: y
internal: n
snippet: y
translate: y
---

# customQueryParams


>**Function Signature:** ` customQueryParams: function (obj) {}` 


>>[!NOTE]
>>
>>You can chain other API calls to this method.
>


>**Reserved Request Keys** 

>The following request keys are reserved and cannot be overwritten by this method: >
>* ` sids`
>* ` pdata`
>* ` logdata`
>* ` callback`
>* ` postCallbackFn`
>* ` useImageRequest`


>**Response** 

>Returns the API object of the current DIL instance. 

>**Sample Code** >
>```
>var partnerObject = DIL.create({ 
>     partner: ' 
<i>partner</i>', 
>     containerNSID:  
<i>NSID</i> 
>}); 
>partnerObject.api.customQueryParams({ 
>     nid: 54231, 
>     ntype: 'default' 
>}); 
>
>```

