---
description: A PUT method to update a user group.
seo-description: A PUT method to update a user group.
seo-title: Update a Group
solution: Audience Manager
title: Update a Group
uuid: 0e3e5e29-670e-45a8-a048-25322823c351
index: y
internal: n
snippet: y
translate: y
---

# Update a Group


>**Request** 

>` PUT /api/v1/groups/<groupId>` 

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
