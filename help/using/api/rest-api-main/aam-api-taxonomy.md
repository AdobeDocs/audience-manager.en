---
description: Methods that let you view the Audience Manager common taxonomy. This optional classification scheme organizes traits into industry standard categories.
seo-description: Methods that let you view the Audience Manager common taxonomy. This optional classification scheme organizes traits into industry standard categories.
seo-title: Taxonomic API Methods
solution: Audience Manager
title: Taxonomic API Methods
uuid: 4ee29ba5-e9ba-4498-a6ee-7343227dd7ba
feature: API
exl-id: 8bc6dcbb-7f5b-4a7b-998d-025eaf76c409
TQID: https://experienceleague.adobe.com/LIHEWvF3t-VNHJEviomvCF-dxE2Jy-BFxBynonvwP3w
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
    internal-label: APIs and SDKs
topic_v2:
  - id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
    internal-label: Taxonomy
---
# Taxonomic API Methods {#taxonomic-api-methods}

Methods that let you view the Audience Manager common taxonomy. This optional classification scheme organizes traits into industry standard categories.

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>You cannot create new taxonomic categories or classify traits with these methods. To classify a trait, specify the appropriate `categoryId` with a trait create or update method.

## Return a Specific Taxonomy {#return-specific-taxonomy}

A `GET` method that returns details about the specified taxonomic category.

<!-- r_rest_api_taxonomy.xml -->

### Request

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### Response

A successful response returns `200 OK` and the category for the specified ID. An unsuccessful request returns `404 No Content` if the ID does not exist.

```
{
    "crUID": 158,
    "name": "Arts & Entertainment",
    "upUID": 158,
    "description": "Arts & Entertainment",
    "categoryID": 1,
    "parentCategoryID": 0
}
```

## Return all Taxonomic Categories {#return-all-taxonomy-categories}

A `GET` method that returns a list of the top-level categories in an array.

<!-- r_rest_api_taxonomies.xml -->

### Request

`GET https://api.demdex.com/v1/taxonomies/0/`

### Response

Truncated for brevity.

```
[
    {
        "crUID": 158,
        "name": "Arts & Entertainment",
        "upUID": 158,
        "description": "Arts & Entertainment",
        "categoryID": 1,
        "parentCategoryID": 0
    },
    {
        "crUID": 158,
        "name": "Automotive",
        "upUID": 158,
        "description": "Automotive",
        "categoryID": 2,
        "parentCategoryID": 0
    },
    {
        "crUID": 158,
        "name": "Business",
        "upUID": 158,
        "description": "Business",
        "categoryID": 3,
        "parentCategoryID": 0
    }
]
```

## Return Taxonomic Sub-Categories {#return-taxonomy-sub-categories}

A `GET` method that returns sub-categories for the specified parent category in an array.

<!-- r_rest_api_taxonomy_sub.xml -->

### Request

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### Response

A successful response returns `200 OK` and the category for the specified ID. An unsuccessful request returns `404 No Content` if the ID does not exist. Truncated for brevity.

```
[
    {
        "crUID": 158,
        "name": "Books & Literature",
        "upUID": 158,
        "description": "Books & Literature",
        "categoryID": 25,
        "parentCategoryID": 1
    },
    {
        "crUID": 158,
        "name": "Celebrity Fan/Gossip",
        "upUID": 158,
        "description": "Celebrity Fan/Gossip",
        "categoryID": 49,
        "parentCategoryID": 1
    },
    {
        "crUID": 158,
        "name": "Fine Art",
        "upUID": 158,
        "description": "Fine Art",
        "categoryID": 72,
        "parentCategoryID": 1
    }
]
```
