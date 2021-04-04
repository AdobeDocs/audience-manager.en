---
description: Frequently asked questions about bringing offline data into Audience Manager.
keywords: ftp or s3;s3 or ftp
seo-description: Frequently asked questions about bringing offline data into Audience Manager.
seo-title: Inbound Customer Data Ingestion FAQ
solution: Audience Manager
title: Inbound Customer Data Ingestion FAQ
uuid: 491e9ec1-4731-46a8-86e7-d8c613e6cedc
feature: Onboarding Offline Data
exl-id: 48eef5f1-0655-4dac-9ab4-74b11c705c13
---
# Inbound Customer Data Ingestion FAQ{#inbound-customer-data-ingestion-faq}

Frequently asked questions about bringing offline data into Audience Manager.

&nbsp;

**Can you summarize the onboarding process?**

The onboarding process consists of two steps described in [Send Batch Data to Audience Manager Overview](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md):

* Step 1: synchronize user IDs;
* Step 2: create and transfer your inbound data file, by adhering to the file format requirements.

&nbsp;

**Can you summarize the deployment process?**

We recommend the following:

* Work with your data provider to format the daily inbound data file according to the Adobe specifications. See the following documentation for file naming and syntax requirements:
  * [Name and Content Requirements for ID Synchronization Files](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)
  * [Inbound Data File Contents: Syntax, Invalid Characters, Variables, and Examples](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)
  * [Amazon S3 Name and File Size Requirements for Inbound Data Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* Work with your [!DNL Adobe] consultant to transfer a test data file to [!DNL Adobe] for format verification.
* Work with your [!DNL Adobe] consultant to produce a taxonomy suitable for interpreting the contents of the data file.
* In the staging/development environment, confirm that the ID synchronization is configured to properly pick up the data provider's visitor ID and transfer it to the [!DNL Audience Manager] servers in realtime.
* Deploy DIL/ID synchronization to production. The ID synchronization will already be configured as a module within the DIL code by your Adobe consultant.
* Transfer production data files to [!DNL Audience Manager]. Given the dependencies on ID synchronization mappings, it might make sense to begin transferring data up to one week after production-code deployment, although you can start transferring the data files as soon as code goes into production.

&nbsp;

**What FTP mode should I use to transfer compressed or encrypted files?**

See [File Compression for Inbound Data Transfer Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

>[!WARNING]
>
>We are gradually phasing out support for FTP configurations. While inbound data file ingestion is still supported in existing FTP integrations, we strongly recommend using Amazon S3 to onboard offline data for new integrations. See [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) for details.

&nbsp;

**Can I upload an inbound data file ([!DNL .sync] or [!DNL .overwrite] file) before deploying [!DNL Audience Manager] code into production?**

Yes. As long as you use a [!UICONTROL cross-device data source] to store the CRM data that you upload, Audience Manager always stores the data. In fact, following the [!UICONTROL Profile Merge Rules] enhancements that Audience Manager launched in October 2019 that allow for offline-only use cases, you can upload and action on data without deploying Audience Manager code into production at all. See:

* [Overview of Profile Merge Rules Enhancements](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/overview-of-profile-merge-rule-enhancements.html)
* [!UICONTROL People-based Destinations] - [Personalization Based on Offline-Only Data](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/destinations/people-based/implementation-guide/people-based-destinations-workflow-offline.html)

<br>&nbsp;

<!---
* If the data provider is configured to use [Profile Link](../features/profile-merge-rules/merge-rules-overview.md) for cross-device targeting, the data available for targeting shortly after an ID sync identifies to the matching [!DNL Audience Manager] visitor ID.

* If the data provider is not configured to use the [!UICONTROL Profile Link] feature, [!DNL Audience Manager] processes only the data for visitor IDs in the inbound data file that have been previously synced/matched back to an [!DNL Audience Manager] visitor ID.

Consider the following use cases in which the data provider is not configured to use [!UICONTROL Profile Merge]:

<table id="table_1A367ED6D016428FB21B3F3BC261BA98"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Use Case </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Case 1</b> </p> </td> 
   <td colname="col2"> <p>On Monday, a visitor identified in the CRM database as visitor ABC logs in, which initiates a client-side ID sync. <span class="keyword"> Audience Manager</span> stores the mapping of visitor ABC to <span class="keyword"> Audience Manager</span> visitor 123. </p> <p>On Tuesday, the CRM database transfers a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager </span>server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> ABC "gender"="male","luxury_shopper"="yes"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_7616432BF9874E7D94F3101C71F73C81"> 
      <li id="li_DC4F5E63D8134A29B703BDF264F02F65">Recognizes visitor ABC from the stored ID sync mapping. </li> 
      <li id="li_62E085FC184D41C3863B1CE832F77946"> Associates the traits <code> male</code> and <code> luxury_shopper</code> with the visitor 123 profile. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Case 2</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the CRM database pushes a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes"</code> </li> 
     </ul> </p> <p> <span class="keyword"> Audience Manager</span> does not have a record of this visitor (or an associated visitor ID) so this record is not processed. </p> <p>On Tuesday, visitor DEF logs in. This action initiates the first client-side ID sync for that visitor. This action maps visitor DEF to <span class="keyword"> Audience Manager</span> ID 456. However, this visitor does not have CRM data associated with their profile. As a result, <span class="keyword"> Audience Manager</span> does not go back and reprocess old files. </p> <p>On Wednesday, the CRM database pushes another data file to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes","dma"="paris"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_E853DA091D9042DAB19774383841D3A3"> 
     <li id="li_64D64A16E99E492BAAE1080867F854A9">Recognizes visitor DEF from the stored ID sync mapping. </li> 
     <li id="li_9CEE7A7B1A954FF6AEEBF8844074CFBB">Associates the traits <code> female</code>, <code> paris</code>, and <code> wine_enthusiast</code> with the visitor 456 profile. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Case 3</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the <span class="keyword"> Audience Manager</span> server receives two files with the following records: </p> <p> <code> .sync</code> file containing: </p> <p> 
     <ul class="simplelist"> 
      <li><code> GHI 123456789</code> </li> 
     </ul> </p> <p> <code> .overwrite</code> file containing: </p> 
    <ul id="ul_084AE448C60447ACA9B1E0C30EAA3E3E"> 
     <li id="li_C68B7BBFE7CA4D22B606D939E32FF4FB"><code> GHI "gender"="male" "wine_enthusiast"="no"</code> </li> 
     <li id="li_FDBCAAFBD606477E8690EA80AD455A81"><code> JKL "gender"="female" "wine_enthusiast"="yes"</code> </li> 
    </ul> <p><span class="keyword"> Audience Manager</span> holds a mapped record of visitor JKL to ID 789, from a previous ID sync. </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_4D083CEA7F1B4F6BBBBB841C21293751"> 
     <li id="li_6DABD380311D49738DAD98F5E6DE45B8">Recognizes visitor JKL from the stored ID sync mapping. </li> 
     <li id="li_CCEF77240E5C4A03AAE347440D73F0BB">Associates the traits <code> female</code> and <code> wine_enthusiast</code> with visitor ID 789's profile. </li> 
     <li id="li_273F8FD7C6214488A26AAFFA6DE043E5">Ignores the trait association for visitor GHI, since its ID was only synced in the current batch. To associate traits with visitor GHI, you need to include them in future <code> .overwrite</code> files. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

-->

**What time of day should I transfer my file?**

[!DNL Audience Manager] checks for and processes files multiple times throughout the day. Upload your data whenever you're ready.

&nbsp;

**How long does it take before data from an uploaded file is available for targeting?**

Data is available for targeting after 48 hours. Also, do not interpret the "successful upload" email as a statement that the data is available. This only means that [!DNL Audience Manager] has picked up the file and completed the first step of processing.

&nbsp;

**How often should I send files and should these be full or incremental files?**

As a best practice, send an incremental file once per day for new visitors and for visitors whose data has changed. Many [!DNL Audience Manager] customers send a full file once per month. However, these file intervals and increments are flexible. You should send data in increments and at times that make sense for you.

&nbsp;

**How long does Audience Manager keep my files on the server?**

FTP files are removed after they've been processed. [!DNL S3] files are removed after 30 days. Files that cannot be processed due to format, syntax, or other errors, are removed. See also, [Privacy and Data Retention FAQ](../faq/faq-privacy.md).

&nbsp;

**What's the difference between full and incremental files?**

* **Full:** A full file overwrites all of your existing visitor profiles and replaces them with the data in your file. Full files are identified by the `.overwrite` tag appended to the file name. You can use a `.overwrite` file to reset visitor traits or remove stale, obsolete traits.

  >[!NOTE]
  >
  >The [!DNL .overwrite] files only overwrite [!DNL Audience Manager] profile data associated to this data provider. In other words, all [!DNL Audience Manager] data associated to the visitor remains intact after a [!DNL .overwrite] file has been processed.

* **Incremental:** An incremental file appends new data to your existing visitor profiles. Incremental files are identified by the `.sync` tag appended to the file name. Sending in an incremental file does not erase or overwrite existing profiles.

The following use cases demonstrate how these file types affect stored visitor profiles.

|Use Case|Description|
|---|---|
|Incremental and Full|<ul><li>Day 1 `.sync` file contents: `visitor123 = a,b,c`</li><li>Day 2 `.overwrite` file contents: `visitor123 = c,d,e`</li><li>Day 3 visitor profile ID 123 contents: `c,d,e`</li></ul>|
|Incremental Only|<ul><li>Day 1 `.sync` file contents: `visitor123 = a,b,c`</li><li>Day 2 `.sync` file contents: `visitor123 = c,d,e`</li><li>Day 3 visitor profile ID 123 contents: `a,b,c,d,e`</li></ul>|

For more information about full and incremental file types, see:

* [Amazon S3 Name and File Size Requirements for Inbound Data...](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

&nbsp;

**What happens if I send in a file with IDs for visitors that have never performed the on-page ID sync?**

During processing, [!DNL Audience Manager] skips that record and moves on to the next. If a [DPID (Data Provider ID)](../reference/ids-in-aam.md) is set up as a cross-device DPID, data that is ingested before an ID synchronization is saved and is available for use shortly after the ID synchronization occurs.

&nbsp;

**What is the time stamp, what is it for, and can you provide an example?**

Time stamps are used for logging and record keeping. They are required by the syntax used for a properly formatted inbound file name. See:

* [Amazon S3 Name Requirements for Inbound Data Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

&nbsp;

**What is a [!DNL Data Provider ID (DPID)] and how do I get it?**

Your Adobe consultant will assign a three-digit or four-digit [DPID (Data Provider ID)](../reference/ids-in-aam.md) to your particular data source. This ID is unique and does not change.

&nbsp;

**How large can the daily data files be?**

See [File Compression for Inbound Data Transfer Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

&nbsp;

**Does Audience Manager support file compression?**

Yes, see:

* [File Compression for Inbound Data Transfer Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [Amazon S3 Name Requirements for Inbound Data Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

&nbsp;

**The primary key in my data source database is an email address. Is that considered personally identifiable information?**

Yes. [!DNL Audience Manager] does not store email addresses in its database. Visitors should be assigned a randomly generated ID or a one-way-hashed version of the email address prior to initiating ID synchronizations.

&nbsp;

**Are the data file contents case-sensitive? How about the ID synchronization?**

There are two basic components of a data file: A [!UICONTROL User ID] (see [!UICONTROL User ID] in [File Variables Defined](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#file-variables-defined)) and profile data, usually in the form of key-value pairs or codes. The [!UICONTROL User ID] is case-sensitive. Generally, profile or key-value data is not case-sensitive.

&nbsp;

**Should I use FTP or [!DNL Amazon S3] to transfer files?**

As best practice, we recommend [!DNL Amazon S3] because the process is simpler. [!DNL Audience Manager] transfers FTP files to [!DNL S3] regardless, so the process is more streamlined if you drop the files on [!DNL Amazon S3] yourself. What's more, customers uploading simultaneously to FTP share the FTP's bandwidth, so they should expect slower upload speeds. [!DNL Amazon S3] is also replicated and distributed, so it is generally safer and more reliable than an FTP server. For more information, see [About Amazon S3](../reference/amazon-s3.md).

>[!WARNING]
>
>We are gradually phasing out support for FTP configurations. While inbound data file ingestion is still supported in existing FTP integrations, we strongly recommend using [!DNL Amazon S3] to onboard offline data for new integrations. See [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) for details.

&nbsp;

**How does Audience Manger process inbound files?**

[!DNL Audience Manager] uses [!DNL Amazon Simple Queue Service (SQS)] for inbound data processing. Here is how this works:

1. [!DNL Audience Manager] customers upload their inbound data to an [!DNL Amazon S3] bucket.
1. The data enters the [!DNL Amazon SQS] queue, waiting to be processed by [!DNL Audience Manager].
1. [!DNL Audience Manager] reads up to 119000 entries from the [!DNL Amazon SQS] queue and splits them in up to 3 batches. Files in each batch get processed simultaneously.

&nbsp;

**I need to upload multiple files at the same time. Will the files be processed simultaneously?**

It depends. [!DNL Audience Manager] reads up to 119000 entries from the [!DNL Amazon SQS] queue and splits them in up to 3 batches. Your files will be processed simultaneously only if they end up in the same batch. However, due to the high amount of data ingested by [!DNL Audience Manager] on a daily basis, we cannot guarantee any file processing order.

>[!MORELIKETHIS]
>
>* [Batch Data Transfer Process Described](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)
