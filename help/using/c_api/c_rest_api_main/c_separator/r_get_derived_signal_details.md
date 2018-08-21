---
description: A GET method that returns details for an individual derived signal.
seo-description: A GET method that returns details for an individual derived signal.
seo-title: Return Properties for a Derived Signal
solution: Audience Manager
title: Return Properties for a Derived Signal
uuid: 703fae47-7106-44a3-8fc4-87ec1ed74ce8
index: y
internal: n
snippet: y
translate: y
---

# Return Properties for a Derived Signal


>**Request** 

>` GET https://api.demdex.com/v1/signals/derived/ <derivedSignalId>` 

>**Sample Response** 

>A successful request returns response code ` 200 OK` and data as shown below. >
>```
>{ 
>    "derivedSignalId": 2, 
>    "targetKey": "targetKey", 
>    "sourceKey": "sourceKey", 
>    "integrationCode": null, 
>    "targetValue": "targetValue", 
>    "pid": 1099, 
>    "updateTime": 1319752928000, 
>    "version": 1, 
>    "upUID": 507, 
>    "crUID": 507, 
>    "sourceValue": "sourceValue", 
>    "createTime": 1319752831000 
>}
>```

