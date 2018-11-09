---
description: Retrieves a partner-specific DIL instance.
keywords: audience manager api;aam api;audience manager apis;aam apis
seo-description: Retrieves a partner-specific DIL instance.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: f39f342d-3c1b-42bc-9220-014a713c4189
index: y
internal: n
snippet: y
---

# getDil{#getdil}

Retrieves a partner-specific DIL instance.

 **Function Signature:** `getDil: function (partner, containerNSID) {}`

<!-- 

r_dil_get_dil.xml

 -->

**Parameters** 

|  Name  | Type  | Description  |
|---|---|---|
|  `partner`  | String  | The partner name to search for.  |
|  `containerNSID`  | Integer  | Defaults is `0`. The NSID of the container you're searching for. Optional.  |

**Response**

A successful partner and container NSID match returns a partner-specific [!UICONTROL DIL] instance. If there is no match, the API returns (does not throw) an error with the message, " `The DIL instance with partner <name> and containerNSID <ID> was not found.`"

**Sample Code** 

```java
DIL.getDil(' 
<i><partner></i>',  
<i><containerNSID></i>); 
DIL.getDil(' 
<i><partner></i>');
```

