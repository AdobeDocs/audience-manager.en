---
description: Changes the request type to image <img> from script <src>.
keywords: create traits;create trait
seo-description: Changes the request type to image <img> from script <src>.
seo-title: useImageRequest
solution: Audience Manager
title: useImageRequest
uuid: e4e24d10-a6c5-4063-a965-104680c75d33
index: y
internal: n
snippet: y
translate: y
---

# useImageRequest


>**Function Signature:** ` useImageRequest: function () {}` 


>>[!NOTE]
>>
>>You can chain other API calls to this method.
>


>**Response** 

>Returns an API object of the current DIL instance. 

>**Sample Code** >
>```
>var dataLib = DIL.create({ 
>     partner:' 
<i>partnerName</i>', 
>     containerNSID:  
<i>containerNSID</i> 
>}); 
> 
>dataLib.api.traits([ 
<i>123, 456, 789</i>]).useImageRequest().submit();
>```

