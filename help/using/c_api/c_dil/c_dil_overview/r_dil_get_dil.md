---
description: Retrieves a partner-specific DIL instance.
keywords: audience manager api;aam api;audience manager apis;aam apis
seo-description: Retrieves a partner-specific DIL instance.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: e4d8f7b4-71c3-454f-a47c-9ad53a7df097
index: y
internal: n
snippet: y
translate: y
---

# getDil


>**Function Signature:** ` getDil: function (partner, containerNSID) {}` 

>**Parameters** 

>|  Name  | Type  | Description  |
>|---|---|---|
>|  ` partner`  | String  | The partner name to search for.  |
>|  ` containerNSID`  | Integer  | Defaults is ` 0`. The NSID of the container you're searching for. Optional.  |

>**Response** 

>A successful partner and container NSID match returns a partner-specific DIL instance. If there is no match, the API returns (does not throw) an error with the message, " ` The DIL instance with partner <name> and containerNSID <ID> was not found.`" 

>**Sample Code** >
>```
>java>DIL.getDil(' 
<i><partner></i>',  
<i><containerNSID></i>); 
>DIL.getDil(' 
<i><partner></i>');
>```

