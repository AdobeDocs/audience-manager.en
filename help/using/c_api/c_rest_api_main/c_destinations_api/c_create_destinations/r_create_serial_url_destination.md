---
description: A POST method that lets you create a destination that accepts multiple values associated with a single key (e.g., color=blue, red, green).
seo-description: A POST method that lets you create a destination that accepts multiple values associated with a single key (e.g., color=blue, red, green).
seo-title: Create a Serialized URL Destination
solution: Audience Manager
title: Create a Serialized URL Destination
uuid: 8511816b-ca3c-40ed-936e-65af09769b8e
index: y
internal: n
snippet: y
translate: y
---

# Create a Serialized URL Destination


>**Request** 

>` POST https://api.demdex.com/v1/destinations/` 

>**Sample Request** 

>Specify the secure URL and delimiter for the key-value pair passed in to the destination. All request values are required unless otherwise indicated. >
>```
>{
>   "name":"Sample URL Destination (Serialized)",
>   "description":"",
>   "destinationType":"PUSH",
>   "serializationEnabled":true,
>   "urlFormatString":"http://www.adobe.com/send?data=%ALIAS%",
>   "secureUrlFormatString":"https://www.adobe.com/%ALIAS%",
>   "delimiter":","
>}
>```


>**Sample Response** 

>A successful update returns response code ` 201 created` and the destination. >
>```
>{
>   "destinationType":"PUSH",
>   "destinationId":4034,
>   "dataSourceId":null,
>   "pid":1099,
>   "name":"Sample URL Destination (Serialized)",
>   "description":"",
>   "startDate":null,
>   "endDate":null,
>   "status":"active",
>   "destinationType":"PUSH",
>   "createTime":1338937420000,
>   "updateTime":1338937420000,
>   "crUID":694,
>   "upUID":694,
>   "domainRestrictions":"all_domains",
>   "tagType":0,
>   "serializationEnabled":true,
>   "urlFormatString":"http://www.adobe.com/send?%ALIAS%",
>   "secureUrlFormatString":"https://www.adobe.com/%ALIAS%",
>   "delimiter":"-",
>   "mappings":null
>}
>```

>[!MORE_LIKE_THIS]
>
>* [ Destination Serialization ](c_dest_serialized.md#concept_02436A7C6C574C799F079EB731A63262)
