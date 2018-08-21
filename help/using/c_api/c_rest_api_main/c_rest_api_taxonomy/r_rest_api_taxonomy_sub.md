---
description: A GET method that returns sub-categories for the specified parent category in an array.
seo-description: A GET method that returns sub-categories for the specified parent category in an array.
seo-title: Return Taxonomic Sub-Categories
solution: Audience Manager
title: Return Taxonomic Sub-Categories
uuid: b7179a66-2303-4119-ad0a-6a32d7493827
index: y
internal: n
snippet: y
translate: y
---

# Return Taxonomic Sub-Categories


>**Request** 

>` GET https://api.demdex.com/v1/taxonomies/0/ *` <categoryId>`*/childCategories/` 

>**Sample Response** 

>A successful response returns ` 200 OK` and the category for the specified ID. An unsuccessful request returns ` 404 No Content` if the ID does not exist. Truncated for brevity. >
>```
>[ 
>    { 
>        "crUID": 158, 
>        "name": "Books & Literature", 
>        "upUID": 158, 
>        "description": "Books & Literature", 
>        "categoryID": 25, 
>        "parentCategoryID": 1 
>    }, 
>    { 
>        "crUID": 158, 
>        "name": "Celebrity Fan/Gossip", 
>        "upUID": 158, 
>        "description": "Celebrity Fan/Gossip", 
>        "categoryID": 49, 
>        "parentCategoryID": 1 
>    }, 
>    { 
>        "crUID": 158, 
>        "name": "Fine Art", 
>        "upUID": 158, 
>        "description": "Fine Art", 
>        "categoryID": 72, 
>        "parentCategoryID": 1 
>    } 
>]
>```

