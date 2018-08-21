---
description: A POST method that lets you create a cookie destination that accepts segments composed of single key-value pairs (e.g., gender=male or gender=female).
seo-description: A POST method that lets you create a cookie destination that accepts segments composed of single key-value pairs (e.g., gender=male or gender=female).
seo-title: Create a Cookie Destination  Single-Key, Non-Serialized
solution: Audience Manager
title: Create a Cookie Destination  Single-Key, Non-Serialized
uuid: 5ff4507f-ce62-4d16-b34a-33818cfb6806
index: y
internal: n
snippet: y
translate: y
---

# Create a Cookie Destination: Single-Key, Non-Serialized


>**Request** 

>` POST https://api.demdex.com/v1/destinations/` 

>**Sample Request** 

>All request values are required unless otherwise indicated. >
>```
>{
>   "name":"Cookie Destination Single Key Not Serialized",
>   "destinationType":"ADS",
>   "adServerTypeID":1,
>   "cookieName":"adobe",
>   "cnameDomain":"adobe.com",
>   "maxSize":"2048",
>   "ttl":"0",
>   "domainRestrictions":"inclusion",
>   "siteIDs":[
>      312
>   ],
>   "formatType":"single_key",
>   "singleKey":"key",
>   "keySeparator":"=",
>   "valueSeparator":",",
>   "serializationEnabled":false
>}
>```


>**Sample Response** 

>A successful update returns response code ` 201 created` and the destination. >
>```
>{
>   "destinationType":"ADS",
>   "destinationId":4035,
>   "pid":1099,
>   "name":"Cookie Destination Single Key Not Serialized",
>   "status":"active",
>   "destinationType":"ADS",
>   "createTime":1338937984000,
>   "updateTime":1338937984000,
>   "crUID":694,
>   "upUID":694,
>   "domainRestrictions":"inclusion",
>   "cnameDomain":"adobe.com",
>   "cookieName":"adobe",
>   "singleKey":"key",
>   "keySeparator":"=",
>   "valueSeparator":",",
>   "formatType":"single_key",
>   "transferMethod":0,
>   "serializationEnabled":false,
>   "maxSize":2048,
>   "ttl":0,
>   "siteIDs":[
>      312
>   ],
>   "uparamEnabled":false
>}
>
>```

>[!MORE_LIKE_THIS]
>
>* [ Destination Serialization ](c_dest_serialized.md#concept_02436A7C6C574C799F079EB731A63262)
>* [ Key-Value Pairs Explained ](c_key_value_explained.md#concept_E4236E003076483AA939791FE2492B49)
