---
description: A GET method that returns the destination for the specified destinationId.
seo-description: A GET method that returns the destination for the specified destinationId.
seo-title: Return A Destination by Destination ID
solution: Audience Manager
title: Return A Destination by Destination ID
uuid: c1041d8b-8682-4024-972a-175f83d510f1
index: y
internal: n
snippet: y
translate: y
---

# Return A Destination by Destination ID


>**Request** 

>` GET https://api.demdex.com/v1/destinations/<destinationId>` 
>>[!NOTE]
>>
>>To populate the ` mappings` field pass in ` includeMappings=true` in the URL. 
>


>**Sample Response** >
>```
>{ 
>   "destinationType":"PUSH", 
>   "destinationId":314, 
>   "dataSourceId":null, 
>   "pid":1099, 
>   "name":"sample destination", 
>   "description":"Turn", 
>   "startDate":null, 
>   "endDate":null, 
>   "status":"active", 
>   "destinationType":"PUSH", 
>   "createTime":1281997484000, 
>   "updateTime":1300752888000, 
>   "crUID":224, 
>   "upUID":308, 
>   "domainRestrictions":"ALL_DOMAINS", 
>   "tagType":0, 
>   "serializationEnabled":false, 
>   "urlFormatString":null, 
>   "secureUrlFormatString":null, 
>   "delimiter":null, 
>   "mappings":null 
>}
>```

