---
description: Retrieves a specific value from an ad server.
seo-description: Retrieves a specific value from an ad server.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: e8826770-664d-4bc9-8568-27e4125d9831
index: y
internal: n
snippet: y
translate: y
---

# dexGetQSVars

Retrieves a specific value from an ad server.


>
>
>**Function Signature:** `dexGetQSVars: function (variableName, partner, containerNSID) {}` 
>
>

><!-- r_dil_get_dexqsvars.xml -->
>**Parameters** 
>
>
>|  Name  | Type  | Description  |
>|---|---|---|
>|  `variableName`  | String  | The name of the variable you want to get a value for.  |
>|  `partner`  | String  | The partner name to search for.  |
>|  `containerNSID`  | Integer  | The [!DNL NSID] of the container you're searching for. Defaults is `0`.  |

>
>
>**Response** 
>
>
>Returns the variable value for a [!UICONTROL DIL] instance. 
>
>
>**Sample Code** >
>```java>
>var value = DIL.dexGetQSVars(' 
<i>variableName</i>',' 
<i>partnerName</i>', 
<i>containerNSID</i>);
>```

