---
description: A POST method that lets you map a segment to single-key, non-serialized cookie destination.
seo-description: A POST method that lets you map a segment to single-key, non-serialized cookie destination.
seo-title: Map a Segment to a Cookie Destination  Single-Key, Non-Serialized
solution: Audience Manager
title: Map a Segment to a Cookie Destination  Single-Key, Non-Serialized
uuid: 1205dde3-752f-48d8-81ed-f0a3bb393af2
index: y
internal: n
snippet: y
translate: y
---

# Map a Segment to a Cookie Destination: Single-Key, Non-Serialized


>**Request** 

>` POST https://api.demdex.com/v1/destinations/ *` <destinationId>`*/mappings/` 

>**Sample Request** 

>In the request, the ` valueAlias` corresponds to the value in a key-value pair. All request values are required unless otherwise indicated. >
>```
>{ 
>   "sid":87723, 
>   "traitType":"SEGMENT", 
>   "startDate":"2012-07-04", 
>   "valueAlias":"123" 
>}
>```


>**Sample Response** >
>```
>{ 
>   "destinationMappingId":65336, 
>   "traitType":"SEGMENT", 
>   "traitValue":0, 
>   "destinationId":4035, 
>   "elementName":"Sample Games", 
>   "elementDescription":"Migration of Sample Games Pixel", 
>   "elementStatus":"active", 
>   "createTime":1338940704000, 
>   "updateTime":1338940704000, 
>   "crUID":694, 
>   "upUID":694, 
>   "sid":87723, 
>   "startDate":"2012-07-03", 
>   "endDate":null, 
>   "priority":1, 
>   "traitAlias":null, 
>   "valueAlias":"123" 
>}
>```

