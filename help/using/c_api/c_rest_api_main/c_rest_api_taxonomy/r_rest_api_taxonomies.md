---
description: A GET method that returns a list of the top-level categories in an array.
seo-description: A GET method that returns a list of the top-level categories in an array.
seo-title: Return all Taxonomic Categories
solution: Audience Manager
title: Return all Taxonomic Categories
uuid: 6d1f244c-afb2-4f1b-9931-4d1ee52266e0
index: y
internal: n
snippet: y
translate: y
---

# Return all Taxonomic Categories


>**Request** 

>` GET https://api.demdex.com/v1/taxonomies/0/` 

>**Sample Response** 

>Truncated for brevity. >
>```
>[
>    {
>        "crUID": 158,
>        "name": "Arts & Entertainment",
>        "upUID": 158,
>        "description": "Arts & Entertainment",
>        "categoryID": 1,
>        "parentCategoryID": 0
>    },
>    {
>        "crUID": 158,
>        "name": "Automotive",
>        "upUID": 158,
>        "description": "Automotive",
>        "categoryID": 2,
>        "parentCategoryID": 0
>    },
>    {
>        "crUID": 158,
>        "name": "Business",
>        "upUID": 158,
>        "description": "Business",
>        "categoryID": 3,
>        "parentCategoryID": 0
>    }
>]
>```

