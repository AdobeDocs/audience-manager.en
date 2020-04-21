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


|Data Type|Description|
|---|---|
|Real-Time Data|Real-time numbers for today are for the hours 00:00 to 23:59:59 UTC from yesterday.|
|General Report Data|The data in the [General Reports](../reporting/general-reports.md#general-reports-overview) depends on the successful completion of other job processes and the amount of data received for a particular day. Most of the time, [!UICONTROL General Report] data should be updated by 18:00 UTC each day.|

## Inbound and Outbound File Transfers {#inbound-outbound-file-transfers}

[!DNL Audience Manager] processes and sends inbound and outbound [!UICONTROL Server-to-Server (S2S)] file transfers according to the schedules described in this section. Given these schedules and the cut-off times, you might see discrepancies with new segments between real-time and total segment numbers.

|File Type|Description|
|---|---|
|Inbound File Ingestion (offline data)|File processing is executed twice per day. These procedures ingest data and prepare it for delivery. File delivery times vary because they are affected by the total amount of customer data that needs to be processed. You should expect a maximum latency of 48 hours between the moment the file is uploaded in Audience Manager and until the data is available for reporting and activation.|
|Outbound (Export) Files|File processing and delivery takes place once per day, at approximately 14:00 UTC. Keep in mind that processing and delivery are affected by the total number and size of these files. In some cases, there may be a delay in file processing for as long as 24-hours. When this happens, Audience Manager will send 2 files for a particular day instead of 1. <p> We will notify our customers in the rare case where Audience Manager has to stop processing a file altogether. Given these conditions, it is difficult to estimate delivery times for outbound data. To determine if you've received a complete set of files, check the timestamp and look for any missing days. This is a 13-digit, UNIX UTC timestamp that records the time when the file was created.</p> See [Real-Time Outbound Data Transfers](../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md).|
|Ad Server Log Files | File processing is executed in near real time to ingest log file records as the hourly files are ready. The process to prepare the files for reporting is executed once a day. <p> File delivery times vary because they are affected by the total amount of customer data that needs to be processed. You should expect a maximum latency of 48 hours between the moment you upload the file to Audience Manager and the moment the data is available for reporting and activation.</p>|

>[!MORELIKETHIS]
>
>* [Inbound Customer Data Ingestion FAQ](../faq/faq-inbound-data-ingestion.md)
