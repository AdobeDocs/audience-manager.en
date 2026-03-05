---
description: Rest API methods to manage permissions for objects and groups.
seo-description: Rest API methods to manage permissions for objects and groups.
seo-title: Permissions Management API Methods
solution: Audience Manager
title: Permissions Management API Methods
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
exl-id: 7aac8ea8-4120-4c6b-88a6-30e8aa727dc8
TQID: https://experienceleague.adobe.com/E9JWh1JKhHOSd7MzeOR8csVXChyh4Q0RiCj3Y5yb2vM
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
    internal-label: APIs and SDKs
  - id: c814092e-2730-45e8-a12d-e084529f52cb
    internal-label: Destinations
subfeature_v2:
  - id: d8f681b8-67cc-42dc-85c5-a0977528a942
    internal-label: Data Collection Server
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
