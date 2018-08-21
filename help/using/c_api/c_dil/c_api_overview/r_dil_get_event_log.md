---
description: Returns chronologically sorted event log data as an array of strings. Useful for debugging and troubleshooting.
seo-description: Returns chronologically sorted event log data as an array of strings. Useful for debugging and troubleshooting.
seo-title: getEventLog
solution: Audience Manager
title: getEventLog
uuid: 0249255d-9f49-4415-ba72-dfea4274d610
index: y
internal: n
snippet: y
translate: y
---

# getEventLog


>**Function Signature:** ` dil.api.getEventLog: function () {}` 

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
<i>123, 456, 789</i>]).logs({ 
>     file: 'dil.js', 
>     message: 'This is the first request' 
>});.signals({ 
>     c_zdid:  
<i>1111</i> 
>     d_dma: ' 
<i>default</i>' 
>});.submit(); 
> 
>//Check log for messages 
>var log = dataLib.api.getEventLog(); 
>if (log && log.length) { 
>     alert(log.join('\n')); 
>}else{ 
>     alert('No log messages'); 
>}
>```

