---
description: An overview for technical and non-technical customers who want to bring data from other systems (offline) into Audience Manager.
keywords: inbound, batch, batch upload, batch data
seo-description: An overview for technical and non-technical customers who want to bring data from other systems (offline) into Audience Manager. To do so, use the batch upload option in Audience Manager.
seo-title: Send Batch Data to Audience Manager Overview
solution: Audience Manager
title: Send Batch Data to Audience Manager Overview
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Inbound Data Transferss
exl-id: ba95537e-30c9-4546-9456-55f46dbe29ff
---
# Send Batch Data to [!DNL Audience Manager] Overview {#send-batch-data-to-audience-manager-overview}

An overview for technical and non-technical customers who want to bring data from other systems (offline) into [!DNL Audience Manager].

## Advantages

You can make data from other systems available in [!DNL Audience Manager]. Our system can help you unlock value and leverage user data that you've collected previously. This includes information about purchases, customer surveys, registration data, [!DNL CRM] databases, etc. While each integration presents its own challenges, they all share these common steps. Review this material to help reduce the effort required to bring your offline data online.

## Step 1: Synchronize User IDs

During synchronization, [!DNL Audience Manager] assigns unique IDs to clients and their users. These IDs are known as the [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) and [!UICONTROL Unique User ID] ([!UICONTROL UUID]), respectively. [!DNL Audience Manager] uses the [!UICONTROL DPID] and [!UICONTROL UUID] to identify users and qualify them for [!UICONTROL traits], [!UICONTROL segments], audience groups, and for reporting. Additionally, our data collection code ([!UICONTROL DIL]) looks for these IDs to capture visitor data from your website. When this step is complete, [!DNL Audience Manager] and your offline repository should contain corresponding IDs for each user record.

Important considerations about this step:

* **Client ID placement:** [!DNL Audience Manager] needs to know where your client ID appears on your website (e.g., is it stored in a cookie, an Analytics variable, in page code, etc.).
* **Exclude [!DNL PII]:** User IDs must not contain personally identifiable information ([!DNL PII]).
* **Case and content sensitivity:** During a real-time data sync, user IDs captured from your site by [!DNL Audience Manager] must correspond to IDs passed in from your offline repository. For example, if offline records hold information about [!DNL User123], but your site renders that ID as [!DNL USER123], [!DNL Audience Manager] sees these as different visitors. As a result, online information for this visitor cannot be associated with the corresponding records in your offline database. IDs must match exactly.

See [ID Synchronization for Inbound Data Transfers](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

## Step 2: Data File Format

File names and content follow strict guidelines. You *must* name and organize data files according to these specifications in this guide. See:

* [Amazon S3 Name Requirements for Inbound Data Files](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) 
* [Inbound Data File Contents: Syntax, Variables, and Examples](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## Online Data is Available for Offline Marketing Efforts

When you bring offline data online, you can still use this information for offline campaigns. To do this, [!DNL Audience Manager] exports trait and segment information to an [!DNL FTP] or [!DNL Amazon S3] location of your choice. Contact your Partner Solutions manager for additional information or assistance.

## Environments

[!DNL Audience Manager] provides the following environments for file drop-off:

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
   <td colname="col2"> <p> <code> ftp-in.demdex.com</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col02"> S3 </td> 
   <td colname="col2"> <p> <code> demdex-s2s-clients</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> <b>Beta Environment</b> </td> 
   <td colname="col02"> FTP </td> 
   <td colname="col2"> <p><code> sandbox-ftp-in.demdex.com</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col02"> S3 </td> 
   <td colname="col2"> <p> <code> demdex-s2s-clients-sandbox-us-east-1</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Further Technical Reading

Systems engineers, developers, or technical/implementation teams should review [Batch Data Transfer Process Described](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) and the other articles in this section. These articles provide details about transfer protocols, file content, and file name requirements.
