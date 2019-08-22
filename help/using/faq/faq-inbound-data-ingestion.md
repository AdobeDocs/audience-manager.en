---
description: Frequently asked questions about bringing offline data into Audience Manager.
keywords: ftp or s3;s3 or ftp
seo-description: Frequently asked questions about bringing offline data into Audience Manager.
seo-title: Inbound Customer Data Ingestion FAQ
solution: Audience Manager
title: Inbound Customer Data Ingestion FAQ
uuid: 491e9ec1-4731-46a8-86e7-d8c613e6cedc
---

# Inbound Customer Data Ingestion FAQ{#inbound-customer-data-ingestion-faq}

Frequently asked questions about bringing offline data into Audience Manager.

<br>&nbsp;

<!-- 

c_inbound_crm_data_ingestion.xml

 -->

**Can you summarize the onboarding process?**

The onboarding process consists of 2 core components described in [Batch Data Transfer Process Described](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md). These involve:

* ID synchronization
* Inbound Data File ( [!DNL .sync] file or [!DNL .overwrite] file)

<!-- 

Removed the Data Translation File bullet from the list above.

 -->

Below is a list of questions and answers you might find helpful after reviewing the documentation.

>[!NOTE]
>
>The examples in this section are simplified or shortened for brevity and demonstration purposes. Refer to the Inbound Data Ingestion documentation for detailed specifications about file formats and syntax.

<br>&nbsp;

**Can you summarize the deployment process?**

We recommend the following:

* Work with your data provider to format the daily inbound data file according to [!DNL Adobe] specifications.
* Transfer a test data file to [!DNL Adobe] for format verification.
* Work with your [!DNL Adobe] consultant to produce a taxonomy suitable for interpreting the contents of the data file.
* In the staging/development environment, confirm that the ID sync is configured to properly pick up the data provider's visitor ID and transfer it to the [!DNL Audience Manager] servers in realtime.
* Deploy DIL/ID sync to production. The ID sync will already be configured as a module within the DIL code by your Adobe consultant.
* Transfer production data files to [!DNL Audience Manager]. Given the dependencies on ID sync mappings, it might make sense to begin transferring data up to one week after production-code deployment, although you can start transferring the data files as soon as code goes into production.

<br>&nbsp;

**What FTP mode should I use to transfer compressed or encrypted files?**

