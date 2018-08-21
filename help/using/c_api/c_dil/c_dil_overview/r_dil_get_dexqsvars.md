---
description: Retrieves a specific value from an ad server.
seo-description: Retrieves a specific value from an ad server.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 61ac1183-1c1e-46e8-92b5-8bd44fd7aa5e
index: y
internal: n
snippet: y
translate: y
---

# dexGetQSVars


>**Function Signature:** ` dexGetQSVars: function (variableName, partner, containerNSID) {}` 

>**Parameters** 

>|  Name  | Type  | Description  |
>|---|---|---|
>|  ` variableName`  | String  | The name of the variable you want to get a value for.  |
>|  ` partner`  | String  | The partner name to search for.  |
>|  ` containerNSID`  | Integer  | The [!DNL  NSID] of the container you're searching for. Defaults is ` 0`.  |

>**Response** 

>Returns the variable value for a [!DNL  DIL] instance. 

>**Sample Code** >
>```
>java>var value = DIL.dexGetQSVars(' 
<i>variableName</i>',' 
<i>partnerName</i>', 
<i>containerNSID</i>);
>```

