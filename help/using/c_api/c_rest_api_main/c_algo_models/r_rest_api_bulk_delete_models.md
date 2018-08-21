---
description: A POST method that lets you bulk delete multiple models.
keywords: api getting started;get started api
seo-description: A POST method that lets you bulk delete multiple models.
seo-title: Delete Models
solution: Audience Manager
title: Delete Models
uuid: 10f63a98-b3db-41f8-afb5-2ea8c797e4dc
index: y
internal: n
snippet: y
translate: y
---

# Delete Models


>**Request** 

>` POST https://api.demdex.com/v1/models/bulk-delete/` 

>**Sample Request** 

>In the request body, pass in a JSON array that includes the model IDs you want to delete. >
>```
>[
>   111,
>   222
>]
>```


>**Sample Response** 

>Returns ` 204 No Content`. 
