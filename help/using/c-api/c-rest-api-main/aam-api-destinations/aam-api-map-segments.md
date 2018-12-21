---
description: Map segments to destinations with these RESTful API methods.
seo-description: Map segments to destinations with these RESTful API methods.
seo-title: Map Segments to a Destination
solution: Audience Manager
title: Map Segments to a Destination
uuid: 35358ace-3082-4e86-a6eb-d77281af6d7e
---

# Map Segments to a Destination {#map-segments-to-a-destination}

Map segments to destinations with these [!DNL RESTful API] methods.

<!--
c_api_map_seg_dest.xml
-->

## Supported Destination Types: [!UICONTROL URL] and [!UICONTROL Cookie] Only

The available `POST` methods let you map segments to [!UICONTROL URL] and [!UICONTROL cookie destinations] only. Currently, you cannot map segments to [!UICONTROL server-to-server destinations] with these [!DNL REST API] methods. Use the user interface instead. However, the related destination `GET` methods let you retrieve information about [!UICONTROL server-to-server destinations] created in the user interface.

>[!MORE_LIKE_THIS]
>
>* [Destinations](../../../c-features/destinations/destinations.md#destination-api-methods)
>* [Destination Serialization](../../../c-features/destinations/key-value-pairs.md#concept_02436A7C6C574C799F079EB731A63262)
>* [Key-Value Pairs Explained](../../../reference/key-value-pairs-explained.md#concept_E4236E003076483AA939791FE2492B49)

## Map a Segment to a Non-Serialized [!UICONTROL URL] Destination {#reference_0BFD55096FD845EC9970012C53CFE643}

A `POST` method that lets you map a segment to a non-serial [!UICONTROL URL] destination.

<!-- 
r_map_noserial_url.xml
-->

### Request

`POST https://api.demdex.com/v1/destinations/ *<destinationId>*/mappings/`

### Sample Request

All request values are required unless otherwise indicated.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-07-04"
}
```

### Response

```
{
   "mappingId":65334,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4033,
   "elementName":"Sample games",
   "elementDescription":"Sample games pixel",
   "elementStatus":"active",
   "createTime":1338940094000,
   "updateTime":1338940094000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "url":"https://adobe.com",
   "secureUrl":null,
   "tagCode":null,
   "secureTagCode":null,
   "traitAlias":null
}
```

## Map a Segment to a Serialized [!UICONTROL URL] Destination {#reference_658AB62CA686491FB9D0E53458801343}

A `POST` method that lets you map a segment to a serialized [!UICONTROL URL] destination.

<!--
r_map_serialized_url.xml
-->

### Request

`POST https://api.demdex.com/v1/destinations/ *<dataOrderId>*/traits/`

### Sample Request

In the request, the `traitAlias` corresponds to the key in a key-value pair. All request values are required unless otherwise indicated.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"123"
}
```

### Response 

```
{
   "mappingId":65335,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4034,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338940401000,
   "updateTime":1338940401000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "url":"123",
   "secureUrl":"123",
   "tagCode":null,
   "secureTagCode":null,
   "traitAlias":"123"
}
```

## Map a Segment to a [!UICONTROL Cookie] Destination: Single-Key, Non-Serialized {#reference_612B2A53AE8E4262A36F73601151CFDD}

A `POST` method that lets you map a segment to single-key, non-serialized [!UICONTROL cookie] destination.

<!--
r_map_cookie_noserial.xml
-->

### Request

`POST https://api.demdex.com/v1/destinations/<destinationId>/mappings/`

### Sample Request

In the request, the `valueAlias` corresponds to the value in a key-value pair. All request values are required unless otherwise indicated. 

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "valueAlias":"123"
}
```

### Response 

```
{
   "destinationMappingId":65336,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4035,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338940704000,
   "updateTime":1338940704000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":1,
   "traitAlias":null,
   "valueAlias":"123"
}
```

## Map a Segment to a [!UICONTROL Cookie] Destination: Multi-Key, Non-Serialized {#reference_139815314E1446BB9E335DCCDD1CEE6E}

A `POST` method that lets you map a segment to multi-key, non-serialized [!UICONTROL cookie] destination.

<!--
r_map_cookie_multikey_noserial.xml
-->

### Request

`POST https://api.demdex.com/v1/destinations/ *<destinationId>*/mappings/`

### Sample Request

In the request, the `traitAlias` and `valueAlias` set the key and the value respectively in a key-value pair. All request values are required unless otherwise indicated.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"type",
   "valueAlias":"123"
}
```

### Response 

```
{
   "mappingId":65338,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4037,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338941092000,
   "updateTime":1338941092000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":1,
   "traitAlias":"type",
   "valueAlias":"123"
}
```

## Map a Segment to a [!UICONTROL Cookie] Destination: Multi-Key, Serialized {#reference_C0FA140B45B844CE8EE6E5E0487D7EB8}

A `POST` method that lets you map a segment to a multi-key, serialized [!UICONTROL cookie destination].

<!-- 

r_map_cookie_multikey_serialized.xml

 -->

### Request

`POST https://api.demdex.com/v1/destinations/ *<destinationId>*/mappings/`

### Sample Request

