---
description: A GET method that returns all destinations for the specified partner.
seo-description: A GET method that returns all destinations for the specified partner.
seo-title: Return All Destinations
solution: Audience Manager
title: Return All Destinations
uuid: f5cedaeb-341d-4066-b8b3-b18ec0eb733c
index: y
internal: n
snippet: y
translate: y
---

# Return All Destinations


>**Request** 

>` GET https://api.demdex.com/v1/destinations` 
>>[!NOTE]
>>
>>
>>* *(Optional)* Pass in ` containsSegment= *` <sid>`*` to return an array of all destinations mapped to the specified segment. For example, your query could look similar to this: ` GET .../destinations/?containsSegment=4321`.
>>* Does not return the full destination object. Get the destination by data order if you need fully populated object.

>


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

>**Sample Response** >
>```
>[ 
>   { 
>      "destinationId":364, 
>      "pid":1099, 
>      "name":"Test", 
>      "description":"", 
>      "status":"active", 
>      "destinationType":"PUSH", 
>      "createTime":1291345192000, 
>      "updateTime":1291347561000, 
>      "crUID":262, 
>      "upUID":262, 
>      "domainRestrictions":"all_domains" 
>   }, 
>   { 
>      "destinationId":369, 
>      "pid":1099, 
>      "name":"sample destination", 
>      "status":"active", 
>      "destinationType":"PUSH", 
>      "createTime":1292631706000, 
>      "updateTime":1292631706000, 
>      "crUID":262, 
>      "upUID":262, 
>      "domainRestrictions":"all_domains" 
>   } 
>]
>```

