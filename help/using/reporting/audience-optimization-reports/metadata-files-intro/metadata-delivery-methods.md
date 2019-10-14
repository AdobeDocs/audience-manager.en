---
description: Send or update metadata files by sending them to a special Amazon S3 directory for your Audience Manager account. Refer to this section for information about delivery/directory paths, file processing times, and updates.
seo-description: Send or update metadata files by sending them to a special Amazon S3 directory for your Audience Manager account. Refer to this section for information about delivery/directory paths, file processing times, and updates.
seo-title: Delivery Methods for Metadata Files
solution: Audience Manager
title: Delivery Methods for Metadata Files
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
---

# Delivery Methods for Metadata Files{#delivery-methods-for-metadata-files}

Send or update metadata files by sending them to a special Amazon S3 directory for your Audience Manager account. Refer to this section for information about delivery/directory paths, file processing times, and updates.

## Delivery Path Syntax and Examples {#syntax}

Data is stored in separate namespace for each customer in an Amazon S3 directory. The file path follows the syntax shown below. Note, *italics* indicates a variable placeholder. Brackets `[ ]` indicate optional parameters. The other elements are constants and do not change.

**Syntax:**
<pre><code>.../log_ingestion/pid=<i>AAM ID</i>/dpid= <i>d_src</i>/[meta|status]/ <i>yyyymmdd</i>_ <i>parent ID</i>_ <i>child ID</i></code></pre>

The following table defines each of these elements in a file delivery path.

<table id="table_E3DB873D4CB3479AA7173838EB9898CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> File Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> .../log_ingestion/</code> </p> </td> 
   <td colname="col2"> <p>This is the start of the directory storage path. You'll receive the full path when everything is set up. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>This key-value pair that contains your <span class="keyword"> Audience Manager</span> customer ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>This key-value pair contains the data source ID passed in on an event call. The data source ID is the value that ties all the contents in your file to the actual data it belongs to. </p> <p>For example, say you have a creative with the ID 123 and the name "Advertiser Creative A." As an event call only passes in the ID you need to include "Advertiser Creative A" in the metadata file. The campaign and creative belong to a data source. The data source ID is what ties these together and lets us accurately associate file contents to an ID sent in on an event call. See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names"> How Event Call IDs Determine File Names, Contents, and Delivery Paths</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>yyyymmdd</i>_<i>parent ID</i>_<i>child ID</i></code> </p> </td> 
   <td colname="col2"> <p>This is the file name. See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Naming Conventions for Metadata Files</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## File Processing Times and Updates {#processing-times}

Metadata files are processed four times a day, at regular intervals.

To update your metadata records, just send a file that contains new information. You don't need to send full updates each time. 
