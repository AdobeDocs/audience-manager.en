---
description: Methods that let you programmatically list Audience Manager DCS regions.
seo-description: Methods that let you programmatically list Audience Manager DCS regions.
seo-title: DCS Region API Methods
solution: Audience Manager
title: DCS Region API Methods
uuid: fc0dbcbe-e32e-43a9-a10d-a3e5ef4479cb
index: y
internal: n
snippet: y
translate: y
---

# DCS Region API Methods

Methods that let you programmatically list Audience Manager DCS regions.

## <wintitle> DCS </wintitle> Region API Methods {#concept_C1EF1A07C73D489FAD2AECA39B113DC6}

Methods that let you programmatically list Audience Manager 
<wintitle>
  DCS
</wintitle> regions. 
<draft-comment otherprops="merge">
  c_rest_api_regions.xml 
</draft-comment>



For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../c_api/dcs-intro/dcs-api-reference/dcs-regions.md#concept_01C1E017A6694D1EAF9BF65BFFA54091). 

## List a Specific <wintitle> DCS </wintitle> Region {#reference_8FCE1F7F285E4EEC94EB37954E146F7B}

A 
<codeph>
  GET
</codeph> method to list a specific 
<wintitle>
  DCS
</wintitle> region. 
<draft-comment otherprops="merge">
  r_rest_api_regions_list_specific.xml 
</draft-comment>


>
>
>**Request** 
>
>
>`GET /v1/dcs-regions/<id>` 
>
>
>**Sample Response** 
>
>```>
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
>
>
>Returns `200 OK` if successful. 
>
>
>For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../c_api/dcs-intro/dcs-api-reference/dcs-regions.md#concept_01C1E017A6694D1EAF9BF65BFFA54091). 

## List <wintitle> DCS </wintitle> Regions {#reference_D9532CB364824BCFABE58F39EA6928F6}

A 
<codeph>
  GET
</codeph> method to list 
<wintitle>
  DCS
</wintitle> regions. 
<draft-comment otherprops="merge">
  r_rest_api_regions_list.xml 
</draft-comment>


>
>
>**Request** 
>
>
>`GET /v1/dcs-regions/` 
>
>
>**Sample Response** 
>
>```>
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
>
>
>Returns `200 OK` if successful. 
>
>
>For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../c_api/dcs-intro/dcs-api-reference/dcs-regions.md#concept_01C1E017A6694D1EAF9BF65BFFA54091). 
