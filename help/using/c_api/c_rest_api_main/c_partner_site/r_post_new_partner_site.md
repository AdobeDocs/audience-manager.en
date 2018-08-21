---
description: A POST method that lets you create a new domain for (cookie destinations only).
seo-description: A POST method that lets you create a new domain for (cookie destinations only).
seo-title: Create a New Domain
solution: Audience Manager
title: Create a New Domain
uuid: f1666098-c5c6-4f69-bbc4-9427d94b04c6
index: y
internal: n
snippet: y
translate: y
---

# Create a New Domain


>**Request** 

>`POST ` https://api.demdex.com/v1/partner-sites/`` 

>**Sample Request** >
>```
>{
>   "url":"example1.com"
>}
>```

>**Sample Response**A successful response returns ` 201 created` and the partner site, including its unique ID. >
>```
>{
>    "pid": 1111,
>    "siteId": 111,
>    "url": "example1.com"
>}
>```

