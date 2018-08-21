---
description: Start here for information about making /event calls to the DCS. This section includes information about call syntax, parameters, formatting, and a request example.
seo-description: Start here for information about making /event calls to the DCS. This section includes information about call syntax, parameters, formatting, and a request example.
seo-title: Send Data to the DCS
solution: Audience Manager
title: Send Data to the DCS
uuid: 333053d4-b923-4fbc-ab37-b2aac8d37496
index: y
internal: n
snippet: y
translate: y
---

# Send Data to the DCS

Contents: 


<ul class="simplelist"> 
 <li> <a href="../../../c_api/dcs-intro/dcs-event-calls/dcs-url-send.md#section_9D6FDD2547174B03B89DBFECBFE53008" format="dita" scope="local"> Call Syntax </a> </li> 
 <li> <a href="../../../c_api/dcs-intro/dcs-event-calls/dcs-url-send.md#section_B6F540658D394E24B8B3A649D1AAEA15" format="dita" scope="local"> Call Parameters </a> </li> 
 <li> <a href="../../../c_api/dcs-intro/dcs-event-calls/dcs-url-send.md#section_6ADCBC45C4A64B09A216AC0882162D99" format="dita" scope="local"> Sample Call </a> </li> 
 <li> <a href="../../../c_api/dcs-intro/dcs-event-calls/dcs-url-send.md#section_36E9E3B86F4C42CDAED4B9B69E317F82" format="dita" scope="local"> Next Steps </a> </li> 
</ul>




>[!NOTE] {type="note"}
>
>In the code and examples,*italics* represents a variable placeholder. Substitute a real value for the placeholder when you send data to the DCS with this method. 



## Call Syntax {#section_9D6FDD2547174B03B89DBFECBFE53008}

A basic URL string that sends data to the DCS uses the syntax shown below. 

` http:// *` domain alias`*.demdex.net/event? *` key1`*= *` val1`*,& *` key2`*= *` val2`*&d_dst=1&d_rtbd=json&d_cb= *` callback`*` 


>[!NOTE]
>
>You can also send data to the DCS by using the POST method. The call syntax is described in[ DCS API Methods ](../../../c_api/dcs-intro/dcs-api-reference/dcs-api-methods.md#concept_084D7A3E30C94145B3BAE305D30640B7). 



## Call Parameters {#section_B6F540658D394E24B8B3A649D1AAEA15}

The following table defines the basic components of a simple DCS call. 



<table id="table_5F6A5B324EB848168543386516FBF384"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Component </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> <span class="varname"> domain alias </span>.demdex.net </span> </p> </td> 
   <td colname="col2"> <p>This part of the call contains: </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Your domain alias assigned by <span class="keyword"> Audience Manager </span> (e.g., <span class="codeph"> my_domain.demdex.net </span>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">The destination domain, which is always <span class="codeph"> demdex.net </span>. See <a href="../../../c_reference/demdex-calls.md#concept_77B3D5A068AE413FA78D190D65AD799F" format="dita" scope="local"> Understanding Calls to the Demdex Domain </a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> /event? </span> </p> </td> 
   <td colname="col2"> <p>This part of the call: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identifies the call as an event call. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Defines the start of the URL string that contains the data you want to send to the DCS. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> <span class="varname"> key </span> </span> </p> </td> 
   <td colname="col2"> <p>A unique identifier in the key-value pair. </p> <p>These key-value pairs use a specific prefix to identify the type of data you're sending to the DCS. For more information, see <a href="../../../c_api/dcs-intro/dcs-api-reference/dcs-keys.md#concept_5ACDD7D09D0441A6AC26F7D345CD19D5" format="dita" scope="local"> Supported Attributes for DCS API Calls </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> <span class="varname"> val </span> </span> </p> </td> 
   <td colname="col2"> <p>A variable value that belongs to a set defined by a key in the key-value pair. </p> <p>When working with values: </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">Enclose string data in double quotes (e.g., <span class="codeph"> <span class="codeph"> age="41 to 55" </span>) </span>. </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">You can pass multiple keys in on a single value (e.g., <span class="codeph"> <span class="varname"> key </span>= <span class="varname"> val1,val2,val3 </span> </span>). </li> 
     </ul> </p> <p>See <a href="../../../c_api/dcs-intro/dcs-api-reference/dcs-key-format.md#reference_D20E71D7090F4F2690F6DFBD5389B000" format="dita" scope="local"> Formatting Key-Value Pairs in DCS Calls </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <span class="codeph"> d_dst=1 </span> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <span class="codeph"> d_rtbd=json </span> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <span class="codeph"> d_cb= <span class="varname"> callback </span> </span> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Optional response parameters. </p> <p> None of these are required to send data to the DCS. However, if you want the DCS to return a response, you must include <span class="codeph"> d_rtbd=json </span> in your request. </p> <p>See <a href="../../../c_api/dcs-intro/dcs-api-reference/dcs-keys.md#section_B5B16D42E2004AF3ABCE25FFFEB0FF28" format="dita" scope="local"> d_ Key-Value Pairs Defined </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>


## Sample Call {#section_6ADCBC45C4A64B09A216AC0882162D99}

This example shows the fictional company Acme, Inc. sending data to the DCS via an HTTP call. Note that this call includes the optional parameters ` d_dst=1`, ` d_rtbd=json`, and ` d_cb= *` callback`*`. These indicate that Acme wants to receive a JSON response from the DCS with a call back function. Remember, this is just an example. Do not cut and paste this code. 

` http://acme_aam_domain.demdex.net/event?videoTypeID=2&amp;data=moarData&amp;d_dst=1&amp;d_rtbd=json&amp;d_cb=acme_callback` 

## Next Steps {#section_36E9E3B86F4C42CDAED4B9B69E317F82}

Now that you're familiar with sending data to the DCS, it's time to look at how to get data back from the DCS and parse that information. See [ Receive Data From the DCS ](../../../c_api/dcs-intro/dcs-event-calls/dcs-url-receive.md#concept_1219EE35E91548F899E2FFE60C107841). 
>[!MORE_LIKE_THIS]
>
>* [ Key-Value Pairs Explained ](c_key_value_explained.md#concept_E4236E003076483AA939791FE2492B49)
