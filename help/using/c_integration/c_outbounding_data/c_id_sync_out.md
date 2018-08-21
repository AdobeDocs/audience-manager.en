---
description: Describes the syntax and parameters used in the initial HTTP call to synchronize user IDs between Audience Manager and a third-party data provider. Contact your Adobe Audience Manager consultant before attempting your first ID synchronization.
seo-description: Describes the syntax and parameters used in the initial HTTP call to synchronize user IDs between Audience Manager and a third-party data provider. Contact your Adobe Audience Manager consultant before attempting your first ID synchronization.
seo-title: ID Synchronization for Outbound Data Transfers
solution: Audience Manager
title: ID Synchronization for Outbound Data Transfers
uuid: e9a55e7e-7b87-4adc-932b-69d91c931b5d
index: y
internal: n
snippet: y
translate: y
---

# ID Synchronization for Outbound Data Transfers

**Purpose of ID Synchronization** 

ID synchronization is the first step in the outbound, asynchronous data transfer process. In this step, [!DNL  Audience Manager] and the vendor compare and match IDs for their respective site visitors. For example, an [!DNL  Audience Manager] customer may know a user by ID 123. However, your data partner could identify this user with ID 456. The synchronization process allows [!DNL  Audience Manager] and a data vendor to reconcile these different IDs and identify users in their respective systems. Once complete, [!DNL  Audience Manager] and the third-party data provider should have corresponding IDs for each unique user seen on our networks. 

**URL Syntax** 

In an ID exchange, a properly formatted URL string should look like this: 
```
http://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&amp;dpuuid=<VENDOR_UUID>&amp;redir=<REDIRECT_URL>
```


**URL Parameters** 

The URL for your inbound ID synchronization call should contain variables described in the table below. 
>[!NOTE]
>
>Replace italicized content with actual parameter values.





<table id="table_EB9F4246E2A34ABB8ED06EA458EB186F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> <span class="varname"> &amp;lt;VENDOR_ID&amp;gt; </span> </span> </td> 
   <td colname="col2"> Unique ID for the data provider (assigned by <span class="keyword"> Audience Manager </span>). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> <span class="varname"> &amp;lt;VENDOR_UUID&amp;gt; </span> </span> </td> 
   <td colname="col2"> Unique user ID. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <span class="codeph"> <span class="varname"> &amp;lt;REDIRECT_URL&amp;gt; </span> </span> </td> 
   <td colname="col2"> An encoded URL redirect with the macro <span class="codeph"> ${DD_UUID} </span> embedded within it. <p>Note:  Added only when the data provider initiates the call. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [ Data Collection Server (DCS) API Methods and Code ](dcs-intro.md#concept_64E817EC9F2E4298BAFDCD5B1B3D03F0)
>* [ Data Collection Components ](c_compcollect.md#concept_66CFFEBF5E8B41ED94082D562A93506E)
