---
description: Describes the required fields, syntax, and conventions used to name an outbound data file.
seo-description: Describes the required fields, syntax, and conventions used to name an outbound data file.
seo-title: Outbound Data File Name  Syntax and Examples
solution: Audience Manager
title: Outbound Data File Name  Syntax and Examples
uuid: effdcaf6-c37c-45f3-9d2f-a938a9da47a6
feature: Outbound Data Transfers
exl-id: 0944da72-5a8d-45a2-951e-b2988eb3d490
---
# Outbound Data File Name: Syntax and Examples{#outbound-data-file-name-syntax-and-examples}

Describes the required fields, syntax, and conventions used to name an outbound data file.

<!-- c_name_reqs_outbound.xml -->

>[!NOTE]
>
>The style elements (`monospaced text`, *italics*, brackets `[ ]` `( )`, etc.) in this document indicate code elements and options. See [Style Conventions for Code and Text Elements](../../../reference/code-style-elements.md) for more information.

## Syntax and File Name Elements {#syntax-file-name}

Outbound file names contain the following elements. All of the elements below are optional.

```
[SYNC_TYPE][_DID][_MASTER_DPID][_PID_ALIAS][_SYNC-MODE][_TIMESTAMP]SPLITNUM.sync[.gz]
```

### Parameters

The table defines the elements in an outbound data file name.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> File Name Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_TYPE </i></code> </p> </td> 
   <td colname="col2"> <p>Refers to the data transfer methods. Transfer methods include: </p> 
    <ul id="ul_4E0CFC7A34E04E2FA216A07E3654D6EE"> 
     <li id="li_0066B99222A64BE9975AE2E91511FB77">FTP - Transfer using SFTP </li> 
     <li id="li_646767FE8AD247B88D0DD5461349F019"> <span class="keyword"> Amazon S3 </span> - Transfer to <span class="keyword"> Amazon AWS </span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DID </i></code> </p> </td> 
   <td colname="col2"> <p>Destination ID. </p> <p>In <span class="keyword"> Audience Manager </span>, a destination is the instance of the integration where you can map your targetable segments. Customers can have multiple destinations, depending on the business requirement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>MASTER_DPID </i></code> </p> </td> 
   <td colname="col2"> <p>Data-provider or data source ID. This ID identifies the type of User ID present in the file content. Most common User ID keys are: </p> <p> 
     <ul id="ul_CC22D019ECED4B17A7695708001F2C1B"> 
      <li id="li_94DAFA169380405981AFEF1B581997E6">20914 - <span class="keyword"> Google Advertiser ID </span> (raw, unhashed) </li> 
      <li id="li_DE74BE06331C49CF87606A192D815B96">20915 - <span class="keyword"> Apple ID for Advertisers </span> (raw, unhashed) </li> 
      <li id="li_E0A033FEC3174EF08E93EB7C65266337">Vendor ID - 3rd party user IDs (web/cookie) </li> 
     </ul> </p> <p>See <a href="https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/global-data-sources.html">Global Data Sources</a> for more details.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>PID_ALIAS </i></code> </p> </td> 
   <td colname="col2"> The customer identifier from the 3rd party platform. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_MODE </i></code> </p> </td> 
   <td colname="col2"> <p>Sync mode is a macro placeholder that adds a label to the file name based on synchronization type. Synchronization types include full and incremental. They'll appear in the file name as <code> iter </code> or <code> full </code>. </p> 
    <ul id="ul_3B3585CEF1434951B6FDCDD29E5013CD"> 
     <li id="li_947D94E9CFAC4041AC1AAEB191805529"> <code> iter </code>: Indicates an "iterative" or incremental synchronization. An incremental file contains only new data collected since the last synchronization.. </li> 
     <li id="li_13ADB3B3346943DAA767A1F416482D3C"> <code> full </code>: Indicates a "full" synchronization. A fully synchronized file contains old data and any new data collected since the last synchronization. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>TIMESTAMP </i></code> </p> </td> 
   <td colname="col2"> <p>A 13-digit UNIX timestamp in milliseconds, in the UTC time zone. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>SPLITNUM</i></code></p> </td> 
   <td colname="col2"> <p>An integer. Identifies part of a file that's been split into multiple parts to improve processing times. The number indicates which part of the original file the data belongs to.</p>  <p>The integer must be at least 3 digits long, preceded by zeros, if the split size is lower than 100 parts.</p>  <p>The original file will not have any split number. The first split file will end with 001. See examples below. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>.gz (optional) </i></code> </p> </td> 
   <td colname="col2"> <p>GZIP compression. </p> </td> 
  </tr> 
 </tbody> 
</table>

## File Name Examples {#file-name-examples}

### Scenario 1

Files sent over to an [!DNL Amazon S3] location, with *`PID_ALIAS="XYZCustomer"`* and with [!DNL Google Advertiser IDs] in the file content.

E.g. incremental files:

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000001.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000002.sync.gz </code> </li> 
</ul>

E.g. full files:

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000001.sync.gz </code> </li> 
</ul>

### Scenario 2

Files sent over to [!DNL FTP] location, without *`PID_ALIAS`* and with [!DNL Apple Advertiser IDs] in the file content:

E.g. incremental files:

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_iter_1486140843000001.sync.gz </code> </li> 
</ul>

E.g. full files:

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_full_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_full_1486140843000001.sync.gz </code> </li> 
</ul>

**Scenario 3**: Files sent over to [!DNL FTP] location, with *`PID_ALIAS="XYZCustomer"`* and with 3rd party User ID in the file content ( *`Vendor ID=45454`*):

E.g. incremental files:

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
</ul>

E.g. full files:

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200001.sync.gz </code> </li> 
</ul>

## Outbound Data File Contents: Syntax and Parameters {#outbound-contents-syntax}

Describes the required fields, syntax, and conventions used to organize information in an outbound data file. Format your data according to these specifications.

<!-- c_outbound_data_file.xml -->

>[!NOTE]
>
>The style elements (`monospaced text`, *italics*, brackets `[ ]` `( )`, etc.) in this document indicate code elements and options. See [Style Conventions for Code and Text Elements](../../../reference/code-style-elements.md) for more information.

### Syntax

Fields in the data file appear in this order:

`UUID<SPACE>SEGMENT_1,SEGMENT_2<SPACE>REMOVED_SEGMENT_,...`

### Parameters

The table lists variables that define the contents of a data file.

<table id="table_109BA747CFDA40108370EFEB208C7E11"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>UUID </i></code> </p> </td> 
   <td colname="col2"> <p>A unique user ID assigned by <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>&lt;SPACE&gt; </i></code> </p> </td> 
   <td colname="col2"> <p>Separate the UUID and segment data with a space </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>The segment ID that a visitor belongs to. Separate multiple segments with a comma. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>REMOVED_SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>The segment ID from which the user was disqualified. Separate multiple segments with a comma. With a full synchronization, you can ignore the removed segments because the data file will contain the complete list of current segments for the user. Usually, you want to know about segments a user belongs to rather than those they've been removed from. See also <a href="../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md#outbound-data-file-name-syntax-and-examples"> Outbound Data File Name: Syntax and Examples </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Example: Basic File Format

A properly formatted data file could look similar to the following sample. This file entry indicates a user qualifies for segments 24, 26, and 27. As required, a space separates the `UUID` and segment IDs. Another space separates the sets of segment IDs. In this example, a user belongs to segments 24, 26, and 27. They've been removed from segments 25 and 28.

```
59767559181262060060278870901087098252  24,26,27  25,28
```
