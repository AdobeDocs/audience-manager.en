---
description: A data file contains impression, click, or conversion data. When formatted properly, you can import this data into Audience Manager and view it in the Audience Optimization reports. Format your data files according to these specifications in this section.
seo-description: A data file contains impression, click, or conversion data. When formatted properly, you can import this data into Audience Manager and view it in the Audience Optimization reports. Format your data files according to these specifications in this section.
seo-title: Data Files for Audience Optimization Reports
solution: Audience Manager
title: Data Files for Audience Optimization Reports
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15fe04c379
---

# Data Files for Audience Optimization Reports{#data-files-for-audience-optimization-reports}

A data file contains impression, click, or conversion data. When formatted properly, you can import this data into Audience Manager and view it in the Audience Optimization reports. Format your data files according to these specifications in this section.

## Overview {#overview}

A properly named and formatted data file lets you import impression, click, or conversion data into the [Audience Optimization Reports](../../../reporting/audience-optimization-reports/audience-optimization-reports.md). This is useful when working with a partner who is not integrated with [!DNL Audience Manager] and you want to work with their data in that report suite. This process requires separate files for impression, click, and conversion data. Do not mix these events in a single file.

A data file must be accompanied by a metadata file. The metadata file contents match data file information to related, human-readable labels in the report menus. For more information, see [Overview and Mappings for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).

## Naming Conventions for Data Files {#naming-conventions}

The following syntax defines the structure of a well-formed data file name. Note, *italics* indicates a variable placeholder that changes depending on the file contents.

**Syntax:** <pre><code><i>event type</i>_<i>yyyymmdd</i></code></pre>

In a file name:

* The event type indicates the file contains impressions, clicks, or conversions. Create a separate file for each event type. 
* An underscore separates the event type and a year-month-date timestamp.
* Before uploading, compress your files using gzip and save them with the `.gz` file extension.

Given these requirements, name your data files based on their contents like this:

* Impression data: <pre><code>impressions_<i>yyyymmdd<i>.gz</code></pre>
* Click data: <pre><code>clicks_<i>yyyymmdd</i>.gz</code></pre>
* Conversion data: <pre><code>conversions_<i>yyyymmdd</i>.gz</code></pre>

## Content Format for Data Files {#content-format}

The following syntax defines the content structure in well-formed data file. Note, *italics* indicates a variable placeholder and is replaced with an label in an actual data file.

**Syntax:** <pre><code><i>header label 1</i> | <i>header label 2</i> ... <i>header label n</i> | <i>version</i></code></pre>

In the file contents:

* The header labels must appear in the order as shown in the table below. Impressions and clicks use the same labels. Conversion files contain extra headers. 
* If you don't have data for a particular column, populate that field with a `-1`.

* Files *must* end with a version number. The current version is 1.1.
* Separate file headers and contents with the non-printing ASCII 001 character. If you cannot use ASCII 001, then separate the headers and data with a tab delimiter. As these are non-printing characters, the syntax example above shows a pipe `"|"` for display purposes only.

**Field Labels**

The table below lists and describes the column headers for your data file. Headers are case-sensitive and must appear as ordered in the table. All data types are integers (INT) unless indicated otherwise.

<table id="table_D8C5068741C3460380505F95F3016757"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Label </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Time-Stamp </p> </td> 
   <td colname="col2"> <p>A UTC date and time for the impression, click, or conversion event. Use the <code> yyyy-dd-mm hh:mm:ss</code> format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>User-ID </p> </td> 
   <td colname="col2"> <p>Your ID for a site visitor, also known as the <span class="term"> data provider unique user ID</span> or DPUUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Advertiser-ID </p> </td> 
   <td colname="col2"> <p>The data source ID or integration code for your advertiser. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>BU-ID </p> </td> 
   <td colname="col2"> <p>Business unit ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campaign-ID </p> </td> 
   <td colname="col2"> <p>Campaign ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creative-ID </p> </td> 
   <td colname="col2"> <p>Creative ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Site-ID </p> </td> 
   <td colname="col2"> <p>Site ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Placement-ID </p> </td> 
   <td colname="col2"> <p> Numeric placement ID from the ad server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Insertion-Order-ID </p> </td> 
   <td colname="col2"> <p>Insertion Order ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tactic-ID </p> </td> 
   <td colname="col2"> <p>Tactic ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vertical-ID </p> </td> 
   <td colname="col2"> <p>ID for an industry vertical or category. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quantity </p> </td> 
   <td colname="col2"> <p> The number of items sold in a conversion event. </p> <p> <i>For conversion data files only.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Revenue </p> </td> 
   <td colname="col2"> <p>Purchase or other conversion amount. Data type: Float. </p> <p> <i>For conversion data files only.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Other-Data </p> </td> 
   <td colname="col2"> <p>URL of the conversion landing page. Data type: String. </p> <p> <i>For conversion data files only.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Event-Type </p> </td> 
   <td colname="col2"> <p>Conversion type. Indicates whether a conversion is matched or not. Options include: </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>: Impression </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>: Click </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>: Unattributed or unknown </li> 
    </ul> <p> <i>For conversion data files only.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Version </p> </td> 
   <td colname="col2"> <p>A required version number that appears at the end of every row in an impression, click, or conversion data file. The current version is 1.1. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Delivery Methods for Data Files {#delivery-methods}

Upload your impression, click, or conversion data files to an Amazon S3 directory for your [!DNL Audience Manager] account. Refer to this section for information about delivery/directory paths, file processing times, and updates.

**Delivery Path Syntax and Examples**

Data is stored in a separate namespace for each customer in an Amazon S3 directory. The file path follows the syntax shown below. Note, *italics* indicates a variable placeholder. Other elements are constants or keys and do not change.

**Syntax:** <pre><code>.../log_ingestion/pid= <i>AAM ID<i>/dpid= <i>d_src</i>/logs/ <i>file type</i>_<i>yyyymmdd</i></code></pre>

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
   <td colname="col2"> <p>This key-value pair contains the data source ID passed in on an event call. It identifies the agency the data comes from and ties that data to a supporting metadata file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> logs</code> </p> </td> 
   <td colname="col2"> <p> A higher level directory for data files. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>file type</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>A file type name that indicates what sort of data it contains and a delivery timestamp. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Sample Upload Path and File Name**

When you upload a file, the path will look similar to this:

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**File Processing Times and Updates**

Data files are processed four times a day, at regular intervals.

To update your data, send in a file that contains all of the impressions, clicks, or conversions for a particular day. In this case, a day is the 24-hour period from one midnight to the next. As a best practice, you may want to use UTC time to define your day interval.

## Next Steps {#next-steps}

Review the requirements for naming and creating metadata files. To get started, see [Overview and Mappings for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md). 
