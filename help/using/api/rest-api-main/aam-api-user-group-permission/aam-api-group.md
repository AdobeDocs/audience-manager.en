---
description: Rest API methods to manage groups, including creating, updating, listing, deleting groups.
seo-description: Rest API methods to manage groups, including creating, updating, listing, deleting groups.
seo-title: Group Management API Methods
solution: Audience Manager
title: Group Management API Methods
uuid: fe042eb5-ea12-42fe-be98-d721f987a914
---

# Group Management API Methods {#group-management-api-methods}

Rest [!DNL API] methods to manage groups, including creating, updating, listing, deleting groups.

<!-- c_rest_api_user_man_group.xml -->

## Create a Group {#reference_1CEABC94762F451CBE7ADE64F11A0D87}

A `POST` method to create a new user group.

<!-- r_rest_api_group_create.xml -->

### Request

`POST /api/v1/groups/`

### Sample Request Body

```
 {
    "name" : <string>,
    "description" : <string_may_be_null>,
 }
```

### Response

```
  {
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }
```

## Update a Group {#reference_0C9F9C5F67DA416AA7F01DF24DC9B878}

A `PUT` method to update a user group.

<!--
r_rest_api_group_update.xml
-->

### Request

`PUT /api/v1/groups/`*`<groupId>`*

### Sample Request Body

```
 {
    "name" : <string>,
    "description" : <string_may_be_null>,
 }
```

### Response

```
  {
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }
```

## List Groups {#reference_E96FB3181F9842478EF30C9CF330A46B}

A `GET` method to list user groups.

<!--
r_rest_api_group_list.xml
-->

### Request

`GET /api/v1/groups/`

### Response

```
[
  { 
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }, ...
]
```

## Delete a Group {#reference_4482423037DB4E71BF5BFDA8C4458038}

A `DELETE` method to delete a user group and remove all members from that group.

<!-- r_rest_api_group_delete.xml -->

### Request

`DELETE /api/v1/groups/`*`<groupId>`*

Returns `204 No Content` if successful. In case of conflict returns `409 Conflict`.

## Delete Groups in Bulk {#reference_B27B1CD22BA0475A870E251AAB8D7764}

A `DELETE` method to delete multiple groups in bulk and remove all members from that group.

<!-- r_rest_api_group_delete_bulk.xml -->

### Request

`DELETE /api/v1/groups/bulk-delete`

Returns `204 No Content` if successful. In case of conflict returns `409 Conflict`.

## List All Permissions for a Group {#reference_9696B6B2AB3F457895FE4B50EBC5BE28}

A `GET` method to list the permission objects on a group.

<!-- r_rest_api_perm_list_group.xml -->

### Request

`GET /api/v1/groups/{groupId}/permissions`

### Response

```
[{
 "objectId" : 34,
 "objectType": "SEGMENT",
 "permissions": ["READ", "WRITE", "DELETE", "MAP_TO_MODELS"]
 },

{
 "objectId" : "234",
 "objectType": "TRAIT",
 "permissions": ["READ", "WRITE", "DELETE", "MAP_TO_MODELS"]
 },
 {
 "objectId" : 277,
 "objectType": "SEGMENT",
 "permissions": ["READ", "WRITE", "MAP_TO_MODELS"]
 }
]
```

Returns `400 Bad Request` if the group is inaccessible. 

## Set Permissions for a Group {#reference_404422A21AEF4E59B05D639E10CDADF6}

A `PUT` method to update group permissions. This method overwrites the old permissions with the new permissions.

<!-- r_rest_api_perm_set.xml -->

### Request

`PUT /api/v1/groups/{groupId}/permissions/`

### Response

```
[ 
  { "objectType" : "SEGMENT",
    "objectId" : 563,
    "permissions" : [ "READ", "WRITE"]
  },
  { "objectType" : "SEGMENT",
    "objectId" : 2363,
    "permissions" : [ "CREATE", "WRITE"]
  },
  { "objectType" : "TRAIT",
    "objectId" : 83498,
    "permissions" : [ "READ", "MAP_TO_SEGMENTS"]
  },
  { "objectType" : "DESTINATION",
    "objectId" : 304,
    "permissions" : [ "READ", "WRITE", "CREATE"]
  }
]
```

The sample response represents the updated list of permission objects.

Returns `200 OK` if successful. Returns `400` if any given permission is invalid. Can also return `403` if the object is not accessible by the logged-in user.