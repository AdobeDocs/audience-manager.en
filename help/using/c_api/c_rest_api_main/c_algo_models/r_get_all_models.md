---
description: A GET method that returns details about all your models.
seo-description: A GET method that returns details about all your models.
seo-title: Return Properties for all Models
solution: Audience Manager
title: Return Properties for all Models
uuid: b67403a4-3484-4d1d-ac88-895b5a9dc30d
index: y
internal: n
snippet: y
translate: y
---

# Return Properties for all Models


>**Request** 

>` GET https://api.demdex.com/v1/models/` 

>**Optional Query Parameters** 

>You can use these optional parameters with API methods that return *all* properties for an object. Set these options in the request string when passing that query in to the API. See [ Optional Parameters ](../../../c_api/c_rest_api_main/c_rest_api_overview/c_rest_api_optional.md#concept_BB1E73AE736F4F54830E6CAF28089608). 

><table id="table_B05A8EE22C9A4C72B84A8479E1AB7D0A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> page </span> </td> 
   <td colname="col2"> Returns results by page number. Numbering starts at 0. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> pageSize </span> </td> 
   <td colname="col2"> Sets the number of response results returned by the request (10 is default). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> sortBy </span> </td> 
   <td colname="col2"> Sorts and returns results according to the specified JSON property. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> descending </span> </td> 
   <td colname="col2"> Sorts and returns results in descending order. Ascending is default. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> search </span> </td> 
   <td colname="col2"> Returns results based on the specified string you want to use as a search parameter. For example, let's say you want to find results for all models that have the word "Test" in any of the value fields for that item. Your sample request could look like this: <p> <span class="codeph"> GET https://api.demdex.com/v1/models/?search=Test </span>. </p> <p>You can search on any value returned by a "get all" method. </p> </td> 
  </tr> 
 </tbody> 
</table>

>**Sample Request** 

>
>```
>GET https://api.demdex.com/v1/models/?page=1&amp;pageSize=2&amp;search=Test
>```


>**Sample Response** >
>```
>["total": 43, 
> "page": 1, 
> "pageSize": 2, 
> "list": [ 
>   { 
>      "algoModelId":698, 
>      "pid":1099, 
>      "name":"Test model", 
>      "description":"For testing", 
>      "algoTypeId":1, 
>      "intervalSeconds":604800, 
>      "lookBackPeriod":30, 
>      "crUID":833, 
>      "upUID":833, 
>      "status":"INACTIVE", 
>      "lastRunStatus":null, 
>      "createTime":1427474087000, 
>      "algoModelVersion":0, 
>      "sid":1784945, 
>      "lastRunTimestamp":null, 
>      "baselineTraitType":"SEGMENT", 
>      "lastSuccessfulRunTimestamp":null, 
>      "updateTime":1427474947000 
>   }, 
>   { 
>      "algoModelId":738, 
>      "pid":1234, 
>      "name":"Another Test Model", 
>      "description":"For testing", 
>      "algoTypeId":1, 
>      "intervalSeconds":604800, 
>      "lookBackPeriod":30, 
>      "crUID":833, 
>      "upUID":833, 
>      "status":"ACTIVE", 
>      "lastRunStatus":2, 
>      "createTime":1422494342000, 
>      "algoModelVersion":0, 
>      "sid":916388, 
>      "lastRunTimestamp":1431445691000, 
>      "baselineTraitType":"SEGMENT", 
>      "lastSuccessfulRunTimestamp":1431445691000, 
>      "updateTime":1429133721000 
>   } 
>]
>```

