---
description: A GET method that returns algorithm details (ID, name, and description) based on the passed in algorithm ID. Currently, TraitWeight (ID 1) is the only available algorithm.
seo-description: A GET method that returns algorithm details (ID, name, and description) based on the passed in algorithm ID. Currently, TraitWeight (ID 1) is the only available algorithm.
seo-title: Return Properties for an Algorithm by ID
solution: Audience Manager
title: Return Properties for an Algorithm by ID
uuid: a1f269c3-96fe-42bd-87ff-e860fd950154
index: y
internal: n
snippet: y
translate: y
---

# Return Properties for an Algorithm by ID


>**Request** 

>` GET https://api.demdex.com/v1/algorithms/ *` <algotype-id>`*/` 

>**Sample Response** 

>A successful response returns response code ` 200 OK` and the algorithm ID, name, and a brief description. >
>```
>{ 
>  "algoTypeId": 1, 
>  "name": "TF-IDF", 
>  "description": "TF-IDF" 
>}
>```

