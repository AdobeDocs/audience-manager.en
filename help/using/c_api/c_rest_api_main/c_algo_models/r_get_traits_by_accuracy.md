---
description: A GET method that returns a list of your most influential (accurate) traits.
seo-description: A GET method that returns a list of your most influential (accurate) traits.
seo-title: Return Properties for Your Most Accurate Traits
solution: Audience Manager
title: Return Properties for Your Most Accurate Traits
uuid: 4f881aae-e717-473c-b503-d7d94c503350
index: y
internal: n
snippet: y
translate: y
---

# Return Properties for Your Most Accurate Traits


>**Request** 

>` GET https://api.demdex.com/v1/models/ *` <model-id>`*/runs/latest/traits/` 

>**Optional Query Parameters** 

>You can use these optional parameters with API methods that return *all* properties for an object. Set these options in the request string when passing that query in to the API. See also [ Optional Parameters ](../../../c_api/c_rest_api_main/c_rest_api_overview/c_rest_api_optional.md#concept_BB1E73AE736F4F54830E6CAF28089608). 

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
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> folderId </span> </td> 
   <td colname="col2"> Returns all the IDs for traits inside the specified folder. Not available to all methods. </td> 
  </tr> 
 </tbody> 
</table>

>**Sample Response** >
>```
>{ 
>   "total": 2, 
>   "page": 0, 
>   "pageSize": 10, 
>   "list": [ 
>        { 
>          "sid": 914, 
>          "pid": 1, 
>          "name": "sample rule", 
>          "description": "hello world, i am your rule.. err", 
>          "traitRuleVersion": 0, 
>          "ttl": 0, 
>          "crUID": 3, 
>          "upUID": 3, 
>          "createTime": 1346790825000, 
>          "updateTime": 1346790825000, 
>          "dataSourceId": 3, 
>          "folderId": 10, 
>          "traitType": "RULE_BASED_TRAIT", 
>          "uniques7Day": 213930, 
>          "uniques14Day": 415599, 
>          "uniques30Day": 770717, 
>          "uniques60Day": 9, 
>          "count7Day": 657, 
>          "count14Day": 626, 
>          "count30Day": 5201,  
>          "count60Day": 149, 
>          "weight": 67, 
>          "rank": 1 
>        }, 
>       { 
>          "sid": 9, 
>          "pid": 1, 
>          "name": "trait2", 
>          "description": "new trait 2", 
>          "comments": "", 
>          "integrationCode": "", 
>          "traitRule": "", 
>          "traitRuleVersion": 0, 
>          "ttl": 0, 
>          "crUID": 3, 
>          "upUID": 3, 
>          "createTime": 1344277873000, 
>          "updateTime": 1344277873000, 
>          "type": 1, 
>          "dataSourceId": 1, 
>          "folderId": 10, 
>          "traitType": 3, 
>          "uniques7Day": 113632, 
>          "uniques14Day": 210777, 
>          "uniques30Day": 393718, 
>          "uniques60Day": 77, 
>          "count7Day": 85502, 
>          "count14Day": 977684, 
>          "count30Day": 3755, 
>          "count60Day": 18517223, 
>          "weight": 37, 
>          "rank": 2 
>        } 
>   ] 
>}
>```

