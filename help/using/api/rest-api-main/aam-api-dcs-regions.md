---
description: Methods that let you programmatically list Audience Manager DCS regions.
seo-description: Methods that let you programmatically list Audience Manager DCS regions.
seo-title: DCS Region API Methods
solution: Audience Manager
title: DCS Region API Methods
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
feature: API
---

# DCS Region API Methods {#dcs-region-api-methods}

Methods that let you programmatically list Audience Manager [!DNL DCS] regions.

<!-- c_rest_api_regions.xml -->

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## List a Specific DCS Region {#list-specific-dcs-region}

A `GET` method to list a specific [!DNL DCS] region.

<!-- r_rest_api_regions_list_specific.xml -->

### Request

`GET /v1/dcs-regions/`*`<id>`*

### Sample Response

```
{ 
    "regionId" : <id>, 
    "location" : "<location>",
    "host" : "<host>",
    "code" : "<code>",
    "status" : "ACTIVE" | "INACTIVE",
    "createTime" : long of milliseconds since epoch,
    "updateTime" : long of milliseconds since epoch,
    "crUID" : <userId who created>,
    "upUID" : <userId who updated>
  }
```

Returns `200 OK` if successful.

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md). 

## List DCS Regions {#list-dcs-regions}

A `GET` method to list [!DNL DCS] regions.

<!-- r_rest_api_regions_list.xml -->

### Request

`GET /v1/dcs-regions/`

### Sample Response

```
[
  { 
    "regionId" : <id>, 
    "location" : "<location>",
    "host" : "<host>",
    "code" : "<code> # APSE, USE, etc,
    "status" : "ACTIVE" | "INACTIVE",
    "createTime" : long of milliseconds since epoch,
    "updateTime" : long of milliseconds since epoch,
    "crUID" : <userId who created>,
    "upUID" : <userId who updated>
  },
  ...
]
```

Returns `200 OK` if successful.

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
