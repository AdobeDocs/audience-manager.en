---
description: A GET method that returns ID, name, and description for the available algorithms. Currently, TraitWeight (ID 1) is the only available algorithm.
seo-description: A GET method that returns ID, name, and description for the available algorithms. Currently, TraitWeight (ID 1) is the only available algorithm.
seo-title: Return Properties for an Algorithm
solution: Audience Manager
title: Return Properties for an Algorithm
uuid: 963b8b6d-5821-446e-80df-c4136da69ba7
index: y
internal: n
snippet: y
translate: y
---

# Return Properties for an Algorithm


>**Request** 

>` GET https://api.demdex.com/v1/algorithms/` 

>**Sample Response** 

>A successful response returns response code ` 200 OK` and the list of algorithm IDs, name, and a brief description. >
>```
>[
>{
>  "algoTypeId": 1,
>  "name": "Trait Weight",
>  "description": "Trait Weight"
>}
>]
>```

