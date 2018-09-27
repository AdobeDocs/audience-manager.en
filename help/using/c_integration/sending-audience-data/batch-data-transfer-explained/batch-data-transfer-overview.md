---
description: An overview for technical and non-technical customers who want to bring data from other systems (offline) into Audience Manager.
seo-description: An overview for technical and non-technical customers who want to bring data from other systems (offline) into Audience Manager.
seo-title: Send Batch Data to Audience Manager Overview
solution: Audience Manager
title: Send Batch Data to Audience Manager Overview
uuid: e9ecb9f0-a1ac-4739-9165-b9421f1d6439
index: y
internal: n
snippet: y
translate: y
---

# Send Batch Data to Audience Manager Overview

An overview for technical and non-technical customers who want to bring data from other systems (offline) into Audience Manager.



**Advantages** 



<!-- c_offline_to_online.xml -->
You can make data from other systems available in Audience Manager. Our system can help you unlock value and leverage user data that you've collected previously. This includes information about purchases, customer surveys, registration data, CRM databases, etc. While each integration presents its own challenges, they all share these common steps. Review this material to help reduce the effort required to bring your offline data online.


**Step 1: Synchronize User IDs** 


During synchronization, Audience Manager assigns unique IDs to clients and their users. These IDs are known as the Data Provider ID (DPID) and Unique User ID (UUID), respectively. Audience Manager uses the DPID and UUID to identify users and qualify them for traits, segments, audience groups, and for reporting. Additionally, our data collection code (DIL) looks for these IDs to capture visitor data from your website. When this step is complete, Audience Manager and your offline repository should contain corresponding IDs for each user record. 


Important considerations about this step: 
* **Client ID placement:** Audience Manager needs to know where your client ID appears on your website (e.g., is it stored in a cookie, an Analytics variable, in page code, etc.).
* **Exclude PII:** User IDs must not contain personally identifiable information (PII).
* **Case and content sensitivity:** During a real-time data sync, user IDs captured from your site by Audience Manager must correspond to IDs passed in from your offline repository. For example, if offline records hold information about User123, but your site renders that ID as USER123, Audience Manager sees these as different visitors. As a result, online information for this visitor cannot be associated with the corresponding records in your offline database. IDs must match exactly.





See [ID Synchronization for Inbound Data Transfers](../../../c_integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#concept_8749F04CACF64B6CA2132D9F9887364A). 

<!-- <p> <b>Step 2: Create a Translation File</b> </p> 
<p>A translation file classifies data according to uniform and logical hierarchy. It is a taxonomy that helps you organize information from general categories (e.g., geography) to more precise classifications (e.g., <i>geography > United States > New York</i>). Also, it labels data with to easy to understand names such as "gender=male" or "color=green" instead of with your internal SKUs, abbreviations, or other names. The file lets Audience Manager display this information in a readable, logical manner. You and your data partners must create and share the translation file with Audience Manager before any real-time or server-to-server data transfers can begin. You can update this file on a schedule relevant to your business needs. </p> 
<p>Important considerations about this step: </p> 
<ul id="ul_6A05AECB0BD649B1BF1B34058E9008E2"> 
 <li id="li_39817ED898F14156A77FCAC066FE0968"> <b>Create a comprehensive list:</b> The translation file must include all the possible values that can be passed in on a particular key. For example, if you have category key called "color" and it accepts the values "red," "green," and "blue," the translation file must contain <i>all</i> those elements. </li> 
 <li id="li_19CAD7683BCF45278E2991C1EDBC9903"> <b>Case and content sensitivity:</b> The key-values in the file must match the values actually passed in to Audience Manager from your website. </li> 
</ul> 
<p>See DATA TRANSLATION FILE. </p> -->


**Step 2: Data File Format** 


File names and content follow strict guidelines. You *must* name and organize data files according to these specifications in this guide. See: 

* [Amazon S3 Name Requirements for Inbound Data Files](../../../c_integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md#concept_B3CAF442BFFE4823B76A5D0D91DF9942)
* [FTP Name Requirements for Inbound Data Files](../../../c_integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#concept_D34898442363415DBF75CEBFC2E86997)
* [Inbound Data File Contents: Syntax, Variables, and Examples](../../../c_integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#concept_49E6F0740E794B07ACD115D10EDEB5AC)




**Online Data is Available for Offline Marketing Efforts** 


When you bring offline data online, you can still use this information for offline campaigns. To do this, Audience Manager exports trait and segment information to an FTP or Amazon S3 location of your choice. Contact your Partner Solutions manager for additional information or assistance. 


**Environments** 


Audience Manager provides the following environments for file drop-off: 

<table id="table_A61AA64578944B23B5A7355F2A76E882"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Environment </th> 
   <th colname="col02" class="entry"> Service </th> 
   <th colname="col2" class="entry"> Location </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <b>Production</b> </td> 
   <td colname="col02"> FTP </td> 
   <td colname="col2"> <p> <span class="codeph"> ftp-in.demdex.com</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col02"> S3 </td> 
   <td colname="col2"> <p> <span class="codeph"> demdex-s2s-clients</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> <b>Beta Environment</b> </td> 
   <td colname="col02"> FTP </td> 
   <td colname="col2"> <p><span class="codeph"> sandbox-ftp-in.demdex.com</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col02"> S3 </td> 
   <td colname="col2"> <p> <span class="codeph"> demdex-s2s-clients-sandbox-us-east-1</span> </p> </td> 
  </tr> 
 </tbody> 
</table>



**Further Technical Reading** 


Systems engineers, developers, or technical/implementation teams should review [Real-Time Inbound Data Integration](../../../c_integration/sending-audience-data/real-time-data-integration/real-time-data-integration.md#concept_D93A558E981243579E853690BB5C07E1) and [Batch Data Transfer Process Described](../../../c_integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md#concept_EC5B2B3B5ED443F0B271400C08B263D3). These sections provide details about transfer protocols, file content, and file name requirements. 
