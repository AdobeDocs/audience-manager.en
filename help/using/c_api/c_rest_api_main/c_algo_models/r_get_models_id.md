---
description: A GET method that returns algorithmic model details based on the passed in model ID.
seo-description: A GET method that returns algorithmic model details based on the passed in model ID.
seo-title: Return Properties for a Model by ID
solution: Audience Manager
title: Return Properties for a Model by ID
uuid: 30f0f1dc-0e1d-4ace-8c2c-e2ab1d914e22
index: y
internal: n
snippet: y
translate: y
---

# Return Properties for a Model by ID


>**Request** 

>` GET https://api.demdex.com/v1/models/ *` <model-id>`*` 

>**Sample Response** 

>A successful request returns details for the model. An unsuccessful request throws an exception and related [ error code ](../../../c_api/c_rest_api_main/c_rest_api_overview/r_api_http_response_codes.md#reference_2AC89154A26E49A48E0DDD8DA520757F). >
>```
>{ 
>     "algoModelId": 16, 
>     "pid": 1099, 
>     "name": "newmodel78", 
>     "description": "descriptions is in the name", 
>     "algoTypeId": 1, 
>     "intervalSeconds": 864000, 
>     "lookBackPeriod": 30, 
>     "crUID": 3, 
>     "upUID": 3, 
>     "status": 1, 
>     "processingStatus": 0, 
>     "createTime": 1344969143000, 
>     "algoModelVersion": 0, 
>     "dataSources": [ 
>                       4 
>                     ], 
>     "sid": 8, 
>     "latestRunTS": 10000, 
>     "baselineTraitType": 3, 
>     "updateTime": 1344969143000 
>  } 
> 
>
>```

