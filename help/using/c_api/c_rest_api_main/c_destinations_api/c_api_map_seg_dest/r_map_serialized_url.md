---
description: A POST method that lets you map a segment to a serialized URL destination.
seo-description: A POST method that lets you map a segment to a serialized URL destination.
seo-title: Map a Segment to a Serialized URL Destination
solution: Audience Manager
title: Map a Segment to a Serialized URL Destination
uuid: 73b47b87-4698-401b-975f-c3ebe5839509
index: y
internal: n
snippet: y
translate: y
---

# Map a Segment to a Serialized URL Destination


>**Request** 

>` POST https://api.demdex.com/v1/destinations/ *` <dataOrderId>`*/traits/` 

>**Sample Request** 

>In the request, the ` traitAlias` corresponds to the key in a key-value pair. All request values are required unless otherwise indicated. >
>```
>{ 
>   "sid":87723, 
>   "traitType":"SEGMENT", 
>   "startDate":"2012-07-04", 
>   "traitAlias":"123" 
>}
>```


>**Sample Response** >
>```
>{ 
>   "mappingId":65335, 
>   "traitType":"SEGMENT", 
>   "traitValue":0, 
>   "destinationId":4034, 
>   "elementName":"Sample Games", 
>   "elementDescription":"Migration of Sample Games Pixel", 
>   "elementStatus":"active", 
>   "createTime":1338940401000, 
>   "updateTime":1338940401000, 
>   "crUID":694, 
>   "upUID":694, 
>   "sid":87723, 
>   "startDate":"2012-07-03", 
>   "endDate":null, 
>   "priority":null, 
>   "url":"123", 
>   "secureUrl":"123", 
>   "tagCode":null, 
>   "secureTagCode":null, 
>   "traitAlias":"123" 
>}
>```

