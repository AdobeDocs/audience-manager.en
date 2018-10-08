---
description: Rest API methods to manage permissions for objects and groups.
seo-description: Rest API methods to manage permissions for objects and groups.
seo-title: Permissions Management API Methods
solution: Audience Manager
title: Permissions Management API Methods
uuid: ee5dcbd7-8142-4e86-bea5-5e3a1e950de3
index: y
internal: n
snippet: y
translate: y
---

# Permissions Management API Methods

Rest API methods to manage permissions for objects and groups.

## Permissions Management API Methods {#concept_592038BE9A2A4B7C9310AFAC9BAC0CB1}

Rest API methods to manage permissions for objects and groups.

<!-- c_rest_api_perm_man.xml -->

## List Available Object Types {#reference_065FE71054DA4ABD985A6A0FAEEDF212}

A `GET` method to list available object types on which role-based access controls can be set.

<!-- r_rest_api_perm_list.xml -->

**Request**

`GET /api/v1/permissionable-object-types/`

**Sample Response**

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## List Available Permissions for an Object Type {#reference_7C8368419A414757BE014999E8B476DB}

A `GET` method to list available permissions for an object type.

<!-- r_rest_api_perm_list_perms.xml -->

**Request**

`GET /api/v1/permissionable-object-types/SEGMENT/`

**Sample Response**

```
{ 
 "wildcard" : [ "VIEW_ALL_SEGMENTS", "EDIT_ALL_SEGMENTS", "CREATE_ALL_SEGMENTS", "DELETE_ALL_SEGMENTS", "MAP_ALL_SEGMENTS_TO_MODELS", "MAP_ALL_TO_DESTINATIONS" ], 
 "perObject" : [ "READ", "WRITE", "CREATE", "DELETE", "MAP_TO_MODELS", "MAP_TO_DESTINATION" ] 
}
```

>[!NOTE]
>
>The object types TAGS and DERIVED SIGNALS have no regular permissions to use. Controls on these object types are changed by the All or Nothing Wild Card Permissions only.

