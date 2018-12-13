---
description: A GET method that returns the destination for the specified destinationId.
seo-description: A GET method that returns the destination for the specified destinationId.
seo-title: Return A Destination by Destination ID
solution: Audience Manager
title: Return A Destination by Destination ID
uuid: abce7426-55a5-4045-93a7-0487652a7189
index: y
internal: n
snippet: y
---

# Return A Destination by Destination ID {#return-a-destination-by-destination-id}

A `GET` method that returns the destination for the specified `destinationId`.

<!--
r_get_all_destinations_order_id.xml
-->

## Request

`GET https://api.demdex.com/v1/destinations/<destinationId>`

>[!NOTE]
>
>To populate the `mappings` field pass in `includeMappings=true` in the URL.

## Response

```
{
   "destinationType":"PUSH",
   "destinationId":314,
   "dataSourceId":null,
   "pid":1099,
   "name":"sample destination",
   "description":"Turn",
   "startDate":null,
   "endDate":null,
   "status":"active",
   "destinationType":"PUSH",
   "createTime":1281997484000,
   "updateTime":1300752888000,
   "crUID":224,
   "upUID":308,
   "domainRestrictions":"ALL_DOMAINS",
   "tagType":0,
   "serializationEnabled":false,
   "urlFormatString":null,
   "secureUrlFormatString":null,
   "delimiter":null,
   "mappings":null
}
```

## Return All Destinations {#reference_74F0AAA5324B4B6CA6463CB634AC7FF5}

A `GET` method that returns all destinations for the specified partner.

<!--
r_get_all_destinations.xml
-->

### Request

`GET https://api.demdex.com/v1/destinations` 

>[!NOTE]
>
>* *(Optional)* Pass in `containsSegment=<sid>` to return an array of all destinations mapped to the specified segment. For example, your query could look similar to this: `GET .../destinations/?containsSegment=4321`. 
>
>* Does not return the full destination object. Get the destination by data order if you need fully populated object.

### Optional Query Parameters

