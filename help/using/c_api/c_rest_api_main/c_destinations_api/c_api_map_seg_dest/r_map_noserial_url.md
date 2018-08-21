---
description: A POST method that lets you map a segment to a non-serial URL destination.
seo-description: A POST method that lets you map a segment to a non-serial URL destination.
seo-title: Map a Segment to a Non-Serialized URL Destination
solution: Audience Manager
title: Map a Segment to a Non-Serialized URL Destination
uuid: f4ee9abd-014c-48f1-a7fd-49d45c93a819
index: y
internal: n
snippet: y
translate: y
---

# Map a Segment to a Non-Serialized URL Destination


>**Request** 

>` POST https://api.demdex.com/v1/destinations/ *` <destinationId>`*/mappings/` 

>**Sample Request** 

>All request values are required unless otherwise indicated. >
>```
>{ 
>   "sid":87723, 
>   "traitType":"SEGMENT", 
>   "url":"http://adobe.com", 
>   "startDate":"2012-07-04" 
>}
>```


>**Sample Response** >
>```
>{ 
>   "mappingId":65334, 
>   "traitType":"SEGMENT", 
>   "traitValue":0, 
>   "destinationId":4033, 
>   "elementName":"Sample games", 
>   "elementDescription":"Sample games pixel", 
>   "elementStatus":"active", 
>   "createTime":1338940094000, 
>   "updateTime":1338940094000, 
>   "crUID":694, 
>   "upUID":694, 
>   "sid":87723, 
>   "startDate":"2012-07-03", 
>   "endDate":null, 
>   "priority":null, 
>   "url":"http://adobe.com", 
>   "secureUrl":null, 
>   "tagCode":null, 
>   "secureTagCode":null, 
>   "traitAlias":null 
>}
>```

