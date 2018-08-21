---
description: A PUT method to update group permissions. This method overwrites the old permissions with the new permissions.
seo-description: A PUT method to update group permissions. This method overwrites the old permissions with the new permissions.
seo-title: Set Permissions for a Group
solution: Audience Manager
title: Set Permissions for a Group
uuid: aaf31a9f-07e0-471f-a269-7d8e41ca3c5b
index: y
internal: n
snippet: y
translate: y
---

# Set Permissions for a Group


>**Request** 

>` PUT /api/v1/groups/{groupId}/permissions/` 

>**Sample Response** 
>
>```
>[ 
>  { "objectType" : "SEGMENT",
>    "objectId" : 563,
>    "permissions" : [ "READ", "WRITE"]
>  },
>  { "objectType" : "SEGMENT",
>    "objectId" : 2363,
>    "permissions" : [ "CREATE", "WRITE"]
>  },
>  { "objectType" : "TRAIT",
>    "objectId" : 83498,
>    "permissions" : [ "READ", "MAP_TO_SEGMENTS"]
>  },
>  { "objectType" : "DESTINATION",
>    "objectId" : 304,
>    "permissions" : [ "READ", "WRITE", "CREATE"]
>  }
>]
>```
>The sample response represents the updated list of permission objects. 

>Returns ` 200 OK` if successful. Returns ` 400` if any given permission is invalid. Can also return ` 403` if the object is not accessible by the logged-in user. 
