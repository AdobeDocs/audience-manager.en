---
description: Returns the value of the container NSID for the DIL instance. Useful for debugging and troubleshooting.
seo-description: Returns the value of the container NSID for the DIL instance. Useful for debugging and troubleshooting.
seo-title: getContainerNSID
solution: Audience Manager
title: getContainerNSID
uuid: 2afffd1d-0d38-42e5-8327-c22576419221
index: y
internal: n
snippet: y
translate: y
---

# getContainerNSID


>**Function Signature:** ` dil.api.getContainerNSID: function () {}` 

>**Sample Code** >
>```
>var dataLib = DIL.create({ 
>     partner: ' 
<i>partnerName</i>', 
>     containerNSID:  
<i>containerNSID</i> 
>}); 
> 
>//Verify the container NSID 
>var nsid = dataLib.api.getContainerNSID();
>```

