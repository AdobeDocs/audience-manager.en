---
description: A GET method that returns details about the specified taxonomic category.
seo-description: A GET method that returns details about the specified taxonomic category.
seo-title: Return a Specific Taxonomy
solution: Audience Manager
title: Return a Specific Taxonomy
uuid: 9bf481ac-4714-41d6-978e-ac0c52033a12
index: y
internal: n
snippet: y
translate: y
---

# Return a Specific Taxonomy


>**Request** 

>` GET https://api.demdex.com/v1/taxonomies/0/ *` <categoryId>`*` 

>**Sample Response** 

>A successful response returns ` 200 OK` and the category for the specified ID. An unsuccessful request returns ` 404 No Content` if the ID does not exist. 
>
>```
>{ 
>    "crUID": 158, 
>    "name": "Arts & Entertainment", 
>    "upUID": 158, 
>    "description": "Arts & Entertainment", 
>    "categoryID": 1, 
>    "parentCategoryID": 0 
>}
>```
