---
description: Describes the required fields, syntax, and naming conventions used for file-based ID synchronization. Name and organize your file contents according to these specifications.
seo-description: Describes the required fields, syntax, and naming conventions used for file-based ID synchronization. Name and organize your file contents according to these specifications.
seo-title: Name and Content Requirements for ID Synchronization Files
solution: Audience Manager
title: Name and Content Requirements for ID Synchronization Files
uuid: bfe42af9-9149-4da3-830e-f227c4e610c2
index: y
internal: n
snippet: y
---

# Name and Content Requirements for ID Synchronization Files{#name-and-content-requirements-for-id-synchronization-files}

Describes the required fields, syntax, and naming conventions used for file-based ID synchronization. Name and organize your file contents according to these specifications.

Contents:

<ul class="simplelist"> 
 <li> <a href="../../../c-integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md#section_0AB70A4265EC478CB9C3540A6DD16000"> File Name Syntax and Examples </a> </li> 
 <li> <a href="../../../c-integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md#section_1DA6C74107E34CC0A4DCCFEDDDDDBCFF"> File Content Syntax and Examples </a> </li> 
 <li> <a href="../../../c-integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md#section_41255CCDC02440C285C03E8001FB7E90"> Synchronization Matches DPIDs to UUIDs </a> </li> 
 <li> <a href="../../../c-integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md#section_86EFF8C6AE40444A83F42411957CD809"> Other Format Requirements </a> </li> 
</ul>

>[!NOTE]
>
>The text styles ( `monospaced text`, *italics*, brackets [ ] ( ), etc.) in this document indicate code elements and options. See [Style Conventions for Code and Text Elements](https://marketing.adobe.com/resources/help/en_US/aam/code-style-elements.html) for more information.

## File Name Syntax and Examples {#section_0AB70A4265EC478CB9C3540A6DD16000}

<!-- 

c_file_based_id_sync.xml

 -->

ID file names contain the following required and optional elements:

`adobe_id_ *`MASTERDPID`*_ *`DPID[_DPID_DPID`*]_ *`TIMESTAMP`*.sync[. *`SPLIT_NUMBER`*][.gz]`

<table id="table_727A465D7C38419CA0750EF32DEDA2FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> adobe_id</span> </p> </td> 
   <td colname="col2"> <p>A static prefix that identifies the file as an ID file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> <span class="varname"> MASTERDPID</span> </span> </td> 
   <td colname="col2"> The master data provider ID is the parent ID of the DPIDs in the file name. Also, the first user ID in the data file corresponds to the master ID. The subsequent DPIDs are other identifiers that belong to the master. Synchronization maps DPIDs in the file name to UUIDs in the file. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> <span class="varname"> DPID</span> </span> </p> </td> 
   <td colname="col2"> <p>Data provider IDs. These IDs represent entities or data sources associated with the master DPID. Synchronization maps DPIDs in the file name to UUIDs in the file. </p> <p>The number of DPIDs in the file name must match the number of UUIDs in the data file. For example, say your file name contains a master DPID and 3 DPIDs. Your data file must include 4 corresponding columns of UUIDs, formatted as described in the file content section below. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> <span class="varname"> timestamp</span> </span> </td> 
   <td colname="col2"> <p>A 10-digit, UNIX timestamp in seconds. The timestamp helps make each file name unique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> .sync</span> </p> </td> 
   <td colname="col2"> <p>Indicates a normal, full synchronization. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph">[<span class="varname"> .SPLIT_NUMBER</span>]</span> </p> </td> 
   <td colname="col2"> <p>An integer. Used when you split large files into multiple smaller files. This helps improve processing times. The number indicates which part of the original file you're sending in. See the file name examples below. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> [.gz]</span> </p> </td> 
   <td colname="col2"> <p>Specifies that your file is compressed with optional gzip compression. </p> </td> 
  </tr> 
 </tbody> 
</table>

**File Name Examples**

The following examples show properly formatted files names. Your file names could look similar.

<ul class="simplelist"> 
 <li> <span class="codeph"> adobe_id_111_222_333_444_1454442149.sync</span> </li> 
 <li> <span class="codeph"> adobe_id_123_898_456_1454442149.sync.1.gz</span> </li> 
 <li> <span class="codeph"> adobe_id_123_898_456_1454442149.sync.2.gz</span> </li> 
</ul>

## File Content Syntax and Examples {#section_1DA6C74107E34CC0A4DCCFEDDDDDBCFF}

The contents of an ID file include the following elements:

` *`UUID`* <tab> *`UUID`* <tab> *`UUID`* <tab> *`UUID`*`

The file contains user IDs (UUID). In each row, separate the IDs with a tab. The following example shows a properly formatted ID file. Your contents could look similar.

```
abc123 def456 ghi789 xyz987

```

## Synchronization Matches DPUUIDs to UUIDs {#section_41255CCDC02440C285C03E8001FB7E90}

The purpose of an ID sync file is to sync the [DPUUIDs](../../../reference/ids-in-aam.md#reference_D55EC67D86664B7499F3257BB870FEC8) from your own Data Sources with [!DNL Audience Manager] UUIDs. Synchronization maps the DPUUIDs from the master DPID and its related DPIDs to the [!DNL Audience Manager] UUIDs. Where you put the IDs in the file name and body determines how these identifiers are mapped to each other. For example, take the two sample files shown here:

* **File 1:** `adobe_id_0_12345_1476312152.sync` 

* **File 2:**  `adobe_id_12345_67890_1476312876.sync`

Given the sample name and contents, the IDs map together like this:

**File 1** ( [Download sample file](https://marketing.adobe.com/resources/help/en_US/aam/downloads/adobe_id_0_12345_1476312152.sync))

|  DPID 0 = Adobe Audience Manager UUIDs  | DPID 12345  |
|---|---|
|  68079982765673198504052656074456196039  | XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-TTrj6E4njaMR38  |
|  67412682083411995725538770443620307584  | XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70  |
|  89159024796760343733111707646026765593  | XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM  |
|  66552757407517449462805881945288602094  | XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M  |
|  66184778222667870903738139438735041506  | XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw  |

Step 1: the ID sync process will sync the DPUUIDs from DPID 12345 with the [!DNL Audience Manager] UUIDs in the left column. Note that the DPID "0" in the file name represents [!DNL Audience Manager] UUIDs.

**File 2** ( [Download sample file](https://marketing.adobe.com/resources/help/en_US/aam/downloads/adobe_id_12345_67890_1477846458.sync))

|  DPID 12345  | DPID 67890  |
|---|---|
|  XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-TTrj6E4njaMR38  | 4598060374  |
|  XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70  | 4581274262  |
|  XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM  | 4392434426  |
|  XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M  | 2351382994  |
|  XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw  | 4601584763  |

Step 2: the DPUUIDs from DPID 12345 have been synced in step 1 with the Audience Manager UUIDs. What this ID sync will do is sync the DPUUIDs from DPID 67890 with the Audience Manager UUIDs from step 1.

## Other Format Requirements {#section_86EFF8C6AE40444A83F42411957CD809}

* User IDs cannot

    * Have tabs in the ID itself. Tabs are used only to separate individual IDs in the data file. 
    * Contain personally identifiable information (PII). 
    * Use URL encoding. Pass in unencoded IDs only.

* Any rows that end with tabs or spaces will not be processed or realized. As a rule, make sure you keep the end of the rows clear.

