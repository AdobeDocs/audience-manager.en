---
description: Audience Manager receives a tremendous amount of data every day. This affects the amount of time it takes to process your data and generate report results. The content in this section describes how these time intervals affect your Audience Manager account. Also, the time frames and schedules described here are general guidelines only. These schedules do not constitute Service-Level Agreements (SLAs) or commitments related to data delivery. Adobe reserves the right to change the time frames and schedules at any time without notice.
seo-description: Audience Manager receives a tremendous amount of data every day. This affects the amount of time it takes to process your data and generate report results. The content in this section describes how these time intervals affect your Audience Manager account. Also, the time frames and schedules described here are general guidelines only. These schedules do not constitute Service-Level Agreements (SLAs) or commitments related to data delivery. Adobe reserves the right to change the time frames and schedules at any time without notice.
seo-title: How Data Delivery and File Processing Times Affect Reports
solution: Audience Manager
title: How Data Delivery and File Processing Times Affect Reports
uuid: 4b975512-f67e-4749-a7ef-168415597682
---

# How Data Delivery and File Processing Times Affect Reports{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager receives a tremendous amount of data every day. This affects the amount of time it takes to process your data and generate report results. The content in this section describes how these time intervals affect your Audience Manager account. Also, the time frames and schedules described here are general guidelines only. These schedules do not constitute Service-Level Agreements (SLAs) or commitments related to data delivery. Adobe reserves the right to change the time frames and schedules at any time without notice.

## Reporting Numbers {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

The following table lists and describes the time intervals in our general and real-time reports.

<table id="table_73AF95DF5D3A423894486444505D816A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Data Type </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Real-Time Data</b> </p> </td> 
   <td colname="col2"> <p> Real-time numbers for today are for the hours 00:00 to 23:59:59 UTC from yesterday. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>General Report Data</b> </p> </td> 
   <td colname="col2"> <p>The data in the <a href="../reporting/general-reports.md#general-reports-overview"> General Reports</a> depends on the successful completion of other job processes and the amount of data received for a particular day. Most of the time, <span class="wintitle"> General Report</span> data should be updated by 18:00 UTC each day. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Inbound and Outbound File Transfers {#inbound-outbound-file-transfers}

[!DNL Audience Manager] processes and sends inbound and outbound [!UICONTROL Server-to-Server (S2S)] file transfers according to the schedules described in this section. Given these schedules and the cut-off times, you might see discrepancies with new segments between real-time and total segment numbers.

<table id="table_303BEBA0756F46DDAA98D366A5304374"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> File Type </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Inbound File Ingestion (offline data)</b> </p> </td> 
   <td colname="col2"> <p>File processing is executed twice per day. These procedures ingest data and prepare it for delivery. </p> <p>File delivery times vary because they are affected by the total amount of customer data that needs to be processed. You should expect a maximum latency of 48 hours between the moment the file is uploaded in <span class="keyword"> Audience Manager</span> and until the data is available for reporting and activation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Outbound (Export) Files</b> </p> </td> 
   <td colname="col2"> <p>File processing and delivery takes place once per day, at approximately 14:00 UTC. Keep in mind that processing and delivery are affected by the total number and size of these files. In some cases, there may be a delay in file processing for as long as 24-hours. When this happens, <span class="keyword"> Audience Manager</span> will send 2 files for a particular day instead of 1. We will notify our customers in the rare case where <span class="keyword"> Audience Manager</span> has to stop processing a file altogether. Given these conditions, it is difficult to estimate delivery times for outbound data. </p> <p>To determine if you've received a complete set of files, check the timestamp and look for any missing days. This is a 13-digit, UNIX UTC timestamp that records the time when the file was created. See <a href="../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md"> Real-Time Outbound Data Transfers</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Inbound Customer Data Ingestion FAQ](../faq/faq-inbound-data-ingestion.md)
