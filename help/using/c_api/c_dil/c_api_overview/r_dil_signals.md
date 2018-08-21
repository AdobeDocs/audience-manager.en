---
description: Adds customer and platform-level mappings to the query string of a pending request.
seo-description: Adds customer and platform-level mappings to the query string of a pending request.
seo-title: signals
solution: Audience Manager
title: signals
uuid: 410d3c96-cba1-4701-8fb5-fef6e8a06a12
index: y
internal: n
snippet: y
translate: y
---

# signals


>**Function Signature:** ` signals: function ({key1:value1, key2:value2},prefix){}` 

>>[!NOTE]
>>
>>
>>* You can chain other API calls to this method.
>>* If the Adobe Experience Cloud JavaScript library is on the page, ` submit()` waits for the Cloud to set a cookie before sending a request.

>
>**Reserved Request Keys** 

>The following request keys are reserved and cannot be overwritten by this method: >
>* ` sids`
>* ` pdata`
>* ` logdata`
>* ` callback`
>* ` postCallbackFn`
>* ` useImageRequest`


>**Parameters** 

>|  Name  | Type  | Description **** |
>|---|---|---|
>|  ` obj`  | Object  | An object representing the key-value pairs for platform-level mappings. Parameter accepts strings and arrays as property values in the object.  |
>|  ` prefix`  | String  | Optional. The string value prefixed to each object key (replaces original key).  |
>|  ` return`  | DIL.api  | Returns the API object of the current DIL instance.  |

>**Response** 

>Returns the API object of the current DIL instance. 

>**Sample Code** >
>```
>var dataLib = DIL.create({ 
>     partner: ' 
<i>partnerName</i>' 
>     containerNSID:  
<i>containerNSID</i> 
>}); 
> 
>// Method 1 
>var obj = { key1 : 1, key2 : 2 }; 
>dataLib.api.signals(obj, 'c_').submit(); 
> 
>// Method 2 
>dataLib.api.signals({c_zdid: 54321}).submit(); 
> 
>// Method 3 
>// Will send 'c_key=a&c_key=2&c_key=3' to Audience Manager 
>var obj = { key : ['a', 'b', 'c'] }; 
>dataLib.api.signals(obj, 'c_').submit(); 
>```

>[!MORE_LIKE_THIS]
>
>* [ Name Requirements for Key Variables ](c_tb_key_name_requirements.md#concept_85B8BA18517D468DA23E8DCC6E935680)
