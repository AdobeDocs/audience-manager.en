---
description: A GET method to list a specific DCS region.
seo-description: A GET method to list a specific DCS region.
seo-title: List a Specific DCS Region
solution: Audience Manager
title: List a Specific DCS Region
uuid: ef6fe0c2-ce1b-4756-859f-edcf75f82e3a
index: y
internal: n
snippet: y
translate: y
---

# List a Specific DCS Region


>**Request** 

>` GET /v1/dcs-regions/<id>` 

>**Sample Response** 
>
>```
>{  
>    "regionId" : <id>,  
>    "location" : "<location>", 
>    "host" : "<host>", 
>    "code" : "<code>", 
>    "status" : "ACTIVE" | "INACTIVE", 
>    "createTime" : long of milliseconds since epoch, 
>    "updateTime" : long of milliseconds since epoch, 
>    "crUID" : <userId who created>, 
>    "upUID" : <userId who updated> 
>  }
>```
>Returns ` 200 OK` if successful. 

>For a list of regions and their corresponding integers, see [ DCS Region IDs, Locations, and Host Names ](../../../c_api/dcs-intro/dcs-api-reference/dcs-regions.md#concept_01C1E017A6694D1EAF9BF65BFFA54091). 
