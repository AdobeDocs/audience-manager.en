---
description: A GET method that returns details about the specified domain (for cookie destinations only).
seo-description: A GET method that returns details about the specified domain (for cookie destinations only).
seo-title: Return Properties for a Domain
solution: Audience Manager
title: Return Properties for a Domain
uuid: f1869697-59d9-476a-b937-1d7c160a1064
index: y
internal: n
snippet: y
translate: y
---

# Return Properties for a Domain


>**Request** 

>` GET ` https://api.demdex.com/v1/partner-sites/` *` <siteId>`*` 

>**Sample Response** 

>A successful response returns ` 200 OK` and data as shown in the sample below. Returns ` 404 Not found` if the site ID or partner is not found. >
>```
>{ 
>    "pid": 1111, 
>    "siteId": 111, 
>    "url": "example1.com" 
>}
>```

