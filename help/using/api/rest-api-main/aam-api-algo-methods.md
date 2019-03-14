---
description: Methods that let you work programmatically with algorithmic modeling features.
keywords: api getting started;get started api
seo-description: Methods that let you work programmatically with algorithmic modeling features.
seo-title: Algorithmic API Methods
solution: Audience Manager
title: Algorithmic API Methods
uuid: 8d5304d7-c1cf-42df-94e7-3f583944bd62
---

# Algorithmic API Methods {#algorithmic-api-methods}

Methods that let you work programmatically with algorithmic modeling features.

<!-- c_algo_models.xml -->

>[!MORE_LIKE_THIS]
>
>* [Models](../../features/algorithmic-models/understanding-models.md#concept_49FB2DBD4AD041A4ABAAEE9D83BB996E)

## Create a New Model {#reference_B4FB46FD007B44C382C132A694478022}

A `POST` method that lets you create a new algorithmic model.

<!-- r_create_new_model.xml -->

### Request

`POST https://api.demdex.com/v1/models/`

### Request Parameters

<table id="table_B333D90E22144BD0B83A65C8129444AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Parameter </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
   <th colname="col3" class="entry"> <p>Example </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> name </code> </p> </td> 
   <td colname="col2"> <p>Give your model a short, logical name that describes its function or purpose. Avoid abbreviations, special characters, and accent marks. </p> </td> 
   <td colname="col3"> <p> <code> Interested in Footwear Model </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description </code> </p> </td> 
   <td colname="col2"> <p>A field for additional descriptive information about the model. </p> </td> 
   <td colname="col3"> <p> <code> This model is created to find traits similar to Interested in Footwear </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataSources </code> </p> </td> 
   <td colname="col2"> <p>Select the first and third-party data sources you want to use in the model. </p> </td> 
   <td colname="col3"> <p> <code> [11212, 33421, 55431] </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> sid </code> </p> </td> 
   <td colname="col2"> <p>Select a trait or segment as the baseline that the system algorithms use for modeling. </p> <p> <p>Note:  Select an onboarded trait, a rule-based trait, or a segment as baseline. Otherwise, your models will not run. </p> </p> </td> 
   <td colname="col3"> <p> <code> 4324 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> algoTypeId </code> </p> </td> 
   <td colname="col2"> <p>Algorithm ID. Currently, only ID 1 is available </p> </td> 
   <td colname="col3"> <p> <code> 1 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> lookBackPeriod </code> </p> </td> 
   <td colname="col2"> <p>Sets a time range for the model. Based on your input, the algorithm includes and evaluates data from the previous 30, 60, or 90 days. </p> </td> 
   <td colname="col3"> <p> <code> 60 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> status </code> </p> </td> 
   <td colname="col2"> <p>Activates or deactivates the model. Select <code> active </code> when creating a model </p> </td> 
   <td colname="col3"> <p> <code> active </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> excludedTraits </code> </p> </td> 
   <td colname="col2"> <p>Specify the SID for traits you want to exclude from modeling. Separate the traits with commas to exclude multiple traits. </p> </td> 
   <td colname="col3"> <p> <code> [110,111] </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Sample Request

```
{ 
 "name": "Interested in Footwear Model", 
 "description": "This model is created to find traits similar to Interested in Footwear", 
 "dataSources": [11212, 33421, 55431], 
 "sid": 4324, 
 "algoTypeId": 1, 
 "lookBackPeriod": 60, 
 "status": "ACTIVE", 
 "excludedTraits": [110,111] 
}
```

### Sample Response

```
{ 
 "algoModelId": 1394, 
 "pid": 1099, 
 "name": "Interested in Footwear Model" 
 "description": "This model is created to find traits similar to Interested in Footwear", 
 "algoTypeId": 1, 
 "intervalSeconds": 86400, 
 "lookBackPeriod": 60, 
 "crUID": 3, 
 "upUID": 3, 
 "status": 1, 
 "processingStatus": 0, 
 "createTime": 1346092322000, 
 "algoModelVersion": 0, 
 "dataSources": [11212, 33421, 55431], 
 "sid": 4324 
 "latestRunTS": 10000, 
 "baselineTraitType": 3, 
 "excludedTraits": [110, 111], 
 "updateTime": 1346092322000 
}
```

>[!MORE_LIKE_THIS]
>
>* [Model Builder](../../features/algorithmic-models/create-model.md#concept_25287B0C161F4BFCBCCFEB5CC6E613D0)

## Update a Model {#reference_96C246F8B89343D1A5120BAB1F42AFFF}

A `PUT` method that lets you revise the model's name, description, and status.

<!-- r_update_model.xml -->

### Request

` PUT https://api.demdex.com/v1/models/`*`<model-id>/`*

### Sample Request

All request values are required unless otherwise indicated. Model status settings include `active` and `inactive` only.

```
{ 
  "name" : "New name", 
  "description" : "Revised description", 
  "status" : "active", 
  "algoTypeId":1, 
  "dataSources":[3,4}, 
  "sid":8 
  "lookBackPeriod":90 
}
```

### Sample Response

```
{ 
    "algoModelId": 1394, 
    "pid": 1, 
    "name": "New name", 
    "description": "Revised description", 
    "algoTypeId": 1, 
    "intervalSeconds": 86400, 
    "lookBackPeriod": 30, 
    "crUID": 3, 
    "upUID": 3, 
    "status": 1, 
    "processingStatus": 0, 
    "createTime": 1346092322000, 
    "algoModelVersion": 0, 
    "dataSources": [3,4], 
    "sid": 8, 
    "latestRunTS": 10000, 
    "baselineTraitType": 3, 
    "updateTime": 1346092322000 
  }
```

## Delete a Model {#reference_43224194DF444077BEA71BCBC99EA162}

A `DELETE` method that removes a model from your collection.

<!-- r_delete_model.xml -->

### Request

` DELETE https://api.demdex.com/v1/models/`*`<model-id>`*

### Sample Response

Returns response code `204 No Content` if successful. Returns `400 Bad Request` if there are any active traits created with this model and returns those trait IDs in an array. Remove traits from the model (or delete them) before you delete a model.

## Delete Models {#reference_CD68FC107BB445F0946D337355B5482B}

A `POST` method that lets you bulk delete multiple models.

<!-- r_rest_api_bulk_delete_models.xml -->

### Request

`POST https://api.demdex.com/v1/models/bulk-delete/`

### Sample Request

In the request body, pass in a [!DNL JSON] array that includes the model IDs you want to delete.

```
[ 
   111, 
   222 
]
```

### Sample Response

Returns `204 No Content`.

## Return Properties for an Algorithm {#reference_6F3A6281F0224E4C879678B54155362E}

A `GET` method that returns ID, name, and description for the available algorithms. Currently, [!UICONTROL TraitWeight] (ID 1) is the only available algorithm.

<!-- r_get_algorithm.xml -->

### Request

`GET https://api.demdex.com/v1/algorithms/`

### Sample Response

A successful response returns response code `200 OK` and the list of algorithm IDs, name, and a brief description.

```
[
{
  "algoTypeId": 1,
  "name": "Trait Weight",
  "description": "Trait Weight"
}
]
```

## Return Properties for an Algorithm by ID {#reference_4A08BA06F91B4DF7B0CDC307FD9B6425}

A `GET` method that returns algorithm details (ID, name, and description) based on the passed in algorithm ID. Currently, [!UICONTROL TraitWeight] (ID 1) is the only available algorithm.

<!-- r_get_algorithm_by_id.xml -->

### Request

`GET https://api.demdex.com/v1/algorithms/`*`<algotype-id>/`*

### Sample Response

A successful response returns response code `200 OK` and the algorithm ID, name, and a brief description.

```
{ 
  "algoTypeId": 1, 
  "name": "TF-IDF", 
  "description": "TF-IDF" 
}
```

## Return Properties for all Models {#reference_7F78115A684B46039F3D103B955D7215}

A `GET` method that returns details about all your models.

<!-- r_get_all_models.xml -->

### Request

`GET https://api.demdex.com/v1/models/`

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
   <td colname="col1"> <code> page </code> </td> 
   <td colname="col2"> Returns results by page number. Numbering starts at 0. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> pageSize </code> </td> 
   <td colname="col2"> Sets the number of response results returned by the request (10 is default). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> sortBy </code> </td> 
   <td colname="col2"> Sorts and returns results according to the specified <span class="keyword"> JSON </span> property. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> descending </code> </td> 
   <td colname="col2"> Sorts and returns results in descending order. Ascending is default. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> search </code> </td> 
   <td colname="col2"> Returns results based on the specified string you want to use as a search parameter. For example, let's say you want to find results for all models that have the word "Test" in any of the value fields for that item. Your sample request could look like this: <p> <code> GET https://api.demdex.com/v1/models/?search=Test </code>. </p> <p>You can search on any value returned by a "get all" method. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Sample Request

```
GET https://api.demdex.com/v1/models/?page=1&pageSize=2&search=Test
```

### Sample Response

```
["total": 43, 
 "page": 1, 
 "pageSize": 2, 
 "list": [ 
   { 
      "algoModelId":698, 
      "pid":1099, 
      "name":"Test model", 
      "description":"For testing", 
      "algoTypeId":1, 
      "intervalSeconds":604800, 
      "lookBackPeriod":30, 
      "crUID":833, 
      "upUID":833, 
      "status":"INACTIVE", 
      "lastRunStatus":null, 
      "createTime":1427474087000, 
      "algoModelVersion":0, 
      "sid":1784945, 
      "lastRunTimestamp":null, 
      "baselineTraitType":"SEGMENT", 
      "lastSuccessfulRunTimestamp":null, 
      "updateTime":1427474947000 
   }, 
   { 
      "algoModelId":738, 
      "pid":1234, 
      "name":"Another Test Model", 
      "description":"For testing", 
      "algoTypeId":1, 
      "intervalSeconds":604800, 
      "lookBackPeriod":30, 
      "crUID":833, 
      "upUID":833, 
      "status":"ACTIVE", 
      "lastRunStatus":2, 
      "createTime":1422494342000, 
      "algoModelVersion":0, 
      "sid":916388, 
      "lastRunTimestamp":1431445691000, 
      "baselineTraitType":"SEGMENT", 
      "lastSuccessfulRunTimestamp":1431445691000, 
      "updateTime":1429133721000 
   } 
]
```

## Return Properties for a Model by ID {#reference_D45022005DF74328BE53E83229ED5902}

A `GET` method that returns algorithmic model details based on the passed in model ID.

<!-- r_get_models_id.xml -->

### Request

` GET https://api.demdex.com/v1/models/`*`<model-id>`*

### Sample Response

A successful request returns details for the model. An unsuccessful request throws an exception and related [error code](../../api/rest-api-main/aam-api-getting-started.md#reference_2AC89154A26E49A48E0DDD8DA520757F).

```
{ 
     "algoModelId": 16, 
     "pid": 1099, 
     "name": "newmodel78", 
     "description": "descriptions is in the name", 
     "algoTypeId": 1, 
     "intervalSeconds": 864000, 
     "lookBackPeriod": 30, 
     "crUID": 3, 
     "upUID": 3, 
     "status": 1, 
     "processingStatus": 0, 
     "createTime": 1344969143000, 
     "algoModelVersion": 0, 
     "dataSources": [ 
                       4 
                     ], 
     "sid": 8, 
     "latestRunTS": 10000, 
     "baselineTraitType": 3, 
     "updateTime": 1344969143000 
  }

```

## Return Properties for Your Most Accurate Traits {#reference_CD65B34911AD42A9AD3B92568607FFC3}

A `GET` method that returns a list of your most influential (accurate) traits.

<!-- r_get_traits_by_accuracy.xml -->

### Request

` GET https://api.demdex.com/v1/models/`*`<model-id>`*`/runs/latest/traits/`

### Optional Query Parameters

You can use these optional parameters with [!DNL API] methods that return *all* properties for an object. Set these options in the request string when passing that query in to the [!DNL API]. See also [Optional Parameters](../../api/rest-api-main/aam-api-getting-started.md#concept_BB1E73AE736F4F54830E6CAF28089608).  

<table id="table_0627C325E6FF4FE28ED8A0458C7ECB48"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> page </code> </td> 
   <td colname="col2"> Returns results by page number. Numbering starts at 0. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> pageSize </code> </td> 
   <td colname="col2"> Sets the number of response results returned by the request (10 is default). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> sortBy </code> </td> 
   <td colname="col2"> Sorts and returns results according to the specified <span class="keyword"> JSON </span> property. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> descending </code> </td> 
   <td colname="col2"> Sorts and returns results in descending order. Ascending is default. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> search </code> </td> 
   <td colname="col2"> Returns results based on the specified string you want to use as a search parameter. For example, let's say you want to find results for all models that have the word "Test" in any of the value fields for that item. Your sample request could look like this: <p> <code> GET https://api.demdex.com/v1/models/?search=Test </code>. </p> <p>You can search on any value returned by a "get all" method. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> folderId </code> </td> 
   <td colname="col2"> Returns all the IDs for traits inside the specified folder. Not available to all methods. </td> 
  </tr> 
 </tbody> 
</table>

### Sample Response

```
{ 
   "total": 2, 
   "page": 0, 
   "pageSize": 10, 
   "list": [ 
        { 
          "sid": 914, 
          "pid": 1, 
          "name": "sample rule", 
          "description": "hello world, i am your rule.. err", 
          "traitRuleVersion": 0, 
          "ttl": 0, 
          "crUID": 3, 
          "upUID": 3, 
          "createTime": 1346790825000, 
          "updateTime": 1346790825000, 
          "dataSourceId": 3, 
          "folderId": 10, 
          "traitType": "RULE_BASED_TRAIT", 
          "uniques7Day": 213930, 
          "uniques14Day": 415599, 
          "uniques30Day": 770717, 
          "uniques60Day": 9, 
          "count7Day": 657, 
          "count14Day": 626, 
          "count30Day": 5201,  
          "count60Day": 149, 
          "weight": 67, 
          "rank": 1 
        }, 
       { 
          "sid": 9, 
          "pid": 1, 
          "name": "trait2", 
          "description": "new trait 2", 
          "comments": "", 
          "integrationCode": "", 
          "traitRule": "", 
          "traitRuleVersion": 0, 
          "ttl": 0, 
          "crUID": 3, 
          "upUID": 3, 
          "createTime": 1344277873000, 
          "updateTime": 1344277873000, 
          "type": 1, 
          "dataSourceId": 1, 
          "folderId": 10, 
          "traitType": 3, 
          "uniques7Day": 113632, 
          "uniques14Day": 210777, 
          "uniques30Day": 393718, 
          "uniques60Day": 77, 
          "count7Day": 85502, 
          "count14Day": 977684, 
          "count30Day": 3755, 
          "count60Day": 18517223, 
          "weight": 37, 
          "rank": 2 
        } 
   ] 
}
```

## Return Accuracy and Reach Values for a Model {#reference_306F74B5E24347A19BFC54AB0D4FF169}

A `GET` method that returns accuracy and reach values for your algorithmic model.

<!-- r_get_accuracy_reach.xml -->

### Request

` GET https://api.demdex.com/v1/models/`*`<model-id>`*`/runs/latest/stats/`

### Sample Response

```
[ 
  { 
    "AccuracyValue": 0.12, 
    "ReachValue": 0 
   }, 
  { 
    "AccuracyValue": 0.18, 
    "ReachValue": 0 
   }, 
  { 
    "AccuracyValue": 0.19, 
    "ReachValue": 23232 
   }, 
  { 
    "AccuracyValue": 0.28, 
    "ReachValue": 33432 
   } 
]
```

## Return Processing Timestamp {#reference_CB6EAF4D9090428C9E6949A9AE14BD1E}

A `GET` method that returns an array of [!DNL UNIX] time stamps ([!DNL UTC]) of successful data runs for your model.

<!-- r_return_model_timestamp.xml -->

### Request

` GET https://api.demdex.com/v1/models/`*`<model-id>`*`/processing-history/`

### Sample Response

```
[ 
   102032939, 1223030409, 1346236373
]
```