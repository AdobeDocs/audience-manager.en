---
seo-title: Making Server-to-Server DCS API Calls
solution: Audience Manager
title: Making Server-to-Server DCS API Calls
uuid: bdfe3430-e27f-4a5c-88d9-ae164d28f601
index: y
internal: n
snippet: y
---

# Making Server-to-Server DCS API Calls{#making-server-to-server-dcs-api-calls}

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. Substitute a real value for the placeholder when you server-to-server calls to the [!UICONTROL DCS].

## Call Syntax and Example {#section_579774FA81764D1EA209BCEA8C0536E9}

A basic server-to-server request that sends data to the [!UICONTROL DCS] uses the syntax shown below.

`"Host: *`domain alias`*.demdex.net" "https:// *`DCS host name`*.demdex.net/event?d_rtbd=json&d_jsonv=1& d_uuid= *`user ID`*`

A sample call looks similar to the following example.

`"Host:foo.demdex.net" "https://usw2.demdex.net/event?d_rtbd=json&d_jsonv=1& d_uuid=123456789"`

## Call Parameters {#section_B34BDE82D2E14CD4B59DE4B7AFDCDA27}

<table id="table_3AF4466009B64F0C9CBE7904A4096E0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> <span class="varname"> domain alias</span>.demdex.net</span> </p> </td> 
   <td colname="col2"> <p>This part of the call contains: </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Your domain alias assigned by <span class="keyword"> Audience Manager</span> (e.g., <span class="codeph"> my_domain.demdex.net</span>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">The destination domain, which is always <span class="codeph"> demdex.net</span>. See <a href="../../../reference/demdex-calls.md#concept_77B3D5A068AE413FA78D190D65AD799F"> Understanding Calls to the Demdex Domain</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> <span class="varname"> DCS host name</span>.demdex.net</span> </p> </td> 
   <td colname="col2"> <p>The http header host parameter which shows the name of the regional <span class="wintitle"> DCS</span> server. The host name is tied to a region ID, which is why you need this before making these types of calls. See <a href="../../../c-api/dcs-intro/dcs-api-reference/dcs-regions.md#concept_01C1E017A6694D1EAF9BF65BFFA54091"> DCS Region IDs, Locations, and Host Names</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph"> /event?</span> </p> </td> 
   <td colname="col2"> <p>This part of the call: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identifies the call as an event call. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Defines the start of the URL string that contains the data you want to send to the DCS. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph">d_uuid=<span class="varname"> Audience Manager user ID</span></span> </p> </td> 
   <td colname="col2"> <p>This is the unique user ID key that holds the <span class="keyword"> Audience Manager</span> user ID value in a key-value pair. </p> <p>Use <span class="codeph"> d_uuid</span> if you're passing in the <span class="keyword"> Audience Manager</span> user ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="codeph">d_mid=<span class="varname"> Experience Cloud user ID</span></span> </p> </td> 
   <td colname="col2"> <p>This is the unique user ID key that holds the <span class="keyword"> Experience Cloud</span> user ID value in a key-value pair. See also <a href="../../../c-api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#section_F28F94780FEC4918B37B62AC9A64AF23"> Get the User ID from the ID Service Cookie</a>. </p> <p>Use <span class="codeph"> d_mid</span> if you're passing in a <span class="keyword"> Experience Cloud</span> ID captured from the <span class="keyword"> Experience Cloud</span> ID service. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><span class="codeph"> d_dst=1</span> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><span class="codeph"> d_rtbd=json</span> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><span class="codeph">d_cb=<span class="varname"> callback</span></span> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Optional response parameters. </p> <p> None of these are required to send data to the <span class="wintitle"> DCS</span>. However, if you want the <span class="wintitle"> DCS</span> to return a response, you must include <span class="codeph"> d_rtbd=json</span> in your request. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sample Response {#section_0746601B5975435687F88507E360CF17}

See [Receive Data From the DCS](../../../c-api/dcs-intro/dcs-event-calls/dcs-url-receive.md#concept_1219EE35E91548F899E2FFE60C107841). 
