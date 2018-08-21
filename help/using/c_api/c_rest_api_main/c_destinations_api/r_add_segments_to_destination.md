---
description: A POST method that lets you map multiple segments to a destination.
seo-description: A POST method that lets you map multiple segments to a destination.
seo-title: Add Multiple Segments to a Destination
solution: Audience Manager
title: Add Multiple Segments to a Destination
uuid: aa172083-4ae6-4e63-91b9-37108f979e9b
index: y
internal: n
snippet: y
translate: y
---

# Add Multiple Segments to a Destination


>**Request** 

>` POST https://api.demdex.com/v1/destinations/ *` <destinationId>`*/bulk-create` 

>**Sample Request** 

>Create multiple destination mappings in an array. All request values are required unless otherwise indicated. >
>```
>[ 
>{ 
>   "sid": 105123, 
>   "traitType":"SEGMENT", 
>   "url":"http://adobe.com", 
>   "startDate":"2012-11-20" 
>}, 
>{ 
>   "sid": 121070, 
>   "traitType":"SEGMENT", 
>   "url":"http://my.adobeconnect.com", 
>   "startDate":"2012-11-21" 
>} 
>]
>```


>**Sample Response** 

>Returns an array of created mappings. >
>```
>[ 
>    { 
>        "destinationMappingId": 103454, 
>        "traitType": "SEGMENT", 
>        "traitValue": 0, 
>        "destinationId": 780, 
>        "elementName": "Case of the Mondays", 
>        "elementDescription": "test", 
>        "elementStatus": "active", 
>        "createTime": 1353373234000, 
>        "updateTime": 1353373234000, 
>        "crUID": 1065, 
>        "upUID": 1065, 
>        "sid": 105123, 
>        "startDate": "2012-11-19", 
>        "endDate": null, 
>        "priority": null, 
>        "url": "http://adobe.com", 
>        "secureUrl": null, 
>        "tagCode": null, 
>        "secureTagCode": null, 
>        "traitAlias": null 
>    }, 
>    { 
>        "traitToDataOrderId": 103455, 
>        "traitType": "SEGMENT", 
>        "traitValue": 0, 
>        "destinationId": 780, 
>        "elementName": "Test Trait", 
>        "elementDescription": "This trait", 
>        "elementStatus": 1, 
>        "createTime": 1353373234000, 
>        "updateTime": 1353373234000, 
>        "crUID": 1065, 
>        "upUID": 1065, 
>        "sid": 121070, 
>        "startDate": "2012-11-20", 
>        "endDate": null, 
>        "priority": null, 
>        "url": "http://my.adobeconnect.com", 
>        "secureUrl": null, 
>        "tagCode": null, 
>        "secureTagCode": null, 
>        "traitAlias": null 
>    } 
>]
>```

