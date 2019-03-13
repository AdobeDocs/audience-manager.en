---
description: API methods that let you work with derived signals. A derived signal qualifies site visitors for additional traits based on a trait they've already seen.
seo-description: API methods that let you work with derived signals. A derived signal qualifies site visitors for additional traits based on a trait they've already seen.
seo-title: Derived Signals API Methods
solution: Audience Manager
title: Derived Signals API Methods
uuid: 698019bc-d7f6-41e0-a78a-1ab0bf0e65a0
---

# Derived Signals [!DNL API] Methods {#derived-signals-api-methods}

[!DNL API] methods that let you work with derived signals. A derived signal qualifies site visitors for additional traits based on a trait they've already seen.

<!-- c_separator.xml -->

For more information about derived signals, see [Derived Signals](../../features/derived-signals.md#concept_36FF7303F39E4748AC048D08F9E371C6).

## Create a New Derived Signal {#reference_A27DB94B1F5C4A6AA55CAA301612D4CA}

A `POST` method that lets you create a new derived signal.

<!-- r_create_new_derived_signal.xml -->

### Request

`POST https://api.demdex.com/v1/signals/derived/`

### Sample Request Body

The [!DNL JSON] request body contains a source key and source value. These parameters are used to associate the source key-value pair with other traits that are associated (derived) from those values. For example, in this request the key-value pair `product SKU=1234` are also associated with a related target key-value pair. Note, source key and value variables must be unique. All request values are required unless otherwise indicated.

```
{
    "sourceKey": "product SKU",
    "sourceValue": "1234",
    "targetKey": "camera",
    "targetValue": "brand x"
}
```

### Response

A successful update returns response code `201 Created` and data as shown below. An unsuccessful attempt returns response code `409 Conflict` if the source/target mapping already exists.

```
{
    "derivedSignalId": 2,
    "targetKey": "camera",
    "sourceKey": "product SKU",
    "integrationCode": null,
    "targetValue": "brand x",
    "pid": 1099,
    "updateTime": 1319752831000,
    "version": 0,
    "upUID": 507,
    "crUID": 507,
    "sourceValue": "1234",
    "createTime": 1319752831000
}
```

## Delete a Derived Signal {#reference_6EBC0874E6F8438393585BEE6DC95294}

A `DELETE` method that lets you remove a derived signal from your collection.

<!-- r_delete_derived_signal.xml -->

### Request

`DELETE https://api.demdex.com/v1/signals/derived/`*`<derivedSignalId>`*

### Response

Returns response code `204 No Content` if successful.

## Return Properties for a Derived Signal {#reference_B9CCCB0A72BF4D6D9DB71A17C1165771}

A `GET` method that returns details for an individual derived signal.

<!-- r_get_derived_signal_details.xml -->

### Request

`GET https://api.demdex.com/v1/signals/derived/`*`<derivedSignalId>`*

### Response

A successful request returns response code `200 OK` and data as shown below. 

```
{
    "derivedSignalId": 2,
    "targetKey": "targetKey",
    "sourceKey": "sourceKey",
    "integrationCode": null,
    "targetValue": "targetValue",
    "pid": 1099,
    "updateTime": 1319752928000,
    "version": 1,
    "upUID": 507,
    "crUID": 507,
    "sourceValue": "sourceValue",
    "createTime": 1319752831000
}
```

## Return Properties for all Derived Signals {#reference_3346F7C5605B4C08BFEFDA56BE2851C4}

A `GET` method that returns details for all your derived signals.

<!-- r_return_all_derived_signals.xml -->

### Request

`GET https://api.demdex.com/v1/signals/derived/`

### Optional Query Parameters

You can use these optional parameters with [!DNL API] methods that return *all* properties for an object. Set these options in the request string when passing that query in to the [!DNL API]. See [Optional Parameters](../../api/rest-api-main/aam-api-getting-started.md#concept_BB1E73AE736F4F54830E6CAF28089608).  

<table id="table_B05A8EE22C9A4C72B84A8479E1AB7D0A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"><code> page</code> </td> 
   <td colname="col2"> Returns results by page number. Numbering starts at 0. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td> 
   <td colname="col2"> Sets the number of response results returned by the request (10 is default). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td> 
   <td colname="col2">Sorts and returns results according to the specified <span class="keyword"> JSON</span> property. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td> 
   <td colname="col2"> Sorts and returns results in descending order. Ascending is default. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code> search</code> </td> 
   <td colname="col2">Returns results based on the specified string you want to use as a search parameter. For example, let's say you want to find results for all models that have the word "Test" in any of the value fields for that item. Your sample request could look like this: <p><code> GET https://api.demdex.com/v1/models/?search=Test</code>. </p> <p>You can search on any value returned by a "get all" method. </p> </td>
  </tr>
 </tbody>
</table>

### Response

A successful update returns response code `200 OK` and data (in an array) as shown below. All request values are required unless otherwise indicated.

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