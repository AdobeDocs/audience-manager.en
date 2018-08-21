---
description: Submits all pending data to Audience Manager for the DIL instance.
seo-description: Submits all pending data to Audience Manager for the DIL instance.
seo-title: submit
solution: Audience Manager
title: submit
uuid: 60a67efc-4d0a-4d05-aee9-30042cfd75b0
index: y
internal: n
snippet: y
translate: y
---

# submit


>**Function Signature:** ` submit: function () {}` 


>>[!NOTE]
>>
>>You can chain other API calls to this method. Also, DIL writes encoded data to a destination cookie. For example, spaces are encoded as ` %20` and semicolons as ` %3B`. 
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
>     file: 'dil.js', 
>     message: 'This is the first request' 
>}).signals({ 
>     c_zdid:  
<i>1111</i> 
>     d_dma: ' 
<i>default</i>' 
>}).submit();
>```

>[!MORE_LIKE_THIS]
>
>* [ Prefix Requirements for Key Variables ](r_tb_variable_prefixes.md#reference_E6F1E4257F664FC2A797C406BF147ABC)
