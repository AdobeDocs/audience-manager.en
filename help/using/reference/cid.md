---
description: Update your code to use d_cid or d_cid_ic instead of d_dpid and d_dpuuid. The DPID and DPUUID variables will continue to work, but you should consider them deprecated. This includes DPID and DPUUID variants without the d_ prefix.
seo-description: Update your code to use d_cid or d_cid_ic instead of d_dpid and d_dpuuid. The DPID and DPUUID variables will continue to work, but you should consider them deprecated. This includes DPID and DPUUID variants without the d_ prefix.
seo-title: CID Replaces DPID and DPUUID
solution: Audience Manager
title: CID Replaces DPID and DPUUID
uuid: 3641eac5-b19e-45d5-bc1c-35a23b4bab8c
index: y
internal: n
snippet: y
---

# CID Replaces DPID and DPUUID{#cid-replaces-dpid-and-dpuuid}

Update your code to use d_cid or d_cid_ic instead of d_dpid and d_dpuuid. The DPID and DPUUID variables will continue to work, but you should consider them deprecated. This includes DPID and DPUUID variants without the d_ prefix.

Contents:

<ul class="simplelist"> 
 <li> <a href="../reference/cid.md#section_8C6B7D86771448A08EC14F527E6687F5"> DPID and DPUUID: A Review </a> </li> 
 <li> <a href="../reference/cid.md#section_CCFCB503887044FE9E87024943CE939A"> CID and CID_IC: About </a> </li> 
 <li><a href="../reference/cid.md#section_D5D6F182DEFB4C7D9F2274BE63C6B2D4"> Important Considerations for Development Teams</a> </li> 
</ul>

## DPID and DPUUID: A Review {#section_8C6B7D86771448A08EC14F527E6687F5}

The DPID and the DPUUID are key-value pairs that contain a data provider ID and a user ID. These key-value pairs link provider IDs to user IDs. They send in data during event calls, for inbound synchronization events, and for ID calls. Without them, [!DNL Audience Manager], and other services or features, would not have a way to match and synchronize IDs. These variables are sometimes expressed with or without the `d_` prefix as shown below. Note, in the code, *italics* indicates a variable placeholder.

