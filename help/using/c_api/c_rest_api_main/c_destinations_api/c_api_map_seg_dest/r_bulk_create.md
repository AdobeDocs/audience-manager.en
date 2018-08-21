---
description: A POST method that lets you pass in an array of cookie or URL destination mappings.
seo-description: A POST method that lets you pass in an array of cookie or URL destination mappings.
seo-title: Bulk Create Destination Mappings
solution: Audience Manager
title: Bulk Create Destination Mappings
uuid: 3296d9d8-b954-4ea5-8880-72f1e58ed3c2
index: y
internal: n
snippet: y
translate: y
---

# Bulk Create Destination Mappings


>**Request** 

>` POST https://api.demdex.com/v1/destinations/ *` <destinationId>`*/bulk-create` 

>**Sample Request** 

>All request values are required unless otherwise indicated. >
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

>A successful response returns the array of created mappings. >
>```
>[ 
>    { 
>        "mappingId": 103454, 
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
>        "mappingId": 103455, 
>        "traitType": "SEGMENT", 
>        "traitValue": 0, 
>        "orderId": 780, 
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
>
>```

