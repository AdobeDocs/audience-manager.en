---
description: A POST method that lets you create a destination that accepts segments that contain multiple keys with different values (e.g., gender=male
description_color: red).
description_gender: female
seo-description: A POST method that lets you create a destination that accepts segments that contain multiple keys with different values (e.g., gender=male
seo-description_color: red).
seo-description_gender: female
seo-title: Create a Cookie Destination  Multi-Key, Non-Serialized
solution: Audience Manager
title: Create a Cookie Destination  Multi-Key, Non-Serialized
uuid: 4843d81b-0a41-4037-b2e4-ca6c49d0f6d5
index: y
internal: n
snippet: y
translate: y
---

# Create a Cookie Destination: Multi-Key, Non-Serialized


>**Request** 

>` POST https://api.demdex.com/v1/destinations/` 

>**Sample Request** 

>All request values are required unless otherwise indicated. >
>```
>{ 
>   "name":"Ad Server Multi-Key Not Serialized", 
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
>   "serializationEnabled":false 
>}
>```


>**Sample Response** 

>A successful update returns response code ` 201 created` and the destination. >
>```
>{ 
>   "destinationType":"ADS", 
>   "destinationId":4037, 
>   "pid":1099, 
>   "name":"Ad Server Multi-Key Not Serialized", 
>   "status":1, 
>   "destinationType":"ADS", 
>   "createTime":1338938666000, 
>   "updateTime":1338938666000, 
>   "crUID":694, 
>   "upUID":694, 
>   "domainRestrictions":"all_domains", 
>   "cnameDomain":"adobe.com", 
>   "cookieName":"adobe", 
>   "keySeparator":"=", 
>   "valueSeparator":",", 
>   "formatType":"key_value", 
>   "transferMethod":0, 
>   "serializationEnabled":false, 
>   "maxSize":2048, 
>   "ttl":0, 
>   "siteIDs":[ 
>  
>   ], 
>   "uparamEnabled":false 
>}
>```