You can use these optional parameters with API methods that return *all* properties for an object. Set these options in the request string when passing that query in to the API. See [Optional Parameters](../../../c-api/c-rest-api-main/aam-api-getting-started.md#concept_BB1E73AE736F4F54830E6CAF28089608).  

<table id="table_B05A8EE22C9A4C72B84A8479E1AB7D0A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"><span class="codeph"> page</span> </td> 
   <td colname="col2"> Returns results by page number. Numbering starts at 0. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><span class="codeph"> pageSize</span> </td> 
   <td colname="col2"> Sets the number of response results returned by the request (10 is default). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><span class="codeph"> sortBy</span> </td> 
   <td colname="col2">Sorts and returns results according to the specified <span class="keyword"> JSON</span> property. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><span class="codeph"> descending</span> </td> 
   <td colname="col2"> Sorts and returns results in descending order. Ascending is default. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><span class="codeph"> search</span> </td> 
   <td colname="col2">Returns results based on the specified string you want to use as a search parameter. For example, let's say you want to find results for all models that have the word "Test" in any of the value fields for that item. Your sample request could look like this: <p><span class="codeph"> GET https://api.demdex.com/v1/models/?search=Test</span>. </p> <p>You can search on any value returned by a "get all" method. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Response 

```
[
   {
      "destinationId":364,
      "pid":1099,
      "name":"Test",
      "description":"",
      "status":"active",
      "destinationType":"PUSH",
      "createTime":1291345192000,
      "updateTime":1291347561000,
      "crUID":262,
      "upUID":262,
      "domainRestrictions":"all_domains"
   },
   {
      "destinationId":369,
      "pid":1099,
      "name":"sample destination",
      "status":"active",
      "destinationType":"PUSH",
      "createTime":1292631706000,
      "updateTime":1292631706000,
      "crUID":262,
      "upUID":262,
      "domainRestrictions":"all_domains"
   }
]
```

## Return a Destination Mapping With the Mapping ID {#reference_B763509781914A5CB8FC89012C56F56D}

A `GET` method that returns an individual destination mapping based on the `mappingId`.

<!-- 
r_get_destination_trait_data_order.xml
-->

### Request

`GET https://api.demdex.com/v1/destinations/<destinationId>/mappings/ <destinationMappingId>`

### Response

```
{
"mappingId": 14593,
"traitType": "SEGMENT",
"traitValue": 0,
"destinationId": 314,
"elementName": "sample",
"elementDescription": "Migration Pixel",
"elementStatus": "active",
"createTime": 1281997484000,
"updateTime": 1300752888000,
"crUID": 224,
"upUID": 308,
"sid": 80920,
"startDate": "2010-11-15",
"endDate": null,
"priority": null,
"url": "https://www.adobe.com/send?%ALIAS%",
"secureUrl": "https://www.adobe.com/send?%ALIAS%",
"tagCode": null,
"secureTagCode": null,
"traitAlias": null
}
```

## Return Destination Mappings {#reference_2EF17D608D804F2FAC95AE18B3F0DCA3}

A `GET` method that returns the mappings for a destination.

<!--
r_get_destination_mappings.xml
-->

>[!NOTE]
>
>The returned mapping is specific to the destination type and configuration.

### Request

`GET https://api.demdex.com/v1/destinations/ *<destinationId>*/mappings`

>[!NOTE]
>
>Supports paging parameters.

### Response

```
{
   "total":354,
   "page":0,
   "pageSize":2,
   "list":[
      {
         "destinationMappingId":14395,
         "traitType":"SEGMENT",
         "traitValue":0,
         "destinationId":314,
         "elementName":"sample pixel",
         "elementDescription":"Migration Pixel",
         "elementStatus":"active",
         "createTime":1281997484000,
         "updateTime":1300752888000,
         "crUID":224,
         "upUID":308,
         "sid":80920,
         "startDate":"2010-11-15",
         "endDate":null,
         "priority":null,
         "url":"https://www.adobe.com/send?%ALIAS%",
         "secureUrl":"https://www.adobe.com/send?%ALIAS%",
         "tagCode":null,
         "secureTagCode":null,
         "traitAlias":null
      }
      {
         "destinationMappingId":15934,
         "traitType":"SEGMENT",
         "traitValue":0,
         "destinationId":314,
         "elementName":"sample pixel",
         "elementDescription":"Migration Pixel",
         "elementStatus":"active",
         "createTime":1281997484000,
         "updateTime":1300752888000,
         "crUID":242,
         "upUID":803,
         "sid":90820,
         "startDate":"2010-11-15",
         "endDate":null,
         "priority":null,
         "url":"https://www.adobe.com/send?%ALIAS%",
         "secureUrl":"https://www.adobe.com/send?%ALIAS%",
         "tagCode":null,
         "secureTagCode":null,
         "traitAlias":null
      }
   ]
{
```

## Return All Available Destination Platforms {#reference_279D5A95143C499EA9A1B8C1B601DB7B}

A `GET` method that returns all available device platforms for destinations.

<!-- 
r_get_dest_platforms.xml
-->

### Request

`GET /destinations/configurations/available-platforms/`

### Response

```
[
BROWSER, ANDROID, iOS, ALL
]
```

## Return [!UICONTROL S2S] and Bulk [!UICONTROL S2S] Destination Job History {#reference_DAAAAE296B1248CAA347D9344EB182F2}

A `GET` method that returns outbound [!UICONTROL Server-to-Server] ( [!UICONTROL S2S]) and bulk [!UICONTROL S2S] destination job history information.

<!--
r_get_job_history.xml
-->

### Request

`GET https://api.demdex.com/v1/destinations/655/history/outbound?startDate=1000000000&endDate=1403034473000`

Required query parameters: `startDate` =< *`epochtime`*> and *`endDate`* =< [!UICONTROL epochtime]>.

### Response

```
[
{
      "pushID":34090,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337292466000,
      "endTime":1337292466000,
      "dataFileName":"ftp_655_269_iter_1337229891903.sync",
      "success":true
   },
   {
      "pushID":34104,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337346397000,
      "endTime":1337346397000,
      "dataFileName":"ftp_655_269_iter_1337285714581.sync",
      "success":true
   },
   {
      "pushID":34124,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337396811000,
      "endTime":1337396812000,
      "dataFileName":"ftp_655_269_iter_1337338243600.sync",
      "success":true
   }
]
```