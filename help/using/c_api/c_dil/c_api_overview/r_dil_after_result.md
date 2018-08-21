---
description: A function that executes after the default destination publishing callback.
seo-description: A function that executes after the default destination publishing callback.
seo-title: afterResult
solution: Audience Manager
title: afterResult
uuid: 954827b7-fd38-4c06-ad0e-9f6e55cf5c20
index: y
internal: n
snippet: y
translate: y
---

# afterResult


>**Function Signature:** ` afterResult: function (fn) {}` 


>>[!NOTE]
>>
>>You can chain other API calls to this method.
>


>**Parameters** 

>|  Name  | Type  | Description  |
>|---|---|---|
>|  ` fn`  | Function  | The function you want to execute after JSON is processed by the default callback that handles destination publishing.  |

>**Response** 

>Returns an API object of the current DIL instance. 

>**Sample Code** >
>```
>var dataLib = DIL.create({ 
>     partner: ' 
<i>partnerName</i>', 
>     containerNSID:  
<i>containerNSID</i> 
>}); 
> 
>dataLib.api.signals({ 
>     c_zdid:  
<i>54321</i> 
>     d_dma: ' 
<i>default</i>' 
>}).afterResult(function(json){ 
>     //Do something with the JSON data returned from the server. 
>}).submit();
>```

