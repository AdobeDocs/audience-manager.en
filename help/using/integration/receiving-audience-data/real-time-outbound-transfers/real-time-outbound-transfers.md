---
description: The outbound real-time data transfer process returns user data as a series of JSON objects passed in with a POST method.
seo-description: The outbound real-time data transfer process returns user data as a series of JSON objects passed in with a POST method.
seo-title: Real-Time Outbound Data Transfers
solution: Audience Manager
title: Real-Time Outbound Data Transfers
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
---

# Real-Time Outbound Data Transfers {#real-time-outbound-data-transfers}

The outbound real-time data transfer process returns user data as a series of JSON objects passed in with a POST method.

<!-- c_outbound_json.xml -->

## Recommendations

To use this method, we recommend that your data partner:

* Accepts data in [!DNL JSON] format.
* Provides a URL that can be used by the `POST` call to return data.
* Accepts secure `HTTPS` data transfers. [!DNL Audience Manager] will not send this file with the unsecure `HTTP` protocol.

## Frequency

This data transfer method can send data in near real-time as users qualify for segments. Additionally, this method can send batches of offline or onboarded data as frequently as every 24-hours.

## Required Responses

By default, the recipient server must return the `200 OK` code to indicate successful receipt. Other codes will be interpreted as failures. This response is expected within 3000 milliseconds. In response to a failure, [!DNL Audience Manager] will make 1 retry attempt only.

## Parameters

The following table defines the elements in the returned [!DNL JSON] data file.  

<table id="table_68475F9D01ED4A44B5909234114AEDE2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Data Type </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"><span class="varname"> ProcessTime</span></span> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>Time when the request was executed. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><span class="codeph"><span class="varname"> User_DPID</span></span> </td> 
   <td colname="col2"> <p>Integer </p> </td> 
   <td colname="col3"> <p>An ID that indicates if the file contains Android or iOS IDs. Uses the following ID values: </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Android IDs (GAID): <span class="codeph"> 20914</span> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">iOS IDs (IDFA): <span class="codeph"> 20915</span> </li> 
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><span class="codeph"><span class="varname"> Client_ID</span></span> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>Client ID used by the system you're sending data to. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><span class="codeph"><span class="varname"> AAM_Destination_ID</span></span> </td> 
   <td colname="col2"> <p>Integer </p> </td> 
   <td colname="col3"> <p>The ID assigned to you by your destination partner. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><span class="codeph"><span class="varname"> User_count</span></span> </td> 
   <td colname="col2"> <p>Integer </p> </td> 
   <td colname="col3"> <p>Total number of users in the <span class="codeph"> POST</span> request. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><span class="codeph"><span class="varname"> Users</span></span> </td> 
   <td colname="col2"> <p>Array </p> </td> 
   <td colname="col3"> <p>An array of user objects. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><span class="codeph"><span class="varname"> AAM_UUID</span></span> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>The <span class="keyword"> Audience Manager</span> UUID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><span class="codeph"><span class="varname"> DataPartner_UUID</span></span> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>Data partner UUID. Leave blank if your data partner does not have a UUID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><span class="codeph"><span class="varname"> AAM_Regions</span></span> </td> 
   <td colname="col2"> Array </td> 
   <td colname="col3"> The <span class="keyword"> Audience Manager</span> region ID where we've seen this device. For instance, if the device had some activity in Paris (Europe), the region ID would be <span class="codeph"> 6</span>. See <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md#concept_01C1E017A6694D1EAF9BF65BFFA54091"> DCS Region IDs, Locations, and Host Names</a>. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><span class="codeph"><span class="varname"> Segments</span></span> </td> 
   <td colname="col2"> <p>Array </p> </td> 
   <td colname="col3"> <p>An array of segment objects. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><span class="codeph"><span class="varname"> Segment_ID</span></span> </td> 
   <td colname="col2"> <p>Integer </p> </td> 
   <td colname="col3"> <p>The segment ID destination mapping. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><span class="codeph"><span class="varname"> Status</span></span> </td> 
   <td colname="col2"> <p>Integer </p> </td> 
   <td colname="col3"> <p>Defines the status of a user in the segment. Accepts the following: </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><span class="codeph"> 1</span>: Active (default) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><span class="codeph"> 0</span>: Inactive, opted-out, or unsegmented. </li> 
    </ul> <p>Users are unsegmented when they are: </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">Removed from a segment based on the segment rule. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">Removed from a segment based on the segment's <a href="../../../features/traits/segment-ttl-explained.md#concept_2F85D4E738754EF387328A9754E125B3"> time-to-live interval</a>. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">Moved to an inactive state if they have not been seen for the last 120-days. </li> 
    </ul> <p>All partner IDs that are synced to an <span class="keyword"> Audience Manager</span> ID will receive the <span class="codeph"> "Status":"0"</span> flag when a user is unsegmented. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><span class="codeph"><span class="varname"> DateTime</span></span> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>Time that a site visitor qualified for the trait. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Security

You can secure your real-time outbound data transfer process by [encrypting HTTP requests](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#concept_1E0F79C0142B4CA38CE03B173022A31C) with private keys or by having [!DNL Audience Manager] authenticate through the [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md#concept_CA17FEF807BE48D8BAC17243234E50A1) protocol.

## Code Sample

A real-time data response can look similar to the following:

```js
{
"ProcessTime": "Wed Jul 27 16:17:42 UTC 2016",
"User_DPID": "12345",
"Client_ID": "74323",
"AAM_Destination_Id": "423",
"User_count": "2",
"Users": [{  
   "AAM_UUID": "19393572368547369350319949416899715727",
   "DataPartner_UUID": "4250948725049857",
   "Segments": [{
            "Segment_ID": "14356",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         },
         {
            "Segment_ID": "12176",
            "Status": "0",  
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         }
      ]
   },
   {
   "AAM_UUID": "0578240750487542456854736923319946899715232",
   "DataPartner_UUID": "848457757347734",
   "Segments": [{
            "Segment_ID": "10329",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:21 UTC 2016"
         },
         {
            "Segment_ID": "23954",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:21 UTC 2016"
        }]
    }]
}

```