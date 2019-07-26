---
description: Refer to this document for the complete list of Adobe Audience Manager IDs.
keywords: DPID;DPUUID;CID;UUID;uuid;uuid
seo-description: Refer to this document for the complete list of Adobe Audience Manager IDs.
seo-title: Index of IDs in Audience Manager
solution: Audience Manager
title: Index of IDs in Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
---

# Index of IDs in Audience Manager{#index-of-ids-in-audience-manager}

Refer to this document for the complete list of Adobe Audience Manager IDs.

<table frame="all" id="table_6727BA8BBF2C40E48768126B4EC9984E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID </th> 
   <th colname="col2" class="entry"> Name and Description </th> 
   <th colname="col3" class="entry"> Example </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>AAM UUID </p> </td> 
   <td colname="col2"> <p> <b><span class="keyword"> Audience Manager</span> Unique User ID </b> </p> <p> A numerical, 38-digit device ID that <span class="keyword"> Audience Manager</span> associates to each device it interacts with. Think of this ID whenever you see a mention of unique users in the Audience Manager UI.<p><span class="keyword"> Audience Manager</span> tries to save this ID as a cookie in the "demdex.net" 3rd party domain.</p> </p> <p>The Audience Manager UUID is sent in event calls as the d_uuid signal. </p> </td> 
   <td colname="col3"> <p><code> demdex = 07955261652886032950143702505894272138</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ImsOrgId </p> </td> 
   <td colname="col2"> <p> <b>Organization ID</b> </p> <p>This is the ID that a company is provided with upon signing up for the Experience Cloud. To learn how you can find your company's Organization ID, read <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html"> Organizations and Account Linking</a> and scroll down to Find your Organization ID.</p> </td> 
   <td colname="col3"> <p><code> 5DC5123F5245B1D20A490D46@AdobeOrg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p> <b>Partner ID</b> </p> <p> The PID is a company's ID in <span class="keyword"> Audience Manager</span>. <span class="keyword"> Audience Manager</span> associates an imsOrgId to a PID. </p> </td> 
   <td colname="col3"> <p><code> 1352</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ECID, MID </p> </td> 
   <td colname="col2"> <p> <b>Experience Cloud ID</b> </p> <p>The Experience Cloud ID (ECID, legacy abbreviations MID or MCID) is derived mathematically from your Organization ID and the <span class="keyword"> Audience Manager</span> Unique User ID. As long as these IDs remain constant, generating the right ECID for a specific user is simply a math problem. With the same organization ID and Audience Manager UUID you get the same ECID value every time. You can read more about the ECID in the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and Experience Cloud ID</a> document. </p> </td> 
   <td colname="col3"> <p><code> mid = 08382830887934830189014177072406221371 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SID </p> </td> 
   <td colname="col2"> <p> <b>Trait ID</b> </p> <p>The Trait ID uniquely identifies traits in the <span class="keyword"> Audience Manager</span> environment. A Trait ID is assigned to each trait in the user interface (UI). </p> </td> 
   <td colname="col3"> <p><code> 289983</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SID </p> </td> 
   <td colname="col2"> <p> <b>Segment ID </b> </p> <p>The Segment ID uniquely identifies segments in the <span class="keyword"> Audience Manager</span> environment. A Segment ID is assigned to each segment in the UI. </p> </td> 
   <td colname="col3"> <p><code> 4798574</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>csegID </p> </td> 
   <td colname="col2"> <p> <b>Legacy Segment ID </b> </p> <p>This ID uniquely identifies segments in the <span class="keyword"> Audience Manager</span> environment. A Legacy Segment ID is assigned to each segment in the UI. </p> </td> 
   <td colname="col3"> <p><code> 741232</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>destID </p> </td> 
   <td colname="col2"> <p> <b>Destination ID </b> </p> <p>The Destination ID uniquely identifies destinations in the <span class="keyword"> Audience Manager</span> environment. An ID is assigned to each destination in the UI. </p> </td> 
   <td colname="col3"> <p><code> 2523</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPID </p> </td> 
   <td colname="col2"> <p> <b>Data Source ID (also referred to as Data Provider ID)</b> </p> <p>The Data Source ID is a namespace for IDs or traits. An ID is assigned to each data source (data provider) in the UI. </p> </td> 
   <td colname="col3"> <p><code> 39217</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPUUID </p> </td> 
   <td colname="col2"> <p> <b>Data Provider Unique User ID </b> <b>(also referred to as CRM ID)</b> </p> <p>A third-party ID. This is the ID by which you identify end users in your own CRM system. You can sync DPUUIDs with <span class="keyword"> Audience Manager</span> UUIDs and you can sync DPUUIDs from your different <span class="wintitle"> Data Sources</span> (DPIDs) in the <a href="../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md"> ID synchronization process</a>. </p> </td> 
   <td colname="col3"> <p><code> 2132-3423vn-343fds-3432r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM ID </p> </td> 
   <td colname="col2"> <p>See DPUUID above. </p> </td> 
   <td colname="col3"> <p><code> 2132-3423vn-343fds-3432r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CID, CID_IC </p> </td>
   <td colname="col2"> <p> <b>Customer ID, Customer ID Integration Code</b> </p> <p> <b>The CID and CID_IC key-value pairs <a href="../reference/cid.md"> replace DPID and DPUUID</a>.</b> They provide the same functions as the DPID and DPUUID, but are more efficient because they include the data provider ID and user ID (or integration code) in a single key-value pair. </p> </td> 
   <td colname="col3"> <p><code> 81841%013ad2948b1570a7e408a7cfb7ff4879e4 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="2"> <p>DAID </p> <p> 
     <ul id="ul_4EA61BDD0C9140C894162F50300BA9DB"> 
      <li id="li_16148BDD80194F509FF7935364B77F7A">IDFA </li> 
      <li id="li_DF7FEEF2D46A42C5B9FECD6377758B1A">GAID </li>
      <li>RIDA</li>
      <li>MAID</li>
      <li>DUID</li>
     </ul> </p> </td> 
   <td colname="col2"> <p> <b>Device Advertising ID</b> </p> <p>An ID unique to each hardware device, to be used for advertising purposes. Usually provided by the manufacturer of the device or device operating system. </p> </td> 
   <td colname="col3"> <p>IDFA, GAID, Roku ID, Playstation ID </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>Device Advertising ID - IDFA - iOS devices</b> </p> <p> <b>IDFA</b> IDs are mobile device identifiers, provided by the device manufacturer. These IDs represent devices that run the iOS operating system. </p> </td> 
   <td colname="col3"> <p> The format strictly consists of 32 <i>uppercase</i> hexadecimal digits, displayed in five groups and separated by hyphens, in the form 8-4-4-4-12, for a total of 36 characters. </p> <p><code> AEBE52E7-03EE-455A-B3C4-E57283966239</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>Device Advertising ID - GAID - Android devices</b> </p> <p><b>GAID</b> IDs are mobile device identifiers, provided by the device manufacturer. These IDs represent devices that run the Android operating system. </p> </td> 
   <td colname="col3"> <p>The format strictly consists of 32 <i>lowercase</i> hexadecimal digits, displayed in five groups and separated by hyphens, in the form 8-4-4-4-12, for a total of 36 characters. </p> <p> <code> e4fe9bde-caa0-47b6-908d-ffba3fa184f2</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>Roku - RIDA - Roku streaming devices</b> </p> <p><b>GAID</b> RIDA IDs are streaming device identifiers provided by the Roku devices manufacturer.</p> </td>
   <td colname="col3"> <p>The format strictly consists of 32 <i>lowercase</i> hexadecimal digits, displayed in five groups and separated by hyphens, in the form 8-4-4-4-12, for a total of 36 characters. </p> <p> <code> fcb2a29c-315a-5e6b-bcfd-d889ba19aada</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>Microsoft Advertising ID - MAID - Windows 10 Devices</b> </p> <p><b>MAID</b> IDs are device identifiers generated by Windows 10 on a per-device, per-user basis.</p> </td>
   <td colname="col3"> <p>MAIDs are formatted as alphanumeric strings.</p></td>
  </tr>
   <tr> 
   <td colname="col2"> <p> <b>Samsung DUID - Samsung devices</b> </p> Samsung DUIDs are device identifiers provided by Samsung TVs.</p> </td>
   <td colname="col3"> <p>Samsung DUIDs are formatted as alphanumeric strings.</p></td>
  </tr>
 </tbody> 
</table>