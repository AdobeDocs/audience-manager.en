---
description: Describes the required fields, syntax, naming conventions and file sizes you need to follow when sending data to Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager FTP directory.
seo-description: Describes the required fields, syntax, naming conventions and file sizes you need to follow when sending data to Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager FTP directory.
seo-title: FTP Name and File Size Requirements for Inbound Data Files
solution: Audience Manager
title: FTP Name and File Size Requirements for Inbound Data Files
uuid: 49eaafac-5cb0-482f-872a-84c056016bdb
---

# FTP Name and File Size Requirements for Inbound Data Files{#ftp-name-and-file-size-requirements-for-inbound-data-files}

Describes the required fields, syntax, naming conventions and file sizes you need to follow when sending data to Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager FTP directory.

>[!NOTE]
>
>The text styles ( `monospaced text`, *italics*, brackets [ ] ( ), etc.) in this document indicate code elements and options. See [Style Conventions for Code and Text Elements](../../../reference/code-style-elements.md#reference_59D0BD0EDB424A65853460D91CCA35D9) for more information.

## File Name Syntax {#section_8E0F0FCC8FCB484E89F09654A03295FB}

FTP file names contain the following required and optional elements:

`fftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

>[!NOTE] {importance="high"}
>
>[!DNL Audience Manager] only processes ASCII and UTF-8 encoded files.

**Name Elements**

The table defines the elements in an FTP file name.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> File Name Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> <span class="varname"> DPID</span> </span> </p> </td> 
   <td colname="col2"> <p>An lD that tells <span class="keyword"> Audience Manager</span> if a data file contains your own user IDs or Android or iOS IDs. Accepts the following options: </p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>Data Partner ID:</b> This is a unique ID Audience Manager assigns to your company or organization. Use this assigned ID in a file name when sending in data that contains your own user IDs. For example, <span class="codeph">...ftp_dpm_21_123456789.sync</span> tells <span class="keyword"> Audience Manager</span> that a partner with ID 21 sent the file and it contains user IDs assigned by that partner. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android IDs (GAID):</b> Use ID 20914 in a data file name if it contains Android ID. For example, <span class="codeph">...ftp_dpm_20914_123456789.sync</span> tells <span class="keyword"> Audience Manager</span> that the data file contains Android IDs only. </li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOS IDs (IDFA):</b> Use ID 20915 in a data file name if it contains iOS IDs. For example, <span class="codeph">...ftp_dpm_20915_123456789.sync</span> tells <span class="keyword"> Audience Manager</span> that the data file contains iOS IDs only. </li> 
    </ul> <p> <p>Note:  Do not mix ID types in your data files. For example, if your file name includes the Android identifier, don't put iOS IDs or your own IDs in the data file. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> <span class="varname"> _DPID_TARGET_DATA_OWNER</span> </span> </p> </td> 
   <td colname="col2"> <p>A placeholder for an ID. For example, you could set it to your <span class="keyword"> Audience Manager</span> ID if you set the DPID to a data source ID or an Android or iOS ID. This lets <span class="keyword"> Audience Manager</span> link the file data back to your organization. </p> <p>For example: </p> 
    <ul id="ul_55EBBCB11F2B4A858AEFBFA1CD99E286"> 
     <li id="li_3404428F4E3D49A5AB6EDF56310D923F"> <span class="codeph">...ftp_dpm_33_21_1234567890.sync</span> shows a partner with ID 21 has sent in data from a data source that uses ID 33. </li> 
     <li id="li_CF8D5AF678764E9984A088FD5D7BBFB6"> <span class="codeph">...ftp_dpm_20914_21_1234567890.sync</span> shows a partner with ID 21 has sent in data that contains Android IDs. </li> 
     <li id="li_3D73168391D7443BADDF27153090274D"> <span class="codeph">...ftp_dpm_20915_21_1234567890.sync</span> shows a partner with ID 21 has sent in data that contains iOS IDs. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> (.sync |.overwrite)</span> </p> </td> 
   <td colname="col2"> <p>Synchronization options that include: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <span class="codeph"> sync</span>: Normal scenario when third-party data providers send traits on a per-user basis to be added or removed in the Audience Manager system. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <span class="codeph"> overwrite</span>: Lets customers and data providers send a list of traits on a per-user basis that should overwrite all of this user's existing traits for a given data source in Audience Manager. You do not need to include all of your users in an overwrite file. Include only those users that you want to change. Traits that are not assigned to the target data source will not be erased. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> ftp_dpm_</span> </p> </td> 
   <td colname="col2"> <p>The path to and name of your <span class="keyword"> Audience Manager</span> FTP directory. Contact your Account Manager for the FTP directory and credentials. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph">[<span class="varname"> SPLIT_NUMBER</span></span>] </p> </td> 
   <td colname="col2"> <p>An integer. Used when you split large files into multiple parts to improve processing times. The number indicates which part of the original file you're sending in. </p> <p>For efficient file processing, split your data files as indicated: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Uncompressed: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Compressed: 200-300 MB </li> 
    </ul> <p>See the first 2 <a href="../../../c-integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#section_0BBFF96B9DEB48F0B863A109DD3AED99"> file name examples</a> below. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> <span class="varname"> TIMESTAMP</span> </span> </p> </td> 
   <td colname="col2"> <p>A 10-digit, UTC UNIX timestamp in seconds. The timestamp helps make each file name unique. </p> 
    <draft-comment> 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> [.gz]</span> </p> </td> 
   <td colname="col2"> <p>Gzip is the allowed compression format for an FTP file name. If you use file compression, make sure the file name has the proper extension. </p> <p>Compressed files must be 1 GB or smaller. If your files files are larger, please talk to Customer Care. Although Audience Manager can handle large files, we may be able to help you reduce the size of your files and make data transfers more efficient. See <a href="../../../c-integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md#concept_7D6FA8BA759143EFBEDB16589BF6EC40"> File Compression for Inbound Data Transfer Files</a> . </p> </td> 
  </tr> 
 </tbody> 
</table>

## File Name Examples {#section_0BBFF96B9DEB48F0B863A109DD3AED99}

The following examples show properly formatted file names. Your file names could look similar.

<ul class="simplelist"> 
 <li> <span class="codeph"> ftp_dpm_478_1366545717.sync.1.gz</span> </li> 
 <li> <span class="codeph"> ftp_dpm_478_1366545717.sync.2.gz</span> </li> 
 <li> <span class="codeph"> ftp_dpm_478_1366545717.overwrite</span> </li> 
</ul>

[Download](https://marketing.adobe.com/resources/help/en_US/aam/downloads/ftp_dpm_1234_1445374061.overwrite) the sample file if you need additional examples. This file is saved with the `.overwrite` file extension. Open it with a simple text editor.

## Accepted File Sizes {#section_758E1B942B334DE1B76F0EBC846303E2}

Consider the figures below for fastest/earliest processing of your files as well as for file size limitations when you send data to an [!DNL Audience Manager] / FTP directory.  

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
   <td colname="col3"> <p>1 GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Uncompressed</b> </td> 
   <td colname="col2"> <p>1 GB </p> </td> 
   <td colname="col3"> <p>5 GB </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [Amazon S3 Name Requirements for Inbound Data Files](../../../c-integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md#concept_B3CAF442BFFE4823B76A5D0D91DF9942)
