---
description: A POST method that lets you map a segment to multi-key, non-serialized cookie destination.
seo-description: A POST method that lets you map a segment to multi-key, non-serialized cookie destination.
seo-title: Map a Segment to a Cookie Destination  Multi-Key, Non-Serialized
solution: Audience Manager
title: Map a Segment to a Cookie Destination  Multi-Key, Non-Serialized
uuid: 2a4770f8-4386-43ce-b479-fe3b37594f73
index: y
internal: n
snippet: y
translate: y
---

# Map a Segment to a Cookie Destination: Multi-Key, Non-Serialized


>**Request** 

>` POST https://api.demdex.com/v1/destinations/ *` <destinationId>`*/mappings/` 

>**Sample Request** 

>In the request, the ` traitAlias` and ` valueAlias` set the key and the value respectively in a key-value pair. All request values are required unless otherwise indicated. >
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
>   "mappingId":65338, 
>   "traitType":"SEGMENT", 
>   "traitValue":0, 
>   "destinationId":4037, 
>   "elementName":"Sample Games", 
>   "elementDescription":"Migration of Sample Games Pixel", 
>   "elementStatus":"active", 
>   "createTime":1338941092000, 
>   "updateTime":1338941092000, 
>   "crUID":694, 
>   "upUID":694, 
>   "sid":87723, 
>   "startDate":"2012-07-03", 
>   "endDate":null, 
>   "priority":1, 
>   "traitAlias":"type", 
>   "valueAlias":"123" 
>}
>```

