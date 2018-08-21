---
description: A POST method that lets you create a new derived signal.
seo-description: A POST method that lets you create a new derived signal.
seo-title: Create a New Derived Signal
solution: Audience Manager
title: Create a New Derived Signal
uuid: 51099e9d-6057-42f8-8915-bb3712de85b2
index: y
internal: n
snippet: y
translate: y
---

# Create a New Derived Signal


<a id="section_8D11215FA5324329A26BECCC7C3A1A9A"></a>

**Request** 

`POST https://api.demdex.com/v1/signals/derived/` 

>**Sample Request Body** 

>The JSON request body contains a source key and source value. These parameters are used to associate the source key-value pair with other traits that are associated (derived) from those values. For example, in this request the key-value pair ` product SKU=1234` are also associated with a related target key-value pair. Note, source key and value variables must be unique. All request values are required unless otherwise indicated. >
>```
>{
>    "sourceKey": "product SKU",
>    "sourceValue": "1234",
>    "targetKey": "camera",
>    "targetValue": "brand x"
>}
>```


>**Sample Response** 

>A successful update returns response code ` 201 Created` and data as shown below. An unsuccessful attempt returns response code ` 409 Conflict` if the source/target mapping already exists. >
>```
>{
>    "derivedSignalId": 2,
>    "targetKey": "camera",
>    "sourceKey": "product SKU",
>    "integrationCode": null,
>    "targetValue": "brand x",
>    "pid": 1099,
>    "updateTime": 1319752831000,
>    "version": 0,
>    "upUID": 507,
>    "crUID": 507,
>    "sourceValue": "1234",
>    "createTime": 1319752831000
>}
>```

