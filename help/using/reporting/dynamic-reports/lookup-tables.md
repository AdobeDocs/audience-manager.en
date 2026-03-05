---
description: Put data in Delivery Performance report log files into tables that contain IDs only. Put non-ID metadata in separate lookup tables to help reduce file size and processing times.
seo-description: Put data in Delivery Performance report log files into tables that contain IDs only. Put non-ID metadata in separate lookup tables to help reduce file size and processing times.
seo-title: Improve Log File Processing Times with Lookup Tables
solution: Audience Manager
title: Improve Log File Processing Times with Lookup Tables
uuid: ffc77618-474b-455e-9c91-15b32fc151a5
feature: Reporting Reference
exl-id: bab51406-21e9-4033-90d4-6100daf6a311
TQID: https://experienceleague.adobe.com/9eLSmpl5-daNV5NgXrPfLThoIlMibaOtbgrsuqfkeCI
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: a99472c1-6aae-4c7a-8aa0-f60636369620
    internal-label: Reporting
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
    internal-label: APIs and SDKs
subfeature_v2:
  - id: a49258d4-867f-4130-b875-d72c001bdf6c
    internal-label: Overlap Reports
  - id: ec0be1ae-7ea9-4f62-869a-963a97d2edc1
    internal-label: Reporting reference
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
---
# Improve Log File Processing Times with Lookup Tables{#improve-log-file-processing-times-with-lookup-tables}

Put data in Delivery Performance report log files into tables that contain IDs only. Put non-ID metadata in separate lookup tables to help reduce file size and processing times.

<!-- 

c_lookup_tables.xml

 -->

## Log File Metadata Increases File Size and Processing Time

A typical log file used by the [!UICONTROL Delivery Performance] report usually contains thousands of rows and dozens of columns. It consists of numeric IDs and human-readable information such as names for creatives, advertisers, insertion orders, etc.

This non-ID information is referred to as *`metadata`* (i.e., information about other information) and gets written in each row of the log file.

However, the [!UICONTROL Delivery Performance] report mainly works with the IDs in the log file. The metadata is useful, but repetitious. It increases file size and data ingestion times.

## Reduce File Size and Shorten Processing Time With Index Tables

To help improve performance, your main data file should contain IDs only. Put metadata in a separate lookup (or index) table and link those records to the main file with a key variable common to both.

## How Lookup Tables Reduce File Size

Let's say you have a data file that looks similar to the one below.  

|  User ID  | Ad ID  | Ad Name  | Order ID  | Order Name  | Advertiser ID  | Advertiser Name  |
|---|---|---|---|---|---|---|
|  1  | 111  | Shoe A  | 456  | Sneakers  | 27  | Company A  |
|  2  | 111  | Shoe A  | 456  | Sneakers  | 27  | Company A  |
|  3  | 111  | Shoe A  | 456  | Sneakers  | 27  | Company A  |
|  4  | 222  | Shoe B  | 789  | Hiking  | 14  | Company B  |
|  5  | 222  | Shoe B  | 789  | Hiking  | 14  | Company B  |

<br>&nbsp;

Here's the same log file with the metadata removed. The file is smaller and easier to process when it consists of IDs only.  

|  User ID  | Ad ID  | Order ID  | Advertiser ID  |
|---|---|---|---|
|  1  | 111  | 456  | 27  |
|  2  | 111  | 456  | 27  |
|  3  | 111  | 456  | 27  |
|  4  | 222  | 789  | 14  |
|  5  | 222  | 789  | 14  |

<br>&nbsp;

The lookup file below holds the metadata and can be linked back to the main file with the Ad ID. Note the size as well. Instead of repeating each advertiser several times, you only need one reference for each.  

|  Ad ID  | Ad Name  | Order Name  | Advertiser Name  |
|---|---|---|---|
|  111  | Shoe A  | Sneakers  | Company A  |
|  222  | Shoe B  | Hiking  | Company B  |

## APIs Can Eliminate the Need for Lookup Tables

If your ad serving system has an API, you might not need to send metadata in a lookup file. We may be able to get that information through the API. When this is the case, your log files should contain IDs only. We'll work with you to determine if metadata can be obtained through an API.
