---
description: A PUT method that lets you revise the model's name, description, and status.
seo-description: A PUT method that lets you revise the model's name, description, and status.
seo-title: Update a Model
solution: Audience Manager
title: Update a Model
uuid: c63f4fbf-ce58-4757-8ddc-3587a3929928
index: y
internal: n
snippet: y
translate: y
---

# Update a Model


>**Request** 

>` PUT https://api.demdex.com/v1/models/ *` <model-id>`*/` 

>**Sample Request** 

>All request values are required unless otherwise indicated. Model status settings include ` active` and ` inactive` only. >
>```
>{ 
>  "name" : "New name", 
>  "description" : "Revised description", 
>  "status" : "active", 
>  "algoTypeId":1, 
>  "dataSources":[3,4}, 
>  "sid":8 
>  "lookBackPeriod":90 
>}
>```


>**Sample Response** >
>```
>{ 
>    "algoModelId": 1394, 
>    "pid": 1, 
>    "name": "New name", 
>    "description": "Revised description", 
>    "algoTypeId": 1, 
>    "intervalSeconds": 86400, 
>    "lookBackPeriod": 30, 
>    "crUID": 3, 
>    "upUID": 3, 
>    "status": 1, 
>    "processingStatus": 0, 
>    "createTime": 1346092322000, 
>    "algoModelVersion": 0, 
>    "dataSources": [size(2) 
>                      3, 
>                      4 
>                    ], 
>    "sid": 8, 
>    "latestRunTS": 10000, 
>    "baselineTraitType": 3, 
>    "updateTime": 1346092322000 
>  }
>```

