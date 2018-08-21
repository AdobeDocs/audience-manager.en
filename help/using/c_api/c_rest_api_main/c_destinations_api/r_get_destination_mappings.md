---
description: A GET method that returns the mappings for a destination.
seo-description: A GET method that returns the mappings for a destination.
seo-title: Return Destination Mappings
solution: Audience Manager
title: Return Destination Mappings
uuid: 6269c466-183e-4925-8d88-921dfe6c9b70
index: y
internal: n
snippet: y
translate: y
---

# Return Destination Mappings



>>[!NOTE]
>>
>>The returned mapping is specific to the destination type and configuration.
>


>**Request** 

>` GET https://api.demdex.com/v1/destinations/ *` <destinationId>`*/mappings` 
>>[!NOTE]
>>
>>Supports paging parameters.
>


>**Sample Response** >
>```
>{ 
>   "total":354, 
>   "page":0, 
>   "pageSize":2, 
>   "list":[ 
>      { 
>         "destinationMappingId":14395, 
>         "traitType":"SEGMENT", 
>         "traitValue":0, 
>         "destinationId":314, 
>         "elementName":"sample pixel", 
>         "elementDescription":"Migration Pixel", 
>         "elementStatus":"active", 
>         "createTime":1281997484000, 
>         "updateTime":1300752888000, 
>         "crUID":224, 
>         "upUID":308, 
>         "sid":80920, 
>         "startDate":"2010-11-15", 
>         "endDate":null, 
>         "priority":null, 
>         "url":"http://www.adobe.com/send?%ALIAS%", 
>         "secureUrl":"https://www.adobe.com/send?%ALIAS%", 
>         "tagCode":null, 
>         "secureTagCode":null, 
>         "traitAlias":null 
>      } 
>      { 
>         "destinationMappingId":15934, 
>         "traitType":"SEGMENT", 
>         "traitValue":0, 
>         "destinationId":314, 
>         "elementName":"sample pixel", 
>         "elementDescription":"Migration Pixel", 
>         "elementStatus":"active", 
>         "createTime":1281997484000, 
>         "updateTime":1300752888000, 
>         "crUID":242, 
>         "upUID":803, 
>         "sid":90820, 
>         "startDate":"2010-11-15", 
>         "endDate":null, 
>         "priority":null, 
>         "url":"http://www.adobe.com/send?%ALIAS%", 
>         "secureUrl":"https://www.adobe.com/send?%ALIAS%", 
>         "tagCode":null, 
>         "secureTagCode":null, 
>         "traitAlias":null 
>      } 
>   ] 
>{
>```

