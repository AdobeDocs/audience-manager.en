---
description: A GET method to list user groups.
seo-description: A GET method to list user groups.
seo-title: List Groups
solution: Audience Manager
title: List Groups
uuid: a9ebe463-f3e1-4579-8ea7-979467139201
index: y
internal: n
snippet: y
translate: y
---

# List Groups


>**Request** 

>` GET /api/v1/groups/` 

>**Sample Response** 
>
>```
>[
>  { 
>    "groupId" : <integer>,
>    "pid" : <integer>,
>    "name" : <string>,
>    "description" : <string_may_be_null>,
>    "membershipCount" : <integer>,
>    "wildcards" : <list of strings>,
>    "users" : <list of user IDs>
>  }, ...
>]
>```
