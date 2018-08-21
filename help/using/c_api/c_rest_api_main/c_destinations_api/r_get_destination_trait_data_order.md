---
description: A GET method that returns an individual destination mapping based on the mappingId.
seo-description: A GET method that returns an individual destination mapping based on the mappingId.
seo-title: Return a Destination Mapping With the Mapping ID
solution: Audience Manager
title: Return a Destination Mapping With the Mapping ID
uuid: 9067224d-ccae-4bf1-89b7-a81037de10e8
index: y
internal: n
snippet: y
translate: y
---

# Return a Destination Mapping With the Mapping ID


>**Request** 

>` GET https://api.demdex.com/v1/destinations/ *` <destinationId>`*/mappings/ *` <destinationMappingId>`*` 

>**Sample Response** >
>```
>{ 
>"mappingId": 14593, 
>"traitType": "SEGMENT", 
>"traitValue": 0, 
>"destinationId": 314, 
>"elementName": "sample", 
>"elementDescription": "Migration Pixel", 
>"elementStatus": "active", 
>"createTime": 1281997484000, 
>"updateTime": 1300752888000, 
>"crUID": 224, 
>"upUID": 308, 
>"sid": 80920, 
>"startDate": "2010-11-15", 
>"endDate": null, 
>"priority": null, 
>"url": "http://www.adobe.com/send?%ALIAS%", 
>"secureUrl": "https://www.adobe.com/send?%ALIAS%", 
>"tagCode": null, 
>"secureTagCode": null, 
>"traitAlias": null 
>}
>```

