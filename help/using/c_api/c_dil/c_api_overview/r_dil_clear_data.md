---
description: Clears all data in a pending request.
seo-description: Clears all data in a pending request.
seo-title: clearData
solution: Audience Manager
title: clearData
uuid: 4d484133-fc55-4e66-acf8-88f9bccd0bfc
index: y
internal: n
snippet: y
translate: y
---

# clearData


>**Function Signature:** ` clearData: function () {}` 


>>[!NOTE]
>>
>>You can chain other API calls to this method.
>


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
<i>123,456, 789</i>]).logs({ 
>     file: 'dil.js' 
>     message: 'This is the first request' 
>}).signals({ 
>     c_zdid:  
<i>1111</i> 
>     d_dma: ' 
<i>default</i>' 
>}); 
> 
>//Reset the pending data 
>dataLib.clearData();
>```

