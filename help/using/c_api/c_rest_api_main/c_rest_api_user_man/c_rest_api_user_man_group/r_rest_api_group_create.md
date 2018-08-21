---
description: A POST method to create a new user group.
seo-description: A POST method to create a new user group.
seo-title: Create a Group
solution: Audience Manager
title: Create a Group
uuid: 68238450-96ee-4d31-9777-45f2a4c8378f
index: y
internal: n
snippet: y
translate: y
---

# Create a Group


>**Request** 

>` POST /api/v1/groups/` 

>**Sample Request Body** 
>
>```
> {
>    "name" : <string>,
>    "description" : <string_may_be_null>,
> }
>```
>**Sample Response** 
>
>```
>  {
>    "groupId" : <integer>,
>    "pid" : <integer>,
>    "name" : <string>,
>    "description" : <string_may_be_null>,
>    "membershipCount" : <integer>,
>    "wildcards" : <list of strings>,
>    "users" : <list of user IDs>
>  }
>```
