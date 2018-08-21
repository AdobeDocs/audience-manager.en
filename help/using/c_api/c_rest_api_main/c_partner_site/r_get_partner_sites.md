---
description: A GET method that returns information about all your domains (for cookie destinations only).
seo-description: A GET method that returns information about all your domains (for cookie destinations only).
seo-title: Return Properties for all Domains
solution: Audience Manager
title: Return Properties for all Domains
uuid: 23e5d5d4-3a16-4780-877a-ebdfd4689986
index: y
internal: n
snippet: y
translate: y
---

# Return Properties for all Domains


>**Request** 

>`GET ` https://api.demdex.com/v1/partner-sites/`` 

>**Optional Query Parameters** 

>You can use these optional parameters with API methods that return *all* properties for an object. Set these options in the request string when passing that query in to the API. See [ Optional Parameters](../../../c_api/c_rest_api_main/c_rest_api_overview/c_rest_api_optional.md#concept_BB1E73AE736F4F54830E6CAF28089608). 

><table id="table_B05A8EE22C9A4C72B84A8479E1AB7D0A">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Parameter </th>
   <th colname="col2" class="entry"> Description </th>
  </tr>
 </thead>
 <tbody>
  <tr valign="top">
   <td colname="col1"><span class="codeph"> page</span></td>
   <td colname="col2"> Returns results by page number. Numbering starts at 0. </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><span class="codeph"> pageSize</span></td>
   <td colname="col2"> Sets the number of response results returned by the request (10 is default). </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><span class="codeph"> sortBy</span></td>
   <td colname="col2"> Sorts and returns results according to the specified JSON property. </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><span class="codeph"> descending</span></td>
   <td colname="col2"> Sorts and returns results in descending order. Ascending is default. </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><span class="codeph"> search</span></td>
   <td colname="col2">Returns results based on the specified string you want to use as a search parameter. For example, let's say you want to find results for all models that have the word "Test" in any of the value fields for that item. Your sample request could look like this: <p><span class="codeph"> GET https://api.demdex.com/v1/models/?search=Test</span>. </p><p>You can search on any value returned by a "get all" method. </p></td>
  </tr>
 </tbody>
</table>

>**Sample Response** 

>A successful response returns ` 200 OK` and data in an array as shown in the sample below. Returns ` 404 Not found` if the site ID or partner is not found. >
>```
>[
>    {
>        "pid": 1111,
>        "siteId": 111,
>        "url": "example1.com"
>    },
>    {
>        "pid": 2222,
>        "siteId": 222,
>        "url": "example2.com"
>    },
>    {
>        "pid": 3333,
>        "siteId": 333,
>        "url": "example3.com"
>    }
>]
>
>```

