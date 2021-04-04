---
description: Rest API methods to manage groups, including creating, updating, listing, deleting groups.
seo-description: Rest API methods to manage groups, including creating, updating, listing, deleting groups.
seo-title: Group Management API Methods
solution: Audience Manager
title: Group Management API Methods
uuid: fe042eb5-ea12-42fe-be98-d721f987a914
feature: API
exl-id: b43c8404-1853-4306-8f26-96d9191a2548
---
# Group Management API Methods {#group-management-api-methods}

Rest [!DNL API] methods to manage groups, including creating, updating, listing, deleting groups.

<!-- c_rest_api_user_man_group.xml -->

## Create a Group {#create-group}

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

## Update a Group {#update-group}

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

## List Groups {#list-groups}

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

## Delete a Group {#delete-groups}

A `DELETE` method to delete a user group and remove all members from that group.

<!-- r_rest_api_group_delete.xml -->

### Request

`DELETE /api/v1/groups/`*`<groupId>`*

Returns `204 No Content` if successful. In case of conflict returns `409 Conflict`.

## Delete Groups in Bulk {#delete-groups-bulk}

A `DELETE` method to delete multiple groups in bulk and remove all members from that group.

<!-- r_rest_api_group_delete_bulk.xml -->

### Request

`DELETE /api/v1/groups/bulk-delete`

Returns `204 No Content` if successful. In case of conflict returns `409 Conflict`.

## List All Permissions for a Group {#list-permissions-group}

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

## Set Permissions for a Group {#set-permissions-group}

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
