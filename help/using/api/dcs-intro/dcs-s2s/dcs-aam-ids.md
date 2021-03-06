---
description: This section describes how to parse a DCS response to retrieve the visitor and region IDs required to make real-time calls to the DCS.
seo-description: This section describes how to parse a DCS response to retrieve the visitor and region IDs required to make real-time calls to the DCS.
seo-title: Get User IDs and Regions From a DCS Response
solution: Audience Manager
title: Get User IDs and Regions From a DCS Response
uuid: 08036045-3b26-4d40-8e94-7d0884048683
feature: DCS
exl-id: 3c0c5e57-2d59-4938-9bbd-761495142c31
---
# Get User IDs and Regions From a DCS Response {#get-user-ids-and-regions-from-a-dcs-response} 

This section describes how to parse a [!DNL DCS] response to retrieve the visitor and region IDs required to make real-time calls to the [!DNL DCS].

## User and Region IDs {#user-region-ids}

A [!DNL DCS] response contains data about your site visitors. You need the visitor and region ID before you can make server-to-server calls to the [!DNL DCS]. 

* The user ID is required to identify and associate data with a particular visitor.
* The region ID is required because it is tied to a regional server name, which you need to send data to the [!DNL DCS]. The [!DNL DCS] stores information in data centers that are geographically closest to site visitors. See [DCS Region IDs, Locations, and Host Names](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

These parameters are described below. Code in *italics* represents a variable placeholder.

<table id="table_822C02D5978348DCB7153001882D397C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Data type </th> 
   <th colname="col3" class="entry"> Example </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code>"uuid": <i>user ID</i></code></span> </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p> <code> "uuid":"123456789"</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>"dcs_region":<i>region ID</i></code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p> <code> "dcs_region":9</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sample Response {#sample-response}

This simple response shows the `UUID` and region `ID`. Note, this is sample data only. Your log files may be longer and more complex.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Next Steps {#next-steps}

Once you have the user ID and regional server name, you can start sending and receiving [!DNL DCS] data. See [Making DCS API Calls](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
