---
description: A POST method that lets you create a destination that accepts segments composed of single key-value pairs (e.g., gender=male or gender=female).
seo-description: A POST method that lets you create a destination that accepts segments composed of single key-value pairs (e.g., gender=male or gender=female).
seo-title: Create a Non-Serial URL Destination
solution: Audience Manager
title: Create a Non-Serial URL Destination
uuid: 17edd65b-99c5-4ddb-80c9-e19be8215671
index: y
internal: n
snippet: y
translate: y
---

# Create a Non-Serial URL Destination


>**Request** 

>` POST https://api.demdex.com/v1/destinations/` 

>**Sample Request** 

>This request creates a single destination. All request values are required unless otherwise indicated. >
>```
>{
>   "name":"Sample URL Destination (not serialized)",
>   "description":"",
>   "destinationType":"PUSH",
>   "serializationEnabled":false
>}
>```


>**Sample Response** 

>A successful request returns ` 201 created` and the destination. 

>
>```
>{
>   "destinationType":"PUSH",
>   "destinationId":4033,
>   "dataSourceId":null,
>   "pid":1099,
>   "name":"Sample URL Destination (not serialized)",
>   "description":"",
>   "startDate":null,
>   "endDate":null,
>   "status":"ACTIVE",
>   "destinationType":"PUSH",
>   "createTime":1338937116000,
>   "updateTime":1338937116000,
>   "crUID":694,
>   "upUID":694,
>   "domainRestrictions":"all_domains",
>   "tagType":0,
>   "serializationEnabled":false,
>   "urlFormatString":"http://www.adobe.com/send?%ALIAS%",
>   "secureUrlFormatString":"https://www.adobe.com/send?%ALIAS%",
>   "delimiter":null,
>   "mappings":null
>}
>
>```

>[!MORE_LIKE_THIS]
>
>* [ Destination Serialization ](c_dest_serialized.md#concept_02436A7C6C574C799F079EB731A63262)
