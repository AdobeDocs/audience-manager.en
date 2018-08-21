---
description: A POST method that lets you create a destination that accepts multiple values associated with a single key (e.g., color=blue, red, green).
seo-description: A POST method that lets you create a destination that accepts multiple values associated with a single key (e.g., color=blue, red, green).
seo-title: Create a Cookie Destination  Single Key, Serialized
solution: Audience Manager
title: Create a Cookie Destination  Single Key, Serialized
uuid: 30d7e847-bf7f-4899-a9cc-c86eed7e00b0
index: y
internal: n
snippet: y
translate: y
---

# Create a Cookie Destination: Single Key, Serialized


>**Request** 

>` POST https://api.demdex.com/v1/destinations/` 

>**Sample Request** 

>All request values are required unless otherwise indicated. >
>```
>{
>   "name":"Cookie Destination Single Key Serialized",
>   "destinationType":"ADS",
>   "adServerTypeID":1,
>   "cookieName":"adobe",
>   "cnameDomain":"adobe.com",
>   "maxSize":"2048",
>   "ttl":"0",
>   "domainRestrictions":"all_domains",
>   "siteIDs":[
>
>   ],
>   "formatType":"single_key",
>   "singleKey":"k",
>   "keySeparator":"=",
>   "valueSeparator":",",
>   "serializationEnabled":true,
>   "serializationSeparator":"#"
>}
>```


>**Sample Response** 

>A successful update returns response code ` 201 created` and the destination. >
>```
>{
>   "destinationType":"ADS",
>   "destinationId":4036,
>   "pid":1099,
>   "name":"Cookie Destination Single Key Serialized",
>   "status":"active",
>   "destinationType":"ADS",
>   "createTime":1338938329000,
>   "updateTime":1338938329000,
>   "crUID":694,
>   "upUID":694,
>   "domainRestrictions":"all_domains",
>   "cnameDomain":"adobe.com",
>   "cookieName":"adobe",
>   "singleKey":"k",
>   "keySeparator":"=",
>   "valueSeparator":",",
>   "formatType":"single_key",
>   "transferMethod":0,
>   "serializationEnabled":true,
>   "serializationSeparator":"#",
>   "maxSize":2048,
>   "ttl":0,
>   "siteIDs":[
>
>   ],
>   "uparamEnabled":false
>}
>```

>[!MORE_LIKE_THIS]
>
>* [ Destination Serialization ](c_dest_serialized.md#concept_02436A7C6C574C799F079EB731A63262)
>* [ Key-Value Pairs Explained ](c_key_value_explained.md#concept_E4236E003076483AA939791FE2492B49)
