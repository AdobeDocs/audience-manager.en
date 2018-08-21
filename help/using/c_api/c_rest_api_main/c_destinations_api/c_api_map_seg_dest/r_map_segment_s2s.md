---
description: A POST method that lets you map a segment to an existing server-to-server destination. Note, however, that you cannot create server-to-server destinations with these currently available API methods.
seo-description: A POST method that lets you map a segment to an existing server-to-server destination. Note, however, that you cannot create server-to-server destinations with these currently available API methods.
seo-title: Map a Segment to a Server-to-Server Destination
solution: Audience Manager
title: Map a Segment to a Server-to-Server Destination
uuid: fac5be43-ae0b-4019-a031-a8e9cd8a7a47
index: y
internal: n
snippet: y
translate: y
---

# Map a Segment to a Server-to-Server Destination


>**Request** 

>` POST https://api.demdex.com/v1/destinations/ *` <destinationId>`*/mappings/` 

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
>   "destinationMappingId":65341, 
>   "traitType":"SEGMENT", 
>   "traitValue":0, 
>   "destinationId":566, 
>   "elementName":"Sample", 
>   "elementDescription":"", 
>   "elementStatus":"active", 
>   "createTime":1338942118000, 
>   "updateTime":1338942118000, 
>   "crUID":308, 
>   "upUID":308, 
>   "sid":84326, 
>   "startDate":"2012-07-03", 
>   "endDate":null, 
>   "priority":null, 
>   "traitAlias":"123" 
>}
>```

