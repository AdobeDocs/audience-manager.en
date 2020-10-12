---
description: Describes the required fields, syntax, naming conventions and file sizes you need to follow when sending data to Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager / Amazon S3 directory.
seo-description: Describes the required fields, syntax, naming conventions and file sizes you need to follow when sending data to Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager / Amazon S3 directory.
seo-title: Amazon S3 Name and File Size Requirements for Inbound Data Files
solution: Audience Manager
title: Amazon S3 Name and File Size Requirements for Inbound Data Files
uuid: 3692a122-6ad5-468c-934e-53067bd8cf71
feature: Inbound Data Transfers
---

# [!DNL Amazon S3] Name and File Size Requirements for Inbound Data Files {#amazon-s-name-and-file-size-requirements-for-inbound-data-files}

Describes the required fields, syntax, naming conventions and file sizes you need to follow when sending data to [!DNL Audience Manager]. Set the names and sizes of your files according to these specifications when you send data to an [!DNL Audience Manager] / [!DNL Amazon S3] directory.

>[!NOTE]
>
>The text styles (`monospaced text`, *italics*, brackets `[ ]` `( )`, etc.) in this document indicate code elements and options. See [Style Conventions for Code and Text Elements](../../../reference/code-style-elements.md) for more information.

## File Name Syntax {#file-name-syntax}

[!DNL S3] file names contain the following required and optional elements:

* **[!DNL S3] prefix:**   `s3n://AWS_directory/partner_name/date=yyyy-mm-dd/` 

