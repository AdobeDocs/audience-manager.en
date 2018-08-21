---
description: A GET method to list DCS regions.
seo-description: A GET method to list DCS regions.
seo-title: List DCS Regions
solution: Audience Manager
title: List DCS Regions
uuid: b1e6ba7e-8b7c-4a9c-a8a8-61c558d853b7
index: y
internal: n
snippet: y
translate: y
---

# List DCS Regions


>**Request** 

>` GET /v1/dcs-regions/` 

>**Sample Response** 
>
>```
>[
>  { 
>    "regionId" : <id>, 
>    "location" : "<location>",
>    "host" : "<host>",
>    "code" : "<code> # APSE, USE, etc,
>    "status" : "ACTIVE" | "INACTIVE",
>    "createTime" : long of milliseconds since epoch,
>    "updateTime" : long of milliseconds since epoch,
>    "crUID" : <userId who created>,
>    "upUID" : <userId who updated>
>  },
>  ...
>]
>```
>Returns ` 200 OK` if successful. 

>For a list of regions and their corresponding integers, see [ DCS Region IDs, Locations, and Host Names](../../../c_api/dcs-intro/dcs-api-reference/dcs-regions.md#concept_01C1E017A6694D1EAF9BF65BFFA54091). 
