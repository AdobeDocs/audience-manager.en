---
description: A POST method that lets you map a segment to a multi-key, serialized cookie destination.
seo-description: A POST method that lets you map a segment to a multi-key, serialized cookie destination.
seo-title: Map a Segment to a Cookie Destination  Multi-Key, Serialized
solution: Audience Manager
title: Map a Segment to a Cookie Destination  Multi-Key, Serialized
uuid: dd44156a-0ecc-47e2-b3d2-bd15009ef9d2
index: y
internal: n
snippet: y
translate: y
---

# Map a Segment to a Cookie Destination: Multi-Key, Serialized


>**Request** 

>` POST https://api.demdex.com/v1/destinations/ *` <destinationId>`*/mappings/` 

>**Sample Request** 

>In the request, the ` traitAlias` and ` valueAlias` set the key and the value in a key-value pair. All request values are required unless otherwise indicated. >
>```
>{ 
>   "sid":87723, 
>   "traitType":"SEGMENT", 
>   "startDate":"2012-07-04", 
>   "traitAlias":"type", 
>   "valueAlias":"123" 
>}
>```


>**Sample Response** >
>```
>{ 
>   "destinationMappingId":65340, 
>   "traitType":"SEGMENT", 
>   "traitValue":0, 
>   "destinationId":4038, 
>   "elementName":"Sample Games", 
>   "elementDescription":"Migration of Sample Games Pixel", 
>   "elementStatus":"active", 
>   "createTime":1338941273000, 
>   "updateTime":1338941273000, 
>   "crUID":694, 
>   "upUID":694, 
>   "sid":87723, 
>   "startDate":"2012-07-03", 
>   "endDate":null, 
>   "priority":2, 
>   "traitAlias":"type", 
>   "valueAlias":"123" 
>}
>```

