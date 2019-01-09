---
description: Domain management methods that let you create and manage the domains to which you want to send data (for cookie destinations only).
seo-description: Domain management methods that let you create and manage the domains to which you want to send data (for cookie destinations only).
seo-title: Domain Management API Methods
solution: Audience Manager
title: Domain Management API Methods
uuid: f2f08bc5-ea42-4171-9a43-0b20976f0cb0
index: y
internal: n
snippet: y
---

# Domain Management API Methods {#domain-management-api-methods}

Domain management methods that let you create and manage the domains to which you want to send data (for cookie destinations only).

<!--
c_partner_site.xml
-->

## Create a New Domain {#reference_C332B8E339504884999ECC5314EF68A1}

A `POST` method that lets you create a new domain for (cookie destinations only).

<!--
r_post_new_partner_site.xml
-->

### Request

`POST` `https://api.demdex.com/v1/partner-sites/`

### Sample Request

```
{
   "url":"example1.com"
}
```

### Response

A successful response returns `201 created` and the partner site, including its unique ID.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Delete a Domain {#reference_C3738EA2162547BE996CCFE22EF0F3B0}

A `DELETE` method that lets you remove a domain (for cookie destinations only).

<!--
r_delete_partner_site.xml
-->

### Request

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### Response

A successful response returns `204 no content`. Returns `404 not found` if the partner site cannot be found.

## Return Properties for a Domain {#reference_6B9BD9A4B15040429F3F9AE0BC6787FE}

A `GET` method that returns details about the specified domain (for cookie destinations only).

<!--
r_get_partner_site.xml
-->

### Request

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### Response

A successful response returns `200 OK` and data as shown in the sample below. Returns `404 Not found` if the site ID or partner is not found.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Return Properties for all Domains {#reference_9EF522F1270E4AD1AC84F862716750DD}

A `GET` method that returns information about all your domains (for cookie destinations only).

<!--
r_get_partner_sites.xml
-->

### Request

`GET https://api.demdex.com/v1/partner-sites/`

### Optional Query Parameters

You can use these optional parameters with API methods that return *all* properties for an object. Set these options in the request string when passing that query in to the API. See [Optional Parameters](../../c-api/c-rest-api-main/aam-api-getting-started.md#concept_BB1E73AE736F4F54830E6CAF28089608).  

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
   <td colname="col2"> Sorts and returns results according to the specified JSON property. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><span class="codeph"> descending</span> </td>
   <td colname="col2"> Sorts and returns results in descending order. Ascending is default. </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><span class="codeph"> search</span> </td>
   <td colname="col2">Returns results based on the specified string you want to use as a search parameter. For example, let's say you want to find results for all models that have the word "Test" in any of the value fields for that item. Your sample request could look like this: <p><span class="codeph"> `GET` `https://api.demdex.com/v1/models/?search=Test`</span>. </p> <p>You can search on any value returned by a "get all" method. </p> </td>
  </tr> 
 </tbody> 
</table>

### Response

A successful response returns `200 OK` and data in an array as shown in the sample below. Returns `404 Not found` if the site ID or partner is not found.

```
[
    {
        "pid": 1111,
        "siteId": 111,
        "url": "example1.com"
    },
    {
        "pid": 2222,
        "siteId": 222,
        "url": "example2.com"
    },
    {
        "pid": 3333,
        "siteId": 333,
        "url": "example3.com"
    }
]
```