---
description: A PUT method that lets you update a mapping to a destination by the specified mappingId.
seo-description: A PUT method that lets you update a mapping to a destination by the specified mappingId.
seo-title: Update a Mapping to a Destination by Mapping ID
solution: Audience Manager
title: Update a Mapping to a Destination by Mapping ID
uuid: 21d7f69c-218e-41a2-82cf-7492f4db952a
index: y
internal: n
snippet: y
translate: y
---

# Update a Mapping to a Destination by Mapping ID


>**Request** 

>` PUT https://api.demdex.com/v1/destinations/mappings/ *` <mappingId>`*` 

>**Sample Request** 

>All request values are required unless otherwise indicated. >
>```
>{ 
>   "sid": 105123, 
>   "traitType":"SEGMENT", 
>   "url":"http://adobe.com", 
>   "startDate":"2012-11-20" 
>}
>```


>**Sample Response** >
>```
>{ 
>    "mappingId": 103453, 
>    "traitType": "SEGMENT", 
>    "traitValue": 0, 
>    "destinationId": 780, 
>    "elementName": "sample", 
>    "elementDescription": "test", 
>    "elementStatus": "active", 
>    "createTime": 1353373005000, 
>    "updateTime": 1353373005000, 
>    "crUID": 1065, 
>    "upUID": 1065, 
>    "sid": 105123, 
>    "startDate": "2012-11-19", 
>    "endDate": null, 
>    "priority": null, 
>    "url": "http://www.adobe.com/send?%ALIAS%", 
>    "secureUrl": null, 
>    "tagCode": null, 
>    "secureTagCode": null, 
>    "traitAlias": null 
>}
>```

