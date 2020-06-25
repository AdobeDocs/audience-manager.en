---
description: Send or update metadata files by sending them to a special Amazon S3 directory for your Audience Manager account. Refer to this section for information about delivery/directory paths, file processing times, and updates.
seo-description: Send or update metadata files by sending them to a special Amazon S3 directory for your Audience Manager account. Refer to this section for information about delivery/directory paths, file processing times, and updates.
seo-title: Delivery Methods for Metadata Files
solution: Audience Manager
title: Delivery Methods for Metadata Files
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
feature: log files
---

# Delivery Methods for Metadata Files{#delivery-methods-for-metadata-files}

Send or update metadata files by sending them to a special [!DNL Amazon S3] directory for your Audience Manager account. Refer to this section for information about delivery/directory paths, file processing times, and updates.

>[!IMPORTANT]
>
> Contact your Audience Manager consultant or Customer Care to get started and set up an [!DNL Amazon S3] directory for your metadata files.

## Delivery Path Syntax and Example {#syntax}

Data is stored in separate namespace for each customer in an [!DNL Amazon S3] directory. The file path follows the syntax shown below. Note, angle brackets `<>` indicate a variable placeholder. The other elements are constants and do not change.

**Syntax:**

```
.../log_ingestion/pid=<AAM ID>/dpid=<d_src>/meta/<yyyymmdd_0_child ID>
```

**Example:**

```
.../log_ingestion/pid=1121/dpid=3342/meta/20200112_0_4
```

<br>&nbsp;

The following table defines each of these elements in a file delivery path.


File Parameter | Description  |
---------|----------|
 `.../log_ingestion/` | This is the start of the directory storage path. You'll receive the full path when everything is set up. |
 `pid=<AAM ID>` | This key-value pair contains your Audience Manager customer ID. |
 `dpid=<d_src>` |  This key-value pair contains the data source ID passed in on an event call. The data source ID is the value that ties all the contents in your file to the actual data it belongs to. </br> For example, say you have a creative with the ID 123 and the name "Advertiser Creative A." As an event call only passes in the ID you need to include "Advertiser Creative A" in the metadata file. The campaign and creative belong to a data source. The data source ID is what ties these together and lets us accurately associate file contents to an ID sent in on an event call. See [How Event Call IDs Determine File Names, Contents, and Delivery Paths](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names). |
 `<yyyymmdd_0_child ID>` | This is the file name. See [Naming Conventions for Metadata Files](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). |

## File Processing Times and Updates {#processing-times}

Metadata files are processed four times a day, at regular intervals.

To update your metadata records, just send a file that contains new information. You don't need to send full updates each time. 