In the request, the `traitAlias` and `valueAlias` set the key and the value in a key-value pair. All request values are required unless otherwise indicated. 

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"type",
   "valueAlias":"123"
}
```

### Response

```
{
   "destinationMappingId":65340,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4038,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338941273000,
   "updateTime":1338941273000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":2,
   "traitAlias":"type",
   "valueAlias":"123"
}
```

## Map a Segment to a [!UICONTROL Server-to-Server] Destination {#reference_1F6C3A534C234BE4B01C32B09EC93101}

A `POST` method that lets you map a segment to an existing [!UICONTROL server-to-server] destination. Note, however, that you cannot create [!UICONTROL server-to-server] destinations with these currently available API methods.

<!-- 
r_map_segment_s2s.xml
-->

### Request

`POST https://api.demdex.com/v1/destinations/ *<destinationId>*/mappings/`

### Sample Request

In the request, the `traitAlias` corresponds to the key in a key-value pair. All request values are required unless otherwise indicated.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"123"
}
```

### Response

```
{
   "destinationMappingId":65341,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":566,
   "elementName":"Sample",
   "elementDescription":"",
   "elementStatus":"active",
   "createTime":1338942118000,
   "updateTime":1338942118000,
   "crUID":308,
   "upUID":308,
   "sid":84326,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "traitAlias":"123"
}
```

## Bulk Create Destination Mappings {#reference_606B59C76501457F9F816AFB617FCF77}

A `POST` method that lets you pass in an array of [!UICONTROL cookie] or [!UICONTROL URL] destination mappings.

<!-- 
r_bulk_create.xml
-->

### Request

`POST https://api.demdex.com/v1/destinations/ *<destinationId>*/bulk-create`

### Sample Request

All request values are required unless otherwise indicated.

```
[
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
},
{
   "sid": 121070,
   "traitType":"SEGMENT",
   "url":"https://my.adobeconnect.com",
   "startDate":"2012-11-21"
}
]
```

### Response

A successful response returns the array of created mappings.

```
[
    {
        "mappingId": 103454,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Case of the Mondays",
        "elementDescription": "test",
        "elementStatus": "active",
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 105123,
        "startDate": "2012-11-19",
        "endDate": null,
        "priority": null,
        "url": "https://adobe.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    },
    {
        "mappingId": 103455,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "orderId": 780,
        "elementName": "Test Trait",
        "elementDescription": "This trait",
        "elementStatus": 1,
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 121070,
        "startDate": "2012-11-20",
        "endDate": null,
        "priority": null,
        "url": "https://my.adobeconnect.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    }
]

```

## Add Multiple Segments to a Destination {#reference_99061353A1BE4722B0CD469E9B598E4B}

A `POST` method that lets you map multiple segments to a destination.

<!--
r_add_segments_to_destination.xml
-->

### Request

`POST https://api.demdex.com/v1/destinations/ *<destinationId>*/bulk-create`

### Sample Request

Create multiple destination mappings in an array. All request values are required unless otherwise indicated.

```
[
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
},
{
   "sid": 121070,
   "traitType":"SEGMENT",
   "url":"https://my.adobeconnect.com",
   "startDate":"2012-11-21"
}
]
```

### Response

Returns an array of created mappings.

```
[
    {
        "destinationMappingId": 103454,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Case of the Mondays",
        "elementDescription": "test",
        "elementStatus": "active",
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 105123,
        "startDate": "2012-11-19",
        "endDate": null,
        "priority": null,
        "url": "https://adobe.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    },
    {
        "traitToDataOrderId": 103455,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Test Trait",
        "elementDescription": "This trait",
        "elementStatus": 1,
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 121070,
        "startDate": "2012-11-20",
        "endDate": null,
        "priority": null,
        "url": "https://my.adobeconnect.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    }
]
```

## Update a Destination by Destination ID {#reference_BECDC0988B5F45C4B8EF75836EA63A48}

A `PUT` method that lets you update an existing destination by `destinationId`.

<!--
r_update_destination_data_order_id.xml
-->

### Request

`PUT https://api.demdex.com/v1/destinations/ *<destinationId>*`

### Sample Request

All request values are required unless otherwise indicated. 

```
{
   "name":"Updated URL Destination (not serialized)",
   "description":"new description",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### Response

```
{
    "destinationType": "PUSH",
    "destinationId": 780,
    "dataSourceId": null,
    "pid": 1099,
    "name": "Updated URL Destination (not serialized)",
    "description": "new description",
    "startDate": null,
    "endDate": null,
    "status": 1,
    "createTime": 1348851790000,
    "updateTime": 1353372029000,
    "crUID": 884,
    "upUID": 1065,
    "domainRestrictions":"all_domains",
    "tagType": 0,
    "serializationEnabled": false,
    "urlFormatString": null,
    "secureUrlFormatString": null,
    "delimiter": null,
    "mappings": null
}
```

## Update a Mapping to a Destination by Mapping ID {#reference_F1C48667B3DA4299BC6E291D7B113281}

A `PUT` method that lets you update a mapping to a destination by the specified `mappingId`.

<!--
r_update_destination_trait_data_order_id.xml
-->

### Request

`PUT https://api.demdex.com/v1/destinations/mappings/ *<mappingId>*`

### Sample Request

All request values are required unless otherwise indicated. 

```
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
}
```

### Response

```
{
    "mappingId": 103453,
    "traitType": "SEGMENT",
    "traitValue": 0,
    "destinationId": 780,
    "elementName": "sample",
    "elementDescription": "test",
    "elementStatus": "active",
    "createTime": 1353373005000,
    "updateTime": 1353373005000,
    "crUID": 1065,
    "upUID": 1065,
    "sid": 105123,
    "startDate": "2012-11-19",
    "endDate": null,
    "priority": null,
    "url": "https://www.adobe.com/send?%ALIAS%",
    "secureUrl": null,
    "tagCode": null,
    "secureTagCode": null,
    "traitAlias": null
}
```