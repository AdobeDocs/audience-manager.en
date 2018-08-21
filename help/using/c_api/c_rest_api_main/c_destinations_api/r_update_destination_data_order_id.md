---
description: A PUT method that lets you update an existing destination by destinationId.
seo-description: A PUT method that lets you update an existing destination by destinationId.
seo-title: Update a Destination by Destination ID
solution: Audience Manager
title: Update a Destination by Destination ID
uuid: 3e1162e9-f15e-4cc4-864b-b33162401c9f
index: y
internal: n
snippet: y
translate: y
---

# Update a Destination by Destination ID


>**Request** 

>` PUT https://api.demdex.com/v1/destinations/ *` <destinationId>`*` 

>**Sample Request** 

>All request values are required unless otherwise indicated. >
>```
>{ 
>   "name":"Updated URL Destination (not serialized)", 
>   "description":"new description", 
>   "destinationType":"PUSH", 
>   "serializationEnabled":false 
>}
>```


>**Sample Response** >
>```
>{ 
>    "destinationType": "PUSH", 
>    "destinationId": 780, 
>    "dataSourceId": null, 
>    "pid": 1099, 
>    "name": "Updated URL Destination (not serialized)", 
>    "description": "new description", 
>    "startDate": null, 
>    "endDate": null, 
>    "status": 1, 
>    "createTime": 1348851790000, 
>    "updateTime": 1353372029000, 
>    "crUID": 884, 
>    "upUID": 1065, 
>    "domainRestrictions":"all_domains", 
>    "tagType": 0, 
>    "serializationEnabled": false, 
>    "urlFormatString": null, 
>    "secureUrlFormatString": null, 
>    "delimiter": null, 
>    "mappings": null 
>}
>```