See [File Compression for Inbound Data Transfer Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

<br>&nbsp;

**Can I upload an inbound data file ([!DNL .sync] or [!DNL .overwrite] file) before deploying [!DNL Audience Manager] code into production?**

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

<br>&nbsp;

**What time of day should I transfer my file?**

[!DNL Audience Manager] checks for and processes files multiple times throughout the day. Upload your data whenever you're ready.

<br>&nbsp;

**How long does it take before data from an uploaded file is available for targeting?**

Data is available for targeting after 48 hours. Also, do not interpret the "successful upload" email as a statement that the data is available. This only means that [!DNL Audience Manager] has picked up the file and completed the first step of processing.

<br>&nbsp;

**How often should I send files and should these be full or incremental files?**

As a best practice, send an incremental file once per day for new visitors and for visitors whose data has changed. Many [!DNL Audience Manager] customers send a full file once per month. However, these file intervals and increments are flexible. You should send data in increments and at times that make sense for you.

<br>&nbsp;

**How long does Audience Manager keep my files on the server?**

FTP files are removed after they've been processed. [!DNL S3] files are removed after 30-days. Files that cannot be processed due to format, syntax, or other errors are removed. See also, [Privacy and Data Retention FAQ](../faq/faq-privacy.md).

<br>&nbsp;

**What's the difference between full and incremental files?**

* **Full:** A full file overwrites all of your existing visitor profiles and replaces them with the data in your file. Full files are identified by the `.overwrite` tag appended to the file name. You can use a `.overwrite` file to reset visitor traits or remove stale, obsolete traits.

  >[!NOTE]
  >
  >The [!DNL .overwrite] files only overwrite [!DNL Audience Manager] profile data associated to this data provider. In other words, all [!DNL Adobe Analytics] data associated to the visitor remains intact after a [!DNL .overwrite] file has been processed.

* **Incremental:** An incremental file appends new data to your existing visitor profiles. Incremental files are identified by the `.sync` tag appended to the file name. Sending in an incremental file does not erase or overwrite existing profiles.

The following use cases demonstrate how these file types affect stored visitor profiles.

<table id="table_CE43B49508384ABF8B25FA8A8FFE5362"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Use Case </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Incremental and Full</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_E89301D815174D45B9B238F2CDE6CCC6"> 
      <li id="li_FA841FEEC0534AD59D1AB61DD5B9DEC4">Day 1 <code> .sync</code> file contents: <code> visitor123 = a,b,c</code> </li> 
      <li id="li_0E1A57B04D26481C8C41EBA63ACBEFE0">Day 2 <code> .overwrite</code> file contents: <code> visitor123 = c,d,e</code> </li> 
      <li id="li_497A5604AD9A49A2ADE548C7CE158F0E"> Day 3 visitor profile ID 123 contains <code> c,d,e </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Incremental Only</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8271C9796BD040E4B8DC64DCE4FE2AD3"> 
      <li id="li_347959BDE83549F794E6661C95097891">Day 1 <code> .sync</code> file contents: <code> visitor123 = a,b,c </code> </li> 
      <li id="li_B25D96526DE94171A3A5DC8DB7A19415">Day 2 <code> .sync</code> file contents: <code> visitor123 = c,d,e</code> </li> 
      <li id="li_6E17809D49C74F4991B0B445469055E6">Day 3 visitor profile ID 123 contains <code> a,b,c,d,e</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

For more information about full and incremental file types, see:

* [Amazon S3 Name and File Size Requirements for Inbound Data...](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

<br>&nbsp;

**What happens if I send in a file with IDs for visitors that have never performed the on-page ID sync?**

During processing, [!DNL Audience Manager] simply skips that record and moves on to the next. If a DPID (Data provider ID) is set up as a cross-device DPID, data that is ingested before an ID sync is saved and is available for use shortly after the ID sync occurs.

<br>&nbsp;

**What is the time stamp, what is it for, and can you provide an example?**

Time stamps are used for logging and record keeping. They are required by the syntax used for a properly formatted inbound file name. See:

* [Amazon S3 Name Requirements for Inbound Data Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) 


<br>&nbsp;

**What is a Data Provider ID (DPID) and how do I get it?**

Your Adobe consultant will assign a three-digit or four-digit DPID to your particular data source. This ID is unique and does not change.

<br>&nbsp;

**How large can the daily data files be?**

See [File Compression for Inbound Data Transfer Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

<br>&nbsp;

**Does Audience Manager support file compression?**

Yes, see:

* [File Compression for Inbound Data Transfer Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) 
* [Amazon S3 Name Requirements for Inbound Data Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) 


<br>&nbsp;

**The primary key in my data source database is an email address. Is that considered personally identifiable information?**

Yes. [!DNL Audience Manager] does not store email addresses in our database. Visitors should be assigned a random ID or a one-way-hashed version of the email address prior to initiating ID syncs.

<br>&nbsp;

**Are the data file contents case-sensitive? How about the ID sync?**

There are two basic components of a data file: A Unique User ID (UUID) and profile data, usually in the form of key-value pairs or codes. The UUID is case-sensitive. Generally, profile or key-value data is not case-sensitive.

<br>&nbsp;

**Should I use FTP or [!DNL Amazon S3] to transfer files?**

As best practice, we recommend [!DNL Amazon S3] because the process is simpler. [!DNL Audience Manager] transfers FTP files to [!DNL S3] regardless, so the process is more streamlined if you drop the files on [!DNL Amazon S3] yourself. What's more, customers uploading simultaneously to FTP share the FTP's bandwidth, so they should expect slower upload speeds. [!DNL Amazon S3] is also replicated and distributed, so it is generally safer and more reliable than an FTP server. For more information, see [About Amazon S3](../reference/amazon-s3.md).

<br>&nbsp;

**How does Audience Manger process inbound files?**

[!DNL Audience Manager] uses [!DNL Amazon Simple Queue Service (SQS)] for inbound data processing. Here is how this works:

1. [!DNL Audience Manager] customers upload their inbound data to an [!DNL Amazon S3] bucket.

2. The data enters the [!DNL Amazon SQS] queue, waiting to be processed by [!DNL Audience Manager].

3. [!DNL Audience Manager] reads up to 119000 entries from the [!DNL Amazon SQS] queue and splits them in up to 3 batches. Files in each batch get processed simultaneously.

<br>&nbsp;

**I need to upload multiple files at the same time. Will the files be processed simultaneously?**

It depends. [!DNL Audience Manager] reads up to 119000 entries from the [!DNL Amazon SQS] queue and splits them in up to 3 batches. Your files will be processed simultaneously only if they end up in the same batch. However, due to the high amount of data ingested by [!DNL Audience Manager] on a daily basis, we cannot guarantee any file processing order.

>[!MORE_LIKE_THIS]
>
>* [Batch Data Transfer Process Described](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)
