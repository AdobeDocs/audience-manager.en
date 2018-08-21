---
description: A GET method to list the permission objects on a group.
seo-description: A GET method to list the permission objects on a group.
seo-title: List All Permissions for a Group
solution: Audience Manager
title: List All Permissions for a Group
uuid: 17091921-2279-4e32-adfd-fb15a7cdcfde
index: y
internal: n
snippet: y
translate: y
---

# List All Permissions for a Group


>**Request** 

>` GET /api/v1/groups/{groupId}/permissions` 

>**Sample Response** 
>
>```
>[{
> "objectId" : 34,
> "objectType": "SEGMENT",
> "permissions": ["READ", "WRITE", "DELETE", "MAP_TO_MODELS"]
> },
>
>{
> "objectId" : "234",
> "objectType": "TRAIT",
> "permissions": ["READ", "WRITE", "DELETE", "MAP_TO_MODELS"]
> },
> {
> "objectId" : 277,
> "objectType": "SEGMENT",
> "permissions": ["READ", "WRITE", "MAP_TO_MODELS"]
> }
>]
>```
>Returns ` 400 Bad Request` if the group is inaccessible. 
