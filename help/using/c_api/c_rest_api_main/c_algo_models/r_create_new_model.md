---
description: A POST method that lets you create a new algorithmic model.
keywords: api getting started;getting started api;get started api;api get started
seo-description: A POST method that lets you create a new algorithmic model.
seo-title: Create a New Model
solution: Audience Manager
title: Create a New Model
uuid: 2afaa6d5-a8d9-4674-af84-56ab7164ed77
index: y
internal: n
snippet: y
translate: y
---

# Create a New Model


>**Request** 

>` POST https://api.demdex.com/v1/models/` 

>**Sample Request** 

>All request values are required unless otherwise indicated. >
>```
>{ 
>  "name" : "New model", 
>  "description" : "Test Model", 
>  "dataSources" : [ 
<span class="varname"> <data_provider_id_1> </span>,  
<span class="varname"> <data_provider_id_2> </span>], 
>  "sid" : 8, 
>  "algoTypeId" :  
<span class="varname"> <Algorithm ID. Currently, only ID 1 is available> </span>, 
>  "lookBackPeriod" :  
<span class="varname"> <Specify 30, 60, or 90 days> </span> 
>} 
>
>```


>**Sample Response** >
>```
>{ 
>    "algoModelId": 1394, 
>    "pid": 1099, 
>    "name": "New model", 
>    "description": "Test Model", 
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

>[!MORE_LIKE_THIS]
>
>* [ Model Builder ](c_model_builder.md#concept_25287B0C161F4BFCBCCFEB5CC6E613D0)
