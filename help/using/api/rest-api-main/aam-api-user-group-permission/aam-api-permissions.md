---
description: Rest API methods to manage permissions for objects and groups.
seo-description: Rest API methods to manage permissions for objects and groups.
seo-title: Permissions Management API Methods
solution: Audience Manager
title: Permissions Management API Methods
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
---

# Permissions Management API Methods {#permissions-management-api-methods}

Rest [!DNL API] methods to manage permissions for objects and groups.

<!-- c_rest_api_perm_man.xml -->

## List Available Object Types {#list-object-types}

A `GET` method to list available object types on which role-based access controls can be set.

<!-- r_rest_api_perm_list.xml -->

### Request

`GET /api/v1/permissionable-object-types/`

### Response

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## List Available Permissions for an Object Type {#list-permissions-object-type}

A `GET` method to list available permissions for an object type.

<!-- r_rest_api_perm_list_perms.xml -->

### Request

`GET /api/v1/permissionable-object-types/SEGMENT/`

### Response

```
{ 
 "wildcard" : [ "VIEW_ALL_SEGMENTS", "EDIT_ALL_SEGMENTS", "CREATE_ALL_SEGMENTS", "DELETE_ALL_SEGMENTS", "MAP_ALL_SEGMENTS_TO_MODELS", "MAP_ALL_TO_DESTINATIONS" ], 
 "perObject" : [ "READ", "WRITE", "CREATE", "DELETE", "MAP_TO_MODELS", "MAP_TO_DESTINATION" ]
}
```

>[!NOTE]
>
>The object types TAGS and DERIVED SIGNALS have no regular permissions to use. Controls on these object types are changed by the All or Nothing Wild Card Permissions only.