* **File name elements:**   `ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

For other accepted file name formats, see [Custom Partner Integrations](/help/using/integration/sending-audience-data/custom-partner-integrations.md). 

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>[!DNL Audience Manager] only processes [!DNL ASCII] and [!DNL UTF-8] encoded files.

### Name Elements

The table defines the elements in an [!DNL S3] file name.

<table id="table_455D174BAB9B494D973DA1023F22B962"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Name Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>AWS_directory</i> </code> </p> </td> 
   <td colname="col2"> <p>The path to and name of your Amazon S3 bucket. Contact your Account Manager for your S3 directory name, path, and credentials. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>date=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>A timestamp (based on UTC time) of when you send the files to your S3 bucket. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>An lD that tells <span class="keyword"> Audience Manager</span> if a data file contains your own user IDs, Android IDs, iOS IDs, or other IDs belonging to <a href="/help/using/features/global-data-sources.md"> global data sources</a>. Accepts the following options:</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>Data Source ID (also known as Data Provider ID):</b> This is a unique ID that Audience Manager assigns to a data source (refer to the Audience Manager <a href="/help/using/reference/ids-in-aam.md"> index of IDs </a>). Use this assigned ID in a file name when sending in data that contains your own user IDs. For example, <code>...ftp_dpm_21_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> to onboard data to IDs belonging to data source 21. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android IDs (GAID):</b> Use ID 20914 in a data file name if it contains Android IDs. You need to use the field <code><i>_DPID_TARGET_DATA_OWNER</i></code> when you use Android IDs. For example, <code>...ftp_dpm_20914_DPID_TARGET_DATA_OWNER_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that the data file contains Android IDs only and the IDs should qualify for the traits belonging to the <code><i>_DPID_TARGET_DATA_OWNER</i></code> data source.</li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOS IDs (IDFA):</b> Use ID 20915 in a data file name if it contains iOS IDs. You need to use the field <code><i>_DPID_TARGET_DATA_OWNER</i></code> when you use iOS IDs. For example, <code>...ftp_dpm_20915_DPID_TARGET_DATA_OWNER_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that the data file contains iOS IDs only and the IDs should qualify for the traits belonging to the <code><i>_DPID_TARGET_DATA_OWNER</i></code> data source.</li>
     <li> <b>IDs belonging to other global data sources</b>: You can onboard Roku IDs for Advertising (RIDA), Microsoft Advertising IDs (MAID), and other IDs. Use the ID corresponding to each data source, as described in the <a href="/help/using/features/global-data-sources.md"> global data sources article</a>.</li> 
    </ul> <p> <p>Note:  Do not mix ID types in your data files. For example, if your file name includes the Android identifier, don't put iOS IDs or your own IDs in the data file. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>This field tells Audience Manager which data source to onboard data to. This field is mandatory if you set the DPID to an Android ID or iOS ID or another ID belonging to global data sources. This lets <span class="keyword"> Audience Manager</span> link the file data back to your organization. </p> <p>For example: </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code> tells Audience Manager that you're qualifying customer IDs belonging to data source 33 for traits or signals belonging to data source 21. </li> 
     <li> <b>Android IDs (GAID):</b> <code>...ftp_dpm_20914_21_1234567890.sync</code> tells <span class="keyword"> Audience Manager</span> that the data file contains Android IDs only and the IDs should qualify for the traits belonging to data source 21.</li> 
     <li> <b>iOS IDs (IDFA):</b> <code>...ftp_dpm_20915_21_1234567890.sync</code> tells <span class="keyword"> Audience Manager</span> that the data file contains iOS IDs only and the IDs should qualify for the traits belonging to data source 21.</li>
     <li> <b>IDs belonging to other global data sources</b>: <code>...ftp_dpm_121963_21_1234567890.sync</code> tells <span class="keyword"> Audience Manager</span> that the data file contains Roku IDs only and the IDs should qualify for the traits belonging to data source 21. Use the ID corresponding to each data source, as described in the <a href="/help/using/features/global-data-sources.md"> global data sources article</a>.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner_name</i> </code> </p> </td> 
   <td colname="col2"> <p>The company or organization name you use in <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>A 10-digit, UTC UNIX timestamp in seconds. The timestamp helps make each file name unique. </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync|.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Synchronization options that include: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: Normal scenario when third-party data providers send traits on a per-user basis to be added or removed in the Audience Manager system. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: Lets data providers send a list of traits on a per-user basis that should overwrite all of this user's existing third-party traits for this data provider in the Audience Manager. You do not need to include all of your users in an overwrite file. Include only those users that you want to change. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>An integer. Used when you split large files into multiple parts to improve processing times. The number indicates which part of the original file you're sending in. </p> <p>For efficient file processing, split your data files as indicated: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Uncompressed: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Compressed: 200-300 MB </li> 
    </ul> <p>See the first 2 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md#file-name-examples"> file name examples</a> below. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>When sending files to Amazon S3, use gzip compression only. When compressed, these files get the <code> .gz</code> extension. Do not use .zip compression. </p> <p>Compressed files must be 3 GB or smaller. If your files are larger, please talk to Customer Care. Although Audience Manager can handle large files, we may be able to help you reduce the size of your files and make data transfers more efficient. See <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> File Compression for Inbound Data Transfer Files</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## File Name Examples {#file-name-examples}

The following examples show properly formatted file names. Your file names could look similar.

<ul class="simplelist"> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_567_1366545717.sync.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

You can [download](assets/ftp_dpm_1234_1445374061.overwrite) the sample file if you want additional examples. This file has been saved with the `.overwrite` file extension. Open it with a simple text editor.

## Accepted File Sizes {#accepted-file-sizes}

Consider the figures below for fastest/earliest processing of your files as well as for file size limitations when you send data to an [!DNL Audience Manager] / [!DNL Amazon S3] directory.  

<table id="table_59FCC63806684DF8BE54A1EAF224A234"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> File Type </th> 
   <th colname="col2" class="entry"> Optimal Size </th> 
   <th colname="col3" class="entry"> Maximum Size </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Compressed</b> </td> 
   <td colname="col2"> <p>200-300 MB </p> </td> 
   <td colname="col3"> <p>3 GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Uncompressed</b> </td> 
   <td colname="col2"> <p>1 GB </p> </td> 
   <td colname="col3"> <p>5 GB </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>The inbound data validation process will mark empty files as invalid and will not process them.

>[!MORELIKETHIS]
>
>* [FTP Name Requirements for Inbound Data Files](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)
