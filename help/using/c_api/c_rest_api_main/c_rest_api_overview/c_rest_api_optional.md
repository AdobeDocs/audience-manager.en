---
description: Set the optional parameters available to methods that return all properties for an object.
seo-description: Set the optional parameters available to methods that return all properties for an object.
seo-title: Optional API Query Parameters
solution: Audience Manager
title: Optional API Query Parameters
uuid: 69049cf0-01d8-4419-b131-14dc5cec05c0
index: y
internal: n
snippet: y
translate: y
---

# Optional API Query Parameters

You can use these optional parameters with API methods that return *all* properties for an object. Set these options in the request string when passing that query in to the API. 

<table id="table_B05A8EE22C9A4C72B84A8479E1AB7D0A"> 
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
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> permissions </span> </td> 
   <td colname="col2"> <p>Returns a list of segments based on the specified permission. <span class="codeph"> READ </span> is default. Permissions include: 
     <ul id="ul_389EA328C64448F0BC76E80E13CAB406"> 
      <li id="li_339A737BC71646699AA337A2243CF992"> <span class="codeph"> READ </span>: Return and view information about a segment. </li> 
      <li id="li_18EF54637F6849D1A72EEE9FB60E3E5F"> <span class="codeph"> WRITE </span>: Use <span class="codeph"> PUT </span> to update a segment. </li> 
      <li id="li_8903069EC759441FACBA2C2922A02CA2"> <span class="codeph"> CREATE </span>: Use <span class="codeph"> POST </span> to create a segment. </li> 
      <li id="li_50F95EE7A08D469F97A555E4AEF7F1EE"> <span class="codeph"> DELETE </span>: Delete a segment. Requires access to underlying traits, if any. For example, you'll need rights to delete the traits that belong to a segment if you want to remove it. </li> 
     </ul> </p> <p>Specify multiple permissions with separate key-value pairs. For example, to return a list of segments with <span class="codeph"> READ </span> and <span class="codeph"> WRITE </span> permissions only, pass in <span class="codeph"> "permissions":"READ", "permissions":"WRITE" </span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> includePermissions </span> </td> 
   <td colname="col2"> <p>(Boolean) Set to <span class="codeph"> true </span> to return your permissions for the segment. Default is <span class="codeph"> false </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**A Note About Page Options** 

When page information *is not* specified, the request returns plain JSON results in an array. If page information *is* specified, then the returned list is wrapped in a JSON object that contains information about the total result and current page. Your sample request using page options could look similar to this: 
```
GET https://api.demdex.com/v1/models/?page=1&amp;pageSize=2&amp;search=Test
```

