---
description: Describes the syntax and parameters used in the initial HTTP call to synchronize user IDs between a vendor and Audience Manager. ID synchronization can begin after you send your data taxonomy to Audience Manager.
seo-description: Describes the syntax and parameters used in the initial HTTP call to synchronize user IDs between a vendor and Audience Manager. ID synchronization can begin after you send your data taxonomy to Audience Manager.
seo-title: ID Synchronization for Inbound Data Transfers
solution: Audience Manager
title: ID Synchronization for Inbound Data Transfers
uuid: f87fc5f9-c483-4b16-9223-9c192cd4e47c
index: y
internal: n
snippet: y
translate: y
---

# ID Synchronization for Inbound Data Transfers

ID synchronization is the first step in the inbound, asynchronous data transfer process. In this step, Audience Manager and the vendor compare and match IDs for their respective site visitors. For example, an [!DNL  Audience Manager] customer may know a user by ID 123. However, your data partner could identify this user with ID 456. The synchronization process allows [!DNL  Audience Manager] and a data vendor to reconcile these different IDs and identify users in their respective systems. Once complete, [!DNL  Audience Manager] and your third-party partner should have corresponding IDs for each unique user seen on our networks. 

You can use the following methods to get your data into [!DNL  Audience Manager]: 

* [ ID Synchronization HTTP Request ](../../../../c_integration/c_onboarding_data/c_async/c_inbound_async_intro/c_id_sync_in.md#section_0FF82F1DBA8E46A39FA65BD3A45004CA)
* [ Declared ID Event ](../../../../c_integration/c_onboarding_data/c_async/c_inbound_async_intro/c_id_sync_in.md#section_22AC5DB0340B4EB9B1A4CF9075743878)
* [ ID Synchronization From an Email Embedded Image ](../../../../c_integration/c_onboarding_data/c_async/c_inbound_async_intro/c_id_sync_in.md#section_DE58B1A4BD454EBB85FA146D19BAB9EE)

## ID Synchronization HTTP Request {#section_0FF82F1DBA8E46A39FA65BD3A45004CA}

In an ID exchange, a properly formatted URL string should look like this: 
```
http://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&amp;dpuuid=<VENDOR_UUID>&amp;redir=<REDIRECT_URL>
```


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
  <tr> 
   <td colname="col1"> <span class="codeph"> <span class="varname"> &amp;lt;VENDOR_ID&amp;gt; </span> </span> </td> 
   <td colname="col2"> <p>Unique ID for the content provider (assigned by <span class="keyword"> Audience Manager </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="codeph"> <span class="varname"> &amp;lt;VENDOR_UUID&amp;gt; </span> </span> </td> 
   <td colname="col2"> <p>URL (Percent) Encoded representation of your Unique User ID. In addition to encoding reserved ASCII characters, any non-ASCII characters should be percent encoded based on the UTF-8 character encoding table. </p> <p>For more information, see the <a href="http://www.url-encode-decode.com" format="http" scope="external"> URL Encode/Decode Online </a> website. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="codeph"> <span class="varname"> &amp;lt;REDIRECT_URL&amp;gt; </span> </span> </td> 
   <td colname="col2"> <p>An encoded URL redirect with the macro <span class="codeph"> ${DD_UUID} </span> embedded within it. </p> <p>Note:  Added only when the content provider initiates the call. </p> </td> 
  </tr> 
 </tbody> 
</table>


## Declared ID Event {#section_22AC5DB0340B4EB9B1A4CF9075743878}

For more information, see [ Declared IDs ](../../../../c_features/c_declared_id/c_declared_id.md#concept_2CD1CC1558354F38B3DEDBE09AE8E869). 

## ID Synchronization From an Email Embedded Image {#section_DE58B1A4BD454EBB85FA146D19BAB9EE}

The format for matching IDs via an email image is the same as shown above. Note, however, that images in an email must be enabled for this to work. This can affect ID synchronization via email because most mail systems disable images by default. 
>[!MORE_LIKE_THIS]
>
>* [ Data Collection Components ](c_compcollect.md#concept_66CFFEBF5E8B41ED94082D562A93506E)
