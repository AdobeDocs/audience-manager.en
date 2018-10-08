---
description: Continue here for information about how to request a DCS response in a /event call. This section includes a response example and definitions for common data elements in a response.
seo-description: Continue here for information about how to request a DCS response in a /event call. This section includes a response example and definitions for common data elements in a response.
seo-title: Receive Data From the DCS
solution: Audience Manager
title: Receive Data From the DCS
uuid: 57cd5f08-0542-40d8-8e7d-1c3e0bbc1081
index: y
internal: n
snippet: y
translate: y
---

# Receive Data From the DCS

Continue here for information about how to request a DCS response in a /event call. This section includes a response example and definitions for common data elements in a response.

Before reviewing this content, see [Send Data to the DCS](../../../c_api/dcs-intro/dcs-event-calls/dcs-url-send.md#concept_9F6C569C1E444002ADF2A43516A9F284).

## DCS Response Parameters: A Review {#section_8D64FBDE90CC4B6582D3E45759392DE9}

Your [!UICONTROL DCS] request must include `d_rtbd=json` if you want to receive a response from the [!UICONTROL DCS]. The [!UICONTROL DCS] will not return data if you omit this parameter. A basic call to the [!UICONTROL DCS] to request data uses this syntax:

`http:// *`domain alias`*.demdex.net/event? *`key1`*= *`val1`*,& *`key2`*= *`val2`*&d_dst=1&d_rtbd=json&d_cb= *`callback`*`

## Sample Response {#section_E98B77488F8345B7BE5085F1DE38E05B}

Recall that from the [Send Data to the DCS](../../../c_api/dcs-intro/dcs-event-calls/dcs-url-send.md#concept_9F6C569C1E444002ADF2A43516A9F284) documentation, the fictional company Acme, Inc. made this call:

`http://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

As this call includes the required response parameter, the [!UICONTROL DCS] sent back the `JSON` object shown below. Yours may be similar or more complex.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Response Parameters {#section_7276ED2DFC754BA892C6F3E079494E63}

The table below lists and defines the more common parameters you may see in a response from the [!UICONTROL DCS]. This applies to event calls or other [!UICONTROL DCS] API queries that return data.

<table id="table_7D12E6454E7D4AADB05E829ABF7549E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> c</span> </p> </td> 
   <td colname="col2"> <p>A URL that has been set as a <a href="../../../c_features/destinations/manage-destinations.md#concept_51842672DFA943EA982B363E74D42DF8" format="dita" scope="local"> URL destination</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> cn</span> </p> </td> 
   <td colname="col2"> <p>The name or ID set in the cookie name field of a <a href="../../../c_features/destinations/manage-destinations.md#concept_2462AA1321984293A92CB174C41B3496" format="dita" scope="local"> cookie destination</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> cv</span> </p> </td> 
   <td colname="col2"> <p>The values sent to the destination defined by the <span class="codeph">"cn":"<span class="varname"> destinaton name</span>" parameter.</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> dcs_region</span> </p> </td> 
   <td colname="col2"> <p>The <a href="../../../c_api/dcs-intro/dcs-api-reference/dcs-regions.md#concept_01C1E017A6694D1EAF9BF65BFFA54091" format="dita" scope="local"> DCS region ID</a>. The region ID is required if you're making <a href="../../../c_api/dcs-intro/dcs-s2s/dcs-s2s-calls.md#concept_57686178E4174EE1A952E0E51BC8A52C" format="dita" scope="local"> server-to-server DCS calls</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> dests</span> </p> </td> 
   <td colname="col2"> <p>This object contains information for all URL destinations which are configured in the UI. This object’s list is dynamic based on the user’s actions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> dmn</span> </p> </td> 
   <td colname="col2"> <p>This is the domain specified in the <span class="wintitle"> Cookie Domain</span> field for a cookie destination. See <a href="../../../c_features/destinations/manage-destinations.md#concept_DEF2E47F31D44BDA936BBB45EA5B136D" format="dita" scope="local"> Optional Settings for Cookie Destinations</a>. </p> <p>For <span class="wintitle"> Server to Server</span> integrations we recommend using a domain like <span class="codeph"> aam-api.com</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> e</span> </p> </td> 
   <td colname="col2"> <p>The secure URL that has been set in a URL destination. 
     <draft-comment>
       LINK TO URL DESTINATION 
     </draft-comment> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> stuff</span> </p> </td> 
   <td colname="col2"> <p>This object contains information for all <span class="wintitle"> Cookie</span> destinations. This object’s list is dynamic based on the user’s actions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> tid</span> </p> </td> 
   <td colname="col2"> <p>Transaction ID, which is a unique 12-character ID used for debugging purposes. Each /event call to the <span class="wintitle"> DCS</span> receives a tid that you can reference in support enquiries for a better and faster response. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> ttl</span> </p> </td> 
   <td colname="col2"> <p>The cookie time-to-live value in days. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> u</span> and <span class="codeph"> uuid</span> </p> </td> 
   <td colname="col2"> <p>Unique User ID assigned by <span class="keyword"> Audience Manager.</span> This is required if you're making <a href="../../../c_api/dcs-intro/dcs-s2s/dcs-s2s-calls.md#concept_57686178E4174EE1A952E0E51BC8A52C" format="dita" scope="local"> server-to-server DCS calls</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> y</span> </p> </td> 
   <td colname="col2"> <p>Destination type, <span class="keyword"> iFrame</span> (<span class="codeph"> iframe</span>) or image (<span class="codeph"> img</span>). </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [Key-Value Prefixes and Variables Supported by the DCS](dcs-keys.md#concept_5ACDD7D09D0441A6AC26F7D345CD19D5)
