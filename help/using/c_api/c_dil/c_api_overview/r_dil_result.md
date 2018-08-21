---
description: Adds a callback (that receives JSON) to the pending request.
seo-description: Adds a callback (that receives JSON) to the pending request.
seo-title: result
solution: Audience Manager
title: result
uuid: f5624eb0-a0d1-4aa2-a447-ad765dc529a6
index: y
internal: n
snippet: y
translate: y
---

# result


>**Function Signature:** ` result: function (callback) {}` 

>This callback replaces the default callback that handles destination publishing. 
>>[!NOTE]
>>
>>You can chain other API calls to this method.
>


>**Parameters** 



>|  Name  | Type  | Description  |
>|---|---|---|
>|  ` callback`  | Function  | JavaScript function executed by the JSONP callback.  |

>**Response** 

>Returns the API object of the current DIL instance. 

>**Sample Code** >
>```
>var dataLib = DIL.create({ 
>     partner: ' 
<i>partnerName</i>', 
>     containerNSID:  
<i>containerNSID</i> 
>}); 
> 
>dataLib.api.traits([ 
<i>123, 456, 789</i>]).result(function(json){ 
>     //Do something, possibly with the JSON data returned from the server. 
>});.submit();
>```

