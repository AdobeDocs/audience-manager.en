---
description: Exchange and synchronize user IDs with Audience Manager from devices or browsers that do not use or accept persistent storage mechanisms, such as third-party cookies.
seo-description: Exchange and synchronize user IDs with Audience Manager from devices or browsers that do not use or accept persistent storage mechanisms, such as third-party cookies.
seo-title: Declared ID Targeting
solution: Audience Manager
title: Declared ID Targeting
uuid: c92ea71f-3dfb-4c8a-ba42-25a48b267eb8
index: y
internal: n
snippet: y
translate: y
---

# Declared ID Targeting

This section contains the following information: 

* [ Purpose of Declared ID Targeting](../../c_features/c_declared_id/declared_id_about.md#section_2127B48E659E4D3AB03C698EBE9B589F)
* [ Opt-out Calls](../../c_features/c_declared_id/declared_id_about.md#section_0C8341CD240945829F87D652DDF70BEC)
* [ Declared ID Opt-Out Examples](../../c_features/c_declared_id/declared_id_about.md#section_C0370B5573CD49408E35356D051B2AD8)

## Purpose of Declared ID Targeting {#section_2127B48E659E4D3AB03C698EBE9B589F}

Some browsers, and most mobile devices, do not accept third-party cookies. This makes it difficult to retain information about site visitors or assign persistent IDs. To resolve this issue, Audience Manager uses DIL to let you pass in declared IDs on an event call. Also, a declared ID can act as a universal ID that applies to the same user across all the solutions in the [!DNL  Experience Cloud]. The following table describes the ID targeting/matching process: 

<table id="table_5D59CD5AF70B44C3B45D279283D4691F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Process </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Event Call</b> </td> 
   <td colname="col2"> <p>To work, you need DIL and the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID service</a> code on the page. DIL gets declared IDs from the <span class="codeph"> setVisitorID</span> function provided by the Experience Cloud ID service and passes that on to <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Match ID</b> </td> 
   <td colname="col2"> <p>Audience Manager attempts to match the client and visitor ID with a corresponding ID in our system. If a matching ID does not exist, Audience Manager creates a new ID and associates it with the client and visitor ID. </p> <p> <p>Note:  The most recent mapping is used if your ID maps to more than one Audience Manager ID. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Return ID</b> </td> 
   <td colname="col2"> <p>Audience Manager writes its synchronized ID to a first-party cookie (or other addressable storage space) in the client domain or application. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Subsequent Event Calls</b> </td> 
   <td colname="col2"> <p>Additional event calls read the Audience Manager ID from the client's domain and send that to Audience Manager. </p> </td> 
  </tr> 
 </tbody> 
</table>

To get started, you need to configure the [!DNL  Experience Cloud] ID service and DIL across the pages on your site that you want to use for data collection. See [ DIL create](../../c_api/c_dil/c_dil_overview/r_dil_create/r_dil_create.md#reference_F87131F6C1CC4ECCA064B24B91710FD4) and [ Declared ID Variables](../../c_features/c_declared_id/r_dil_declared_id_vars.md#reference_F697F0D53E56430D95EC0C408B767F80). 

## Opt-out Calls {#section_0C8341CD240945829F87D652DDF70BEC}

The declared ID process honors site visitor preferences to opt-out of Audience Manager targeting by your website. When Audience Manager receives an opt-out request, the JSON returned by the DCS contains the error code 171, with the message "Encountered opt out tag", instead of the Audience Manager user ID. 


* Audience Manager can pass in a declared ID opt-out alongside an Audience Manager UUID in the URL.
* The declared ID opt-out is stored in the Profile Cache Server (PCS) on a per-partner basis. There is no platform-level opt-out using declared IDs. Additionally, Audience Manager opts the user out from that particular region on the edge (the opt-out does not cross DCS regions).


See [ Data Privacy](../../c_am_overview_intro/c_data_security_and_privacy/data_privacy.md#concept_C1E36C6BF4C0461F9D31687E275DC46A) for more information about opting-out of data collection. 

## Declared ID Opt-Out Examples {#section_C0370B5573CD49408E35356D051B2AD8}

You can make a declared ID opt-out requests with the ` d_cid` and ` d_cid_ic` key-value pairs. The legacy parameters like ` d_dpid` and ` d_dpuuid` still work, but are considered deprecated. See [ CID Replaces DPID and DPUUID](../../c_reference/cid.md#concept_E9DE716F22E8491AB27057DB92B79081). In the examples, *italics* indicates a variable placeholder. 

**Opt-Outs With CID and CID_IC** 

For a description and syntax, see[ URL Variables and Syntax for Declared IDs](../../c_features/c_declared_id/c_declared_id_var_syntax.md#concept_22E2210AA6604B83B46F5E0CD5504A51). 



<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opt-Out Using </th> 
   <th colname="col2" class="entry"> Code Sample </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>A data provider ID and user ID. </p> </td> 
   <td colname="col2"> <p> <span class="codeph">http://<span class="varname"> domain name</span>/demoptout.jpg?d_cid=123%01987...</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>An integration code and user ID. </p> </td> 
   <td colname="col2"> <p> <span class="codeph">http://<span class="varname"> domain name</span>/demoptout?d_cid_ic=456%01321...</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Multiple <span class="codeph"> d_cid</span> and <span class="codeph"> d_cid_ic</span> key-value pairs. </p> </td> 
   <td colname="col2"> <p> <span class="codeph">http://<span class="varname"> domain name</span>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321...</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Opt-Outs With DPID, DPUUID, and UUID (Deprecated)** 

These methods still work but are considered deprecated. This information is provided for legacy purposes and reference. Legacy opt-outs include: 



<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opt-Out (Deprecated) </th> 
   <th colname="col2" class="entry"> Code Sample </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> d_uuid</span> only </p> </td> 
   <td colname="col2"> <p> <span class="codeph">http://domain/demoptout.jpg?d_uuid=AAM ID</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Partner level opt-out </p> </td> 
   <td colname="col2"> <p> <span class="codeph">http:///demoptout.jpg?d_dpuuid=user ID&amp;d_dpid=data provider ID</span> </p> <p>A partner level opt-out gets stored for the latest mapping of this <span class="codeph"> dpid</span> + <span class="codeph"> dpuuid</span> pair to an AAM UUID. If there is no previously existing mapping, Audience Manager checks whether the request contains an AAM UUID in the cookie, and if it does, uses that for storing the opt-out. Otherwise, Audience Manager generates a new AAM UUID and stores the opt-out under it. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> d_dpuuid</span> + <span class="codeph"> d_dpid</span> and explicit <span class="codeph"> d_uuid</span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph">http://domain/demoptout.jpg?d_uuid=user ID&amp;d_dpuuid=data provider's user ID&amp;<span class="varname"> d_dpid=data provider ID</span></span> </p> <p> <span class="codeph"> d_uuid</span> always takes precedence. If the <span class="codeph"> dpid</span> + <span class="codeph"> dpuuid</span> combination maps to another AAM UUID, the opt-out is stored under the AAM UUID passed in the request (<span class="codeph"> d_uuid</span>). </p> </td> 
  </tr> 
 </tbody> 
</table>

