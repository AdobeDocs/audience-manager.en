---
description: Optional methods that let you to assign traits to a user-defined type or category, usually according to function or for your own internal reporting processes.
seo-description: Optional methods that let you to assign traits to a user-defined type or category, usually according to function or for your own internal reporting processes.
seo-title: Trait Type Methods
solution: Audience Manager
title: Trait Type Methods
uuid: 082931d5-457b-4622-817b-86303f38c26a
---

# Trait Type Methods {#trait-type-methods}

Optional methods that let you to assign traits to a user-defined type or category, usually according to function or for your own internal reporting processes.

<!-- 
c_rest_api_trait_types_intro.xml
-->

>[!NOTE]
>
>Trait type methods do not assign traits to categories used by the [common taxonomy](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods). Think of these as labels that are separate from the common taxonomy.

For visual reference, [!UICONTROL Trait Types] is a dropdown control located in the UI under **[!UICONTROL Traits > Create new trait > Basic Information]**.

## Create a New Trait Type {#reference_ADC6A3D2B2E146E88906003FC05FDEF6}

A `POST` method that lets you create a new trait type.

<!-- 
r_rest_api_create_trait_type.xml
-->

### Request

`POST https://api.demdex.com/v1/customer-trait-types`

### Sample Request

```
{
"name":"Custom trait type"
}
```

### Response

```
{
    "pixelType": 34,
    "pid": 1099,
    "name": "Custom type",
    "description": null,
    "crUID": 694,
    "upUID": 694,
    "createTime": 1358297352000,
    "updateTime": 1358297352000
}
```

## Return Properties for a Trait Type {#reference_6434DDEA7B4647CAAFFAECF3667C8331}

A `GET` method that returns details about the specified trait type.

<!-- 
r_rest_api_get_trait_type.xml
-->

### Request

`GET https://api.demdex.com/v1/customer-trait-types/`*`<customerTraitTypeId>`*

### Response

```
{
    "pixelType": 4,
    "pid": 0,
    "name": "Delivery Event",
    "description": "Delivery Event",
    "crUID": 158,
    "upUID": 158,
    "createTime": 1299115496000,
    "updateTime": 1299115496000
}
```

## Return Properties for all Trait Types {#reference_109CEE62B3044C189B032C51CE6EC7B2}

A `GET` method that returns details about all your trait types in an array.

<!--
r_rest_api_get_trait_types.xml
-->

### Request

`GET https://api.demdex.com/v1/customer-trait-types/`

### Response 

```
[
    {
        "pixelType": 200,
        "pid": 1099,
        "name": "Customer Specific Trait Type",
        "description": "Test",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1349990458000,
        "updateTime": 1349990458000
    },
    {
        "pixelType": 1,
        "pid": 0,
        "name": "User Trait",
        "description": "User Trait",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1299115492000,
        "updateTime": 1299115492000
    },
    {
        "pixelType": 2,
        "pid": 0,
        "name": "Site Visitor",
        "description": "Site Visitor",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1299115493000,
        "updateTime": 1299115493000
    }
]
```