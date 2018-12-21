---
description: Create destinations with these RESTful API methods.
seo-description: Create destinations with these RESTful API methods.
seo-title: Create Destinations
solution: Audience Manager
title: Create Destinations
uuid: 12f04151-ad0e-4cb6-8f3b-b5c427dc2cef
---

# Create Destinations {#create-destinations}

Create destinations with these [!UICONTROL RESTful API] methods.

<!-- 
c_create_destinations.xml
-->

## Supported Destination Types: [!DNL URL] and [!DNL Cookie] Only

The available `POST` methods let you create [!UICONTROL URL] and [!UICONTROL cookie destinations] only. Currently, you cannot create [!UICONTROL server-to-server destinations] with these [!DNL REST API] methods. However, the related destination `GET` methods let you retrieve information about [!UICONTROL server-to-server destinations] created in the user interface.

>[!MORE_LIKE_THIS]
>
>* [Destinations](../../../c-features/destinations/destinations.md#destination-api-methods)
>* [Destination Serialization](../../../c-features/destinations/key-value-pairs.md#concept_02436A7C6C574C799F079EB731A63262)
>* [Key-Value Pairs Explained](../../../reference/key-value-pairs-explained.md#concept_E4236E003076483AA939791FE2492B49)

## Create a Non-Serial [!UICONTROL URL Destination] {#reference_CD17C3E3D02143C89A00B28CBB2A9EE9}

A `POST` method that lets you create a destination that accepts segments composed of single key-value pairs (e.g., `gender=male` or `gender=female`).

<!-- 
r_create_nonserial_destination.xml
-->

### Request

`POST https://api.demdex.com/v1/destinations/`

### Sample Request

This request creates a single destination. All request values are required unless otherwise indicated.

```
{ 
   "name":"Sample URL Destination (not serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### Response

A successful request returns `201 created` and the destination.

```
{ 
   "destinationType":"PUSH", 
   "destinationId":4033, 
   "dataSourceId":null, 
   "pid":1099, 
   "name":"Sample URL Destination (not serialized)", 
   "description":"", 
   "startDate":null, 
   "endDate":null, 
   "status":"ACTIVE", 
   "destinationType":"PUSH", 
   "createTime":1338937116000, 
   "updateTime":1338937116000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "tagType":0, 
   "serializationEnabled":false, 
   "urlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "secureUrlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "delimiter":null,
   "mappings":null
} 

```

>[!MORE_LIKE_THIS]
>
>* [Destination Serialization](../../../c-features/destinations/key-value-pairs.md#concept_02436A7C6C574C799F079EB731A63262)

## Create a Serialized [!UICONTROL URL Destination] {#reference_5F0A43A3FE8E4014B1F1010E39FD8EC3}

A `POST` method that lets you create a destination that accepts multiple values associated with a single key (e.g., `color=blue, red, green`).

<!-- 
r_create_serial_url_destination.xml
-->

### Request

`POST https://api.demdex.com/v1/destinations/`

### Sample Request

Specify the secure URL and delimiter for the key-value pair passed in to the destination. All request values are required unless otherwise indicated.

```
{ 
   "name":"Sample URL Destination (Serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":true,
   "urlFormatString":"https://www.adobe.com/send?data=%ALIAS%",
   "secureUrlFormatString":"https://www.adobe.com/%ALIAS%",
   "delimiter":","
}
```

### Response

A successful update returns response code `201 created` and the destination. 

```
{ 
   "destinationType":"PUSH", 
   "destinationId":4034, 
   "dataSourceId":null, 
   "pid":1099, 
   "name":"Sample URL Destination (Serialized)", 
   "description":"", 
   "startDate":null, 
   "endDate":null, 
   "status":"active", 
   "destinationType":"PUSH", 
   "createTime":1338937420000, 
   "updateTime":1338937420000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "tagType":0, 
   "serializationEnabled":true, 
   "urlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "secureUrlFormatString":"https://www.adobe.com/%ALIAS%", 
   "delimiter":"-", 
   "mappings":null 
}
```

>[!MORE_LIKE_THIS]
>
>* [Destination Serialization](../../../c-features/destinations/key-value-pairs.md#concept_02436A7C6C574C799F079EB731A63262)

## Create a [!UICONTROL Cookie] Destination: Single-Key, Non-Serialized {#reference_1CFA380EE9E740099E43B28E985BF23D}

A `POST` method that lets you create a [!UICONTROL cookie destination] that accepts segments composed of single key-value pairs (e.g., `gender=male` or `gender=female`).

<!--
r_cookie_destination_singlekey_noserial.xml
-->

### Request

`POST https://api.demdex.com/v1/destinations/`

### Sample Request

All request values are required unless otherwise indicated.

```
{ 
   "name":"Cookie Destination Single Key Not Serialized",
   "destinationType":"ADS",
   "adServerTypeID":1,
   "cookieName":"adobe",
   "cnameDomain":"adobe.com",
   "maxSize":"2048",
   "ttl":"0",
   "domainRestrictions":"inclusion",
   "siteIDs":[
      312
   ],
   "formatType":"single_key",
   "singleKey":"key",
   "keySeparator":"=",
   "valueSeparator":",",
   "serializationEnabled":false
}
```

### Response

A successful update returns response code `201 created` and the destination. 

```
{ 
   "destinationType":"ADS", 
   "destinationId":4035, 
   "pid":1099, 
   "name":"Cookie Destination Single Key Not Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338937984000, 
   "updateTime":1338937984000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"inclusion", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "singleKey":"key", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"single_key", 
   "transferMethod":0, 
   "serializationEnabled":false, 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
      312 
   ], 
   "uparamEnabled":false 
} 

```

>[!MORE_LIKE_THIS]
>
>* [Destination Serialization](../../../c-features/destinations/key-value-pairs.md#concept_02436A7C6C574C799F079EB731A63262)
>* [Key-Value Pairs Explained](../../../reference/key-value-pairs-explained.md#concept_E4236E003076483AA939791FE2492B49)

## Create a [!UICONTROL Cookie] Destination: Single Key, Serialized {#reference_D83C9F35928E4226AA89E7A089971147}

A `POST` method that lets you create a destination that accepts multiple values associated with a single key (e.g., `color=blue, red, green`).

<!--
r_cookie_destination_singlekey_serial.xml
-->

### Request

`POST https://api.demdex.com/v1/destinations/`

### Sample Request

All request values are required unless otherwise indicated. 

```
{ 
   "name":"Cookie Destination Single Key Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains", 
   "siteIDs":[ 
 
   ], 
   "formatType":"single_key", 
   "singleKey":"k", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":true, 
   "serializationSeparator":"#" 
}
```

### Response

A successful update returns response code `201 created` and the destination. 

```
{ 
   "destinationType":"ADS", 
   "destinationId":4036, 
   "pid":1099, 
   "name":"Cookie Destination Single Key Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338938329000, 
   "updateTime":1338938329000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "singleKey":"k", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"single_key", 
   "transferMethod":0, 
   "serializationEnabled":true, 
   "serializationSeparator":"#", 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
 
   ], 
   "uparamEnabled":false
}
```

>[!MORE_LIKE_THIS]
>
>* [Destination Serialization](../../../c-features/destinations/key-value-pairs.md#concept_02436A7C6C574C799F079EB731A63262)
>* [Key-Value Pairs Explained](../../../reference/key-value-pairs-explained.md#concept_E4236E003076483AA939791FE2492B49)

## Create a [!UICONTROL Cookie] Destination: Multi-Key, Non-Serialized {#reference_DA9D74FD834C463FBC9B28E4C1BD05CC}

A `POST` method that lets you create a destination that accepts segments that contain multiple keys with different values (e.g., `gender=male; gender=female; color=blue; color=red`).

<!--
r_create_cookie_multikey_noserial.xml
-->

### Request

`POST https://api.demdex.com/v1/destinations/`

### Sample Request

All request values are required unless otherwise indicated. 

```
{ 
   "name":"Ad Server Multi-Key Not Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains", 
   "siteIDs":[ 
  
   ], 
   "formatType":"key_value", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":false 
}
```

### Response

A successful update returns response code `201 created` and the destination. 

```
{ 
   "destinationType":"ADS", 
   "destinationId":4037, 
   "pid":1099, 
   "name":"Ad Server Multi-Key Not Serialized", 
   "status":1, 
   "destinationType":"ADS", 
   "createTime":1338938666000, 
   "updateTime":1338938666000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"key_value", 
   "transferMethod":0, 
   "serializationEnabled":false, 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
  
   ], 
   "uparamEnabled":false 
}
```

## Create a [!UICONTROL Cookie] Destination: Multi-Key, Serialized {#reference_DD9EC8757B504F9D9F2D0512D25269A3}

A `POST` method that lets you create a destination that accepts segments that contain multiple keys and values (e.g., `gender=male, female; color=blue, red, green`).

<!-- 
r_cookie_destination_multikey_serial.xml
-->

### Request

`POST https://api.demdex.com/v1/destinations/`

### Sample Request

All request values are required unless otherwise indicated. 

```
{ 
   "name":"Cookie Destination Multi-Key Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains", 
   "siteIDs":[ 
 
   ], 
   "formatType":"key_value", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":true, 
   "serializationSeparator":"#" 
}
```

### Response

A successful update returns response code `201 created` and the destination. 

```
{ 
   "destinationType":"ADS", 
   "destinationId":4038, 
   "pid":1099, 
   "name":"Ad Server Multi-Key Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338938872000, 
   "updateTime":1338938872000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"key_value", 
   "transferMethod":0, 
   "serializationEnabled":true, 
   "serializationSeparator":"#", 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
 
   ], 
   "uparamEnabled":false 
}
```

>[!MORE_LIKE_THIS]
>
>* [Destination Serialization](../../../c-features/destinations/key-value-pairs.md#concept_02436A7C6C574C799F079EB731A63262)
>* [Key-Value Pairs Explained](../../../reference/key-value-pairs-explained.md#concept_E4236E003076483AA939791FE2492B49)
