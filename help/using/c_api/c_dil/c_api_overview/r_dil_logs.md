---
description: Add data to log files in the pending request.
seo-description: Add data to log files in the pending request.
seo-title: logs
solution: Audience Manager
title: logs
uuid: 79392d72-eedf-491a-b7bb-e3554c4cb8b2
index: y
internal: n
snippet: y
translate: y
---

# logs


>**Function signature:** ` logs: function {key1:value1, key2:value2}` 

>**Response** 

>Returns the API object of the current DIL instance. 

>**Sample Code** 

>
>```
>var partnerObject = DIL.create({ 
>     partner: ' 
<i>partner</i>', 
>     containerNSID:  
<i>NSID</i> 
>}); 
>partnerObject.api.logs({ 
>     file: 'dil.js', 
>     message: 'This is the first request' 
>});
>```