<table id="table_932B4416AE1E44E4A1E98D779D3B1ED5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Syntax </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Data Provider ID (DPID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_0567D39DCE784C20A81EC0845C7B1C6B"> 
     <li id="li_DDD8C18266314987A7C802918F4892A8"> <span class="codeph">d_dpid=<span class="varname"> data provider ID</span></span> </li> 
     <li id="li_80185558932E416698ABD71158303EA8"> <span class="codeph">dpid=<span class="varname"> data provider ID</span></span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Data Provider Unique User ID (DPUUID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EA7F769523B142CE8FF5886E5CDFF2D9"> 
     <li id="li_C984E2FF0A83495880BB87C610FA3F79"> <span class="codeph">d_dpuuid=<span class="varname"> data provider unique user ID</span></span> </li> 
     <li id="li_DCFFAC995DCC49F489ACEFD97A06F877"> <span class="codeph">dpuuid=<span class="varname"> data provider unique user ID</span></span> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

These key-value pairs still work, but they are deprecated. You should update your code to use CID or CID_IC instead.

## CID and CID_IC: About {#section_CCFCB503887044FE9E87024943CE939A}

The CID and CID_IC key-value pairs replace DPID and DPUUID. They provide the same functions as the DPID and DPUUID, but are more efficient because they include the data provider ID (or integration code) and user ID in a single key-value pair. In each key-value pair:

* The = symbol separates the key from its related values. 
* The non-printing ASCII character %01 separates the values.

`d_cid` and `d_cid_ic` use the syntax shown below. Note, in the code, *italics* indicates a variable placeholder.

<table id="table_0C8A4F8FDBC84416B4EB476F67BCFA8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Syntax </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Customer ID (CID) </p> </td> 
   <td colname="col2"> <p> <span class="codeph">d_cid=<span class="varname"> data provider ID</span>%01<span class="varname"> user ID</span></span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Customer ID Integration Code (CID_IC) </p> </td> 
   <td colname="col2"> <p> <span class="codeph">d_cid_ic=<span class="varname"> integration code</span>%01<span class="varname"> user ID</span></span> </p> <p> An <span class="term"> integration code</span> is an alternate ID you can use instead of the Data Source ID, assigned by <span class="keyword"> Audience Manager</span>. See <a href="../c-features/manage-datasources.md#concept_3B7696B3EC77416492D3B99EBD79EA44"> Create a Data Source</a> if you need to configure an integration code. </p> </td> 
  </tr> 
 </tbody> 
</table>

See also, [URL Variables and Syntax for Declared IDs](../c-features/declared-ids.md#concept_22E2210AA6604B83B46F5E0CD5504A51).

>[!NOTE]
>
>You can use integration codes for your own data sources and for global [shared data sources](../c-features/datasources-list-and-settings.md#reference_A87B381067E04C26A426514AF3B64E64), which you have access to. For example, you can use integration codes when working with mobile identifiers data sources. Use the following integration codes, exactly as specified below:

* **DSID_20914** for GAID, representing devices running the Android operating system. 
* **DSID_20915** for IDFA, representing devices running the iOS operating system.

**Examples**

The following table provides examples by event type.  

<table id="table_097A58CCD6E64C4DB0652271A4F31AE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Event Type </th> 
   <th colname="col2" class="entry"> Example </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Event </p> </td> 
   <td colname="col2"> 
    <ul id="ul_6EAB4188C6954512A28D1A8328794BCB"> 
     <li id="li_344AAEF1622343489E2AD6E2929CEA98">New: <span class="codeph"> .../event?d_cid=123%01987...</span> </li> 
     <li id="li_B673C1BA5AD24C46AB8F8232EF89CE89">Deprecated: <span class="codeph"> .../event?d_dpid=123&amp;d_dpuuid=987...</span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Inbound Synchronization (IBS) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_78270745CBC2469B8CA9EDB7032B8F92"> 
     <li id="li_8C4620A04504442185F013F74E6B0647">New: <span class="codeph"> .../ibs:d_cid=123%01987...</span> </li> 
     <li id="li_2A8F761C76334C1BB097CF1A9D7E8429">Deprecated: <span class="codeph"> .../ibs:d_dpid=123&amp;d_dpuuid=987</span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Generate Audience Manager UUID (ID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EAA764DCFF7244F69ABF67ACEE13E579"> 
     <li id="li_18467A531FAF454A881CBD157BBFD6D2">New: <span class="codeph"> .../id?d_cid=123%01987...</span> </li> 
     <li id="li_433C33F7BC284362AC7CC3C9DC0BF471">Deprecated: <span class="codeph"> .../id?d_dpid=123&amp;d_dpuuid=987</span> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Each call can also include multiple `d_cid` and `d_cid_ic` key value pairs like this:

```
...?d_cid=123%01456&d_cid=123%01789&d_cid_ic=543%01333...
```

## Important Considerations for Development Teams {#section_D5D6F182DEFB4C7D9F2274BE63C6B2D4}

<table id="table_5DD068FAE68A42CDB49B6C064706802A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Item </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>URL encoding </p> </td> 
   <td colname="col2"> <p>Your development teams <i>must</i> apply URL encoding to the following variables in the CID key-value pair: </p> <p> 
     <ul id="ul_66DCB63C60914057B2BE21F49D9A36CA"> 
      <li id="li_6D82B4DB40BB4BB0B8FAF5841577FAAC"><span class="codeph"> user ID</span> <span class="codeph"> (dpuuid)</span> </li> 
      <li id="li_D2F94B07B0D84B09A5CDFA48518DDD62"><span class="codeph"> integration code</span> </li> 
     </ul> </p> <p> <p>Note: You must URL encode the user ID and integration code <i>before</i> concatenating them into a string. This is because the ASCII character %01 that separates the two variables must not be captured in the URL encoding. </p> </p> <p>URL encoding assures that your user IDs and integration codes that contain reserved or unsafe characters such as, but not limited to, + or = are transmitted correctly to our servers. </p> <p>Use the <a href="https://www.w3schools.com/tags/ref_urlencode.asp" format="https" scope="external"> ASCII encoding table</a> for reference. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Using integration codes for global shared data sources </p> </td> 
   <td colname="col2"> <p>You can use integration codes for your own data sources and for global <a href="../c-features/datasources-list-and-settings.md#reference_A87B381067E04C26A426514AF3B64E64"> shared data sources</a>, which you have access to. For example, you can use integration codes when working with mobile identifiers data sources. Use the following integration codes, exactly as specified below: </p> <p> 
     <ul id="ul_B306EE96A3BD4CE982E113D5E23826CF"> 
      <li id="li_3340C7AFA9AB4105A2CCF3E476EC7552"> <b>DSID_20914</b> for GAID, representing devices running the Android operating system. </li> 
      <li id="li_779D9F08021043FCB233A0ABF5160C76"> <b>DSID_20915</b> for IDFA, representing devices running the iOS operating system. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

