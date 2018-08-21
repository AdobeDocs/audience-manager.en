---
description: A GET method that returns details for all your derived signals.
seo-description: A GET method that returns details for all your derived signals.
seo-title: Return Properties for all Derived Signals
solution: Audience Manager
title: Return Properties for all Derived Signals
uuid: 5173b9af-4cad-433f-9ccd-0742c04753c0
index: y
internal: n
snippet: y
translate: y
---

# Return Properties for all Derived Signals


<a id="section_8D11215FA5324329A26BECCC7C3A1A9A"></a>

**Request** 

` GET https://api.demdex.com/v1/signals/derived/` 

**Optional Query Parameters** 

You can use these optional parameters with API methods that return *all* properties for an object. Set these options in the request string when passing that query in to the API. See [ Optional Parameters](../../../c_api/c_rest_api_main/c_rest_api_overview/c_rest_api_optional.md#concept_BB1E73AE736F4F54830E6CAF28089608). 

<table id="table_B05A8EE22C9A4C72B84A8479E1AB7D0A">
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

**Sample Response** 

A successful update returns response code ` 200 OK` and data (in an array) as shown below. All request values are required unless otherwise indicated. 
```
[
    {
        "derivedSignalId": 1,
        "targetKey": "targetKey",
        "sourceKey": "sourceKey",
        "integrationCode": null,
        "targetValue": "targetValue",
        "pid": 1099,
        "updateTime": 1319746748000,
        "version": 0,
        "upUID": 507,
        "crUID": 507,
        "sourceValue": "sourceValue",
        "createTime": 1319746748000
    },
    {
        "DerivedSignalId": 2,
        "targetKey": "targetKey",
        "sourceKey": "sourceKey",
        "integrationCode": null,
        "targetValue": "targetValue",
        "pid": 1099,
        "updateTime": 1319752831000,
        "version": 0,
        "upUID": 507,
        "crUID": 507,
        "sourceValue": "sourceValue2",
        "createTime": 1319752831000
    }
]
```

