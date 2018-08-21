---
description: A GET method to list available permissions for an object type.
seo-description: A GET method to list available permissions for an object type.
seo-title: List Available Permissions for an Object Type
solution: Audience Manager
title: List Available Permissions for an Object Type
uuid: 2624167c-c5af-4b8d-916c-f508c690ae6d
index: y
internal: n
snippet: y
translate: y
---

# List Available Permissions for an Object Type


>**Request** 

>` GET /api/v1/permissionable-object-types/SEGMENT/` 

>**Sample Response** 
>
>```
>{
> "wildcard" : [ "VIEW_ALL_SEGMENTS", "EDIT_ALL_SEGMENTS", "CREATE_ALL_SEGMENTS", "DELETE_ALL_SEGMENTS", "MAP_ALL_SEGMENTS_TO_MODELS", "MAP_ALL_TO_DESTINATIONS" ],
> "perObject" : [ "READ", "WRITE", "CREATE", "DELETE", "MAP_TO_MODELS", "MAP_TO_DESTINATION" ]
>}
>```

>>[!NOTE]
>>
>>The object types TAGS and DERIVED SIGNALS have no regular permissions to use. Controls on these object types are changed by the All or Nothing Wild Card Permissions only.
>

