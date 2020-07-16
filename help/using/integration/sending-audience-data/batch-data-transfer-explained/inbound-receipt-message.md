---
description: Whenever an inbound Server-to-Server file is processed, a receipt is sent via email to partner solutions and, if configured, to the partner.
seo-description: Whenever an inbound Server-to-Server file is processed, a receipt is sent via email to partner solutions and, if configured, to the partner.
seo-title: Sample Message to Partners after Inbound Processing
solution: Audience Manager
title: Sample Message to Partners after Inbound Processing
uuid: 69e3a8b3-8465-4f4c-8005-8a9ff15ae19a
feature: Inbound Data Transfers
---

# Sample Message to Partners after Inbound Processing{#sample-message-to-partners-after-inbound-processing}

Whenever an inbound [!UICONTROL Server-to-Server] file is processed, a receipt is sent via email to partner solutions and, if configured, to the partner.

<!-- r_inbound_message.xml -->

The following example is a sample email message. The table below the message describes the various lines in the message.

<table id="table_F579C2278A044213BFCEF97F3BEC2C0C"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>From: aam-noreply@adobe.com </b> </p> <p> <b>Subject: Adobe Audience Manager Server-To-Server Processing Result:</b> </p> <p> <b>Dear Adobe Partner: (ID:7)</b> <b></b> </p> <p> <b>We have received your Adobe Audience Manager Server-To-Server file delivery</b> </p> <p> <b>File name:</b> <i></i> </p> <p> <b> s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806402.sync</b> </p> <p> <b> s3n://&lt;<i>bucket_name&gt;</i>/2018-05-16/ftp_dpm_7_901_1368655202.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784804.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806403.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784802.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784803.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806404.sync</b> </p> <p> <b>Records received: 40669900</b> </p> <p><b>Format Errors: 0</b> </p> <p> <b>Invalid AAM ID: 112 </b> </p> <p> <b>No Matching AAM ID: 0 </b> </p> <p> <b>No Trait Realized: 26730823 </b> </p> <p> <b>Records processed: 40669900 </b> </p> <p> <b>Stored Records: 13938958 </b> </p> <p> <b>Total devices: 21 </b> </p> <p> <b>Total signals: 918878926 </b> </p> <p> <b>Total unused signals: 660348376 </b> </p> <p> <b>Total realized traits: 258086908 </b> </p> <p> <b>Total removed traits: 0 </b> </p> <p> <b>Total traits failed validation: 0 </b> </p> <p> <b>Total users that have traits which failed validation: 0 </b> </p> <p> <b>Job start time: 2018-05-17 18:07:49 </b> </p> <p> <b>Job end time: 2018-05-17 18:45:02</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

The following table contains rows corresponding to lines in the received email message.

<table id="table_93076D46AC50411395E72B9B987E99BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Line </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> File name </td> 
   <td colname="col2"> <p>List of all inbound files that Adobe received for this partner that were processed together. In the previous sample email message, the partner ID is 7 and the data owner ID is 901. </p> <p>The tail number (1,2,3...) is the split number added either by the customer or by the inbound distributor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Records received </td> 
   <td colname="col2"> <p>Total number of records Adobe received across all files. In most cases, this should be the total number of lines in inbound files. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Format Errors </td> 
   <td colname="col2"> <p>Number of lines that did not match the expected format. These lines were not recognizable by the inbound job. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Invalid AAM ID </td> 
   <td colname="col2"> <p>Number of Audience Manager UUIDs that did not match the expected 38-digit format. Or the Audience Manager UUIDs sent in the file are not numbers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> No Matching AAM ID </td> 
   <td colname="col2"> <p>Total number of users for whom Audience Manager failed to find a matching UUID. These files have not been ID synced, so Audience Manager cannot look up the UUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> No Trait Realized </td> 
   <td colname="col2"> <p>Number of records where none of the signals on the line maps to an Audience Manager trait. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Records processed </td> 
   <td colname="col2"> <p>Total number of records Audience Manager processed. In most cases, this number should be the same as "Records received." </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stored Records </td> 
   <td colname="col2"> <p>Number of records resulting in data to be loaded into the system = Records Processed - Format Errors - Invalid AAM IDs - No Matching AAM ID - No Trait Realized. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total devices </td> 
   <td colname="col2"> <p>Number of devices for which data was loaded into the system. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total signals </td> 
   <td colname="col2"> <p> Total number of signals for all users across all inbound files (total number of key/value pairs in the records processed). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total unused signals </td> 
   <td colname="col2"> <p>Total number of unused signal for all users across all inbound files (key/value pairs that did not map to Audience Manager traits). In most cases, this means that Audience Manager does not have rules defined for the signal. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total realized traits </td> 
   <td colname="col2"> <p>Number of Audience Manager traits for all users across all inbound files based on the signals. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total removed traits </td> 
   <td colname="col2"> <p> Total number of removed traits for all users across all inbound files. For full syncs, this happens if the user had the trait in a previous run but not in the current run. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total traits failed validation </td> 
   <td colname="col2"> <p>Represents the number of traits that do not belong to the data source declared in the file name. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total users that have traits which failed validation </td> 
   <td colname="col2"> <p>The number of records that had traits that failed validation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Job start time </td> 
   <td colname="col2"> <p>The time the inbound job starts. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Job end time </td> 
   <td colname="col2"> <p>The time the inbound job ends. </p> </td> 
  </tr> 
 </tbody> 
</table>