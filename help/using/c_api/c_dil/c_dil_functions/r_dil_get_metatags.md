---
description: Searches for specific content defined in the meta tags on a Web page and returns that data in an object.
seo-description: Searches for specific content defined in the meta tags on a Web page and returns that data in an object.
seo-title: getMetaTags
solution: Audience Manager
title: getMetaTags
uuid: 48ea216e-5ecc-421f-9ea0-8bdb9db59399
index: y
internal: n
snippet: y
translate: y
---

# getMetaTags


>**Function signature:** ` DIL.tools.getMetaTags( 1 or more parameters)` 

>**Function Parameters** 

>` getMetaTags` accepts one or more name parameters (string type) to search for. It returns an object composed of key-value pairs. 

>**Sample Code** >
>```
>var dataLib = DIL.create({ 
>     partner: ' 
<i>partnerName'</i>, 
>     containerNSID:  
<i>containerNSID</i> 
>}); 
> 
>dataLib.api.signals(DIL.tools.getMetaTags(' 
<i>application</i>', ' 
<i>keywords</i>', 
>' 
<i>description</i>'), 'c_').submit();
>```

