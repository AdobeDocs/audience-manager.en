---
description: A POST method that lets you create a destination that accepts segments that contain multiple keys and values (e.g., gender=male, female
description_color: blue, red, green).
seo-description: A POST method that lets you create a destination that accepts segments that contain multiple keys and values (e.g., gender=male, female
seo-description_color: blue, red, green).
seo-title: Create a Cookie Destination  Multi-Key, Serialized
solution: Audience Manager
title: Create a Cookie Destination  Multi-Key, Serialized
uuid: 4d73d7b1-725f-4529-84bd-de3fd8a44e32
index: y
internal: n
snippet: y
translate: y
---

# Create a Cookie Destination: Multi-Key, Serialized


>**Request** 

>` POST https://api.demdex.com/v1/destinations/` 

>**Sample Request** 

>All request values are required unless otherwise indicated. >
>```
>{ 
>   "name":"Cookie Destination Multi-Key Serialized", 
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
>   "formatType":"key_value", 
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
>   "destinationId":4038, 
>   "pid":1099, 
>   "name":"Ad Server Multi-Key Serialized", 
>   "status":"active", 
>   "destinationType":"ADS", 
>   "createTime":1338938872000, 
>   "updateTime":1338938872000, 
>   "crUID":694, 
>   "upUID":694, 
>   "domainRestrictions":"all_domains", 
>   "cnameDomain":"adobe.com", 
>   "cookieName":"adobe", 
>   "keySeparator":"=", 
>   "valueSeparator":",", 
>   "formatType":"key_value", 
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
