---
description: useCORSOnly is a boolean true/false parameter that controls how the browser requests resources from other domains.
seo-description: useCORSOnly is a boolean true/false parameter that controls how the browser requests resources from other domains.
seo-title: useCORSOnly
solution: Audience Manager
title: useCORSOnly
uuid: ceca28cc-abc6-46a9-9ffb-7584eec84561
index: y
internal: n
snippet: y
translate: y
---

# useCORSOnly

**Overview** 

` useCORSOnly` is false by default. False means the browser can perform resource checks with CORS or JSONP. However, DIL always tries to request resources with CORS first. It reverts to JSONP on older browsers that do not support CORS. If you need to force the browser to use CORS only, such as with sites that have high-security requirements, set ` useCORSOnly:true`. 

**Code Sample** 


```
jsvar dilInstance = DIL.create({ 
     ... 
     useCORSOnly: true 
});
```



>[!IMPORTANT]
>
>
>* We recommend that you set ` useCORSOnly: true` only when you're sure that your site visitors have browsers that support this feature.
>* When ` useCORSOnly: true`, DIL will not make ID calls from Internet Explorer version 9 or older.



>[!MORE_LIKE_THIS]
>
>* [ DIL create ](r_dil_create.md#reference_F87131F6C1CC4ECCA064B24B91710FD4)
>* [  ](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-use-cors-only.html)
>* [  ](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-cors.html)
