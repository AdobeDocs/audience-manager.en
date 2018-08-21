---
description: A GET method that returns accuracy and reach values for your algorithmic model.
seo-description: A GET method that returns accuracy and reach values for your algorithmic model.
seo-title: Return Accuracy and Reach Values for a Model
solution: Audience Manager
title: Return Accuracy and Reach Values for a Model
uuid: a8a3199c-0e6e-4a68-bb5c-942cbe545572
index: y
internal: n
snippet: y
translate: y
---

# Return Accuracy and Reach Values for a Model


>**Request** 

>` GET https://api.demdex.com/v1/models/ *` <model-id>`*/runs/latest/stats`/ 

>**Sample Response** >
>```
>[ 
>  { 
>    "AccuracyValue": 0.12, 
>    "ReachValue": 0 
>   }, 
>  { 
>    "AccuracyValue": 0.18, 
>    "ReachValue": 0 
>   }, 
>  { 
>    "AccuracyValue": 0.19, 
>    "ReachValue": 23232 
>   }, 
>  { 
>    "AccuracyValue": 0.28, 
>    "ReachValue": 33432 
>   } 
>]
>```

