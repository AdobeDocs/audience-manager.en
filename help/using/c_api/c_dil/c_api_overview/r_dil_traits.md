---
description: Adds SIDs to the query string of a pending request.
seo-description: Adds SIDs to the query string of a pending request.
seo-title: traits
solution: Audience Manager
title: traits
uuid: 9662f735-40bc-47d7-bf24-aef7f7494887
index: y
internal: n
snippet: y
translate: y
---

# traits


>**Function signature:** ` traits:function (sids){}` 


>>[!NOTE]
>>
>>You can chain other API calls to this method.
>


>**Parameters** 

>|  Name  | Type  | Description  |
>|---|---|---|
>|  ` sids`  | Array  | Trait segment IDs in an array.  |

>**Response** 

>Returns the API object of the current DIL instance. 

>**Sample Code** >
>```
>var partnerObject = DIL.create({ 
>     partner: ' 
<i>partner name</i>', 
>     containerNSID:  
<i>NSID</i> 
>}); 
>partnerObject.api.traits( 
<i>[123, 456, 789]</i>); 
>
>```

