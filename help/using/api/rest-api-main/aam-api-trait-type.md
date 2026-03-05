---
description: Optional methods that let you to assign traits to a user-defined type or category, usually according to function or for your own internal reporting processes.
seo-description: Optional methods that let you to assign traits to a user-defined type or category, usually according to function or for your own internal reporting processes.
seo-title: Trait Type Methods
solution: Audience Manager
title: Trait Type Methods
uuid: 082931d5-457b-4622-817b-86303f38c26a
feature: API
exl-id: d450f9ce-2abb-4a8b-b8db-2962b84fb341
TQID: https://experienceleague.adobe.com/IoPUeMYwHk-D5F31Gx76Vmd97yRQqRIHlDWu3-5KZLg
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: a99472c1-6aae-4c7a-8aa0-f60636369620
    internal-label: Reporting
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
    internal-label: APIs and SDKs
subfeature_v2:
  - id: a49258d4-867f-4130-b875-d72c001bdf6c
    internal-label: Overlap Reports
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
    internal-label: Taxonomy
---
# Trait Type Methods {#trait-type-methods}

Optional methods that let you to assign traits to a user-defined type or category, usually according to function or for your own internal reporting processes.

<!-- c_rest_api_trait_types_intro.xml -->

>[!NOTE]
>
>Trait type methods do not assign traits to categories used by the [common taxonomy](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods). Think of these as labels that are separate from the common taxonomy.

For visual reference, [!UICONTROL Trait Types] is a dropdown control located in the [!DNL UI] under **[!UICONTROL Traits > Create new trait > Basic Information]**.

## Create a New Trait Type {#create-trait-type}

A `POST` method that lets you create a new trait type.

<!-- r_rest_api_create_trait_type.xml -->

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

## Return Properties for a Trait Type {#return-props}

A `GET` method that returns details about the specified trait type.

<!-- r_rest_api_get_trait_type.xml -->

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

## Return Properties for all Trait Types {#return-props-all}

A `GET` method that returns details about all your trait types in an array.

<!-- r_rest_api_get_trait_types.xml -->

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
